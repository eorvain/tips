# tips developpement iOS

# Collection View Controller

```

import UIKit

final class MyViewController: UIViewController{
    private let collectionView: UICollectionView

    private lazy var collectionView: UICollectionView = {
        let view = UICollectionView(frame: CGRect.zero, collectionViewLayout: layout)
        view.dataSource = self
        view.delegate = self
        view.register(EventCollectionViewCell.self, forCellWithReuseIdentifier: "cellid")
        print("collection view built")
        return view
    }()
    
    private lazy var layout: UICollectionViewFlowLayout = {
        let layout = UICollectionViewFlowLayout()
        layout.scrollDirection = .vertical
        //Will be overriden by UICollectionViewDelegateFlowLayout
        layout.sectionInset = UIEdgeInsets(top: 10, left: 10, bottom:10, right: 10)
        layout.itemSize = CGSize(width: 200, height: 150)
        layout.minimumLineSpacing = 10.0
        layout.minimumInteritemSpacing = 10.0
        print("layout built")
        return layout
    }()
    
    //MARK: - Lifecycle
    deinit{
        print("dealloc \(self)")
    }
        
    override func viewDidLoad() {
        super.viewDidLoad()
        view.addSubview(collectionView)
        
        buildStyle()
        buildConstraints()
    }
    
    func buildStyle(){
    }
    
    func buildConstraints(){
        collectionView.translatesAutoresizingMaskIntoConstraints = false
        //let guide = view.safeAreaLayoutGuide
        let guide = view!
        NSLayoutConstraint.activate([
            collectionView.topAnchor.constraint(equalTo: guide.topAnchor),
            collectionView.bottomAnchor.constraint(equalTo: guide.bottomAnchor),
            collectionView.leftAnchor.constraint(equalTo: guide.leftAnchor),
            collectionView.rightAnchor.constraint(equalTo: guide.rightAnchor),
        ])
    }
}

extension MyViewController: UICollectionViewDelegate{
    
}

extension MyViewController: UICollectionViewDataSource{
    func numberOfSections(in collectionView: UICollectionView) -> Int {
        return 1
    }
    
    func collectionView(_ collectionView: UICollectionView, numberOfItemsInSection section: Int) -> Int {
        return 10
    }
    
    func collectionView(_ collectionView: UICollectionView, cellForItemAt indexPath: IndexPath) -> UICollectionViewCell {
        let cell = collectionView.dequeueReusableCell(withReuseIdentifier: "cellid", for: indexPath)
        cell.contentView.backgroundColor = .green
        return cell
    }
}

#if DEBUG && canImport(SwiftUI) && canImport(Combine)
import SwiftUI

@available(iOS 13.0, *)
struct MyViewControllerRepresentable: UIViewRepresentable {
  func makeUIView(context: Context) -> UIView {
    let vc = MyViewController()
    vc.view.backgroundColor = .brown
    return vc.view
  }
  
  func updateUIView(_ view: UIView, context: Context) {
  }
}

@available(iOS 13.0, *)
struct MyViewControllerRepresentablePreview: PreviewProvider {
  static var previews: some View {
    MyViewControllerRepresentable().previewDevice(PreviewDevice(rawValue: "iPhone SE (2nd generation)"))
  }
}
#endif
```

# Collection View Cell


```
import UIKit

final class MyCollectionViewCell : UICollectionViewCell{
    
    private(set) var titleLabel = UILabel()
    
    override init(frame: CGRect) {
        super.init(frame: frame)
        buildSubviews()
        buildConstraints()
        buildStyle()
    }
    
    required init?(coder: NSCoder) {
        fatalError("init(coder:) has not been implemented")
    }
    
    deinit {
        print("dealloc \(self)")
    }
    
    private func buildSubviews(){
        contentView.addSubview(titleLabel)
    }
    
    private func buildConstraints(){
        titleLabel.translatesAutoresizingMaskIntoConstraints = false
        NSLayoutConstraint.activate([
            titleLabel.topAnchor.constraint(equalTo: contentView.topAnchor),
            titleLabel.centerXAnchor.constraint(equalTo: contentView.centerXAnchor),
        ])
    }
    
    private func buildStyle(){
        
    }
}

#if DEBUG && canImport(SwiftUI) && canImport(Combine)
import SwiftUI

@available(iOS 13.0, *)
struct MyCollectionViewCellRepresentable: UIViewRepresentable {
  func makeUIView(context: Context) -> UIView {
    let cell = MyCollectionViewCell()
    cell.backgroundColor = .red
    cell.titleLabel.textAlignment = .center
    cell.titleLabel.text = "Hello World!"
    return cell
  }
  
  func updateUIView(_ view: UIView, context: Context) {
  }
}

@available(iOS 13.0, *)
struct MyCollectionViewCellRepresentablePreview: PreviewProvider {
  static var previews: some View {
    MyCollectionViewCellRepresentable().frame(width: /*@START_MENU_TOKEN@*/100/*@END_MENU_TOKEN@*/, height: /*@START_MENU_TOKEN@*/100/*@END_MENU_TOKEN@*/, alignment: /*@START_MENU_TOKEN@*/.center/*@END_MENU_TOKEN@*/)
  }
}
#endif

```
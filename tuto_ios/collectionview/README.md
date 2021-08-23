# tips developpement iOS

# Collection View Controller

```

import UIKit

final class MyViewController: UIViewController{
    private let collectionView: UICollectionView

    //MARK: - Lifecycle
    init(){
        let layout = UICollectionViewFlowLayout()
        layout.scrollDirection = .vertical
        //Will be overriden by UICollectionViewDelegateFlowLayout
        layout.sectionInset = UIEdgeInsets(top: 10, left: 10, bottom:10, right: 10)
        layout.itemSize = CGSize(width: 100, height: 50)
        layout.minimumLineSpacing = 10.0
        layout.minimumInteritemSpacing = 10.0
        collectionView = UICollectionView(frame: CGRect.zero, collectionViewLayout: layout)
        super.init(nibName: nil, bundle: nil)
        collectionView.dataSource = self
        collectionView.delegate = self
        collectionView.register(UICollectionViewCell.self, forCellWithReuseIdentifier: "cellid")
        print("alloc \(self)")
    }

    required init?(coder: NSCoder) {
        fatalError("init(coder:) has not been implemented")
    }

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

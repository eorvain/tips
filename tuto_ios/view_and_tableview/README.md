# tips developpement iOS

# Custom View

```
//
//  BarcodeTypeCell.swift
//  ScanProduct
//
//  Created by Manu on 29/04/2021.
//

import UIKit

class MyView: UIView{
    
    override init(frame: CGRect) {
        super.init(frame: frame)
        print("alloc \(self)")
        buildStyle()
        buildConstraints()
    }
    
    required init?(coder: NSCoder) {
        fatalError("init(coder:) has not been implemented")
    }
    
    deinit{
        print("dealloc \(self)")
    }
    
    private func buildStyle(){
    }
    
    private func buildConstraints(){
    }
}


#if DEBUG && canImport(SwiftUI) && canImport(Combine)
import SwiftUI

@available(iOS 13.0, *)
struct MyViewRepresentable: UIViewRepresentable {
    func makeUIView(context: Context) -> UIView {
        let view = MyView()
        view.backgroundColor = .brown
        return view
    }
    
    func updateUIView(_ view: UIView, context: Context) {
    }
}

@available(iOS 13.0, *)
struct MyViewPreview: PreviewProvider {
    static var previews: some View {
        MyViewRepresentable()
        //MyViewRepresentable().previewLayout(.fixed(width: 400, height: 50))
    }
}
#endif

```

# Custom Table Cell

```
import UIKit

class MyViewCell:UITableViewCell{
    
    override init(style: UITableViewCell.CellStyle, reuseIdentifier: String?) {
        super.init(style: style, reuseIdentifier: reuseIdentifier)
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
    }
    
    private func buildConstraints(){
    }
    
    private func buildStyle(){
    }
}

#if DEBUG && canImport(SwiftUI) && canImport(Combine)
import SwiftUI

@available(iOS 13.0, *)
struct MyViewCellRepresentable: UIViewRepresentable {
  func makeUIView(context: Context) -> UIView {
    let cell = MyViewCell()
    cell.textLabel?.text = "Hello World!"
    return cell
  }
  
  func updateUIView(_ view: UIView, context: Context) {
  }
}

@available(iOS 13.0, *)
struct MyViewCellPreview: PreviewProvider {
  static var previews: some View {
    MyViewCellRepresentable().previewLayout(.fixed(width: 400, height: 60))
  }
}
#endif
```

# Custom Table View

```
//
//  MyTableView.swift
//  ScanProduct
//
//  Created by Manu on 29/04/2021.
//

import UIKit

class MyTableView:UIView{
    
    let tableView = UITableView(frame: CGRect.zero, style: .grouped)
    
    override init(frame: CGRect = CGRect.zero) {
        super.init(frame: frame)
        print("alloc \(self)")
        buildSubviews()
        buildConstraints()
        buildStyle()
    }
    
    required init?(coder: NSCoder) {
        fatalError("init(coder:) has not been implemented")
    }
    
    deinit{
         print("dealloc \(self)")
    }
    
    private func buildSubviews(){
        tableView.register(UITableViewCell.self, forCellReuseIdentifier: "cellid")
        tableView.rowHeight = 65.0
        self.addSubview(tableView)
    }
    
    private func buildStyle(){
    }
    
    private func buildConstraints(){
        tableView.translatesAutoresizingMaskIntoConstraints = false
        NSLayoutConstraint.activate([
        tableView.centerXAnchor.constraint(equalTo: centerXAnchor),
        tableView.centerYAnchor.constraint(equalTo: centerYAnchor),
        tableView.widthAnchor.constraint(equalTo: widthAnchor),
        tableView.heightAnchor.constraint(equalTo: heightAnchor),
            ])
    }
}

#if DEBUG && canImport(SwiftUI) && canImport(Combine)
import SwiftUI

@available(iOS 13.0, *)
struct MyTableViewRepresentable: UIViewRepresentable {
  func makeUIView(context: Context) -> MyTableView {
    let view = MyTableView()
    view.backgroundColor = UIColor.cyan
    view.tableView.backgroundColor = UIColor.yellow
    return view
  }
  
  func updateUIView(_ view: MyTableView, context: Context) {
  }
}

@available(iOS 13.0, *)
struct MyTableViewPreview: PreviewProvider {
  static var previews: some View {
    MyTableViewRepresentable().previewDevice(PreviewDevice(rawValue: "iPhone SE (2nd generation)"))
  }
}
#endif

```

# Custom Table View Controller

```
//
//  MyTableViewController.swift
//  ScanProduct
//
//  Created by Manu on 29/04/2021.
//

import UIKit

class MyTableViewController:UIViewController{

    let myTableView: MyTableView
    
    //MARK: - Lifecycle
    init(){
        myTableView = MyTableView(frame: CGRect.zero)
        super.init(nibName: nil, bundle: nil)
        myTableView.tableView.dataSource = self
        myTableView.tableView.delegate = self
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
        view.addSubview(myTableView)
        myTableView.frame = view.bounds
        buildStyle()
        buildConstraints()
    }
    
    override func viewWillAppear(_ animated: Bool) {
        super.viewWillAppear(animated)
    }
    
    private func buildStyle(){
        if let bar  = navigationController?.navigationBar{
            bar.barTintColor = Theme.navigationBarColor
            bar.tintColor = Theme.navigationBarTintColor
            let font = Theme.font.withSize(18.0)
            bar.titleTextAttributes = [NSAttributedString.Key.font : font,
                                       NSAttributedString.Key.foregroundColor : Theme.navigationBarTintColor]
        }
        self.navigationItem.title = Tr.t("export.title")
    }
    
    private func buildConstraints(){
        let views = [UIView]()
        views.forEach{$0.translatesAutoresizingMaskIntoConstraints = false}
    }
    
    
}

extension MyTableViewController:UITableViewDataSource{
    func numberOfSections(in tableView: UITableView) -> Int {
        return 1
    }
    
    func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
        return 6
    }
    
    func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
        let cell = MyTableViewCell()
        return cell
    }
}

extension MyTableViewController:UITableViewDelegate{
    func tableView(_ tableView: UITableView, didSelectRowAt indexPath: IndexPath) {
        switch indexPath.row {
        case 0:
            _ = 0
        default:
            _ = 0
        }
    }
}

#if DEBUG && canImport(SwiftUI) && canImport(Combine)
import SwiftUI

@available(iOS 13.0, *)
struct MyTableViewControllerRepresentable: UIViewRepresentable {
  func makeUIView(context: Context) -> UIView {
    let vc = MyTableViewController()
    return vc.view
  }
  
  func updateUIView(_ view: UIView, context: Context) {
  }
}

@available(iOS 13.0, *)
struct MyTableViewControllerPreview: PreviewProvider {
  static var previews: some View {
    MyTableViewControllerRepresentable().previewDevice(PreviewDevice(rawValue: "iPhone SE (2nd generation)"))
  }
}
#endif

```

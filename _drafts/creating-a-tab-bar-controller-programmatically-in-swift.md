---
layout: ''
title: Creating a Tab Bar Controller Programmatically in Swift
author: Dedi Prakasa
categories: ''
tags:
- swift
- ios
image: ''

---
Tab bar navigations are common to be found on mobile applications considering the convenience they offer in terms of switching between screens. Here, I am going to show you how to create a tab bar navigation in programmatically in Swift (without using Storyboard).

The main thing that we need to understand is that this tab bar controller holds other view controllers. Thus, creating the view controllers the tab bar contains is a good point, to begin with.

I create two separate files for each view controllers, I name them HomeVC and FavoritesVC. The view controllers simply show plain background color.

    import UIKit
    
    class HomeVC: UIViewController {
    
        override func viewDidLoad() {
            super.viewDidLoad()
            
            view.backgroundColor = .systemPink
        }
    
    }

    import UIKit
    
    class FavoritesVC: UIViewController {
    
        override func viewDidLoad() {
            super.viewDidLoad()
    
            view.backgroundColor = .systemBlue
        }
    }

sdf

sdf
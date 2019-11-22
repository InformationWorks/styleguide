<h2>Naming Conventions</h2>

|Component|Name|
|---|---|
|View controller|GettingStartedScreenVC.swift|
|TableView|homeTV|
|TableViewCell|bannerTVCell|
|CollectionView|contentCV|
|CollectionViewCell|cardCVCell|


<h2>Folder Structure</h2>

* Models
* Targets
* Screens

**Models**

* $Helpers
  * LoadingHelper.swift
  * NavigationHelper.swift
* $Extensions 
  * UILabelExtension.swift
* $RestkitDescriptors 
  * RKCountryDescriptor.swift
* $Utilities
  * ScrollPager.swift 
  * Utility.swift

* User.swift
* Country.swift
* Course.swift
* Collection.swift 

**Targets**

* $TagetName 
  * TargetConfig.swift
  * Launch Screen.swift
  * Info.plist
  * GoogleService-Info.plist

**Screens**
* $GettingStartedScreen
  * GettingStartedScreenVC.swift
  * GettingStartedScreenVC.xib
* $LoginScreen
  * $LoginScreenVC
    * ForgotPasswordTVCell.swift
    * ForgotPasswordTVCell.swift
  * LoginScreenVC.swift
  * LoginScreenVC.xib
  

<h2>Coding Conventions</h2>

<h3>View Controllers</h3>

**Code Folding**

Below are the regions for the Ruby classes. (Example)

    class GettingStartedScreenVC: UIViewController {
      // MARK: - Declarations
      
      // MARK: - Init/Deinit

      // MARK: - View Callbacks

      // MARK: - Initialize

      // MARK: - API Calls

      // MARK: - UI Updates

      // MARK: - Click Handlers

      // MARK: - Navigation

      // MARK: - Others

      // MARK: - Delegates
    }

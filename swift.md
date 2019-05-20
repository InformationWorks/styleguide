<h1>Naming Conventions</h1>

**Naming a View Controller**

We name view controllers by appending VC at the end.

   --> Example: EditProfileVC.swift
    
**Naming Tableviews and CollectionViews**

We name tableviews and collectionviews variables by appendig TV and CV.

  --> Example: homeTV and collectionCV
  
**Naming TableViewCells and CollectionViewCells

We name tableview cells and collectionview cells by appending TVCell and CVCell

  --> Example: ProfileTVCell and CardCVCell
  
**Naming folders**

1. *For Targets*

Create a **Targets** folder in which we will create folders for each target 

  --> Example: $Targets -> $SoorMalhar
  
We will add all the target specific files in it.

  --> Example: TargetConfig.plist, Info.plist, Launch Screen.storyboard, Images, Google-Service Info.plist etc

2. Create a folder for all **Models**

  --> Example: $Models --> User.swift, Country.swift
  
3. All the controllers and xib should be in **Components** folder 

  --> Exapmple: $Components --> $TabBarGroup --> $Home --> HomeVC.swift and HomeVC.xib
                                            
   and $Components --> $TabBarGroup --> $Course --> CourseVC.swift and CourseVC.xib
                                             
4. When we have **TableView** or **CollectionView** in controller then create a folder for that controller and add all the cells in that folder.

  --> Example: Suppose we added tableview in CourseVC then use this convention
  
  $Course --> $CourseVC --> OverviewTVCell.swift and OverviewTVCell.xib
  
5. RestKit Descriptor will be stored in **RestKitDescriptors**

6. We create helper files in **Helpers** folder

  --> Example: $Helpers --> AccountHelper.swift, NavigationHelper.swift, ColorHelper.swift
  

**Functions**

1. Create a function in every tableview and collectionview cell and name it *updateLayout()*

  --> Example: For ProfileTVCell, 
    
      func updateLayout(user: User) {
        userName.text = user.name
      }
       
 2. Create a function in view controllers to start loading process.
 
  --> Example: HomeVC.swift
    
      func startLoadingFromStart() {
        courses = [Course]()
        BackgroundHelper.execute(loadingHelper: loadingHelper, noInternetError: "Failed to load courses.Please check your  internet connection.") {
          self.loadCourses()
        }
      }
  
  Call it from *viewDidLoad()*
  
    override func viewDidLoad() {
      startLoadingFromStart()
    }
    
 
  

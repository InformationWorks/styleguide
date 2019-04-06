## Table of Contents
  1. [Code Folding](#code-folding)
      1. [Top Level](#top-level)
          1. [Top Level Model Class Regions](#top-level-model-class-regions)
          1. [Top Level Activity Class Regions](#top-level-activity-class-regions)
      1. [Inner Level](#inner-level)
          1. [Inner Level Model Class Regions](#inner-level-model-class-regions)
          1. [Inner Level Activity Class Regions](#inner-level-activity-class-regions)
  1. [Handling Clicks](#Handling Clicks)

## Code Folding

Use regions in Java classes to support code folding.

### Top Level

### Top Level Model Class Regions

````java

class Person {
  
  // region Declarations
  // endregion Declarations
  
  // region Getter Setter
  // endregion Getter Setter
  
  // region Parceable
  // endregion Parceable
  
  // region Class Methods
  // endregion Class Methods
  
  // region Instance Methods
  // endregion Instance Methods
  
  // region interface 
  // endregion interface

}

````

### Top Level Activity Class Regions

````java
class SettingsActivity extends AppCompatActivity {
   
   // region Declarations
   // endregion Declarations
   
   // region onCreate
   // endregion onCreate
 
   // region Overrides
   // endregion Overrides
   
   // region onClick Functions
   // endregion onClick Functions
   
}
````

### Inner Level


### Inner Level Model Class Regions

````java

class Person {
  
  // region Declarations

      // region Final static
      // endregion Final static
      
      // region Primitives
      // endregion Primitives
      
      // region Objects
      // endregion Objects

  
  // endregion Declarations
}

````

### Handling Clicks

##### Don't set clicklisteners from onCreate when you can directly implement android:onClick from xml.

````java

// Bad

@Override
protected void onCreate(Bundle savedInstanceState) {

    llLogout.setOnClickListener(new View.OnClickListener() {
        @Override
        public void onClick(View v) {
            promptForLogout(SettingsActivity.this);
        }
    });

}

// Good

<LinearLayout
    android:id="@+id/ll_logout"
    android:onClick="logoutButtonClicked">
</LinearLayout>

public void logoutButtonClicked(View view) {
    promptForLogout(SettingsActivity.this);
}
````

## Reference Links

* [https://jeroenmols.com/blog/2016/03/07/resourcenaming/](https://jeroenmols.com/blog/2016/03/07/resourcenaming/)
* [https://github.com/ribot/android-guidelines/blob/master/project_and_code_guidelines.md](https://github.com/ribot/android-guidelines/blob/master/project_and_code_guidelines.md)
* [https://google.github.io/styleguide/javaguide.html](https://google.github.io/styleguide/javaguide.html)

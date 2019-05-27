## Table of Contents
  1. [Naming Convention](#naming-convention)
  1. [Code Folding](#code-folding)
      1. [Top Level](#top-level)
          1. [Top Level Model Class Regions](#top-level-model-class-regions)
          1. [Top Level Activity Class Regions](#top-level-activity-class-regions)
      1. [Inner Level](#inner-level)
          1. [Inner Level Model Class Regions](#inner-level-model-class-regions)
          1. [Inner Level Activity Class Regions](#inner-level-activity-class-regions)
  1. [Handling Clicks](#Handling Clicks)

## Naming Convention

| Component   | Class Name | Layout Name |
|---|---|---|
| Activity | UserProfileActivity | activity_user_profile.xml |
| Fragment | SignUpFragment | fragment_sign_up.xml |
| Dialog | ChangePasswordDialog | dialog_change_password.xml |
| DialogFragment | ApplyCouponCodeDialogFragment | dialog_fragment_apply_coupon_code.xml |
| AdapterView Item | - | item_person.xml |

## UI Elements Naming Convention

| Component   | Prefix | Example @id | Java Variable |
|---|---|---|---|
| Button | btn_ | btn_login | btnLogin |
| TextView | tv_ | tv_email | tvEmail |
| ProgressBar | pb_ | pb_loading_countries | pbLoadingCountries |

TODO: Add below examples to the above table.

* Frame Layout: fl 
* Linear Layout: ll 
* Table Layout: tl 
* Table Row: tr
* Grid Layout: gl 
* Relative Layout: rl

* Text View: tv 
* Button: bt 
* Check Box: cb 
* Switch: sw 
* Toggle Button: tb
* Image Button: ib 
* Image View: iv 
* Progress Bar: pb
* Seek Bar: sb 
* Rating Bar: rb 
* Spinner: sp 
* WebView: wv 
* Edit Text: et

* Radio Group: rg 
* List View: lv 
* Grid View: gv 
* Expandable List View: el 
* Scroll View: sv 
* Horizontal Scroll View: hs 
* Search View:* se 
* Tab Host: th 
* Video View: vv 
* Dialer Filter: df

* Include: ic 
* Fragment: fr 
* Custom View (other): cv

## Code Folding

Use regions in Java classes to support code folding.

### Top Level

### Top Level Model Class Regions

````java

class Person {
  
  // region Declarations
  // endregion Declarations
  
  // region Constructors
  // endregion Constructors
  
  // region Getter Setter
  // endregion Getter Setter
  
  // region Parceable
  // endregion Parceable
  
  // region Class Methods
  // endregion Class Methods
  
  // region Instance Methods
  // endregion Instance Methods

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

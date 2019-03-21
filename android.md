### Model Class Top Level Regions

Use below regions in the model classes to support code folding.

````java

class Person
  
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

end

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



### Do

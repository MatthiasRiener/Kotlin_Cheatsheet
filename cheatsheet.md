# Inhaltsverzeichnis
- [Inhaltsverzeichnis](#inhaltsverzeichnis)
- [Projekt anlegen](#projekt-anlegen)
    - [Projekt anlegen](#projekt-anlegen-1)
- [Gradle File](#gradle-file)
    - [Plugins](#plugins)
    - [Databinding enablen (in Android Tag)](#databinding-enablen-in-android-tag)
    - [Dependencies (für Corona Test Tracker)](#dependencies-für-corona-test-tracker)
- [Navigation](#navigation)
  - [Navigation erstellen](#navigation-erstellen)
  - [Navigation einbinden](#navigation-einbinden)
    - [activity_main.xml refactor](#activity_mainxml-refactor)
  - [Fragment erstellen](#fragment-erstellen)

# Projekt anlegen
### Projekt anlegen
```
New Project -> Empty Activity
```

Android SDK
```
SDK Oreo 8.0 API 26
```


# Gradle File
Wichtig: Imports im build.gradle (module)

### Plugins
```
plugins {
    id 'com.android.application'
    id 'kotlin-android'
    id 'kotlin-android-extensions'
    id 'kotlin-kapt'
}
```

### Databinding enablen (in Android Tag)
```Gradle
dataBinding {
    enabled true
}
```


### Dependencies (für Corona Test Tracker)
```gradle
dependencies {
    implementation 'androidx.legacy:legacy-support-v4:1.0.0'
    def nav_version = "2.3.5"
    def gradle_version = "7.0.2"

    implementation 'androidx.core:core-ktx:1.7.0'
    implementation 'androidx.appcompat:appcompat:1.3.1'
    implementation 'com.google.android.material:material:1.4.0'
    implementation 'androidx.constraintlayout:constraintlayout:2.1.1'

    implementation "androidx.navigation:navigation-fragment-ktx:$nav_version"
    implementation "androidx.navigation:navigation-ui-ktx:$nav_version"

    implementation "com.google.android.material:material:1.1.0"

    testImplementation 'junit:junit:4.+'
    androidTestImplementation 'androidx.test.ext:junit:1.1.3'
    androidTestImplementation 'androidx.test.espresso:espresso-core:3.4.0'

    kapt "com.android.databinding:compiler:$gradle_version"

    def lifecycle_version = "2.2.0"
    // ViewModel
    implementation "androidx.lifecycle:lifecycle-viewmodel-ktx:$lifecycle_version"
    // LiveData
    implementation "androidx.lifecycle:lifecycle-livedata-ktx:$lifecycle_version"
    // Lifecycles only (without ViewModel or LiveData)
    implementation "androidx.lifecycle:lifecycle-runtime-ktx:$lifecycle_version"
    implementation "androidx.lifecycle:lifecycle-extensions:$lifecycle_version"
    // needed for: val viewModel . ... by viewModels()
    implementation "androidx.activity:activity-ktx:1.1.0"
}
```

# Navigation
## Navigation erstellen
```
Rechtsklick res -> New -> Android Resource File

File name: nav_graph
Resource Type: navigation
```
... Ordner mit dem Namen navigation wird in res erstellt. Darin befindet sich nav_graph.xml

## Navigation einbinden
1. activity_main.xml auswählen
2. NavHostFragment einfügen
3. nav_graph auswählen
4. Constraints setzen

### activity_main.xml refactor
```
Vorher: androidx.fragment.app.FragmentContainerView
Nachher: fragment
```


## Fragment erstellen
1. nav_graph.xml auswählen
2. Mobile Icon mit grünem + klicken
3. Fragment (Blank) auswählen
4. Fragment umkonvertieren von FrameLayout in ConstraintLayout





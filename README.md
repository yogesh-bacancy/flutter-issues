#### This File is created to highlight what issues the Flutter team has faced and corresponsing solution that has actually worked. The goal is if someone faces the similar problem an instant solution can be provided


###### 1)  Manifest merger failed : Attribute data@scheme at AndroidManifest.xml requires a placeholder substitution but no value for \<appAuthRedirectScheme\> is provided.

##### ***Solution***
 ###### Add below code in app level build.gradle
        android {
          ...
          defaultConfig {
            ...
            manifestPlaceholders += [
                'appAuthRedirectScheme': '<your_custom_scheme>'
            ]
          }
        }
        

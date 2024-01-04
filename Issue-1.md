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

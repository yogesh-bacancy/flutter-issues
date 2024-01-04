###### 1)  Manifest merger failed : Attribute data@scheme at AndroidManifest.xml requires a placeholder substitution but no value for \<appAuthRedirectScheme\> is provided.

##### ***Solution***
 ###### Following issue occurs when [firebase_appauth](https://pub.dev/packages/firebase_auth) package is used, for this we have to provide an redirect sceheme and host to the application. For this follow the mentioned steps.
 ###### 1) Add below code in app level build.gradle to supply the **appAuthRedirectScheme**
        android {
          ...
          defaultConfig {
            ...
            manifestPlaceholders += [
                'appAuthRedirectScheme': '<your_custom_scheme>'
            ]
          }
        }
###### 2) Add the redirect scheme and host resolver activity in **AndroidManifest.xml**
       <activity
        android:name="net.openid.appauth.RedirectUriReceiverActivity"
        android:exported="true"
        tools:node="replace">
        <intent-filter>
          <action android:name="android.intent.action.VIEW"/>
          <category android:name="android.intent.category.DEFAULT"/>
          <category android:name="android.intent.category.BROWSABLE"/>
          <data android:scheme="<your_custom_scheme>"
              android:host="<your_custom_host>"/>
        </intent-filter>
       </activity>



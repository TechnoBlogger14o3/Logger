# Logger
A simple class to restrict your Log in the release build.


android {
    compileSdkVersion 26
    buildToolsVersion "26.0.0"
    defaultConfig {
        applicationId "com.logger"
        minSdkVersion 15
        targetSdkVersion 26
        versionCode 1
        versionName "1.0"
        testInstrumentationRunner "android.support.test.runner.AndroidJUnitRunner"
        buildConfigField "boolean", "ON_DEBUG_MODE", "true"

        /**
         * We are using "ON_DEBUG_MODE", in AppLogger Class
         */

        /**
         * In Debug build it is "true", so the Log will be printed.
         */
    }
    buildTypes {
        release {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android.txt'), 'proguard-rules.pro'
            buildConfigField "boolean", "ON_DEBUG_MODE", "false"
            /**
             * In Release build it is "false", so the Log will not be printed.
             */
        }
    }
}

# Documentation

### ButterKnife Download
```
implementation 'com.jakewharton:butterknife:8.8.1'
annotationProcessor 'com.jakewharton:butterknife-compiler:8.8.1'
```

### Laravel 5.6 Error Migration
```
<?php

namespace App\Providers;

use Illuminate\Support\ServiceProvider;
use Illuminate\Support\Facades\Schema;


public function boot()
{
    Schema::defaultStringLength(191);
}
```

### Secret API_KEY or Other on Gradle

> 1. Add /gradle.properties into gitignore file.
> 2. Add line in Gradle.properties file "API_KEY = "CopyYourAPI_KEYhere""
> 3. Add below line in app:build.gradle buildConfigField("String", "API_KEY", API_KEY)
> 4. Use Key using the following statement "BuildConfig.API_KEY" Copy this whereever do you need API_KEY

__Example__ :
gradle.properties
```
API_KEY="TooManySecrets"
```
build.gradle (app)
```
defaultConfig {
    applicationId "com.miqdad.myProjects"
    minSdkVersion 16
    targetSdkVersion 27
    versionCode 1
    versionName "1.0"

    // Please ensure you have a valid API KEY for themoviedb.org↵
       to use this app
    // A valid key will need to be entered
    buildConfigField("String", "API_KEY", API_KEY)
  }
```
Java file
```
private static final String API_KEY = BuildConfig.API_KEY;
```


### RecycleView ItemClick Support on MainActivity
__Code__ :
> [Code](./ItemClickSupport.java)  

__Usage__ :
```
ItemClickSupport.addTo(rvBooks).setOnItemClickListener(new ItemClickSupport.OnItemClickListener() {
            @Override
            public void onItemClicked(RecyclerView recyclerView, int position, View v) {
                // action code here
            }
        });
```

### Laravel User Model Auth
```

use Illuminate\Notifications\Notifiable;
use Illuminate\Contracts\Auth\MustVerifyEmail;
use Illuminate\Foundation\Auth\User as Authenticatable;

class User extends Authenticatable
{

use Notifiable;

...

```

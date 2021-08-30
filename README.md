# Easy Folder Picker
Convenience library for including Folder/Directory selection into you Android applications. Easily integrated and styled to matched the feel and look of your apps.

---

## How to Use 

### Step 1

Include the below dependency in your `build.gradle` project.

```gradle
buildscript {
    repositories {
        google()
        jcenter()
        maven { url "https://newtronlabs.jfrog.io/artifactory/libs-release-local"
            metadataSources {
                artifact()
            }
        }
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:3.5.2'
        classpath 'com.newtronlabs.android:plugin:4.0.5'
    }
}

allprojects {
    repositories {
        google()
        jcenter()
        maven { url "https://newtronlabs.jfrog.io/artifactory/libs-release-local"
            metadataSources {
                artifact()
            }
        }
    }
}

subprojects {
    apply plugin: 'com.newtronlabs.android'
}
```

In the `build.gradle` for your app include:

```gradle
dependencies {
    compileOnly 'com.newtronlabs.easyfolderpicker:easyfolderpicker:4.0.0'
}
```


### Step 2

Make sure you implement `IFolderSelectionListener` to be notified about the user selection.


#### Example 1
This example shows you how to open a folder picker which uses your application's default theme.

```java
EasyFolderPicker.with(this)
                .open(new IFolderSelectionListener()
                {
                    @Override
                    public void onSelection(File file)
                    {
                        // Called when the user makes a selection.
                    }

                    @Override
                    public void onSelectionCanceled()
                    {
                        // Called when the user cancels the selection.
                    }
                });
```

#### Example 2
The Easy Folder Picker library includes a set of default icons which uses unless you otherwise specify what icons to use. This example shows you how to provide your own icons by providing your own implementation of `IFolderIconVisitor`.

```java
EasyFolderPicker.with(this)
                .iconVisitor(new IFolderIconVisitor()
                {
                    @Override
                    public void visitParent(File file, ImageView imageView)
                    {
                        // Set the icon to use for the folder up icon.
                    }

                    @Override
                    public void visitChild(File file, ImageView imageView)
                    {
                        // Set the icon to use for the given file.
                    }
                })
                .open(new IFolderSelectionListener()
                {
                    @Override
                    public void onSelection(File file)
                    {

                    }

                    @Override
                    public void onSelectionCanceled()
                    {

                    }
                });
```

---

## Support Us
Please support the continued development of these libraries. We host and develop these libraries for free. Any support is deeply appriciated. Thank you!

<p align="center">
  <img src="https://drive.google.com/uc?id=1rbY8qjxvWU8GQgaqDrOY4-fYOWobQKk3" width="200" height="200" title="Support us" alt="Support us">
</p>

<p align="center">
  <strong>BTC Address:</strong> 39JmAfnNhaEPKz5wjQjQQj4jcv9BM11NQb
</p>

---

## License
https://gist.github.com/NewtronLabs/216f45db2339e0bc638e7c14a6af9cc8

## Contact

solutions@newtronlabs.com

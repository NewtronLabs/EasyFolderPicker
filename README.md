# Easy Folder Picker
Convenience library for including Folder/Directory selection into you Android applications. Easily integrated and styled to matched the feel and look of your apps.

---

## How to Use 

### Step 1

Include the below dependency in your `build.gradle` project.

```gradle
buildscript {
    repositories {
        maven { url "http://code.newtronlabs.com:8081/artifactory/libs-release-local" }
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:3.5.2'
        classpath 'com.newtronlabs.android:plugin:3.0.0'
    }
}

allprojects {
    repositories {
        maven { url "http://code.newtronlabs.com:8081/artifactory/libs-release-local" }
    }
}

subprojects {
    apply plugin: 'com.newtronlabs.android'
}
```

In the `build.gradle` for your app include:

```gradle
dependencies {
    compileOnly 'com.newtronlabs.easyfolderpicker:easyfolderpicker:3.0.0'
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

## License

Easy Folder Picker binaries and source code can only be used in accordance with Freeware license. That is, freeware may be used without payment, but may not be modified. The developer of Easy Folder Picker retains all rights to change, alter, adapt, and/or distribute the software. Easy Folder Picker is not liable for any damages and/or losses incurred during the use of Easy Folder Picker.

You may not decompile, reverse engineer, pull apart, or otherwise attempt to dissect the source code, algorithm, technique or other information from the binary code of Easy Folder Picker unless it is authorized by existing applicable law and only to the extent authorized by such law. In the event that such a law applies, user may only attempt the foregoing if: (1) user has contacted Newtron Labs to request such information and Newtron Labs has failed to respond in a reasonable time, or (2) reverse engineering is strictly necessary to obtain such information and Newtron Labs has failed to reply. Any information obtained by user from Newtron Labs may be used only in accordance to the terms agreed upon by Newtron Labs and in adherence to Newtron Labs confidentiality policy. Such information supplied by Newtron Labs and received by user shall not be disclosed to a third party or used to create a software substantially similar to the technique or expression of the Newtron Labs Easy Folder Picker software.

You are solely responsible for determining the appropriateness of using Easy Folder Picker and assume any risks associated with Your use of Easy Folder Picker. In no event and under no legal theory, whether in tort (including negligence), contract, or otherwise, unless required by applicable law (such as deliberate and grossly negligent acts) or agreed to in writing, shall Newtron Labs be liable to You for damages, including any direct, indirect, special, incidental, or consequential damages of any character arising as a result of this License or out of the use or inability to use the Easy Folder Picker (including but not limited to damages for loss of goodwill, work stoppage, computer failure or malfunction, or any and all other commercial damages or losses), even if Newtron Labs has been advised of the possibility of such damages. 

## Contact

solutions@newtronlabs.com

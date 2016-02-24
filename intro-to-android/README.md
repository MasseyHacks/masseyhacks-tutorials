# Intro to Android

## Preliminaries

For information on the preliminary requirements for your specific system, see the files in the subfolder labelled `preliminaries`.

## What the heck is Android?

_Estimated Time_: 1-2 min

Just like how Windows and Mac OS X and Linux are operating systems for your computer, _Android_ is an operating system for mobile devices. It allows you to do everything you do on your computer from your phone, including surfing the web, watching videos, playing games, etc. Furthermore, just like how you have apps on your computer, you have apps on Android, which are just programs that use the _Android API_ to interact with your phone.

Apps for Android are written in Java.

Android Studio is the IDE (Integrated Development Environment) that allows you to make apps really easily, just like how Visual Studio allows you to write other programs more easily.

## Creating a Project

1. Open Android Studio

2. In the Setup Wizard, click `Start a new Android Studio Project` to open the New Project Wizard.

    i. Set the `Application Name` field to something like `AndroidSample`. This is not just the name that will be used to refer to the app in Android Studio, but will also be the name of the app once we get it onto your phones.
    
    ii. The `Package Name` is just a unique identifier for your app in the Google Play Store. The general naming convention is the reverse of your company's domain name, followed by the name of the application. For example, if your company domain is `www.mycompany.com` and the application has been named `AndroidSample`, then the package name might be `com.mycompany.androidsample`.
    
    If you don't own a domain name, don't worry about it. As said prior, this is just some unique identifier name specific to your app. The important thing is not that it refers to an actual domain, simply that it is _unique_. The easiest thing to do is to just use the default
    `Company Domain` given, which will be something like `<name>.example.com`.
    
    iii. The `Project Location` is simply where the project will be stored.
    
3. Click `Next` when you've filled out the necessary info. This will bring you to the _Form Factors_ screen.

    i. Make sure `Phone and Tablet` is checked. This will indicate that your app is intended for phones and tablets. The other options, `Wear`, `TV`, and `Android Auto`, refer to wearable devices (such as Google Glass), Google TV, and automobile dashboards respectively. Leave these unchecked.
    
    ii. Select `API 16: Android 4.1 (Jelly Bean)` as the `Minimum SDK` setting. This ensures that your app will run on most devices. The older the version selected, the wider the range of devices your app will run on. If we selected `API 23: Android 6.0 (Marshmallow)`, your app would only run on a small percentage of all devices (< 1% as indicated).
    
4. Click `Next`. This will bring you to the _Add an activity to Mobile_ screen. For the purposes of this tutorial, simply select `Blank Activity`.

5. In the new dialog, set the following fields:

    i. `Activity Name` - AndroidSampleActivity
    
    ii. `Layout Name` - activity_android_sample
    
    iii. `Title` - AndroidSampleActivity
    
    iv. `Menu Resource Name` - menu_android_sample
    
*Note*: *Do not* select `Use a Fragment` for now.

6. Click `Finish`. It may take a few minutes for the project to build, and once the Android Studio window is loaded, give it a few minutes to load everything (as there is a LOT it has to load).

### What's an Activity?

An `Activity` is a component of your application that your user can interact with. Activities usually take care of creating a window in which you can add your UI. For example, you should be able to see that there's a `Blank Activity`, which is just an empty window, a `Google Maps Activity` which is the base activity for Google Maps based applications, and there's a whole bunch of other things.

*Note*: Some activities require higher versions of the SDK than 8.

You can have multiple activities simultaneously, but there's usually only one that the user interacts with (typically the "main" activity). Activities can create other activities to perform different actions.

## Inside Android Studio

It's easy to get overwhelmed by the amount of content available at first glance, but don't worry, as we'll focus our attention to only a few key areas, and the rest is just extra stuff necessary for our app to work you can learn about later. Android Studio is an incredibly powerful tool that gives us a lot of control over how our app looks and functions, and provides a large tool belt of gadgets that make designing apps really easy. It's just a matter of learning.

Upon initially loading, your Android Studio Window will look something like this:

![Initial Window](https://github.com/Michaelfonzolo/tutorials/blob/master/intro-to-android/images/image1.png)

The leftmost rectangle is the *Project* tool window (highlighted in red below), which displays the files and folders associated with your project. The _window mode_ (highlighted in blue) determines the mode in which the information is displayed. By default it's set to _Android_, which displays only the essential files and folders. Another common mode is _Project_ which lists _all_ files and folders associated with your project. Check out the other modes too!

![Project Tool Window](https://github.com/Michaelfonzolo/tutorials/blob/master/intro-to-android/images/image2.png)

The central *Designer window* (green) shows us whatever we're currently working on. This could be a java file or an xml file or a graphical display. Right now it's giving us a preview of what our app will look like. Specifically, it's showing us our _blank activity_. As you can see, right now our app will simply be a blank window with the text "Hello World!" displayed in the top left corner. Currently in your editor, you should have the file `content_android_sample.xml` open. If not, you can locate it in the Project window under `app/res/layout`. 

In the left of the designer window is a panel called the *palette* (pictured below), which contains a bunch of user interface _components_ that we can add to our activity to make our app look the way we want it to. You should recognize some of these components, such as `Large Text` and `Button` as these are pretty common things to include in a user interface.

![Palette](https://github.com/Michaelfonzolo/tutorials/blob/master/intro-to-android/images/image5.png)

Not all components are things that the user can clearly see like text and buttons, that's why the palette is divided up into _widgets_ and _layouts_. Layouts define the visual structure for your activity, whereas widgets are things with _function_ that can be placed in your activity.

If you go over to the side panel on the right of the designer window, you can see the _Component Tree_ for your activity (pictured below). This represents the hierarchy of components in your activity. As we can see, our activity consists of a `RelativeLayout`, which contains a single `TextView` object whose text is set to "Hello World!".

![Component Tree](https://github.com/Michaelfonzolo/tutorials/blob/master/intro-to-android/images/image5.png)

#### Interlude: What's a RelativeLayout?

In Android, a `RelativeLayout` is a layout in which the positions of the things inside it can be specified as relative to _other_ things. For example, this allows you to say things like "button 2 to the right of button 1" and Android will figure out the rest.

Let's remove the default "Hello World!" text from our activity and add in our own. To remove the widget, click on the `TextView` object in the component tree and press the "delete" key. Alternatively, you can click on the widget in the preview and then press "delete". Now we have an empty slate.

**Note**: Did you accidentally mess something up? Android Studio has a pretty intelligent "undo" button activated by pressing "Ctrl+Z" as usual, so don't be afraid to make mistakes!

To add some text of our own, click and drag the "Large Text" widget from the palette and drop it into the designer window. When you go to place it, you should see a bunch of dotted lines appear on the designer. These are guides so that you know where you're placing your widget relative to everything else. These also allow you to "snap" the location of your widget to common points such as the center of the device screen.

It really doesn't matter where you put the text, but for the purposes of this tutorial you should place it in the center of the device screen.

To change the text the widget displays, double click on it in the designer and change the `Text` field to whatever you want ("Hey MasseyHackers!" for this tutorial). Another way you can do this is by selecting the widget in the component tree and going to the panel beneath the component tree labelled _Properties_ (pictured below). This panel displays all the properties of the selected object, and allows you to change them to whatever you want. There's a TON there, but we only want to change the `text` property, so scroll down until you find it, then click on it to edit the text.

![Properties Window](https://github.com/Michaelfonzolo/tutorials/blob/master/intro-to-android/images/image7.png)

You may notice that the Large Text widget we just placed has a little light bulb icon over it in the component tree. If you hover your mouse over it and click (or press "Alt" + "Enter") it will display the following message:
```
[I18N] Hardcoded string "Hey MasseyHackers!", should use @string resource
```

THe lightbulb indicates a potential problem with a widget. In this case, the issue is that we've _hardcoded_ the string "Hey MasseyHackers!". When you _hardcode_ something, you're basically making it so that you can't change its value unless you change the source code of the program. This is a bad idea if we want to change the value of the string while the app is running, such as if we wanted the text in our app to be translatable into other languages.

_Note_: the `I18N` stands for "Internationalization", which comes from the fact that the first letter is "i", the last letter is "n", and there are 18 letters in between.

The awesome thing about the lightbulb is that it gives you solutions for the problems it identifies. If we click the message, we'll be brought to a dialog that looks like the following:

![](https://github.com/Michaelfonzolo/tutorials/blob/master/intro-to-android/images/image8.png)

The dialog asks you to create a "resource" for the string. A resource is basically just a variable stored in an Xml file. You can se the `Resource Name` to be whatever you want, but, as with variable names, it should describe the purpose of the string. You can ignore `Source set`. The `File name` field is just the name of the file you want to store your resource in. You can just leave it alone for now. Press `OK`, and now the lightbulb icon should be gone from your text widget.

**Note**: If you're getting a "Rendering Problem" saying "Couldn't resolve resource (resourcename)" try building your project by going to `Build` -> `Make Project`. If you're still having problems, save your project, then go to `File` -> `Invalid Caches/Restart` and choose `Just Restart`.

### What are those Xml files?

Throughout the tutorial, we've made reference to Xml files, like `content_android_sample.xml`. Upon opening this file in the editor, we are given a visual preview of our app. But what exactly *is* this Xml file? Well, beneath all the fancy graphics, it's actually just an ordinary text file like anything else you've ever created. Android Studio just reads this text file, and then *creates* the graphical display based on what it says.

If you notice in the bottom left corner of the designer window there are two tabs labelled "Design" and "Text" respectively (![](https://github.com/Michaelfonzolo/tutorials/blob/master/intro-to-android/images/image9.png)). If you click on the "Text" tab (while the `content_android_sample.xml` file is open), a text file will open up that should look something like the following:

![](https://github.com/Michaelfonzolo/tutorials/blob/master/intro-to-android/images/image10.png)

You should recognize some things in this file. Namely, we have a `RelativeLayout` element, and a `TextView` element inside it. This corresponds to the component tree back when were we using the "Design" tab, which showed us that our app consisted of a `RelativeLayout` component with a `TextView` subcomponent. This is how Android Studio knows what to do; it reads the elements in the file and turns them into the app's component tree. Almost every Android app you make will have this general Xml format.

Another important thing to recognize is that the attributes on each of the elements correspond to the component properties. For example, on the `TextView` element, we see it has an attribute labelled `text`, which will be set to `@string/mainstring` (or whatever we decided to call our string resource).

Not everything we do has to be done in the graphical design window. We can actually make changes directly to the Xml file and see the effects it has on the appearance of our app in real time in the preview on the right. Let's test this out! We're going to change the background colour of our app to a light blue. To do this, we have to add the attribute `android:background` to the `RelativeLayout` object and set it equal to `"#96E5FF"` (which just happens to be the colour we want to use in hexadecimal form). Now you're `RelativeLayout` element should look something like the following:

![](https://github.com/Michaelfonzolo/tutorials/blob/master/intro-to-android/images/image11.png)

After you make this change, you should see the effect immediately in the preview to the right. The background has turned light blue, just as we wanted!

There are all sorts of attributes we can add to our elements, so lets do a few more just to get the hang of it. Let's change the colour of our text now to a contrasting dark orange (rgb = `"#FF8800"`). The name of the attribute we have to add now is called `android:textColor`. Thus our `TextView` element should look like this:

![](https://github.com/Michaelfonzolo/tutorials/blob/master/intro-to-android/images/image12.png)

#### Interlude: Android Studio Autocomplete

As you might've noticed, when you were typing the name of the attributes, a little list popped up next to your cursor. This list was a list generated by Android Studio that showed you *every possible attribute you could add*. This is an incredibly useful feature because it means if you forget the exact name of an attribute, you can just look for it *while you type*. It also features an autocomplete feature, where you can scroll through the list using the arrow keys and then select what you want by pressing enter. If that wasn't enough, for certain attributes, after pressing enter and going to type the value of the attribute Android studio will also suggest *possible values for the attribute*. How handy is that?

We'll add one last attribute, which will change the font of our text. The name of the attribute is `fontFamily`, and the value we want to change it to is `"sans-serif-medium"`. 

*Give them a minute to do that and then jump back in.*

So our final `TextView` element should be:

![](https://github.com/Michaelfonzolo/tutorials/blob/master/intro-to-android/images/image13.png)

#### Interlude: Fonts in Android

In Android, it is unfortunately kind of difficult to use any font you want in your apps. There are only a few built in fonts that you can use everywhere. For example, you *won't* be able to use `"Verdana"` as the value of a `fontFamily` attribute because Verdana isn't one of the builtin fonts.

In fact, there just plain *isn't* a way of representing external fonts in pure Xml. You *can* use other fonts, but you have to have the `.ttf` file for the font placed in a folder somewhere in your resources folder, then you have to load that font in Java. It exists, but is too complicated for the purposes of this lecture.

## How do I test my app?

So we've spent some time developing this relatively simple app, but we haven't really gone into how we're supposed to *test* and *use* it? These are two incredibly important practices in development that require addressing.

There are two main ways of testing your app:

A.) Use an Android Virtual Device (AVD).

B.) Load your app onto a physical device.

### Using a Physical Device

Though sometimes it may be more practical to use an AVD, there is nothing quite like the feel of a physical device. Android Studio allows you to test our app on your device very easily. If you simply hook up your device to your computer via USB connection, then hit run, you will be brought to a window that looks like this:

![](https://github.com/Michaelfonzolo/tutorials/blob/master/intro-to-android/images/image16.png)

In this dialog, simply choose the device you have connected (in this case, the only one listed) and hit "OK". Make sure "Launch emulator" is not enabled, and neither is "Use same device for future launches" (unless you are absolutely positive you will be using the same device to test your app in the future). Upon hitting OK, you should see your app appear on your device's screen momentarily!

**Note**: There are a number of circumstances in which your device **will not** be listed in the device chooser. This mainly stems either from the Developer options on your device not being enabled, or your device is listed as a `Portable Device` when it should really be configured as an `Android ADB Composite Device`. `ADB` stands for "Android Debug Bridge"; it's the program that is responsible for the communciation between Android Studio and the emulator (for AVD's) and physical devices.

Instructions for configuring your device can be found [here](#Enabling ADB on Android 5.0 Based Devices).

# A More Useful App

Now that we've covered the basics of the Android API and Android Studio, let's put our skills to the test by designing something a little more useful.

## Other Important Things

In the top menu of the central Designer window there's a dropdown menu with the "Nexus 4" on it. If you click it, a dropdown will open up listing a bunch of different devices. You can choose different devices to preview how your app will look on a specific device. The dropdown is highlighted in red below:

![](https://github.com/Michaelfonzolo/tutorials/blob/master/intro-to-android/images/image3.png)

To the right of that menu you should see a button that looks like ![](https://github.com/Michaelfonzolo/tutorials/blob/master/intro-to-android/images/image4.png). This determines the orientation of the display. You can click the middle of the button to automatically toggle between portrait and landscape, or you can click the arrow to bring up a dropdown menu with even more options.

### Documentation

Inevitably, no tutorial will ever include everything you need to know about *everything* in Android. Fortunately, the developers also supplied an extensive set of documentation that *does* have information on absolutely everything. Android Studio is also kind enough to give you a quick way of accessing the documentation for something in your code. If you place your cursor inside an object's name and press Ctrl + Q (Ctrl + J on Mac OS X), the quick-documentation window will pop-up next to the name, giving you a snapshot of everything you need to know about the object.

For example, in `content_android_sample.xml`, if you place your cursor inside the word `TextView` and hit Ctrl + Q/J, it will bring up the documentation for the `TextView` class. From this we can see that `TextView` is a subclass of `View` and implements the `ViewTreeObserver.OnPreDrawListener` interface. We can even click on those names to bring up *their* documentation and find out what they're for.

*Note*: This feature also works for Java code.

## Enabling ADB on Android 5.0 Based Devices

(This section is taken directly from Android Studio Essentials)

Before ADB can connect to an Android device, that device must first be configured to allow the connection. On phone and tablet devices running Android 5.0 or later, the steps to achieve this are as follows.

1. Open the Settings on the device and select the *About tablet* or *About phone* option.
2. On the *About* screen, scroll down to the *Build number* field and tap on it seven times until a message appears indicating that developer mode has been enabled.
3. Return to the main settings screen and note the appearance of a new option titled *Developer options*. Select this option and locate the setting on the developer screen entitled *USB debugging*. Enable the checkbox next to this item to enable the adb debugging connection.
4. Swipe downward from the top of the screen to display the notifications panel and note that the device is currently connected as a *media device* (this assumes you are performing these steps while the device is plugged in).

At this point, the device is now configured to accept debugging connections from adb on the development system. All that remains is to configure the development system to detect the device when it is attached. Whilst this is a relatively straightforward process, the steps involved differ depending on the development system is running Windows, Mac OS X or Linux. Note that the following steps assume that the Android SDK *platform-tools* directory is included in the operating system PATH environment variable.

### Windows ADB Configuration

The first step in configuring a Windows based development system to connect to an Android device using ADB is to install the appropriate USB drivers on the system. In the case of some devices, the *Google USB Driver* must be installed (a full listing of devices supported by the Google USB driver can be found online [here](http://developer.android.com/sdk/win-usb.html)).

To install this driver, perform the following steps:

1. Launch Android Studio and open the Android SDK Manager, either by selecting `Configure -> SDK Manager` from the Welcome screen, or using the `Tools -> Android -> SDK Manager` menu option when working on an existing project.
2. Scroll down to the *Extras* section and check the status of the *Google USB Driver* package to make sure that it is listed as *Installed*.
3. If the driver is not installed, select it and click on the *Install packages* button to initiate the installation.
4. Once installation is complete, close the Android SDK Manager.

For Android devices not supported by the Google USB driver, it will be necessary to download the drivers provided by the device manufacturer. A listing of drivers and download information can be obtained online [here](http://developer.android.com/tools/extras/oem-usb.html).

When an Android device is attached to a Windows system it is configured as a *Portable Device*. In order for the device to connect to ADB it must be configured as an *Android ADB Composite Device*. 

First, connect the Android device to the computer system if it is not currently connected. Next, display the Control Panel and select Device Manager. In the resulting dialog, check for a category entitled *Other Devices*. Unfold this category and check to see if the Android device is listed.

Right-click on the device name and select *Update Driver Software* from the menu. Select the option to *Browse my computer for driver software* and in the next dialog, keep the *Include subfolder* option selected and click on the *Browse...* button. Navigate to the location into which the USB drivers were installed. In the case of the Google USB driver, this will be in the `sdk\extras\google\usb_driver` subfolder of the Android Studio installation directory (the location of which can be found in the SDK Manager). Once located, click on *OK* to select the driver folder followed by *Next* to initiate the installation.

During the installation, a Windows Security prompt will appear seeking permission to install the driver. When this dialog appears, click on the `Install` button to proceed.

Once the installation completes, the Windows driver update screen will refresh to display a message indicating that the driver has been installed and that the device is now recognized as an Android Composite ADB Interface.

Return to the Device Manager and note that the device is no longer listed under `Other Devices` and is now categorized as an Android Composite ADB Interface.

With the drivers installed and the device now being recognized as the correct device type, open a Command Prompt window and execute the following command:

```
adb devices
```

This command should output information about the connected device similar to the following:

```
List of devices attached
015d41d4454bf80c        offline
```

If the device is listed as *offline* or *unauthorized*, go to the device display and check for the dialog seeking permission to *Allow USB debugging*.

Enable the checkbox next to the option that reads *Always allow from this computer*, before clicking on *OK*. Repeating the *adb devices* command should now list the device as being ready:

```
List of devices attached
015d41d4454bf80c        device
```

In the event that the device is not listed, execute the following commands to restart the ADB server:

```
adb kill-server
adb start-server
```

If the device is still not listed, try executing the following command:

```
android update adb
```

Note that it may also be necessary to reboot the system.

### Mac OS X ADB Configuration

In order to configure the ADB environment on a Mac OS X system, connect the device to the computer system using a USB cable, open a terminal window and execute the following command:

```
android update adb
```

Next, restart the adb server by issuing the following commands in the terminal window:

```
$ adb kill-server
$ adb start-server
* daemon not running. starting it now on port 5037 *
* daemon started successfully *
```

Once the server is successfully running, execute the following command to verify that the device has been detected:

```
$ adb devices
List of devices attached
74CE000600000001        offline
```

If the device is listed as *offline*, go to the Android device and check for the presence of the dialog seeking permission to *Allow USB debugging*. Enable the checkbox next to the option that reads *Always allow from this computer*, before clicking on *OK*. Repeating the *adb devices* command should now list the device as being available:

```
List of devices attached
015d41d4454bf80c        device
```

In the event that the device is not listed, try logging out and then back in to the Mac OS X desktop and, if the problem persists, rebooting the system.

### Linux adb Configuration

For the purposes of this tutorial, we will once again use Ubuntu Linux as a refence example in terms of configuring adb on Linux to connect to a physical Android device for application testing.

Begin by attaching the Android device to a USB port on the Ubuntu Linux System. Once connected, open a Terminal window and execute the Linux `lsusb` command to list currently available USB devices:

```
~$ lsusb
Bus 001 Device 003: ID 18d1:4e44 asus Nexus 7 [9999]
Bus 001 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
```

Each USB device detected on the system will be listed along with a vendor ID and a product ID. A list of vendor IDs can be found online [here](http://developer.android.com/tools/device.html#VendorIds). The above output shows that a Google Nexus 7 device has been detected. Make a note of the vendor and product ID numbers displayed for your particular device (in the above case these are 18D1 and 4E44 respectively).

Use the *sudo* command to edit the *51-android.rules* file located in the */etc/udev/rules.d* directory. For example:

```
sudo gedit  /etc/udev/rules.d/51-android.rules
```

Within the editor, add the appropriate entry for the Android device, replacing `vendor_id` and `product_id` with the vendor product IDs returned previously by the lsusb command:

```
SUBSYSTEM==="usb", ATTR{idVendor}=="vendor_id",
ATTRS{idProduct}=="product_id", MODE="0660", OWNER="root",
GROUP="androidadb", SYMLINK+="android%n"
```

Once the entry has been added, save the file and exit from the editor.

Next, use an editor to modify (or create if it does not yet exist) the adb_usb.ini file:

```
gedit   ~/.android/adb_usb.ini
```

Once the file is loaded into the editor, add the following lines (once again replacing `vendor_id` and `product_id` with the vendor and product IDs returned previously by the `lsusb` command) before saving the file and exiting:

```
0xvendor_id
0xproduct_id
```

Using the above syntax, the entries for the Nexus 7 would, for example, read:

```
0x18d1
0x4e44
```

The final task is to create the *androidadb* user group and add your user account to it. To achieve this, execute the following commands making sure to replace `username` with your Ubuntu user account name:

```
sudo addgroup --system androidadb
sudo adduser username androidadb
```
Once the above changes have been made, reboot the Ubuntu system. Once the system has restarted, open a Terminal window, start the adb server and check the list of attached devices:

```
$ adb start-server
* daemon not running. starting it now on port 5037 *
* daemon started successfully *
$ adb devices
List of devices attached
015d41d4454bf80c        offline
```

If the device is listed as *offline*, go to the Android device and check for the dialog seeking permission to *Allow USB debugging*.

### Testing the ADB Connection

Assuming that the adb configuration has been successful on your chosen devleopment platform, the next step is to try running the test application you created. Launch Android Studio, open the AndroidSample project and, once the project has loaded, click on the run button located in the Android Studio toolbar (the sideways green triangle).

Assuming that the project has not previously been configured to run automatically in an emulator environment, the *Choose Device* dialog will appear with the connected Android device listed as a currently running device.

To make this the default device for testing, enable the *Use same device for future launches* option. With the device selected, click on the *OK* button to install and run the application on the device. As with the emulator environment, diagnostic output relating to the installation and launch of the application on the device will be logged in the Run tool window.
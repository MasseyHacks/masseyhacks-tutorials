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

### Using an AVD

An AVD is an emulator of a physical android device; basically a program on your computer that accurately simulates what will happen when you load your app onto an actual device. What you do is you *create* an AVD that represents the device you want to test on, then you run your app using that AVD. Let's do an example.

First, to create an AVD from Android Studio, go to `Tools -> Android -> AVD Manager`. This will open a new window that looks something like the following:

![](https://github.com/Michaelfonzolo/tutorials/blob/master/intro-to-android/images/image14.png)

Now you can either select a pre-existing device like the one we have there, or create a new device. We will create a new AVD. Clicking the button in the bottom left corner will bring up yet another window that looks like this:

![](https://github.com/Michaelfonzolo/tutorials/blob/master/intro-to-android/images/image15.png)

Here is where we can choose what device we want to base our AVD off of. Choose whatever device you desire, then press next. Navigating through the pages will reveal different settings you can change. Fill these in however you require, then click "Finish" and you're device will have been created. From there you can use it to test out your app by simply clicking the green triangle button in the AVD manager.

### Using a Physical Device



### Other Important Things

In the top menu of the central Designer window there's a dropdown menu with the "Nexus 4" on it. If you click it, a dropdown will open up listing a bunch of different devices. You can choose different devices to preview how your app will look on a specific device. The dropdown is highlighted in red below:

![](https://github.com/Michaelfonzolo/tutorials/blob/master/intro-to-android/images/image3.png)

To the right of that menu you should see a button that looks like ![](https://github.com/Michaelfonzolo/tutorials/blob/master/intro-to-android/images/image4.png). This determines the orientation of the display. You can click the middle of the button to automatically toggle between portrait and landscape, or you can click the arrow to bring up a dropdown menu with even more options.





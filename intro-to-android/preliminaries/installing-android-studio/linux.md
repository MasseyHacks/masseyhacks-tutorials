### Installation on Linux

(Taken directly from "Android Studio Development Essentials")

Having downloaded the Linux Android Studio package, open a terminal window, change directory to the location where Android Studio is to be installed and execute the following command:
```
unzip /<path to package>/android-studio-ide-<version>-linux.zip
```

Note that the Android Studio bundle will be installed into a sub-directory named `android-studio`. Assuming, therefore, that the above command was executed in `/home/demo`, the software packages will be unpacked into `/home/demo/android-studio`.

To launch Android Studio, open a terminal window, change directory to the `android-studio/bin` sub-directory and execute the following command:
```
./studio.sh
```

On Linux it may also be necessary to specify the location of the JDK using the following steps:

1. Launch Android Studio and create a new project.
2. Select the `File -> Other Settings -> Default Project Structure...` menu option.
3. Enter the full path to the directory containing the JDK into the `JDK Location` field.
4. Click `Apply` followed by `OK`.
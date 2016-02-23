## Preliminaries for Intro to Android Lecture

For attendees to be able to participate in the lecture, they must have the Java Development Kit (JDK) and the Android Studio Integrated Development Environment (IDE) which also includes the Android Software Develompent Kit (SDK).

### System Requirements

- One of the following systems:
  - Windows 2003 (32-bit or 64-bit)
  - Windows Vista (32-bit or 64-bit)
  - Windows 7 (32-bit or 64-bit)
  - Windows 8 / Windows 8.1 
  - Windows 10
  - Mac OS X 10.8.5 or later (Intel based systems only)
  - Linux systems with version 2.11 or later of GNU C Library (glibc)
- Minimum of 2GB of RAM (4GB is preferred)
- 1.5GB of available distk space.

### Installing JDK

#### Installing JDK on Windows and Mac OS X

Most systems have the JDK already installed. To check, enter the command `java -version`. If the JDK isn't installed, it will display some sort of error message saying `java is not a recognized command` (different error on different systems).

To download the JDK, go to [this link](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) and download the version of the JDK that matches your system. Run the executable and follow the instructions for an ordinary installation.

#### Installing JDK on Linux

(Taken directly from "Android Studio Development Essentials")

Firstly, if the chosen development system is running the 64-bit version of Ubuntu then it is essential that the 32-bit library support packages be installed:
```
sudo apt-get install lib32z1 lib32ncurses5 lib32bz2-1.0 lib32stdc++6
```

As with Windows based JDK installation, it is possible to install the JDK on Linux by downloading the appropriate package from the Oracle web site (link above).

Packages are provided by Oracle in RPM format (for installation on Red Hat LInux based systems such as Red Hat Enterprise Linux, Fedora, and CentOS) and as a tar archive for other Linux distributions such as Ubuntu.

On Red Hat based Linux systems, download the .rpm JDK file from the Oracle web site and perform the installation using the `rmp` command in a terminal window. Assuming, for example, that the downloaded JDK file was named `jdk-8u73-linux-x64.rpm`, the commands to perform the installation would read as follows:
```
su
rpm -ihv jdk-8u73-linux-x64.rpm
```
To install using the compressed tar package (tar.gz) perform the following steps:

1. Create the directory into which the JDK is to be installed (for the purposes of this example we will assume `/home/demo/java`).

2. Download the appropriate tar.gz package form the Oracle web site (link above) into the directory.

3. Execute the following command (where `<jdk-file>` is replaced by the name of the downloaded JDK file):
```
tar xvfz <jdk-file>.tar.gz
```

4. Remove the downloaded tar.gz file.

5. Add the path to the `bin` directory of the JDK installation to your `$PATH` variable. For example, assuming that the JDK ultimately installed into `/home/demo/java/jdk1.8.0_73` the following would need to be added to your `$PATH` environment variable:
```
/home/demo/java/jdk1.8.0_73/bin
```

This can typically be achieved by adding a command to the `.bashrc` file in your home directory (specifics may differ depending on the particular Linux distribution in use). For example, change directory to your home directory, edit the `.bashrc` file contained therein and add the following line at the end of the file (modifying the path to match the location of the JDK on your system):
```
export PATH=/home/demo/java/jdk1.8.0_73/bin:$PATH
```

Having saved the change, future terminal sessions will include the JDK in the $PATH environment variable.

### Installing the Android Studio

Android Studio may be downloaded from [this link](http://developer.android.com/sdk/index.html). The download should be for the correct platform, but if not go [here](http://developer.android.com/sdk/index.html#Other) and select the appropriate package for your platform and operating system.

#### Installation on Windows

Run the executable you just downloaded. Click `Yes` if the User Account Control dialog appears.

#### Installation on Mac OS X

(Taken directly from "Android Studio Development Essentials")

Run the disk image file you just downloaded.

In the new window opened up, to install the package, simply drag the Android Studio icon and drop it onto the Applications folder. The Android Studio package will then be installed into the Applications folder of the system, a process which will typically take a few minutes to complete.

To launch Android Studio, locate the executable in the Applications folder using a Finder window and double click on it.

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

### Installing JDK on Linux

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
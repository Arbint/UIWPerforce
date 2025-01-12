# Perforce Server Documentation

```Note:```To access our P4 server outside the Labs, you will need [VPN Access](workingFromHome.md).

```Your User Name:``` Your user name should be the same as the local part of your email, if your email is ```abcde@uiwtx.edu```, your user name is ```abcde```, if you belive you don't have an account, contact your faculty to add one for you.

### Setup P4 Client
* Download ```Perforce Visual Client``` from [here](https://help.uiw.edu/support/solutions/articles/17000071028-Install-Cisco-AnyConnect-VPN-for-Windows). Make sure you select ```Windows```(or ```MacOS``` if you are using Mac), and the latest version. And click the ```DOWNLOAD``` button.

<img src="Assets/DownloadP4V.png" width=600>


* Launch the Downloaded installer, in the first settings, check on all four, use detault install directory, and click ```Next```.

<img src="Assets/P4VInstall01.png">


* In the next page, make sure the ```Server``` Setting is ```10.40.14.107:1666```. And the ```User Name``` is set to be your user name. Click on ```Next```, and then Click on ```Install```

<img src="Assets/P4VInstall02.png">


* Launch ```P4V```, the Perforce Visual Client if it does not automatically open after the installation. In the ```Server``` setting, make sure it is configured as ```10.40.14.107:1666``` if it is not already, and your ```User Name``` to be your user name. Leave the Workspace Empty. And Click the ```OK``` button.

<img src="Assets/P4ConnectionConfig.png">


* The ```Perforce Visual Client``` should now be launched as shown in the image:

<img src="Assets/P4VWindow.png" width=670>


* If this is the first time you login, there is no password set for your. You should ```ALWAYS``` add your password, to do so, go to the ```Main Menu```->```Connection```->```Change Password...```.

<img src="Assets/ChangePassword.png">

* You should setup some of the important environt variables so your system knows what your default configureation is.

    1, Press the ```Start``` Button, and search for ```Environment Variable``` find and launch the ```Edit the system envrionment``` option:

    <img src="Assets/EditEnvironmentVarIcon.png">

    2, In the ```System Properties``` window, click ```Environment Variables...``` and in the pop up window, click the ```New``` Button. and in the new pop up window, set the ```Variable name``` to ```P4PORT``` and ```Variable value``` to ```10.40.14.107:1666``. Click the ```OK``` button to add the variable. Perfore will try to find this environment variable to use as the port (the adress to connect to the server). You should also add the following envrionment variables:

    |  Variable Name | Variable Value |
    |----------------|----------------|
    | P4IGNORE       | .p4ignore      |
    | P4USER         | Your User Name |

    <img src="Assets/P4SystemEnv.png">

    The ```P4IGNORE``` is ```VERY IMPORTANT```, it tells perforce what files to not track and sync with the server, for both ```Unity``` and ```Unreal Engine```, there are alot of generated files that are both re-generatable and super elaborate to keep track of and syncronize. 

    If you are a programmer, the .p4ignore servers the same purpose as .gitignore. But they work very differently, .gitignore is for the repos, but the .p4ignore is per client, you have specifically setup the ```P4IGNORE``` system varible on each of the machine you want to use the .p4ignore, it will not funcion if the environment variable is missing.

### Other Topics:

- [Making a Workspace](MakingWorkspace.md)

- [Adminastrations](Admin.md)

- [Issues](Issues.md)

- [Back Up Routine](BackingUpRoutine.md)

- [For Programmers](ForCoders.md)
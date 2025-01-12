# Setup System Environment Variables

You should setup some of the important environt variables so your system knows what your default configureation is.

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

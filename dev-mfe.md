The MFE inside tutor are wrapped through the tutor-mfe plugin.
The creator of tutor only create three mfe at this time ( profile, gradebook, account )

## Activate the tutor-mfe plugin

To activate a the tutor-mfe plugin you have these commands:

```sh
pip install tutor-mfe # install the tutor-mfe 

tutor plugins enable mfe # enable the plugin

tutor config save # save the config file
```

## Customize the tutor-mfe plugin 

you can add new mfe using the tutor-mfe plugin you have just to add the new mfe in this section 



## Working with MFE plugins 

To activate the mfe plugins follow these steps: 

1. clone the **tutor-mfe** in your local machine
```sh
git clone https://github.com/overhangio/tutor-mfe.git # to clone the mfe plugins in your local 
```
2. Add what ever mfe plugin we want in this section 
```sh
# /tutor-mfe/tutormfe/plugin.py 

config = {
    "defaults": {
        "MYMFE_MFE_APP": {
            "name": "mymfe",
            "repository": "https://github.com/myorg/mymfe",
            "port": 2001,
            "env": {
                "production": {
                    "MY_CUSTOM_MFE_SETTING": "prod value"
                },
                "development": {
                    "MY_CUSTOM_MFE_SETTING": "dev value"
                }
            }
        }
    }
} 
```
3. Install the customized tutor-mfe
 ```sh
 pip install -e ./tutor-mfe 
 ```
4. Enable the new mfe plugin
```
tutor plugins enable mfe
 ```
5. Re-save the config file
```
tutor config save 
```


After activating the mfe plugin, we need to bind the mfe to the dev volumes 
 
```sh 
tutor dev bindmount <mfe_name> <volume>
```
After that we need to run the local tutor server bound to the mfe
```sh
tutor dev runserver --volume=<volume> <mfe_name>
```
**Example**

we are going to use the profile mfe 

```sh
tutor dev bindmount profile /openedx/app
tutor dev runserver --volume=/openedx/app profile
```
Go to this link local.overhang.io:1995/profile/u/< username >

To start working on the bound mfe you can access to the source code through this cmd
```sh
cd "$(tutor config printroot)/volumes/app"
```




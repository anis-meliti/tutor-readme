# Setup the dev env using tutor

## Requirement for tutor 
`Docker <https://docs.docker.com/engine/install/>`:v18.06.0+
`Docker Compose <https://docs.docker.com/compose/install/> `: v1.22.0+

## Installing tutor 

```sh
pip install tutor 
```

or you can install it from the source 

```sh
git clone  https://github.com/overhangio/tutor
cd tutor 
pip install -e .
```

## Running tutor on dev-env

For the development mode you should: 
1. run ``` tutor local quickstart ``` to create the configuration files for the first time ( not needed later )
2. run ``` tutor local stop ``` to stop all the services 
3. run ``` tutor images build openedx-dev``` you have to rebuild the openedx image in dev mode 
4. run ``` tutor dev runserver lms # Access the lms at http://local.overhang.io:8000 
           tutor dev runserver cms #Access the cms at http://studio.local/overhang.io:8001 ```


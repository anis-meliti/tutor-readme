# Important Links

* [Tutor commands](https://docs.tutor.overhang.io/reference.html)

* [Tutor docs](https://docs.tutor.overhang.io/index.html)

* [Tutor forum](https://discuss.overhang.io/)

* [Youtube channel](https://www.youtube.com/overhangio)

* [OpenEdx github repo](https://github.com/edx)

* [Front dev openEdx](https://openedx.atlassian.net/wiki/spaces/FEDX/overview)

# Setup the dev env using tutor

## Requirement for tutor 
[Docker](https://docs.docker.com/engine/install/):v18.06.0+

[Docker Compose](https://docs.docker.com/compose/install/): v1.22.0+

[Python](https://www.python.org/downloads/)
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
4. run 
```sh
    tutor dev runserver lms # Access the lms at http://local.overhang.io:8000 

    tutor dev runserver cms #Access the cms at http://studio.local/overhang.io:8001
```

# Background

This repository contains a simple example of a zephyr application as a west manifest file.

This approach allows new developers to setup an application with minimal effort.  The manifest file will pull in a copy of zephyr and another libraries/repos specified in the west.yml.

This manifest references a sample module/library repository as an example of how to structure a libraries that can be shared between multiple applications.

Some background on Zephyr workspaces and west manifest files.

https://docs.zephyrproject.org/latest/develop/west/basics.html

https://docs.zephyrproject.org/latest/develop/application/index.html

https://blog.golioth.io/improving-zephyr-project-structure-with-manifest-files/


# Setup

1. Create a working folder on your local machine i.e. 'z-start-workspace'


2. cd into that folder and run:


```
west init -m https://github.com/wavenumber-eng/zephyr-start --mr main
```

This initializes the folder as a west/zephyr workspace registered to our application repository.

3.  Run `west update`.   

This may take several minutes to pull in all of the dependencies. In this step,  west will look at the manifest and pull down all the dependencies.   In this case, the dependecies are the vanilla Zephyr repository and our sample modules/library repository. It is quite large and can take several minutes but only has to be initialized once.  Future calls to west update are much quicker.

It is possible to filter which pieces are imported from zephyr for faster setup.  

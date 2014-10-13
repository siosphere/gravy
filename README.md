gravy
=====

Simple PHP Build Script powered by JSON

Run the gravy file in a directory with a build.json, it will go through the build steps executing the callback functions.

Example build script
```
{
    "name": "Gravy",
    "version": "0.0.1",
    "steps": {
        "clean": {
            "Gravy/Gravy::clean": {
                "dir": "{{working_dir}}build"
            }
        },
        "build": {
            "Gravy/Gravy::exec": {
                "command": "git clone {{checkout_url}} {{working_dir}}build"
            }
        },
        "test": {
            
        },
        "deploy": {
            "Gravy/Gravy::sshDeploy": {
                "params": "{{prod_config}}"
            }
        }
    },
    "variables": {
        "prod_config": {
            "host": "localhost",
            "user": "test",
            "dir": "/var/www/html/"
        },
        "checkout_url": "https://github.com/siosphere/gravy.git"
    }
}
```

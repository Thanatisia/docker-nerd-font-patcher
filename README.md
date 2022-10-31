Nerd Font Patcher for Docker

Docker scripts to execute Nerd Fonts Patcher in a containerized environent with the help of the nerd fonts patch official image.

I have used the patcher on bare metal linux, but this is primarily to simplify the usage of nerd fonts in my workflow, regardless of Operating System, as well as to test out my docker(-compose) scripting in an attempt to containerize everything.

thanks to [https://github.com/ryanoasis] and the nerd fonts team for the ability to patch our own fonts into Nerd Fonts on top of providing fantastic font icon packs for ricing.

## Table of Contents
+ [Disclaimer](#disclaimer)
+ [Information](#information)
+ [Setup](#setup)
+ [Documentation](#documentation)
+ [Wiki](#wiki)
+ [TODO (Pipeline)](#todo-pipeline)
+ [References](#references)

## Disclaimer
 * The docker-compose file is created via referencing and translating the docker run command found in the Nerd Fonts repository.
 * If you would like to run this via a manual run, or to learn more about the Nerd Fonts project, please refer to the Nerd Fonts README page

## Information
+ Base Distribution : nerdfonts/patcher
+ Container Default Name : "nerd-font-patcher"
+ Default Filesystem Structure:
    ```
    ./
    |
    |-- fonts/
        |
        |-- in/
        |-- out/
    ```

## Setup
### Pre-Requisites
- Create 2 folders in the path specified in your docker-compose volume mounts (default: your current working directory)
    + input fonts folder for '/in' 
    + output fonts folder for '/out'

### Dependencies
+ docker
+ docker-compose

### Installing
- 

## Documentation

### Customization/Configuration
- To add a parameter to the command
    - Edit the docker-compose file
        - Add your parameter to the 'command' key
            ```yaml
            ...
            command: [your-parameter]
            ...
            ```

### Usage
- Starting up the docker-compose environment
    ```console
    docker-compose up -d
    ```
- Checking status of the patching
    ```console
    docker-compose ps
    ```
- Check current logs of the patch
    ```console
    docker logs [container-name]
    ```

## Wiki
### Components
+ input folder : This is where you place the original font before you startup the docker environment.
+ output folder : This is where the converted/patched font will be placed after the docker environment has finished executing the patcher.

### File Structure
- This is basically the structure of the docker operation 
    - In Host system
        - Input ('/in') folder
            ```
            path/
            |
	    |-- to/
        	|
        	|-- volume/
        	    |
        	    |-- in/
    	    ```
        - Output ('/out') folder
            ```
            path/
            |
	    |-- to/
        	|
        	|-- volume/
        	    |
        	    |-- out/
    	    ```

## TODO (Pipeline)
 + [] Make my own dockerfile to install and setup nerd fonts for use, just entirely for fun because why not

## References
+ [Nerd Fonts](https://github.com/ryanoasis/nerd-fonts)

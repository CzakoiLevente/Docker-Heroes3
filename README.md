# Docker-Heroes3

During the FedEx-day 24 hour coding challenge our 3 member team aimed the goal to create a conainerized Heroes3 application.

### Features
  - The apllication is able to use saved games using volumes.
  - GUI using [x11docker](https://github.com/mviereck/x11docker) 

## How to use the images:


### VCMI

  - Pull the image from dockerhub:
  
  ```
$ docker pull czakoilevente/vcmi  
  ```

  - Create a container from it with the following command:

```
x11docker -i -p --size [resolution in pixels like 800x600] -- -v [path to maps]:/usr/share/vcmi/Maps -v [path to saves]:/fakehome -- czakoilevente/vcmi  
  ```

  - Do some majick with the following commands:
  
  ```
$ export PATH=$PATH:/usr/games
$ vcmilauncher  
  ```
  
After the last command the VCMI launcher should appear in the window opened by the first command. 
Use it to configure the game as you like. 
Don't forget to enable VCMI Essentials. 
Finally launch the game with button on the bottom left.

If you want to add savegames, do all of the above, then go to the Saves folder in your host machine 
and go to:
`[your username]/.local/share/vcmi/Saves` 
and copy the saves.

If you want to add maps copy them in the Maps folder, the container will see them.

```Note: 
the videos and most of the music files are not included in the image file to make it smaller
```

<br>

### WINE

Pull the image from dockerhub:

 ```
$ docker pull czakoilevente/heroes  
  ```
  
Create a container from it with the following command:
```
$ x11docker -i -p --size [resolution in pixels like 800x600] -- -v [path to maps]:/h3/Maps -v [path to saves]:/h3/Games -- czakoilevente/heroes
```

When the container is ready give this command:

```
$ wine HD_Launcher.exe 
```

Then, install the dependencies (mono, gecko, .NET). Check the settings, then launch the game.

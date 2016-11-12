### Command `rocker build` ###
  1. Open `Rockerfile`
  1. Figure out base image and create copy of it with the given new image name
  1. Mount copy image's data partion somewhere
  1. Follow `Rockerfile`
    * `WORKDIR` - sets the active workdir on the image
    * `RUN` - executes command with WORKDIR set as the active working directory
      * add image specific scripts to search path?
      * (idea) if Rockerfile folder contains `scripts` or `bin` folder, add it to search path
    * `ADD` - add something from `Rockerfile` folder to `abs/path/` destination
      * folder support
      * `wget` support
      * `git` support (with or without .git folder)
      * `tar.gz` support
      * `zip, 7z` support,
      * or, just `unp` it?
    * `ENTRYPOINT` - adds given command to cronfile with tag @reboot
  1. Done, unmount
  
### Command `rocker flash <image> [<device>]` ###
  1. If no `<device>`, pop up a dialog to let the user select the device
    ```apache
    Index:   Device:   Size:  Plugged:
    0:      /dev/sdc    4 GB   10s ago
    1:      /dev/sdb  256 GB    5h ago
    2:      /dev/sda  512 GB    5h ago
    Please select target device (empty=0):
    
    ```
    1. **Linux**, parse from dmesg?
    1. **Windows**, no idea.
  1. Flash
    1. **Linux**, run a dd command
    1. **Windows**, no idea, open instance of Win32DiskImager?


### Problems ###
* Where to host/get latest images?
  * Just `wget` it to some local common Rocker directory?
* Where to host/get image specific set scripts
  * From this repo?
  ```apache
  /Rocker/data/scripts/noobs_2.0.0/
  /Rocker/data/scripts/raspbian_jessie/
  /Rocker/data/scripts/raspbian_jessie_lite/
  
  ```

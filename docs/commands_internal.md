### Command `rocker build` ###
  1. Open `Rockerfile`
  1. Figure out base image and create copy of it with the given new image name
  1. Mount copy image's data partion somewhere
  1. Execute RUN and ADD commands to it
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

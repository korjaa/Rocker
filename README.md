# Rocker
Rocker creates Raspberry Pi images with Dockerfile like syntax.

# Usage

`Rockerfile` defines the image:

    # Use the latest raspbian as base
    FROM raspbian:latest
    
    # Set some Network config
    RUN set_static_ip.sh eth0 192.168.0.10
    
    # Add input from somewhere
    ADD my_custom_prog.tar /home/user/my_custom_prog/
    ADD my_custom_prog2.tar /home/user/my_custom_prog/
    
Build image from current folder

    rocker build <output image> .
    
Flash image

    rocker flash <image file> [<device>]
   
if `<device>` is omitted, user is prompted with currently available storage devices ordered by detection time (visible) with newest first.

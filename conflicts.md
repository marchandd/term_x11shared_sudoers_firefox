# Recent conflicts with marchandd/term_x11shared_sudoers_firefox

Return to [index](https://github.com/marchandd/term_x11shared_sudoers_firefox/ "Index")

## :relaxed: FATA[0000] error & solution

### Context

Make sure your user / group id is 1000.  
Run terminal with your account. Display your ids with this command:  
:computer: `id -a`  
But if you check images presence with:  
:computer: `docker image`  
You can obtain this error:  
FATA[0000] Get http:///var/run/docker.sock/v1.17/images/json: dial unix /var/run/docker.sock: permission denied. Are you trying to connect to a TLS-enabled daemon without TLS?

### Solution

Confirme than only root and docker users can havec access:  
:computer: `ls -l /var/run/docker.sock`  
Add current user to docker group:  
:computer: `sudo gpasswd -a ${USER} docker`  
Confirmed by:  
:computer: `cat /etc/group | grep ^docker`  
Restart service:  
:computer: `sudo service docker restart`  
If you can't again check images presence, reboot your computer.

## :disappointed: GLib-CRITICAL error not resolved (20150302)

### Context

Load image from Docker Hub:  
:computer: `docker pull marchandd/term_x11shared_sudoers_firefox`  
Try to make a container:  
:computer: `docker run -ti -e DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix marchandd/term_x11shared_sudoers_firefox`  
You could obtain this error:  
GLib-CRITICAL **: g_slice_set_config: assertion 'sys_page_size == 0' failed

### None solution at the moment

It was successfull for a long moment but since Firefox 36, it doesn't work now.  
[Bug is identified here](https://bugs.launchpad.net/ubuntu/+source/glib2.0/+bug/1179554 "Firefox 36 bugs")

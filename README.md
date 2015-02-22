# marchandd/term_x11shared_sudoers_firefox

marchandd/term_x11shared_sudoers_firefox [Docker:copyright:](https://docs.docker.com/ "Docker") image

## Description

A sandbox container with last version of Mozilla Firefox ready to use from Linux host.

### Goal

Very easy method to produce a light GUI containers to access to Firefox into sandbox from Linux host.

### Image size

Around 450 Mb

## References

[Marchand D. Maintainer](https://github.com/marchandd/ "Maintainer")

[Details](https://github.com/marchandd/term_x11shared_sudoers_firefox/ "Details")

[Part of Project studies](https://github.com/marchandd/docker_index/ "References")

## Command build image usage

### Command line

:computer: docker pull marchandd/term_x11shared_sudoers_firefox

### Command line explanation

Make sure your user / group id is 1000.
Run terminal with your account. Display your ids with this command:

:computer: id -a

If not equal to 1000, try another command:

:computer: sudo su

:computer: id -a

### Firewall

Due to sudoers privileges, none particularity.

## Command container usage

### Command line

:computer: docker run -ti -e DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix --name firefox11 marchandd/term_x11shared_sudoers_firefox

### Command line explanation

- Run in interactive mode.
- Export display.
- Share x11 drivers from host to container.

## Container usage

### Alias

When you access to container firefox is launched automatically.

:computer: firefox (if you have closed firefox windows and you want to reload it)

## Explanations

### Dockerfile

- After to be sure for your user ID and group ID you can export data.
- Create identical user with Developper name.
- Give him sudoers privileges to machine host to access without password.
- Using Developer user.
- Launch Firefox.

### Display

Use host drivers to display GUI applications from container.

### Risks

Make sudoers give dangerous access permissions...
Sharing drivers turn sandbox to isolation failure...
Reserve it to test only in local mode.
 
### Test environment host

- KUbuntu (14.10)
- Docker (1.4.1)

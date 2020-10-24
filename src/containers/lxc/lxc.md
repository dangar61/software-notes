# Software Engineering Notes.

### LXC

"Vendor neutral containers which offer an environment as close as possible as the one you'd get from a VM but without the overhead that comes with running a separate kernel and simulating all the hardware."

If you are used to using docker, you will find LXC to be different, but familiar. My first exposure to LXC was in 2018. Back then the documentation was confusing and complex. I tried for quite awhile to get an LXC container running on my workstation, but it was very difficult compared to docker and I soon gave up.

I revisited LXC in 2020 and found the documentation to be better and actually got an LXC container working this time. LXD adds an extra API for managing LXC containers which looks very promising for app and tools development.

LXC containers are very interesting in that they give you a full linux operating system experience.


[Linux Containers - LXC, LXD and LXCFS](https://linuxcontainers.org)

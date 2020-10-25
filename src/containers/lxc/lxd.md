# Software Engineering Notes.

### LXD 
A system container manager.


[Linux Containers - LXC, LXD and LXCFS](https://linuxcontainers.org)


**For Fun:** An mdBook development environment in a container

**Part 1:** ***Setup the container*** ***(LXD "snap" installation)***
    
    Create a LXC container:
        $ lxc launch ubuntu:20.04 ubuntu-1

    Open shell to the LXC container:
        $ lxc exec ubuntu-1 -- sudo --login --user root bash

    Install dependencies:
        $ apt update && apt upgrade
        $ apt install build-essential
        
    Install Rust:
        $ curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
        $ source $HOME/.cargo/env

    Install mdBook:
        $ cargo install mdbook
    

**Part 2:** ***Create an mdBook Project***

[Create an mdBook Project on the Host](https://github.com/rust-lang/mdBook)

**Part 3:** ***Run the mdBook server in the container*** 

    Host to Container port mapping:
        $ lxc config device add ubuntu-1 myport3000 proxy listen=tcp:0.0.0.0:3000 connect=tcp:127.0.0.1:3000

    Mount host folder to container:
        $ lxc config device add ubuntu-1 sharedmdbook disk source=/host-path-to-my-mdbook-project/ path=/root/mdbook-project

    Set file permissions:
        $ lxc config set ubuntu-1 raw.idmap "both 1000 1000"

    Run the mdBook server:
        $ lxc exec ubuntu-1 -- sudo --login --user root bash -ilc "cd mdbook-project && mdbook serve"

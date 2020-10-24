# Software Engineering Notes.

### Unprivileged Containers

---
Unprivileged containers are the safest containers.

---

$ lxc-start -n my-container -d

$ lxc-info -n my-container
    
    Name:           my-container
    State:          RUNNING
    PID:            196825
    IP:             10.0.3.11
    Memory use:     70.86 MiB
    KMem use:       12.60 MiB
    Link:           veth1000_zHjw
    TX bytes:      1.76 KiB
    RX bytes:      7.55 KiB
    Total bytes:   9.31 KiB

$ lxc-ls -f

    NAME         STATE   AUTOSTART GROUPS IPV4      IPV6 UNPRIVILEGED 
    my-container RUNNING 0         -      10.0.3.11 -    true         


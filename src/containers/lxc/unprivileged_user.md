# Software Engineering Notes.

### Unprivileged Containers ***as a user***

---
Unprivileged containers are the safest containers.

---
The missing piece of the setup was:
        
    To get containers to run unpriveleged:
        chmod a+rx ~/.local
        chomd a+rx ~/.local/share/

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


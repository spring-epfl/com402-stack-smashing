# COM402 Homework 5 - Exercise 1: Stack Smashing  

The goal of this exercise is to gain hands-on experience with the effects of
buffer overflows and other memory-safety bugs. Your goal is to understand the
vulnerabilities in four target programs, and write an exploit for each target
program.

## VM Images

You will test your exploits within the virtual machine (VM) we provide that is
configured with Debian Lenny that has the address space layout randomization
(ASLR) turned off.

#### VirtualBox
+ [OVF](http://com402.epfl.ch/download/Boxes2.ovf)
+ [Disk](http://com402.epfl.ch/download/Boxes2-disk1.vmdk)

#### VMWare
+ [Image](http://com402.epfl.ch/download/vmware-boxes-2.1.tar.bz2)

## Tips for the VM Images

+ User account username/password: `user/user`
+ Root account username/password: `root/root`

#### Networking

Sometimes accessing the VM via SSH is easier (copy-paste may work better, and you can transfer files both way using the `scp` command). The images we provide use the Network Address Translation (NAT) networking mode by default.

If you are using **_VMWare_**: start up the VM, login as user or root, and find the IP address of the guest OS using the command:

`sbin/ifconfig`

The address you need is the **_inet addr_** that is **NOT** assigned to the loopback. Assuming that the IP address is `192.168.115.128`, you can:

Connect to the guest OS via SSH:

`ssh user@192.168.115.128`

Copy files _TO_ the VM:

`scp <path_to_copy_from_on_host_OS> user@192.168.115.128:<path_to_copy_to_on_guest_OS>`

Copy files _FROM_ the VM:

`scp user@192.168.115.128:<path_to_copy_from_on_guest_OS> <path_to_copy_to_on_host_OS> `

If you are using **_VirtualBox_**, you have two options:

1. Keep operating in NAT mode. In this case, you will need to do port forwarding to be able to SSH into the guest OS. Your bestest friend Google can help you with setting up the port forwarding.

2. Change the network operation mode to **_Bridged Adapter_** from the VM settings. Once you change it, the instructions for using SSH are same as those above.

## Acknowledgements

This assignment is based in part on materials from Prof. Hovav Shacham at UC San Diego, Prof. Dan Boneh at Stanford and Adam Everspaugh at UW Madison. Thanks for their hard work.

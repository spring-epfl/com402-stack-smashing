# COM402 Homework 1 - Exercise 5: Stack Smashing  

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

It's most convenient to access the VM via SSH (copy-paste works better, and you can transfer files both way using the `scp` command). The images we provide use the Network Address Translation (NAT) networking mode by default.

If you're using _VirtualBox_, for example, you need to do the following steps to set up NAT networking:
 * Open the settings of your image
 * Go to the "Networking" panel
 * Choose "Advanced" and click on the "Port forwarding" button
 * Add a forwarding rule (green "plus" button on the side)
 * In the forwarding rule, leave IP addresses empty, set **Host port** to _2222_, and **Guest port** to 22 (the default SSH port)
 * Restart the virtual machine

Now, you can connect to your virtual machine via ssh:
`ssh -p 2222 user@127.0.0.1`

This is how you copy files _TO_ the VM:
`scp -P 2222 <path_to_copy_from_on_host_OS> user@127.0.0.1:<path_to_copy_to_on_guest_OS>`

Copy files _FROM_ the VM:
`scp -P 2222 user@127.0.0.1:<path_to_copy_from_on_guest_OS> <path_to_copy_to_on_host_OS> `

## Acknowledgements

This assignment is based in part on materials from Prof. Hovav Shacham at UC San Diego, Prof. Dan Boneh at Stanford and Adam Everspaugh at UW Madison. Thanks for their hard work.

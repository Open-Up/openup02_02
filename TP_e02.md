# TP DNS

In this practical work (2h), you will install a dns system. You will experience several configuration, slaves, delegation, direct and reverse zones configurations, etc...

I remind you caching issues, so don't hesitate to change DNS records names on *ANY* strange behavior you will encounter.

## Q1 Boot your VMs

For this practical work we need 4 running VMs :

- Start Virtual box
- Use the debian image to create 4 virtual machines
- Add a network adapter configured to be **intern** (click the VM + options + network + network adapter 2 + enable + intern)
- Boot the 3 virtual machines (login : root, passwd : 1234)
- Configure statically the network on these three VMs for eth1

## Q2 Without DNS

- Edit /etc/hosts to be able to give a name to each machine
- Test it using **ping** and **nslookup**
- Give the strength / weakness of such a mechanism
- Evaluate its complexity (total entry count)
- Remove your entries from /etc/hosts

## Q3 Configure a forwarding DNS server

- Install **bind** on a VM
- Configure it to ask 8.8.8.8
- Configure the other VMs to use this DNS for name resolution
- Test it using **ping** and **nslookup**

## Q4 Defining your zones

- Define a zone file to do the same work as in Q 2
- Test it using **ping** and **nslookup**
- Give the strength / weakness of such a mechanism
- Evaluate its complexity (total entry count)

## Q5 Reverse DNS for your network

- Define a reverse zone file symmetric to Q 4
- Test it using **nslookup**

## Q5 Setting up slave

- On server 2 install bind
- Configure server 1 to let server 2 access zone files
- Configure server 2 to be a slave
- Configure server 3 to query server 2
- Test it using **ping** and **nslookup**
- Explain why *slavery* is useful here

## Q6 Delegeting zones

- On server 3 install bind
- Configure server 1 to delegate a zone to server 3
- Configure server 3 to handle this zone
- Configure server 3 to add entry to the delegated zone
- Test it using **ping** and **nslookup** using server 1 2 and 3 as DNS servers
- Turn bind off on server 3 and remove zone delegation on server 1

## Q7 Configure TSIG

- Generate a secret and share it between server 1 and server 2
- Configure TSIG on server 1 and 2
- Test it using **ping** and **nslookup**

## Clean Up

Destroy your VMs and your private network

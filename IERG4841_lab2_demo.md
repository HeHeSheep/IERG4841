<h1>Mission 1: vCenter deployment</h1>

    In this part, I guess showing the correct deployment is the main dish, expect 1.3 have heavy demo. 

1.1 Correct deploy to hypervisor  

    open the vCenter and check if you deploy it correctly.

Pre-Checking: N/A
Demo: N/A

1.2 Correct setup network  

    open the vCenter and check if you deploy it correctly.

Checking:  N/A

Demo: N/A

__1.3 Create another administator account and create one console user account__

Checking:  N/A

Demo:   
Common steps:   
1. At left top corner, click the three lines.
2. Click "Administration".
3. Click "Users and Groups" under "Single Sign On".
4. Click "Users" tab.
5. Choose domain "vsphere.local".
6. Click "Add".
For admin account:
7. Fill in the form.
```
User name: admin_demo
Password: 
Confirm password: 
First name: admin_demo
Last name: vsphere.local

```
```
User name: user_demo
Password: 
Confirm password: 
First name: user_demo
Last name: vsphere.local
```
8. After setting new users, clicl "vSphere Client" at the top left corner and back to "Hosts and Clusters".

9. Click "Permission" at right top plane. 

10. Click "Add Permission" at the top left corner.  

For Admin: 
```
User/Group: admin_demo
Role: Administrator
Choose "Propagate to children"
```

For User:
```
User/Group: user_demo
Role: Virtual Machine Console User
Choose "Propagate to children"
```

<h1>Mission 2: Cluster deployment</h1>

    Basicly, we have to demo all steps on the lab manual in this part. 

2.1 Correct create DC (Data Center)

Checking: Nothing can check. 

Demo guessing: Create one in new admin account. 

2.2 Correct create cluster (DRS, EVC, hosts...)

Checking: Right click cluster -> Configure 
VMware DRS: 
```
Automation level: Manual
Virtual machine Automation: Un-Click
```
VMware EVC:
```
enable EVC for Intel hosts
select Intel "Broadwell" Generation at CPU mode
```
hosts: Nothing can check.

Demo guessing: Create one new cluster. 
```
Right click a DC -> New Cluster 

Name: demo
enable DRS
de-select "Manage all hosts in this cluster with a single vCenter Server"
de-select "Manage configuration at a cluster level"
```


2.3 Correct create resource pool

Checking: Check if there is a resource pool in the cluster.

<h1>Mission 3: DSW deployment</h1>

3.1 Correct create DSW at ESXi2

Checking: Network -> dSW-iSCSI -> Configure 
```
Number of uplinks: 1
Advanced -> MTU : 9000

Default port group: dpg-iSCSI
```

Network -> dSW-VM -> Configure 
```
Number of uplinks: 1
Advanced -> MTU : 9000

Default port group: dpg-Tkpgp
```

3.2 Correct deploy DSW at ESXi2

Checking: ESXi2 -> Networks -> dSW-iSCSI... and dSW-VM...  

3.3 Mount the iSCSI disk successfully at ESXi2

Checking: ESXi2 -> Datastores -> idisk1 

3.4 Correct create DSW at ESXi1

Checking: You can compare the settings with ESXi2. They should be the same.

Demo: Need to do again in admin account? 

3.5 Correct deploy DSW at ESXi1

Checking: You can compare the settings with ESXi2. They should be the same.

Demo: Need to do again in admin account? 

3.6 Correct migrate the standard portgroup to distributed portgroup

Checking: 

3.7 Mount the iSCSI disk successfully at ESXi1

Checking: ESXi1 -> Datastores -> idisk1 

Demo: Check P.7 in lab manual. May require to mount iSCSI disk to ESXi1 again. 

<h1>Mission 4: Live migration</h1>

    In this part, no scores for showing. So I guess we have to demo moving in the new admin account.
4.1 Move the running vCenter from ESXiA to ESXiB  

Demo : ESXiA -> Vms -> select VMs, right click and migrate. 

Demo: Maybe move from ESXi2 to ESXi1? Or move in new admin account?

<h1>Practice before Demo</h1>

    AKA, those carrying 4+ points in demo.

1. Know how to create a new Admin account and Console user account.

2. Know how to create cluster

3. Create and deploy DSW at ESXi1

4. Mount iSCSI disk as ESXi1

5. Move running vCenter. 

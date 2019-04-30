CloudSimJavaExample1.java shows how to create a datacenter with one host and run one cloudlet on it


basic model overview:

![](/images/structureOverviewExample1.png)


1. Register Datacenters to CIS (Cloud Information Structure)
2. Datacenter has Hosts. one or more.  Each Host has it owns hardware characteristics.
3. Each host creates its Virtual Machines.
4. Cloudlets (BoT) are submitted to Broker. Broker will execute Cloudlets at Datacenter on available physical resources through the virtualization process.


Resources are provided with base in policies:
- VmAllocationPolicy: policy used for host resource allocation to virtual machines, in a Datacenter;
- VmSchedulerPolicy: policy used for sharing processing power among VMs, running in a host;
- CloudletSchedulerPolicy: policy used for management of cloudlet by a virtual machine.


[pt. 1](https://www.youtube.com/watch?time_continue=585&v=qBFlB5puRRs)
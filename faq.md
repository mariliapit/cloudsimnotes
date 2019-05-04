## policies n algorithms

#What are the default scheduling policies n how can i change them?

cloudsim models scheduling of cpu resources at 2 levels: host n VM.
at host level, the host shares fractions of processors to each VM running on it.this scheduler is called VmScheduler.

in VM level, each VM divides the resources received from the host among it cloudlets. this scheduler is called CloudletSchedular. 


in both levels, theres two default policies: space shared and time shared.

space shared: cloudlets/mvs are exclusively allocated. if there are more VMs or cloudlets than processors, they will have to wait on a queue until resources are free.
time shared: fractions of processors are shared among VMs and cloudlets, so they all run simultaneously.

#What class should I modify to implement my algorithm?

There are several places in CloudSim where you can implement your algorithm depending on what the algorithm is intended to do. Here are several examples of classes that you may need to modify or extend:

    DatacenterBroker -- modifying the way VM provisioning requests are submitted to data centers and the way cloudlets are submitted and assigned to VMs.
    VmAllocatonPolicy -- you need to extend this abstract class to implement your own algorithms for deciding which host a new VM should be placed on. You can also implement dynamic VM reallocation algorithms by implementing the optimizeAllocation method, which is called at every time frame and passed with the full set of current VMs in the data center.
    VmScheduler -- implementing algorithms for resource allocation to VMs within a single host.
    CloudletScheduler -- implementing algorithms for scheduling cloudlets within a single VM.
    PowerVmAllocationPolicyMigrationAbstract -- a template class for implementing power-aware dynamic VM consolidation algorithms that use VM live migration to dynamically reallocate VMs at every time frame. The main method to be overridden is optimizeAllocation.


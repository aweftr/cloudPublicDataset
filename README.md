# Overview

This folder comprises the public release of our cloud traces collected between 2022 and 2023. These traces have been created to support research in Quality of Service-aware online scheduling of Virtual Machines (VM). 

The trace consists of comprehensive VM information, with over 100,000+ VM entries available. It includes 297 testing instances, where each instance represents a specific scenario involving a queue of VMs that need to be allocated across a fixed number of PMs.


## Traces Description

In cloud resource scheduling and management, efficiency and quality are two vital yet conflicting objectives. Cloud providers, prioritize quality by avoiding hotspots and aim to optimize and increase the utilization efficiency of PM resources without compromising quality. The typical online VM scheduling problem in cloud practice can be stated as follows: given a fixed number of PMs and a queue of arriving VMs, the goal is to place as many VMs as possible onto the PMs while ensuring that no hotspots occur. 

The trace consists of a total of 297 instances, where each instance is represented by a JSON file named in the format X-1.json, X-2.json, and X-3.json. Here, X represents the number of PMs capable of hosting the arriving VMs, ranging from 2 to 100. For example, 50-1.json indicates that there are 50 available PMs to host the arriving VMs. For each value of X, there are three replicas denoted by the suffixes 1, 2, and 3. 

There are multiple flavors of PM available in our cloud service provider. Readers can refer to our online paper to learn about the specific flavor we used for academic and testing purposes. However, they are also free to use other typical flavors as per their requirements. 

Each JSON file contains information about the VMs waiting to be assigned to PMs, and the fields for these VMs are as follows (each line represents a VM): 

+ **Created_at_point**: the timestamp when the VM arrives. The list is already sorted in ascending order based on the arrival times.
+ **memory**: the memory capacity of the VM defined by its flavor, measured in gigabytes (GB).
+ **duration_point**: the timestamps indicating the duration of the VM's usage. Each timestamp represents a 5-minute interval in practice.
+ **vm_util**: the real utilized capacity of the VM at each timestamp. The length of the list is equal to the value of "duration_point".

[Trace Download link](https://1drv.ms/u/c/1e28d2df4704b15c/EchMfCGWbHdIiL3QirEHUTMBcpdMhtmW5GMhyt_kbdfGHw)

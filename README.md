# Penguin Doctor
Currently if Linux VM fail to provision/start, Customer has to use manual work arounds to trouble shooting, it will provide much value if we could provide an automation tool to facilitate it. Furthermore, this tool could expand to other function/features to make it more useful. 

## Use Cases:
Use Case 1: Rescure/restore an Azure Linux VM
```
$pd rescure vm <service_name> <vm_name>
>>>Start rescure job.
>>>Shutting down vm
>>>Backup vhd
>>>Create rescure vm under the same service with ssh port 9999
>>>Remove vm
>>>Break lease of blob
>>>Remove disk
>>>Create data disk
>>>Attach data disk to the new VM
$#
$#User do analysis or fix.
$#
$pd restore
>>>Remove data disk
>>>Break lease
>>>Create new disk
>>>Re-create vm
>>>Remove rescure vm
```

Use Case 2: Continue with preivous/failed rescure job
```
$pd rescure vm <service_name> <vm_name>
>>>There is already a rescure job on-going with vm <vm_name>. Do you want to continue?
>>>Continue(C), Abort(A), Cancel(C)
$C
>>>Continue with rescure job.
```

Use Case 3: List on-going rescure jobs
```
$pd rescure jobs
>>>List all rescure jobs:
>>>Id	Name	Type
>>>-------------------
>>>0	qingfu	vm
>>>1	abel	disk
>>>2	yue	vhd
```

Use Case 4: Remove rescure job
```
$pd rescure jobs rm <job_id>
```

Use Case 5: Continue rescure job
```
$pd rescure jobs continue <job_id>
```

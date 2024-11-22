---
external help file: CCPPSH.dll-Help.xml
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/set-hpcnode?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-HpcNode
---

# Set-HpcNode

## SYNOPSIS
Changes the properties for a node.

## SYNTAX

```
Set-HpcNode [-Description <String>] [-Chassis <String>] [-DataCenter <String>] [-Role <NodeRole[]>]
 [-ManagementIpAddress <String>] [-Rack <String>] [-ProductKey <String>] [-Location <String>]
 [-SubscribedCores <UInt32>] [-SubscribedSockets <UInt32>] [-Affinity <Boolean>] [-Name] <String[]>
  [-Scheduler <String[]>] [<CommonParameters>]
```

```
Set-HpcNode [-Description <String>] [-Chassis <String>] [-DataCenter <String>] [-Role <NodeRole[]>]
 [-ManagementIpAddress <String>] [-Rack <String>] [-ProductKey <String>] [-Location <String>]
 [-SubscribedCores <UInt32>] [-SubscribedSockets <UInt32>] [-Affinity <Boolean>] -Node <HpcNode[]>
  [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-HpcNode** cmdlet changes the properties for one or more nodes, including the description, location, roles, and product key for the nodes.

## EXAMPLES

### Example 1: Set the description for a node: Set the description for a node
```
PS C:\>Set-HpcNode -Name "hpc01cn01" -Description "Test Node"
```

This command sets the description for the node named hpc01cn01 to Test Node.

### Example 2: Set the location for multiple nodes: Set the location for multiple nodes
```
PS C:\>Set-HpcNode -Name "hpc01*" -DataCenter "East"
```

This command sets the data center to East for all nodes with names that start with hpc01.

### Example 3: Set the location for a node: Set the location for a node
```
PS C:\>Set-HpcNode -Name "ComputeNode02" -Location "\center4\rack3\chassis26"
```

This command sets the location of the node named ComputeNode02 to \center4\rack3\chassis26.

### Example 4: Get nodes by group name and set their roles: Get nodes by group name and set their roles
```
PS C:\>Get-HpcNode -GroupName "Broker" | Set-HpcNode -Role BrokerNode
```

This command gets the **HpcNode** objects for all nodes in the node group named Broker, and sets the roles for those nodes to BrokerNode.

## PARAMETERS

### -Chassis
Specifies the chassis in which the node is located.
If you specify the *Chassis* parameter, you must also specify the *DataCenter* and *Rack* parameters. This parameter is deprecated as of Microsoft® HPC Pack 2012.
Use the *Location* parameter instead.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DataCenter
Specifies the data center in which the node is located. This parameter is deprecated as of Microsoft® HPC Pack 2012. Use the *Location* parameter instead.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the node.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Location
Specifies the location of the node as a string with a format. This parameter was introduced in HPC Pack 2008 R2.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementIpAddress
Specifies an IP address that Intelligent Platform Management Interface (IPMI) tools can use to manage power on the node.
The format of the value for this parameter is the same as the format of a valid IP address.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies an array of names for the nodes for which you want to change the properties.
You cannot specify both the *Name* and *Node* parameters.

```yaml
Type: String[]
Parameter Sets: Name
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Node
Specifies an array of **HpcNode** objects for the nodes for which you want to change the properties.
Use the Get-HpcNode cmdlet to get the **HpcNode** object for a node.
You cannot specify both the *Node* and the *Name* parameters.

```yaml
Type: HpcNode[]
Parameter Sets: Node
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProductKey
Specifies the product key for Windows Server 2008 to use when you provision the node.
The product key should be in the format of xxxxx-xxxxx-xxxxx-xxxxx-xxxxx, where x is a letter of either case or a digit.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Rack
Specifies a rack position for the node.
If you specify the *Rack* parameter, you must also specify the *DataCenter* parameter.

This parameter is deprecated as of Microsoft® HPC Pack 2012.
Use the Location parameter instead.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Role
Specifies an array of roles for the node.
Valid values are:

- None
- ComputeNode
- BrokerNode
- WorkstationNode

You must take a node offline before you can change the role of the node.
Use the Set-HpcNodeState cmdlet to take nodes offline.

```yaml
Type: NodeRole[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that includes the nodes.
The value must be a valid computer name or IP address.
If you do not specify the *Scheduler* parameter, this cmdlet uses the scheduler on the head node that the CCP_SCHEDULER environment variable specifies.
To set this environment variable, run the following cmdlet: **Set-Content Env: CCP_CONNECTIONSTRING \<head_node_name\>**.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Affinity
Indicates how affinity is managed for tasks that run on the node.
By default, the value is $Null, which means that affinity is managed according to the job scheduler affinity policy.
If this property is set, node affinity overrides the job scheduler affinity settings.
A value of 0 or $False specifies that affinity on the node is not managed by the HPC services, and the operating system or the application manages placement of tasks on physical cores.
A value of 1 or $True specifies that the HPC Node Manager Service sets affinity for tasks (assigns tasks to specific cores).

For more information relating to affinity, see Understanding Affinityhttp://technet.microsoft.com/library/ff919424(WS.10).aspx.

This parameter was introduced in HPC Pack 2008 R2 with Service Pack 2 (SP2).
It is not supported in previous versions.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscribedCores
Specifies the number of cores that you want the HPC job scheduler service to use when it is allocating tasks to the node.
This value may be smaller than, or exceed the number of physical cores.
To clear this property, set the value to $Null.
If this value is $Null, the number of physical cores is used.

You should ensure that the number of subscribed cores is divisible by the number of subscribed sockets.
Therefore, each socket must have the same number of cores (for example 4 cores and 2 sockets are valid, but 10 cores and 4 sockets are not).

This parameter was introduced in HPC Pack 2008 R2 with Service Pack 2 (SP2).
It is not supported in previous versions.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscribedSockets
Specifies the number of sockets that the HPC job scheduler service should use when it is allocating tasks to the node.
This value may be smaller than, or exceed the number of actual physical sockets.
To clear this property, set the value to $Null.

You should ensure that the number of subscribed cores is divisible by the number of subscribed sockets.
Therefore, each socket must have the same number of cores (for example 4 cores and 2 sockets is valid, but 10 cores and 4 sockets is not).

This parameter was introduced in HPC Pack 2008 R2 with Service Pack 2 (SP2).
It is not supported in previous versions.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### HpcNode[]

## OUTPUTS

### HpcNode[]

## NOTES
This *DataCenter*, *Rack*, and *Chassis* parameters are deprecated as of HPC Pack 2012. Use the *Location* parameter instead.
If you specify the *Location* parameter for a node when you run **Set-HpcNode**, the *DataCenter*, *Rack*, and *Chassis* properties of the **HpcNode** object for the node do not get set. If you specify the *DataCenter*, *Rack*, or *Chassis* parameter when you run **Set-HpcNode**, the *Location* property of the **HpcNode** object for the node is set to the equivalent location string.
You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcNode](/powershell/module/hpcpack2016/get-hpcnode?view=hpc16-ps)

[Remove-HpcNode](/powershell/module/hpcpack2016/remove-hpcnode?view=hpc16-ps)

[Restart-HpcNode](/powershell/module/hpcpack2016/restart-hpcnode?view=hpc16-ps)

[Shutdown-HpcNode](./Shutdown-HpcNode.md)

[Start-HpcNode](./Start-HpcNode.md)

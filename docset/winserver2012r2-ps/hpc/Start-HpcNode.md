---
external help file: CCPPSH.dll-Help.xml
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/start-hpcnode?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-HpcNode
---

# Start-HpcNode

## SYNOPSIS
Turns on nodes by using an Intelligent Platform Management Interface (IPMI) script.

## SYNTAX

### Name (Default)
```
Start-HpcNode [-Name] <String[]>  [-Scheduler <String[]>]
 [<CommonParameters>]
```

### Node
```
Start-HpcNode -Node <HpcNode[]>  [-Scheduler <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Start-HpcNode** cmdlet turns on one or more nodes by using a preconfigured Intelligent Platform Management Interface (IPMI) script.
Your computer vendor should have configured the IPMI script for your computer.
If the IPMI script is not configured, **Start-HpcNode** generates an error.

## EXAMPLES

### Example 1: Start a node
```
PS C:\>Start-HpcNode -Name "hpc01cn02"
```

This command turns on a node named hpc01cn02.

### Example 2: Get nodes by group name and start them
```
PS C:\>Get-HpcNode -GroupName "Maintenance" | Start-HpcNode
```

This command gets the **HpcNode** objects for all of the nodes in the group named Maintenance, and starts those nodes.

## PARAMETERS

### -Name
Specifies a list of the names of the nodes that you want to turn on.
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
Specifies one or more **HpcNode** objects for the nodes that you want to turn on.
You cannot specify both the *Node* and *Name* parameters.

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

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that includes the nodes.
The value must be a valid computer name or IP address.
If you do not specify the *Scheduler* parameter, this cmdlet uses the scheduler on the head node that the CCP_SCHEDULER environment variable specifies.
To set this environment variable, run the following cmdlet:

`Set-Content Env:CCP_SCHEDULER \<head_node_name\>`

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### HpcNode[]

## OUTPUTS

### None

## NOTES
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcNode](/powershell/module/hpcpack2016/get-hpcnode?view=hpc16-ps)

[Remove-HpcNode](/powershell/module/hpcpack2016/remove-hpcnode?view=hpc16-ps)

[Restart-HpcNode](/powershell/module/hpcpack2016/restart-hpcnode?view=hpc16-ps)

[Set-HpcNode](./Set-HpcNode.md)

[Shutdown-HpcNode](./Shutdown-HpcNode.md)

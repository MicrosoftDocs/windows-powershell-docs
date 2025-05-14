---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/resume-vmreplication?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-VMReplication
---

# Resume-VMReplication

## SYNOPSIS
Resumes a virtual machine replication that is in a state of Paused, Error, Resynchronization Required, or Suspended.

## SYNTAX

### VMName (Default)
```
Resume-VMReplication [-ComputerName <String[]>] [-VMName] <String[]>
 [-ReplicationRelationshipType <VMReplicationRelationshipType>] [-ResynchronizeStartTime <DateTime>]
 [-Resynchronize] [-AsJob] [-Continue] [-Passthru] [-CimSession <CimSession[]>] [-Credential <PSCredential[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Resume-VMReplication [-VM] <VirtualMachine[]> [-ReplicationRelationshipType <VMReplicationRelationshipType>]
 [-ResynchronizeStartTime <DateTime>] [-Resynchronize] [-AsJob] [-Continue] [-Passthru]
 [-CimSession <CimSession[]>] [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMReplication
```
Resume-VMReplication [-VMReplication] <VMReplication[]> [-ResynchronizeStartTime <DateTime>] [-Resynchronize]
 [-AsJob] [-Continue] [-Passthru] [-CimSession <CimSession[]>] [-Credential <PSCredential[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Resume-VMReplication** cmdlet resumes replication of a virtual machine with a replication state of Paused, Error, Resynchronization Required, or Suspended.

## EXAMPLES

### Example 1
```
PS C:\> Resume-VMReplication VM01
```

This example resumes replication of virtual machine VM01.

### Example 2
```
PS C:\> Resume-VMReplication VM01 -Resynchronize
```

This example resynchronizes replication of virtual machine VM01.

### Example 3
```
PS C:\> Resume-VMReplication VM01 -Resynchronize -ResynchronizeStartTime "8/1/2012 05:00 AM"
```

This example schedules the resynchronization of replication for virtual machine VM01 to start at 5:00 AM on August 1, 2012.

### Example 4
```
PS C:\> Resume-VMReplication *
```

This example resumes replication of all virtual machines for which replication is paused.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual machine replication is to be resumed.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Continue
Indicates that Hyper-V Replica continues the resynchronization comparisons from where it left off when you resume the virtual machine replication.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Indicates that this cmdlet returns a **VMReplication** object.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicationRelationshipType
Specifies the replication relationship type of the virtual machine.
Specify whether the replication relationship is a simple primary to replica or is an extended replication chain.
The cmdlet resumes the replication of the virtual machines that have the replication type that you specify.

```yaml
Type: VMReplicationRelationshipType
Parameter Sets: VMName, VMObject
Aliases: Relationship
Accepted values: Simple, Extended

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Resynchronize
Specifies that resynchronization is to be started for the virtual machine.
Resynchronization requires significant storage, processor, and network resources.
We recommend running this process during off-peak hours.
Use the **Set-VMReplication** cmdlet to specify whether to automatically resynchronize the virtual machine in the future.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: Resync

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResynchronizeStartTime
Specifies when resynchronization should start.
If not specified, resynchronization starts immediately.
You can schedule the resynchronization to start up to 7 days later.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: ResyncStart

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine whose replication is to be resumed.

```yaml
Type: VirtualMachine[]
Parameter Sets: VMObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine whose replication is to be resumed.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMReplication
Specifies a virtual machine replication object representing the virtual machine replication to be resumed.

```yaml
Type: VMReplication[]
Parameter Sets: VMReplication
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### None
Default

### VMReplication
If **-PassThru** is specified.

## NOTES

## RELATED LINKS


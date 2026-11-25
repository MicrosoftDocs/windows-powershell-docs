---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/stop-vmreplication?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-VMReplication
---

# Stop-VMReplication

## SYNOPSIS
Cancels an ongoing virtual machine resynchronization.

## SYNTAX

### VMName (Default)
```
Stop-VMReplication [-ComputerName <String[]>] [-VMName] <String[]>
 [-ReplicationRelationshipType <VMReplicationRelationshipType>] [-Passthru] [-CimSession <CimSession[]>]
 [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Stop-VMReplication [-VM] <VirtualMachine[]> [-ReplicationRelationshipType <VMReplicationRelationshipType>]
 [-Passthru] [-CimSession <CimSession[]>] [-Credential <PSCredential[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMReplication
```
Stop-VMReplication [-VMReplication] <VMReplication[]> [-Passthru] [-CimSession <CimSession[]>]
 [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-VMReplication** cmdlet cancels an ongoing virtual machine resynchronization.

## EXAMPLES

### Example 1
```
PS C:\> Stop-VMReplication *
```

Stops all ongoing replications of virtual machines on the local server that runs Hyper-V.

## PARAMETERS

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
Specifies one or more Hyper-V hosts on which the ongoing virtual machine resynchronization is to be stopped.
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
Specifies that an object is to be passed through to the pipeline representing the virtual machine on which the ongoing virtual machine resynchronization is to be stopped.

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
The cmdlet cancels the ongoing resynchronization of the virtual machines that have the replication type that you specify.

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

### -VM
Specifies the virtual machine whose resynchronization is to be stopped.

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
Specifies the name of the virtual machine whose resynchronization is to be stopped.

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
Specifies the resynchronization to be stopped.

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

### Microsoft.HyperV.PowerShell.VirtualMachine
If **-PassThru** is specified.

## NOTES

## RELATED LINKS


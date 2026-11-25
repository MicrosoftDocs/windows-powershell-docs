---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/start-vminitialreplication?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-VMInitialReplication
---

# Start-VMInitialReplication

## SYNOPSIS
Starts replication of a virtual machine.

## SYNTAX

### VMName (Default)
```
Start-VMInitialReplication [-ComputerName <String[]>] [-VMName] <String[]> [-DestinationPath <String>]
 [-InitialReplicationStartTime <DateTime>] [-UseBackup] [-AsJob] [-Passthru] [-CimSession <CimSession[]>]
 [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Start-VMInitialReplication [-VM] <VirtualMachine[]> [-DestinationPath <String>]
 [-InitialReplicationStartTime <DateTime>] [-UseBackup] [-AsJob] [-Passthru] [-CimSession <CimSession[]>]
 [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMReplication
```
Start-VMInitialReplication [-VMReplication] <VMReplication[]> [-DestinationPath <String>]
 [-InitialReplicationStartTime <DateTime>] [-UseBackup] [-AsJob] [-Passthru] [-CimSession <CimSession[]>]
 [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-VMInitialReplication** cmdlet starts replication of a virtual machine using the method you select.
You also can schedule replication to start up to 7 days later.

## EXAMPLES

### Example 1
```
PS C:\> Start-VMInitialReplication VM01
```

This example starts initial replication of virtual machine VM01 over the network.

### Example 2
```
PS C:\> Start-VMInitialReplication *
```

This example starts initial replication over the network for all the virtual machines on the local Hyper-V host for which initial replication is pending.

### Example 3
```
PS C:\> Start-VMInitialReplication * -DestinationPath R:\IRLoc
```

This example exports the initial replication of all virtual machines on the local Hyper-V host for which initial replication is pending, to the location R:\IRLoc.
This example assumes that the location is an external drive, which would be shipped to the Replica site so that the initial replication can be completed.

### Example 4
```
PS C:\> Enable-VMReplication VM01 -AsReplica -computername MyReplica.contoso.com
PS C:\> Enable-VMReplication VMO1 -ReplicaServerName ReplicaServer01 -ReplicaServerPort 80 -AuthenticationType Kerberos -computername MyPrimary.contoso.comPS
PS C:\> Start-VMInitialReplication VM01 -usebackup -computername MyPrimary.contoso.com
```

This example uses several consecutive commands to start initial replication from backup.
First, it enables a restored copy of virtual machine VM01 on the Replica server as a Replica virtual machine.
Then, it enables replication for VM01 from the primary server.
Finally, it starts the initial replication to use the restored copy of VM01 on Replica server as the basis of the initial replication.

### Example 5
```
PS C:\> $VMRepl = Get-VMReplication -VMName MyVM
PS C:\> Start-VMInitialReplication -VMReplication $VMRepl
```

The first command returns a VMReplication object for the VM named MyVM and stores it in the variable $VMRepl.

The second cmdlet then uses this object to start the initial replication for the stored VM.

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
Specifies one or more Hyper-V hosts on which replication of a virtual machine is to be started.
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

### -DestinationPath
Specifies the path to use when copying the files for initial replication; assumes use of external media as the method for initial replication.
External media is typically a removable drive that is shipped to the location of the Replica server.
When the external media arrives at the Replica site, use the **Import-InitialVMReplication** cmdlet on the Replica virtual machine to copy the files.

```yaml
Type: String
Parameter Sets: (All)
Aliases: IRLoc

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitialReplicationStartTime
Specifies the time to start the initial replication, when scheduling initial replication to occur later.
You can specify a time up to 7 days later.
When this parameter is not specified, initial replication occurs immediately.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: IRTime

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a virtual machine object is to be passed through to the pipeline representing the virtual machine on which replication is to be started.

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

### -UseBackup
Indicates that you want to use a copy of this virtual machine on the Replica server as the basis for the initial replication.
Specify this option only if it was specified when replication was enabled on the primary virtual machine.

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

### -VM
Specifies the virtual machine on which replication is to be started.

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
Specifies the name of the virtual machine on which replication is to be started.

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
Specifies an object that represents the replication to be started.
You can get this object from the **Get-VMReplication** cmdlet.

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


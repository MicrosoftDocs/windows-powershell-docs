---
description: Gets the host machine’s partitionable GPU.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 09/22/2022
online version: https://learn.microsoft.com/en-us/powershell/module/hyper-v/get-vmhostpartitionablegpu?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-VMHostPartitionableGpu

## SYNOPSIS
Gets the host machine’s partitionable GPU.

## SYNTAX

### ComputerName (Default)
```
Get-VMHostPartitionableGpu [[-ComputerName] <String[]>] [[-Credential] <PSCredential[]>] [-Name <String>]
 [<CommonParameters>]
```

### CimSession
```
Get-VMHostPartitionableGpu [-CimSession] <CimSession[]> [-Name <String>] [<CommonParameters>]
```

## DESCRIPTION
The Get-VMHostPartitionableGpu cmdlet get the host machine’s partitionable Graphic Processing Unit.
This displays the information of the GPU as provided by the manufacturer driver.

## EXAMPLES

### Example 1
```
PS C:\> Get-VMHostPartitionableGpu
```

Gets the details of the local partitionable graphic processing unit on the host

### Example 2
```powershell
PS C:\> Get-VMHostPartitionableGpu -ComputerName "SampleHost"
```

Display a partitionable GPU by using the Host Name. This command will display all the GPU devices available for partitioning in the host:

### Example 3
```powershell
PS C:\> Get-VMHostPartitionableGpu -name "SampleGPUDeviceIDName"
```

Display a partitionable GPU by using the specific GPU Device Name. The result will show the details of the specific GPU listed:

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: CimSession
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts that run this cmdlet.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: ComputerName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: ComputerName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the graphic processing unit to be retrieved

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimSession[]

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMHostPartitionableGpu

## NOTES

## RELATED LINKS

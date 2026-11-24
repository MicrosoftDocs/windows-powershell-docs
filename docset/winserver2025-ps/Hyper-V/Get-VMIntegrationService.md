---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmintegrationservice?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMIntegrationService
---

# Get-VMIntegrationService

## SYNOPSIS
Gets the integration services of a virtual machine or snapshot.

## SYNTAX

### VMName (Default)
```
Get-VMIntegrationService [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMName] <String[]> [[-Name] <String[]>] [<CommonParameters>]
```

### VMObject
```
Get-VMIntegrationService [-VM] <VirtualMachine[]> [[-Name] <String[]>] [<CommonParameters>]
```

### VMSnapshot
```
Get-VMIntegrationService [-VMSnapshot] <VMSnapshot> [[-Name] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMIntegrationService** cmdlet gets the integration services of a virtual machine or snapshot.

## EXAMPLES

### Example 1
```
PS C:\> Get-VMIntegrationService -VMName TestVM | Where-Object {$_.SecondaryOperationalStatus -eq 'ProtocolMismatch'}
```

Gets the out-of-date integration services from virtual machine TestVM.

### Example 2
```
PS C:\> Get-VM -Name TestVM | Get-VMIntegrationService -Name Shutdown,VSS
```

Gets the Shutdown and VSS integration services from virtual machine TestVM.

### Example 3
```
PS C:\> Get-VMSnapshot -VMName TestVM -Name 'Before applying updates' | Get-VMIntegrationService Shutdown,VSS
```

Gets the Shutdown and VSS integration services from the snapshot Before applying updates of virtual machine TestVM.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the integration services are to be retrieved.
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

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the integration service to be retrieved.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine from which the integration services are to be retrieved.

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
Specifies the name of the virtual machine from which the integration services are to be retrieved.

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

### -VMSnapshot
Specifies the snapshot from which the integration services are to be retrieved.

```yaml
Type: VMSnapshot
Parameter Sets: VMSnapshot
Aliases: VMCheckpoint

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMIntegrationComponent

## NOTES

## RELATED LINKS


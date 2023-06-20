---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmintegrationservice?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMIntegrationService
---

# Get-VMIntegrationService

## SYNOPSIS
Gets the integration services of a virtual machine or snapshot.

## SYNTAX

### VMName (Default)
```
Get-VMIntegrationService [-ComputerName <String[]>] [-VMName] <String[]> [[-Name] <String[]>]
 [<CommonParameters>]
```

### VMSnapshot
```
Get-VMIntegrationService [-VMSnapshot] <VMSnapshot> [[-Name] <String[]>] [<CommonParameters>]
```

### VMObject
```
Get-VMIntegrationService [[-Name] <String[]>] [-VM] <VirtualMachine[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMIntegrationService** cmdlet gets the integration services of a virtual machine or snapshot.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMIntegrationService -VMName TestVM | Where-Object {$_.SecondaryOperationalStatus -eq 'ProtocolMismatch'}
```

Gets the out-of-date integration services from virtual machine TestVM.

### Example 2
```
PS C:\>Get-VM -Name TestVM | Get-VMIntegrationService -Name Shutdown,VSS
```

Gets the Shutdown and VSS integration services from virtual machine TestVM.

### Example 3
```
PS C:\>Get-VMSnapshot -VMName TestVM -Name 'Before applying updates' | Get-VMIntegrationService Shutdown,VSS
```

Gets the Shutdown and VSS integration services from the snapshot Before applying updates of virtual machine TestVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the integration services are to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: 

Required: False
Position: Named
Default value: .
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
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.IntegrationService

## NOTES

## RELATED LINKS


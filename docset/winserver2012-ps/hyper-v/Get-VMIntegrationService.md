---
author: Kateyanne
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmintegrationservice?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-VMIntegrationService

## SYNOPSIS
Gets the integration services of a virtual machine or snapshot.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VMIntegrationService [-VMName] <String[]> [[-Name] <String[]>] [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-VMIntegrationService [-VM] <VirtualMachine[]> [[-Name] <String[]>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-VMIntegrationService [-VMSnapshot] <VMSnapshot> [[-Name] <String[]>]
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -VM
Specifies the virtual machine from which the integration services are to be retrieved.

```yaml
Type: VirtualMachine[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine from which the integration services are to be retrieved.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -VMSnapshot
Specifies the snapshot from which the integration services are to be retrieved.

```yaml
Type: VMSnapshot
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Virtualization.PowerShell.IntegrationService

## NOTES

## RELATED LINKS




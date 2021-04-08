---
author: Kateyanne
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/hyper-v/disconnect-vmnetworkadapter?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Disconnect-VMNetworkAdapter

## SYNOPSIS
Disconnects a virtual network adapter from a virtual switch or Ethernet resource pool.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Disconnect-VMNetworkAdapter [-VMName] <String[]> [[-Name] <String[]>] [-ComputerName <String[]>] [-Passthru]
```

### UNNAMED_PARAMETER_SET_2
```
Disconnect-VMNetworkAdapter [-VMNetworkAdapter] <VMNetworkAdapter[]> [-Passthru]
```

## DESCRIPTION
The **Disconnect-VMNetworkAdapter** cmdlet disconnects a virtual network adapter from a virtual switch or Ethernet resource pool.

## EXAMPLES

### Example 1
```
PS C:\>Disconnect-VMNetworkAdapter -VMNetworkAdapter Test1
```

Disconnects virtual network adapter Test1.

### Example 2
```
PS C:\>Get-VMNetworkAdapter -VMName * | Where-Object {$_.SwitchName -eq 'InternetAccess'} | Disconnect-VMNetworkAdapter
```

Disconnects all virtual network adapters whose SwitchName is InternetAccess in all virtual machines on the local Hyper-V server.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which a virtual network adapter is to be disconnected.
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
Specifies the name of the virtual network adapter to be disconnected.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.Virtualization.Powershell.VMNetworkAdapter** object is to be passed through to the pipeline representing the virtual network adapter to be disconnected.

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

### -VMName
Specifies the name of the virtual machine in which the virtual network adapter is to be disconnected.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMNetworkAdapter
Specifies the virtual network adapter to be disconnected.

```yaml
Type: VMNetworkAdapter[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.Virtualization.Powershell.VMNetworkAdapter
If **-PassThru** is specified.

## NOTES

## RELATED LINKS




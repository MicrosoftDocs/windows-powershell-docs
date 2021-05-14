---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmswitch?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-VMSwitch

## SYNOPSIS
Gets virtual switches from one or more virtual Hyper-V hosts.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VMSwitch [[-Name] <String>] [[-ResourcePoolName] <String[]>] [-ComputerName <String[]>]
 [-SwitchType <VMSwitchType[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-VMSwitch [[-Id] <Guid[]>] [[-ResourcePoolName] <String[]>] [-ComputerName <String[]>]
 [-SwitchType <VMSwitchType[]>]
```

## DESCRIPTION
The **Get-VMSwitch** gets the virtual switches from a Hyper-V host.
If you specify no parameters, this cmdlet returns all virtual switches from the local Hyper-V host.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMSwitch
```

Gets all virtual switches from the local Hyper-V host.

### Example 2
```
PS C:\>Get-VMSwitch -SwitchType External
```

Gets all virtual switches that connect to the external network.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts from which virtual switches are to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the unique identifier of the virtual switch to be retrieved.

```yaml
Type: Guid[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the virtual switch to be retrieved.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -ResourcePoolName
Specifies the resource pool from which the virtual switches are to be retrieved.

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

### -SwitchType
Specifies the type of the virtual switches to be retrieved.
Allowed values are **External**, **Internal**, and **Private**.

```yaml
Type: VMSwitchType[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

## INPUTS

## OUTPUTS

### Microsoft.Virtualization.Powershell.EthernetSwitch

## NOTES

## RELATED LINKS




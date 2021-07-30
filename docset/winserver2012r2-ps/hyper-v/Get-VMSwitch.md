---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmswitch?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMSwitch
---

# Get-VMSwitch

## SYNOPSIS
Gets virtual switches from one or more virtual Hyper-V hosts.

## SYNTAX

### Name (Default)
```
Get-VMSwitch [[-Name] <String>] [[-ResourcePoolName] <String[]>] [-SwitchType <VMSwitchType[]>]
 [-ComputerName <String[]>] [<CommonParameters>]
```

### Id
```
Get-VMSwitch [[-Id] <Guid[]>] [[-ResourcePoolName] <String[]>] [-SwitchType <VMSwitchType[]>]
 [-ComputerName <String[]>] [<CommonParameters>]
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
Parameter Sets: Id
Aliases: SwitchId

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the virtual switch to be retrieved.

```yaml
Type: String
Parameter Sets: Name
Aliases: SwitchName

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourcePoolName
Specifies the resource pool from which the virtual switches are to be retrieved.

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

### -SwitchType
Specifies the type of the virtual switches to be retrieved.
Allowed values are **External**, **Internal**, and **Private**.

```yaml
Type: VMSwitchType[]
Parameter Sets: (All)
Aliases: 
Accepted values: Private, Internal, External

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.EthernetSwitch

## NOTES

## RELATED LINKS


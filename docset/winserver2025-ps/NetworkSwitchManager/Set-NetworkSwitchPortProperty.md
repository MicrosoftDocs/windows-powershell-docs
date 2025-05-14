---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetworkSwitchEthernetPort.psm1-help.xml
Module Name: NetworkSwitchManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkswitchmanager/set-networkswitchportproperty?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetworkSwitchPortProperty
---

# Set-NetworkSwitchPortProperty

## SYNOPSIS
Sets the port properties for a network switch.

## SYNTAX

```
Set-NetworkSwitchPortProperty [-CimSession] <CimSession> [[-Property] <Hashtable>]
 [-InputObject] <CimInstance[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetworkSwitchPortProperty** cmdlet sets the port properties for a network switch.
This cmdlet can modify any property.
If you run this cmdlet, you must specify at least one property to change.
Otherwise, the command returns an error.

## EXAMPLES

### Example 1: Set properties for a port
```
PS C:\>$Session = New-CimSession -ComputerName "NetworkSwitch08"
PS C:\> $PortSpeed = 1
PS C:\> $Description = "Port on management device 02."
PS C:\> Set-NetworkSwitchPortProperty -CimSession $Session -Property @{Speed = $portSpeed; Description = $Description }
```

The first command creates a **CimSession** for a network switch, and then stores it in the **$Session** variable.
For more information about **CimSession** objects, type `Get-Help New-CimSession`.

The second and third commands assign values to the **$PortSpeed** variable and the **$Description** variable.
These are the values of the key/value pairs.

The final command sets a properties by using the **$Session** object.
The command uses standard syntax to create a hash table that contains the key/value pairs as the value of the **Property** parameter.

## PARAMETERS

### -CimSession
Specifies the **CimSession** that this cmdlet uses to connect to the network switch.
For more information about **CimSession** objects, type `Get-Help New-CimSession`.

```yaml
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Property
Specifies a hash table of name/value pairs.
The cmdlet sets the properties that this parameter specifies.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance[]
You can pipe an array of **CimInstance** objects to this cmdlet.

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Set-NetworkSwitchVlanProperty](./Set-NetworkSwitchVlanProperty.md)


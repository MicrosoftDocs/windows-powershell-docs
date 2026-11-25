---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetworkSwitchFeature.psm1-help.xml
Module Name: NetworkSwitchManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkswitchmanager/disable-networkswitchfeature?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-NetworkSwitchFeature
---

# Disable-NetworkSwitchFeature

## SYNOPSIS
Disables features of a network switch.

## SYNTAX

### FeatureNameSet
```
Disable-NetworkSwitchFeature -CimSession <CimSession> -FeatureName <Int32> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### NameSet
```
Disable-NetworkSwitchFeature -CimSession <CimSession> -Name <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InstanceIdSet
```
Disable-NetworkSwitchFeature -CimSession <CimSession> -InstanceId <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObjectSet
```
Disable-NetworkSwitchFeature -CimSession <CimSession> -InputObject <CimInstance[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Disable-NetworkSwitchFeature** cmdlet disables specified features of a network switch.

## EXAMPLES

### Example 1: Disable a feature by using its name
```
PS C:\>$Session = New-CimSession -ComputerName "NetworkSwitch08"
PS C:\> Disable-NetworkSwitchFeature -CimSession $Session -Name "SSH"
```

The first command creates a **CimSession** for a network switch, and then stores it in the **$Session** variable.
For more information about **CimSession** objects, type `Get-Help New-CimSession`.

The second command disables the feature named SSH for the network switch NetworkSwitch08 by using the **$Session** object.

### Example 2: Disable a feature by using an instance ID
```
PS C:\>Disable-NetworkSwitchFeature -CimSession $Session -InstanceID "Contoso:Feature:2"
```

This command disables a feature by using the instance ID to identify it.
The command includes a **CimSession**, similar to the first example.

## PARAMETERS

### -CimSession
Specifies the **CimSession** that this cmdlet uses to connect to the network switch.
For more information about **CimSession** objects, type `Get-Help New-CimSession`.

```yaml
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: True
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FeatureName
Specifies a feature name, an integer, of a feature to disable.
A feature name might not be unique.
This cmdlet disables all features with the same name.

```yaml
Type: Int32
Parameter Sets: FeatureNameSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObjectSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InstanceId
Specifies the instance ID of a feature to disable.

```yaml
Type: String
Parameter Sets: InstanceIdSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a feature to disable.
This parameter supports wildcard characters.

```yaml
Type: String
Parameter Sets: NameSet
Aliases:

Required: True
Position: Named
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
You can pipe an array of **CimInstance** objects that correspond to a feature to this cmdlet.

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Enable-NetworkSwitchFeature](./Enable-NetworkSwitchFeature.md)

[Get-NetworkSwitchFeature](./Get-NetworkSwitchFeature.md)


---
external help file: Microsoft.Windows.Bcd.Cmdlets.dll-Help.xml
Module Name: Microsoft.Windows.Bcd.Cmdlets
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/microsoft.windows.bcd.cmdlets/remove-bcdelement?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-BcdElement
---

# Remove-BcdElement

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### Id
```
Remove-BcdElement [-Element] <String> [[-Id] <String>] [[-Store] <BcdStoreInfo>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Entry
```
Remove-BcdElement [-Element] <String> [-Entry] <BcdEntryInfo> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -Element
{{ Fill Element Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Entry
{{ Fill Entry Description }}

```yaml
Type: Microsoft.Windows.Bcd.Cmdlets.BcdExtensions.BcdEntryInfo
Parameter Sets: Entry
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
{{ Fill Force Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
{{ Fill Id Description }}

```yaml
Type: System.String
Parameter Sets: Id
Aliases: Identifier

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Store
{{ Fill Store Description }}

```yaml
Type: Microsoft.Windows.Bcd.Cmdlets.BcdExtensions.BcdStoreInfo
Parameter Sets: Id
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

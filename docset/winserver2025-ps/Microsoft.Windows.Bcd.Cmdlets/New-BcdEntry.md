---
external help file: Microsoft.Windows.Bcd.Cmdlets.dll-Help.xml
Module Name: Microsoft.Windows.Bcd.Cmdlets
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/microsoft.windows.bcd.cmdlets/new-bcdentry?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-BcdEntry
---

# New-BcdEntry

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### Application
```
New-BcdEntry -Application <String> [-Description <String>] [[-Id] <String>] [[-Store] <BcdStoreInfo>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Device
```
New-BcdEntry [-Description <String>] [-Device] [[-Id] <String>] [[-Store] <BcdStoreInfo>] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Inherit
```
New-BcdEntry [-Description <String>] [[-Id] <String>] -Inherit <String> [[-Store] <BcdStoreInfo>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Default
```
New-BcdEntry [-Description <String>] [-Id] <String> [[-Store] <BcdStoreInfo>] [-Force] [-WhatIf] [-Confirm]
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

### -Application
{{ Fill Application Description }}

```yaml
Type: System.String
Parameter Sets: Application
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
{{ Fill Description Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Device
{{ Fill Device Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Device
Aliases:

Required: True
Position: Named
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
Parameter Sets: Application, Device, Inherit
Aliases: Identifier

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: Default
Aliases: Identifier

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Inherit
{{ Fill Inherit Description }}

```yaml
Type: System.String
Parameter Sets: Inherit
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Store
{{ Fill Store Description }}

```yaml
Type: Microsoft.Windows.Bcd.Cmdlets.BcdExtensions.BcdStoreInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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

### Microsoft.Windows.Bcd.Cmdlets.BcdExtensions.BcdEntryInfo

## NOTES

## RELATED LINKS

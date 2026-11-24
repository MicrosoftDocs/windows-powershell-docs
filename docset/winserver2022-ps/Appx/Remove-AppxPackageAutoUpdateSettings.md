---
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
Module Name: appx
online version: https://go.microsoft.com/fwlink/?LinkId=246400
schema: 2.0.0
title: Remove-AppxPackageAutoUpdateSettings
---

# Remove-AppxPackageAutoUpdateSettings

## SYNOPSIS
Removes settings configured for a particular Windows app.

## SYNTAX

```
Remove-AppxPackageAutoUpdateSettings [-PackageFamilyName] <String> [-UseSystemPolicySource] [-AllUsers]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The 'Remove-AppxPackageAutoUpdateSettings' PowerShell cmdlet removes the settings configured for a specific or all installed Windows apps in relation to the Auto Update and Repair settings.

## EXAMPLES

### Example 1
```powershell
PS C:\> Remove-AppxPackageAutoUpdateSettings -PackageFullName publisher.package1_1.0.0.0_neutral__8wekyb3d8bbwe
```

This example removes the Auto Update and Repair settings for a specific Windows app that has been installed and registered to the signed-in user.

## PARAMETERS

### -AllUsers
{{ Fill AllUsers Description }}

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

### -PackageFamilyName
{{ Fill PackageFamilyName Description }}

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

### -UseSystemPolicySource
{{ Fill UseSystemPolicySource Description }}

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

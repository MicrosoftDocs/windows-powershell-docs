---
external help file: Microsoft.Windows.DeveloperLicense.Commands.dll-Help.xml
Module Name: WindowsDeveloperLicense
online version: https://docs.microsoft.com/powershell/module/windowsdeveloperlicense/unregister-windowsdeveloperlicense?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Unregister-WindowsDeveloperLicense

## SYNOPSIS
Removes the developer license from the current computer.

## SYNTAX

```
Unregister-WindowsDeveloperLicense [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Unregister-WindowsDeveloperLicense** cmdlet removes a developer license from the current computer.
If you remove the developer license, you can no longer install and test your apps.
Any developer apps no longer run on the current computer.
For more information about developer licenses, see Get a developer license (Windows Store apps) (Windows)http://msdn.microsoft.com/en-us/library/windows/apps/hh974578.aspx (http://msdn.microsoft.com/en-us/library/windows/apps/hh974578.aspx) in the Microsoft Developer Network library.

You need Administrator rights to remove a developer license.
If the cmdlet cannot find a developer license, it returns an error that informs you that there is no developer license on the current computer.

## EXAMPLES

### Example 1: Remove a developer license
```
PS C:\> Unregister-WindowsDeveloperLicense
```

This command removes a developer license from the current computer.
The cmdlet prompts you for confirmation before it removes the license.
To skip this prompt, use the **Force** parameter.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Removes a developer license without prompting you for confirmation.
By default, the cmdlet prompts you for confirmation before it proceeds.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WindowsDeveloperLicense](./Get-WindowsDeveloperLicense.md)

[Show-WindowsDeveloperLicenseRegistration](./Show-WindowsDeveloperLicenseRegistration.md)


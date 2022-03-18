---
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
Module Name: appx
online version: https://docs.microsoft.com/powershell/module/appx/remove-appsharedpackagecontainer?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-AppSharedPackageContainer

## SYNOPSIS
Removes the shared package container.

## SYNTAX

```
Remove-AppSharedPackageContainer [-Name] <String> [-ForceApplicationShutdown] [-AllUsers] [<CommonParameters>]
```

## DESCRIPTION 
The Remove-AppSharedPackageContainer cmdlet removes the shared package container definiton for the particular user.

## EXAMPLES

### Example 1
```powershell
PS C:\> Remove-AppSharedPackageContainer -Name ContosoTestContainer
```

This command removes the shared package container definiton with the name ContosoTestContainer

## PARAMETERS

### -AllUsers
Remove matching packages that are deployed to any user

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

### -ForceApplicationShutdown
Closes all packages in the Shared Package Container

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

### -Name
The name of the container.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

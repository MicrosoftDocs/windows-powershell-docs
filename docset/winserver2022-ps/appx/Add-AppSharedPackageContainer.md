---
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
Module Name: appx
online version: https://docs.microsoft.com/powershell/module/appx/get-appxlog?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-AppSharedPackageContainer

## SYNOPSIS
Deploys the shared package container definiton.

## SYNTAX

```
Add-AppSharedPackageContainer [-Path] <String> [-ForceApplicationShutdown] [-Merge] [-Force]
 [<CommonParameters>]
```

## DESCRIPTION
The Add-AppSharedPackageContainer cmdlet deploys the shared package container definiton for the particular user.

## EXAMPLES

### Example 1
```powershell
PS C:\> Add-AppSharedPackageContainer -Path C:\MyFolder\ContosoTestContainer.xml
```

This command deploys the definition described in the ContosoTestContainer file

## PARAMETERS

### -Force
Replaces an existing container of the same name with the newly created
container's definition for the target user(s)


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
Closes all packages currently running in the Shared Package Container

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

### -Merge
Merges a new container's definition into an existing container
definition of the same name for target user(s)


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

### -Path
Path to the XML definition file

```yaml
Type: String
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

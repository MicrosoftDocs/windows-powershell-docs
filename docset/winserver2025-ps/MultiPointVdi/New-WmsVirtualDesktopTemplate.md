---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPointVdi.dll-Help.xml
Module Name: MultiPointVdi
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipointvdi/new-wmsvirtualdesktoptemplate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-WmsVirtualDesktopTemplate
---

# New-WmsVirtualDesktopTemplate

## SYNOPSIS
Create a virtual desktop template.

## SYNTAX

### NonDomainJoin
```
New-WmsVirtualDesktopTemplate -InputFilePath <String> [-VhdLocation <String>] -TemplatePrefix <String>
 -AdministratorUser <String> -AdministratorPassword <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DomainJoin
```
New-WmsVirtualDesktopTemplate -InputFilePath <String> [-VhdLocation <String>] -TemplatePrefix <String>
 -AdministratorUser <String> -Domain <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-WmsVirtualDesktopTemplate** cmdlet shuts down all station virtual desktops based on an existing template of the same name.
It then creates a virtual desktop template using the virtual hard disk created with Import-WmsVirtualDesktop.
This virtual desktop is in either a workgroup or attached to the supplied domain, and has an administrative account with the specified user name and password.

## EXAMPLES

### Example 1: Create a virtual desktop template
```
PS C:\> New-WmsVirtualDesktopTemplate -InputFilePath "C:\Images\Windows10Enterprise.iso" -TemplatePrefix "MyVdiImage" -VhdLocation "C:\MultiPointVhdImages" -AdministratorUser "admin" -AdministratorPassword "password"
```

This command creates a virtual desktop template that you can customize or use to generate station virtual desktops.

## PARAMETERS

### -AdministratorPassword
Specifies the password to assign to the Administrator account.

```yaml
Type: String
Parameter Sets: NonDomainJoin
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdministratorUser
Specifies the name of a user to create in the virtual desktop template that has Administrator privileges.

```yaml
Type: String
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Domain
Specifies the name of the Active Directory domain for the virtual desktop.

```yaml
Type: String
Parameter Sets: DomainJoin
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputFilePath
Specifies the full path of the input file to use for the virtual desktop template.
Valid file types are .wim, .iso, or .vhd that contains the version of Windows to use as the guest operating system.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TemplatePrefix
Specifies the prefix to use for the name of the virtual machine template.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VhdLocation
Specifies the path to the location to store the desktop template and station .vhd files.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS


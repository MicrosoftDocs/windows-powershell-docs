---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/remove-webvirtualdirectory?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WebVirtualDirectory
---

# Remove-WebVirtualDirectory

## SYNOPSIS
Removes an IIS virtual directory.

## SYNTAX

```
Remove-WebVirtualDirectory [-Site <String>] [-Application <String>] [-Name] <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WebVirtualDirectory** cmdlet removes an Internet Information Services (IIS) virtual directory.

## EXAMPLES

### Example 1: Remove a virtual directory
```
IIS:\> Remove-WebVirtualDirectory -Site "Default Web Site" -Application "TestApp" -Name "TestVirtualDir"
```

This command removes the virtual directory named TestVirtualDir from the default website.

## PARAMETERS

### -Application
Specifies the name of the application that hosts the virtual directory to remove.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Name
Specifies the name of the virtual directory that this cmdlet removes.

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

### -Site
Specifies the name of the site that hosts the virtual directory to remove.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WebVirtualDirectory](./Get-WebVirtualDirectory.md)

[New-WebVirtualDirectory](./New-WebVirtualDirectory.md)


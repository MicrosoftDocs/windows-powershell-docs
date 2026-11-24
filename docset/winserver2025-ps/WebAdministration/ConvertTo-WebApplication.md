---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/convertto-webapplication?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-WebApplication
---

# ConvertTo-WebApplication

## SYNOPSIS
Converts an IIS virtual directory to an IIS web application.

## SYNTAX

```
ConvertTo-WebApplication [-ApplicationPool <String>] [-Force] [[-PSPath] <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **ConvertTo-WebApplication** cmdlet converts an Internet Information Services (IIS) virtual directory to an IIS web application.

## EXAMPLES

### Example 1: Convert a virtual directory to a web application
```
IIS:\> Md $Env:systemdrive\inetpub\Contoso
IIS:\> New-WebVirtualDirectory -Site "Default Web Site" -Name "ContosoVDir" -PhysicalPath "$Env:systemdrive\inetpub\Contoso"
IIS:\> ConvertTo-WebApplication -PSPath "IIS:\Sites\Default Web Site\ContosoVDir"
```

The first command creates a physical directory named Contoso.

The second command creates a virtual directory in IIS that uses that physical directory.

The last command converts the virtual directory to a web application.

## PARAMETERS

### -ApplicationPool
Specifies the application pool in which the application runs.

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

### -Force
Forces the command to run without asking for user confirmation.

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

### -PSPath
Specifies the configuration path.
This can be either an IIS configuration path in the format computer name/webroot/apphost, or the IIS module path in the format IIS:\sites\Default Web Site.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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

[Get-WebApplication](./Get-WebApplication.md)

[New-WebApplication](./New-WebApplication.md)

[New-WebVirtualDirectory](./New-WebVirtualDirectory.md)

[Remove-WebApplication](./Remove-WebApplication.md)


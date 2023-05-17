---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: https://learn.microsoft.com/powershell/module/webadministration/convertto-webapplication?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# ConvertTo-WebApplication

## SYNOPSIS
Converts an IIS virtual directory to an IIS Web application.

## SYNTAX

```
ConvertTo-WebApplication [-ApplicationPool <String>] [-Force] [[-PSPath] <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Converts an IIS virtual directory to an IIS Web application.

## EXAMPLES

### EXAMPLE 1: Convert a Virtual Directory to a Web Application
```
md $env:systemdrive\inetpub\Contoso
New-WebVirtualDirectory -Site "Default Web Site" -Name ContosoVDir -physicalPath $env:systemdrive\inetpub\Contoso 
ConvertTo-WebApplication "IIS:\Sites\Default Web Site\ContosoVDir"
```

This example creates a physical directory named "Contoso." It then creates a virtual directory in IIS that uses that physical directory.
It then converts the virtual directory to a Web application.

## PARAMETERS

### -ApplicationPool
The application pool in which the application runs.

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
Forces the conversion without prompting you for confirmation.

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
This can be either an IIS configuration path in the format computer name/webroot/apphost, or the IIS module path in this format IIS:\sites\Default Web Site.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WebApplication](./Get-WebApplication.md)

[New-WebApplication](./New-WebApplication.md)

[Remove-WebApplication](./Remove-WebApplication.md)


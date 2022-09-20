---
external help file: Microsoft.Management.UI.PowWA.Commands.dll-help.xml
Module Name: PowerShellWebAccess
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/powershellwebaccess/install-pswawebapplication?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Install-PswaWebApplication
---

# Install-PswaWebApplication

## SYNOPSIS
Configures the Windows PowerShell®Web Access web application in IIS.

## SYNTAX

```
Install-PswaWebApplication [[-WebApplicationName] <String>] [-WebSiteName <String>] [-UseTestCertificate]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Install-PswaWebApplication** cmdlet configures Windows PowerShell Web Access web application.
This cmdlet installs the web application, associates it with a web site, and optionally creates a test SSL certificate using the **useTestCertificate** parameter.
For security reasons web administrators should not use a test certificate for production environments.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Install-PswaWebApplication
```

This example installs the PSWA web application using the default values for the **WebApplicationName** (pswa) and **WebSiteName** (Default Web Site) parameters .

### EXAMPLE 2
```
PS C:\>Install-PswaWebApplication -UseTestCertificate
```

This example installs the PSWA web application with a test certificate, and using the default values for the **WebApplicationName** and **WebSiteName** parameters.

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

### -UseTestCertificate
Specifies that a test certificate is created.
If this parameter is set to true, then this cmdlet creates a test certificate and configures the Windows PowerShell Web Access web application to use the certificate for HTTPS requests.
If this parameter is set to false, then no certificate or binding is created.
Set this value to false if another certificate is used for Windows PowerShell Web Access.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -WebApplicationName
Specifies the name for your web application.
This is displayed as the last part of the Windows PowerShell Web Access URL.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: Pswa
Accept pipeline input: False
Accept wildcard characters: False
```

### -WebSiteName
Specifies the name of the Web Server (IIS) website on which to install this Windows PowerShell Web Access web application.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Default Web Site
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

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Add-PswaAuthorizationRule](./Add-PswaAuthorizationRule.md)

[Get-PswaAuthorizationRule](./Get-PswaAuthorizationRule.md)

[Remove-PswaAuthorizationRule](./Remove-PswaAuthorizationRule.md)

[Test-PswaAuthorizationRule](./Test-PswaAuthorizationRule.md)


---
external help file: Microsoft.Management.UI.PowWA.Commands.dll-help.xml
Module Name: PowerShellWebAccess
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/powershellwebaccess/uninstall-pswawebapplication?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-PswaWebApplication
---

# Uninstall-PswaWebApplication

## SYNOPSIS
Uninstalls the Windows PowerShell® web application.

## SYNTAX

```
Uninstall-PswaWebApplication [[-WebApplicationName] <String>] [-WebSiteName <String>] [-DeleteTestCertificate]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Uninstall-PswaWebApplication** cmdlet uninstalls the Windows PowerShell web application and removes the website from IIS.
The cmdlet does not uninstall IIS, or any other features installed because they were required for Windows PowerShell to run.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Uninstall-PswaWebApplication
```

This command uninstalls the Windows PowerShell Web Application.
You can use this cmdlet to uninstall the Windows PowerShell Web Application if you installed it using the default values.

### EXAMPLE 2
```
PS C:\>Uninstall-PswaWebApplication -DeleteTestCertificate
```

This command uninstalls the Windows PowerShell Web Application, and deletes the test certificate associated with the application.
You can use this cmdlet to uninstall the Windows PowerShell Web Application if you installed it using the default values and created a test certificate.

### EXAMPLE 3
```
PS C:\> Uninstall-PswaWebApplication -WebApplicationName TestApplication -WebsiteName MySite -DeleteTestCertificate
```

This command uninstalls the Windows PowerShell Web Application when a custom website and application were specified during the install.
The command removes the website named MySite and the application named TestApplication and specifies that the test certificates associated with the application are also deleted.

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

### -DeleteTestCertificate
Indicates that the test certificates created by the **Install_PswaWebApplication** cmdlet (with the **UseTestCertificate** parameter) is deleted. 
Only the test certificate with the same name as the one created by the **Install-PswaWebApplication** cmdlet is removed.

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
Specifies the name of the web application to uninstall.

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
Specifies the name of the web site where the web application is installed.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Install-PswaWebApplication](./Install-PswaWebApplication.md)


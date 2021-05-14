---
external help file: Microsoft.IdentityServer.Management.Proxy.dll-Help.xml
Module Name: WebApplicationProxy
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/webapplicationproxy/set-webapplicationproxysslcertificate?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WebApplicationProxySslCertificate
---

# Set-WebApplicationProxySslCertificate

## SYNOPSIS
Sets the binding to the AD FS SSL certificate that is installed and configured for the FS proxy component of the Web Application Proxy.

## SYNTAX

```
Set-WebApplicationProxySslCertificate -Thumbprint <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Sets the binding to the AD FS SSL certificate that is installed and configured for the FS proxy component of the Web Application Proxy.

## EXAMPLES

### Example 1
```
PS C:\> Set-WebApplicationProxySslCertificate -Thumbprint FC85DDB0FC58E63D8CB52654F22E4BE7900FE349
```

This example installs the certificate specified by the thumbprint and configures for use by the FS proxy component.

### 1:
```
PS C:\>
```

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

### -Thumbprint
The thumbprint of the x.509 certificate the administrator wishes to set as the AD FS SSL certificate that is installed and configured for the FS proxy component of the Web Application Proxy.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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


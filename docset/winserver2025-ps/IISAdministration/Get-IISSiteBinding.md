---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
Module Name: IISAdministration
online version: https://learn.microsoft.com/powershell/module/iisadministration/get-iissitebinding?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IISSiteBinding
---

# Get-IISSiteBinding

## SYNOPSIS
Gets the bindings on the specified IIS site. This cmdlet has been introduced in version 1.1.0.0 of IISAdministration module.

## SYNTAX

```
Get-IISSiteBinding [-Name] <String> [[-BindingInformation] <String>] [[-Protocol] <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-IISSiteBinding** cmdlet gets information about website bindings and their current status and other key information.

## EXAMPLES

### Example 1: Get Information about an IIS website binding
```
PS C:\> Get-IISSiteBinding "Default Web Site" "*:80:"
```

This command gets the binding information for the "*:80:" binding of the Default Web Site.

### Example 2: Get information about all bindings of an IIS website
```
PS C:\> Get-IISSiteBinding "Default Web Site"

protocol bindingInformation sslFlags
-------- ------------------ --------
http     *:80:                  None
http     *:1234:                None
```

This command gets all configuration information about all bindings of the Default Web Site

## PARAMETERS

### -BindingInformation
Specifies the binding information string to use for the new site. The binding information of the form
IP:Port:hostname such as 192.168.0.1:80:www.contoso.com and one or more of the fields can be left blank, which
is equivalent to using a wildcard character such as \*:443:. In this representation \* indicates all IP
addresses and all hostnames are indicated by leaving the corresponding field blank.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the IIS website.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Protocol
The protocol for which the binding is configured, usually http, https or ftp.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String


## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[New-IISSiteBinding](./New-IISSiteBinding.md)

[Remove-IISSiteBinding](./Remove-IISSiteBinding.md)

[IIS Administration Cmdlets for Windows PowerShell](./iisadministration.md)

---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
Module Name: IISAdministration
online version: https://learn.microsoft.com/powershell/module/iisadministration/remove-iissitebinding?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-IISSiteBinding
---

# Remove-IISSiteBinding

## SYNOPSIS
Removes a binding from an IIS website. This cmdlet has been introduced in version 1.1.0.0 of IISAdministration module.

## SYNTAX

```
Remove-IISSiteBinding [-Name] <String> [-BindingInformation] <String> [[-Protocol] <String>]
 [-RemoveConfigOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Removes a binding from an IIS website.

## EXAMPLES

### Example 1
```
PS C:\> Remove-IISSiteBinding -Name "TestSite" -BindingInformation "*:8080:"
```

This command removes a binding of "*:8080:" from a website named TestSite.

## PARAMETERS

### -BindingInformation
Specifies the binding information string to use for the new site. The binding information of the form
IP:Port:hostname such as 192.168.0.1:80:www.contoso.com and one or more of the fields can be left blank, which
is equivalent to using a wildcard character such as \*:443:. In this representation \*  indicates all IP
addresses and all hostnames are indicated by leaving the corresponding field blank.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### -RemoveConfigOnly
Indicates that this operation does not remove the SSL certificate information and only removes the IIS binding configuration information in the applicationhost.config.

If you want to delete a HTTPS binding configuration that shares a SSL certificate with other existing bindings, only the IIS binding configuration should be removed so that the SSL certificate information remains.
This is to ensure that the other existing bindings will still have access to the certificate.

This parameter is ignored if you are removing a binding which does not have a certificate.


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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

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
Default value: None
Accept pipeline input: False
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

[Get-IISSiteBinding](./Get-IISSiteBinding.md)

[New-IISSiteBinding](./New-IISSiteBinding.md)

[IIS Administration Cmdlets for Windows PowerShell](./iisadministration.md)

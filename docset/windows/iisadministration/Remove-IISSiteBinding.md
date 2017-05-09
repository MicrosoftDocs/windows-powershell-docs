---
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# Remove-IISSiteBinding

## SYNOPSIS
Removes a binding from an IIS Web site.

## SYNTAX

```
Remove-IISSiteBinding [-Name] <String> [-BindingInformation] <String> [[-Protocol] <String>]
 [-RemoveConfigOnly] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Removes a binding from an IIS Web site.

## EXAMPLES

### Example 1
```
PS C:\> Remove-IISSiteBinding -Name "TestSite" -BindingInformation "*:8080:"
```

This command removes a binding of "*:8080:" from a web site named TestSite.

## PARAMETERS

### -BindingInformation
Specifies the binding information string to use for the new site. The binding information of the form 
IP:Port:hostname such as 192.168.0.1:80:www.contoso.com and one or more of the fields can be left blank, which 
is equivalent to using a wildcard character such as *:443:. In this representation *  indicates all IP 
addresses and all hostnames is indicated by leaving the corresponding field blank.

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
Indicates that this operation does not remove the HTTPS certificate binding information and only remove the IIS binding configuration information in the applicationhost.config.

If you want to delete a binding of HTTPS and the HTTPS binding is sharing a certificate with other bindings, you should remove only IIS binding configuration with this parameter. 
Otherwise, the other bindings which were using the same certficate will not work anymore.

This parameter is ignored if you are removing a binding which does not have a certificate binding.


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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-IISSiteBinding](./Get-IISSiteBinding.md)

[New-IISSiteBinding](./New-IISSiteBinding.md)

[IIS Administration Cmdlets for Windows PowerShell](./iisadministration.md)

---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
Module Name: ADFS
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfsproxyconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-ADFSProxyConfiguration

## SYNOPSIS
Sets the configuration properties of the federation server proxy.

## SYNTAX

```
Set-ADFSProxyConfiguration [-HostName <String>] [-HttpPort <Int32>] [-HttpsPort <Int32>] [-LogLevel <String[]>]
 [-ForwardProxyUrl <Uri>] [-ProxyTrustRenewPeriod <Int32>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The Set-ADFSProxyConfiguration cmdlet changes the properties of a federation server proxy that has been previously configured.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\>Set-ADFSProxyProperties -Hostname "fs.fabrikam.com"
```

Sets the properties for the federation server proxy with the name "fs.fabrikam.com".

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

### -ForwardProxyUrl
Specifies the URL of a forward proxy to use for communication to the federation service, if any.
By default, there is no forward proxy configured.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostName
Specifies the network addressable host name of the Federation Service.

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

### -HttpPort
Specifies the HTTP port for the server.
The default value is 80.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HttpsPort
Specifies the HTTPS port for the server.
The default value is 443.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogLevel
Specifies the level of logging detail.
The list defines which types of events are logged.

Possible values are Errors, Warnings, Information, SuccessAudits, and FailureAudits.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 
Accepted values: Errors, FailureAudits, Information, Verbose, None, SuccessAudits, Warnings

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Passes an object to the pipeline.
By default, this cmdlet does not generate any output.

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

### -ProxyTrustRenewPeriod
Sets the interval (in minutes) that the federation server proxy uses to check with its associated federation server for updated trust tokens.

```yaml
Type: Int32
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES
* This cmdlet may be used only on a computer that is configured in Active Directory Federation Services (AD FS) as a federation server proxy. It will not work on a federation server.

## RELATED LINKS

[Get-ADFSProxyConfiguration](./Get-ADFSProxyConfiguration.md)


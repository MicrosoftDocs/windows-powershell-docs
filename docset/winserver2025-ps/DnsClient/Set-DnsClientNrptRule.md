---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsClientNRPTRule_v1.0.0.cdxml-help.xml
Module Name: DnsClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsclient/set-dnsclientnrptrule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DnsClientNrptRule
---

# Set-DnsClientNrptRule

## SYNOPSIS
Modifies a DNS client Name Resolution Policy Table (NRPT) rule for the specified namespace.

## SYNTAX

```
Set-DnsClientNrptRule [-DAEnable <Boolean>] [-DAIPsecEncryptionType <String>] [-DAIPsecRequired <Boolean>]
 [-DANameServers <String[]>] [-DAProxyServerName <String>] [-DAProxyType <String>] [-Comment <String>]
 [-DnsSecEnable <Boolean>] [-DnsSecIPsecEncryptionType <String>] [-DnsSecIPsecRequired <Boolean>]
 [-DnsSecValidationRequired <Boolean>] [-GpoName <String>] [-IPsecTrustAuthority <String>] [-Name] <String>
 [-NameEncoding <String>] [-NameServers <String[]>] [-Namespace <String[]>] [-Server <String>]
 [-DisplayName <String>] [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DnsClientNrptRule** cmdlet modifies the specified DNS client Name Resolution Policy Table (NRPT) rule.

## EXAMPLES

### Example 1: Modify an NRPT rule
```
PS C:\> Set-DnsClientNrptRule  -DAEnable $True -DAIPsecEncryptionType "High" -DAIPsecRequired $True -DANameServers "10.0.0.1" -DAProxyServerName "DaServer.com:6666" -DAProxyType "UseProxyName" -DisplayName "Sample" -PassThru -IPsecTrustAuthority "RootCA" -Name "{1326d9d0-4fb5-4fed-9f67-f53637b85010}" -NameEncoding "Punycode" -NameServers "10.0.0.1" -Namespace "dnsnrpt.com" -Server "host1.com" -Comment "Sample NRPT Rule" -DnsSecEnable $True -DnsSecIPsecEncryptionType "Medium" -DnsSecIPsecRequired $True -DnsSecValidationRequired $True -GpoName "TestGPO"
```

This example modifies an NRPT rule for a GPO named TestGPO on the server named host1.com for namespace dnsnrpt.com.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Comment
Stores administrator comments.

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

### -DAEnable
Indicates the rule state for DirectAccess (DA).

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: DirectAccessEnabled

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DAIPsecEncryptionType
Specifies the IPsec encryption type for DA.
The acceptable values for this parameter are:

- None
- Low
- Medium
- High

```yaml
Type: String
Parameter Sets: (All)
Aliases: DirectAccessQueryIPSSECEncryption
Accepted values: , None, Low, Medium, High

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DAIPsecRequired
Indicates whether IPsec is required.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: DirectAccessQueryIPsecRequired

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DANameServers
Specifies the DNS servers which will be queried when DA is enabled.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: DirectAccessDNSServers

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DAProxyServerName
Specifies the proxy server to be used when connecting to the Internet.

This parameter is only applicable when the *DAProxyType* parameter is set to UseProxyName.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DirectAccessProxyName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DAProxyType
Specifies the proxy server type to be used when connecting to the Internet.
The acceptable values for this parameter are:

- NoProxy
- UseDefault
- UseProxyName

```yaml
Type: String
Parameter Sets: (All)
Aliases: DirectAccessProxyType
Accepted values: , NoProxy, UseDefault, UseProxyName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisplayName
Specifies an optional friendly name for the NRPT rule.

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

### -DnsSecEnable
Indicates whether DNSSEC is enabled on the rule.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: DnsSecEnabled

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DnsSecIPsecEncryptionType
Specifies the IPsec tunnel encryption settings.
The acceptable values for this parameter are:

- None
- Low
- Medium
- High

```yaml
Type: String
Parameter Sets: (All)
Aliases: DnsSecQueryIPsecEncryption
Accepted values: , None, Low, Medium, High

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DnsSecIPsecRequired
Indicates that the DNS client must set up an IPsec connection to the DNS server.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: DnsSecQueryIPsecRequired

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DnsSecValidationRequired
Indicates that DNSSEC validation is required.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GpoName
Specifies the name of the Group Policy Object (GPO).

- If this parameter and the *Server* parameter are specified, then the NRPT rule is added in the GPO of domain.
The *Server* parameter specifies the domain controller (DC).
- If neither this parameter nor the *Server* parameter is specified, then the NRPT rule is added for local client computer.
- If this parameter is specified and the *Server* parameter is not specified, then the DC of the domain specified by this parameter value is found and NRPT rule is added to the GPO.
- If this parameter is not specified and the *Server* parameter is specified, then an error is displayed.

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

### -IPsecTrustAuthority
Specifies the Certification Authority (CA) to validate the IPsec channel for DA.

```yaml
Type: String
Parameter Sets: (All)
Aliases: IPsecCARestriction

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name which uniquely identifies a rule.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NameEncoding
Specifies the encoding format for host names in the DNS query.
The acceptable values for this parameter are:

- Disable
- Utf8WithMapping
- Utf8WithoutMapping
- Punycode

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Disable, Utf8WithMapping, Utf8WithoutMapping, Punycode

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NameServers
Specifies the DNS servers to which the DNS query is sent when DA is disabled.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Namespace
Specifies the DNS namespace.
The acceptable values for this parameter are:

- Suffix
- Prefix
- FQDN
- Subnet
- Any

If this parameter is set to Any, then the parameter value must be specified in dot-notation.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
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

### -Server
Specifies the server hosting the GPO.
This parameter is only applicable with the *GpoName* parameter.

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

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DNS/DnsClientNrptRule
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DNS/DnsClientNrptRule
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The **DnsClientNrptRule** object contains all of the properties of the DNS client NRPT rule.

## NOTES

## RELATED LINKS

[Add-DnsClientNrptRule](./Add-DnsClientNrptRule.md)

[Get-DnsClientNrptGlobal](./Get-DnsClientNrptGlobal.md)

[Get-DnsClientNrptPolicy](./Get-DnsClientNrptPolicy.md)

[Get-DnsClientNrptRule](./Get-DnsClientNrptRule.md)

[Remove-DnsClientNrptRule](./Remove-DnsClientNrptRule.md)

[Set-DnsClientNrptGlobal](./Set-DnsClientNrptGlobal.md)


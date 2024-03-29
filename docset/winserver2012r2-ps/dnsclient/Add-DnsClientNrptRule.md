---
external help file: PS_DnsClientNRPTRule_v1.0.0.cdxml-help.xml
Module Name: DnsClient
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/dnsclient/add-dnsclientnrptrule?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DnsClientNrptRule
---

# Add-DnsClientNrptRule

## SYNOPSIS
Adds a rule to the Name Resolution Policy Table (NRPT).

## SYNTAX

```
Add-DnsClientNrptRule [-GpoName <String>] [-DANameServers <String[]>] [-DAIPsecRequired]
 [-DAIPsecEncryptionType <String>] [-DAProxyServerName <String>] [-DnsSecEnable] [-DnsSecIPsecRequired]
 [-DnsSecIPsecEncryptionType <String>] [-NameServers <String[]>] [-NameEncoding <String>]
 [-Namespace] <String[]> [-Server <String>] [-DAProxyType <String>] [-DnsSecValidationRequired] [-DAEnable]
 [-IPsecTrustAuthority <String>] [-Comment <String>] [-DisplayName <String>] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DnsClientNrptRule** cmdlet adds a Name Resolution Policy Table (NRPT) rule for the specified namespace.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Add-DnsClientNrptRule -GpoName TestGPO -DANameServers 10.0.0.1 -DAIPsecRequired -DAIPsecEncryptionType "High" -DAProxyServerName "DaServer.com:6666" -DnsSecEnable -PassThru -DAProxyType "UseProxyName" -DnsSecValidationRequired -DAEnable -IPsecTrustAuthority "RootCA" -Comment "Sample NRPT Rule" -DisplayName "Sample" -DnsSecIPsecRequired -DnsSecIPsecEncryptionType "Medium" -NameServers 10.0.0.1 -NameEncoding "Punycode" -Namespace "dnsnrpt.com" -Server host1.com
```

This example adds an NRPT rule in TestGPO on server host1.com for the namespace dnsnrpt.com.

### EXAMPLE 2
```
PS C:\>Add-DnsClientNrptRule -Namespace pqr.com -NameServers 10.0.0.1
```

This example adds an NRPT rule that configures the server named 10.0.0.1 as a DNS server for the namespace pqr.com.

### EXAMPLE 3
```
PS C:\>Add-DnsClientNrptRule -Namespace pqr.com -DnsSecEnable
```

This example adds an NRPT rule that enables DNSSEC queries to be sent for the namespace pqr.com.

### EXAMPLE 4
```
PS C:\>Add-DnsClientNrptRule -Namespace pqr.com -DnsSecEnable -NameServers 10.0.0.1
```

This example adds an NRPT rule that enables DNSSEC queries to be sent to DNS server named 10.0.0.1 for the namespace pqr.com.

### EXAMPLE 5
```
PS C:\>Add-DnsClientNrptRule -Namespace pqr.com -NameEncoding Punycode -NameServers 10.1.1.1 -PassThru
Name                             : {6a78d8d1-231d-4d1e-bc23-fb593e11a53d} 
Version                          : 2 
Namespace                        : {pqr.com} 
IPsecCARestriction               : 
DirectAccessDnsServers           : 
DirectAccessEnabled              : False 
DirectAccessProxyType            : 
DirectAccessProxyName            : 
DirectAccessQueryIPsecEncryption : 
DirectAccessQueryIPsecRequired   : 
NameServers                      : 10.1.1.1 
DnsSecEnabled                    : False 
DnsSecQueryIPsecEncryption       : 
DnsSecQueryIPsecRequired         : 
DnsSecValidationRequired         : 
NameEncoding                     : Punycode 
DisplayName                      : 
Comment                          :
```

This example adds an NRPT rule that sends DNS queries encoded in Punycode to DNS server named 10.1.1.1 for the namespace pqr.com.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
Stores administrator notes.

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
Specifies the rule state for DirectAccess (DA).

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: DirectAccessEnabled

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DAIPsecEncryptionType
Specifies the IPsec encryption setting for DA. 
The acceptable values for this parameter are: None, Low, Medium, or High.

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
Specifies that IPsec is required for DA.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: DirectAccessQueryIPsecRequired

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DANameServers
Specifies the DNS servers that will be queried when DA is enabled.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: DirectAccessDnsServers

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DAProxyServerName
Specifies the proxy server to be used when connecting to the Internet. 

This parameter is only applicable the **DAProxyType** parameter is set to UseProxyName. 

The allowed formats for this parameter are: hostname:port, IPv4 address:port, or IPv6 address:port.

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
The acceptable values for this parameter are: NoProxy, UseDefault, or UseProxyName.

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
Specifies that DNSSEC is enabled on the rule.

```yaml
Type: SwitchParameter
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
Specifies that the DNS client must set up an IPsec connection to the DNS server.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: DnsSecQueryIPsecRequired

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DnsSecValidationRequired
Specifies that DNSSEC validation is required.

```yaml
Type: SwitchParameter
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

 -- If this parameter and the **Server** parameter are specified, then the NRPT rule is added in the GPO of domain.
The **Server** parameter specifies the domain controller (DC). 

 -- If neither this parameter nor the **Server** parameter is specified, then the NRPT rule is added for local client computer. 

 -- If this parameter is specified and the **Server** parameter is not specified, then the DC of the domain specified by this parameter value is found and NRPT rule is added to the GPO. 

 -- If this parameter is not specified and the **Server** parameter is specified, then an error is displayed.

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
Specifies the certification authority to validate the IPsec channel.

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

### -NameEncoding
Specifies the encoding format for host names in the DNS query. 
The acceptable values for this parameter are: Disable, Utf8WithMapping, Utf8WithoutMapping, or Punycode.

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

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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
This parameter is only applicable with the **GpoName** parameter.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DNS/DnsClientNrptRule
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DNS/DnsClientNrptRule
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The DnsClientNrptRule object contains all of the properties of the DNS client NRPT rule.

## NOTES

## RELATED LINKS

[Get-DnsClientNrptGlobal](./Get-DnsClientNrptGlobal.md)

[Get-DnsClientNrptPolicy](./Get-DnsClientNrptPolicy.md)

[Get-DnsClientNrptRule](./Get-DnsClientNrptRule.md)

[Remove-DnsClientNrptRule](./Remove-DnsClientNrptRule.md)

[Set-DnsClientNrptGlobal](./Set-DnsClientNrptGlobal.md)

[Set-DnsClientNrptRule](./Set-DnsClientNrptRule.md)


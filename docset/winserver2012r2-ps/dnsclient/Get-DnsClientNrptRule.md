---
external help file: PS_DnsClientNRPTRule_v1.0.0.cdxml-help.xml
Module Name: DnsClient
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/dnsclient/get-dnsclientnrptrule?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DnsClientNrptRule
---

# Get-DnsClientNrptRule

## SYNOPSIS
Retrieves the DNS client Name Resolution Policy Table (NRPT) rules.

## SYNTAX

```
Get-DnsClientNrptRule [-GpoName <String>] [[-Name] <String[]>] [-Server <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DnsClientNrptRule** cmdlet retrieves DNS client Name Resolution Policy Table (NRPT) rules with the following details: 
                       
 -- DNS client name setting. 
                       
 -- DNS client version setting. 
                       
 -- DNS client namespace setting. 
                       
 -- DNS client IPsec Certification Authority (CA) restriction setting. 
                       
 -- Direct Access (DA) DNS servers setting. 
                       
 -- DA enabled setting. 
                       
 -- DA proxy type setting. 
                       
 -- DA proxy name setting. 
                       
 -- DA query IPsec encryption setting. 
                       
 -- DA query IPsec required setting. 
                       
 -- DNS client name servers setting. 
                       
 -- DNS security enabled setting. 
                       
 -- DNS security query IPsec encryption setting. 
                       
 -- DNS security query IPsec required setting. 
                       
 -- DNS security validation required setting. 
                       
 -- DNS client name encoding setting. 
                       
 -- DNS client display name setting. 
                       
 -- DNS client comment setting.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DnsClientNrptRule -GpoName "corp.contoso.com\DirectAccess Client Settings"
Name                             : DA-{FD4B6054-F8C8-4868-94E6-8132AC707DBD} 
Version                          : 1 
Namespace                        : {.corp.contoso.com} 
IPsecCARestriction               : 
DirectAccessDnsServers           : {2001:db8:1::2, 2001:db8:2::20, 2001:db8:6::6} 
DirectAccessEnabled              : True 
DirectAccessProxyType            : NoProxy 
DirectAccessProxyName            : 
DirectAccessQueryIPsecEncryption : 
DirectAccessQueryIPsecRequired   : False 
NameServers                      : 
DnsSecEnabled                    : False 
DnsSecQueryIPsecEncryption       : 
DnsSecQueryIPsecRequired         : 
DnsSecValidationRequired         : 
NameEncoding                     : Disable 
DisplayName                      : 
Comment                          : 
 
Name                             : DA-{274D94E4-E38B-4997-BA9F-84700712C09E} 
Version                          : 1 
Namespace                        : {nls.corp.contoso.com} 
IPsecCARestriction               : 
DirectAccessDnsServers           : 
DirectAccessEnabled              : True 
DirectAccessProxyType            : UseDefault 
DirectAccessProxyName            : 
DirectAccessQueryIPsecEncryption : 
DirectAccessQueryIPsecRequired   : False 
NameServers                      : 
DnsSecEnabled                    : False 
DnsSecQueryIPsecEncryption       : 
DnsSecQueryIPsecRequired         : 
DnsSecValidationRequired         : 
NameEncoding                     : Disable 
DisplayName                      : 
Comment                          :
```

This example retrieves an NRPT rules for the specified GPO.

### EXAMPLE 2
```
PS C:\>Get-DnsClientNrptRule -GpoName "corp.contoso.com\DirectAccess Client Settings" -Server dc1
Name                             : DA-{FD4B6054-F8C8-4868-94E6-8132AC707DBD} 
Version                          : 1 
Namespace                        : {.corp.contoso.com} 
IPsecCARestriction               : 
DirectAccessDnsServers           : {2001:db8:1::2, 2001:db8:2::20, 2001:db8:6::6} 
DirectAccessEnabled              : True 
DirectAccessProxyType            : NoProxy 
DirectAccessProxyName            : 
DirectAccessQueryIPsecEncryption : 
DirectAccessQueryIPsecRequired   : False 
NameServers                      : 
DnsSecEnabled                    : False 
DnsSecQueryIPsecEncryption       : 
DnsSecQueryIPsecRequired         : 
DnsSecValidationRequired         : 
NameEncoding                     : Disable 
DisplayName                      : 
Comment                          : 
 
Name                             : DA-{274D94E4-E38B-4997-BA9F-84700712C09E} 
Version                          : 1 
Namespace                        : {nls.corp.contoso.com} 
IPsecCARestriction               : 
DirectAccessDnsServers           : 
DirectAccessEnabled              : True 
DirectAccessProxyType            : UseDefault 
DirectAccessProxyName            : 
DirectAccessQueryIPsecEncryption : 
DirectAccessQueryIPsecRequired   : False 
NameServers                      : 
DnsSecEnabled                    : False 
DnsSecQueryIPsecEncryption       : 
DnsSecQueryIPsecRequired         : 
DnsSecValidationRequired         : 
NameEncoding                     : Disable 
DisplayName                      : 
Comment                          :
```

This example retrieves an NRPT rule for the specified GPO on the specified server.

### EXAMPLE 3
```
PS C:\>Get-DnsClientNrptRule -GpoName "corp.contoso.com\DirectAccess Client Settings" -CimSession 2-dc1.corp2.corp.contoso.com
```

This example retrieves the NRPT rules on the remote computer named 2-dc1.corp2.corp.contoso.com.

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

### -Name
Specifies the name which uniquely identifies a rule.
If this parameter is not specified, then all of the available NRPT rules are retrieved.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DNS/DnsClientNrptRule[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DNS/DnsClientNrptRule[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
                         
The DnsClientNrptRule object contains all of the properties of the DNS client NRPT rule.

## NOTES

## RELATED LINKS

[Add-DnsClientNrptRule](./Add-DnsClientNrptRule.md)

[Get-DnsClientNrptGlobal](./Get-DnsClientNrptGlobal.md)

[Get-DnsClientNrptPolicy](./Get-DnsClientNrptPolicy.md)

[Remove-DnsClientNrptRule](./Remove-DnsClientNrptRule.md)

[Set-DnsClientNrptGlobal](./Set-DnsClientNrptGlobal.md)

[Set-DnsClientNrptRule](./Set-DnsClientNrptRule.md)


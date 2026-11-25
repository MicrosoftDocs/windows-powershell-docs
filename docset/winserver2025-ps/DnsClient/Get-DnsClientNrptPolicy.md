---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsClientNrptPolicy_v1.0.0.cdxml-help.xml
Module Name: DnsClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsclient/get-dnsclientnrptpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DnsClientNrptPolicy
---

# Get-DnsClientNrptPolicy

## SYNOPSIS
Gets the NRPT configured on a computer.

## SYNTAX

```
Get-DnsClientNrptPolicy [-Effective] [[-Namespace] <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DnsClientNrptPolicy** cmdlet gets the following Name Resolution Policy Table (NRPT) details for each namespace.

- DNS client name resolution fallback policy.
- DNS client secure name query fallback setting.
- Direct Access (DA) IPsec Certification Authority (CA) restriction setting.
- DA proxy name setting.
- DA DNS servers setting.
- DA enabled setting.
- DA proxy type setting.
- DA Query IPsec encryption setting.
- DA Query IPsec required setting.
- DNS client name servers setting.
- DNS security IPsec CA restriction setting.
- DNS security query IPsec encryption setting.
- DNS security query IPsec required setting.
- DNS security validation required setting.
- DNS client name encoding setting.

## EXAMPLES

### Example 1: Get the NRPT policy
```
PS C:\> Get-DnsClientNrptPolicy

Namespace                        : nls.corp.contoso.com
QueryPolicy                      :
SecureNameQueryFallback          :
DirectAccessIPsecCARestriction   :
DirectAccessProxyName            :
DirectAccessDnsServers           :
DirectAccessEnabled              :
DirectAccessProxyType            : UseDefault
DirectAccessQueryIPsecEncryption :
DirectAccessQueryIPsecRequired   : False
NameServers                      :
DnsSecIPsecCARestriction         :
DnsSecQueryIPsecEncryption       :
DnsSecQueryIPsecRequired         : False
DnsSecValidationRequired         : False
NameEncoding                     : Utf8WithoutMapping

Namespace                        : .corp.contoso.com
QueryPolicy                      :
SecureNameQueryFallback          :
DirectAccessIPsecCARestriction   :
DirectAccessProxyName            :
DirectAccessDnsServers           : {2001:db8:1::2, 2001:db8:2::20,
                                   2001:db8:6::6}
DirectAccessEnabled              :
DirectAccessProxyType            : NoProxy
DirectAccessQueryIPsecEncryption :
DirectAccessQueryIPsecRequired   : False
NameServers                      :
DnsSecIPsecCARestriction         :
DnsSecQueryIPsecEncryption       :
DnsSecQueryIPsecRequired         : False
DnsSecValidationRequired         : False
NameEncoding                     : Utf8WithoutMapping
```

This example gets the NRPT policy on a computer.

### Example 2: Get the effective NRPT policy
```
PS C:\> Get-DnsClientNrptPolicy -Effective

Namespace                        : nls.corp.contoso.com
QueryPolicy                      : QueryIPv6Only
SecureNameQueryFallback          : FallbackPrivate
DirectAccessIPsecCARestriction   :
DirectAccessProxyName            :
DirectAccessDnsServers           :
DirectAccessEnabled              : True
DirectAccessProxyType            : UseDefault
DirectAccessQueryIPsecEncryption :
DirectAccessQueryIPsecRequired   : False
NameServers                      :
DnsSecIPsecCARestriction         :
DnsSecQueryIPsecEncryption       :
DnsSecQueryIPsecRequired         :
DnsSecValidationRequired         :
NameEncoding                     :

Namespace                        : .corp.contoso.com
QueryPolicy                      : QueryIPv6Only
SecureNameQueryFallback          : FallbackPrivate
DirectAccessIPsecCARestriction   :
DirectAccessProxyName            :
DirectAccessDnsServers           : {2001:db8:1::2, 2001:db8:2::20,
                                   2001:db8:6::6}
DirectAccessEnabled              : True
DirectAccessProxyType            : NoProxy
DirectAccessQueryIPsecEncryption :
DirectAccessQueryIPsecRequired   : False
NameServers                      :
DnsSecIPsecCARestriction         :
DnsSecQueryIPsecEncryption       :
DnsSecQueryIPsecRequired         :
DnsSecValidationRequired         :
NameEncoding                     :
```

This example gets the effective NRPT policy on a computer.

### Example 3: Get the effective NRPT policy for a specified namespace
```
PS C:\> Get-DnsClientNrptPolicy -Effective -Namespace "nls.corp.contoso.com"

Namespace                        : nls.corp.contoso.com
QueryPolicy                      : QueryIPv6Only
SecureNameQueryFallback          : FallbackPrivate
DirectAccessIPsecCARestriction   :
DirectAccessProxyName            :
DirectAccessDnsServers           :
DirectAccessEnabled              : True
DirectAccessProxyType            : UseDefault
DirectAccessQueryIPsecEncryption :
DirectAccessQueryIPsecRequired   : False
NameServers                      :
DnsSecIPsecCARestriction         :
DnsSecQueryIPsecEncryption       :
DnsSecQueryIPsecRequired         :
DnsSecValidationRequired         :
NameEncoding                     :
```

This example gets an effective NRPT policy for the namespace nls.corp.contoso.com.

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

### -Effective
Indicates that the effective NRPT policy is returned.

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

### -Namespace
Specifies the DNS namespace for which the policy is retrieved.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DNS/DnsClientPolicyConfiguration[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The **DnsClientPolicyConfiguration** object contains all of the properties of the DNS client NRPT policy.
If the *Effective* parameter is specified, then only the contents of effective policy are retrieved.

## NOTES

## RELATED LINKS

[Add-DnsClientNrptRule](./Add-DnsClientNrptRule.md)

[Get-DnsClientNrptGlobal](./Get-DnsClientNrptGlobal.md)

[Get-DnsClientNrptPolicy](./Get-DnsClientNrptPolicy.md)

[Get-DnsClientNrptRule](./Get-DnsClientNrptRule.md)

[Remove-DnsClientNrptRule](./Remove-DnsClientNrptRule.md)

[Set-DnsClientNrptGlobal](./Set-DnsClientNrptGlobal.md)

[Set-DnsClientNrptRule](./Set-DnsClientNrptRule.md)


---
external help file: DnsServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 8581EE53-E8DD-4A77-8268-656868EB36B3
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Clear-DnsServerCache

## SYNOPSIS
Clears resource records from a cache on the DNS server.

## SYNTAX

```
Clear-DnsServerCache [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-Force]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Clear-DnsServerCache** cmdlet clears resource records from a Domain Name System (DNS) server cache.

## EXAMPLES

### Example 1:
```
PS C:\> Clear-DnsServerCache -ComputerName "Win12S-05.DNSServer-01.Contoso.com" -Force
```

This command clears the DNS server cache on a specified DNS server.
If you do not use the Force parameter, you must confirm the action before it is performed.

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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies a DNS server.
The acceptable values for this parameter are: an IP V4 address; an IP V6 address; any other value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

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

### -Force
If specified, overrides the default confirmation before the operation is performed.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-DnsServerCache](./Get-DnsServerCache.md)

[Set-DnsServerCache](./Set-DnsServerCache.md)

[Show-DnsServerCache](./Show-DnsServerCache.md)


---
external help file: DnsServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: EA5012C8-2C10-4E44-BD05-122954970183
manager: dansimp
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Set-DnsServerEDns

## SYNOPSIS
Changes EDNS settings on a DNS server.

## SYNTAX

```
Set-DnsServerEDns [-AsJob] [-CacheTimeout <TimeSpan>] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-EnableProbes <Boolean>] [-EnableReception <Boolean>] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Set-DnsServerEDns** cmdlet changes extension mechanisms for DNS (EDNS) settings on a Domain Name System (DNS) server.

## EXAMPLES

### Example 1: Change the EDNS cache setting
```
PS C:\> Set-DnsServerEDns -CacheTimeout 00:30:00 -PassThru
```

This command changes the EDNS cache setting on a local DNS server.
This command specifies that the DNS server caches EDNS information for 30 minutes.

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

### -CacheTimeout
Specifies the number of seconds that the DNS server caches EDNS information.
The default value is 604,800 seconds (one week).

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Specifies a remote DNS server.
You can specify an IP address or any value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

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

### -EnableProbes
Disables or enables the server to probe other servers to determine whether they support EDNS.
The acceptable values for this parameter are:

- 0: Disables active support for EDNS probes. 
- 1: Enables active support for EDNS probes.

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

### -EnableReception
Specifies whether the DNS server accepts queries that contain an EDNS record.
The acceptable values for this parameter are:

- 0: Disables EDNS reception.
- 1: Enables EDNS reception.

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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerEDns

## NOTES

## RELATED LINKS

[Get-DnsServerEDns](./Get-DnsServerEDns.md)


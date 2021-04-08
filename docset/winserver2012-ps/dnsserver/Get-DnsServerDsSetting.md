---
author: Kateyanne
external help file: DnsServer_Cmdlets.xml
manager: dansimp
Module Name: DnsServer
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/dnsserver/get-dnsserverdssetting?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-DnsServerDsSetting

## SYNOPSIS
Retrieves DNS Server Active Directory settings

## SYNTAX

```
Get-DnsServerDsSetting [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DnsServerDsSetting** cmdlet retrieves the following Domain Name System (DNS) Server Active Directory settings: PollingInterval, DirectoryPartitionAutoEnlistInterval, LazyUpdateInterval, MinimumBackgroundLoadThreads, and RemoteReplicationDelay.

## EXAMPLES

### Example 1: Get Active Directory service settings
```
PS C:\> Get-DnsServerDsSetting
PollingInterval(s)                   : 180

TombstoneInterval                    : 14.00:00:00

DirectoryPartitionAutoEnlistInterval : 1.00:00:00

LazyUpdateInterval(s)                : 3

MinimumBackgroundLoadThreads         : 1

RemoteReplicationDelay(s)            : 30
```

This command gets the Active Directory service settings of a DNS server.

PS C:\Users\Administrator\>

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

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerDsSetting

## NOTES

## RELATED LINKS

[Set-DnsServerDsSetting](./Set-DnsServerDsSetting.md)


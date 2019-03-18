---
external help file: DnsServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: B491D354-EAD2-402F-B762-0136B615C9FB
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Set-DnsServerSetting

## SYNOPSIS
Modifies DNS server settings.

## SYNTAX

```
Set-DnsServerSetting [[-InputObject] <CimInstance>] [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-DnsServerSetting** cmdlet modifies Domain Name System (DNS) server settings.

## EXAMPLES

### Example 1: Copy DNS server settings from one DNS server to another
```
PS C:\>Get-DnsServerSetting -ComputerName "172.23.90.136" -All | Set-DnsServerSetting
```

This command copies DNS server settings from the DNS server that has an IP address of 172.23.90.136 to the local DNS server.

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
Valid values are an IPv4 address; an IPv6 address; and any other value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
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

### 
"Class: DNSServerSettings {

string  Name; //Specifies the FQDN or IP address of a DNS server.
This specification should be common across roles.

uint32  Version;  //Specifies the read-only version of the DNS server.

sint32  RpcProtocol; //Specifies the remote procedure call (RPC) protocol or protocols over which administrative RPC runs.

uint32 NameCheckFlag; //Specifies the set of eligible characters to use in DNS server names.

uint32  AddressAnswerLimit; //Specifies the maximum number of host records that are returned in response to an address request.
Values of 5 through 28 are valid.

uint32  BootMethod; //Specifies the initialization method for a DNS server. 

boolean DsAvailable; //Indicates whether an available directory service is on the DNS server.

boolean DisableAutoReverseZones; //Indicates whether the DNS server automatically creates standard reverse lookup zones.

boolean RoundRobin; //Indicates whether the DNS server uses the round robin mechanism to rotate the order of multiple address (A) records.

boolean LooseWildcarding ;//Indicates whether the DNS server uses loose wildcards.
If undefined or zero, the server follows the wildcard behavior that is specified in the DNS RFC.
In this case, an administrator should include mail exchanger (MX) records for all hosts that cannot receive mail.
If nonzero, the server seeks the closest wildcard node and an administrator should put MX records at the zone root and in a wildcard node (*) directly below the zone root.
Administrators should also put self-referencing MX records on hosts that receive their own mail.

boolean WriteAuthorityNS; //Indicates whether the DNS server writes name server (NS) and start of authority (SOA) records to the authority section on successful response.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerSetting

## NOTES

## RELATED LINKS

[Get-DnsServerSetting](./Get-DnsServerSetting.md)


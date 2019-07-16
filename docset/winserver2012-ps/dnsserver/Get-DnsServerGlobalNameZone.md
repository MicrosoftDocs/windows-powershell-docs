---
external help file: DnsServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 674E481E-00CA-4895-98A0-33FBECB36688
manager: dansimp
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Get-DnsServerGlobalNameZone

## SYNOPSIS
Retrieves DNS server GlobalName zone configuration details.

## SYNTAX

```
Get-DnsServerGlobalNameZone [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DnsServerGlobalNameZone** cmdlet gets a Domain Name System (DNS) server GlobalNames zone object for the local server or a specified DNS server.
This object contains the following settings: 

- Enable
- GlobalOverLocal
- PreferAAAA
- AlwaysQueryServer
- EnableEDnsProbes
- BlockUpdates
- SendTimeout(s)
- ServerQueryInterval

## EXAMPLES

### Example 1: Get GlobalName zone settings
```
PS C:\> Get-DnsServerGlobalNameZone
```

This command gets DNS server GlobalName zone settings.

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
If you do not specify this parameter, the command runs on the local system.
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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerGlobalNameZone

## NOTES

## RELATED LINKS

[00000000-0000-0000-0000-000000000000](00000000-0000-0000-0000-000000000000)


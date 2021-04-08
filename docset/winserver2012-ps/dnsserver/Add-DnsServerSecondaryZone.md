---
author: Kateyanne
external help file: DnsServer_Cmdlets.xml
manager: dansimp
Module Name: DnsServer
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/dnsserver/add-dnsserversecondaryzone?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-DnsServerSecondaryZone

## SYNOPSIS
Adds a DNS server secondary zone.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Add-DnsServerSecondaryZone [-Name] <String> [-ZoneFile] <String> [-MasterServers] <IPAddress[]> [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-LoadExisting] [-PassThru] [-ThrottleLimit <Int32>]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Add-DnsServerSecondaryZone [-ZoneFile] <String> [-MasterServers] <IPAddress[]> [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-LoadExisting] [-PassThru] [-ThrottleLimit <Int32>]
 -NetworkId <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-DnsServerSecondaryZone** cmdlet adds a specified secondary zone on a Domain Name System (DNS) server.
You can create either a forward lookup zone or a reverse lookup zone.
To create a reverse lookup zone, specify a network ID by using the **NetworkID** parameter, or specify a full reverse lookup zone name by using the **Name** parameter.

## EXAMPLES

### Example 1: Add a secondary DNS server zone
```
PS C:\> Add-DnsServerSecondaryZone -Name "western.contoso.com" -ZoneFile "western.contoso.com.dns" -MasterServers 172.23.90.124
```

This command creates a secondary DNS zone named western.contoso.com with the specified master server.
This zone is file-backed.

### Example 2: Create secondary zones
```
PS C:\>Get-DnsServerZone -ComputerName win-olpn33s5q3m.mytest.contoso.com | where {("Primary" -eq $_.ZoneType) -and ($false -eq $_.IsAutoCreated) -and ("TrustAnchors" -ne $_.ZoneName)} | %{ $_ | Add-DnsServerSecondaryZone -MasterServers 172.23.90.136  -ZoneFile "$($_.ZoneName).dns"}
```

This example gets primary zones from the server win-olpn33s5q3m.mytest.contoso.com and creates secondary zones (except TrustAnchors and AutoCreated zones) on the local system.

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

### -LoadExisting
Loads an existing file for the zone.
Otherwise, the cmdlet creates default zone records automatically.
This switch is relevant only for file-backed zones.

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

### -MasterServers
Specifies an array of IP addresses of the master servers of the zone.
You can use both IPv4 and IPv6.

```yaml
Type: IPAddress[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name of a zone.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkId
Specifies the network ID and prefix for the secondary zone.
Enter an IP address with prefix length in this format: 11.1.1/24 or 1234::/64.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
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

### -ZoneFile
Specifies the name of the zone file.
This parameter is only relevant for file-backed zones.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerSecondaryZone

## NOTES

## RELATED LINKS

[ConvertTo-DnsServerSecondaryZone](./ConvertTo-DnsServerSecondaryZone.md)

[Restore-DnsServerSecondaryZone](./Restore-DnsServerSecondaryZone.md)

[Set-DnsServerSecondaryZone](./Set-DnsServerSecondaryZone.md)


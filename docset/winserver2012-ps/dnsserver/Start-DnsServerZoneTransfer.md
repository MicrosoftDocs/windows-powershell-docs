---
external help file: DnsServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: C63BA3B9-2BBB-43C8-90A5-7C95CE0DB67A
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Start-DnsServerZoneTransfer

## SYNOPSIS
Starts a zone transfer for a secondary DNS zone from master servers.

## SYNTAX

```
Start-DnsServerZoneTransfer [-Name] <String> [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-FullTransfer] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Start-DnsServerZoneTransfer** cmdlet starts a zone transfer of a secondary zone from the master servers. 
You can do a full transfer, where the secondary Domain Name System (DNS) server gets a copy of all the resource records for the zone.
You can also do an incremental transfer, where the secondary DNS server gets new and changed resource records.

A zone transfer forces a check of the version number in the master server Start of Authority (SOA) record.
If the version number on the master server is higher than the secondary server version number, then a zone transfer begins that updates the secondary server.
If the version number is the same, no zone transfer begins.

## EXAMPLES

### Example 1: Start a zone transfer
```
PS C:\> Start-DnsServerZoneTransfer -Name "contoso.com"
```

This command starts a zone transfer on the local DNS server for the secondary zone named contoso.com.
The command does not use the **FullTransfer** parameter, so it performs an incremental transfer.

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
You can specify an IP address or any value that resolves to an IP address, such as a fully qualified domain name (FQDN), Hostname, or NETBIOS name.

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

### -FullTransfer
Performs a full transfer.
Without this parameter, the cmdlet does an incremental transfer.

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

### -Name
Specifies the name of a zone.
The cmdlet transfers records for this zone.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerZone

## NOTES

## RELATED LINKS




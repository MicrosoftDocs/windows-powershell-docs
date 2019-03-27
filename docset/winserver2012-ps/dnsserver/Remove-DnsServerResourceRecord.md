---
external help file: DnsServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 544BB23C-3448-41ED-B098-823B74D0FFF7
manager: dansimp
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Remove-DnsServerResourceRecord

## SYNOPSIS
Removes specified DNS server resource records from a zone.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-DnsServerResourceRecord [-ZoneName] <String> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-Force] [-PassThru] [-ThrottleLimit <Int32>] -InputObject <CimInstance> [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-DnsServerResourceRecord [-ZoneName] <String> [-Name] <String> [-RRType] <String> [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-Force] [-PassThru] [-RecordData <String[]>]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-DnsServerResourceRecord** removes resource record objects from a DNS zone.

You can either use the **Get-DnsServerResourceRecord** cmdlet to specify an object, or you can specify the **RRtype**, **Name** and **RecordData** of the resource record you want to remove.
If you specify an **RRtype** or name and there are multiple resource records, you can specify the **RecordData** to delete a specific record.
If you do not specify **RecordData**, the cmdlet deletes all records that match **RRtype** and **Name** for the specified zone.

## EXAMPLES

### Example 1: Remove all root hints
```
PS C:\>Get-DnsServerResourceRecord -ZoneName "..roothints" | Remove-DnsServerResourceRecord -Force -ZoneName "..roothints"
```

This command removes all root hints for a DNS server.

### Example 2: Remove multiple A records
```
PS C:\>Remove-DnsServerResourceRecord -ZoneName "contoso.com" -RRType "A" -Name "Host01"
Confirm

Removing DNS resource record Host01 of type A from zone contoso.com on ROOT server. Do you want to continue?

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): n
```

This command removes all A resource records in the contoso.com zone that have the name Host01.

### Example 3: Remove a named A record
```
PS C:\>Remove-DnsServerResourceRecord -ZoneName "contoso.com" -RRType "A" -Name "Host01" -RecordData "10.17.1.41"
```

This command removes the A resource record from a zone named contoso.com that has the name Host01 and the IP address 10.17.1.41.

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

### -Force
Removes a record or records without prompting you for confirmation.
By default, the cmdlet prompts you for confirmation before it proceeds.

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of a DNS server resource record object.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 3
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

### -RecordData
Specifies the data contained in the resource record you want to delete.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RRType
Specifies the type of resource record.

The acceptable values for this parameter are:
- HInfo 
- Afsdb 
- Atma 
- Isdn 
- Key 
- Mb 
- Md 
- Mf 
- Mg 
- MInfo 
- Mr 
- Mx 
- NsNxt 
- Rp 
- Rt 
- Wks 
- X25 
- A 
- AAAA 
- CName 
- Ptr 
- Srv 
- Txt 
- Wins 
- WinsR 
- Ns 
- Soa 
- NasP 
- NasPtr 
- DName 
- Gpos 
- Loc 
- DhcId 
- Naptr 
- RRSig 
- DnsKey 
- DS 
- NSec 
- NSec3 
- NSec3Param

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 4
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

### -ZoneName
Specifies the name of a DNS zone.

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

### Microsoft.Management.Infrastructure.CimInstance# DnsServerResourceRecord[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerResourceRecord[]

## NOTES

## RELATED LINKS

[Get-DnsServerResourceRecord](./Get-DnsServerResourceRecord.md)

[Set-DnsServerResourceRecord](./Set-DnsServerResourceRecord.md)

[Add-DnsServerResourceRecord](./Add-DnsServerResourceRecord.md)


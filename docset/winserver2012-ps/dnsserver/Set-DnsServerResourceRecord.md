---
external help file: DnsServer_Cmdlets.xml
Module Name: DnsServer
online version: https://docs.microsoft.com/powershell/module/dnsserver/set-dnsserverresourcerecord?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-DnsServerResourceRecord

## SYNOPSIS
Changes a resource record in a DNS zone.

## SYNTAX

```
Set-DnsServerResourceRecord [-ZoneName] <String> [-OldInputObject] <CimInstance>
 [-NewInputObject] <CimInstance> [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-PassThru]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-DnsServerResourceRecord** cmdlet changes a resource record object located in a Domain Name System (DNS) zone.
You can use the **OldInputObject** parameter to specify a resource record object that you want to change and **NewInputObject** to specify a new resource record.
This cmdlet cannot change the Name or Type of a DNS server resource record object.

## EXAMPLES

### Example 1: Change the settings of a resource record
```
PS C:\> $NewObj = $OldObj = Get-DnsServerResourceRecord -Name "Host01" -ZoneName "contoso.com" -RRType "A"

PS C:\> $NewObj.TimeToLive = [System.TimeSpan]::FromHours(2)

PS C:\> Set-DnsServerResourceRecord -NewInputObject $NewObj -OldInputObject $OldObj -ZoneName "contoso.com" -PassThru
HostName                  RecordType Timestamp            TimeToLive      RecordData

--------                  ---------- ---------            ----------      ----------

Host01                       A          0                    02:00:00        2.2.2.2
```

In this example, the time to live (TTL) value of the resource record named Host01 in the zone named contoso.com is changed to 2 hours.

The first command assigns a resource record named Host01 in the zone named contoso.com to the variables $NewObj and $OldObj.

The second command sets the TTL time span for $NewObj to 2 hours.

The third command changes the properties of $OldObj to the settings specified for $NewObj in the previous command.

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

### -NewInputObject
Specifies a DNS server resource record object to overwrite the **OldInputObject** parameter value.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OldInputObject
Specifies a DNS server resource record object.

```yaml
Type: CimInstance
Parameter Sets: (All)
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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerResourceRecord

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerResourceRecord

## NOTES

## RELATED LINKS

[Get-DnsServerResourceRecord](./Get-DnsServerResourceRecord.md)

[Add-DnsServerResourceRecord](./Add-DnsServerResourceRecord.md)

[Remove-DnsServerResourceRecord](./Remove-DnsServerResourceRecord.md)


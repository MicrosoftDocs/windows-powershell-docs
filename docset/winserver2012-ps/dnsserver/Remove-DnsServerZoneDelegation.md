---
external help file: DnsServer_Cmdlets.xml
Module Name: DnsServer
online version: https://learn.microsoft.com/powershell/module/dnsserver/remove-dnsserverzonedelegation?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-DnsServerZoneDelegation

## SYNOPSIS
Removes a name server or delegation from a DNS zone.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-DnsServerZoneDelegation [-InputObject] <CimInstance> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-Force] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-DnsServerZoneDelegation [-Name] <String> [-ChildZoneName] <String> [[-NameServer] <String>] [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-Force] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Remove-DnsServerZoneDelegation** cmdlet removes a name server or delegation from a Domain Name System (DNS) zone.

If you specify a DNS server for the child in this cmdlet, the cmdlet removes that server from the delegation.
If you remove the last DNS server, or if you do not specify a DNS server, the cmdlet removes the delegation from the zone, after confirmation.

## EXAMPLES

### Example 1: Remove a delegation
```
PS C:\> Remove-DnsServerZoneDelegation -Name "contoso.com" -ChildZoneName "west05" -PassThru -Verbose
```

This command removes delegation west05 from the domain contoso.com.

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

### -ChildZoneName
Specifies the name of a child zone.
The cmdlet removes the delegation for this zone.

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
Removes the name server or delegation without prompting you for confirmation.
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
This is a Microsoft.Management.Infrastructure.CimInstance#DnsServerZoneDelegation object.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the parent zone.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NameServer
Specifies the name of the DNS server for the child zone.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 4
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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerZoneDelegation

## NOTES

## RELATED LINKS



[Add-DnsServerZoneDelegation](./Add-DnsServerZoneDelegation.md)

[Get-DnsServerZoneDelegation](./Get-DnsServerZoneDelegation.md)

[Set-DnsServerZoneDelegation](./Set-DnsServerZoneDelegation.md)


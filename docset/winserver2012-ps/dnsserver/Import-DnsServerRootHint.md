---
external help file: DnsServer_Cmdlets.xml
Module Name: DnsServer
online version: https://learn.microsoft.com/powershell/module/dnsserver/import-dnsserverroothint?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Import-DnsServerRootHint

## SYNOPSIS
Copies root hints from a DNS server.

## SYNTAX

```
Import-DnsServerRootHint [-NameServer] <String> [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Import-DnsServerRootHint** cmdlet copies root hints from a DNS server.
The root hints that you copy will not overwrite any existing root hints.

## EXAMPLES

### Example 1: Copy root hints by using an IP address
```
PS C:\> Import-DnsServerRootHint -NameServer "172.23.90.136" -PassThru -Verbose
```

This command copies root hints from the DNS server that has the IP address 172.23.90.136.

### Example 2: Copy root hints by using a DNS server name
```
PS C:\>Import-DnsServerRootHint -NameServer "dept01.server01.contoso.com" -PassThru
```

This command copies root hints from the DNS server that is named dept01.server01.contoso.com.

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

### -NameServer
Specifies a DNS name server.

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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerRootHint[]

## NOTES

## RELATED LINKS

[Add-DnsServerRootHint](./Add-DnsServerRootHint.md)

[Remove-DnsServerRootHint](./Remove-DnsServerRootHint.md)

[Get-DnsServerRootHint](./Get-DnsServerRootHint.md)

[Set-DnsServerRootHint](./Set-DnsServerRootHint.md)


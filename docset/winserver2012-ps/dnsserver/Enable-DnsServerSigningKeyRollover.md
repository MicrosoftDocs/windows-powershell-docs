---
external help file: DnsServer_Cmdlets.xml
Module Name: DnsServer
online version: https://learn.microsoft.com/powershell/module/dnsserver/enable-dnsserversigningkeyrollover?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Enable-DnsServerSigningKeyRollover

## SYNOPSIS
Enables rollover on the input key.

## SYNTAX

```
Enable-DnsServerSigningKeyRollover [-ZoneName] <String> [-KeyId] <Guid> [[-RolloverPeriod] <TimeSpan>]
 [[-InitialRolloverOffset] <TimeSpan>] [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-Force]
 [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Enable-DNSServerSigningKeyRollover** cmdlet enables rollover on the input key.
For more information about DNS server signing keys, see the **Key Management** section of Overview of DNSSEChttp://technet.microsoft.com/en-us/library/jj200221.aspx.

## EXAMPLES

### Example 1: Get keys and enable rollover
```
PS C:\> Get-DnsServerSigningKey -ZoneName "DNSServer06.Contoso.com" | Enable-DnsServerSigningKeyRollover
```

This command uses the **Get-DnsServerSigningKey** cmdlet to get keys for the DNSServer06.contoso.com zone.
These keys are then piped to the **Enable-DnsServerSigningKeyRollover** cmdlet, which enables rollover for each key.

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
The acceptable values for this parameter are: an IP v4 address, an IP v6 address, and any other value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

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
Instructs the cmdlet to perform the operation without prompting for confirmation.

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

### -InitialRolloverOffset
Specifies the amount of time before the first scheduled key rollover occurs.
You can stagger key rollovers by using this parameter.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyId
Identifies a key.

```yaml
Type: Guid
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

### -RolloverPeriod
Specifies the amount of time between scheduled key rollovers.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
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
Specifies the name of the zone in which DNS Security Extensions (DNSSEC) operations are performed.

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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerSigningKey

## NOTES

## RELATED LINKS

[Disable-DnsServerSigningKeyRollover](./Disable-DnsServerSigningKeyRollover.md)

[Invoke-DnsServerSigningKeyRollover](./Invoke-DnsServerSigningKeyRollover.md)

[Get-DnsServerSigningKey](./Get-DnsServerSigningKey.md)


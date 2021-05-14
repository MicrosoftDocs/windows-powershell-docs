---
external help file: DnsServer_Cmdlets.xml
Module Name: DnsServer
online version: https://docs.microsoft.com/powershell/module/dnsserver/set-dnsserversigningkey?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-DnsServerSigningKey

## SYNOPSIS
Changes settings of a signing key.

## SYNTAX

```
Set-DnsServerSigningKey [-ZoneName] <String> [-KeyId] <Guid> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-DnsKeySignatureValidityPeriod <TimeSpan>] [-DSSignatureValidityPeriod <TimeSpan>]
 [-NextRolloverAction <String>] [-PassThru] [-RolloverPeriod <TimeSpan>] [-ThrottleLimit <Int32>]
 [-ZoneSignatureValidityPeriod <TimeSpan>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-DnsServerSigningKey** cmdlet changes settings of a signing key for a zone.
You must specify the **ZoneName** parameter and at least one of the optional parameters.

## EXAMPLES

### Example 1: Retire signing keys during the next rollover
```
PS C:\> Get-DnsServerSigningKey -ZoneName "sec.contoso.com" | Set-DnsServerSigningKey -NextRolloverAction "Retire"
```

This command retires the signing keys of a zone during the next rollover.
The **Get-DnsServerSigningKey** cmdlet gets the signing keys for the zone that is named sec.contoso.com and pipes the results to the **Set-DnsServerSigningKey** cmdlet.

**Set-DnsServerSigningKey** specifies that the signing keys will be retired during the next rollover.

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

### -DnsKeySignatureValidityPeriod
Specifies the amount of time that signatures that cover DNSKEY record sets are valid.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DSSignatureValidityPeriod
Specifies the amount of time that signatures that cover DS record sets are valid.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyId
Specifies the unique identifier of a key.

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

### -NextRolloverAction
Specifies the next rollover action.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
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

### -RolloverPeriod
Specifies the amount of time between scheduled key rollovers.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

### -ZoneSignatureValidityPeriod
Specifies the amount of time that signatures that cover all other record sets are valid.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

[Get-DnsServerSigningKey](./Get-DnsServerSigningKey.md)

[Add-DnsServerSigningKey](./Add-DnsServerSigningKey.md)

[Remove-DnsServerSigningKey](./Remove-DnsServerSigningKey.md)

[Disable-DnsServerSigningKeyRollover](./Disable-DnsServerSigningKeyRollover.md)

[Enable-DnsServerSigningKeyRollover](./Enable-DnsServerSigningKeyRollover.md)

[Invoke-DnsServerSigningKeyRollover](./Invoke-DnsServerSigningKeyRollover.md)


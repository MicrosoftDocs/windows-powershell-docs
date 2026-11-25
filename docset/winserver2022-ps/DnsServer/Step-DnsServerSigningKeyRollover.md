---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerSigningKeyRollover_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/step-dnsserversigningkeyrollover?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Step-DnsServerSigningKeyRollover
---

# Step-DnsServerSigningKeyRollover

## SYNOPSIS

Rolls over a KSK that is waiting for a parent DS update.

## SYNTAX

```
Step-DnsServerSigningKeyRollover [-ZoneName] <String> [-KeyId] <Guid> [-Force] [-PassThru]
 [-ComputerName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Step-DnsServerSigningKeyRollover` cmdlet rolls over a key signing key (KSK) that is waiting
for an update from a parent delegation signer (DS). If a Domain Name System (DNS) server that hosts
a securely delegated zone cannot check whether the DS record in a parent is updated, use this cmdlet
to force a rollover.

Important: You must manually update the DS record in the parent before you run this cmdlet.

## EXAMPLES

### Example 1: Force a key signing key rollover

This example gets keys for a signed zone, and then forces a KSK rollover for one of the keys in the zone.

The first command uses the **Get-DnsServerSigningKey** cmdlet to gets keys for the signed zone Sec.Contoso.com.

```powershell
Get-DnsServerSigningKey -ZoneName "Sec.Contoso.com"
```

```Output
KeyId                                  KeyType         CryptoAlgorithm    KeyLength  StoreKeysInAD   IsRolloverEnabled
-----                                  -------         ---------------    ---------  -------------   -----------------
5fe47b29-6bf8-457a-b457-e640893ebd53   KeySigningKey   RsaSha256          2048       True            True
aaf3301e-feb2-4ba7-8ac6-273c6bda75af   KeySigningKey   RsaSha1NSec3       2048       True            True
fbf3116f-b0ba-4bf8-bf35-68dab6d4765b   ZoneSigningKey  RsaSha1NSec3       1024       True            True
f760fcb5-577b-4237-b0b2-513e1f68ec72   ZoneSigningKey  RsaSha256          1024       True            True
```

```powershell
Step-DnsServerSigningKeyRollover -KeyId 5fe47b29-6bf8-457a-b457-e640893ebd53 -ZoneName "Sec.Contoso.com" -Force
```

The last command forces a KSK rollover that is waiting for a parent DS update on Contoso.com. The
command performs a KSK rollover for the specified key in the zone named Sec.Contoso.com.

## PARAMETERS

### -AsJob

Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to
complete.

The cmdlet immediately returns an object that represents the job and then displays the command
prompt. You can continue to work in the session while the job completes. To manage the job, use the
`*-Job` cmdlets. To get the job results, use the
[Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see
[about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967)
or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet. The default is the
current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Specifies a remote DNS server. Specify the IP address or any value that resolves to an IP address,
such as a fully qualified domain name (FQDN), host name, or NETBIOS name, for the DNS server.

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

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Forces the command to run without asking for user confirmation.

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

### -KeyId

Specifies the ID of the key for which to perform the KSK rollover.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Returns an object representing the item with which you are working. By default, this cmdlet does not
generate any output.

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

Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell&reg; calculates an
optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the
computer. The throttle limit applies only to the current cmdlet, not to the session or to the
computer.

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

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ZoneName

Specifies the name of the DNS zone in which the cmdlet performs the KSK rollover.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerSigningKey[]

The output object contains the following fields:

- ActiveKey
- CryptoAlgorithm
- CurrentRolloverStatusCurrentState
- DnsKeySignatureValidityPeriod
- DSSignatureValidityPeriodInitialRolloverOffset
- KeyId
- KeyLengthKeyStorageProvider
- KeyType
- LastRolloverTime
- NextKey
- NextRolloverAction
- NextRolloverTime
- RolloverPeriod
- RolloverType
- StandbyKey
- StoreKeysInAD
- ZoneName
- ZoneSignatureValidityPeriod

## NOTES

## RELATED LINKS

[Enable-DnsServerSigningKeyRollover](./Enable-DnsServerSigningKeyRollover.md)

[Invoke-DnsServerSigningKeyRollover](./Invoke-DnsServerSigningKeyRollover.md)

[Disable-DnsServerSigningKeyRollover](./Disable-DnsServerSigningKeyRollover.md)

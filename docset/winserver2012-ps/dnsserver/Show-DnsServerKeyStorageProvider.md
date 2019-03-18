---
external help file: DnsServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: E7D3765D-0BBD-4D0C-A8F7-54C656A746FD
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Show-DnsServerKeyStorageProvider

## SYNOPSIS
Returns a list of key storage providers.

## SYNTAX

```
Show-DnsServerKeyStorageProvider [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Show-DnsServerKeyStorageProvider** cmdlet returns a list key storage providers that are available on a DNS server.
You can use the key storage providers to create a zone signing key (ZSK) and a key signing key (KSK).

## EXAMPLES

### Example 1: Return key storage providers
```
PS C:\> Show-DnsServerKeyStorageProvider
```

This command returns the key storage providers on the local DNS server.

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

### System.String[]

## NOTES

## RELATED LINKS

[00000000-0000-0000-0000-000000000000](00000000-0000-0000-0000-000000000000)


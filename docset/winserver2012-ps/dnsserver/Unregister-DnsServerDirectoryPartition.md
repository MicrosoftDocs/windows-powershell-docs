---
external help file: DnsServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 28F4646E-A4E7-4C9B-A195-69E733F55D7E
manager: dansimp
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Unregister-DnsServerDirectoryPartition

## SYNOPSIS
Deregisters a DNS server from a DNS application directory partition.

## SYNTAX

```
Unregister-DnsServerDirectoryPartition [-Name] <String> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-Force] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **UnRegister-DnsServerDirectoryPartition** cmdlet deregisters a Domain Name System (DNS) server from a specified DNS application directory partition.
After you deregister a DNS server from a DNS application directory partition, the DNS server removes itself the from the replication scope of the partition.

## EXAMPLES

### Example 1: Deregister a DNS server from a directory application partition
```
PS C:\> UnRegister-DnsServerDirectoryPartition -Name "ADpart" -Verbose
```

This command deregisters a DNS server from the DNS directory application partition named ADpart.

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

### -Force
Deregisters a DNS server from a DNS application directory partition without prompting you for confirmation.
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

### -Name
Specifies the FQDN of a DNS application directory partition.

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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerDirectoryPartition

## NOTES

## RELATED LINKS

[Add-DnsServerDirectoryPartition](./Add-DnsServerDirectoryPartition.md)

[Get-DnsServerDirectoryPartition](./Get-DnsServerDirectoryPartition.md)

[Register-DnsServerDirectoryPartition](./Register-DnsServerDirectoryPartition.md)

[Remove-DnsServerDirectoryPartition](./Remove-DnsServerDirectoryPartition.md)


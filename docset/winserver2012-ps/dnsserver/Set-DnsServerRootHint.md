---
external help file: DnsServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 67E8F936-780C-426C-B4AA-C6387C2F8E02
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Set-DnsServerRootHint

## SYNOPSIS
Replaces a list of root hints.

## SYNTAX

```
Set-DnsServerRootHint [-InputObject] <CimInstance> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-DnsServerRootHint** cmdlet replaces the list of root hints on a Domain Name System (DNS) server.
This cmdlet overwrites the list of root hints with the list of root hints that you specify by using the **InputObject** parameter.

## EXAMPLES

### Example 1: Change the IP address of a root hint
```
The first command adds a root hint for the DNS name server that is named H.Root-Servers.net and the IP address 172.24.60.128.
PS C:\>Add-DnsServerRootHint -NameServer "H.Root-Servers.net" -IPAddress 172.24.60.128

The second command assigns the value that is returned by the **Get-DnsServerRootHint** cmdlet to the variable $a. **Get-DnsServerRootHint** gets a list of all root hints on the local DNS server. The command then pipes that collection to the **Where-Object** cmdlet. **Where-Object** filters the resource record to get the root hint for the DNS name server that is named H.Root-Servers.net.
PS C:\>$a = (Get-DnsServerRootHint | Where-Object {$_.NameServer.RecordData.NameServer -eq "H.Root-Servers.net."} )

The third command sets the value of the IP address of the root hint to 172.24.60.132 for the DNS name server H.Root-Servers.net.
PS C:\>$a.IPAddress[0].RecordData.Ipv4address = "172.24.60.132"

The fourth command replaces the list of root hints on the local DNS server with the root hint for the DNS name server H.Root-Servers.net.
PS C:\>Set-DnsServerRootHint $a
```

This example adds a root hint to the list of root hints on a DNS server and changes the IP address of the root hint.

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerRootHint

## NOTES

## RELATED LINKS

[Get-DnsServerRootHint](./Get-DnsServerRootHint.md)

[Import-DnsServerRootHint](./Import-DnsServerRootHint.md)

[Add-DnsServerRootHint](./Add-DnsServerRootHint.md)

[Remove-DnsServerRootHint](./Remove-DnsServerRootHint.md)


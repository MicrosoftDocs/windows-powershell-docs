---
external help file: DnsServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: AB325C11-CDA0-4071-A573-30FFBD46760D
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-DnsServer

## SYNOPSIS
Retrieves a DNS server configuration.

## SYNTAX

```
Get-DnsServer [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DnsServer** cmdlet retrieves a Domain Name System (DNS) server configuration.

You can pipe the output of the **Get-DnsServer** cmdlet to the **Export-Clixml** cmdlet, which generates an XML file of the configuration.
You can use the XML file to back up or transfer DNS settings between computers.
For more information about **Export-Clixml**, see [Using the Export-Clixml cmdlet](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-clixml).

## EXAMPLES

### Example 1: Get a DNS server configuration
```powershell
PS C:\>Get-DnsServer -ComputerName "10.255.255.254"
```

This command gets a DNS server configuration.

### Example 2: Get local DNS server configuration and pipe it to Export-Clixml
```powershell
PS C:\>Get-DnsServer | Export-Clixml -Path "c:\config\DnsServerConfig.xml"
```

This command gets the DNS server configuration on the local server and pipes it to the **Export-Clixml** cmdlet to be translated into an XML file.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete. 

The cmdlet immediately returns an object that represents the job and then displays the command prompt. 
You can continue to work in the session while the job completes. 
To manage the job, use the `*-Job` cmdlets. 
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet. 

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
The acceptable values for this parameter are: an IP V4 address; an IP V6 address; any other value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

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

### Microsoft.Management.Infrastructure.CimInstance#DnsServer

## NOTES

## RELATED LINKS

[Set-DnsServer](./Set-DnsServer.md)

[Test-DnsServer](./Test-DnsServer.md)


---
external help file: UnifiedRA_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 259C1108-5C9C-4DDA-BBEF-2A6C49D98CD2
manager: dansimp
---

# Get-DAClientDnsConfiguration

## SYNOPSIS
Displays all the Name Resolution Policy Table (NRPT) entries and the local name resolution property.

## SYNTAX

```
Get-DAClientDnsConfiguration [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DAClientDNSConfiguration** cmdlet displays all the Name Resolution Policy Table (NRPT) entries and the local name resolution property.

Specifically, the following properties are displayed. 

 -- List of suffixes. 

 -- DirectAccess (DA) rules state. 

 -- DNS client Local Name resolution fallback policy. 

 -- DNS client query policy (Disable, QueryIPv6Only, or QueryBoth).

The configuration returned is applicable, globally, to the entire DA deployment.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-DAClientDNSConfiguration
NrptSuffixes   : {.corp.contoso.com, edge1.corp.contoso.com} 
EnableDAForAllNetworks  : Disable 
SecureNameQueryFallback : FallbackPrivate 
QueryPolicy             : Disable
```

This example gets the NRPT configuration for the DA deployment.

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
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the Remote Access server computer specific tasks should be run.

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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DAClientDnsConfiguration
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The output object contains the following properties: 

 -- The NRPT entries in the NRPT table.
Each entry is an instance of the **DnsClientNrptRule** object. 

 -- The **DnsClientNrptGlobal** object which contains the local name resolution settings.

## NOTES

## RELATED LINKS

[Add-DAClientDnsConfiguration](./Add-DAClientDnsConfiguration.md)

[Remove-DAClientDnsConfiguration](./Remove-DAClientDnsConfiguration.md)

[Set-DAClientDnsConfiguration](./Set-DAClientDnsConfiguration.md)


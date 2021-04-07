---
author: Kateyanne
description: 
external help file: MSFT_DnsClientCache.cdxml-help.xml
manager: jasgro
Module Name: DnsClient
ms.author: v-kaunu
ms.date: 10/29/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/dnsclient/get-dnsclientcache?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DnsClientCache
---

# Get-DnsClientCache

## SYNOPSIS
Retrieves the contents of the DNS client cache.

## SYNTAX

```
Get-DnsClientCache [[-Entry] <String[]>] [-Name <String[]>] [-Type <Type[]>] [-Status <Status[]>]
 [-Section <Section[]>] [-TimeToLive <UInt32[]>] [-DataLength <UInt16[]>] [-Data <String[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DnsClientCache** cmdlet retrieves the contents of the local DNS client cache.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DnsClientCache
```

This example gets the contents of the DNS client cache.

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
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Data
Specifies the record data.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DataLength
Specifies the record data length.

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Entry
Specifies the cache entry name.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the record name.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: RecordName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Section
Specifies the record section.
The acceptable values for this parameter are: Answer, Authority, or Additional.

```yaml
Type: Section[]
Parameter Sets: (All)
Aliases: 
Accepted values: Answer, Authority, Additional

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status
Specifies the record status.
The acceptable values for this parameter are: Success, NotExist, or NoRecords.

```yaml
Type: Status[]
Parameter Sets: (All)
Aliases: 
Accepted values: Success, NotExist, NoRecords

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

### -TimeToLive
Specifies the record time-to-live, in seconds.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases: TTL

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type
Specifies the record type.
The acceptable values for this parameter are: A, NS, CNAME, SOA, PTR, MX, AAAA, or SRV.

```yaml
Type: Type[]
Parameter Sets: (All)
Aliases: RecordType
Accepted values: A, NS, CNAME, SOA, PTR, MX, AAAA, SRV

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_DnsClientCache
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The MSFT_DnsClientCache object contains all of the entries in the DNS client cache.

## NOTES

## RELATED LINKS

[Clear-DnsClientCache](./Clear-DnsClientCache.md)


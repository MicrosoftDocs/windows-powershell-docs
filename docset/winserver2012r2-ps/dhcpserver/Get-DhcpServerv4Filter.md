---
external help file: PS_DhcpServerv4Filter_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
online version: 
schema: 2.0.0
title: Get-DhcpServerv4Filter
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 25E6A9FE-9B42-49D6-AEC4-66562806B17E
---

# Get-DhcpServerv4Filter

## SYNOPSIS
Gets the list of all MAC addresses from the allow list or the deny list on the Dynamic Host Configuration Protocol (DHCP) server service.

## SYNTAX

```
Get-DhcpServerv4Filter [[-List] <String>] [-ComputerName <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DhcpServerv4Filter** cmdlet gets the list of all MAC addresses from the allow list or the deny list on the Dynamic Host Configuration Protocol (DHCP) server service.

If the **List** parameter is not specified, both allow and deny filters are returned.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DhcpServerv4Filter -ComputerName dhcpserver.contoso.com
```

This example gets all of the MAC addresses in the allowed and denied lists configured on the DHCP server service on the computer named dhcpserver.contoso.com.

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

### -ComputerName
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer running the DHCP server service.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -List
Specifies the list from which one or more MAC addresses are to be retrieved.
The acceptable values for this parameter are: Allow or Deny.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Allow, Deny

Required: False
Position: 1
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Filter[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv4Filter](./Add-DhcpServerv4Filter.md)

[Get-DhcpServerv4FilterList](./Get-DhcpServerv4FilterList.md)

[Remove-DhcpServerv4Filter](./Remove-DhcpServerv4Filter.md)

[Set-DhcpServerv4FilterList](./Set-DhcpServerv4FilterList.md)


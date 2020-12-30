---
external help file: PS_DhcpServerv4MulticastExclusionRange_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
online version: 
schema: 2.0.0
title: Add-DhcpServerv4MulticastExclusionRange
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
ms.assetid: 5D3C543D-220A-4673-8E80-0E18F03928F4
---

# Add-DhcpServerv4MulticastExclusionRange

## SYNOPSIS
Adds a range of addresses to exclude from a multicast scope.

## SYNTAX

```
Add-DhcpServerv4MulticastExclusionRange [-ComputerName <String>] [-Name] <String> [-StartRange] <IPAddress>
 [-EndRange] <IPAddress> [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DhcpServerv4MulticastExclusionRange** cmdlet add a range of addresses to exclude from a multicast scope.
An exclusion prevents the Dynamic Host Configuration Protocol (DHCP) Server service from offering these addresses for DHCP assignment.

## EXAMPLES

### Example 1: Add an exclusion range for a multicast scope
```
PS C:\> Add-DhcpServerv4MulticastExclusionRange -ComputerName "DhcpServer01.Contoso.com" -Name "Multicast_AudioConference" -StartRange 224.0.0.21 -EndRange 224.0.0.25
```

This command adds an exclusion range with the IP addresses 224.0.0.21 to 224.0.0.25 for the multicast scope named Multicast_AudioConferenceGroup on the DHCP Server service that runs on the computer named DhcpServer01.Contoso.com.

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
Specifies the Domain Name System (DNS) name or IP address of the target computer that runs the DHCP Server service.

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

### -EndRange
Specifies the high end of the range of IP addresses to exclude from a multicast scope.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the multicast scope for which to add the IP address exclusion range.

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

### -StartRange
Specifies the low end of the range of IP addresses to exclude from a multicast scope.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DhcpServerv4MulticastExclusionRange

## NOTES

## RELATED LINKS

[Get-DhcpServerv4MulticastExclusionRange](./Get-DhcpServerv4MulticastExclusionRange.md)

[Remove-DhcpServerv4MulticastExclusionRange](./Remove-DhcpServerv4MulticastExclusionRange.md)


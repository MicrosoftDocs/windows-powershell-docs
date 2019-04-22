---
external help file: MSFT_NetNatStaticMapping.cdxml-help.xml
Module Name: NetNat
online version: 
schema: 2.0.0
title: Get-NetNatStaticMapping
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 312BF566-61E3-4061-B9F9-828BC1A13695
ms.author: kenwith
ms.reviewer: brianlic
---

# Get-NetNatStaticMapping

## SYNOPSIS
Gets static mappings configured on NAT instances.

## SYNTAX

```
Get-NetNatStaticMapping [[-NatName] <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetNatMapping** cmdlet gets static mappings configured on network address translation (NAT) instances.
A static mapping enables an incoming connection from an external network to an internal network through the NAT.

## EXAMPLES

### Example 1: Get static mappings of NAT instances
```
PS C:\> Get-NetNatStaticMapping
```

This command gets all static mappings of NAT instances configured on the local computer.

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

### -NatName
Specifies an array of names of NAT instances.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetNatStaticMapping

## NOTES

## RELATED LINKS

[Add-NetNatStaticMapping](./Add-NetNatStaticMapping.md)

[Remove-NetNatStaticMapping](./Remove-NetNatStaticMapping.md)


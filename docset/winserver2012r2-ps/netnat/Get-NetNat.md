---
external help file: MSFT_NetNat.cdxml-help.xml
Module Name: NetNat
online version: 
schema: 2.0.0
title: Get-NetNat
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 23CBE431-3C83-4104-BEE7-C5BEEAB418EF
ms.author: kenwith
ms.reviewer: brianlic
---

# Get-NetNat

## SYNOPSIS
Gets NAT objects.

## SYNTAX

```
Get-NetNat [[-Name] <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetNat** cmdlet gets Network Address Translation (NAT) objects configured on a computer.
NAT modifies IP address and port information in packet headers.

Specify a value for the **Name** parameter to get specific NAT objects.
To get all the NAT objects for a computer, do not include the **Name** parameter.
You can use this cmdlet to get NAT objects to modify by using the Set-NetNat cmdlet or NAT objects to remove by using the Remove-NetNat cmdlet.

## EXAMPLES

### Example 1: Get all the NAT objects for the current computer
```
PS C:\> Get-NetNat
```

This command gets all the NAT objects for the current computer.

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

### -Name
Specifies an array of names of NAT objects.

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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetNat

## NOTES

## RELATED LINKS

[New-NetNat](./New-NetNat.md)

[Remove-NetNat](./Remove-NetNat.md)

[Set-NetNat](./Set-NetNat.md)


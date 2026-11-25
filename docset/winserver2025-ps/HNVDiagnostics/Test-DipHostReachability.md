---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DipHostReachability.psm1-help.xml
Module Name: HNVDiagnostics
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hnvdiagnostics/test-diphostreachability?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-DipHostReachability
---

# Test-DipHostReachability

## SYNOPSIS
Tests whether DIPs can be reached.

## SYNTAX

```
Test-DipHostReachability [[-OperationId] <String>] [-Dips] <String[]> [[-PayloadSize] <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Test-DipHostReachability** cmdlet tests whether datacenter IP (DIP) addresses can be reached.

## EXAMPLES

### Example 1: Test a DIP
```
PS C:\> Test-DipHostReachability -Dips "10.123.176.108"
```

This command tests whether the specified DIP can be reached.

## PARAMETERS

### -Dips
Specifies an array of DIPs to test.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OperationId
Specifies the operation ID.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PayloadSize
Specifies the size of the payload to include in Internet Control Message Protocol (ICMP) requests.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS


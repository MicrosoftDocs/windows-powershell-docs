---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_DtcClusterTMMappingTask_v1.0.cdxml-help.xml
Module Name: MsDtc
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/msdtc/get-dtcclustertmmapping?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DtcClusterTMMapping
---

# Get-DtcClusterTMMapping

## SYNOPSIS
Gets cluster DTC Mapping data.

## SYNTAX

```
Get-DtcClusterTMMapping [-Name <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-DtcClusterTMMapping** cmdlet gets cluster Distributed Transaction Coordinator (DTC) Mapping data.
If you do not specify the **Name** parameter, the cmdlet gets all cluster Transaction Manager (TM) mapping data.
This cmdlet is supported on clustered computers only.

## EXAMPLES

### Example 1: Get cluster mapping
```
PS C:\> Get-DtcClusterTMMapping -Name "TestMapping"
```

This example get the cluster DTC TM mapping for the **MappingName** TestMapping.

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
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the **MappingName**.
If you do not specify this parameter, the cmdlet gets all TM mappings.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### DtcClusterTMMapping
This cmdlet returns a **DtcClusterTMMapping** object that contains the specified **MappingName** value.
If you do not specify a **MappingName**, this cmdlet gets all mappings.

## NOTES

## RELATED LINKS

[Add-DtcClusterTMMapping](./Add-DtcClusterTMMapping.md)

[Remove-DtcClusterTMMapping](./Remove-DtcClusterTMMapping.md)

[Set-DtcClusterTMMapping](./Set-DtcClusterTMMapping.md)


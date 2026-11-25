---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_MpThreatCatalog.cdxml-help.xml
Module Name: Defender
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/defender/get-mpthreatcatalog?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-MpThreatCatalog
---

# Get-MpThreatCatalog

## SYNOPSIS
Gets known threats from the definitions catalog.

## SYNTAX

### DefaultSet (Default)

```
Get-MpThreatCatalog [<CommonParameters>]
```

### ById

```
Get-MpThreatCatalog
 [-AsJob]
 [-CimSession <CimSession[]>]
 [-ThreatID <Int64[]>]
 [-ThrottleLimit <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION

The **Get-MpThreatCatalog** cmdlet gets known threats from the Windows Defender definitions catalog.
The definitions catalog contains references to all known threats that Windows Defender can identify.

## EXAMPLES

### Example 1: Get a known threat from the definitions catalog

```powershell
PS C:\> Get-MpThreatCatalog -ThreatID 1994
```

This command gets the known threat that has the ID 1994.

## PARAMETERS

### -AsJob

Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to
complete.

The cmdlet immediately returns an object that represents the job and then displays the command
prompt. You can continue to work in the session while the job completes. To manage the job, use the
`*-Job` cmdlets. To get the job results, use the
[Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see
[about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

```yaml
Type: SwitchParameter
Parameter Sets: ById
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967)
or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet. The default is the
current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: ById
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThreatID

Specifies an array of threat IDs.
This cmdlet gets the threats that you specify from the definitions catalog.

```yaml
Type: Int64[]
Parameter Sets: ById
Aliases: ID

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an
optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the
computer. The throttle limit applies only to the current cmdlet, not to the session or to the
computer.

```yaml
Type: Int32
Parameter Sets: ById
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-MpThreat](./Get-MpThreat.md)

[Remove-MpThreat](./Remove-MpThreat.md)

[Get-MpThreatDetection](./Get-MpThreatDetection.md)

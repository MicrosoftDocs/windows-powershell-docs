---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_DtcClusterTMMappingTask_v1.0.cdxml-help.xml
Module Name: MsDtc
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/msdtc/add-dtcclustertmmapping?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DtcClusterTMMapping
---

# Add-DtcClusterTMMapping

## SYNOPSIS
Adds a cluster DTC mapping.

## SYNTAX

### ServiceSet
```
Add-DtcClusterTMMapping -Name <String> -ClusterResourceName <String> -Local <Boolean> [-PassThru]
 -Service <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ExeSet
```
Add-DtcClusterTMMapping -Name <String> -ClusterResourceName <String> -Local <Boolean> [-PassThru]
 -ExecutablePath <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ComPlusSet
```
Add-DtcClusterTMMapping -Name <String> -ClusterResourceName <String> -ComPlusAppId <String> -Local <Boolean>
 [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DtcClusterTMMapping** cmdlet adds a cluster Distributed Transaction Coordinator (DTC) mapping.
This cmdlet is supported on clustered computers only.

## EXAMPLES

### Example 1: Create a cluster mapping
```
PS C:\> Add-DtcClusterTMMapping -ClusterResourceName "DtcResource1" -ExecutablePath "C:\TestApp\App.exe" -Local $False -Name "LocalTestAppMapping"
```

This command creates a DTC cluster Transaction Manager (TM) mapping.

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

### -ClusterResourceName
Specifies the name of a cluster DTC resource.
This cmdlet associates this mapping with the resource that the name specifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComPlusAppId
Specifies the COM+ application identifier to associate with this mapping.

```yaml
Type: String
Parameter Sets: ComPlusSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExecutablePath
Specifies the path of the application to associate with this mapping.

```yaml
Type: String
Parameter Sets: ExeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Local
Specifies whether the application type is local.
If you specify a value of $False, the application is a clustered resource.
If the application type is local, the application maps to the Local DTC instance and the cmdlet ignores the value of the **ClusterResourceName** parameter.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the DTC mapping to add.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### -Service
Specifies the name of the Windows service to associate with this mapping.

```yaml
Type: String
Parameter Sets: ServiceSet
Aliases:

Required: True
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-DtcClusterTMMapping](./Get-DtcClusterTMMapping.md)

[Remove-DtcClusterTMMapping](./Remove-DtcClusterTMMapping.md)

[Set-DtcClusterTMMapping](./Set-DtcClusterTMMapping.md)


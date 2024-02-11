---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_DtcTask_v1.0.cdxml-help.xml
Module Name: MsDtc
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/msdtc/stop-dtc?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Dtc
---

# Stop-Dtc

## SYNOPSIS
Stops a DTC instance.

## SYNTAX

```
Stop-Dtc [-DtcName <String>] [-Recursive] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-Dtc** cmdlet stops the Distributed Transaction Coordinator (DTC) instance that the **DtcName** parameter specifies.

## EXAMPLES

### Example 1: Stop a local DTC instance
```
This command uses the **Get-Dtc** cmdlet to view the status of the local DTC instance.
PS C:\> Get-Dtc -DtcName "Local"
__GENUS           : 2
__CLASS           : DtcInstance
__SUPERCLASS      :
__DYNASTY         : DtcInstance
__RELPATH         :
__PROPERTY_COUNT  : 7
__DERIVATION      : {}
__SERVER          :
__NAMESPACE       :
__PATH            :
DtcName           : Local
KtrmEndpointCid   : b6628c9f-46ff-404d-a0fa-62657cb828af
OleTxEndpointCid  : f3027ea1-4ee5-45b5-a01c-06f41221111b
Status            : Started
UisEndpointCid    : e9385758-8092-4dd7-8b09-587aa427a58e
VirtualServerName : Contoso093
XAEndpointCid     : ced49d85-82a9-49d9-a6ee-8c5b4bd7b5bd

This command stops the local DTC instance. The first command shows that the instance is started, and, therefore, it is safe to stop that instance.
PS C:\> Stop-Dtc -DtcName "Local"

This command uses **Get-Dtc**, again, to confirm that the DTC instance is stopped.
PS C:\> Get-Dtc -DtcName "Local"
__GENUS           : 2
__CLASS           : DtcInstance
__SUPERCLASS      :
__DYNASTY         : DtcInstance
__RELPATH         :
__PROPERTY_COUNT  : 7
__DERIVATION      : {}
__SERVER          :
__NAMESPACE       :
__PATH            :
DtcName           : Local
KtrmEndpointCid   : b6628c9f-46ff-404d-a0fa-62657cb828af
OleTxEndpointCid  : f3027ea1-4ee5-45b5-a01c-06f41221111b
Status            : Stopped
UisEndpointCid    : e9385758-8092-4dd7-8b09-587aa427a58e
VirtualServerName : Contoso093
XAEndpointCid     : ced49d85-82a9-49d9-a6ee-8c5b4bd7b5bd
```

This example stops the local DTC instance.
To stop a different instance, specify a different value for the **DtcName** parameter.

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

### -DtcName
Specifies the DTC instance to stop.
If you do not specify this parameter, or if you specify a value of Local, this cmdlet stops the local DTC instance.

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

### -Recursive
Indicates that the cmdlet stops any services that rely on the specified DTC instance, such as Microsoft SQL Server.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-Dtc](./Get-Dtc.md)

[Install-Dtc](./Install-Dtc.md)

[Start-Dtc](./Start-Dtc.md)

[Test-Dtc](./Test-Dtc.md)

[Uninstall-Dtc](./Uninstall-Dtc.md)


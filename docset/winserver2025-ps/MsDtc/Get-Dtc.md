---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_DtcTask_v1.0.cdxml-help.xml
Module Name: MsDtc
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/msdtc/get-dtc?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Dtc
---

# Get-Dtc

## SYNOPSIS
Gets DTC instances.

## SYNTAX

```
Get-Dtc [-DtcName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-Dtc** cmdlet gets Distributed Transaction Coordinator (DTC) instances that run on the host.
Use the **DtcName** parameter to specify a DTC instance.

## EXAMPLES

### Example 1: Get a DTC instance
```
PS C:\> Get-Dtc
DtcName           : Local
KtrmEndpointCid   : b6628c9f-46ff-404d-a0fa-62657cb828af
OleTxEndpointCid  : f3027ea1-4ee5-45b5-a01c-06f41221111b
Status            : Started
UisEndpointCid    : e9385758-8092-4dd7-8b09-587aa427a58e
VirtualServerName : Contoso093
XAEndpointCid     : ced49d85-82a9-49d9-a6ee-8c5b4bd7b5bd

DtcName           : MSDTC-Contoso093DTC1
KtrmEndpointCid   :
OleTxEndpointCid  : 04c1c8e4-4810-4dc5-945b-b1cb2c9a2cc4
Status            : Started
UisEndpointCid    : 9a8d3a2f-c28c-4bb6-91fd-8378492bf6a9
VirtualServerName : Contoso093DTC1
XAEndpointCid     : 956d64a7-a307-4aaa-a5d9-10e31f6c51fa

DtcName           : MSDTC-Contoso093DTC2
KtrmEndpointCid   :
OleTxEndpointCid  : ab8eacbf-7b9e-45a5-b61d-b42194d492ea
Status            : Started
UisEndpointCid    : bf1986e4-7c9f-455b-beba-4b8f9fb431ad
VirtualServerName : Contoso093DTC2
XAEndpointCid     : 2833ac93-f291-4fa2-b413-a7b67f7529c1
```

This command gets a DTC instance.
The command does not specify the **DtcName** parameter, so the cmdlet gets the local instance.

### Example 2: Get the local DTC instance
```
PS C:\> Get-Dtc -DtcName "Local"
DtcName           : Local
KtrmEndpointCid   : b6628c9f-46ff-404d-a0fa-62657cb828af
OleTxEndpointCid  : f3027ea1-4ee5-45b5-a01c-06f41221111b
Status            : Started
UisEndpointCid    : e9385758-8092-4dd7-8b09-587aa427a58e
VirtualServerName : Contoso093
XAEndpointCid     : ced49d85-82a9-49d9-a6ee-8c5b4bd7b5bd
```

This command gets the local DTC instance.

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

### -DtcName
Specifies the DTC instance to get on the host.
If you do not specify this parameter, or if you specify a value of Local, this cmdlet gets the local DTC instance for the host.

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

[Install-Dtc](./Install-Dtc.md)

[Start-Dtc](./Start-Dtc.md)

[Stop-Dtc](./Stop-Dtc.md)

[Test-Dtc](./Test-Dtc.md)

[Uninstall-Dtc](./Uninstall-Dtc.md)


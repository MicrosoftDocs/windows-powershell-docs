---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetEventWFPCaptureProvider.cdxml-help.xml
Module Name: NetEventPacketCapture
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/neteventpacketcapture/get-neteventwfpcaptureprovider?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetEventWFPCaptureProvider
---

# Get-NetEventWFPCaptureProvider

## SYNOPSIS
Displays settings for a local or remote WFP capture provider configuration.

## SYNTAX

### BySessionName (Default)
```
Get-NetEventWFPCaptureProvider [[-SessionName] <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### BySessionOfTheProvider
```
Get-NetEventWFPCaptureProvider [-AssociatedEventSession <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetEventWFPCaptureProvider** cmdlet displays settings for a local or remote Windows Firewall Platform (WFP) capture provider configuration.
For more information about WFP capture providers, see the Add-NetEventWFPCaptureProvider cmdlet.

## EXAMPLES

### Example 1: Get a WFP capture provider
```
PS C:\>Get-NetEventWFPCaptureProvider -SessionName "WFPCapture"
```

This command gets the WFP capture provider configuration for the session named WFPCapture.
The output of this example displays the settings of the **NetEventWFPCaptureProvider**.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -AssociatedEventSession
Specifies the associated network event session, as a CIM object.
To obtain the network event session, use the Get-NetEventSession cmdlet.

```yaml
Type: CimInstance
Parameter Sets: BySessionOfTheProvider
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -SessionName
Specifies an array of session names that are associated with the **NetEventWFPCaptureProvider**.

```yaml
Type: String[]
Parameter Sets: BySessionName
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-NetEventWFPCaptureProvider](./Add-NetEventWFPCaptureProvider.md)

[Remove-NetEventWFPCaptureProvider](./Remove-NetEventWFPCaptureProvider.md)

[Set-NetEventWFPCaptureProvider](./Set-NetEventWFPCaptureProvider.md)


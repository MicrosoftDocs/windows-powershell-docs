---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetQosDcbxSetting.cdxml-help.xml
Module Name: DcbQos
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/dcbqos/set-netqosdcbxsetting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetQosDcbxSetting
---

# Set-NetQosDcbxSetting

## SYNOPSIS
Sets the data center bridging exchange settings.

## SYNTAX

### ByIfAlias (Default)
```
Set-NetQosDcbxSetting [[-InterfaceAlias] <String>] -Willing <Boolean> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByIfIndex
```
Set-NetQosDcbxSetting [[-InterfaceIndex] <UInt32>] -Willing <Boolean> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetQosDcbxSetting -InputObject <CimInstance[]> -Willing <Boolean> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetQosDcbxSetting** cmdlet sets the data center bridging exchange (DCBX) settings.
The only setting that Windows Server® 2012 and later allows a user to set is that the network adapters in computers that run Windows Server 2012 and later accept data center bridging (DCB) configurations from Windows Server 2012 and later or from a remote device by using the DCBX protocol, which is specified in the IEEE data center bridging (DCB) standard.

If the *Willing* parameter is set to $True, Windows Server 2012 or later does not send priority-based flow control (PFC) and traffic class settings to DCB-capable network adapters in the computer.
If the *Willing* parameter is set to $False, Windows Server 2012 or later sends the settings to the network adapters.

## EXAMPLES

### Example 1: Enable the DCBX willing state
```
PS C:\> Set-NetQosDcbxSetting -Willing $True
```

This command enables the DCBX willing state, so that a DCB-capable network adapter is willing to accept configurations from a remote peer.

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InterfaceAlias
```yaml
Type: String
Parameter Sets: ByIfAlias
Aliases: IfAlias

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceIndex
```yaml
Type: UInt32
Parameter Sets: ByIfIndex
Aliases: IfIndex

Required: False
Position: 0
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

### -Willing
Specifies whether a DCB-capable network adapter accepts the configuration from a remote peer by using the DCBX protocol.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.UInt32

### Microsoft.Management.Infrastructure.CimInstance[]

### System.Boolean

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetQosDcbxSettingData

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
This cmdlet returns a **MSFT_NetQosDcbxSettingData** object that contains the DCBX setting configured in Windows Server 2012 and later.
Only if you specify the *PassThru* parameter does the command return the **MSFT_NetQosDcbxSettingData** object.

## NOTES

## RELATED LINKS

[Get-NetQosDcbxSetting](./Get-NetQosDcbxSetting.md)

[Get-NetQosDcbxSetting](./Get-NetQosDcbxSetting.md)


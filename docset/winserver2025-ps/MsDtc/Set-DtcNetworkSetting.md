---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_DtcNetworkSettingTask_v1.0.cdxml-help.xml
Module Name: MsDtc
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/msdtc/set-dtcnetworksetting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DtcNetworkSetting
---

# Set-DtcNetworkSetting

## SYNOPSIS
Modifies DTC network and security configuration for a DTC instance.

## SYNTAX

### NetworkSettings
```
Set-DtcNetworkSetting [-DtcName <String>] [-InboundTransactionsEnabled <Boolean>]
 [-OutboundTransactionsEnabled <Boolean>] [-RemoteClientAccessEnabled <Boolean>]
 [-RemoteAdministrationAccessEnabled <Boolean>] [-XATransactionsEnabled <Boolean>]
 [-LUTransactionsEnabled <Boolean>] [-AuthenticationLevel <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DisableNetwork
```
Set-DtcNetworkSetting [-DtcName <String>] [-DisableNetworkAccess] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DtcNetworkSetting** cmdlet modifies the Distributed Transaction Coordinator (DTC) network and security configuration for the DTC instance specified by the **DtcName** parameter.
This cmdlet also restarts the DTC instance.

## EXAMPLES

### Example 1: Modify network and security settings
```
PS C:\> Set-DtcNetworkSetting -DtcName "Local" -AuthenticationLevel "Incoming" -InboundTransactionsEnabled $False
PS C:\> Get-DtcNetworkSetting -DtcName "Local"
__GENUS                           : 2
__CLASS                           : DtcNetworkSettings
__SUPERCLASS                      :
__DYNASTY                         : DtcNetworkSettings
__RELPATH                         :
__PROPERTY_COUNT                  : 7
__DERIVATION                      : {}
__SERVER                          :
__NAMESPACE                       :
__PATH                            :
AuthenticationLevel               : Mutual
InboundTransactionsEnabled        : True
LUTransactionsEnabled             : True
OutboundTransactionsEnabled       : True
RemoteAdministrationAccessEnabled : True
RemoteClientAccessEnabled         : True
XATransactionsEnabled             : True
```

The first command modifies the DTC network and security settings for the local DTC instance.
The second command verifies the changes.

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

### -AuthenticationLevel
Sets the network authentication level of the DTC instance to NoAuth, Incoming, or Mutual.

```yaml
Type: String
Parameter Sets: NetworkSettings
Aliases:
Accepted values: NoAuth, Incoming, Mutual

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

### -DisableNetworkAccess
Specifies whether to disable network access for the DTC instance.

```yaml
Type: SwitchParameter
Parameter Sets: DisableNetwork
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DtcName
Specifies a DTC instance.
If you do not specify this parameter, or if you specify a value of Local, this cmdlet modifies the local DTC instance.

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

### -InboundTransactionsEnabled
Indicates whether to enable inbound transactions to the DTC instance.

```yaml
Type: Boolean
Parameter Sets: NetworkSettings
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LUTransactionsEnabled
Indicates whether to enable LU transactions in the DTC instance.

```yaml
Type: Boolean
Parameter Sets: NetworkSettings
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutboundTransactionsEnabled
Indicates whether to enable outbound transactions from the DTC instance.

```yaml
Type: Boolean
Parameter Sets: NetworkSettings
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteAdministrationAccessEnabled
Indicates whether to enable remote administration access for the DTC instance.

```yaml
Type: Boolean
Parameter Sets: NetworkSettings
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteClientAccessEnabled
Indicates whether to enable remote client access for the DTC instance.

```yaml
Type: Boolean
Parameter Sets: NetworkSettings
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

### -XATransactionsEnabled
Indicates whether to enable XA transactions in the DTC instance.

```yaml
Type: Boolean
Parameter Sets: NetworkSettings
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

[Get-DtcNetworkSetting](./Get-DtcNetworkSetting.md)


---
external help file: MsDTC_Cmdlets.xml
Module Name: MsDTC
online version: https://docs.microsoft.com/powershell/module/msdtc/set-dtcnetworksetting?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-DtcNetworkSetting

## SYNOPSIS
Modifies DTC network and security configuration for a DTC instance.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-DtcNetworkSetting [-AuthenticationLevel] [-CimSession <CimSession[]>] [-DtcName <String>]
 [-InboundTransactionsEnabled <Boolean>] [-LUTransactionsEnabled <Boolean>]
 [-OutboundTransactionsEnabled <Boolean>] [-RemoteAdministrationAccessEnabled <Boolean>]
 [-RemoteClientAccessEnabled <Boolean>] [-ThrottleLimit <Int32>] [-XATransactionsEnabled <Boolean>] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-DtcNetworkSetting [-CimSession <CimSession[]>] [-DtcName <String>] [-ThrottleLimit <Int32>]
 [-DisableNetworkAccess] [-Confirm] [-WhatIf]
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

### -AuthenticationLevel
Sets the network authentication level of the DTC instance to NoAuth, Incoming, or Mutual.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

### -DisableNetworkAccess
Specifies whether to disable network access for the DTC instance.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -InboundTransactionsEnabled
Indicates whether to enable inbound transactions to the DTC instance.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

### -XATransactionsEnabled
Indicates whether to enable XA transactions in the DTC instance.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

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
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-DtcNetworkSetting](./Get-DtcNetworkSetting.md)


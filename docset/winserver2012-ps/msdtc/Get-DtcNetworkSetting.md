---
external help file: MsDTC_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 0D446E62-AC43-4B9C-BFA3-A2CFB9C9DF40
manager: dansimp
---

# Get-DtcNetworkSetting

## SYNOPSIS
Gets DTC network and security configuration settings.

## SYNTAX

```
Get-DtcNetworkSetting [-CimSession <CimSession[]>] [-DtcName <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DtcNetworkSetting** cmdlet gets the Distributed Transaction Coordinator (DTC) network and security configuration settings for a DTC instance.
Use the **DtcName** parameter to specify a DTC instance.

## EXAMPLES

### Example 1: Get network and security configuration settings for the local DTC instance
```
PS C:\> Get-DtcNetworkSetting -DtcName "Local"
AuthenticationLevel               : Mutual
InboundTransactionsEnabled        : True
LUTransactionsEnabled             : True
OutboundTransactionsEnabled       : True
RemoteAdministrationAccessEnabled : True
RemoteClientAccessEnabled         : True
XATransactionsEnabled             : True
```

This command gets the network and security configuration settings for the local DTC instance.

## PARAMETERS

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

### -DtcName
Specifies a DTC instance.
The cmdlet gets network and security configuration settings for this instance.
If you do not specify this parameter, or if you specify a value of Local, this cmdlet returns the DTC network and security configuration settings for the local DTC instance.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-DtcNetworkSetting](./Set-DtcNetworkSetting.md)


---
external help file: MsDTC_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 98B9E36F-285E-45AF-BA09-9049F0AD2852
manager: dansimp
---

# Get-DtcLog

## SYNOPSIS
Gets DTC log file settings.

## SYNTAX

```
Get-DtcLog [-CimSession <CimSession[]>] [-DtcName <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DtcLog** cmdlet gets the log file settings for a Distributed Transaction Coordinator (DTC) instance.
Use the **DtcName** parameter to specify a DTC instance.

## EXAMPLES

### Example 1: Get the log file settings for the local DTC instance
```
PS C:\> Get-DtcLog
MaxSizeInMB      : 512
Path             : C:\Windows\system32\MSDtc
SizeInMB         : 4
```

This command gets the DTC log file settings for the local DTC instance.

### Example 2: Get the log file settings for a specified DTC instance
```
PS C:\> Get-DtcLog -DtcName "InstanceName"
MaxSizeInMB      : 512
Path             : G:\MSDTC\beb6d145-405e-47cd-b326-a5505a461229
SizeInMB         : 4
```

This command gets the DTC log file settings for the specified DTC instance.

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
The cmdlet displays log file settings for this instance.
If you do not specify this parameter, or if you specify a value of Local, the log file settings for the local DTC instance are displayed.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Reset-DtcLog](./Reset-DtcLog.md)

[Set-DtcLog](./Set-DtcLog.md)


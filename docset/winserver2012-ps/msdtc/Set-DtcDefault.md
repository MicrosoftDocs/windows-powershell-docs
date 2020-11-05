---
external help file: MsDTC_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 3FA71004-D5B6-41AA-8EF4-618A55A41DDB
manager: dansimp
---

# Set-DtcDefault

## SYNOPSIS
Sets the default transactions coordinator.

## SYNTAX

```
Set-DtcDefault [-CimSession <CimSession[]>] [-ServerName <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Set-DtcDefault** cmdlet sets the default transactions coordinator.

## EXAMPLES

### Example 1: Set the default DTC coordinator
```
PS C:\>Set-DtcDefault -ServerName "host14"
```

This command sets the default DTC coordinator to host14.

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

### -ServerName
Specifies the host name or virtual server name of the Distributed Transaction Coordinator (DTC) to set as the default coordinator.
If you do not specify this parameter, this cmdlet specifies the local DTC as the default coordinator.

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

[Get-DtcDefault](./Get-DtcDefault.md)


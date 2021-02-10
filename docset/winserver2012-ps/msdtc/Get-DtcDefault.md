---
external help file: MsDTC_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 52539594-92A8-4E49-B96D-C0FD19BC165D
manager: dansimp
---

# Get-DtcDefault

## SYNOPSIS
Gets the default DTC instance.

## SYNTAX

```
Get-DtcDefault [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DtcDefault** cmdlet gets the default Distributed Transaction Coordinator (DTC) instance that runs on the host.

## EXAMPLES

### Example 1: Get the default DTC
```
PS C:\>Get-DtcDefault

TestMachine17
```

This command queries the default DTC server name.

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

### String
This cmdlet returns the computer name of the default transactions coordinator.

## NOTES

## RELATED LINKS

[Set-DtcDefault](./Set-DtcDefault.md)


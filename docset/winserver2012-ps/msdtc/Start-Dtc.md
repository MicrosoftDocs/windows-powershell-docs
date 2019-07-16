---
external help file: MsDTC_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: F5E605BD-7C7B-45A0-BDEC-2943E971735F
manager: dansimp
---

# Start-Dtc

## SYNOPSIS
Starts the DTC instance.

## SYNTAX

```
Start-Dtc [-CimSession <CimSession[]>] [-DtcName <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Start-Dtc** cmdlet starts the Distributed Transaction Coordinator (DTC) instance that the **DtcName** parameter specifies.

## EXAMPLES

### Example 1: Start the local DTC instance
```
PS C:\>Start-Dtc -DtcName "Local"
```

This command starts the local DTC instance.

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
Specifies the DTC instance to start.
If you do not specify this parameter, or if you specify a value of Local, this cmdlet starts the local DTC instance.

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

[Get-Dtc](./Get-Dtc.md)

[Install-Dtc](./Install-Dtc.md)

[Stop-Dtc](./Stop-Dtc.md)

[Test-Dtc](./Test-Dtc.md)

[Uninstall-Dtc](./Uninstall-Dtc.md)


---
external help file: MsDTC_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: BF3DAE79-8988-4920-AE2E-58BF5E70E5A9
manager: dansimp
---

# Set-DtcAdvancedHostSetting

## SYNOPSIS
Sets the DTC host level properties in the registry.

## SYNTAX

```
Set-DtcAdvancedHostSetting [-CimSession <CimSession[]>] [-Subkey <String>] [-ThrottleLimit <Int32>]
 -Name <String> [-Type] -Value <String>
```

## DESCRIPTION
The **Set-DtcAdvancedHostSetting** cmdlet sets the Distributed Transaction Coordinator (DTC) host level properties in the registry.

## EXAMPLES

### Example 1: Specify a diagnostic trace file path
```
PS C:\> Set-DtcAdvancedHostSetting -Name "TraceFilePath" -Type "SZ" -Value "C:\Temp" -SubKey "Tracing\Output"
```

This command specifies a diagnostic trace file path.

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

### -Name
Specifies the name of the property to set.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Subkey
Specifies the subkey name for the property to set.

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

### -Type
Specifies the registry type of the property to store.
The acceptable values for this parameter are:

- SZ
- DWORD

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: String, DWORD

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value
Specifies the value of the property to store.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-DtcAdvancedHostSetting](./Get-DtcAdvancedHostSetting.md)


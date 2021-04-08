---
author: Kateyanne
external help file: MsDTC_Cmdlets.xml
manager: dansimp
Module Name: MsDTC
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/msdtc/install-dtc?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Install-Dtc

## SYNOPSIS
Installs the local transactions coordinator.

## SYNTAX

```
Install-Dtc [-CimSession <CimSession[]>] [-LogPath <String>] [-StartType] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Install-Dtc** cmdlet installs the local transactions coordinator.

## EXAMPLES

### Example 1: Install DTC
```
PS C:\>Install-Dtc -LogPath "C:\log" -StartType "AutoStart"
```

This command installs local DTC.
The command specifies AutoStart as the start type.

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

### -LogPath
Specifies the path of the log file.
If not specified, this cmdlet uses the default log path.

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

### -StartType
Specifies the start type for the local transactions coordinator.
The acceptable values for this parameter are:

- AutoStart
- DemandStart
- Disabled

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: BootStart, SystemStart, AutoStart, DemandStart, Disabled

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

[Start-Dtc](./Start-Dtc.md)

[Stop-Dtc](./Stop-Dtc.md)

[Test-Dtc](./Test-Dtc.md)

[Uninstall-Dtc](./Uninstall-Dtc.md)


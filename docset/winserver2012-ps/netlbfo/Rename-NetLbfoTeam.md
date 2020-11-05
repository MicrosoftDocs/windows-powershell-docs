---
external help file: NetLbfo_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 87EAA7C7-9042-49F9-8970-E9C29D393F8B
manager: dansimp
---

# Rename-NetLbfoTeam

## SYNOPSIS
Renames a NIC team.

## SYNTAX

```
Rename-NetLbfoTeam [-Name] <String> [-NewName] <String> [-AsJob] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Rename-NetLbfoTeam** cmdlet renames the specified NIC team to the specified new name.
Also updates the team interface names accordingly, if they use default values.

You need administrator privileges to use **Rename-NetLbfoTeam**.

## EXAMPLES

### Example 1: Rename a team
```
PS C:\>Rename -NetLbfoTeam -Name Team1 -NewName TeamA
```

This command renames the team named Team1 to TeamA.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the NIC team to rename.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewName
Specifies the new name of the NIC team.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

### None
This cmdlet takes no input objects.

## OUTPUTS

### MSFT_NetLbfoTeam
If the **PassThru** parameter is specified, this cmdlet produces newly renamed team object.
If the **PassThru** parameter is not specified, there is no output.

## NOTES

## RELATED LINKS

[New-NetLbfoTeam](./New-NetLbfoTeam.md)

[Get-NetLbfoTeam](./Get-NetLbfoTeam.md)

[Set-NetLbfoTeam](./Set-NetLbfoTeam.md)

[Remove-NetLbfoTeam](./Remove-NetLbfoTeam.md)


---
author: Kateyanne
external help file: NetLbfo_Cmdlets.xml
manager: dansimp
Module Name: NetLbfo
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/netlbfo/set-netlbfoteamnic?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NetLbfoTeamNic

## SYNOPSIS
Sets a new VLAN id on a team interface, or restores the interface to Default mode.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NetLbfoTeamNic [[-Name] <String[]>] [[-Team] <String[]>] [-AsJob] [-CimSession <CimSession[]>] [-Default]
 [-PassThru] [-ThrottleLimit <Int32>] [-VlanID <UInt32>]
```

### UNNAMED_PARAMETER_SET_2
```
Set-NetLbfoTeamNic [-AsJob] [-CimSession <CimSession[]>] [-Default] [-PassThru]
 [-TeamOfTheTeamNic <CimInstance>] [-ThrottleLimit <Int32>] [-VlanID <UInt32>]
```

### UNNAMED_PARAMETER_SET_3
```
Set-NetLbfoTeamNic [-AsJob] [-CimSession <CimSession[]>] [-Default] [-PassThru] [-ThrottleLimit <Int32>]
 [-VlanID <UInt32>] -InputObject <CimInstance[]>
```

## DESCRIPTION
The **Set-NetLbfoTeamNic** cmdlet sets the optional values on a team interface.
Only the team interface that was created when the team was created can be set to Default mode.

You need administrator privileges to use **Set-NetLbfoTeamNic**.

## EXAMPLES

### Example 1: Set the VLAN ID
```
PS C:\>Set-NetLbfoTeamNIC -Name "Team1 - VlanID 42"   -VlanID   15
```

This command modifies the current VLAN ID of the team interface named "Team1 - VLAN 42" to the specified VLAN ID 15.

### Example 2: Set the VLAN ID of the primary interface to 5, and then revert it to default
```
PS C:\>Set-NetLbfoTeamNic -Name Team1 -VlanID 5


This command changes the primary team interface, "Team1 - VLAN 5" to default mode.
PS C:\>Set-NetLbfoTeamNic -Name "Team1 - VLAN 5" -Default
```

This command sets the VLAN ID of the primary team interface named Team1 to 5.

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

### -Default
Indicates that the team interface should be restored to Default mode.

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

### -InputObject
Specifies the object which contains the team interface to modify.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the team interface to modify.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -Team
Specifies the name of the NIC team for which to modify the team interface.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -TeamOfTheTeamNic
Specifies the network adapter team object whose team interfaces are to be modified.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -VlanID
Specifies the VLAN ID of the team interface to modify.

```yaml
Type: UInt32
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

### None
By default, this cmdlet produces no output.

If the **PassThru** parameter is specified, the cmdlet returns the newly modified **MSFT_NetLbfoTeamNic** object.

## NOTES

## RELATED LINKS

[Add-NetLbfoTeamNic](./Add-NetLbfoTeamNic.md)

[Get-NetLbfoTeamNic](./Get-NetLbfoTeamNic.md)

[Remove-NetLbfoTeamNic](./Remove-NetLbfoTeamNic.md)


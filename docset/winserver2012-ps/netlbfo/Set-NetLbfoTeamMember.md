---
external help file: NetLbfo_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: CF89FA2A-ECCA-406A-A43B-4D94D452724D
manager: dansimp
---

# Set-NetLbfoTeamMember

## SYNOPSIS
Sets the role of a member network adapter in a NIC team.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NetLbfoTeamMember [[-Name] <String[]>] [[-Team] <String[]>] [-AdministrativeMode <AdminModes>] [-AsJob]
 [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Set-NetLbfoTeamMember [-AdministrativeMode <AdminModes>] [-AsJob] [-CimSession <CimSession[]>] [-PassThru]
 [-ThrottleLimit <Int32>] -InputObject <CimInstance[]>
```

### UNNAMED_PARAMETER_SET_3
```
Set-NetLbfoTeamMember [-AdministrativeMode <AdminModes>] [-AsJob] [-CimSession <CimSession[]>] [-PassThru]
 [-TeamOfTheMember <CimInstance>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Set-NetLbfoTeamMember** cmdlet sets the role of a specified network adapter (team member) in the NIC team.
You can specify the team member either by specifying the name or by specifying the network adapter object retrieved using the Get-NetLbfoTeamMember cmdlet.

You need administrative privileges to use **Set-NetLbfoTeamMember**.

## EXAMPLES

### Example 1: Set the team member role
```
PS C:\>Set-NetLbfoTeamMember -Name "NIC4" -AdministrativeMode Standby
```

This command sets the administrative mode of the specified team member named NIC4 to Standby.

## PARAMETERS

### -AdministrativeMode
Specifies the administrative mode of the network adapter to modify.

You can specify one of the following two administrative modes:

**Active**: Allows the team member to participate in the NIC team.
By default, the role of the team member is Active.

**Standby**: Places the member in a standby state where it does not participate in the team.
The team member will be automatically moved to Active state if any other member of the team fails.

At most one member in a team can be in Standby mode.

```yaml
Type: AdminModes
Parameter Sets: (All)
Aliases: am

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -InputObject
Specifies the object which contains the team member to modify.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the team member to modify.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: ifAlias, InterfaceAlias

Required: False
Position: 1
Default value: All members adapters across all teams
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
Specifies the name of the NIC team which contains the network adapter to modify.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 2
Default value: All teams on the host
Accept pipeline input: False
Accept wildcard characters: True
```

### -TeamOfTheMember
Specifies the NIC team object whose associated member objects are to be modified.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_3
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

## INPUTS

### None
This cmdlet takes no input objects.

## OUTPUTS

### MSFT_NetLbfoTeamMember
By default, this cmdlet produces no output.

If the **PassThru** parameter is specified, the cmdlet returns the updated **MSFT_NetLbfoTeamMember** object.

## NOTES

## RELATED LINKS

[Get-NetLbfoTeamMember](./Get-NetLbfoTeamMember.md)

[Add-NetLbfoTeamMember](./Add-NetLbfoTeamMember.md)

[Remove-NetLbfoTeamMember](./Remove-NetLbfoTeamMember.md)


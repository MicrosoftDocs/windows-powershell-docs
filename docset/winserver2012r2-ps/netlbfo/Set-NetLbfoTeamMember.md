---
external help file: MSFT_NetLbfoTeamMember.cdxml-help.xml
Module Name: NetLbfo
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/netlbfo/set-netlbfoteammember?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetLbfoTeamMember
---

# Set-NetLbfoTeamMember

## SYNOPSIS
Sets the role of a member network adapter in a NIC team.

## SYNTAX

### ByNameAndOrTeam (Default)
```
Set-NetLbfoTeamMember [[-Name] <String[]>] [[-Team] <String[]>] [-AdministrativeMode <AdminModes>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByTeamOfTheMember
```
Set-NetLbfoTeamMember [-TeamOfTheMember <CimInstance>] [-AdministrativeMode <AdminModes>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetLbfoTeamMember -InputObject <CimInstance[]> [-AdministrativeMode <AdminModes>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetLbfoTeamMember** cmdlet sets the role of a specified network adapter (team member) in the NIC team.
You can specify the team member either by specifying the name or by specifying the network adapter object retrieved using the Get-NetLbfoTeamMember cmdlet.

You need administrative privileges to use **Set-NetLbfoTeamMember**.

## EXAMPLES

### Example 1: Set the team member role
```
PS C:\> Set-NetLbfoTeamMember -Name "NIC4" -AdministrativeMode Standby
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
Accepted values: Active, Standby

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the object which contains the team member to modify.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
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
Parameter Sets: ByNameAndOrTeam
Aliases: ifAlias, InterfaceAlias

Required: False
Position: 0
Default value: All members adapters across all teams
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
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
Parameter Sets: ByNameAndOrTeam
Aliases: 

Required: False
Position: 1
Default value: All teams on the host
Accept pipeline input: False
Accept wildcard characters: False
```

### -TeamOfTheMember
Specifies the NIC team object whose associated member objects are to be modified.

```yaml
Type: CimInstance
Parameter Sets: ByTeamOfTheMember
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

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


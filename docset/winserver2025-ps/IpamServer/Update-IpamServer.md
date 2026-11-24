---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamServer.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/update-ipamserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Update-IpamServer
---

# Update-IpamServer

## SYNOPSIS
Updates an IPAM server following an operating system upgrade.

## SYNTAX

```
Update-IpamServer [-DeleteSystemCheckFailureRows] [-Force] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Update-IpamServer** cmdlet updates an IP Address Management (IPAM) server following an operating system upgrade.
IPAM binaries and schema files are made available as a part of an upgrade.
An error occurs if there is no update available.

As part of an IPAM server update, this cmdlet performs the following steps:

- Applies IPAM schema updates.
  The cmdlet performs data and schema validation of the existing IPAM database, and returns an error if the validation fails.
  A log is generated on the server in the %SystemDrive%\Windows\System32\IPAM\logs folder.
  If you specify the *DeleteSystemCheckFailureRows* parameter, the cmdlet proceeds to automatically delete the error rows.

- Completes any required data format transformation.
  This will not result in any loss of existing data.

- Applies changes in security groups and roles.

No changes are made to any existing user configuration, such as adding users to a security group.
Any customizations to IPAM task schedules are retained.
In case of an error, any changes will be reverted.

## EXAMPLES

### Example 1: Update an existing IPAM installation
```
PS C:\> Update-IpamServer
Upgrading IPAM Server.

 As a part of upgrade, any changes in IPAM Server settings & configuration will be applied. Any requisite changes to database schema changes will be made. Do you want to continue?

[Y]Yes [N]No [S]Suspend [?]Help (default is "Y"): Y
```

This command updates an existing IPAM installation following an operating system upgrade.
If there are system check errors, the cmdlet terminates and generates a log file in the %System Drive%\System 32\IPAM\Logs folder.

### Example 2: Update an IPAM installation and delete system check failure rows
```
PS C:\> Update-IpamServer -DeleteSystemCheckFailureRows
Upgrading IPAM Server.

 As a part of upgrade, any changes in IPAM Server settings & configuration will be applied. Any requisite changes to database schema changes will be made. Do you want to continue?

[Y]Yes [N]No [S]Suspend [?]Help (default is "Y"): Y
```

This command updates an existing IPAM installation after an operating system upgrade.
The command does not terminate due to system check errors, and it deletes conflicting errors in the IPAM database.
The command generates a log in the %System Drive%\System 32\IPAM\Logs folder.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -DeleteSystemCheckFailureRows
Indicates that the cmdlet automatically deletes errors rows when it validates data and schema for an existing IPAM database.
An error occurs if the system check fails.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: DeleteErrorRows

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[IP Address Management (IPAM) Server Cmdlets in Windows PowerShell](./ipamserver.md)


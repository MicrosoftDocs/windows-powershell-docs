---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WdsDriverPackage_v1.0.cdxml-help.xml
Module Name: WDS
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/wds/import-wdsdriverpackage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-WdsDriverPackage
---

# Import-WdsDriverPackage

## SYNOPSIS
Imports a driver package into the Windows Deployment Services driver store.

## SYNTAX

```
Import-WdsDriverPackage -Path <String> [-GroupName <String>] [-DisplayName <String>]
 [-Architecture <Architecture>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Import-WdsDriverPackage** cmdlet imports a driver package into the Windows Deployment Services driver store.
Specify the .inf file for the driver package to import.

You can specify a display name for the driver package.
You can assign it to a driver group.
If you want to assign a driver package to a group later, use the Add-WdsDriverPackage cmdlet.
A client must have access to at least one group that a driver package belongs to in order to install it.

If the package contains drivers for multiple architectures, you can specify a single architecture.
If you do not specify an architecture, the cmdlet adds all the architectures.

## EXAMPLES

### Example 1: Import a driver package for the x64 architecture
```
PS C:\> Import-WdsDriverPackage -Path "D:\Drivers\Fabrikam.inf" -Architecture X64 -DisplayName "Fabrikam Device Driver (x64)" -GroupName "Drivers for Fabrikam Devices"
```

This command imports a driver package for the x64 architecture into the Windows Deployment Services driver store from the specified .inf file.
The command specifies a display name for the driver package and assigns the package to the Drivers for Fabrikam Devices group.

## PARAMETERS

### -Architecture
Specifies an architecture.
This is the architecture of the driver package to add to the server.
If you do not specify this parameter, the cmdlet includes all the architectures it finds.
The acceptable values for this parameter are:

- Arm
- Ia64
- X64
- X86

```yaml
Type: Architecture
Parameter Sets: (All)
Aliases:
Accepted values: X86, Ia64, X64, Arm

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
Runs the cmdlet as a background job.
Use this parameter to run commands that take a long time to complete.
 The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.
 For more information about Windows PowerShell® background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -DisplayName
Specifies a display name for the driver package.
If you do not supply a display name, the cmdlet creates one based on the driver name and architecture.

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

### -GroupName
Specifies the name of a driver group.
The cmdlet adds the driver package to this group.

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

### -Path
Specifies an absolute path.
This is the path an .inf file.
The cmdlet imports the driver package from this file.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_WdsDriverPackage

## NOTES

## RELATED LINKS

[Add-WdsDriverPackage](./Add-WdsDriverPackage.md)

[Disable-WdsDriverPackage](./Disable-WdsDriverPackage.md)

[Enable-WdsDriverPackage](./Enable-WdsDriverPackage.md)

[Get-WdsDriverPackage](./Get-WdsDriverPackage.md)

[Remove-WdsDriverPackage](./Remove-WdsDriverPackage.md)


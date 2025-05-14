---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WdsDriverPackage_v1.0.cdxml-help.xml
Module Name: WDS
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/wds/disable-wdsdriverpackage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WdsDriverPackage
---

# Disable-WdsDriverPackage

## SYNOPSIS
Disables a driver package in the Windows Deployment Services driver store.

## SYNTAX

### DriverPackageId
```
Disable-WdsDriverPackage -Id <Guid> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### DriverPackageName
```
Disable-WdsDriverPackage -Name <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Disable-WdsDriverPackage** cmdlet disables a driver package in the Windows Deployment Services driver store.
Specify a driver package by its unique name or ID.

While a driver package is disabled, clients that request the package cannot install it.

Use the Enable-WdsDriverPackage cmdlet to enable a driver package.
Use the Remove-WdsDriverPackage cmdlet to delete a driver package from the driver store.

## EXAMPLES

### Example 1: Disable a driver package by using a package ID
```
PS C:\> Disable-WdsDriverPackage -Id 32d78628-07fb-4e18-adc4-f0ecf8b41bbe
```

This command disables the driver package that has the specified ID.

### Example 2: Disable a driver package by name
```
PS C:\>Disable-WdsDriverPackage -Name "Fabrikam Device Driver (x64)"
```

This command disables the driver package named Fabrikam Device Driver (x64).
This name must be unique.

## PARAMETERS

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

### -Id
Specifies an ID.
This is the ID of the driver package to disable.

```yaml
Type: Guid
Parameter Sets: DriverPackageId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name.
This is the unique name of the driver package.
If this name is not unique, specify the driver package ID, instead, by using the *Id* parameter.

```yaml
Type: String
Parameter Sets: DriverPackageName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[Enable-WdsDriverPackage](./Enable-WdsDriverPackage.md)

[Get-WdsDriverPackage](./Get-WdsDriverPackage.md)

[Import-WdsDriverPackage](./Import-WdsDriverPackage.md)

[Remove-WdsDriverPackage](./Remove-WdsDriverPackage.md)


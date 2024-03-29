---
external help file: MSFT_WdsDriverPackage_v1.0.cdxml-help.xml
Module Name: WDS
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/wds/get-wdsdriverpackage?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WdsDriverPackage
---

# Get-WdsDriverPackage

## SYNOPSIS
Gets properties of driver packages from the Windows Deployment Services driver store.

## SYNTAX

### DriverPackageId
```
Get-WdsDriverPackage -Id <Guid> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### DriverPackageName
```
Get-WdsDriverPackage [-Name <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-WdsDriverPackage** cmdlet gets properties of driver packages from the Windows Deployment Services driver store.
Specify a driver package by its unique name or ID.
If you do not specify a name or ID, the cmdlet gets all driver packages in the store.

## EXAMPLES

### Example 1: Get a driver package by using a package ID
```
PS C:\> Get-WdsDriverPackage -Id 32d78628-07fb-4e18-adc4-f0ecf8b41bbe
```

This command gets the driver package that has the specified ID.

### Example 2: Get a driver package by name
```
PS C:\>Get-WdsDriverPackage -Name "Fabrikam Device Driver (x64)"
```

This command gets the driver package named Fabrikam Device Driver (x64).
This name must be unique.

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
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies an ID.
This is the ID of the driver package to get.

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
If this name is not unique, specify the driver package ID, instead, by using the **Id** parameter.

```yaml
Type: String
Parameter Sets: DriverPackageName
Aliases: 

Required: False
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_WdsDriverPackage

## NOTES

## RELATED LINKS

[Add-WdsDriverPackage](./Add-WdsDriverPackage.md)

[Disable-WdsDriverPackage](./Disable-WdsDriverPackage.md)

[Enable-WdsDriverPackage](./Enable-WdsDriverPackage.md)

[Import-WdsDriverPackage](./Import-WdsDriverPackage.md)

[Remove-WdsDriverPackage](./Remove-WdsDriverPackage.md)


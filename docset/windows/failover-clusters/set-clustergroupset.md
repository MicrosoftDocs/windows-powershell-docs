---
author: brianlic-msft
description: 
external help file: ClusterCollection.cdxml-help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-ClusterGroupSet
ms.assetid: AB00AE4C-DEDD-43EB-AE9D-201BA5D730CF
---

# Set-ClusterGroupSet

## SYNOPSIS
Updates a cluster group set.

## SYNTAX

### Query (cdxml) (Default)
```
Set-ClusterGroupSet [[-Name] <String[]>] [-StartupSetting <StartupSettingType>] [-StartupCount <UInt32>]
 [-IsGlobal <Boolean>] [-StartupDelay <UInt32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-ClusterGroupSet -InputObject <CimInstance[]> [-StartupSetting <StartupSettingType>]
 [-StartupCount <UInt32>] [-IsGlobal <Boolean>] [-StartupDelay <UInt32>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Set-ClusterGroupSet** cmdlet updates a cluster group set.
To update the groups in the set, use the Add-ClusterGroupToSet and Remove-ClusterGroupFromSet cmdlets.
To update the dependencies, use the Add-ClusterGroupSetDependency and Remove-ClusterGroupSetDependency cmdlets.

## EXAMPLES

### Example 1: Change a group set to the specified startup setting
```
PS C:\>Set-ClusterGroupSet -Name "Set002" -StartupSetting Online
```

This command changes the group set named Set002 to the startup setting Online.

## PARAMETERS

### -AsJob
{{Fill AsJob Description}}

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

### -InputObject
{{Fill InputObject Description}}

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

### -IsGlobal
Indicates that this cmdlet sets the group set as global.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the group set.

```yaml
Type: String[]
Parameter Sets: Query (cdxml)
Aliases: 

Required: False
Position: 0
Default value: None
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

### -StartupCount
Specifies the number of groups to meet the ready setting.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: Count

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartupDelay
Specifies the delay to use after reaching the ready state, in seconds.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: Delay

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartupSetting
Specifies the startup setting when the set is deemed ready.
When delay it is when the groups specified in the *StartupCount* parameter are in pending in addition to the *StartupDelay* parameter.
If it is online it is when *StartupCount* groups reach online in addition to the delay.

The acceptable values for this parameter are: Delay or Online.

```yaml
Type: StartupSettingType
Parameter Sets: (All)
Aliases: StartupDelayTrigger
Accepted values: Delay, Online

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-ClusterGroupSet](./Get-ClusterGroupSet.md)

[New-ClusterGroupSet](./New-ClusterGroupSet.md)

[Remove-ClusterGroupSet](./Remove-ClusterGroupSet.md)


---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FSRMClassificationPropertyDefinition.cdxml-help.xml
Module Name: FileServerResourceManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/new-fsrmclassificationpropertydefinition?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-FsrmClassificationPropertyDefinition
---

# New-FsrmClassificationPropertyDefinition

## SYNOPSIS
Creates a classification property definition.

## SYNTAX

```
New-FsrmClassificationPropertyDefinition [-Name] <String> [-DisplayName <String>] [-Description <String>]
 -Type <PropertyDefinitionTypeEnum> [-PossibleValue <CimInstance[]>] [-Parameters <String[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-FsrmClassificationPropertyDefinition** cmdlet creates a classification property definition on the server.
You create a property definition to define the property that you want to use to classify files.
One or more classification rules can specify the property.
The File Server Resource Manager (FSRM) server limits the number of property definitions to 100.

## EXAMPLES

### Example 1: Create a YesNo classification property definition
```
PS C:\> New-FsrmClassificationPropertyDefinition -Name "ClassProp01" -DisplayName "Central Level Definitions" -Type YesNo
```

This command creates a YesNo classification property definition that named ClassProp01 with a display name of Central Level Definitions.

### Example 2: Create an ordered list classification property definition
```
PS C:\> New-FsrmClassificationPropertyDefinition -Name "Impact" -Type OrderedList -PossibleValue @("High","Moderate","Low")
```

This command creates an OrderedList classification property definition named Impact, and specifies the possible values for the property.

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

### -Description
Specifies a description for the property definition.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisplayName
Specifies an optional name for the property.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the property.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Parameters
Specifies an array of strings using the format \<name\>=\<value\>.
The File Classification Infrastructure and other management tools use these parameters.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PossibleValue
Specifies an array of property values.
The default value is an empty list.
You can use the **New-FsrmClassificationPropertyValue** cmdlet to create possible values for a classification property.

```yaml
Type: CimInstance[]
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

### -Type
Specifies the type of the classification property definition.
The acceptable values for this parameter are:

- OrderedList
- MultiChoice
- SingleChoice
- String
- MultiString
- Integer
- YesNo
- DateTime

```yaml
Type: PropertyDefinitionTypeEnum
Parameter Sets: (All)
Aliases:
Accepted values: OrderedList, MultiChoice, SingleChoice, String, MultiString, Integer, YesNo, DateTime

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System.String

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.PropertyDefinitionTypeEnum

### System.String[]

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

[Get-FsrmClassificationPropertyDefinition](./Get-FsrmClassificationPropertyDefinition.md)

[New-FsrmClassificationPropertyValue](./New-FsrmClassificationPropertyValue.md)

[Remove-FsrmClassificationPropertyDefinition](./Remove-FsrmClassificationPropertyDefinition.md)

[Set-FsrmClassificationPropertyDefinition](./Set-FsrmClassificationPropertyDefinition.md)

[Update-FsrmClassificationPropertyDefinition](./Update-FsrmClassificationPropertyDefinition.md)


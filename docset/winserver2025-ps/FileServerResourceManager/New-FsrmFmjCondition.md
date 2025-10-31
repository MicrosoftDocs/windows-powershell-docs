---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FSRMFmjCondition.cdxml-help.xml
Module Name: FileServerResourceManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/new-fsrmfmjcondition?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-FsrmFmjCondition
---

# New-FsrmFmjCondition

## SYNOPSIS
Creates a file management property condition object.

## SYNTAX

```
New-FsrmFmjCondition [-Property] <String> [-Condition] <FmjConditionTypeEnum> [-Value <String>]
 [-DateOffset <Int32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-FsrmFmjCondition** cmdlet creates a file management condition object.
A file management condition object defines a condition that determines if a file management job acts on a file.

## EXAMPLES

### Example 1: Create a property condition
```
PS C:\> New-FsrmFmjCondition -Property "PII" -Condition Equal -Value "1"
```

This command creates a property condition that verifies that a file has a PII classification property set to true.

### Example 2: Create a condition based on a file classification
```
PS C:\> New-FsrmFmjCondition -Property "DatePublished" -Condition Equal -Value "File.DateLastModified"
```

This command creates a condition based on the file's classification.
The command verifies that a file has a DatePublished classification property (of type DateTime) set to the file's Last Modified timestamp.

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

### -Condition
Specifies the condition of the property that must be matched for the file management job.
The acceptable values for this parameter are:

- Equal
- NotEqual
- GreaterThan
- LessThan
- Contain
- Exist
- NotExist
- StartWith
- EndWith
- ContainedIn
- PrefixOf
- SuffixOf
- MatchesPattern

```yaml
Type: FmjConditionTypeEnum
Parameter Sets: (All)
Aliases:
Accepted values: Equal, NotEqual, GreaterThan, LessThan, Contain, Exist, NotExist, StartWith, EndWith, ContainedIn, PrefixOf, SuffixOf, MatchesPattern

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -DateOffset
Specifies an offset from the *Value* parameter for DateTime values.
The default value is 0.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Property
Specifies the property to compare for the condition.
Specify one of the following values:

- The name of a classification property definition on the server.
(Do not specify the display name of the property definition.)
- The string File.Name
- The string File.DateCreated
- The string File.DateLastModified
- The string File.DateLastAccessed

The value of this parameter limits the values that other parameters to the cmdlet can accept as follows:

File.Name:

- You can set the *Condition* parameter only to MatchesPattern.
- The *Value* parameter must contain a semi-colon separated list of wildcard patterns.
- You cannot specify the *DateOffset* parameter.

File.DateCreated, File.DateLastModified, or File.DateLastAccessed:

- You can set the *Condition* parameter only to LessThan or Equal.
- If you specify the *DateOffset* parameter, you can set the *Value* parameter to one of the following: File.DateCreated, File.DateLastModified, File.DateLastAccessed, or Date.Now.
- If you do not specify the *DateOffset* parameter, you can set the *Value* parameter to a FileTime value.

The name of a classification property definition whose Type is DateTime:

- You can set the *Condition* parameter to Exist, NotExist, Equal, NotEqual, LessThan, GreaterThan.
- If you specify the *DateOffset* parameter, the *Value* parameter can contain one of the following: File.DateCreated, File.DateLastModified, File.DateLastAccessed, or Date.Now.
- If you do not specify the *DateOffset* parameter, the *Value* parameter can contain a FileTime value.

The name of a classification property definition whose Type is not DateTime:

- You cannot specify the *DateOffset* parameter.
- If the *Condition* parameter is Exist or NotExist, you cannot specify the *Value* parameter.
- If the Type is Integer, you can set the *Condition* parameter to Equal, NotEqual, Exist, NotExist, LessThan, GreaterThan.
- If the Type is String, you can set the *Condition* parameter to Equal, NotEqual, Exist, NotExist, Contains, IsContainedIn, LessThan, GreaterThan, StartsWith, EndsWith, PrefixOf, SuffixOf.
- If the Type is YesNo, you can set the *Condition* parameter to Equal, NotEqual, Exist, NotExist.
- If the Type is OrderedList, you can set the *Condition* parameter to Equal, NotEqual, Exist, NotExist, LessThan, GreaterThan.
- If the Type is SingleChoice, you can set the *Condition* parameter to Equal, NotEqual, Exist, NotExist.
- If the Type is MultiChoice, you can set the *Condition* parameter to Equal, NotEqual, Exist, NotExist, Contains.
- If the Type is MultiString, you can set the *Condition* parameter to Equal, NotEqual, Exist, NotExist, Contains.

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

### -Value
Specifies a name of a file condition property value.
Do not specify this parameter if you specify Exists or NotExist for the *Condition* parameter.
If you specify the name of a DateTime property, specify the *DateOffset* parameter.

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

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.FmjConditionTypeEnum

### System.Int32

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

## NOTES

## RELATED LINKS

[Get-FsrmClassificationPropertyDefinition](./Get-FsrmClassificationPropertyDefinition.md)


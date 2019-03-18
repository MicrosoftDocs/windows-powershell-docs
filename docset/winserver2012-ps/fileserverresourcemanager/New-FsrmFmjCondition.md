---
external help file: FSRM_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: CC36DC38-518C-430A-9A23-45B7049854E8
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# New-FsrmFmjCondition

## SYNOPSIS
Creates a file management property condition object.

## SYNTAX

```
New-FsrmFmjCondition [-Property] <String> [-Condition] <FmjConditionTypeEnum> [-AsJob]
 [-CimSession <CimSession[]>] [-DateOffset <Int32>] [-ThrottleLimit <Int32>] [-Value <String>] [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **New-FsrmFmjCondition** cmdlet creates a file management condition object.
A file management condition object defines a condition that determines if a file management job acts on a file.

## EXAMPLES

### Example 1: Create a property condition
```
PS C:\>New-FsrmFmjCondition -Property "PII" -Condition Equal -Value "1"
```

This command creates a property condition that verifies that a file has a PII classification property set to true.

### Example 2: Create a condition based on a file classification
```
PS C:\>New-FsrmFmjCondition -Property "DatePublished" -Condition Equal -Value "File.DateLastModified"
```

This command creates a condition based on the file's classification.
The command verifies that a file has a DatePublished classification property (of type DateTime) set to the file's Last Modified timestamp.

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

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DateOffset
Specifies an offset from the **Value** parameter for DateTime values.
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
- You can set the **Condition** parameter only to MatchesPattern.
- The **Value** parameter must contain a semi-colon separated list of wildcard patterns.
- You cannot specify the **DateOffset** parameter.

File.DateCreated, File.DateLastModified, or File.DateLastAccessed:
- You can set the **Condition** parameter only to LessThan or Equal.
- If you specify the **DateOffset** parameter, you can set the **Value** parameter to one of the following: File.DateCreated, File.DateLastModified, File.DateLastAccessed, or Date.Now.
- If you do not specify the **DateOffset** parameter, you can set the **Value** parameter to a FileTime value.

The name of a classification property definition whose Type is DateTime:
- You can set the **Condition** parameter to Exist, NotExist, Equal, NotEqual, LessThan, GreaterThan.
- If you specify the **DateOffset** parameter, the **Value** parameter can contain one of the following: File.DateCreated, File.DateLastModified, File.DateLastAccessed, or Date.Now.
- If you do not specify the **DateOffset** parameter, the **Value** parameter can contain a FileTime value.

The name of a classification property definition whose Type is not DateTime:
- You cannot specify the **DateOffset** parameter.
- If the **Condition** parameter is Exist or NotExist, you cannot specify the **Value** parameter.
- If the Type is Integer, you can set the **Condition** parameter to Equal, NotEqual, Exist, NotExist, LessThan, GreaterThan.
- If the Type is String, you can set the **Condition** parameter to Equal, NotEqual, Exist, NotExist, Contains, IsContainedIn, LessThan, GreaterThan, StartsWith, EndsWith, PrefixOf, SuffixOf.
- If the Type is YesNo, you can set the **Condition** parameter to Equal, NotEqual, Exist, NotExist.
- If the Type is OrderedList, you can set the **Condition** parameter to Equal, NotEqual, Exist, NotExist, LessThan, GreaterThan.
- If the Type is SingleChoice, you can set the **Condition** parameter to Equal, NotEqual, Exist, NotExist.
- If the Type is MultiChoice, you can set the **Condition** parameter to Equal, NotEqual, Exist, NotExist, Contains.
- If the Type is MultiString, you can set the **Condition** parameter to Equal, NotEqual, Exist, NotExist, Contains.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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
Do not specify this parameter if you specify Exists or NotExist for the **Condition** parameter.
If you specify the name of a DateTime property, specify the **DateOffset** parameter.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMFMJCondition

## NOTES

## RELATED LINKS

[Get-FsrmClassificationPropertyDefinition](./Get-FsrmClassificationPropertyDefinition.md)


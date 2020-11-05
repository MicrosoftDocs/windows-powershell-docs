---
external help file: FSRM_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 93C4A867-5C2A-43F5-9B9F-4F2684CCED81
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Set-FsrmClassificationRule

## SYNOPSIS
Changes configuration settings of classification rules.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-FsrmClassificationRule [-Name] <String[]> [-AsJob] [-CimSession <CimSession[]>]
 [-ClassificationMechanism <String>] [-ContentRegularExpression <String[]>] [-ContentString <String[]>]
 [-ContentStringCaseSensitive <String[]>] [-Description <String>] [-Disabled] [-Flags <RuleFlagsEnum[]>]
 [-Namespace <String[]>] [-Parameters <String[]>] [-PassThru] [-Property <String>] [-PropertyValue <String>]
 [-ReevaluateProperty <RuleReevaluatePropertyEnum>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-FsrmClassificationRule [-AsJob] [-CimSession <CimSession[]>] [-ClassificationMechanism <String>]
 [-ContentRegularExpression <String[]>] [-ContentString <String[]>] [-ContentStringCaseSensitive <String[]>]
 [-Description <String>] [-Disabled] [-Flags <RuleFlagsEnum[]>] [-Namespace <String[]>]
 [-Parameters <String[]>] [-PassThru] [-Property <String>] [-PropertyValue <String>]
 [-ReevaluateProperty <RuleReevaluatePropertyEnum>] [-ThrottleLimit <Int32>] -InputObject <CimInstance[]>
 [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-FsrmClassificationRule** cmdlet changes configuration settings of one or more classification rules.

## EXAMPLES

### Example 1: Change a classification rule
```
PS C:\>Set-FsrmClassificationRule -Name "Find confidential files" -ContentString @("confidential", "secret")
```

This command changes the "Find confidential files" rule to search for the strings "confidential" and "secret".

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

### -ClassificationMechanism
Specifies the name of a valid classification mechanism available on the server for assigning the property value.

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

### -ContentRegularExpression
Specifies an array of regular expressions for pattern matching.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContentString
Specifies an array of strings for the content classifier to search for.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContentStringCaseSensitive
Specifies an array of content sensitive strings for the content classifier to search for.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the classification rule.

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

### -Disabled
Indicates that the classification rule is disabled.

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

### -Flags
Specifies an array of flags that define the possible states of the rule.

```yaml
Type: RuleFlagsEnum[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

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
Specifies an array of names of classification rules.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Namespace
Specifies an array of namespaces where the rule is applied. 
Each value must be either a value of the FolderType property defined on the server (in the format "\[Folder type property name=\<value\>\]") or a static path.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Accept pipeline input: False
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

### -Property
Specifies the name of a classification property definition to set.
Specify the value of the **Name** property in an **FsrmClassificationPropertyDefinition** object.

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

### -PropertyValue
Specifies the property value that the rule will assign.
The property value that you set must be a valid value supported by the classification mechanism that you specify in the **ClassificationMechanism** parameter.

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

### -ReevaluateProperty
Specifies the evaluation policy of the rule.
The acceptable values for this parameter are:
- Never: Assign values to properties only if that property does not already have a value for the file.
- Overwrite: Reclassify files when the files change and overwrite this property.
- Aggregate: Reclassify files when the files change and aggregate the new value for the property with the existing value.

```yaml
Type: RuleReevaluatePropertyEnum
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Never
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMClassificationRule

## NOTES

## RELATED LINKS

[Get-FsrmClassificationRule](./Get-FsrmClassificationRule.md)

[New-FsrmClassificationRule](./New-FsrmClassificationRule.md)

[Remove-FsrmClassificationRule](./Remove-FsrmClassificationRule.md)

[Get-FsrmClassificationPropertyDefinition](./Get-FsrmClassificationPropertyDefinition.md)


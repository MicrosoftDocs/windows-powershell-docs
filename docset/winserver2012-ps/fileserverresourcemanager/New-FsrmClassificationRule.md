---
external help file: FSRM_Cmdlets.xml
Module Name: FileServerResourceManager
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/new-fsrmclassificationrule?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-FsrmClassificationRule

## SYNOPSIS
Creates an automatic classification rule.

## SYNTAX

```
New-FsrmClassificationRule [-Name] <String> [-AsJob] [-CimSession <CimSession[]>]
 [-ContentRegularExpression <String[]>] [-ContentString <String[]>] [-ContentStringCaseSensitive <String[]>]
 [-Description <String>] [-Disabled] [-Parameters <String[]>] [-PropertyValue <String>]
 [-ReevaluateProperty <RuleReevaluatePropertyEnum>] [-ThrottleLimit <Int32>] -ClassificationMechanism <String>
 -Namespace <String[]> -Property <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **New-FsrmClassificationRule** cmdlet creates an automatic classification rule on the server.
Each rule sets the value for a single property.
By default, a rule runs only once and ignores files that already have a property value assigned.
However, you can configure a rule to evaluate files regardless of whether a value is already assigned to the property.

## EXAMPLES

### Example 1: Create a classification rule
```
PS C:\>New-FsrmClassificationRule -Name "Find confidential files" -Namespace @("C:\shares\CtrShare03") -Property "Impact" -PropertyValue "High" -ClassificationMechanism "Content Classifier" -ContentString "Confidential"
```

This command creates a classification rule that marks any files as Impact=High if the files contain the word "Confidential" and the files do not already have an Impact property.

### Example 2: Create a classification rule and overwrite the property value
```
PS C:\>New-FsrmClassificationRule -Name "Find confidential files" -Namespace @("C:\shares\CtrShare03") -Property "Impact" -PropertyValue "High" -ClassificationMechanism "Content Classifier" -ContentString "confidential" -ReevaluateProperty Overwrite
```

This command creates a classification rule that marks any files as Impact=High if they contain the word "Confidential", and overwrites any existing Impact property value.

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

The classification mechanisms are provided by a series of plug-ins that are included with Windows Server® 2012 or produced by you or an ISV.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ContentStringCaseSensitive
Specifies an array of case sensitive strings for the content classifier to search for.

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

### -Description
Specifies a description for the classification rule.

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

### -Name
Specifies a name for the classification rule.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Namespace
Specifies an array of namespaces where the rule is applied.
Each value must be either a value of the FolderType property defined on the server (using the format "\[Folder type property name=\<value\>\]") or a static path.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
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

### -Property
Specifies the name of a classification property definition to set.
Specify the value of the **Name** property in a **FsrmClassificationPropertyDefinition** object.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PropertyValue
Specifies the property value that the rule will assign.
The property value that you set must be an valid value supported by the classification mechanism that you specify in the **ClassificationMechanism** parameter.

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

[Set-FsrmClassificationRule](./Set-FsrmClassificationRule.md)

[Remove-FsrmClassificationRule](./Remove-FsrmClassificationRule.md)

[Get-FsrmClassificationPropertyDefinition](./Get-FsrmClassificationPropertyDefinition.md)


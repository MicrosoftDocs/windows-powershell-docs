---
external help file: FSRM_Cmdlets.xml
Module Name: FileServerResourceManager
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/remove-fsrmclassificationpropertydefinition?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-FsrmClassificationPropertyDefinition

## SYNOPSIS
Removes classification property definitions.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-FsrmClassificationPropertyDefinition [-Name] <String[]> [-AsJob] [-CimSession <CimSession[]>]
 [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-FsrmClassificationPropertyDefinition [-AsJob] [-CimSession <CimSession[]>] [-PassThru]
 [-ThrottleLimit <Int32>] -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-FsrmClassificationPropertyDefinition** cmdlet removes one or more classification property definitions from the server.
The cmdlet can remove only locally defined property definitions.

## EXAMPLES

### Example 1: Remove a classification property definition
```
PS C:\>Remove-FsrmClassificationPropertyDefinition -Name "Business Impact"
```

This command removes the classification property definition named "Business Impact".

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
Specifies an array of property names.

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

## NOTES

## RELATED LINKS

[Get-FsrmClassificationPropertyDefinition](./Get-FsrmClassificationPropertyDefinition.md)

[Set-FsrmClassificationPropertyDefinition](./Set-FsrmClassificationPropertyDefinition.md)

[New-FsrmClassificationPropertyDefinition](./New-FsrmClassificationPropertyDefinition.md)

[Remove-FsrmClassificationPropertyDefinition](./Remove-FsrmClassificationPropertyDefinition.md)


---
external help file: FSRM_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 950A3ABF-7FA0-426B-94C5-42DA59C2B13B
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# New-FsrmClassificationPropertyValue

## SYNOPSIS
Creates a classification property value.

## SYNTAX

```
New-FsrmClassificationPropertyValue [-Name] <String> [-AsJob] [-CimSession <CimSession[]>]
 [-Description <String>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **New-FsrmClassificationPropertyValue** cmdlet creates a classification property value.

## EXAMPLES

### Example 1: Create a classification property number value
```
PS C:\>New-FsrmClassificationPropertyValue -Name "1" -Description "The value 1"
```

This command creates the classification property value named "1" and adds a description to the property value.

### Example 2: Create a classification property string value
```
PS C:\>New-FsrmClassificationPropertyValue -Name "Value 1" -Description "First item in a list"
```

This command creates the classification property value named "Value1" and adds a description to the property value.

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

### -Description
Specifies a description for the classification property value.

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

### -Name
Specifies a name for the classification property value.

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

[New-FsrmClassificationPropertyDefinition](./New-FsrmClassificationPropertyDefinition.md)

[Set-FsrmClassificationPropertyDefinition](./Set-FsrmClassificationPropertyDefinition.md)


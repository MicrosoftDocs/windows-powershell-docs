---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamCustomValue.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/rename-ipamcustomvalue?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-IpamCustomValue
---

# Rename-IpamCustomValue

## SYNOPSIS
Changes a value for a custom field.

## SYNTAX

```
Rename-IpamCustomValue [-Name] <String> [-Value] <String> [-NewValue] <String> [-PassThru] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Rename-IpamCustomValue** cmdlet changes a value for a multivalued custom field.
The cmdlet changes only the custom value.
Associations between the custom field and other custom fields and assignments to other IP Address Management (IPAM) server objects remain valid.
You cannot change built-in values of built-in custom fields.
The cmdlet results in an error if the value that you specify does not exist for the custom field that you specify.

## EXAMPLES

### Example 1: Change a value for a custom field
```
PS C:\> Rename-IpamCustomValue -Name "Building" -Value "NorthB3" -NewValue "MainB3" -PassThru
Value                                   Category                                CustomField

-----                                   --------                                -----------

NorthB2                              UserDefined                             Building
```

This command changes the value from NorthB3 to MainB3 for the custom field named Building.

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

### -Force
Forces the command to run without asking for user confirmation.

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
Specifies the name of a custom field.
The cmdlet changes the value from the custom field that you specify for the *Value* parameter.

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

### -NewValue
Specifies a value to replace the custom field value that you specify for the *Value*  parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
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
Specifies a custom value.
The cmdlet changes this value to the value that you specify for the *NewValue*  parameter.

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

## OUTPUTS

### IpamCustomField
This cmdlet returns an object that represents a custom metadata field in IPAM Server.

## NOTES

## RELATED LINKS

[Add-IpamCustomValue](./Add-IpamCustomValue.md)

[Remove-IpamCustomValue](./Remove-IpamCustomValue.md)


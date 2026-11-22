---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamCustomField.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/add-ipamcustomfield?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-IpamCustomField
---

# Add-IpamCustomField

## SYNOPSIS
Adds a free-form or multivalued custom field to IPAM.

## SYNTAX

```
Add-IpamCustomField [-Name] <String> [-MultiValue] [-Value <String[]>] [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-IpamCustomField** cmdlet adds a custom field to IP Address Management (IPAM).
Specify a name for the custom field.
By default, a custom field is free-form.
Specify the *MultiValue* parameter to indicate that the custom field is multivalued.

## EXAMPLES

### Example 1: Add a custom field
```
PS C:\> Add-IpamCustomField -Name "CustomField01" -PassThru
Name                  Category               Multivalue        CustomValue
---------------------------------------------------------------------------------
CustomField01         UserDefined            False
```

This command adds a custom field named CustomField01 to the IPAM server and returns the custom field object.
By default, the custom field is free-form.

### Example 2: Add a multivalued custom field
```
PS C:\> Add-IpamCustomField -Name "CustomMVField02" -MultiValue -PassThru
Name                  Category               Multivalue        CustomValue
---------------------------------------------------------------------------------
CustomMVField02       UserDefined            True
```

This command adds a multivalued custom field named CustomMVField02 to the IPAM server, and returns the custom field object.

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

### -MultiValue
Indicates that the custom field is multivalued.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the custom field.

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
Specifies an array of values for the custom field.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: CustomValueName

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

### None

## OUTPUTS

### Microsoft.Windows.Ipam.Commands.IpamCustomField
This cmdlet returns an object that contains an IPAM custom field.

## NOTES

## RELATED LINKS

[Add-IpamCustomValue](./Add-IpamCustomValue.md)

[Get-IpamCustomField](./Get-IpamCustomField.md)

[Remove-IpamCustomField](./Remove-IpamCustomField.md)

[Rename-IpamCustomField](./Rename-IpamCustomField.md)


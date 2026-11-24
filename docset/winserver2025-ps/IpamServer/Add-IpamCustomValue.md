---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamCustomValue.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/add-ipamcustomvalue?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-IpamCustomValue
---

# Add-IpamCustomValue

## SYNOPSIS
Adds a value to a custom field in IPAM.

## SYNTAX

```
Add-IpamCustomValue [-Name] <String> [-Value] <String> [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-IpamCustomValue** cmdlet adds a value to a custom field in IP Address Management (IPAM).
You can add a value to a built-in field or user-defined custom field.

## EXAMPLES

### Example 1: Add a custom value
```
PS C:\> Add-IpamCustomValue -Name "Divisions" -Value "DivMain01"
```

This command adds the custom value DivMain01 to the user defined custom field named Divisions.

### Example 2: Add a custom value to a user defined custom field
```
PS C:\> Add-IpamCustomValue -Name "Divisions" -Value "DivMain01" -PassThru
Value                  Category             CustomField
------------------------------------------------------------
DivMain01              UserDefined          Divisions
```

This command adds the custom value DivMain01 to the user defined custom field named Divisions.
The command includes the *PassThru* parameter, so it displays results to the console.

### Example 3: Add a custom value to a built-in custom field
```
PS C:\> Add-IpamCustomValue -Name "ServiceInstance" -Value "vmm1.contoso.com" -PassThru
Value                  Category             CustomField
------------------------------------------------------------
vmm1.contoso.com       UserDefined          ServiceInstance
```

This command adds the custom value vmm1.contoso.com to the built-in custom field named ServiceInstance.
The command includes the *PassThru* parameter, so it displays results to the console.

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

### -Name
Specifies the name of a custom field.
The cmdlet adds the value that you specify for the *Value* parameter to the custom field.
You can specify the localized server name or the non-localized name of a built-in, multivalued custom field.

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
Specifies a value to add to the custom field.

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

### None

## OUTPUTS

### Microsoft.Windows.Ipam.Commands.IpamCustomValue
This cmdlet returns an object that contains an IPAM custom value.

## NOTES

## RELATED LINKS

[Remove-IpamCustomValue](./Remove-IpamCustomValue.md)

[Rename-IpamCustomValue](./Rename-IpamCustomValue.md)

[Add-IpamCustomField](./Add-IpamCustomField.md)

[Get-IpamCustomField](./Get-IpamCustomField.md)


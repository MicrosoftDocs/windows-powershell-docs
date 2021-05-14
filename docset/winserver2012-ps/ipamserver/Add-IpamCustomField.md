---
external help file: IpamServer_Cmdlets.xml
Module Name: IpamServer
online version: https://docs.microsoft.com/powershell/module/ipamserver/add-ipamcustomfield?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-IpamCustomField

## SYNOPSIS
Adds a new free form or multi-valued custom field to the computer running the  IP Address Management (IPAM) server.

## SYNTAX

```
Add-IpamCustomField [-Name] <String> [-Multivalue] [-PassThru] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-IpamCustomField** cmdlet adds a new custom field name to the computer running the IP Address Management (IPAM) server.
The user can indicate if the newly added custom field is free form or multi-valued.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Add-IpamCustomField -Name MyField -PassThru
Name                  Category               Multivalue        CustomValue 
--------------------------------------------------------------------------------- 
MyField               UserDefined            False
```

This example adds an IPAM custom field named MyField and returns the object associated with it.

### EXAMPLE 2
```
PS C:\>Add-IpamCustomField -Name MyMultiValueField -Multivalue -PassThru
Name                  Category               Multivalue        CustomValue 
--------------------------------------------------------------------------------- 
MyMultiValueField      UserDefined            True
```

This example adds a multi-valued, IPAM custom field named MyMultiValueField and returns the object associated with it.

## PARAMETERS

### -Multivalue
Adds the specified custom field as a multi-valued field.
If this parameter is not specified, then the custom field is added as a free-form field.

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
Specifies the name of the new custom field being added.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

### None

## OUTPUTS

### Microsoft.Windows.Ipam.Commands.IpamCustomField
This object contains an IPAM custom field.

## NOTES

## RELATED LINKS

[Add-IpamCustomValue](./Add-IpamCustomValue.md)

[Get-IpamCustomField](./Get-IpamCustomField.md)


---
author: Kateyanne
external help file: IpamServer_Cmdlets.xml
manager: dansimp
Module Name: IpamServer
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/ipamserver/add-ipamcustomvalue?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-IpamCustomValue

## SYNOPSIS
Adds a new custom value to a multi-valued, custom field in IP Address Management (IPAM).

## SYNTAX

```
Add-IpamCustomValue [-Name] <String> [-Value] <String> [-PassThru] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-IpamCustomValue** cmdlet adds a new custom value to the specified multi-valued custom field name in IP Address Management (IPAM).
The multi-valued custom field can either be built-in or user-defined.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Add-IpamCustomValue -Name MyField -Value MyValue
```

This example adds an IPAM custom value named MyValue to the user defined custom field MyField.

### EXAMPLE 2
```
PS C:\>Add-IpamCustomValue -Name MyField -Value MyValue -PassThru
Value                  Category             CustomField 
------------------------------------------------------------ 
MyValue                UserDefined          MyField
```

This example adds an IPAM custom value named MyValue to the user defined custom field MyField, and returns the object associated with the custom value.

### EXAMPLE 3
```
PS C:\>Add-IpamCustomValue -Name ServiceInstance -Value MyValue -PassThru
Value                  Category             CustomField 
------------------------------------------------------------ 
MyValue                UserDefined          ServiceInstance
```

This example adds an IPAM custom value named MyValue to the in-built custom field ServiceInstance, and returns the object associated with the custom value.

## PARAMETERS

### -Name
Specifies the name of the custom field against which the new value needs is being added.
The cmdlet accepts both the localized server name as well as the English name of the built-in, multi-valued, custom fields.

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

### -Value
Specifies the name of the new custom field value being added.

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

### Microsoft.Windows.Ipam.Commands.IpamCustomValue
This object contains an IPAM custom value.

## NOTES

## RELATED LINKS

[Add-IpamCustomField](./Add-IpamCustomField.md)

[Get-IpamCustomField](./Get-IpamCustomField.md)


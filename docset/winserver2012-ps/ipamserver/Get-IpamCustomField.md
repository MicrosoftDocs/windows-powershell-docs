---
external help file: IpamServer_Cmdlets.xml
Module Name: IpamServer
online version: https://docs.microsoft.com/powershell/module/ipamserver/get-ipamcustomfield?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-IpamCustomField

## SYNOPSIS
Gets the IP Address Management (IPAM) custom field information.

## SYNTAX

```
Get-IpamCustomField [[-Name] <String>]
```

## DESCRIPTION
The **Get-IpamCustomField** cmdlet gets the IP Address Management (IPAM) custom field information.
The custom field and associated custom values can be fetched from IPAM using this cmdlet.
If the custom field name is not specified, then this cmdlet returns all of the IPAM custom fields and associated values.
For multi-valued fields the custom field objects returned by this cmdlet contains the collection of corresponding custom value objects.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-IpamCustomField
Name                 Category               Multivalue          CustomValue 
---------------------------------------------------------------------------------------------------------------------------- 
AdSite                BuiltIn               False 
CountryOrRegion       BuiltIn               True            {Afghanistan, Alfand Islands,...} 
..... 
.....
```

This example gets the custom field information for all the built-in and user defined fields of IPAM.
For multi-valued fields, the corresponding custom value information is also returned

### EXAMPLE 2
```
PS C:\>Get-IpamCustomField -Name ManagedByService
Name                 Category               Multivalue          CustomValue 
---------------------------------------------------------------------------------------------------------------------------- 
ManagedByService      BuiltIn                True           {IPAM,MS DHCP,Non-MS DHCP...}
```

This example gets the custom field information and the corresponding custom value information for the specified field named ManagedByService.

## PARAMETERS

### -Name
Specifies the name of the custom field that is retrieved.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
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

[Add-IpamCustomField](./Add-IpamCustomField.md)

[Add-IpamCustomValue](./Add-IpamCustomValue.md)


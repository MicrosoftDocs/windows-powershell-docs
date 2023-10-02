---
external help file: GPv2_Cmdlets.xml
Module Name: GroupPolicy
online version: https://learn.microsoft.com/powershell/module/grouppolicy/remove-gpo?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-GPO

## SYNOPSIS
Deletes a GPO.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-GPO [-Domain <String>] [-KeepLinks] [-Server <String>] -Guid <Guid> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-GPO [-Name] <String> [-Domain <String>] [-KeepLinks] [-Server <String>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The Remove-GPO cmdlet removes the GPO container and data from the directory service and the system volume folder (SysVol).

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Remove-GPO -guid 50cc3e45-0b14-46dd-8b4d-afa012bc331c -Domain contoso.com -KeepLinks
```

Description

-----------

Removes the GPO that has the GUID 50cc3e45-0b14-46dd-8b4d-afa012bc331c from the contoso.com domain.
Because the KeepLinks parameter is specified, links between the GPO and all sites, and links between the GPO and all containers in the domain are preserved.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Remove-GPO -Name TestGPO
```

Description

-----------

Removes the "TestGPO" GPO from the domain of the user that is running the session (or, for startup and shutdown scripts, the domain of the computer).
Because the KeepLinks parameter is not specified, links between the GPO and all sites, and links between the GPO and all containers in the domain are deleted.

## PARAMETERS

### -Domain
Specifies the domain in which you want to remove a GPO.
You must specify the fully qualified domain name (FQDN) of the domain (for example: SalesDomain.Contoso.com).

If you do not specify the Domain parameter, the domain of the computer that you are logged on to is used.

If you specify a domain that differs from the domain of your user object, a trust must exist between the domain from which you want to remove the GPO and the domain of your user object.

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

### -Guid
Specifies the GPO to delete by its globally unique identifier (GUID).
The GUID uniquely identifies the GPO.

You can also refer to the Guid parameter by its built-in alias, "id".
For more information, see about_Aliases.

```yaml
Type: Guid
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeepLinks
Preserves the links to the GPO in the specified domain (including OUs) and all sites when the GPO is removed.

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
Specifies the GPO to delete by its display name.

The display name is not guaranteed to be unique in the domain.
If another GPO with the same display name exists in the domain an error occurs.
You can use the Guid parameter to uniquely identify a GPO.

You can also refer to the Name parameter by its built-in alias, "displayname".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -Server
Specifies the name of the domain controller that this cmdlet contacts to complete the operation.
You can specify either the fully qualified domain name (FQDN) or the host name.
For example:

FQDN: DomainController1.sales.contoso.com

Host Name: DomainController1

If you do not specify the name by using the Server parameter, the PDC emulator is contacted.

You can also refer to the Server parameter by its built-in alias, "dc".
For more information, see about_Aliases.

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

### Microsoft.GroupPolicy.Gpo
A GPO to be deleted.
Collections that contain GPOs from different domains are not supported.

## OUTPUTS

### None
This cmdlet does not output any objects.

## NOTES
* When you delete a GPO, by default, all links to that GPO in the domain of the GPO are deleted. To delete a link to a GPO, you must have permission to link Group Policy Objects for the organizational unit or domain. If you do not have rights to delete a link, the GPO is deleted, but the link remains. Links from other domains and sites are not deleted. The link to a deleted GPO appears in the GPMC as Not Found. To delete Not Found links, you must either have permission on the site, domain, or organizational unit containing the link, or ask someone with sufficient rights to delete it.

## RELATED LINKS

[Get-GPO](./Get-GPO.md)

[New-GPO](./New-GPO.md)


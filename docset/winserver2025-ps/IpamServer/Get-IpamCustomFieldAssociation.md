---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamCustomFieldAssociation.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/get-ipamcustomfieldassociation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IpamCustomFieldAssociation
---

# Get-IpamCustomFieldAssociation

## SYNOPSIS
Gets associations between two custom fields defined in IPAM.

## SYNTAX

```
Get-IpamCustomFieldAssociation [[-CustomFieldOne] <String>] [[-CustomFieldTwo] <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-IpamCustomFieldAssociation** cmdlet gets associations between two custom fields defined in IP Address Management (IPAM).
You can specify the custom fields by using the *CustomFieldOne* and *CustomFieldTwo* parameters.
If you specify only one of these parameters, the cmdlet gets all associations that include the field that you specify.
Associations are not directional, so you can use either parameter for either field.
If you do not specify either parameter, the cmdlet gets all the associations.

Use the **Add-IpamCustomFieldAssociation** cmdlet to create associations.
Use the **Remove-IpamCustomFieldAssociation** cmdlet to remove associations.
Use the **Set-IpamCustomFieldAssociation** cmdlet to modify associations.

## EXAMPLES

### Example 1: Get all custom field associations in IPAM
```
PS C:\> Get-IpamCustomFieldAssociation
CustomFieldOne   : Region

CustomFieldTwo   : Site

AssociationValue : {Region03,Site09, Region03,Site10, Region03,Site11, Region03,Site12}

CustomFieldOne   : ManagedByService

CustomFieldTwo   : ServiceInstance

AssociationValue : {IPAM,Localhost, MS DHCP,dhcp1.contoso.com}
CustomFieldOne   : VmmLogicalNetwork

CustomFieldTwo   : NetworkSite

AssociationValue : {Public:Site03, Storage:Site02, Storage:Site01}
```

This command gets all the associations of custom fields specified in IPAM.

### Example 2: Get associations for two custom fields
```
PS C:\> Get-IpamCustomFieldAssociation -CustomFieldOne "ManagedByService" -CustomFieldTwo "ServiceInstance"
CustomFieldOne   : ManagedByService

CustomFieldTwo   : ServiceInstance

AssociationValue : {IPAM:Localhost, MS DHCP:dhcp1.contoso.com}
```

This command gets the associations between two custom fields, ManagedByService and ServiceInstance.

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

### -CustomFieldOne
Specifies a custom field.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CustomFieldTwo
Specifies a custom field.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-IpamCustomFieldAssociation](./Add-IpamCustomFieldAssociation.md)

[Remove-IpamCustomFieldAssociation](./Remove-IpamCustomFieldAssociation.md)

[Set-IpamCustomFieldAssociation](./Set-IpamCustomFieldAssociation.md)


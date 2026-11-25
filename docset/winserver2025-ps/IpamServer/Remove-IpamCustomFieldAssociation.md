---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamCustomFieldAssociation.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/remove-ipamcustomfieldassociation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-IpamCustomFieldAssociation
---

# Remove-IpamCustomFieldAssociation

## SYNOPSIS
Removes an association between two custom fields that are defined in IPAM.

## SYNTAX

```
Remove-IpamCustomFieldAssociation [-CustomFieldOne] <String> [-CustomFieldTwo] <String> [-Force] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-IpamCustomFieldAssociation** cmdlet removes an association between two custom fields that are defined in IP Address Management (IPAM).
Specify the custom fields by using the *CustomFieldOne* and *CustomFieldTwo* parameters.
The cmdlet does not find an association that contains both specified fields, it informs you of the error.
The cmdlet does not delete the custom fields themselves.

Use the **Get-IpamCustomFieldAssociation** cmdlet to see existing associations.
Use the **Add-IpamCustomFieldAssociation** cmdlet to create associations.
Use the **Set-IpamCustomFieldAssociation** cmdlet to modify associations.

## EXAMPLES

### Example 1: Remove association between fields
```
The first command removes the association between the two custom fields, VmmLogicalNetwork and NetworkSite. The cmdlet prompts you before it removes associations.
PS C:\> Remove-IpamCustomFieldAssociation -CustomFieldOne "VmmLogicalNetwork" -CustomFieldTwo "NetworkSite"
Confirm

This will permanently delete the Custom Field Association between Custom Field VmmLogicalNetwork and

NetworkSite.Do you want to continue?

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y


The second command uses the Get-IpamCustomFieldAssociation to get all associations. The associations that the first command removed do not appear.
PS C:\> Get-IpamCustomFieldAssociation
CustomFieldOne   : Region

CustomFieldTwo   : Site

AssociationValue : {Region01:Site09, Region01:Site10, Region01:Site11}
CustomFieldOne   : ManagedByService

CustomFieldTwo   : ServiceInstance

AssociationValue : {IPAM:Localhost, MS DHCP:dhcp1.contoso.com}
```

This example removes an association between fields, and then verifies the removal.

### Example 2: Remove all associations for a field
```
The first command uses the **Get-IpamCustomFieldAssociation** cmdlet to get all the associations specified by the ManagedByService custom field, and then passes them to the current cmdlet by using the pipeline operator. The cmdlet prompts you for confirmation, and then removes all the associations.
PS C:\> Get-IpamCustomFieldAssociation -CustomFieldOne "ManagedByService" | Remove-IpamCustomFieldAssociation
Confirm

This will permanently delete the Custom Field Association between Custom Field ManagedByService and

ServiceInstance.Do you want to continue?

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y

The second command uses the Get-IpamCustomFieldAssociation to get all associations. The associations that the first command removed do not appear.
PS C:\> Get-IpamCustomFieldAssociation
CustomFieldOne   : Region

CustomFieldTwo   : Site

AssociationValue : {Region01:Site09, Region01:Site10, Region01:Site11}
```

This example removes all associations for a specified field, and then verifies the removal.

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

### -CustomFieldOne
Specifies a custom field.
The cmdlet removes an association between this field and the field specified by the *CustomFieldTwo* parameter.

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

### -CustomFieldTwo
Specifies a custom field.
The cmdlet removes an association between this field and the field specified by the *CustomFieldOne* parameter.

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

## NOTES

## RELATED LINKS

[Add-IpamCustomFieldAssociation](./Add-IpamCustomFieldAssociation.md)

[Get-IpamCustomFieldAssociation](./Get-IpamCustomFieldAssociation.md)

[Set-IpamCustomFieldAssociation](./Set-IpamCustomFieldAssociation.md)


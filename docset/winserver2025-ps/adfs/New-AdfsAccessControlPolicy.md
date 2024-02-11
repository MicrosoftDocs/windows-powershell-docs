---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/new-adfsaccesscontrolpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-AdfsAccessControlPolicy
---

# New-AdfsAccessControlPolicy

## SYNOPSIS
Creates an AD FS access control policy.

## SYNTAX

```
New-AdfsAccessControlPolicy -Name <String> [-SourceName <String>] [-Identifier <String>]
 [-Description <String>] [-PolicyMetadata <PolicyMetadata>] [-PolicyMetadataFile <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-AdfsAccessControlPolicy** cmdlet creates an Active Directory Federation Services (AD FS) access control policy from a policy metadata file.

**How to create a federation metadata file**

The federation metadata document is an XML file that is available for [download](https://adfshelp.microsoft.com/MetadataExplorer/GetFederationMetadata). To retrieve your document, enter your federation service name, and then select the **Get federation metadata** button.

## EXAMPLES

### Example 1: Create a policy template from a policy metadata file
```
PS C:\> $t=New-AdfsAccessControlPolicy -Name "DemoOne" -PolicyMetadataFile "C:\filepath\ PolicyTemplateIntranetWithOneGroupParameterMFA.xml"
```

This command creates a policy template from a policy metadata file.

### Example 2: Create a relying party using the policy template
```
PS C:\> Add-AdfsRelyingPartyTrust -Name "DemoRP1" -Identifier "https://DemoRP1" -AccessControlPolicyName DemoOne -AccessControlPolicyParameters "Administrators"
```

This command creates a relying party using the policy template.

### Example 3: Change parameters
```
PS C:\> Set-AdfsRelyingPartyTrust -TargetName "DemoRP1" -AccessControlPolicyParameters ("Administrators","Users") -AccessControlPolicyName "DemoOne"
```

This command changes parameters for an access control policy.

### Example 4: Un-assign a policy template
```
PS C:\> Set-AdfsRelyingPartyTrust -TargetName "DemoRP1" -AccessControlPolicyName $null
```

This command un-assigns a policy template.

### Example 5: Create a policy template from an existing template
```
PS C:\> New-AdfsAccessControlPolicy -Name "DemoCopyOne" -SourceName "DemoOne"
```

This command creates a policy template from an existing template.

### Example 6: Create a policy template from existing metadata
```
PS C:\> New-AdfsAccessControlPolicy -Name "DemoCopyTwo" -PolicyMetadata $t.PolicyMetadata
```

This command creates a policy template from existing metadata.
The $t variable is an object from **New-AccessControlPolicy**.

### Example 7: Create a policy template from a relying party result policy
```
PS C:\> New-AdfsAccessControlPolicy -Name "DemoCopyWithAssignment" -PolicyMetadata $r.ResultantPolicy
```

This command creates a policy template from a relying party result policy.
The $r variable is the object returned from **Get-AdfsRelyingPartyTrust**.

### Example 8: Change the relying party to use a new template
```
PS C:\> Set-AdfsRelyingPartyTrust -TargetName "DemoRP1" -AccessControlPolicyName "DemoTwo" -AccessControlPolicyParameters @{PermitGroup="Users";RejectGroup="Administrators"}
```

This command changes the relying party to use a new template.

### Example 9: Complicated conditions with specific claims
```
PS C:\> Set-AdfsRelyingPartyTrust -TargetName "DemoRP1" -AccessControlPolicyName DemoRP -AccessControlPolicyParameters`
    @{"SPParameter"= @{ClaimType="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/OfficeLocation"; Operator="Equals"; Value="Redmond"}}
```

### Example 10: Two specific claims for single parameter
```
PS C:\> Set-AdfsRelyingPartyTrust -TargetName "DemoRP1" -AccessControlPolicyName "DemoRP" -AccessControlPolicyParameters`
    @{"SPParameter"= (@{ClaimType="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/OfficeLocation"; Operator="Equals"; Value=("Redmond","DC")},`
                      @{ClaimType="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/Department"; Operator="Equals"; Value="Azure"})}
```

## PARAMETERS

### -Description
Specifies a description.

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

### -Identifier
Specifies an ID.

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
Specifies a name.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyMetadata
Specifies metadata for the policy.

```yaml
Type: PolicyMetadata
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyMetadataFile
Specifies a file that contains metadata for the policy.

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

### -SourceName
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
Aliases: cf

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

[Get-AdfsAccessControlPolicy](./Get-AdfsAccessControlPolicy.md)

[Remove-AdfsAccessControlPolicy](./Remove-AdfsAccessControlPolicy.md)

[Set-AdfsAccessControlPolicy](./Set-AdfsAccessControlPolicy.md)


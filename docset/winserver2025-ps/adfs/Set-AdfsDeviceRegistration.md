---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfsdeviceregistration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsDeviceRegistration
---

# Set-AdfsDeviceRegistration

## SYNOPSIS
Configures the administrative policies for the Device Registration Service.

## SYNTAX

### NumberOfInactiveDays
```
Set-AdfsDeviceRegistration -MaximumInactiveDays <UInt32> [-AccessControlPolicyName <String>]
 [-AccessControlPolicyParameters <Object>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NumberOfDevicesPerUser
```
Set-AdfsDeviceRegistration -DevicesPerUser <UInt32> [-AccessControlPolicyName <String>]
 [-AccessControlPolicyParameters <Object>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ServiceAccountIdentifier
```
Set-AdfsDeviceRegistration -ServiceAccountIdentifier <String> -Credential <PSCredential>
 [-AccessControlPolicyName <String>] [-AccessControlPolicyParameters <Object>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### IssuanceCertificate
```
Set-AdfsDeviceRegistration [-IssuanceCertificate] [-AccessControlPolicyName <String>]
 [-AccessControlPolicyParameters <Object>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RelyingParty
```
Set-AdfsDeviceRegistration [-AccessControlPolicyName <String>] [-AccessControlPolicyParameters <Object>]
 [-AllowedAuthenticationClassReferences <String[]>] [-IssuanceAuthorizationRules <String>]
 [-IssuanceAuthorizationRulesFile <String>] [-IssuanceTransformRules <String>]
 [-IssuanceTransformRulesFile <String>] [-AdditionalAuthenticationRules <String>]
 [-AdditionalAuthenticationRulesFile <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsDeviceRegistration** cmdlet configures the administrative policies for the Device Registration Service.
Use this cmdlet to change the default policies of the Device Registration Service in Active Directory Federation Services (AD FS), such as the maximum number of devices that a user can register.

## EXAMPLES

### Example 1: Set the number of devices that a user can register
```
PS C:\> Set-AdfsDeviceRegistration -DevicesPerUser 10
```

This command sets the number of devices that a user can register to 10.

### Example 2: Configure the maximum inactive days for a device
```
PS C:\> Set-AdfsDeviceRegistration -MaximumInactiveDays 90
```

This command configures the number of days before the Device Registration Service removes an inactive device object.

### Example 3: Set the service account for the Device Registration Service
```
PS C:\> $Cred = Get-Credential
PS C:\> Set-AdfsDeviceRegistration -ServiceAccountIdentifier "CONTOSO\Svc_adfs" -Credential $Cred
```

The first command uses the **Get-Credential** cmdlet to create a credential object for the Active Directory account under which the AD FS service runs.
The command stores the credential object in the $Cred variable.

The second command sets the service account that has the ID Svc_adfs.
The command specifies the credentials stored in $Cred for the Active Directory account under which the AD FS service runs.

## PARAMETERS

### -AccessControlPolicyName
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

### -AccessControlPolicyParameters
```yaml
Type: Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AdditionalAuthenticationRules
```yaml
Type: String
Parameter Sets: RelyingParty
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AdditionalAuthenticationRulesFile
```yaml
Type: String
Parameter Sets: RelyingParty
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowedAuthenticationClassReferences
```yaml
Type: String[]
Parameter Sets: RelyingParty
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
```yaml
Type: PSCredential
Parameter Sets: ServiceAccountIdentifier
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DevicesPerUser
Specifies the maximum number of devices that a user can register.

```yaml
Type: UInt32
Parameter Sets: NumberOfDevicesPerUser
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IssuanceAuthorizationRules
```yaml
Type: String
Parameter Sets: RelyingParty
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IssuanceAuthorizationRulesFile
```yaml
Type: String
Parameter Sets: RelyingParty
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IssuanceCertificate
Indicates that the cmdlet generates and uses a new signing certificate for the Device Registration Service.

```yaml
Type: SwitchParameter
Parameter Sets: IssuanceCertificate
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IssuanceTransformRules
```yaml
Type: String
Parameter Sets: RelyingParty
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IssuanceTransformRulesFile
```yaml
Type: String
Parameter Sets: RelyingParty
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumInactiveDays
Specifies the number of days before a device object is removed because of inactivity.

```yaml
Type: UInt32
Parameter Sets: NumberOfInactiveDays
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ServiceAccountIdentifier
Specifies the ID of the service account.
The cmdlet grants this account read and write access to the Device Registration Service configuration and containers in Active Directory® Domain Services.

```yaml
Type: String
Parameter Sets: ServiceAccountIdentifier
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### uint, string, switch

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-AdfsDeviceRegistration](./Disable-AdfsDeviceRegistration.md)

[Enable-AdfsDeviceRegistration](./Enable-AdfsDeviceRegistration.md)

[Get-AdfsDeviceRegistration](./Get-AdfsDeviceRegistration.md)


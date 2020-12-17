---
external help file: Microsoft.Security.ApplicationId.PolicyManagement.Cmdlets.dll-Help.xml
Module Name: AppLocker
online version: 
schema: 2.0.0
title: Set-AppLockerPolicy
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: A5B91C2A-73C3-417C-84B1-D430B42860A3
---

# Set-AppLockerPolicy

## SYNOPSIS
Sets the AppLocker policy for the specified Group Policy Object (GPO).

## SYNTAX

### ByXmlPolicy (Default)
```
Set-AppLockerPolicy [-XmlPolicy] <String> [-Ldap <String>] [-Merge] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByPolicyObject
```
Set-AppLockerPolicy [-PolicyObject] <AppLockerPolicy> [-Ldap <String>] [-Merge] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AppLockerPolicy cmdlet** sets the specified GPO to contain the specified AppLocker policy.
If no Lightweight Directory Access Protocol (LDAP) is specified, then the default is the local GPO.

The input values for the AppLocker policy can be an AppLockerPolicy object or an XML-formatted file containing the AppLocker policy.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Set-AppLockerPolicy -XMLPolicy C:\Policy.xml
```

This example sets the local AppLocker policy to the policy specified in C:\Policy.xml.

### EXAMPLE 2
```
PS C:\> Set-AppLockerPolicy -XMLPolicy C:\Policy.xml -LDAP "LDAP://DC13.Contoso.com/CN={31B2F340-016D-11D2-945F-00C04FB984F9},CN=Policies,CN=System,DC=Contoso,DC=com"
```

This example sets the GPO specified in the LDAP path to contain the AppLocker policy that is specified in C:\Policy.xml.

### EXAMPLE 3
```
PS C:\> Get-AppLockerPolicy -Local | Set-AppLockerPolicy -LDAP "LDAP://DC13.Contoso.com/CN={31B2F340-016D-11D2-945F-00C04FB984F9},CN=Policies,CN=System,DC=Contoso,DC=com" -Merge
```

This example gets the local AppLocker policy, and then merges the policy with the existing AppLocker policy in the GPO specified in the LDAP path.
See the **Merge** parameter description for more details on how two policies are merged.

## PARAMETERS

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

### -Ldap
Specifies the LDAP path of the GPO.
It must specify a unique GPO.
If this parameter is not specified, then the local AppLocker policy is set.

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

### -Merge
Merges the rules in the specified AppLocker policy with the AppLocker rules in the target GPO specified in the LDAP path.
The merging of policies will remove rules with duplicate rule IDs, and the enforcement setting specified by the AppLocker policy in the target GPO will be preserved.
If the **Merge** parameter is not specified, then the new policy will overwrite the existing policy.

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

### -PolicyObject
Specifies the **AppLockerPolicy** object that contains the AppLocker policy.
Can be obtained from the Get-AppLockerPolicy and the New-AppLockerPolicy cmdlets.

```yaml
Type: AppLockerPolicy
Parameter Sets: ByPolicyObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### -XmlPolicy
Specifies the path where the XML-formatted file containing the AppLocker policy is saved.

```yaml
Type: String
Parameter Sets: ByXmlPolicy
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Security.ApplicationId.PolicyManagement.PolicyModel.AppLockerPolicy
AppLockerPolicy

### System.String

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-AppLockerFileInformation](./Get-AppLockerFileInformation.md)

[Get-AppLockerPolicy](./Get-AppLockerPolicy.md)

[New-AppLockerPolicy](./New-AppLockerPolicy.md)

[Test-AppLockerPolicy](./Test-AppLockerPolicy.md)


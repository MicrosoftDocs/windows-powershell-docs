---
external help file: Microsoft.Security.ApplicationId.PolicyManagement.Cmdlets.dll-Help.xml
Module Name: AppLocker
online version: 
schema: 2.0.0
title: Get-AppLockerPolicy
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
ms.assetid: EE3463D6-A81F-4C97-900B-E6C0F400D40F
---

# Get-AppLockerPolicy

## SYNOPSIS
Gets the local, the effective, or a domain AppLocker policy.

## SYNTAX

### LocalPolicy (Default)
```
Get-AppLockerPolicy [-Local] [-Xml] [<CommonParameters>]
```

### DomainPolicy
```
Get-AppLockerPolicy [-Domain] -Ldap <String> [-Xml] [<CommonParameters>]
```

### EffectivePolicy
```
Get-AppLockerPolicy [-Effective] [-Xml] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppLockerPolicy** cmdlet retrieves the AppLocker policy from the local Group Policy Object (GPO), a specified Group Policy Object (GPO), or the effective policy on the computer.

By default, the output is an AppLockerPolicy object.
If the **XML** parameter is used, then the output will be the AppLocker policy as an XML-formatted string.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-AppLockerPolicy -Local
                                Version RuleCollections                         RuleCollectionTypes 
                                ------- ---------------                         ------------------- 
                                      1 {}                                      {}
```

This example gets the local AppLocker policy as an AppLockerPolicy object.

### EXAMPLE 2
```
PS C:\>Get-AppLockerPolicy -Domain -LDAP "LDAP:// DC13.Contoso.com/CN={31B2F340-016D-11D2-945F-00C04FB984F9},CN=Policies,CN=System,DC=Contoso,DC=com"
```

This example gets the AppLocker policy of the unique GPO specified by the LDAP path as an AppLockerPolicy object.

### EXAMPLE 3
```
PS C:\>Get-AppLockerPolicy -Effective -Xml | Set-Content ('c:\temp\curr.xml')
```

This example gets the effective policy on the computer, and then sends it in XML-format to the specified file on an existing path.

### EXAMPLE 4
```
PS C:\>Get-AppLockerPolicy -Local | Test-AppLockerPolicy -Path C:\Windows\System32\*.exe -User Everyone
```

This example gets the local AppLocker policy on the computer, and then tests the policy using the Test-AppLockerPolicy cmdlet to test whether the .exe files in C:\Windows\System32 will be allowed to run by the Everyone group.

## PARAMETERS

### -Domain
Gets the AppLocker policy from the GPO specified by the path given in the **Ldap** parameter.

```yaml
Type: SwitchParameter
Parameter Sets: DomainPolicy
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Effective
Gets the effective AppLocker policy on the local computer.
The effective policy is the merge of the local AppLocker policy and any applied AppLocker domain policies on the local computer.

```yaml
Type: SwitchParameter
Parameter Sets: EffectivePolicy
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ldap
Specifies the LDAP path of the GPO and must specify a unique GPO.

```yaml
Type: String
Parameter Sets: DomainPolicy
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Local
Gets the AppLocker policy from the local GPO.

```yaml
Type: SwitchParameter
Parameter Sets: LocalPolicy
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Xml
Specifies that the AppLocker policy be output as an XML-formatted string.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Security.ApplicationId.PolicyManagement.PolicyModel.AppLockerPolicy
AppLockerPolicy

### System.String

## NOTES

## RELATED LINKS

[Get-AppLockerFileInformation](./Get-AppLockerFileInformation.md)

[New-AppLockerPolicy](./New-AppLockerPolicy.md)

[Set-AppLockerPolicy](./Set-AppLockerPolicy.md)

[Test-AppLockerPolicy](./Test-AppLockerPolicy.md)


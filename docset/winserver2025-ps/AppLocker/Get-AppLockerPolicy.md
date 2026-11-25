---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Security.ApplicationId.PolicyManagement.Cmdlets.dll-Help.xml
Module Name: AppLocker
ms.date: 09/28/2020
online version: https://learn.microsoft.com/powershell/module/applocker/get-applockerpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AppLockerPolicy
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
The **Get-AppLockerPolicy** cmdlet retrieves the AppLocker policy from the local Group Policy Object (GPO), a specified GPO, or the GP-deployed effective policy on the computer.

By default, the output is an **AppLockerPolicy** object.
If the *Xml* parameter is used, then the output will be the AppLocker policy as an XML-formatted string.

Note that the Get-AppLockerPolicy cmdlet only functions with policies deployed via GP. It does not have any knowledge of the AppLocker CSP, so it will return incorrect data if the policy in place has been applied via the CSP.

## EXAMPLES

### Example 1: Get an AppLocker policy
```
PS C:\> Get-AppLockerPolicy -Local
                                Version RuleCollections                         RuleCollectionTypes
                                ------- ---------------                         -------------------
                                      1 {}                                      {}
```

This example gets the local AppLocker policy as an **AppLockerPolicy** object.

### Example 2: Get the AppLocker policy for a GPO
```
PS C:\> Get-AppLockerPolicy -Domain -LDAP "LDAP:// DC13.Contoso.com/CN={31B2F340-016D-11D2-945F-00C04FB984F9},CN=Policies,CN=System,DC=Contoso,DC=com"
```

This example gets the AppLocker policy of the unique GPO specified by the LDAP path as an **AppLockerPolicy** object.

### Example 3: Get the effective policy
```
PS C:\> Get-AppLockerPolicy -Effective -Xml | Set-Content ('c:\temp\curr.xml')
```

This example gets the effective policy on the computer, and then sends it in XML-format to the specified file on an existing path.

### Example 4: Get and test an AppLocker policy
```
PS C:\> Get-AppLockerPolicy -Local | Test-AppLockerPolicy -Path C:\Windows\System32\*.exe -User Everyone
```

This example gets the local AppLocker policy on the computer, and then tests the policy using the **Test-AppLockerPolicy** cmdlet to test whether the .exe files in C:\Windows\System32 will be allowed to run by the Everyone group.

## PARAMETERS

### -Domain
Gets the AppLocker policy from the GPO specified by the path given in the *Ldap* parameter.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Security.ApplicationId.PolicyManagement.PolicyModel.AppLockerPolicy
**AppLockerPolicy**

### System.String

## NOTES

## RELATED LINKS

[Get-AppLockerFileInformation](./Get-AppLockerFileInformation.md)

[New-AppLockerPolicy](./New-AppLockerPolicy.md)

[Set-AppLockerPolicy](./Set-AppLockerPolicy.md)

[Test-AppLockerPolicy](./Test-AppLockerPolicy.md)


---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Security.ApplicationId.PolicyManagement.Cmdlets.dll-Help.xml
Module Name: AppLocker
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/applocker/test-applockerpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-AppLockerPolicy
---

# Test-AppLockerPolicy

## SYNOPSIS
Specifies the AppLocker policy to determine whether the input files will be allowed to run for a given user.

## SYNTAX

### ByXmlPolicy (Default)
```
Test-AppLockerPolicy [-XmlPolicy] <String> -Path <System.Collections.Generic.List`1[System.String]>
 [-User <String>]
 [-Filter <System.Collections.Generic.List`1[Microsoft.Security.ApplicationId.PolicyManagement.PolicyDecision]>]
 [<CommonParameters>]
```

### ByXmlPolicyAppx
```
Test-AppLockerPolicy [-XmlPolicy] <String>
 -Packages <System.Collections.Generic.List`1[Microsoft.Windows.Appx.PackageManager.Commands.AppxPackage]>
 [-User <String>]
 [-Filter <System.Collections.Generic.List`1[Microsoft.Security.ApplicationId.PolicyManagement.PolicyDecision]>]
 [<CommonParameters>]
```

### ByPolicyObject
```
Test-AppLockerPolicy [-PolicyObject] <AppLockerPolicy> -Path <System.Collections.Generic.List`1[System.String]>
 [-User <String>]
 [-Filter <System.Collections.Generic.List`1[Microsoft.Security.ApplicationId.PolicyManagement.PolicyDecision]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Test-AppLockerPolicy** cmdlet specifies the AppLocker policy to determine whether a list of files is allowed to run on the local computer for a specified user.

To test AppLocker rules for a nested group, a representative member of the nested group should be specified for the *User* parameter.
For example, a rule that allows the Everyone group to run calc.exe may not appear to apply correctly when the nested Finance group for the *User* parameter is specified.
Instead, a representative member of the Finance group should be specified for the *User* parameter.

## EXAMPLES

### Example 1: Report if programs are allowed to run
```
PS C:\> Test-AppLockerPolicy -XMLPolicy C:\Policy.xml -Path c:\windows\system32\calc.exe, C:\windows\system32\notepad.exe -User Everyone
```

This example reports if calc.exe and notepad.exe will be allowed to run for Everyone under the policy specified by C:\Policy.xml.

### Example 2: List executables specified by no policy
```
PS C:\> Get-ChildItem C:\windows\system32\*.exe | Test-AppLockerPolicy c:\Policy.xml -Filter DeniedByDefault
```

This example lists the executables under C:\Windows\System32 that everyone will be denied by the policy specified by C:\Policy.xml because there is no explicit rule for the file.

### Example 3: List executables specified by no policy to a text file
```
PS C:\> Get-AppLockerPolicy -Local | Test-AppLockerPolicy -Path C:\Windows\System32\*.exe -User contoso\saradavis -Filter Denied | Format-List -Property | Set-Content (ꞌC:\temp\DeniedFiles.txtꞌ)
```

This example gets the local AppLocker policy, uses the policy to determine which executables in C:\Windows\System32 that contoso\saradavis is explicitly denied access to run, and then redirects the list to a text file.

### Example 4: Lists packages and test against a policy
```
PS C:\> Get-AppxPackage -AllUsers | Test-AppLockerPolicy -XmlPolicy .\SamplePolicy.xml
```

This example lists all the packages installed on this computer, for all the users, and tests them against a saved policy.

## PARAMETERS

### -Filter
Specifies the policy decision by which to filter the output for each input file.
The acceptable values for this parameter are: Allowed, Denied, DeniedByDefault, or AllowedByDefault.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Security.ApplicationId.PolicyManagement.PolicyDecision]
Parameter Sets: (All)
Aliases:
Accepted values: Allowed, AllowedByDefault, Denied, DeniedByDefault

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Packages
Specifies a list of installed packaged applications, from which the file information is retrieved.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Windows.Appx.PackageManager.Commands.AppxPackage]
Parameter Sets: ByXmlPolicyAppx
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Path
Specifies the list of the file paths to test.
Regular expressions are supported.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: ByXmlPolicy, ByPolicyObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PolicyObject
Specifies the Applocker policy.
Can be obtained from the Get-AppLockerPolicy or the New-AppLockerPolicy cmdlet.

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

### -User
Defines the user or group to be used for testing the rules in a specified AppLocker policy.
The acceptable values for this parameter are:

- DNS user name (`domain\username`)
- User Principal Name (`username@domain.com`)
- SAM user name (`username`)
- Security identifier (`S-1-5-21-3165297888-301567370-576410423-1103`)

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

### -XmlPolicy
Specifies the file path and name of the XML-formatted file that contains the AppLocker policy.

```yaml
Type: String
Parameter Sets: ByXmlPolicy, ByXmlPolicyAppx
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Security.ApplicationId.PolicyManagement.PolicyModel.AppLockerPolicy
**AppLockerPolicy**

## OUTPUTS

### Microsoft.Security.ApplicationId.PolicyManagement.AppLockerPolicyDecision

## NOTES

## RELATED LINKS

[Get-AppLockerFileInformation](./Get-AppLockerFileInformation.md)

[Get-AppLockerPolicy](./Get-AppLockerPolicy.md)

[New-AppLockerPolicy](./New-AppLockerPolicy.md)

[Set-AppLockerPolicy](./Set-AppLockerPolicy.md)


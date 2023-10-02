---
external help file: Microsoft.Management.UI.PowWA.Commands.dll-Help.xml
Module Name: PowerShellWebAccess
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/powershellwebaccess/test-pswaauthorizationrule?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-PswaAuthorizationRule
---

# Test-PswaAuthorizationRule

## SYNOPSIS
Verifies whether a rule exists for a specified user, computer, or endpoint.

## SYNTAX

### ComputerName (Default)
```
Test-PswaAuthorizationRule [-ComputerName] <String> [[-ConfigurationName] <String>]
 [-Credential <PSCredential>] [-Rule <PswaAuthorizationRule[]>] [-UserName] <String> [<CommonParameters>]
```

### ConnectionUri
```
Test-PswaAuthorizationRule [[-ConfigurationName] <String>] [-Credential <PSCredential>] [-ConnectionUri] <Uri>
 [-Rule <PswaAuthorizationRule[]>] [-UserName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Test-PswaAuthorizationRule** cmdlet verifies whether a rule exists for a specified user, computer, or endpoint.
This cmdlet can also be used to test authorization rules to validate that a particular user, computer or endpoint access request is authorized. 
 
                      
By default, this cmdlet evaluates all rules in the authorization file.
However, you can specify a subset of rules to test.

You can use this cmdlet to help troubleshoot authentication failures.

The parameters for this cmdlet correspond to fields on the Windows PowerShell® Web Access sign-on page.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Test-PswaAuthorizationRule -ComputerName srv2.contoso.com -UserName contoso\mhanson -ConfigurationName test
```

This example tests all authorization rules in order to display all the rules that allow the user contoso\mhanson to connect to the computer srv2 and use a Windows PowerShell session configuration named test.

### EXAMPLE 2
```
PS C:\>Test-PswaAuthorizationRule -UserName contoso\mhanson -ComputerName *
```

This example tests all authorization rules to check which authorization rules apply to the user contoso\mhanson.

## PARAMETERS

### -ComputerName
Specifies the name of the computer to test.

```yaml
Type: String
Parameter Sets: ComputerName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigurationName
Specifies the name of the Windows PowerShell session configuration, also known as endpoint or runspace, to test.

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

### -ConnectionUri
Specifies the connection URI to test.

```yaml
Type: Uri
Parameter Sets: ConnectionUri
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a **PSCredential** object for a user account that you want to use to test Windows PowerShell Web Access authorization rules.
If you do not add this parameter, the cmdlet uses the currently logged-on user account.
To get a **PSCredential** object, which is required to test authorization rules remotely, run the Get-Credentialhttp://go.microsoft.com/fwlink/?LinkID=293936 cmdlet.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Rule
Specifies a subset of rules to test.
If this parameter is not specified, then this cmdlet tests against all authorization rules.

```yaml
Type: PswaAuthorizationRule[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -UserName
Specifies the name of the user to test.

```yaml
Type: String
Parameter Sets: (All)
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

### Microsoft.Management.PowerShellWebAccess.PswaAuthorizationRule[]
This cmdlet accepts a PswaAuthorizationRule object as input.

## OUTPUTS

### Microsoft.Management.PowerShellWebAccess.PswaAuthorizationRule[]
This cmdlet produces a PswaAuthorizationRule object as output.

## NOTES

## RELATED LINKS

[Get-Credential](https://go.microsoft.com/fwlink/?LinkID=293936)

[Add-PswaAuthorizationRule](./Add-PswaAuthorizationRule.md)

[Get-PswaAuthorizationRule](./Get-PswaAuthorizationRule.md)

[Remove-PswaAuthorizationRule](./Remove-PswaAuthorizationRule.md)

[Install-PswaWebApplication](./Install-PswaWebApplication.md)


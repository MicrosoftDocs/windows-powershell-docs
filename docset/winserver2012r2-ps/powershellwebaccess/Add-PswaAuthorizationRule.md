---
external help file: Microsoft.Management.UI.PowWA.Commands.dll-Help.xml
Module Name: PowerShellWebAccess
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/powershellwebaccess/add-pswaauthorizationrule?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-PswaAuthorizationRule
---

# Add-PswaAuthorizationRule

## SYNOPSIS
Adds a new authorization rule to the Windows PowerShell® Web Access authorization rule set.

## SYNTAX

### UserGroupNameComputerGroupName
```
Add-PswaAuthorizationRule -ComputerGroupName <String> [-ConfigurationName] <String>
 [-Credential <PSCredential>] [-RuleName <String>] -UserGroupName <String[]> [-Force] [<CommonParameters>]
```

### UserNameComputerGroupName
```
Add-PswaAuthorizationRule -ComputerGroupName <String> [-ConfigurationName] <String>
 [-Credential <PSCredential>] [-RuleName <String>] [-UserName] <String[]> [-Force] [<CommonParameters>]
```

### UserGroupNameComputerName
```
Add-PswaAuthorizationRule -ComputerName <String> [-ConfigurationName] <String> [-Credential <PSCredential>]
 [-RuleName <String>] -UserGroupName <String[]> [-Force] [<CommonParameters>]
```

### UserNameComputerName
```
Add-PswaAuthorizationRule -ComputerName <String> [-ConfigurationName] <String> [-Credential <PSCredential>]
 [-RuleName <String>] [-UserName] <String[]> [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Add-PswaAuthorizationRule** cmdlet adds a new authorization rule to the Windows PowerShell® Web Access authorization rule set.

You must specify the users, computers, and Windows PowerShell endpoints for this rule.
You can specify both users and computers either by individual user accounts and computer names, or by specifying groups.

For a computer that is joined to an Active Directory domain, the cmdlet uses the security identifier (SID) of the computer to create the rule.
This allows you to use a short name, a fully qualified domain name (FQDN), or an IP address for the **Computer Name** field on the sign-in page.

For a computer that is not joined to an Active Directory domain, the cmdlet creates the rule using the computer name provided by the administrator.
To successfully connect to this machine, the end user must provide the computer name exactly as it appears in the rule.

If there are multiple computers with the same name on the network, then short name can resolve to more than one computer.
This can lead to ambiguity when establishing a connection.
For example, if a rule exists for the workgroup computer named "Server1" and a new computer named server1.contoso.com is joined to the network, validation using the authorization rules succeeds and Windows PowerShell Web Access attempts to establish a connection to the computer named "Server1".
It is not guaranteed that the connection is established with the specified workgroup computer; the attempt could be made on either the workgroup or the domain computer named "Server1".
To reduce ambiguity, it is recommended that you use the FQDN for the destination computer whenever possible to create an authorization rule.

The authorization rules evaluate the primary sign-in credential of the Windows PowerShell Web Access users, not the alternate credentials (the second set of credentials found in the Optional connection settings section of the sign-in page).
For an example of this, see Example 6.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Add-PswaAuthorizationRule -ComputerName srv2.contoso.com -UserGroupName contoso\SMAdmins -ConfigurationName PSWAEndpoint
```

This example grants access to the session configuration PSWAEndpoint, a restricted runspace, on srv2 for users in the SMAdmins group. 
Note: The computer name must be a fully qualified domain name (FQDN).
Administrators define a restricted session configuration or runspace, which is a limited range of cmdlets and tasks that end users can run.
Defining a restricted runspace can prevent users from accessing other computers that are not in the allowed Windows PowerShell® runspace, thus offering a more secure connection.
For more information on session configurations, see about_Session_Configurationshttps://technet.microsoft.com/library/dd819508.aspx or the Windows PowerShell Web Access Helphttps://go.microsoft.com/fwlink/p/?LinkID=221050.

### EXAMPLE 2
```
PS C:\>Add-PswaAuthorizationRule -UserName contoso\user1, contoso\user2, contoso\user3 -ComputerName srv2.contoso.com -ConfigurationName Microsoft.PowerShell
```

This example grants access to the default Windows PowerShell session configuration, `Microsoft.PowerShell`, on srv2 for users in the users named contoso\user1, contoso\user2, and contoso\user3.
This cmdlet creates three rules (1 per person).

### EXAMPLE 3
```
PS C:\> "contoso\user1","contoso\user2" | Add-pswaAuthorizationRule -ComputerName srv2.contoso.com -ConfigurationName Microsoft.PowerShell
```

This example illustrates how to input user name values via the pipeline.

### EXAMPLE 4
```
PS C:\>$o = New-Object -TypeName PSObject | Add-Member -Type NoteProperty -Name "UserName" -Value "contoso\user1" -PassThru | Add-Member -Type NoteProperty -Name "ComputerName" -Value "srv2.contoso.com" -PassThru | Add-Member -Type NoteProperty -Name "ConfigurationName" -Value "Microsoft.PowerShell" -PassThru



PS C:\>$o | Add-PswaAuthorizationRule
```

This example illustrates how all parameters take values from pipeline by property name.

### EXAMPLE 5
```
PS C:\>Add-PswaAuthorizationRule -UserName PswaServer\ChrisLocal -ComputerName srv1.contoso.com -ConfigurationName Microsoft.PowerShell
```

This example adds a rule to allow the local user named PswaServer\ChrisLocal access to the server named srv1.contoso.com.

This example illustrates a scenario where the gateway is in a workgroup and the destination computer is in a domain.
The authorization rule applies to the local users on the gateway.
On the Windows PowerShell Web Access sign-in page, to successfully authenticate, the user must provide a second set of credentials in the **Optional connection settings** area.
The gateway server uses the additional set of credentials to authenticate the user on the destination computer, a server named srv1.contoso.com.

### EXAMPLE 6
```
PS C:\> Add-PswaAuthorizationRule -UserName * -ComputerName * -ConfigurationName *
```

This example allows all users access to all endpoints on all computers.
This essentially turns off authorization rules. 
Note: Use of the `*` wildcard character is not recommended for security-sensitive deployments and should only be considered for test environments or used in deployments where security can be relaxed.

## PARAMETERS

### -ComputerGroupName
Specifies the name of a computer group in Active Directory Domain Services (AD DS) or local groups to which this rule grants access.

```yaml
Type: String
Parameter Sets: UserGroupNameComputerGroupName, UserNameComputerGroupName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
Specifies the computer name to which this rule grants access.

```yaml
Type: String
Parameter Sets: UserGroupNameComputerName, UserNameComputerName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConfigurationName
Specifies the name of the Windows PowerShell session configuration, also known as runspace, to which this rule grants access.

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

### -Credential
Specifies a **PSCredential** object for a user account that you want to use to change Windows PowerShell Web Access authorization rules.
If you do not add this parameter, the cmdlet uses the currently logged-on user account.
To get a **PSCredential** object, which is required to add authorization rules remotely, run the Get-Credentialhttps://go.microsoft.com/fwlink/?LinkID=293936 cmdlet.

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

### -Force
Forces the command to run without asking for user confirmation.
                         
In addition, it also prompts for confirmation when you enter a simple or short computer name (such as a name that is not a domain name or is not fully qualified).
Confirmation is requested for security reasons, so that you can use the simple name to add a computer only if the computer is in a workgroup.

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

### -RuleName
Specifies the friendly name for this rule.

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

### -UserGroupName
Specifies the name of one or more user groups in AD DS or local groups to which this rule grants access.

```yaml
Type: String[]
Parameter Sets: UserGroupNameComputerGroupName, UserGroupNameComputerName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserName
Specifies one or more users to which this rule grants access.
The user name can be a local user account on the gateway computer or a user in AD DS. 
                         
The format is `domain\user` or `computer\user`.

```yaml
Type: String[]
Parameter Sets: UserNameComputerGroupName, UserNameComputerName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String, String[]
This cmdlet accepts a string or an array of strings as input.

## OUTPUTS

### Microsoft.Management.PowerShellWebAccess.PswaAuthorizationRule

## NOTES

## RELATED LINKS

[Add-Member](https://go.microsoft.com/fwlink/p/?LinkId=113280)

[New-Object](https://go.microsoft.com/fwlink/p/?LinkId=113355)

[Get-Credential](https://go.microsoft.com/fwlink/?LinkID=293936)

[Get-PswaAuthorizationRule](./Get-PswaAuthorizationRule.md)

[Remove-PswaAuthorizationRule](./Remove-PswaAuthorizationRule.md)

[Test-PswaAuthorizationRule](./Test-PswaAuthorizationRule.md)

[Install-PswaWebApplication](./Install-PswaWebApplication.md)


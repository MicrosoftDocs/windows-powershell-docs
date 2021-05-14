---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/add-wssmsouser?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-WssMsoUser
---

# Add-WssMsoUser

## SYNOPSIS
Add an online service account, and assign it to a user account.

## SYNTAX

```
Add-WssMsoUser [-WssUserName] <String> [-MsoUserName] <String> [[-License] <MSOLicense[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-WssMsoUser** cmdlet adds and enables an online service account to aad_1, and assigns that account to a local network user account.

## EXAMPLES

### Example 1: Add an online account
```
PS C:\> Add-WSSMSOUser -WssUserName "DavidChew" -MsoUserName "DavidChew@TSQA.Contoso.com"
```

This command adds an online service account DavidChew@TSQA.Contoso.com and assigns it to the local network user account named DavidChew.

### 1:
```
PS C:\>
```

## PARAMETERS

### -License
Specifies an array of user licenses.
Specifies an array of licenses as **MSOLicense** objects.
The cmdlet assigns the licenses that you specify to the user account.
To obtain **MSOLicense** objects, use the Get-WssMsoSubscription cmdlet to get subscription information.
Subscription information contains the **MSOLicenseSuite** array that refers to **MSOLicense** objects.

```yaml
Type: MSOLicense[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MsoUserName
Specifies a user principal name (UPN).
The cmdlet adds an online service account that has the UPN that you specify.

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

### -WssUserName
Specifies the name of a user account.
The cmdlet assigns an online service account to the user account that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
WssUserName
Type: System.String
Description: local network account name of user

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-WssMsoUser](./Disable-WssMsoUser.md)

[Enable-WssMsoUser](./Enable-WssMsoUser.md)

[Get-WssMsoUser](./Get-WssMsoUser.md)

[Remove-WssMsoUser](./Remove-WssMsoUser.md)


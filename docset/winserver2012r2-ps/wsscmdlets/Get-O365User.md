---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-o365user?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-O365User
---

# Get-O365User

## SYNOPSIS
Gets an office_365_2 account.

## SYNTAX

```
Get-O365User [-O365AccountUPN] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-O365User** cmdlet gets an office_365_1 account.

## EXAMPLES

### Example 1: Get an office_365_2 accountoffice_365_2
```
PS C:\> Get-O365User -O365AccountUPN "PattiFuller@contoso.onmicrosoft.com"
```

This command gets the office_365_2 account that has the UPN PattiFuller@contoso.onmicrosoft.com.

### 1:
```
PS C:\>
```

## PARAMETERS

### -O365AccountUPN
Specifies a user principal name (UPN).
The cmdlet gets the office_365_2 user account that has the UPN that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
LocalAccountName
Type: System.String
Description: local user name

## OUTPUTS

### Microsoft.WindowsServerSolutions.O365Integration.O365User
This cmdlet returns a class that represents an office_365_2 online account.
When output: office_365_2 online account exists
ObjectId Property System.Guid
UserPrincipalName Property System.String
Activated Property System.Boolean
LocalUserName Property System.String
Licenses Property System.Collections.ObjectModel.ReadOnlyCollection\<O365UserLicense\>

## NOTES

## RELATED LINKS

[Add-O365User](./Add-O365User.md)

[Enable-O365User](./Enable-O365User.md)

[Disable-O365User](./Disable-O365User.md)

[Remove-O365User](./Remove-O365User.md)


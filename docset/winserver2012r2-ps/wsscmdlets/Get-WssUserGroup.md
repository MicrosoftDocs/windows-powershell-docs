---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssusergroup?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssUserGroup
---

# Get-WssUserGroup

## SYNOPSIS
Gets user groups.

## SYNTAX

### AllParamSet (Default)
```
Get-WssUserGroup [<CommonParameters>]
```

### ByNameParamSet
```
Get-WssUserGroup [-Name <String>] [<CommonParameters>]
```

### BySidParamSet
```
Get-WssUserGroup [-Sid <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssUserGroup** cmdlet gets Windows Server Essentials user groups.
If you do not specify the name or security identifier (SID) of a group, the cmdlet gets all user groups.

## EXAMPLES

### Example 1: Get a user group by specifying a name
```
PS C:\> Get-WssUserGroup -Name "Support"
```

This command gets the user group named Support.

### 1:
```
PS C:\>
```

## PARAMETERS

### -Name
Specifies a name.
The cmdlet gets the user group that has the name that you specify.

```yaml
Type: String
Parameter Sets: ByNameParamSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sid
Specifies a SID.
The cmdlet gets the user group that has the SID that you specify.

```yaml
Type: String
Parameter Sets: BySidParamSet
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

## OUTPUTS

### Microsoft.WindowsServerSolutions.Groups.Group

## NOTES

## RELATED LINKS

[Add-WssUserGroup](./Add-WssUserGroup.md)

[Remove-WssUserGroup](./Remove-WssUserGroup.md)

[Set-WssUserGroup](./Set-WssUserGroup.md)


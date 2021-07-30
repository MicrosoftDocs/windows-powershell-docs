---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/set-wsspasswordpolicy?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WssPasswordPolicy
---

# Set-WssPasswordPolicy

## SYNOPSIS
Modifies password policy requirements for the server.

## SYNTAX

```
Set-WssPasswordPolicy [-Strength] <WssPasswordPolicy> [-PasswordNeverExpire] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssPasswordPolicy** cmdlet modifies password policy requirements for the server.

## EXAMPLES

### Example 1: Modify the password policy
```
PS C:\> Set-WssPasswordPolicy -Strength Strong -PasswordNeverExpire
```

This command changes the password policy to require Strong passwords.
Passwords never expire.

### 1:
```
PS C:\>
```

## PARAMETERS

### -PasswordNeverExpire
Indicates that passwords never expire.
If you do not specify this parameter, passwords expire after 180 days.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Strength
Specifies the password strength for the server.
The acceptable values for this parameter are:

- Weak.
Passwords are not blank.
- Medium.
Passwords must contain at least five characters.
- MediumStrong.
Passwords must contain at least five characters, and must contain at least three of the following categories: uppercase letters, lowercase letters, numbers, and symbols.
- Strong.
Passwords must contain at least seven characters, and must contain at least three of the following categories: uppercase letters, lowercase letters, numbers, and symbols.

```yaml
Type: WssPasswordPolicy
Parameter Sets: (All)
Aliases: 
Accepted values: Weak, Medium, MediumStrong, Strong

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssPasswordPolicy](./Get-WssPasswordPolicy.md)


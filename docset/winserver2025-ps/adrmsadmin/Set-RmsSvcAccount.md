---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
Module Name: ADRMSADMIN
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adrmsadmin/set-rmssvcaccount?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-RmsSvcAccount
---

# Set-RmsSvcAccount

## SYNOPSIS
Sets the service account for an AD RMS cluster.

## SYNTAX

```
Set-RmsSvcAccount [-Credential] <PSCredential> [-Force] [-PassThru] [-Path] <String[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-RmsSvcAccount** cmdlet sets the service account of an Active Directory Rights Management Services (AD RMS) cluster.

To specify the service account, set the *Credential* parameter to the service account credentials, and then set the *Path* parameter to `<PSDrive>:\` where `<PSDrive>` is the AD RMS provider drive ID.

## EXAMPLES

### Example 1: Modify the service account
```
PS C:\> Set-RmsSvcAccount -Path "."
```

This command changes the AD RMS service account.
Because the *Credential* parameter is not used, the **Set-RmsSvcAccount** cmdlet prompts for the user name and password of the new service account.

### Example 2: Modify the service account with specified credentials
```
PS C:\> Set-RmsSvcAccount -Path "." -Force -PassThru -Credential ITDOMAIN\adrmssvc
```

This command changes the AD RMS service account.
Because the *Credential* parameter specifies the domain and user name of the account, the **Set-RmsSvcAccount** cmdlet prompts for the password of the new service account.

### Example 3: Get credentials to use to modify a service account
```
PS C:\> $userAccount = Get-Credential ITDOMAIN\adrmssvc
PS C:\> Set-RmsSvcAccount -Path "." -Force -PassThru -Credential $userAccount
```

This command uses the **Get-Credential** cmdlet to prompt for the password for the ITDOMAIN\adrmsvc account and then stores the account credentials securely in a variable, which is then passed to the **Set-RmsSvcAccount** cmdlet.

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

### -Credential
Specifies a user name and password as a **PSCredential** object.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Overrides restrictions that prevent the command from succeeding if the restrictions do not compromise security.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Path
Specifies a provider drive and path or relative path on the current drive.
Use a dot (.) to specify the current location.
This parameter does not accept wildcards and has no default value.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PSCredential

## NOTES

## RELATED LINKS

[Using Windows PowerShell with AD RMS](https://go.microsoft.com/fwlink/?LinkId=136806)

[Get-RmsSvcAccount](./Get-RmsSvcAccount.md)


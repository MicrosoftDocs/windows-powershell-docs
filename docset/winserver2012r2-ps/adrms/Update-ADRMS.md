---
external help file: Microsoft.RightsManagementServices.Configuration.dll-Help.xml
Module Name: ADRMS
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/adrms/update-adrms?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Update-ADRMS
---

# Update-ADRMS

## SYNOPSIS
Updates an existing deployment of rms_2 Server.

## SYNTAX

```
Update-ADRMS [-ServiceAccount] <PSCredential> [[-PrivateKeyPassword] <SecureString>] [[-NewCspName] <String>]
 [-UpdateCryptographicModeOnly] [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Update-ADRMS cmdlet updates the Active Directory Rights Management Services (AD RMS) server role on a server that has been upgraded to this version of Windows.
The cmdlet can also be used to update the rms_2 cryptographic mode on a server.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>$mySecureStringPassword = ConvertTo-SecureString -String <password> -AsPlainText -Force
$myCred = Get-Credential
Update-ADRMS -PrivateKeyPassword $mySecureStringPassword -ServiceAccount $myCred
```

Description

-----------

Upgrades an rms_2 server and cluster that is using a cluster key password.
The password must be specified securely as console input.
The **Get-Credential** cmdlet will launch a popup dialog to enter the rms_2 Service Account credentials (username and password) that are also required to upgrade rms_2.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>$myCred = Get-Credential
Update-ADRMS -UpdateCryptographicModeOnly -ServiceAccount $myCred
```

Description

-----------

Updates an rms_2 server that is using a cluster key password to cryptographic mode 2.
The **Get-Credential** command will launch a popup dialog to enter the rms_2 Service Account credentials (username and password) which are required for this update.
The cluster key password is not required; but if the server is using CSP key storage, the **-NewCspName** parameter must be included.

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
Specifies user credentials to use for the update process.
If this parameter is specified, you will be prompted to enter credentials.
This parameter operates in a similar manner to the RunAs command.

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
Forces completion of the command by overriding restrictions that would prevent it from succeeding (so long as a the changes made do not compromise security).

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewCspName
Specifies the new name of the cryptographic service provider (CSP) to use for storing the private key of the rms_2 server.
This parameter is used in combination with the **-UpdateCryptographicMode** parameter for rms_2 servers that are using CSP key storage.

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

### -PrivateKeyPassword
Specifies the password for the AD RMS centrally managed key.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceAccount
Specifies the identity of the domain account that is used for the rms_2 service account.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateCryptographicModeOnly
If set, indicates that only the cryptographic mode of the server is to be updated.
To update the cryptographic mode of an rms_2 server, you must be logged in with an account that has membership in the local rms_2 Enterprise Administrators Group on that server.
If the rms_2 server is using CSP key storage, the **-NewCspName** parameter should also be specified.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### SwitchParameter, string, PSCredential, SecureString

## OUTPUTS

## NOTES

## RELATED LINKS


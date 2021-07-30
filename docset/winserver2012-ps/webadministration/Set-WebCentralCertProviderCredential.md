---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: https://docs.microsoft.com/powershell/module/webadministration/set-webcentralcertprovidercredential?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-WebCentralCertProviderCredential

## SYNOPSIS
Sets the user-account credentials for the central certificate provider.

## SYNTAX

```
Set-WebCentralCertProviderCredential [-UserName] <String> [<CommonParameters>]
```

## DESCRIPTION
Sets the user-account credentials (user name and password) for the central certificate provider.

## EXAMPLES

### Example 1: Set credentials
```
PS C:\>Set-WebCentralCertProviderCredentials -UserName CertStoreUser
UserName=CertStoreUser

Password=

*********

Confirm Password=

*********
```

Sets the user account credentials for the central certificate store.

## PARAMETERS

### -UserName
Password for the user account that is used to access the central certificate store.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Clear-WebCentralCertProvider](./Clear-WebCentralCertProvider.md)

[Disable-WebCentralCertProvider](./Disable-WebCentralCertProvider.md)

[Get-WebCentralCertProvider](./Get-WebCentralCertProvider.md)

[Set-WebCentralCertProvider](./Set-WebCentralCertProvider.md)


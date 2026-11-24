---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
Module Name: IISAdministration
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iisadministration/get-iiscentralcertprovider?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IISCentralCertProvider
---

# Get-IISCentralCertProvider

## SYNOPSIS
Gets information about the IIS central certificate store.

## SYNTAX

```
Get-IISCentralCertProvider [-CertStoreLocation] [-UserName] [-PrivateKeyPassword] [-Enabled]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-IISCentralCertProvider** cmdlet returns information about the IIS central certificate store.
The central certificate store allows you to store all your IIS certificates in a centralized location (such as a file share); IIS servers then retrieve certificate from this centralized location.
That means that you only have to install certificates in one location; there is no need to install the same certificate on each and every IIS server.

Called without any parameters, **Get-IISCentralCertProvider** returns information for all the certificate store property values.
Alternatively, you can include one or more optional parameters in order to limit the returned data only to the specified properties.
For example, this command limits the returned data to the **Enabled** property:

Get-IISCentralCertProvider -Enabled

## EXAMPLES

### Example 1
```
PS C:\> Get-IISCentralCertProvider
```

This command returns information about the IIS central certificate store.
Because no parameters are used when running this command **Get-IISCentralCertProvider** returns information for all the certificate store properties.

### Example 2
```
PS C:\> Get-IISCentralCertProvider -CertStoreLocation -UserName
```

This command returns information for two properties of the IIS central certificate store: the store location (**CertStoreLocation**) and the name of the user account used for accessing the store (**UserName**).
Values for other properties (such as the private key password) are not returned.
To return all the property values leave off all parameter when calling **Get-IISCentralCertProvider**.

## PARAMETERS

### -CertStoreLocation
Indicates that the certificate store location will be returned when running the command.
If no parameters are specified when calling **Get-IISCentralCertProvider** then information will be returned for all the property values.

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

### -Enabled
Indicates that the current state of the central store (enabled or disabled) will be returned when running the command.
If no parameters are specified when calling **Get-IISCentralCertProvider** then information will be returned for all the property values.

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

### -PrivateKeyPassword
Indicates that the private key password will be returned when running the command.
If no parameters are specified when calling **Get-IISCentralCertProvider** then information will be returned for all the property values.

Note that the password itself will not be displayed on screen; instead, you will only see a series of asterisks (*******).
While this does not tell you what the private key password is, it does let you know that a private key password has been configured for the certificate store.
If no value is returned for the **PrivateKeyPassword** property that means that no private key password has been assigned to the certificate store.

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

### -UserName
Indicates that the central store user account name will be returned when running the command.
If no parameters are specified when calling **Get-IISCentralCertProvider** then information will be returned for all the property values.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Clear-IISCentralCertProvider](./Clear-IISCentralCertProvider.md)

[Disable-IISCentralCertProvider](./Disable-IISCentralCertProvider.md)

[Enable-IISCentralCertProvider](./Enable-IISCentralCertProvider.md)

[Set-IISCentralCertProvider](./Set-IISCentralCertProvider.md)

[Set-IISCentralCertProviderCredential](./Set-IISCentralCertProviderCredential.md)


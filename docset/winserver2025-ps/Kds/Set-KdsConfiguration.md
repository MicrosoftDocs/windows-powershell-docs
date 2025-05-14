---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.KeyDistributionService.Cmdlets.dll-Help.xml
Module Name: KDS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/kds/set-kdsconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-KdsConfiguration
---

# Set-KdsConfiguration

## SYNOPSIS
Sets the configuration of Microsoft Group KdsSvc.

## SYNTAX

### KdsConfiguration
```
Set-KdsConfiguration [-LocalTestOnly] [-SecretAgreementPublicKeyLength <Int32>]
 [-SecretAgreementPrivateKeyLength <Int32>] [-SecretAgreementParameters <Byte[]>]
 [-SecretAgreementAlgorithm <String>] [-KdfParameters <Byte[]>] [-KdfAlgorithm <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### RevertToDefault
```
Set-KdsConfiguration [-LocalTestOnly] [-RevertToDefault] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Set-KdsConfiguration [-LocalTestOnly] [-InputObject] <KdsServerConfiguration> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-KdsConfiguration** cmdlet sets the configuration of Microsoft Group Key Distribution Service (KdsSvc).
This cmdlet sets the following configuration data:

- The key derivation function algorithm and parameters used to generate private group keys
- The secret agreement algorithm and parameters used to generate public group keys

This cmdlet also validates input by performing key derivation function tests and secret agreement tests.

## EXAMPLES

### Example 1: Set the configuration of Microsoft Group Key Distribution Service
```
PS C:\> $config = Get-KdsConfiguration
PS C:\> Set-KdsConfiguration -InputObject $config
```

This command retrieves a server configuration object in to a variable $config using the **Get-KdsConfiguration** cmdlet, and passes the contents of the variable to this cmdlet.

### Example 2: Test the configuration on the local server
```
PS C:\> Set-KdsConfiguration -LocalTestOnly
```

This command tests the local server configuration.

### Example 3: Set the key derivation function algorithm
```
PS C:\> Set-KdsConfiguration -KdfAlgorithm "SHA-1"
```

This command sets the key derivation function (KDF) algorithm name to SHA-1.
This algorithm generates a private group key.

### Example 4: Set the secret agreement algorithm
```
PS C:\> Set-KdsConfiguration -SecretAgreementAlgorithm "ECDH"
```

This command sets the secret agreement algorithm name to ECDH.
This algorithm generates a public group key.

### Example 5: Set the Group Key Distribution Service configuration to the default configuration
```
PS C:\> Set-KdsConfiguration -RevertToDefault
```

This command validates that the customized group key distribution service configurations are deleted and the SID key starts to use the default configuration.

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

### -InputObject
Specifies the server configuration object that contains the configuration information of the Microsoft Group KdsSvc.

```yaml
Type: KdsServerConfiguration
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -KdfAlgorithm
Specifies the name of the key derivation function algorithm that the key distribution server uses to generate the keys.

```yaml
Type: String
Parameter Sets: KdsConfiguration
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KdfParameters
Specifies the parameters for the key derivation function used to generate the group private key.
If this parameter is not specified or this parameter is set to $Null, then no key derivation function parameters are needed.

```yaml
Type: Byte[]
Parameter Sets: KdsConfiguration
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LocalTestOnly
Indicates that the cmdlet only validates the new group key distribution service configuration on the local computer, and does not store the key in Active Directory.

If this parameter is specified, then the cmdlet returns a value that indicates whether the test passed.

If this parameter is not specified, then the cmdlet returns the new server configuration object.

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

### -RevertToDefault
Indicates that the customized service configuration is reverted to the default configuration.

```yaml
Type: SwitchParameter
Parameter Sets: RevertToDefault
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecretAgreementAlgorithm
Specifies the name of the secret agreement algorithm used to generate a group public key.

```yaml
Type: String
Parameter Sets: KdsConfiguration
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SecretAgreementParameters
Specifies the parameters for the secret agreement algorithm.
If this parameter is not specified or this parameter is set to $Null, then no secret agreement algorithm parameters are needed.

```yaml
Type: Byte[]
Parameter Sets: KdsConfiguration
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SecretAgreementPrivateKeyLength
Specifies the length of the private key used in the secret agreement algorithm.

```yaml
Type: Int32
Parameter Sets: KdsConfiguration
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SecretAgreementPublicKeyLength
Specifies the length of the public key used in the secret agreement algorithm.

```yaml
Type: Int32
Parameter Sets: KdsConfiguration
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.KeyDistributionService.KdsServerConfiguration
This cmdlet returns a **KdsServerConfiguration** object that contains configuration information for the Microsoft Group KdsSvc.

## OUTPUTS

### Microsoft.KeyDistributionService.KdsServerConfiguration

### System.Boolean

## NOTES

## RELATED LINKS

[Add-KdsRootKey](./Add-KdsRootKey.md)

[Clear-KdsCache](./Clear-KdsCache.md)

[Get-KdsConfiguration](./Get-KdsConfiguration.md)

[Get-KdsRootKey](./Get-KdsRootKey.md)

[Test-KdsRootKey](./Test-KdsRootKey.md)


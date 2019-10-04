---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.WindowsAuthenticationProtocols.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.assetid: BE7DBA03-4544-4996-BEFA-0DF041BFFE86
ms.author: v-anbarr
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-TlsCipherSuite
ms.reviewer:
---

# Get-TlsCipherSuite

## SYNOPSIS
Gets the list of cipher suites for TLS for a computer.

## SYNTAX

```
Get-TlsCipherSuite [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-TlsCipherSuite** cmdlet gets the ordered list of cipher suites for a computer that Transport Layer Security (TLS) can use.

For more information about the TLS cipher suites, see the documentation for the Enable-TlsCipherSuite cmdlet or type `Get-Help Enable-TlsCipherSuite`.

For more information about protocol versions , see [BCRYPT_KDF_TLS_PRF (L"TLS_PRF")](https://docs.microsoft.com/windows/desktop/api/bcrypt/nf-bcrypt-bcryptderivekey#bcrypt_kdf_tls_prf-ltls_prf) .

## EXAMPLES

### Example 1: Get all cipher suites
```
PS C:\>Get-TlsCipherSuite
KeyType               : 0
Certificate           : RSA
MaximumExchangeLength : 65536
MinimumExchangeLength : 0
Exchange              : ECDH
HashLength            : 0
Hash                  : 
CipherBlockLength     : 16
CipherLength          : 256
BaseCipherSuite       : 49200
CipherSuite           : 49200
Cipher                : AES
Name                  : TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384
Protocols             : {771}


KeyType               : 0
Certificate           : RSA
MaximumExchangeLength : 65536
MinimumExchangeLength : 0
Exchange              : ECDH
HashLength            : 0
Hash                  : 
CipherBlockLength     : 16
CipherLength          : 128
BaseCipherSuite       : 49199
CipherSuite           : 49199
Cipher                : AES
Name                  : TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256
Protocols             : {771}
```

This command gets all TLS cipher suites for the computer.

### Example 2: Get the cipher suites that match a string
```
PS C:\>Get-TlsCipherSuite -Name "AES"
KeyType               : 0
Certificate           : ECDSA
MaximumExchangeLength : 65536
MinimumExchangeLength : 0
Exchange              : ECDH
HashLength            : 0
Hash                  :
CipherBlockLength     : 16
CipherLength          : 256
BaseCipherSuite       : 49196
CipherSuite           : 49196
Cipher                : AES
Name                  : TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384
Protocols             : {771, 65277}

KeyType               : 0
Certificate           : ECDSA
MaximumExchangeLength : 65536
MinimumExchangeLength : 0
Exchange              : ECDH
HashLength            : 0
Hash                  :
CipherBlockLength     : 16
CipherLength          : 128
BaseCipherSuite       : 49195
CipherSuite           : 49195
Cipher                : AES
Name                  : TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256
Protocols             : {771, 65277}
```

This command gets all the cipher suites that have names that contain the string AES.
The output includes a field for the TLS/SSL protocols supported by the cipher. See [Cipher Suites in TLS/SSL (Schannel SSP)](https://docs.microsoft.com/windows/desktop/secauthn/cipher-suites-in-schannel) for more information.


## PARAMETERS

### -Name
Specifies the name of the TLS cipher suite to get.
The cmdlet gets cipher suites that match the string that this cmdlet specifies, so you can specify a partial name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-TlsCipherSuite](./Disable-TlsCipherSuite.md)

[Enable-TlsCipherSuite](./Enable-TlsCipherSuite.md)


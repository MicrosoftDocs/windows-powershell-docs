---
author: brianlic-msft
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.WindowsAuthenticationProtocols.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.assetid: BE7DBA03-4544-4996-BEFA-0DF041BFFE86
ms.author: brianlic
ms.date: 2016-12-20
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-TlsCipherSuite
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
PS C:\>Get-TlsCipherSuite -Name "SSL"
KeyType               : 0
Certificate           : RSA
MaximumExchangeLength : 16384
MinimumExchangeLength : 512
Exchange              : RSA
HashLength            : 128
Hash                  : MD5
CipherBlockLength     : 1
CipherLength          : 128
BaseCipherSuite       : 65664
CipherSuite           : 65664
Cipher                : RC4
Name                  : SSL_CK_RC4_128_WITH_MD5
Protocols             : {2}

KeyType               : 0
Certificate           : 
MaximumExchangeLength : 0
MinimumExchangeLength : 0
Exchange              : 
HashLength            : 0
Hash                  : 
CipherBlockLength     : 0
CipherLength          : 0
BaseCipherSuite       : 0
CipherSuite           : 0
Cipher                : 
Name                  : SSL_CK_DES_192_EDE3_CBC_WITH_MD5
Protocols             : {}
```

This command gets all the cipher suites that have names that contain the string SSL.

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


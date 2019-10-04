---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.WindowsAuthenticationProtocols.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.assetid: C34206C9-28D4-4525-BBF2-D8FCEF6F5BF3
ms.author: v-anbarr
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Disable-TlsCipherSuite
ms.reviewer:
---

# Disable-TlsCipherSuite

## SYNOPSIS
Disables a TLS cipher suite.

## SYNTAX

```
Disable-TlsCipherSuite [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-TlsCipherSuite** cmdlet disables a cipher suite.
This cmdlet removes the cipher suite from the list of Transport Layer Security (TLS) protocol cipher suites for the computer.

For more information about the TLS cipher suites, see the documentation for the Enable-TlsCipherSuite cmdlet or type `Get-Help Enable-TlsCipherSuite`.

## EXAMPLES

### Example 1: Disable a cipher suite
```
PS C:\>Disable-TlsCipherSuite -Name "TLS_RSA_WITH_3DES_EDE_CBC_SHA"
```

This command disables the cipher suite named TLS_RSA_WITH_3DES_EDE_CBC_SHA.
The command removes the cipher suite from the list of TLS protocol cipher suites.

## PARAMETERS

### -Name
Specifies the name of the TLS cipher suite to disable.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

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

## NOTES

## RELATED LINKS

[Enable-TlsCipherSuite](./Enable-TlsCipherSuite.md)

[Get-TlsCipherSuite](./Get-TlsCipherSuite.md)


---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.SecureBoot.Commands.dll-Help.xml
Module Name: SecureBoot
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/secureboot/get-securebootuefi?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SecureBootUEFI
---

# Get-SecureBootUEFI

## SYNOPSIS
Gets the UEFI variable values related to Secure Boot.

## SYNTAX

```
Get-SecureBootUEFI [-Name] <String> [-OutputFilePath <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SecureBootUEFI** cmdlet gets the UEFI variable values related to Secure Boot which are: SetupMode, SecureBoot, KEK, PK, SignatureDatabase (DB), and forbidden SignatureDatabase (DBX).

If the computer does not support Secure Boot or is a BIOS (non-UEFI) computer, this cmdlet displays the following:

`Cmdlet not supported on this platform.`

If the variable does not exist, this cmdlet displays the following:

`Variable is currently undefined.`

If Windows PowerShell® is not run in administrator mode, this cmdlet displays the following:

`Unable to set proper privileges.
Access was denied.`

## EXAMPLES

### Example 1: Get information about PK
```
PS C:\>Get-SecureBootUefi -Name PK | Format-List
Name       : PK
Bytes      : {161, 89, 192, 165...}
Attributes : NON VOLATILE
             BOOTSERVICE ACCESS
             RUNTIME ACCESS
             TIME BASED AUTHENTICATED WRITE ACCESS
```

This command gets information about PK from the UEFI variable.

## PARAMETERS

### -Name
Specifies the name of the UEFI environment variable.

```yaml
Type: String
Parameter Sets: (All)
Aliases: n
Accepted values: PK, KEK, db, dbx, SetupMode, SecureBoot, PKDefault, KEKDefault, dbDefault, dbxDefault, dbt, dbtDefault

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -OutputFilePath
Specifies the output file path of the UEFI environment variable.

```yaml
Type: String
Parameter Sets: (All)
Aliases: f

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
You can pipe a string that represents the UEFI variable name to this cmdlet.

## OUTPUTS

### Microsoft.SecureBoot.Commands.UEFIEnvironmentVariable
This cmdlet returns a **UEFIEnvironmentVariable** object that contains the following properties:

- **Name**
- **Bytes**
- **Attributes**

## NOTES

## RELATED LINKS

[Confirm-SecureBootUEFI](./Confirm-SecureBootUEFI.md)

[Format-SecureBootUEFI](./Format-SecureBootUEFI.md)

[Get-SecureBootPolicy](./Get-SecureBootPolicy.md)

[Set-SecureBootUEFI](./Set-SecureBootUEFI.md)


---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.SecureBoot.Commands.dll-Help.xml
Module Name: SecureBoot
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/secureboot/set-securebootuefi?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-SecureBootUEFI
---

# Set-SecureBootUEFI

## SYNOPSIS
Sets the Secure Boot-related UEFI variables.

## SYNTAX

### ContentsFromFile
```
Set-SecureBootUEFI -Name <String> [-ContentFilePath <String>] [-SignedFilePath <String>] -Time <String>
 [-AppendWrite] [-OutputFilePath <String>] [<CommonParameters>]
```

### ContentsFromByteArray
```
Set-SecureBootUEFI -Name <String> [-Content <Byte[]>] [-SignedFilePath <String>] -Time <String> [-AppendWrite]
 [-OutputFilePath <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SecureBootUEFI** cmdlet takes a formatted content object that is created by running the Format-SecureBootUEFI cmdlet and a signed file, combines the two and then attempts to set the package in one of the Secure Boot variables.
The supported Secure Boot variables include Platform Key (PK), Key Exchange Key (KEK), Signature Database (DB), and Forbidden Signature Database (DBX).

If successful, this cmdlet returns a **UEFIEnvironmentVariable** object.
Otherwise, it displays an error.

This cmdlet runs on both UEFI and BIOS (non-UEFI) computers.
If the computer does not support Secure Boot or is a non-UEFI computer, this cmdlet displays the following:

`Cmdlet not supported on this platform.`

If you do not run Windows PowerShell® in administrator mode, this cmdlet displays the following:

`Unable to set proper privileges.
Access was denied.`

If you supply a signed file to this cmdlet that is not valid, this cmdlet displays the following:

`Incorrect authentication data.`

## EXAMPLES

### Example 1: Set the DBX UEFI variable
```
PS C:\> $ObjectFromFormat = ( Format-SecureBootUEFI -Name DBX -SignatureOwner 12345678-1234-1234-1234-123456789abc -Algorithm SHA256 -Hash 0011223344556677889900112233445566778899001122334455667788990011 -SignableFilePath GeneratedFileToSign.bin -Time 2011-11-01T13:30:00Z -AppendWrite )
PS C:\> .\signtool.exe sign /fd sha256 /p7 .\ /p7co 1.2.840.113549.1.7.1 /p7ce DetachedSignedData /a /f PrivateKey.pfx GeneratedFileToSign.bin
PS C:\> $ObjectFromFormat | Set-SecureBootUEFI -SignedFilePath GeneratedFileToSign.bin.p7
Name       : dbx
Bytes      : {161, 89, 192, 165...}
Attributes : NON VOLATILE
             BOOTSERVICE ACCESS
             RUNTIME ACCESS
             TIME BASED AUTHENTICATED WRITE ACCESS
```

This example sets the information obtained from the Format-SecureBootUEFI cmdlet to the DBX UEFI variable.

The first command supplies a path to the signed package to be authenticated.
The file named GeneratedFileToSign.bin is a digest created by the Format-SecureBootUEFI cmdlet that needs to be signed according to the UEFI specification.

The second command runs the SignTool.exe tool from the current directory to sign the digest.
The SignTool.exe tool can be downloaded from [Windows Software Development Kit (SDK) for Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=236500) on MSDN.

The third command sets the information.

### Example 2: Set the DBX UEFI variable by using a signed package
```
PS C:\> Set-SecureBootUEFI -ContentFilePath FormattedVariable.bin -SignedFilePath GeneratedFileToSign.bin.p7
Name       : dbx
Bytes      : {161, 89, 192, 165...}
Attributes : NON VOLATILE
             BOOTSERVICE ACCESS
             RUNTIME ACCESS
             TIME BASED AUTHENTICATED WRITE ACCESS
```

This command sets the formatted data that was written to file FormattedVariable.bin to the DBX UEFI variable.
This cmdlet supplies a path to the signed package to be authenticated.

### Example 3: Set the DBX UEFI variable by using unsigned data
```
PS C:\> $objectFromFormat = ( Format-SecureBootUEFI -Name DB -SignatureOwner 12345678-1234-1234-1234-123456789abc -Time 2011-11-01T13:30:00Z -CertificateFilePath db.cer -FormatWithCert )
PS C:\> $objectFromFormat | Set-SecureBootUEFI
Name       : db
Bytes      : {161, 89, 192, 165...}
Attributes : NON VOLATILE
             BOOTSERVICE ACCESS
             RUNTIME ACCESS
             TIME BASED AUTHENTICATED WRITE ACCESS
```

This example creates formatted data that is not signed and sets the unsigned data into the UEFI variable named db.

## PARAMETERS

### -AppendWrite
Indicates that the contents of the current variable are appended instead of overwritten.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: append

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Content
Specifies the byte contents of the variable that is being set.

```yaml
Type: Byte[]
Parameter Sets: ContentsFromByteArray
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ContentFilePath
Specifies the file that contains the contents that is being set to the environment variable.

If you specify only the name, the file must be in the current working directory.
Otherwise, specify the full path of the file.

```yaml
Type: String
Parameter Sets: ContentsFromFile
Aliases: f

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the UEFI environment variable.
The acceptable values for this parameter are: PK, KEK, DB, and DBX.

```yaml
Type: String
Parameter Sets: (All)
Aliases: n
Accepted values: PK, KEK, db, dbx

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OutputFilePath
Specifies the name of the file created that contains the contents of what is set.
If you specify this parameter, instead of setting the variable, the cmdlet stores the contents in this file.

The file is created in the specified path location.

```yaml
Type: String
Parameter Sets: (All)
Aliases: of

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignedFilePath
Specifies the signed data that is paired with the contents that are being set to the environment variable.

If you specify only the name, the file must be in the current working directory.
Otherwise, specify the full path of the file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: s

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Time
Specifies the timestamp that is used in the signature.
Format this value as follows so that it is accepted as a **DateTime** object:

`"2011-11-01T13:30:00Z"`

```yaml
Type: String
Parameter Sets: (All)
Aliases: t

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.SecureBoot.Commands.UEFIFormattedVariable
This command accepts a **UEFIFormattedVariable** object that contains the information for the *Name*, *Time*, *Content*, and *AppendWrite* parameters.

## OUTPUTS

### Microsoft.SecureBoot.Commands.UEFIEnvironmentVariable
This cmdlet returns a **UEFIEnvironmentVariable** object that contains the following properties:

- **Name**
- **Guid**
- **Bytes**
- **Attributes**

## NOTES

## RELATED LINKS

[Confirm-SecureBootUEFI](./Confirm-SecureBootUEFI.md)

[Format-SecureBootUEFI](./Format-SecureBootUEFI.md)

[Get-SecureBootPolicy](./Get-SecureBootPolicy.md)

[Get-SecureBootUEFI](./Get-SecureBootUEFI.md)


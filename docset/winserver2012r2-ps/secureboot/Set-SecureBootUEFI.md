---
external help file: Microsoft.SecureBoot.Commands.dll-Help.xml
Module Name: SecureBoot
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/secureboot/set-securebootuefi?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-SecureBootUEFI
---

# Set-SecureBootUEFI

## SYNOPSIS
Sets the Secure Boot-related UEFI variables such as Platform Key, Key Exchange Key, Signature Database and Forbidden Signature Database.

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
The **Set-SecureBootUEFI** cmdlet takes a formatted content object that is created by running the Format-SecureBootUEFI cmdlet and a signed file, combines the twos and attempts to set the package in one of the Secure Boot variables.
The supported Secure Boot variables include Platform Key (PK), Key Exchange Key (KEK), Signature Database (DB), and Forbidden Signature Database (DBX).

This cmdlet returns an UEFIEnvironmentVariable object if successful, otherwise displays an error.

This cmdlet runs on both UEFI and BIOS (non-UEFI) computer.If the computer does not support Secure Boot or is a non-UEFI computer, then this cmdlet returns an error displaying the following: `Cmdlet not supported on this platform.`

If Windows PowerShell® is not run in administrator mode, then this cmdlet returns an error displaying the following: `Unable to set proper privileges.
Access was denied.`

If the signed file supplied to this cmdlet is not valid, then this cmdlet returns an error displaying the following: `Incorrect authentication data.`

## EXAMPLES

### EXAMPLE 1
```
PS C:\> $objectFromFormat = ( Format-SecureBootUEFI -Name DBX -SignatureOwner 12345678-1234-1234-1234-123456789abc -Algorithm SHA256 -Hash 0011223344556677889900112233445566778899001122334455667788990011 -SignableFilePath GeneratedFileToSign.bin -Time 2011-11-01T13:30:00Z -AppendWrite ) 
PS C:\>.\signtool.exe sign /fd sha256 /p7 .\ /p7co 1.2.840.113549.1.7.1 /p7ce DetachedSignedData /a /f PrivateKey.pfxGeneratedFileToSign.bin
PS C:\> $objectFromFormat | Set-SecureBootUEFI -SignedFilePath GeneratedFileToSign.bin.p7
Name       : dbx 
Bytes      : {161, 89, 192, 165...} 
Attributes : NON VOLATILE 
             BOOTSERVICE ACCESS 
             RUNTIME ACCESS 
             TIME BASED AUTHENTICATED WRITE ACCESS
```

This example sets the information obtained from the Format-SecureBootUEFI cmdlet to the DBX UEFI variable.
This cmdlet supplies a path to the signed package to be authenticated.
The file named GeneratedFileToSign.bin is a digest created by the Format-SecureBootUEFI cmdlet that needs to be signed according to the UEFI specification.
The second command runs the SignTool.exe tool from the current directory to sign the digest.
The SignTool.exe tool can be downloaded from Windows Software Development Kit (SDK) for Windows 8https://go.microsoft.com/fwlink/p/?LinkId=236500 on MSDN.

### EXAMPLE 2
```
PS C:\> Set-SecureBootUEFI -ContentFilePath FormattedVariable.bin -SignedFilePath GeneratedFileToSign.bin.p7
Name       : dbx 
Bytes      : {161, 89, 192, 165...} 
Attributes : NON VOLATILE 
             BOOTSERVICE ACCESS 
             RUNTIME ACCESS 
             TIME BASED AUTHENTICATED WRITE ACCESS
```

This example sets the formatted data that was written to file FormattedVariable.bin to the DBX UEFI variable.
This cmdlet supplies a path to the signed package to be authenticated.

### EXAMPLE 3
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
Specifies the byte contents of the variable being set.

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

If only the name is specified, then the file must be in the current working directory; otherwise the full path of the file must be specified.

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
The acceptable values for this parameter are: PK, KEK, DB, or DBX.

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
If this parameter is specified, then the content are not actually set, just stored into this file. 

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

If only the name is specified, then the file must be in the current working directory; otherwise the full path of the file must be specified.

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
This parameter value should be formatted as follows so that it will be accepted by the DateTime object.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.SecureBoot.Commands.UEFIFormattedVariable
The UEFIFormattedVariable object contains the information for the **Name**, **Time**, **Content**, and **AppendWrite** parameters.

## OUTPUTS

### Microsoft.SecureBoot.Commands.UEFIEnvironmentVariable
The UEFIEnvironmentVariable object contains the following properties: 

 -- Name 

 -- Guid 

 -- Bytes 

 -- Attributes

## NOTES

## RELATED LINKS

[Confirm-SecureBootUEFI](./Confirm-SecureBootUEFI.md)

[Format-SecureBootUEFI](./Format-SecureBootUEFI.md)

[Get-SecureBootPolicy](./Get-SecureBootPolicy.md)

[Get-SecureBootUEFI](./Get-SecureBootUEFI.md)


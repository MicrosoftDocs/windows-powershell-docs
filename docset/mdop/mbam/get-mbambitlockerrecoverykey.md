---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.MBAM.Server.Commands.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Get-MbamBitLockerRecoveryKey
---

# Get-MbamBitLockerRecoveryKey

## SYNOPSIS
Requests an MBAM recovery key.

## SYNTAX

```
Get-MbamBitLockerRecoveryKey -KeyID <String> -Reason <String> [-UserDomain <String>] [-UserID <String>]
 -HelpDeskUrl <Uri> [<CommonParameters>]
```

## DESCRIPTION
The **Get-MbamBitLockerRecoveryKey** cmdlet requests a Microsoft BitLocker Administration and Monitoring (MBAM) recovery key.
This recovery key enables a user to unlock a volume that is in recovery mode.
A volume can enter recovery mode due to a forgotten BitLocker PIN or password, a Windows update, or a change to the BIOS settings of the computer.

## EXAMPLES

### Example 1: Get a recovery key by specifying an eight-digit recovery key ID
```
PS C:\> Get-MbamBitLockerRecoveryKey -KeyID "4374f3b9" -Reason "Forgot PIN" -HelpDeskUrl https://helpdeskserver/HelpDesk -UserDomain "ContosoDomain" -UserID "ContosoUser"
```

This command gets the recovery key from the specified help desk server for the user ContosoUser.
The command specifies only the first eight digits of the key ID.

### Example 2: Get a recovery key by specifying the complete recovery key ID
```
PS C:\> Get-MbamBitLockerRecoveryKey -KeyID "4374f3b9-58c7-4a41-87a5-0701d4fdbb86" -Reason "Forgot PIN" -HelpDeskUrl https://helpdeskserver/HelpDesk -UserDomain "ContosoDomain" -UserID "ContosoUser"
```

This command gets the recovery key from the specified help desk server for the user ContosoUser.
The command specifies the complete key ID.

## PARAMETERS

### -HelpDeskUrl
Specifies the URL for the MBAM help desk site.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: url

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyID
Specifies the recovery key ID.
You can specify the first eight digits of the recovery key ID for this parameter or you can specify the complete ID.
For example, if the recovery key ID is 4734f3b9-58c7-4a41-87a5-0701d4fdbb86, you can specify 4734f3b9 for this parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: key, k

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Reason
Specifies the reason for the recovery key request.
Reasons can include a forgotten BitLocker PIN or password, a Windows Update, or a change to BIOS settings of the computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: r

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserDomain
Specifies the domain of the user.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ud

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserID
Specifies the ID of the user.

```yaml
Type: String
Parameter Sets: (All)
Aliases: uid

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### string
The BitLocker recovery key for the specified volume.

## NOTES

## RELATED LINKS

[Microsoft BitLocker Administration and Monitoring](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/)



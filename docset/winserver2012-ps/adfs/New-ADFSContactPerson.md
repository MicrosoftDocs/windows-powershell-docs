---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
ms.assetid: CC60A897-EF69-40DD-9016-C0C3EF457DD8
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# New-ADFSContactPerson

## SYNOPSIS
Creates a new contact person object.

## SYNTAX

```
New-ADFSContactPerson [-Company <String>] [-EmailAddress <String[]>] [-GivenName <String>]
 [-TelephoneNumber <String[]>] [-Surname <String>] [<CommonParameters>]
```

## DESCRIPTION
The New-ADFSContactPerson cmdlet creates a new contact person object in the Federation Service.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>$cp = New-ADFSContactPerson -EmailAddress "support@fabrikam.com"
Set-ADFSProperties -ContactPerson $cp
```

Description

-----------

Creates a new contact person and sets it in the Federation Service.

## PARAMETERS

### -Company
Specifies the company name of the contact person.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EmailAddress
Specifies the e-mail address of the contact person.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GivenName
Specifies the given name of the contact person.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Surname
Specifies the surname (last name) of the contact person.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TelephoneNumber
Specifies the telephone number of the contact person.

```yaml
Type: String[]
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

### Microsoft.IdentityServer.PowerShell.Resources.ContactPerson
A class structure that represents a contact person object in the Federation Service.

## NOTES
* You can publish this contact person in the federation metadata of the Federation Service by using the Set-ADFSProperties cmdlet.

## RELATED LINKS

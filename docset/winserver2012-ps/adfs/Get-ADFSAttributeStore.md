---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
Module Name: ADFS
online version: https://learn.microsoft.com/powershell/module/adfs/get-adfsattributestore?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-ADFSAttributeStore

## SYNOPSIS
Gets the attribute stores of the Federation Service.

## SYNTAX

```
Get-ADFSAttributeStore [[-Name] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The Get-ADFSAttributeStore cmdlet retrieves the attribute stores of the Federation Service.
You can use this cmdlet with no parameters to retrieve all the attribute stores of the Federation Service.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Get-ADFSAttributeStore  -Name "MyCustomStore"
```

Description

-----------

Gets the properties for the attribute store named MyCustomStore.

## PARAMETERS

### -Name
Specifies the name of the attribute store to retrieve.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.IdentityServer.PowerShell.Resources.AttributeStore
A class structure that represents the attribute stores that are configured for the Federation Service.

## NOTES
* An Active Directory Federation Services (AD FS) 2.0 attribute store is a pluggable module that the policy process for AD FS 2.0 can query to retrieve claim values. You can use either an Active Directory database or a Microsoft SQL Server database as your attribute store. You can also use your own custom attribute store.

## RELATED LINKS

[Add-ADFSAttributeStore](./Add-ADFSAttributeStore.md)

[Remove-ADFSAttributeStore](./Remove-ADFSAttributeStore.md)

[Set-ADFSAttributeStore](./Set-ADFSAttributeStore.md)


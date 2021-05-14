---
external help file: VAMT_Cmdlets.xml
Module Name: VAMT
online version: https://docs.microsoft.com/powershell/module/vamt/install-vamtconfirmationid?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Install-VamtConfirmationId

## SYNOPSIS
Installs Confirmation IDs (CID) acquired from Microsoft to the respective computers to complete proxy activation.

## SYNTAX

```
Install-VamtConfirmationId [-Products] <Product[]> [[-Username] <String>] [[-Password] <String>]
```

## DESCRIPTION
The **Install-VamtConfirmationID** cmdlet installs the confirmation IDs (CIDs) to the computers in the system and alerts the products that they have been activated.
Use this cmdlet for proxy activations after you have acquired the CIDs from the Microsoft licensing servers.

## EXAMPLES

### Example
```
PS C:\> import-vamtdata -inputfile c:\users\me\desktop\vamtdata.cilx
PS C:\> $productinfo = get-vamtproduct
PS C:\> $updatedproductinfo = install-vamtconfirmationid -products $productinfo
PS C:\> import-vamtdata -products $updatedproductinfo
```

Run this command at the end of a proxy activation.
This command imports a file and acquires the data in the file.
It then installs the CIDs to the dep_nextref_vamt data object.
Finally, it imports the dep_nextref_vamt data object into the dep_nextref_vamt database.

## PARAMETERS

### -Password
Provides a password for password-protected environments.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Products
Specifies the product or products to install the CIDs on during the proxy activation process.

```yaml
Type: Product[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -Username
Provides a user name for password-protected environments.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-VamtConfirmationId](./Get-VamtConfirmationId.md)


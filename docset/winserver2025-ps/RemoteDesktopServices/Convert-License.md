---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: TSPSCmdlets.dll-Help.xml
Module Name: RemoteDesktopServices
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/remotedesktopservices/convert-license?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Convert-License
---

# Convert-License

## SYNOPSIS
Converts licenses in a key pack to per-device or per-user licenses.

## SYNTAX

```
Convert-License -KeyPackId <UInt32> [-Count <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Convert-License** cmdlet converts licenses in a specified key pack.
A key pack contains a number of licenses that enable clients to connect to a Remote Desktop Session Host (RD Session Host) server.
Remote Desktop Licensing (RD Licensing) supports the following kinds of licenses:

- Per-device.
RD Licensing requires a license for each device that connects to an RD Session Host server.
- Per-user.
RD Licensing requires a license for each user that connects to an RD Session Host server.

If a key pack contains per-device licenses, this cmdlet converts them to per-user licenses.
If a key pack contains per-user licenses, this cmdlet converts them to per-device licenses.
This cmdlet returns an object corresponding to the new key pack.

You can specify how many licenses in the key pack to convert by using the *Count* parameter.
If the number that you specify is greater than the number of available unissued keys, the cmdlet raises an error.
If you do not specify a value for this parameter, this cmdlet converts all the licenses in the key pack.

## EXAMPLES

### Example 1: Convert all the licenses in a key pack
```
PS C:\> $KeyPack = Get-WmiObject -Class Win32_TSLicenseKeyPack
PS C:\> Convert-License -KeyPackId $KeyPack[2].KeyPackId
```

This example converts all the unissued licenses in a key pack to per-device or per-user licenses.

The first command gets all the license key packs on the current computer by using the Get-WmiObject cmdlet, and then stores them as an array in the $KeyPack variable.
For more information, type `Get-Help Get-WmiObject`.

The second command uses standard array notation to specify the third member of the $KeyPack array.
The command specifies the **KeyPackId** property of that key pack as the value for the *KeyPackId* parameter.
The command converts the licenses in that key pack.
To see all the properties of a key pack, use the Get-Member cmdlet.
For more information, type `Get-Help Get-Member`.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Count
Specifies the number of licenses that this cmdlet converts.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyPackId
Specifies the ID for a key pack.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-RDLicenseConfiguration](../remotedesktop/Get-RDLicenseConfiguration.md)

[Get-RDSessionHost](../remotedesktop/Get-RDSessionHost.md)

[Get-WmiObject](https://go.microsoft.com/fwlink/?LinkId=821595)

[Get-Member](https://go.microsoft.com/fwlink/?LinkId=821792)

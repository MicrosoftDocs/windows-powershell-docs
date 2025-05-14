---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/enable-adfsendpoint?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-AdfsEndpoint
---

# Enable-AdfsEndpoint

## SYNOPSIS
Enables an endpoint in AD FS.

## SYNTAX

### Address
```
Enable-AdfsEndpoint [[-TargetAddressPath] <String>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### TargetObject
```
Enable-AdfsEndpoint [-TargetEndpoint] <Endpoint> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FullUrl
```
Enable-AdfsEndpoint [-TargetFullUrl] <Uri> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-AdfsEndpoint** cmdlet enables an endpoint in Active Directory Federation Services (AD FS).

## EXAMPLES

### Example 1: Enable an endpoint
```
PS C:\> Enable-AdfsEndpoint -TargetAddress "/adfs/services/trust/13/Windows"
```

This command enables the WS-Trust 1.3 endpoint for AD FS.

## PARAMETERS

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetAddressPath
Specifies the address path of the endpoint.
The cmdlet enables the endpoint that you specify.

```yaml
Type: String
Parameter Sets: Address
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetEndpoint
Specifies the endpoint to enable.
This value is typically taken from the pipeline.

```yaml
Type: Endpoint
Parameter Sets: TargetObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetFullUrl
Specifies the full URL of the endpoint to enable.

```yaml
Type: Uri
Parameter Sets: FullUrl
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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
Default value: False
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

### Microsoft.IdentityServer.PowerShell.Resources.Endpoint
A class structure that represents the endpoints for the Federation Service.

## OUTPUTS

### None

## NOTES
* Endpoints provide access to the federation server functionality of AD FS, such as token issuance and the publishing of federation metadata. Depending on the type of endpoint, you can enable or disable the endpoint or control whether the endpoint is published to Web Application Proxy.

## RELATED LINKS

[Disable-AdfsEndpoint](./Disable-AdfsEndpoint.md)

[Get-AdfsEndpoint](./Get-AdfsEndpoint.md)

[Set-AdfsEndpoint](./Set-AdfsEndpoint.md)


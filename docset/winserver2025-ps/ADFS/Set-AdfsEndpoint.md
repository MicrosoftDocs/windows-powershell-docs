---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfsendpoint?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsEndpoint
---

# Set-AdfsEndpoint

## SYNOPSIS
Sets the endpoint on a Web Application Proxy.

## SYNTAX

### Address
```
Set-AdfsEndpoint [[-TargetAddressPath] <String>] -Proxy <Boolean> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### TargetObject
```
Set-AdfsEndpoint -TargetEndpoint <Endpoint> -Proxy <Boolean> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### FullUrl
```
Set-AdfsEndpoint [-TargetFullUrl] <Uri> -Proxy <Boolean> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsEndpoint** cmdlet sets endpoints on a Web Application Proxy.

## EXAMPLES

### Example 1: Set an endpoint
```
PS C:\> Set-AdfsEndpoint -TargetAddressPath "/adfs/services/trust/13/Windows" -Proxy $True
```

This command sets the WS-Trust 1.3 endpoint for proxy use.

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

### -Proxy
Indicates whether the endpoint is available on the federation server proxy.
This is the only field of the endpoint that can be set.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetAddressPath
Specifies the address path of the endpoint.
The cmdlet makes the endpoint that you specify available to the extranet.

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
Specifies the endpoint that the cmdlet modifies.
This value is typically taken from the pipeline.

```yaml
Type: Endpoint
Parameter Sets: TargetObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetFullUrl
Specifies the full URL of the endpoint that the cmdlet modifies.

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
This cmdlet returns a class structure that represents an endpoint.

## OUTPUTS

### None

## NOTES
* This cmdlet has three parameter-sets. You can use the Address, FullUrl, or TargetEndpoint parameter set, over the pipeline, to identify the endpoint. This cmdlet only allows you to modify the Proxy property of the endpoint.

* Endpoints provide access to the federation server functionality of AD FS, such as token issuance and the publishing of federation metadata.
Depending on the type of endpoint, you can enable or disable the endpoint or control whether the endpoint is published to Web Application Proxy.

## RELATED LINKS

[Disable-AdfsEndpoint](./Disable-AdfsEndpoint.md)

[Enable-AdfsEndpoint](./Enable-AdfsEndpoint.md)

[Get-AdfsEndpoint](./Get-AdfsEndpoint.md)


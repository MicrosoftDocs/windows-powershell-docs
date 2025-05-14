---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/remove-webbinding?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WebBinding
---

# Remove-WebBinding

## SYNOPSIS
Removes a binding from an IIS website.

## SYNTAX

### InputBindingProperties (Default)
```
Remove-WebBinding [-Protocol <String>] [-Name <String>] [-IPAddress <String>] [-Port <String>]
 [-HostHeader <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Remove-WebBinding -InputObject <PSObject> [-Protocol <String>] [-Name <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputBindingInformation
```
Remove-WebBinding [-Protocol <String>] [-Name <String>] -BindingInformation <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WebBinding** cmdlet removes a binding from an Internet Information Services (IIS) website.

## EXAMPLES

### Example 1: Add and remove a site binding
```
IIS:\> New-WebBinding -Name "Default Web Site" -Port 1234 -IPAddress "*" -HostHeader "testsite" "Sleep 5 seconds before removing the binding"; Sleep 5
IIS:\> Get-WebBinding -Port 1234 -Name "Default Web Site" | Remove-WebBinding
```

This example creates a binding, and then removes that binding after waiting 5 seconds.
The second command uses the Get-WebBinding cmdlet to get the new binding, and then passes it to the current cmdlet by using the pipeline operator.

## PARAMETERS

### -BindingInformation
Specifies a **BindingInformation** object.

```yaml
Type: String
Parameter Sets: InputBindingInformation
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -HostHeader
Specifies the host header of the site binding that this cmdlet removes.

```yaml
Type: String
Parameter Sets: InputBindingProperties
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPAddress
Specifies the IP address of the site from which this cmdlet removes the binding.
You can use globbing (*) to specify all IP addresses.

```yaml
Type: String
Parameter Sets: InputBindingProperties
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies an input object that contains site binding information.

```yaml
Type: PSObject
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the site from which this cmdlet removes the binding.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Port
Specifies the port used by the binding that this cmdlet removes.

```yaml
Type: String
Parameter Sets: InputBindingProperties
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Protocol
Specifies the protocol of the binding that this cmdlet removes.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[Get-WebBinding](./Get-WebBinding.md)

[New-WebBinding](./New-WebBinding.md)

[Set-WebBinding](./Set-WebBinding.md)


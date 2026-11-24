---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: HgsClient-help.xml
Module Name: HgsClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgsclient/import-hgsguardian?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-HgsGuardian
---

# Import-HgsGuardian

## SYNOPSIS
Creates a guardian object from an .xml file.

## SYNTAX

```
Import-HgsGuardian [-Path] <String> -Name <String> [-AllowExpired] [-AllowUntrustedRoot] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Import-HgsGuardian** cmdlet creates a Host Guardian Service guardian object from an .xml file.
If you specify a name for the guardian, this cmdlet also persists that object in the local guardian store.

## EXAMPLES

### Example 1: Import a guardian
```
PS C:\> Import-HgsGuardian -Path "C:\MyDirectory\Guardian11.xml" -Name "Guardian11"
```

This command imports a guardian from the specified .xml file.

## PARAMETERS

### -AllowExpired
Indicates whether to allow guardian creation with certificates that are expired.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowUntrustedRoot
Indicates whether to allow a guardian to be created using self-signed certificates.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name to associate with this guardian when it is persisted to the local guardian store.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the path to an XML file containing the Guardian information.

```yaml
Type: String
Parameter Sets: (All)
Aliases: FilePath

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### CimInstance#MSFT_HgsGuardian
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Export-HgsGuardian](./Export-HgsGuardian.md)

[Get-HgsGuardian](./Get-HgsGuardian.md)

[New-HgsGuardian](./New-HgsGuardian.md)

[Remove-HgsGuardian](./Remove-HgsGuardian.md)


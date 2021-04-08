---
author: Kateyanne
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
manager: dansimp
Module Name: ADFS
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/adfs/set-adfsattributestore?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-ADFSAttributeStore

## SYNOPSIS
Sets the properties of the attribute store.

## SYNTAX

### Name
```
Set-ADFSAttributeStore [-Name <String>] [-Configuration <Hashtable>] [-TargetName] <String> [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Set-ADFSAttributeStore [-Name <String>] [-Configuration <Hashtable>] [-TargetAttributeStore] <AttributeStore>
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Set-ADFSAttributeStore cmdlet configures the attribute stores in the Federation Service.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Set-ADFSAttributeStore -TargetName 'MyCustomStore' -Configuration @("runmode" = "verbose"; configParaName2 = configParaValueNew)
```

Description

-----------

Sets configuration for a custom attribute store.

## PARAMETERS

### -Configuration
Specifies the initialization parameters of the attribute store, such as a connection string.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -Name
Specifies the friendly name of this attribute store.

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

### -PassThru
Passes an object to the pipeline.
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

### -TargetAttributeStore
Specifies the attribute store that will be modified by the cmdlet.
This value is typically taken from the pipeline.

```yaml
Type: AttributeStore
Parameter Sets: InputObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetName
Specifies the name of the attribute store that will be modified by the cmdlet.

```yaml
Type: String
Parameter Sets: Name
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS




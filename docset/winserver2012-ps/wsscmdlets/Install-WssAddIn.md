---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/install-wssaddin?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Install-WssAddIn

## SYNOPSIS
Installs or redeploys an add-in package.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Install-WssAddIn [-PackagePath] <String> [-Force] [-InstallOnClients] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Install-WssAddIn [-Redeploy] [-Id] <Guid> [-Force] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Install-WssAddIn** cmdlet installs a new add-in or redeploys an installed add-in.
To install an add-in, specify the path of a package file.
To redeploy an add-in, specify the Id of the alert.

## EXAMPLES

### Example 1: Install an add-in package
```
PS C:\> Install-WssAddIn -PackagePath "c:\TSQAaddin.wssx"
```

This command installs the add-in from the add-in package named TSQAaddin.wssx.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.

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

### -Id
Specifies the GUID for an installed package.
The cmdlet redeploys the add-ins for this package.

```yaml
Type: Guid
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstallOnClients
Indicates that cmdlet deploys the add-in to clients.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackagePath
Specifies the absolute path of the add-in package file (.wssx).

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Redeploy
Indicates that the cmdlet redeploys an add-in.
If you specify this parameter, specify the **PackagePath** parameter.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

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
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssAddIn](./Get-WssAddIn.md)

[Uninstall-WssAddIn](./Uninstall-WssAddIn.md)


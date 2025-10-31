---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
Module Name: IISAdministration
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iisadministration/disable-iissharedconfig?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-IISSharedConfig
---

# Disable-IISSharedConfig

## SYNOPSIS
Disables IIS shared configuration.

## SYNTAX

```
Disable-IISSharedConfig [-DontRestoreBackedUpKeys] [-CopyRemoteConfigToLocalFiles] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-IISSharedConfig** cmdlet disables the IIS shared configuration feature, and reverts to the keys that were backed up when shared configuration was enabled.
IIS also reverts to the local applicationHost.config file that was used before shared configuration was enabled.

You can enable shared configuration through the IIS Administration Manager UI or the **Enable-IISSharedConfig** cmdlet.

If there are no backup keys for any reason, the cmdlet fails with a warning.
To disable shared configuration in this scenario, you can use the *DontRestoreBackedUpKeys* parameter.

## EXAMPLES

### Example 1: Disable shared configuration and restore keys
```
PS C:\> Disable-IISSharedConfig
```

This command disables shared configuration.
IIS subsequently uses the local applicationHost.config file in %WINDIR%\config.
The backed up keys are restored to the local key store and deleted.

### Example 2: Disable shared configuration without restoring keys
```
PS C:\> Disable-IISSharedConfig -DontRestoreBackedUpKeys
```

This command disables shared configuration.
IIS subsequently uses the local applicationHost.config file in %WINDIR%\config.
The backed up keys are deleted and are not restored.

### Example 3: Disable shared configuration and use it locally
```
PS C:\> Disable-IISSharedConfig -CopyRemoteConfigToLocalFiles
```

This command disables shared configuration.
IIS copies the shared configuration locally and uses it.
The backed up keys are deleted and are not restored.

## PARAMETERS

### -CopyRemoteConfigToLocalFiles
Copies remote configuration over the local version of applicationHost.config before disabling shared configuration.

The version of the applicationHost.config file that was used before enabling shared configuration is overwritten.
The backup keys are also deleted, because those keys would only work with the overwritten version of applicationHost.config.

IIS continues to use the active keys that worked with shared configuration, which is now the local configuration.

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

### -DontRestoreBackedUpKeys
Indicates that this operation does not restore backed up keys.
If you do not specify the *CopyRemoteConfigToLocalFiles* parameter, IIS reverts to using its local copy of applicationHost.config, and uses the active keys for the shared configuration.

If the local copy of the applicationHost.config file had secrets encrypted with keys other than the currently active ones, IIS will no longer be able to decrypt those secrets.
You must re-enter and re-encrypt these secrets for the features that depend on them.

*DontRestoreBackedUpKeys* is useful in scenarios where backup keys are deleted but the IIS administrator wants to disable shared configuration.

This parameter is ignored if you specify the *CopyRemoteConfigToLocalFiles* parameter, because the backed up keys are not restored in that case.
In any circumstance, backed up keys are deleted when a shared configuration is disabled.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Enable-IISSharedConfig](./Enable-IISSharedConfig.md)

[Get-IISSharedConfig](./Get-IISSharedConfig.md)


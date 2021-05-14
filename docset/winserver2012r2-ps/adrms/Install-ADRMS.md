---
external help file: Microsoft.RightsManagementServices.Configuration.dll-Help.xml
Module Name: ADRMS
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/adrms/install-adrms?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Install-ADRMS
---

# Install-ADRMS

## SYNOPSIS
Configures a new deployment of AD RMS Server.

## SYNTAX

### MainProvisioningParameterSet
```
Install-ADRMS [-Path] <String> [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ADFSProvisioningParameterSet
```
Install-ADRMS [-ADFSUrl] <String> [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The Install-ADRMS cmdlet configures the Active Directory Rights Management Services (AD RMS) server role.
Before running this cmdlet, create a Windows PowerShell drive specifying the ADRmsInstall provider and the type of installation (RootCluster, LicensingCluster, or JoinCluster) as the root, and then set properties on the containers and child items in the drive to specify the initial values for provisioning the server.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Install-ADRMS -Path adrmsDrive:\
```

Description

-----------

This command configures AD RMS by using configuration settings that were previously set on items in the adrmsdrive:\ drive.
For more information on using this cmdlet, see http://go.microsoft.com/fwlink/?LinkId=136806.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Install-ADRMS -ADFSUrl https://sampleadfsurl.com -Force
```

Description

-----------

This command configures Identity Federation Support for the AD RMS cluster and sets the federation server URL.
For more information on using this cmdlet, see http://go.microsoft.com/fwlink/?LinkId=136806.

## PARAMETERS

### -ADFSUrl
Configures the AD RMS cluster to support Active Directory Federation Services (AD FS) and specifies the federation server URL.

```yaml
Type: String
Parameter Sets: ADFSProvisioningParameterSet
Aliases: 

Required: True
Position: 0
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

### -Credential
Specifies user credentials to use for the configuration process.
If this parameter is specified, you will be prompted to enter credentials.
This parameter operates in a similar manner to the RunAs command.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces completion of the command by overriding restrictions that would prevent it from succeeding (so long as a the changes made do not compromise security).

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies a provider drive and path or relative path on the current drive.
This parameter is required.
Use a dot (.) to specify the current location.
This parameter does not accept wildcards and has no default value.

```yaml
Type: String
Parameter Sets: MainProvisioningParameterSet
Aliases: 

Required: True
Position: 0
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### string, PSCredential

## OUTPUTS

## NOTES

## RELATED LINKS


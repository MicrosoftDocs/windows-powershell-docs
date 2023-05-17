---
external help file: NPS_Cmdlets.xml
Module Name: NPS
online version: https://learn.microsoft.com/powershell/module/nps/import-npsconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Import-NpsConfiguration

## SYNOPSIS
Imports NPS settings.

## SYNTAX

```
Import-NpsConfiguration [-Path] <String>
```

## DESCRIPTION
The **Import-NpsConfiguration** cmdlet imports settings for Network Policy Server (NPS).
NPS manages network access policies for client health, connection request authentication, and connection request authorization.
You can use NPS as a Remote Authentication Dial-In User Service (RADIUS) proxy to forward connection requests to NPS or other RADIUS servers that you configure in remote RADIUS server groups.
For more information about NPS, see Network Policy Serverhttp://technet.microsoft.com/en-us/library/cc732912.aspx (http://technet.microsoft.com/en-us/library/cc732912.aspx) on TechNet.

## EXAMPLES

### Example 1: Import settings to a Network Policy Server
```
PS C:\>Import-NpsConfiguration -Path "C:\Npsconfig.xml"
```

This command imports settings from the file named C:\Npsconfig.xml to NPS.

## PARAMETERS

### -Path
Specifies the full file path of the NPS configuration to import.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Export-NpsConfiguration](./Export-NpsConfiguration.md)


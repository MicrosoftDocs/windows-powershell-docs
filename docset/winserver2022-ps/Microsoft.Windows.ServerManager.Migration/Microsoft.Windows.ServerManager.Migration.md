---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
Download Help Link:
Help Version:
Locale: en-US
Module Name: Microsoft.Windows.ServerManager.Migration
Module Guid: 00000000-0000-0000-0000-000000000000
ms.date: 05/29/2025
schema: 2.0.0
title: Microsoft.Windows.ServerManager.Migration
---
# Microsoft.Windows.ServerManager.Migration Module

## Description

This reference provides cmdlet descriptions and syntax for all Server Migration cmdlets. It lists
the cmdlets in alphabetical order based on the verb at the beginning of the cmdlet.

Administrators can use the Windows Server Migration Tools cmdlets for Windows PowerShell to migrate
server roles, features, operating system settings, and other data and shares to computers that are
running the latest version of Windows Server.

## Microsoft.Windows.ServerManager.Migration Cmdlets

### [Disable-ServerManagerStandardUserRemoting](Disable-ServerManagerStandardUserRemoting.md)

Disables access for specified standard users to event, service, performance counter, and role and
feature inventory data that is collected by Server Manager for a server.

### [Enable-ServerManagerStandardUserRemoting](Enable-ServerManagerStandardUserRemoting.md)

Provides one or more standard, non-Administrator users access to event, service, performance
counter, and role and feature inventory data for a server that you are managing by using Server
Manager.

### [Export-SmigServerSetting](Export-SmigServerSetting.md)

Exports selected Windows features and operating system settings from the local computer, and stores
them in a migration store.

### [Get-SmigServerFeature](Get-SmigServerFeature.md)

Gets the set of all Windows features that can be migrated from the local server or from a migration store.

### [Get-WindowsFeature](Get-WindowsFeature.md)

Gets information about Windows Server roles, role services, and features that are available for
installation and installed on a specified server.

### [Import-SmigServerSetting](Import-SmigServerSetting.md)

Imports selected Windows features, and operating system settings from a migration store, and applies
them to the local computer.

### [Install-WindowsFeature](Install-WindowsFeature.md)

Installs one or more roles, role services, or features on either the local or a specified remote
server that is running Windows Server 2012 R2.

### [Receive-SmigServerData](Receive-SmigServerData.md)

Allows a destination server to receive shares, folders, files, and associated permissions and share
properties that are migrated from a source server. The cmdlet Send-SmigServerData must be run on the
source server at the same time Receive-SmigServerData is running on the destination server.

### [Send-SmigServerData](Send-SmigServerData.md)

Migrates folders, files, and associated permissions and share properties from a source server to a
destination server through port 7000. The cmdlet Receive-SmigServerData must be run on the
destination server at the same time Send-SmigServerData is running on the source server.

### [Uninstall-WindowsFeature](Uninstall-WindowsFeature.md)

Uninstalls specified Windows Server roles, role services, and features from a computer that is
running Windows Server 2012 R2.

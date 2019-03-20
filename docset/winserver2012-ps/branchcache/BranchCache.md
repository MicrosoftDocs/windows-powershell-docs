---
Module Name: BranchCache
Module Guid: D57AEE1E-6FE7-4BBC-8C57-8675A3A83E0D
Download Help Link: http://go.microsoft.com/fwlink/?LinkID=206777
Help Version: 3.1.0.0
Locale: en-US
ms.assetid: 05AD9108-DE76-4F8C-B0AC-DFB2E99ADD66
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# BranchCache Module
## Description
This reference provides cmdlet descriptions and syntax for all BranchCache **Manageability-specific** cmdlets. 
It lists the cmdlets in alphabetical order based on the verb at the beginning of the cmdlet.

## BranchCache Cmdlets
### [Add-BCDataCacheExtension](./Add-BCDataCacheExtension.md)
Increases the amount of cache storage space that is available on a hosted cache server by adding a new cache file.

### [Clear-BCCache](./Clear-BCCache.md)
Deletes all data in all data cache files and all hash cache files.

### [Disable-BC](./Disable-BC.md)
Disables the BranchCache service.

### [Disable-BCDowngrading](./Disable-BCDowngrading.md)
Disables downgrading, so that client computers that are running operating systems later than Windows 7® do not request Windows 7-specific versions of content information from content servers.

### [Disable-BCServeOnBattery](./Disable-BCServeOnBattery.md)
Configures a client to ignore content discovery requests in distributed cache mode when operating on battery power.

### [Enable-BCDistributed](./Enable-BCDistributed.md)
Enables BranchCache and configures a computer to operate in distributed cache mode.

### [Enable-BCDowngrading](./Enable-BCDowngrading.md)
Instructs a client computer that is running an operating system later than Windows 7® to operate in a downgraded Windows 7 mode.

### [Enable-BCHostedClient](./Enable-BCHostedClient.md)
Configures BranchCache to operate in hosted cache client mode.

### [Enable-BCHostedServer](./Enable-BCHostedServer.md)
Configures BranchCache to operate in hosted cache server mode.

### [Enable-BCLocal](./Enable-BCLocal.md)
Enables the BranchCache service in local caching mode.

### [Enable-BCServeOnBattery](./Enable-BCServeOnBattery.md)
Configures a client to listen for content discovery requests in distributed cache mode when operating on battery power.

### [Export-BCCachePackage](./Export-BCCachePackage.md)
Exports a cache package.

### [Export-BCSecretKey](./Export-BCSecretKey.md)
Exports a secret key to a file.

### [Get-BCClientConfiguration](./Get-BCClientConfiguration.md)
Retrieves the current BranchCache client computer settings.

### [Get-BCContentServerConfiguration](./Get-BCContentServerConfiguration.md)
Retrieves the current BranchCache content server settings.

### [Get-BCDataCache](./Get-BCDataCache.md)
Retrieves an object that represents the BranchCache data cache.

### [Get-BCDataCacheExtension](./Get-BCDataCacheExtension.md)
Retrieves objects that represent the BranchCache data cache extensions from a hosted cache server.

### [Get-BCHashCache](./Get-BCHashCache.md)
Retrieves the BranchCache hash cache.

### [Get-BCHostedCacheServerConfiguration](./Get-BCHostedCacheServerConfiguration.md)
Retrieves the current BranchCache hosted cache server settings.

### [Get-BCNetworkConfiguration](./Get-BCNetworkConfiguration.md)
Retrieves the current BranchCache network settings.

### [Get-BCStatus](./Get-BCStatus.md)
Retrieves a set of objects that provide BranchCache status and configuration information.

### [Import-BCCachePackage](./Import-BCCachePackage.md)
Imports a cache package.

### [Import-BCSecretKey](./Import-BCSecretKey.md)
Imports the cryptographic key that BranchCache uses for the generation of segment secrets.

### [Publish-BCFileContent](./Publish-BCFileContent.md)
Generates hashes, also called content information, for files in shared folders on a file server that have BranchCache enabled and the BranchCache for Network Files role service installed.

### [Publish-BCWebContent](./Publish-BCWebContent.md)
Creates hashes for web content when deploying content servers that are running Windows Server® 8 Beta with the Web Services (IIS) server role installed.

### [Remove-BCDataCacheExtension](./Remove-BCDataCacheExtension.md)
Deletes a data cache file.

### [Reset-BC](./Reset-BC.md)
Resets BranchCache to the default configuration.

### [Set-BCAuthentication](./Set-BCAuthentication.md)
Specifies the BranchCache computer authentication mode.

### [Set-BCCache](./Set-BCCache.md)
Modifies the cache file configuration.

### [Set-BCDataCacheEntryMaxAge](./Set-BCDataCacheEntryMaxAge.md)
Modifies the maximum amount of time that data can remain in the cache.

### [Set-BCMinSMBLatency](./Set-BCMinSMBLatency.md)
Sets the minimum latency that must exist between client and server before transparent caching functions are utilized.

### [Set-BCSecretKey](./Set-BCSecretKey.md)
Sets the cryptographic key used in the generation of segment secrets.


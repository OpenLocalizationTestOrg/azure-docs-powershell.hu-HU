---
title: "Az Azure PowerShell változásnaplója | Microsoft Docs"
description: "Az alábbiakban az Azure PowerShell legutóbbi kiadásában végrehajtott módosítások előzményei olvashatók."
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.service: azure-powershell
ms.product: azure
ms.devlang: powershell
ms.topic: conceptual
ms.workload: 
ms.date: 11/14/2017
ms.openlocfilehash: ab35cbc4ec1a0bd4e7ee40e1864bd7941f5bca87
ms.sourcegitcommit: 79dd3700b5cb4cb90b268778b482082052160093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/14/2017
---
# <a name="release-notes"></a>Kibocsátási megjegyzések

Az alábbiakban az Azure PowerShell jelen kiadásában végrehajtott módosítások listája olvasható.

## <a name="20171110-version-501"></a>2017.11.10. – 5.0.1-es verzió
* Kijavítottuk a szerelvénybetöltési hibát, amely egyes parancsmagok sikertelen futtatását okozta az alábbi modulokban történő végrehajtás során:
    - AzureRM.ApiManagement
    - AzureRM.Backup
    - AzureRM.Batch
    - AzureRM.Compute
    - AzureRM.DataFactories
    - AzureRM.HDInsight
    - AzureRM.KeyVault
    - AzureRM.RecoveryServices
    - AzureRM.RecoveryServices.Backup
    - AzureRM.RecoveryServices.SiteRecovery
    - AzureRM.RedisCache
    - AzureRM.SiteRecovery
    - AzureRM.Sql
    - AzureRM.Storage
    - AzureRM.StreamAnalytics

## <a name="2017118---version-500"></a>2017.11.8. – 5.0.0-s verzió
* Megjegyzés: Ez egy használhatatlanná tévő változást tartalmazó kiadás. A bevezetett használhatatlanná tévő változások teljes listájához tekintse meg a migrálási útmutatót (https://aka.ms/azps-migration-guide).
* Mostantól az AzureRM összes parancsmagja támogatja az online súgó használatát
    - Futtassa a Get-Help parancsmagot -Online paraméterrel az online súgónak az alapértelmezett böngészőben történő megnyitásához
* AnalysisServices
    * A Synchronize-AzureAsInstance mostantól működik az új AsAzure szinkronizálási REST API-val
* ApiManagement
    * A jelen kiadás keretében az ApiManagement parancsban történt használhatatlanná tévő változásokért tekintse meg a migrálási útmutatót
    * A Get-AzureRmApiManagementUser parancsmag frissítve az alábbi hiba javítása érdekében: https://github.com/Azure/azure-powershell/issues/4510
    * A New-AzureRmApiManagementApi parancsmag frissítve üres elérési útvonallal rendelkező API létrehozásához: https://github.com/Azure/azure-powershell/issues/4069
* ApplicationInsights
    * Parancsok hozzáadása Application Insights-erőforrások lekérdezéséhez/létrehozásához/eltávolításához
        - Get-AzureRmApplicationInsights
        - New-AzureRmApplicationInsights
        - Remove-AzureRmApplicationInsights
    * Parancsok hozzáadása az Application Insights-erőforrások díjszabásának és napi maximális értékének lekérdezéséhez/frissítéséhez
        - Get-AzureRmApplicationInsights -IncludeDailyCap
        - Set-AzureRmApplicationInsightsPricingPlan
        - Set-AzureRmApplicationInsightsDailyCap
    * Parancsok hozzáadása az Application Insights-erőforrások folyamatos exportálásának lekérdezéséhez/létrehozásához/frissítéséhez/eltávolításához
        - Get-AzureRmApplicationInsightsContinuousExport
        - Set-AzureRmApplicationInsightsContinuousExport
        - New-AzureRmApplicationInsightsContinuousExport
        - Remove-AzureRmApplicationInsightsContinuousExport
    * Parancsok hozzáadása az Application Insights-erőforrások API-kulcsainak lekérdezéséhez/létrehozásához/eltávolításához
        - Get-AzureRmApplicationInsightsApiKey
        - New-AzureRmApplicationInsightsApiKey
        - Remove-AzureRmApplicationInsightsApiKey
* AzureBatch
    * Új paraméterek hozzáadva a következőhöz: `New-AzureRmBatchAccount`.
        - `PoolAllocationMode`: Készletek a Batch-fiókban történő létrehozásához használandó lefoglalási mód. Ha olyan Batch-fiókot szeretne létrehozni, amely lefoglalja a készletcsomópontokat a felhasználó előfizetésében, állítsa `UserSubscription` értékre.
        - `KeyVaultId`: A Batch-fiókhoz társított Azure Key Vault erőforrás-azonosítója.
        - `KeyVaultUrl`: A Batch-fiókhoz társított Azure Key Vault URL-címe.
    * Paraméterek frissítve a következő esetében: `New-AzureBatchTask`.
        - A `RunElevated` kapcsoló eltávolítva. A `UserIdentity` paraméter hozzáadva a `RunElevated` helyett, az egyenértékű viselkedés pedig egy `PSUserIdentity` felépítésével érhető el, az alábbi módon:
            - $autoUser = New-Object Microsoft.Azure.Commands.Batch.Models.PSAutoUserSpecification -ArgumentList @("Task", "Admin")
            - $userIdentity = New-Object Microsoft.Azure.Commands.Batch.Models.PSUserIdentity $autoUser
        - A következő paraméter hozzáadva: `AuthenticationTokenSettings`. Ez a paraméter lehetővé teszi a Batch szolgáltatás felkérését arra, hogy biztosítson egy hitelesítési tokent a feladat számára annak futtatásakor. Így nincs szükség a Batch-fiók kulcsainak átadására a feladat számára, hogy az kéréseket küldhessen a Batch szolgáltatásnak.
        - A következő paraméter hozzáadva: `ContainerSettings`.
            - Ez a paraméter lehetővé teszi, hogy felkérje a Batch szolgáltatást a feladat tárolóban történő futtatására.
        - A következő paraméter hozzáadva: `OutputFiles`.
            - Ez a paraméter lehetővé teszi, hogy úgy konfigurálja a feladatot, hogy az fájlokat töltsön fel az Azure Storage-ba, miután befejeződött.
    * Paraméterek frissítve a következő esetében: `New-AzureBatchPool`.
        - A következő paraméter hozzáadva: `UserAccounts`.
            - Ez a paraméter a készlet egyes csomópontjain létrehozott felhasználói fiókokat definiálja.
        - `TargetLowPriorityComputeNodes` hozzáadva, `TargetDedicated` átnevezve a következőre: `TargetDedicatedComputeNodes`.
            - Egy `TargetDedicated` alias létrehozva a következő paraméterhez: `TargetDedicatedComputeNodes`.
        - A következő paraméter hozzáadva: `NetworkConfiguration`.
            - Ez a paraméter lehetővé teszi a készletek hálózati beállításainak konfigurálását.
    * Paraméterek frissítve a következő esetében: `New-AzureBatchCertificate`.
        - A `Password` paraméter mostantól `SecureString`.
    * Paraméterek frissítve a következő esetében: `New-AzureBatchComputeNodeUser`.
        - A `Password` paraméter mostantól `SecureString`.
    * Paraméterek frissítve a következő esetében: `Set-AzureBatchComputeNodeUser`.
        - A `Password` paraméter mostantól `SecureString`.
    * A `Name` paraméter átnevezve erre: `Path` a `Get-AzureBatchNodeFile`, `Get-AzureBatchNodeFileContent` és `Remove-AzureBatchNodeFile` esetében.
        - Egy `Name` alias létrehozva a következő paraméterhez: `Path`.
    * Objektumokat érintő változások
        - A teljes listáért tekintse meg a Batch változásnaplóját
    * Támogatás hozzáadva az Azure Active Directory-alapú hitelesítéshez.
        - Az Azure Active Directory-hitelesítés használatához kérjen le egy `BatchAccountContext` objektumot a `Get-AzureRmBatchAccount` parancsmag használatával, majd adja meg a `BatchAccountContext` paramétert egy Batch szolgáltatás parancsmagjának `-BatchContext` paraméteréhez. Az Azure Active Directory-hitelesítés kötelező a `PoolAllocationMode = UserSubscription` lefoglalási móddal rendelkező fiókok esetében.
        - A meglévő vagy a `PoolAllocationMode = BatchService` használatával létrehozott új fiókok esetében továbbra is használhat megosztott kulcsos hitelesítést, ha lekér egy `BatchAccountContext` objektumot a `Get-AzureRmBatchAccoutKeys` parancsmag segítségével.
* Számítás
    * Az Azure Disk Encryption bővítmény parancsai
        - A 'Set-AzureRmVmDiskEncryptionExtension’ parancs új paramétere, az '-EncryptFormatAll’ titkosított módon formázza az adatlemezeket
        - A 'Set-AzureRmVmDiskEncryptionExtension' parancs új paraméterei, az '-ExtensionPublisherName' és '-ExtensionType’ lehetővé teszik a bővítmény másik verziójára történő váltást
        - A 'Disable-AzureRmVmDiskEncryption' parancs új paraméterei, az '-ExtensionPublisherName' és '-ExtensionType’ lehetővé teszik a bővítmény másik verziójára történő váltást
        - A 'Get-AzureRmVmDiskEncryptionStatus' parancs új paraméterei, az '-ExtensionPublisherName' és '-ExtensionType’ lehetővé teszik a bővítmény másik verziójára történő váltást
* DataLakeAnalytics
    * A jelen kiadás keretében a DataLakeAnalytics parancsban történt használhatatlanná tévő változásokért tekintse meg a migrálási útmutatót
    * A Get-AzureRmDataLakeAnalyticsAccount egyik OutputType paramétere módosítva
        - Erről: List\<DataLakeAnalyticsAccount>, erre: List\<PSDataLakeAnalyticsAccountBasic>
        - A PSDataLakeAnalyticsAccountBasic tulajdonságai a DataLakeAnalyticsAccount tulajdonságainak egy szigorú alkészletéből állnak
        - A DataLakeAnalyticsAccount paraméterben található további tulajdonságokat nem adja vissza a szolgáltatás.  A változtatás célja tehát ennek pontos megjelenítése. Ezek a további tulajdonságok továbbra is megtalálhatók a PSDataLakeAnalyticsAccountBasic paraméterben, de Obsolete (Elavult) címkével vannak ellátva.
    * A Get-AzureRmDataLakeAnalyticsJob egyik OutputType paramétere módosítva
        - Erről: List\<JobInformation>, erre List\<PSJobInformationBasic>
        - A PSJobInformationBasic tulajdonságai a JobInformation tulajdonságainak egy szigorú alkészletéből állnak
        - A JobInformation paraméterben található további tulajdonságokat nem adja vissza a szolgáltatás.  A változtatás célja tehát ennek pontos megjelenítése. Ezek a további tulajdonságok továbbra is megtalálhatók a PSJobInformationBasic paraméterben, de Obsolete (Elavult) címkével vannak ellátva.
* DataLakeStore
    * A jelen kiadás keretében a DataLakeStore parancsban történt használhatatlanná tévő változásokért tekintse meg a migrálási útmutatót
    * A Get-AzureRmDataLakeStoreAccount egyik OutputType paramétere módosítva
        - Erről: List\<PSDataLakeStoreAccount>, erre: List\<PSDataLakeStoreAccountBasic>
        - A PSDataLakeStoreAccountBasic tulajdonságai a PSDataLakeStoreAccount tulajdonságainak egy szigorú alkészletéből állnak
        - A PSDataLakeStoreAccount paraméterben található további tulajdonságokat nem adja vissza a szolgáltatás.  A változtatás célja tehát ennek pontos megjelenítése. Ezek a további tulajdonságok továbbra is megtalálhatók a PSDataLakeStoreAccountBasic paraméterben, de Obsolete (Elavult) címkével vannak ellátva.
* DNS
    * A CAA-rekordtípusok támogatása az Azure DNS szolgáltatásban
       - A CAA-rekordtípuson elvégzett összes műveletet támogatja
* EventHub
    * A jelen kiadás keretében az EventHub parancsban történt használhatatlanná tévő változásokért tekintse meg a migrálási útmutatót
* Insights
    * A jelen kiadás keretében az Insights parancsban történt használhatatlanná tévő változásokért tekintse meg a migrálási útmutatót
* Network (Hálózat)
    * A jelen kiadás keretében a Network parancsban történt használhatatlanná tévő változásokért tekintse meg a migrálási útmutatót
    * Parancsmag hozzáadva az egyes Azure-régiókban elérhető internetszolgáltatók felsorolásához
        - Get-AzureRmNetworkWatcherReachabilityProvidersList
    * Parancsmag hozzáadva az internetszolgáltatók egy adott hely és az Azure-régiók közötti relatív késési pontszámának lekéréséhez
        - Get-AzureRmNetworkWatcherReachabilityReport
* Profil
    - Set-AzureRmDefault
        - A parancsmag használatával alapértelmezett erőforráscsoportot adhat meg.  Ennek következtében a -ResourceGroup nem lesz kötelező egyes parancsmagok esetében, és ha nincs erőforráscsoport megadva, a parancs az alapértelmezést használja majd
        - ```Set-AzureRmDefault -ResourceGroupName "ExampleResourceGroup"```
        - Ha van megadott erőforráscsoport az előfizetésben, az lesz alapértelmezettként beállítva.  Ellenkező esetben a rendszer létrehozza az erőforráscsoportot, majd beállítja alapértelmezettként.
    - Get-AzureRmDefault
        - A parancsmag használatával lekérdezheti az aktuális alapértelmezett erőforráscsoportot (és egyéb alapértelmezéseket is a jövőben).
        - ```Get-AzureRmDefault -ResourceGroup```
    - Clear-AzureRmDefault
        - A parancsmag használatával eltávolíthatja az aktuális alapértelmezett erőforráscsoportot
        - ```Clear-AzureRmDefault -ResourceGroup```
    - Add-AzureRmEnvironment és Set-AzureRmEnvironment
        - A BatchAudience paraméter hozzáadása lehetővé teszi az Azure Batch Active Directory célközönségének megadását, amelyet a hitelesítési tokeneknek a Batch szolgáltatás számára történő beszerzésekor kíván használni.
* RecoveryServices.Backup
    * Parancsmagok hozzáadva azonnali fájlhelyreállítás végrehajtásához.
        - Get-AzureRmRecoveryServicesBackupRPMountScript
        - Disable-AzureRmRecoveryServicesBackupRPMountScript
    * A RecoveryServices.Backup SDK frissítve a legújabb verzióra
    * Az Azure virtuális gép számítási feladatainak tesztje frissítve, hogy a tesztek futtatásához szükséges beállításokat maguk a tesztek végezzék el.
    * Ez a következőt javítja ki: https://github.com/Azure/azure-powershell/issues/3164
* RecoveryServices.SiteRecovery
    * Az ASR VMware–Azure Site Recovery változásai (a parancsmagok jelenleg az Enterprise–Enterprise, Enterprise–Azure és HyperV–Azure műveleteket támogatják)
        - New-AzureRmRecoveryServicesAsrPolicy
        - New-AzureRmRecoveryServicesAsrProtectedItem
        - Update-AzureRmRecoveryServicesAsrPolicy
        - Update-AzureRmRecoveryServicesAsrProtectionDirection
    * Támogatás hozzáadva az AAD-alapú tárolóhoz
    * Parancsmagok hozzáadva a VCenter-erőforrások kezeléséhez
        - Get-AzureRmRecoveryServicesAsrVCenter
        - New-AzureRmRecoveryServicesAsrVCenter
        - Remove-AzureRmRecoveryServicesAsrVCenter
        - Update-AzureRmRecoveryServicesAsrVCenter
    * Egyéb parancsmagok hozzáadva
        - Get-AzureRmRecoveryServicesAsrAlertSetting
        - Get-AzureRmRecoveryServicesAsrEvent
        - New-AzureRmRecoveryServicesAsrProtectableItem
        - Set-AzureRmRecoveryServicesAsrAlertSetting
        - Start-AzureRmRecoveryServicesAsrResynchronizeReplicationJob
        - Start-AzureRmRecoveryServicesAsrSwitchProcessServerJob
        - Start-AzureRmRecoveryServicesAsrTestFailoverCleanupJob
        - Update-AzureRmRecoveryServicesAsrMobilityService
* ServiceBus
    - A jelen kiadás keretében a ServiceBus parancsban történt használhatatlanná tévő változásokért tekintse meg a migrálási útmutatót
* SQL
    * Támogatás hozzáadása az aszinkron updateslo művelet listázásához és megszakításához az adatbázison
        - a meglévő Get-AzureRmSqlDatabaseActivity parancsmag frissítése, hogy visszaadja az adatbázis updateslo műveletének állapotát.
        - új Stop-AzureRmSqlDatabaseActivity hozzáadása az aszinkron updateslo művelet megszakításához az adatbázison.
    * A Zone Redudancy támogatásának hozzáadása adatbázisok és rugalmas készletek esetében
        - Új kapcsolóparaméter (ZoneRedundant) hozzáadása a New-AzureRmSqlDatabase parancsmaghoz
        - Új kapcsolóparaméter (ZoneRedundant) hozzáadása a Set-AzureRmSqlDatabase parancsmaghoz
        - Új kapcsolóparaméter (ZoneRedundant) hozzáadása a New-AzureRmSqlElasticPool parancsmaghoz
        - Új kapcsolóparaméter (ZoneRedundant) hozzáadása a Set-AzureRmSqlElasticPool parancsmaghoz
    * Támogatás hozzáadása a kiszolgálói DNS-aliasok számára
        - A Get-AzureRmSqlServerDnsAlias parancsmag hozzáadása, amely lekérdezi a kiszolgálói DNS-aliasokat a kiszolgálók és aliasok neve szerint, vagy egy Azure SQL-kiszolgáló kiszolgálói DNS-aliasainak listáját.
        - A New-AzureRmSqlServerDnsAlias parancsmag hozzáadása, amely létrehoz egy új kiszolgálói DNS-aliast egy adott Azure SQL-kiszolgáló számára
        - A Set-AzurermSqlServerDnsAlias parancsmag hozzáadása, amely lehetővé teszi azon Azure SQL-kiszolgáló frissítését, amelyre a kiszolgálói DNS-alias mutat
        - A Remove-AzureRmSqlServerDnsAlias parancsmag hozzáadása, amely eltávolítja egy adott Azure SQL-kiszolgáló egy kiszolgálói DNS-aliasát
* Azure.Storage
    * Frissítés az Azure Storage ügyféloldali kódtárának 8.5.0-s és az Azure Storage adatátviteli kódtárának 0.6.3-as verziójára
    * Fájlmegosztási pillanatkép támogatásának hozzáadása
        - 'SnapshotTime’ hozzáadva a Get-AzureStorageShare parancsmaghoz
        - 'IncludeAllSnapshot’ hozzáadva a Remove-AzureStorageShare parancsmaghoz
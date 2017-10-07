Az Azure PowerShell 4.3.1 telepítője: [hivatkozás](https://github.com/Azure/azure-powershell/releases/download/v4.3.1-August2017/azure-powershell.4.3.1.msi)

Az ARM-parancsmagok gyűjteménymodulja: [hivatkozás](https://www.powershellgallery.com/packages/AzureRM/4.3.1)

Az örökölt szolgáltatásfelügyeleti (RDFE) parancsmagok gyűjteménymodulja: [hivatkozás](https://www.powershellgallery.com/packages/Azure/4.3.1)

## <a name="changes-in-431"></a>Módosítások a 4.3.1 verzióban

- Ki lett javítva a probléma, melynek hatására a rendszer bizonyos szerelvényeket nem írt alá, ami `could not load file or assembly` hibát okozott a modulok importálásakor

## <a name="changes-in-430"></a>Módosítások a 4.3.0 verzióban

* AnalysisServices
    * A Set-AzureRmAnalysisServciesServer parancsmag hibájának javítása
        - Ha nincs megadva a rendszergazda, a rendszer eltávolítja a rendszergazdát.
    * Megjelent a BackupBlobContainerUri paraméter a New-AzureRmAnalysisServicesServer és a Set-AzureRmAnalysisServicesServer parancsmagban
        - Biztonsági blobtároló beállításának vagy letiltásának lehetősége tartalék vagy visszaállítási Azure Analysis Services-kiszolgálóhoz
    * A termékváltozat-keresés frissítése a New-AzureRmAnalysisServicesServer és a Set-AzureRmAnalysisServicesServer parancsmagban
        - Módosítva lett a dinamikus keresés nem változtatható termékváltozata.
    * Az Add-AzureAnalysisServicesAccount parancsmag most már támogatja a szolgáltatásnévvel való bejelentkezést
* Automatizálás
    * Módosítva lettek az Automation DSC* parancsmagok, hogy 100-nál több rekordot kérjenek le
    * Meg lett oldva a probléma, amely miatt a részletes streamek néhány Automation-parancsmag (például a Get-AzureRmAutomationVariable és a Get-AzureRmAutomationJob) meghívása után nem működnek tovább.
    * Most már támogatott a csomópont-konfiguráció buildjeinek verziószámozása a StartAzureAutomationDscCompilationJob és az ImportAzureAutomationDscNodeConfiguration parancsmagban.
    * Meglévő problémák hibajavításai – az aliasokkal kapcsolatos, 3775-ös számú probléma, valamint a runOn aliasok és a hibrid feldolgozók támogatásának javítása.
* Számítás
    * Set-AzureRmVMAEMExtension: Mostantól támogatottak az új prémium szintű lemezméretek
    * Set-AzureRmVMAEMExtension: Mostantól támogatott az M-sorozat
    * Megjelent a ForceUpdateTag paraméter az Add-AzureRmVmssExtension parancsmagban
    * Megjelent a Primary paraméter a New-AzureRmVmssIpConfig parancsmagban
    * Megjelent az EnableAcceleratedNetworking paraméter az Add-AzureRmVmssNetworkInterfaceConfig parancsmagban
    * Megjelent az InstanceId paraméter a Set-AzureRmVmss parancsmagban
    * A MaintenanceRedeployStatus paraméter megjelenítése a Get-AzureRmVM parancsmag kimenetében
    * A korlátozások és a képességek megjelenítése a Get-AzureRmComputeResourceSku parancsmag táblázatformátumában
* DataLakeStore
    * A probléma javítása: https://github.com/Azure/azure-powershell/issues/4323
* EventHub
    * Megjelent a ResourceGroup tulajdonság a névtérattribútumok között
        - A ResourceGroup tulajdonság azon erőforráscsoport nevét olvassa be, melyben a névtér található
    * a parancsmagok új paraméterrel és paraméteraliassal lettek frissítve
        - az alábbi parancsmagok névtérre és EventHubra vonatkozó paraméterkészletekkel lettek frissítve engedélyezési szabályok használatához
        - New-AzureRmEventHubAuthorizationRule
            + Új engedélyezési szabályt ad hozzá egy meglévő névtérhez vagy EventHubhoz.
        - Get-AzureRmEventHubAuthorizationRule
            + Beolvas egy engedélyezési szabályt vagy az engedélyezési szabályok listáját egy meglévő névtérből vagy EventHubból.
        - Set-AzureRmEventHubAuthorizationRule
            + Frissíti egy meglévő névtér vagy EventHub tulajdonságait.
        - Remove-AzureRmEventHubAuthorizationRule
            + Töröl egy meglévő engedélyezési szabályt egy meglévő névtérből vagy EventHubból.
        - New-AzureRmEventHubKey
            + Új elsődleges és másodlagos kulcsot generál egy meglévő névtér vagy EventHub egy engedélyezési szabályához.
        - Get-AzureRmEventHubKey
            + Beolvassa egy meglévő névtér vagy EventHub egy engedélyezési szabályának elsődleges és másodlagos kulcsát.
* Network (Hálózat)
    * New-AzureRmExpressRouteCircuitPeeringConfig: Most már támogatott az IPv6 használata. Új nem kötelező paraméter jelent meg
        - PeerAddressType
    * Set-AzureRmExpressRouteCircuitPeeringConfig: Most már támogatott az IPv6 használata. Új nem kötelező paraméter jelent meg
        - PeerAddressType
    * Remove-AzureRmExpressRouteCircuitPeeringConfig: Most már támogatott az IPv6 használata. Új nem kötelező paraméter jelent meg
        - PeerAddressType
    * A -ProbeEnabled paraméter meg lett jelölve elavultként
        - Add-AzureRmApplicationGatewayBackendHttpSettings
        - New-AzureRmApplicationGatewayBackendHttpSettings
        - Set-AzureRmApplicationGatewayBackendHttpSettings
* Profil
    * Az adatgyűjtés most már alapértelmezés szerint engedélyezve van. A Microsoft a felhasználói élmény javítása érdekében gyűjti a használati adatokat. Az adatok névtelenek, és nem tartalmazzák a parancssori argumentumok értékeit.
        - A funkció a Disable-AzureRmDataCollection parancsmaggal kapcsolható ki
        - A funkció az Enable-AzureRmDataCollection parancsmaggal kapcsolható be
* Erőforrások
    * Mostantól támogatott a hatókörök érvényesítése az ARM-nek küldött kérelem küldése előtt az alábbi szerepkör-definíciós és szerepkör-hozzárendelési parancsmagok esetében
        - Get-AzureRMRoleAssignment
        - New-AzureRMRoleAssignment
        - Remove-AzureRMRoleAssignment
        - Get-AzureRMRoleDefinition
        - New-AzureRMRoleDefinition
        - Remove-AzureRMRoleDefinition
        - Set-AzureRMRoleDefinition
* ServiceBus
    * Az alábbi új engedélyezési szabályokkal, névterekkel, üzenetsorokkal és témakörökkel kapcsolatos parancsmagok jelentek meg. a rendszer a paraméterkészlet alapján elvégzi az engedélyezési szabályokra vonatkozó műveleteket.
     - New-AzureRmServiceBusAuthorizationRule
       - Új engedélyezési szabályt ad hozzá egy meglévő ServiceBus-névtérhez, -üzenetsorhoz vagy -témakörhöz.
     - Get-AzureRmServiceBusAuthorizationRule
       - Beolvas egy engedélyezési szabályt vagy az engedélyezési szabályok listáját egy meglévő ServiceBus-névtérből, -üzenetsorból vagy -témakörből.
     - Set-AzureRmServiceBusAuthorizationRule
       - Frissíti egy meglévő ServiceBus-névtér, -üzenetsor vagy -témakör tulajdonságait.
     - New-AzureRmServiceBusKey
       - Új elsődleges és másodlagos kulcsot generál egy meglévő ServiceBus-névtér, -üzenetsor vagy -témakör egy engedélyezési szabályához.
     - Get-AzureRmServiceBusKey
       - Beolvassa egy meglévő ServiceBus-névtér, -üzenetsor vagy -témakör egy engedélyezési szabályának elsődleges és másodlagos kulcsát.
     - Remove-AzureRmServiceBusNamespaceAuthorizationRule
       - Töröl egy meglévő engedélyezési szabályt egy ServiceBus-névtérből, -üzenetsorból vagy -témakörből.
    * Megjelent a ResourceGroup tulajdonság a névtérattribútumok között
* SQL
    * A Set-AzureRmSqlServerTransparentDataEncryptionProtector parancsmag frissítése, hogy figyelmeztetést jelenítsen meg és megerősítést kérjen, ha a titkosítási védelem típusa az AzureKeyVault értékre van állítva
    * Új, frissített naplózási beállításokra vonatkozó parancsmagok jelentek meg
        - Megjelenik a Get-AzureRmSqlDatabaseAuditing parancsmag, mely egy Azure SQL Database-adatbázis naplózási beállításait olvassa be.
        - Megjelenik a Get-AzureRmSqlServerAuditing parancsmag, mely egy Azure SQL Server-kiszolgáló naplózási beállításait olvassa be.
        - Megjelenik a Set-AzureRmSqlDatabaseAuditing parancsmag, mely egy Azure SQL Database-adatbázis naplózási beállításait módosítja.
        - Megjelenik a Set-AzureRmSqlServerAuditing parancsmag, mely egy Azure SQL Server-kiszolgáló naplózási beállításait módosítja.
    * A meglévő naplózási szabályzatra vonatkozó parancsmagok elavulttá válnak
        - A Get-AzureRmSqlDatabaseAuditingPolicy parancsmag elavulttá válik
        - A Get-AzureRmSqlServerAuditingPolicy parancsmag elavulttá válik
        - A Set-AzureRmSqlDatabaseAuditingPolicy parancsmag elavulttá válik
        - A Set-AzureRmSqlServerAuditingPolicy parancsmag elavulttá válik
        - A Use-AzureRmSqlServerAuditingPolicy parancsmag elavulttá válik
        - A Remove-AzureRmSqlDatabaseAuditing parancsmag elavulttá válik
        - A Remove-AzureRmSqlServerAuditing parancsmag elavulttá válik
    * A sémafájlok elemzése az Update-AzureRmSqlSyncGroup parancsmag esetében mostantól nem különbözteti meg a kis- és nagybetűket.
* Storage
    * A NetworkRule tulajdonság támogatása az erőforrásmód-tárfiókok parancsmagjaihoz
        - New-AzureRmStorageAccount
        - Set-AzureRmStorageAccount
        - Get-AzureRmStorageAccountNetworkRuleSet
        - Update-AzureRmStorageAccountNetworkRuleSet
        - Add-AzureRmStorageAccountNetworkRule
        - Remove-AzureRmStorageAccountNetworkRule

[A legutóbbi kiadás óta történt változások](https://github.com/Azure/azure-powershell/compare/v4.2.1-July2017...v4.3.1-August2017) megtekintése

---
title: "Az Azure PowerShell telepítése és konfigurálása macOS és Linux rendszeren | Microsoft Docs"
description: "Az Azure PowerShell telepítése és konfigurálása az első használathoz macOS és Linux rendszeren."
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/06/2017
ms.openlocfilehash: 94b39c18acaca7a4b17b5207feed025442665acc
ms.sourcegitcommit: c42c7176276ec4e1cc3360a93e6b15d32083bf9f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/14/2017
---
# <a name="install-and-configure-azure-powershell-on-macos-and-linux"></a>Az Azure PowerShell telepítése és konfigurálása macOS és Linux rendszeren

A PowerShell 6-os verziója (béta) és az Azure PowerShell most már nem Windows rendszerű platformokra is telepíthető.
Az Azure PowerShell macOS és Linux rendszeren való telepítése nem sokban tér el a Windows rendszeren való telepítéstől, azonban először telepítenie kell a PowerShell 6-os verzióját (béta) is.

> [!NOTE]

> Jelenleg a PowerShell 6 (béta) és a .NET Core-hoz készült Azure PowerShell csak a bétaverzióban érhető el.
> A termékek korlátozott támogatással rendelkeznek. Ha problémákba ütközik vagy hibákat észlel, kérjük, a GitHubon keresztül jelentse.
>
> * [A PowerShell 6 (béta) problémái](https://github.com/PowerShell/PowerShell/issues)
> * [Az Azure PowerShell problémái](https://github.com/azure/azure-docs-powershell/issues)

## <a name="step-1-install-powershell-6-beta"></a>1. lépés: A PowerShell 6 (béta) telepítése

A PowerShell 6 (béta) telepítési folyamata a cél operációs rendszertől függően változik.
Bár a PowerShell 6-os verziója (béta) a Windows rendszeren is telepíthető, ez a cikk a macOS és a Linux rendszerre összpontosít. Ha Windows rendszeren szeretné használni az Azure PowerShellt, tekintse meg a Windowsra vonatkozó [telepítési](./install-azurerm-ps.md) cikket.

A **PowerShell 6** (béta) Linux vagy macOS rendszeren való telepítéséhez a következőket kell tennie:

1. Szerezze be az adott operációs rendszerhez és verzióhoz tartozó PowerShellt a [GitHubról](https://github.com/powershell/powershell#get-powershell)
2. Kövesse a telepítési utasításokat
   - [Linux](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md)
   - [macOS](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md#macos-1012)

## <a name="step-2-install-azure-powershell-for-net-core"></a>2. lépés: A .NET Core-hoz készült Azure PowerShell telepítése

A PowerShell 6-os verziója (béta) tartalmazza az előre telepített PowerShellGet modult. Ez megkönnyíti a PowerShell-galériában közzétett modulok telepítését. Az Azure PowerShell telepítéséhez nyisson meg egy új PowerShell-munkamenetet, majd futtassa az alábbi parancsot:

```powershell
Install-Module AzureRM.NetCore
```

## <a name="step-3-load-the-azurermnetcore-module"></a>3. lépés: Az AzureRM.Netcore modul betöltése

A modul telepítése után be kell tölteni a azt a PowerShell-munkamenetbe. A modulok az `Import-Module` parancsmaggal, az alábbi módon tölthetők be:

```powershell
Import-Module AzureRM.Netcore
```

Amikor az importálás befejeződött, tesztelheti az újonnan telepített modult. Ehhez próbáljon meg bejelentkezni az Azure-ba az alábbi paranccsal:

```powershell
Login-AzureRMAccount
```

A fenti parancsnak fel kell kérnie, hogy lépjen a `https://aka.ms/devicelogin` oldalra, és adja meg a megadott kódot.

## <a name="available-cmdlets"></a>Elérhető parancsmagok

A .NET Standardhoz elérhető Azure PowerShell-modulok még fejlesztés alatt állnak. Ezek a modulok nem tartalmazzák a modulok Windows verziójához elérhető teljes parancsmagkészletét. Az AzureRM.Netcore-modulokban az alábbi funkciók érhetők el:

* Fiókkezelés
  - Bejelentkezés Microsoft-fiókkal, szervezeti fiókkal vagy egyszerű szolgáltatásnévvel a Microsoft Azure Active Directoryn keresztül
  - Hitelesítő adatokat mentése lemezre a Save-AzureRmContext parancsmaggal és a mentett hitelesítő adatok betöltése az Import-AzureRmContext parancsmaggal
* Környezet
  - Különböző nem beépített Microsoft Azure-környezetek beszerzése
  - Testre szabott környezetek (például az Azure Stack- vagy a Windows Azure Pack-környezetek) hozzáadása/beállítása/eltávolítása
* Felügyeletisík-parancsmagok az Azure-szolgáltatásokhoz a Resource Manager és a Service Manager felületeinek használatával.
  - Virtuális gép
  - App Service (webhelyek)
  - SQL Database
  - Storage
  - Network (Hálózat)

## <a name="next-steps"></a>Következő lépések

Az Azure PowerShell használatával kapcsolatos további információkért tekintse meg az [Ismerkedés az Azure PowerShell szolgáltatással](get-started-azureps.md) című cikket.

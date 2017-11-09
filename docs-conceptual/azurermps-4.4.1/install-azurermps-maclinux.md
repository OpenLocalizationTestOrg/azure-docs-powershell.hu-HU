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
ms.sourcegitcommit: b256bf48e15ee98865de0fae50e7b81878b03a54
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/03/2017
---
# <a name="install-and-configure-azure-powershell-on-macos-and-linux"></a><span data-ttu-id="9d1ce-103">Az Azure PowerShell telepítése és konfigurálása macOS és Linux rendszeren</span><span class="sxs-lookup"><span data-stu-id="9d1ce-103">Install and configure Azure PowerShell on macOS and Linux</span></span>

<span data-ttu-id="9d1ce-104">A PowerShell 6-os verziója (béta) és az Azure PowerShell most már nem Windows rendszerű platformokra is telepíthető.</span><span class="sxs-lookup"><span data-stu-id="9d1ce-104">It is now possible to install PowerShell 6 (beta) and Azure PowerShell on non-Windows platforms.</span></span>
<span data-ttu-id="9d1ce-105">Az Azure PowerShell macOS és Linux rendszeren való telepítése nem sokban tér el a Windows rendszeren való telepítéstől, azonban először telepítenie kell a PowerShell 6-os verzióját (béta) is.</span><span class="sxs-lookup"><span data-stu-id="9d1ce-105">The process of installing Azure PowerShell on macOS and Linux is not that different from Windows, however, you must first install PowerShell 6 (beta).</span></span>

> [!NOTE]

> <span data-ttu-id="9d1ce-106">Jelenleg a PowerShell 6 (béta) és a .NET Core-hoz készült Azure PowerShell csak a bétaverzióban érhető el.</span><span class="sxs-lookup"><span data-stu-id="9d1ce-106">At this time, both PowerShell 6 (beta) and Azure PowerShell for .NET Core are still in beta.</span></span>
> <span data-ttu-id="9d1ce-107">A termékek korlátozott támogatással rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="9d1ce-107">Support for these products is limited.</span></span> <span data-ttu-id="9d1ce-108">Ha problémákba ütközik vagy hibákat észlel, kérjük, a GitHubon keresztül jelentse.</span><span class="sxs-lookup"><span data-stu-id="9d1ce-108">If you have problems or discover bugs, please file Issues in GitHub.</span></span>
>
> * [<span data-ttu-id="9d1ce-109">A PowerShell 6 (béta) problémái</span><span class="sxs-lookup"><span data-stu-id="9d1ce-109">Issues for PowerShell 6 (beta)</span></span>](https://github.com/PowerShell/PowerShell/issues)
> * [<span data-ttu-id="9d1ce-110">Az Azure PowerShell problémái</span><span class="sxs-lookup"><span data-stu-id="9d1ce-110">Issues for Azure PowerShell</span></span>](https://github.com/azure/azure-docs-powershell/issues)

## <a name="step-1-install-powershell-6-beta"></a><span data-ttu-id="9d1ce-111">1. lépés: A PowerShell 6 (béta) telepítése</span><span class="sxs-lookup"><span data-stu-id="9d1ce-111">Step 1: Install PowerShell 6 (beta)</span></span>

<span data-ttu-id="9d1ce-112">A PowerShell 6 (béta) telepítési folyamata a cél operációs rendszertől függően változik.</span><span class="sxs-lookup"><span data-stu-id="9d1ce-112">The process of installing PowerShell 6 (beta) on varies depending on the target operating system.</span></span>
<span data-ttu-id="9d1ce-113">Bár a PowerShell 6-os verziója (béta) a Windows rendszeren is telepíthető, ez a cikk a macOS és a Linux rendszerre összpontosít.</span><span class="sxs-lookup"><span data-stu-id="9d1ce-113">While it is possible to install PowerShell 6 (beta) on Windows, this article focuses on macOS and Linux.</span></span> <span data-ttu-id="9d1ce-114">Ha Windows rendszeren szeretné használni az Azure PowerShellt, tekintse meg a Windowsra vonatkozó [telepítési](./install-azurerm-ps.md) cikket.</span><span class="sxs-lookup"><span data-stu-id="9d1ce-114">If you want to use Azure PowerShell on Windows, see the [install](./install-azurerm-ps.md) article for Windows.</span></span>

<span data-ttu-id="9d1ce-115">A **PowerShell 6** (béta) Linux vagy macOS rendszeren való telepítéséhez a következőket kell tennie:</span><span class="sxs-lookup"><span data-stu-id="9d1ce-115">To install **PowerShell 6** (beta) on Linux or macOS, you need to:</span></span>

1. <span data-ttu-id="9d1ce-116">Szerezze be az adott operációs rendszerhez és verzióhoz tartozó PowerShellt a [GitHubról](https://github.com/powershell/powershell#get-powershell)</span><span class="sxs-lookup"><span data-stu-id="9d1ce-116">Get PowerShell for the specific OS and version, from [GitHub](https://github.com/powershell/powershell#get-powershell)</span></span>
2. <span data-ttu-id="9d1ce-117">Kövesse a telepítési utasításokat</span><span class="sxs-lookup"><span data-stu-id="9d1ce-117">Follow the installation instructions</span></span>
   - [<span data-ttu-id="9d1ce-118">Linux</span><span class="sxs-lookup"><span data-stu-id="9d1ce-118">Linux</span></span>](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md)
   - [<span data-ttu-id="9d1ce-119">macOS</span><span class="sxs-lookup"><span data-stu-id="9d1ce-119">macOS</span></span>](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md#macos-1012)

## <a name="step-2-install-azure-powershell-for-net-core"></a><span data-ttu-id="9d1ce-120">2. lépés: A .NET Core-hoz készült Azure PowerShell telepítése</span><span class="sxs-lookup"><span data-stu-id="9d1ce-120">Step 2: Install Azure PowerShell for .NET Core</span></span>

<span data-ttu-id="9d1ce-121">A PowerShell 6-os verziója (béta) tartalmazza az előre telepített PowerShellGet modult.</span><span class="sxs-lookup"><span data-stu-id="9d1ce-121">PowerShell 6 (beta) comes with the PowerShellGet module already installed.</span></span> <span data-ttu-id="9d1ce-122">Ez megkönnyíti a PowerShell-galériában közzétett modulok telepítését.</span><span class="sxs-lookup"><span data-stu-id="9d1ce-122">This makes it easy to install any module that is published to the PowerShell Gallery.</span></span> <span data-ttu-id="9d1ce-123">Az Azure PowerShell telepítéséhez nyisson meg egy új PowerShell-munkamenetet, majd futtassa az alábbi parancsot:</span><span class="sxs-lookup"><span data-stu-id="9d1ce-123">To install Azure PowerShell, open a new PowerShell session and run the following command:</span></span>

```powershell
Install-Module AzureRM.NetCore
```

## <a name="step-3-load-the-azurermnetcore-module"></a><span data-ttu-id="9d1ce-124">3. lépés: Az AzureRM.Netcore modul betöltése</span><span class="sxs-lookup"><span data-stu-id="9d1ce-124">Step 3: Load the AzureRM.Netcore module</span></span>

<span data-ttu-id="9d1ce-125">A modul telepítése után be kell tölteni a azt a PowerShell-munkamenetbe.</span><span class="sxs-lookup"><span data-stu-id="9d1ce-125">Once the module is installed, you need to load the module into your PowerShell session.</span></span> <span data-ttu-id="9d1ce-126">A modulok az `Import-Module` parancsmaggal, az alábbi módon tölthetők be:</span><span class="sxs-lookup"><span data-stu-id="9d1ce-126">Modules are loaded using the `Import-Module` cmdlet, as follows:</span></span>

```powershell
Import-Module AzureRM.Netcore
```

<span data-ttu-id="9d1ce-127">Amikor az importálás befejeződött, tesztelheti az újonnan telepített modult. Ehhez próbáljon meg bejelentkezni az Azure-ba az alábbi paranccsal:</span><span class="sxs-lookup"><span data-stu-id="9d1ce-127">After the import completes, you can test your newly installed and module by attempting to sign into Azure using the following command:</span></span>

```powershell
Login-AzureRMAccount
```

<span data-ttu-id="9d1ce-128">A fenti parancsnak fel kell kérnie, hogy lépjen a `https://aka.ms/devicelogin` oldalra, és adja meg a megadott kódot.</span><span class="sxs-lookup"><span data-stu-id="9d1ce-128">The above command should prompt you to go to `https://aka.ms/devicelogin` and enter the provided code.</span></span>

## <a name="available-cmdlets"></a><span data-ttu-id="9d1ce-129">Elérhető parancsmagok</span><span class="sxs-lookup"><span data-stu-id="9d1ce-129">Available cmdlets</span></span>

<span data-ttu-id="9d1ce-130">A .NET Standardhoz elérhető Azure PowerShell-modulok még fejlesztés alatt állnak.</span><span class="sxs-lookup"><span data-stu-id="9d1ce-130">The Azure PowerShell modules for .NET Standard are still in development.</span></span> <span data-ttu-id="9d1ce-131">Ezek a modulok nem tartalmazzák a modulok Windows verziójához elérhető teljes parancsmagkészletét.</span><span class="sxs-lookup"><span data-stu-id="9d1ce-131">These modules do not provide the full set of cmdlets that are available for the Windows version of the modules.</span></span> <span data-ttu-id="9d1ce-132">Az AzureRM.Netcore-modulokban az alábbi funkciók érhetők el:</span><span class="sxs-lookup"><span data-stu-id="9d1ce-132">The following functions are implemented in AzureRM.Netcore modules:</span></span>

* <span data-ttu-id="9d1ce-133">Fiókkezelés</span><span class="sxs-lookup"><span data-stu-id="9d1ce-133">Account management</span></span>
  - <span data-ttu-id="9d1ce-134">Bejelentkezés Microsoft-fiókkal, szervezeti fiókkal vagy egyszerű szolgáltatásnévvel a Microsoft Azure Active Directoryn keresztül</span><span class="sxs-lookup"><span data-stu-id="9d1ce-134">Login with Microsoft account, Organizational account, or Service Principal through Microsoft Azure Active Directory</span></span>
  - <span data-ttu-id="9d1ce-135">Hitelesítő adatokat mentése lemezre a Save-AzureRmContext parancsmaggal és a mentett hitelesítő adatok betöltése az Import-AzureRmContext parancsmaggal</span><span class="sxs-lookup"><span data-stu-id="9d1ce-135">Save Credentials to disk with Save-AzureRmContext and load saved credentials using Import-AzureRmContext</span></span>
* <span data-ttu-id="9d1ce-136">Környezet</span><span class="sxs-lookup"><span data-stu-id="9d1ce-136">Environment</span></span>
  - <span data-ttu-id="9d1ce-137">Különböző nem beépített Microsoft Azure-környezetek beszerzése</span><span class="sxs-lookup"><span data-stu-id="9d1ce-137">Get the different out-of-box Microsoft Azure environments</span></span>
  - <span data-ttu-id="9d1ce-138">Testre szabott környezetek (például az Azure Stack- vagy a Windows Azure Pack-környezetek) hozzáadása/beállítása/eltávolítása</span><span class="sxs-lookup"><span data-stu-id="9d1ce-138">Add/Set/Remove customized environments (like your Azure Stack or Windows Azure Pack environments)</span></span>
* <span data-ttu-id="9d1ce-139">Felügyeletisík-parancsmagok az Azure-szolgáltatásokhoz a Resource Manager és a Service Manager felületeinek használatával.</span><span class="sxs-lookup"><span data-stu-id="9d1ce-139">Management plane cmdlets for Azure services using Resource Manager and Service Management interfaces.</span></span>
  - <span data-ttu-id="9d1ce-140">Virtuális gép</span><span class="sxs-lookup"><span data-stu-id="9d1ce-140">Virtual Machine</span></span>
  - <span data-ttu-id="9d1ce-141">App Service (webhelyek)</span><span class="sxs-lookup"><span data-stu-id="9d1ce-141">App Service (Websites)</span></span>
  - <span data-ttu-id="9d1ce-142">SQL Database</span><span class="sxs-lookup"><span data-stu-id="9d1ce-142">SQL Database</span></span>
  - <span data-ttu-id="9d1ce-143">Storage</span><span class="sxs-lookup"><span data-stu-id="9d1ce-143">Storage</span></span>
  - <span data-ttu-id="9d1ce-144">Network (Hálózat)</span><span class="sxs-lookup"><span data-stu-id="9d1ce-144">Network</span></span>

## <a name="next-steps"></a><span data-ttu-id="9d1ce-145">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="9d1ce-145">Next Steps</span></span>

<span data-ttu-id="9d1ce-146">Az Azure PowerShell használatával kapcsolatos további információkért tekintse meg az [Ismerkedés az Azure PowerShell szolgáltatással](get-started-azureps.md) című cikket.</span><span class="sxs-lookup"><span data-stu-id="9d1ce-146">For more information about using Azure PowerShell, see the [Get started with Azure PowerShell](get-started-azureps.md) article.</span></span>

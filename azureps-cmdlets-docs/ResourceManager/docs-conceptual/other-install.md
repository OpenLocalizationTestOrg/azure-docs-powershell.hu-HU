---
title: "Az Azure PowerShell telepítésének egyéb módjai | Microsoft Docs"
description: "Az Azure PowerShell telepítése az MSI-csomag vagy a Webplatform-telepítő használatával."
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/15/2017
ms.openlocfilehash: 9cee582f74b7f3260c6ae167a8ac358d360ad8ab
ms.sourcegitcommit: 45587b5091293288e16cfae8ac412e0d42f8f450
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/15/2017
---
# <a name="other-installation-methods"></a><span data-ttu-id="e5512-103">Egyéb telepítési módszerek</span><span class="sxs-lookup"><span data-stu-id="e5512-103">Other installation methods</span></span>

<span data-ttu-id="e5512-104">Az Azure PowerShell többféle módszerrel telepíthető.</span><span class="sxs-lookup"><span data-stu-id="e5512-104">Azure PowerShell has multiple installation methods.</span></span> <span data-ttu-id="e5512-105">Az előnyben részesített módszer a PowerShellGet használata a PowerShell-galériával.</span><span class="sxs-lookup"><span data-stu-id="e5512-105">Using PowerShellGet with the PowerShell Gallery is the preferred method.</span></span> <span data-ttu-id="e5512-106">Az Azure PowerShell telepíthető a Webplatform-telepítő (WebPI) vagy a [GitHubról](https://github.com/Azure/azure-powershell/releases/latest) elérhető MSI-fájl használatával.</span><span class="sxs-lookup"><span data-stu-id="e5512-106">Azure PowerShell can be installed using the Web Platform Installer (WebPI) or by using the MSI file available from [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span></span>

## <a name="docker"></a><span data-ttu-id="e5512-107">Docker</span><span class="sxs-lookup"><span data-stu-id="e5512-107">Docker</span></span>

<span data-ttu-id="e5512-108">Elérhető az Azure PowerShell-hez előre konfigurált Docker-rendszerkép.</span><span class="sxs-lookup"><span data-stu-id="e5512-108">We maintain a Docker image preconfigured with Azure PowerShell.</span></span>

<span data-ttu-id="e5512-109">A tárolót a következő paranccsal futtathatja: `docker run`.</span><span class="sxs-lookup"><span data-stu-id="e5512-109">Run the container with `docker run`.</span></span>

```powershell
docker run azuresdk/azure-powershell
```

<span data-ttu-id="e5512-110">Emellett elérhető a parancsmagok egy részhalmaza PowerShell Core-tároló formájában.</span><span class="sxs-lookup"><span data-stu-id="e5512-110">In addition, we maintain a subset of cmdlets as a PowerShell Core container.</span></span>

<span data-ttu-id="e5512-111">Mac és Linux rendszereken a `latest` rendszerképet használhatja.</span><span class="sxs-lookup"><span data-stu-id="e5512-111">For Mac/Linux, use the `latest` image.</span></span>

```bash
docker run azuresdk/azure-powershell-core:latest
```

<span data-ttu-id="e5512-112">Windowson a `nanoserver` rendszerképet használhatja.</span><span class="sxs-lookup"><span data-stu-id="e5512-112">For Windows, use the `nanoserver` image.</span></span>

```powershell
docker run azuresdk/azure-powershell-core:nanoserver
```

<span data-ttu-id="e5512-113">Az Azure PowerShell az `Install-Module` parancsmaggal van telepítve a [PowerShell-galériából](https://www.powershellgallery.com/).</span><span class="sxs-lookup"><span data-stu-id="e5512-113">Azure PowerShell is installed on the image via `Install-Module` from the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>

## <a name="install-using-the-web-platform-installer"></a><span data-ttu-id="e5512-114">Telepítés a Webplatform-telepítővel</span><span class="sxs-lookup"><span data-stu-id="e5512-114">Install using the Web Platform Installer</span></span>

<span data-ttu-id="e5512-115">A legújabb Azure PowerShell ugyanúgy telepíthető a WebPI-ről, ahogy a korábbi verziók.</span><span class="sxs-lookup"><span data-stu-id="e5512-115">Installing the latest Azure PowerShell from WebPI is the same as it was for previous versions.</span></span>
<span data-ttu-id="e5512-116">Töltse le az [Azure PowerShell WebPI csomagot](http://aka.ms/webpi-azps), és indítsa el a telepítést.</span><span class="sxs-lookup"><span data-stu-id="e5512-116">Download the [Azure PowerShell WebPI package](http://aka.ms/webpi-azps) and start the install.</span></span>

> [!NOTE]
> <span data-ttu-id="e5512-117">Ha korábban már telepített Azure-modulokat a PowerShell-galériából, a telepítő automatikusan eltávolítja őket.</span><span class="sxs-lookup"><span data-stu-id="e5512-117">If you have previously installed Azure modules from the PowerShell Gallery, the installer automatically removes them.</span></span> <span data-ttu-id="e5512-118">Ez egyszerűbbé teszi a környezetet, mivel így biztosítható, hogy csak egy Azure PowerShell-verzió lesz telepítve.</span><span class="sxs-lookup"><span data-stu-id="e5512-118">This simplifies your environment by ensuring that only one version of Azure PowerShell is installed.</span></span> <span data-ttu-id="e5512-119">Léteznek azonban olyan forgatókönyvek, amikor több telepített verzióra lehet szüksége egy időben.</span><span class="sxs-lookup"><span data-stu-id="e5512-119">However, there are scenarios where you may need multiple versions installed at the same time.</span></span>
>
> <span data-ttu-id="e5512-120">A PowerShell-galéria moduljai a következő helyen települnek: `$env:ProgramFiles\WindowsPowerShell\Modules`.</span><span class="sxs-lookup"><span data-stu-id="e5512-120">PowerShell Gallery modules install modules in `$env:ProgramFiles\WindowsPowerShell\Modules`.</span></span> <span data-ttu-id="e5512-121">A WebPI telepítője ezzel szemben a következő helyen telepíti az Azure-modulokat: `$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\`.</span><span class="sxs-lookup"><span data-stu-id="e5512-121">In contrast, the WebPI installer installs the Azure modules in `$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\`.</span></span>
>
> <span data-ttu-id="e5512-122">Ha hiba merül fel a telepítés során, törölje manuálisan az Azure* mappákat a `$env:ProgramFiles\WindowsPowerShell\Modules` mappából, és próbálkozzon újra a telepítéssel.</span><span class="sxs-lookup"><span data-stu-id="e5512-122">If an error occurs during install, you can manually remove the Azure* folders in your `$env:ProgramFiles\WindowsPowerShell\Modules` folder, and try the installation again.</span></span>

<span data-ttu-id="e5512-123">A telepítés befejeztével a `$env:PSModulePath` beállításnak tartalmaznia kell az Azure PowerShell-parancsmagokat tartalmazó könyvtárakat.</span><span class="sxs-lookup"><span data-stu-id="e5512-123">Once the installation completes, your `$env:PSModulePath` setting should include the directories containing the Azure PowerShell cmdlets.</span></span> <span data-ttu-id="e5512-124">A következő paranccsal ellenőrizheti, hogy az Azure PowerShell megfelelően van-e telepítve.</span><span class="sxs-lookup"><span data-stu-id="e5512-124">The following command can be used to verify that the Azure PowerShell is installed properly.</span></span>

```powershell
# To make sure the Azure PowerShell module is available after you install
Get-Module -ListAvailable Azure* | Select-Object Name, Version, Path
```

> [!NOTE]
> <span data-ttu-id="e5512-125">Létezik egy ismert hiba, amely a WebPI telepítésekor léphet fel.</span><span class="sxs-lookup"><span data-stu-id="e5512-125">There is a known issue that can occur when installing from WebPI.</span></span> <span data-ttu-id="e5512-126">Ha a számítógépet a rendszerfrissítések és egyéb telepítések miatt újra kell indítani, előfordulhat, hogy az `$env:PSModulePath` frissítései nem tartalmazzák az Azure PowerShell telepítési útvonalát.</span><span class="sxs-lookup"><span data-stu-id="e5512-126">If your computer requires a restart due to system updates or other installations, it may cause updates to `$env:PSModulePath` to fail to include the path where Azure PowerShell is installed.</span></span>

<span data-ttu-id="e5512-127">A parancsmagok telepítés utáni betöltése vagy végrehajtása során a következő hibaüzenet jelenhet meg:</span><span class="sxs-lookup"><span data-stu-id="e5512-127">When attempting to load or execute cmdlets after installation, you can receive the following error message:</span></span>

```
PS C:\> Login-AzureRmAccount
Login-AzureRmAccount : The term 'Login-AzureRmAccount' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:1 char:1
+ Login-AzureRmAccount
+ ~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (Login-AzureRmAccount:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

<span data-ttu-id="e5512-128">Ez a hiba a gép újraindításával vagy a modul teljes útvonallal való importálásával javítható.</span><span class="sxs-lookup"><span data-stu-id="e5512-128">This error can be corrected by restarting the machine or importing the module using the fully qualified path.</span></span> <span data-ttu-id="e5512-129">Példa:</span><span class="sxs-lookup"><span data-stu-id="e5512-129">For example:</span></span>

```powershell
Import-Module "$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\AzureRM.psd1"
```

## <a name="install-using-the-msi-package"></a><span data-ttu-id="e5512-130">Telepítés az MSI-csomaggal</span><span class="sxs-lookup"><span data-stu-id="e5512-130">Install using the MSI Package</span></span>

<span data-ttu-id="e5512-131">Az Azure PowerShell telepíthető a [GitHubról](https://github.com/Azure/azure-powershell/releases/latest) elérhető MSI-fájllal is.</span><span class="sxs-lookup"><span data-stu-id="e5512-131">Azure PowerShell can be installed using the MSI file available from [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span></span> <span data-ttu-id="e5512-132">Ha az Azure-modulok korábbi verziói már telepítve vannak, a telepítő automatikusan eltávolítja őket.</span><span class="sxs-lookup"><span data-stu-id="e5512-132">If you have installed previous versions of Azure modules, the installer automatically removes them.</span></span> <span data-ttu-id="e5512-133">Az MSI-csomag a(z) `$env:ProgramFiles\WindowsPowerShell\Modules` helyre telepíti a modulokat, azonban nem hoz létre verzióspecifikus mappákat.</span><span class="sxs-lookup"><span data-stu-id="e5512-133">The MSI package installs modules in `$env:ProgramFiles\WindowsPowerShell\Modules` but does not create version-specific folders.</span></span>

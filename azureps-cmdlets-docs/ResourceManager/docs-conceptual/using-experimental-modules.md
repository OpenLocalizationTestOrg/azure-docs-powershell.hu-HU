---
title: "Kísérleti Azure PowerShell-modulok használata"
description: "A kísérleti Azure PowerShell-modulok filozófiájának és használatának ismertetése."
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/05/2017
ms.openlocfilehash: 4a8a74977440fa89b89843bbc95e43d622a58474
ms.sourcegitcommit: e6b7e20bbd04eda51416c56b13f867102b602d1a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/07/2017
---
# <a name="using-experimental-azure-powershell-modules"></a><span data-ttu-id="c2caf-103">Kísérleti Azure PowerShell-modulok használata</span><span class="sxs-lookup"><span data-stu-id="c2caf-103">Using experimental Azure PowerShell modules</span></span>

<span data-ttu-id="c2caf-104">Mivel az Azure a fejlesztői eszközökre (különösen a parancssori felületekre) helyezi a hangsúlyt, az Azure PowerShell csapata az Azure PowerShell felhasználói felületének számos fejlesztésével kísérletezik.</span><span class="sxs-lookup"><span data-stu-id="c2caf-104">With the emphasis on developer tools (especially CLIs) in Azure, the Azure PowerShell team is experimenting with many improvements to the Azure PowerShell experience.</span></span>

## <a name="experimentation-methodology"></a><span data-ttu-id="c2caf-105">Kísérleti módszertan</span><span class="sxs-lookup"><span data-stu-id="c2caf-105">Experimentation methodology</span></span>

<span data-ttu-id="c2caf-106">A kísérletezés érdekében új Azure PowerShell-modulokat hozunk létre, amelyek az Azure SDK meglévő funkcióit új, könnyebben használható módon kezelik.</span><span class="sxs-lookup"><span data-stu-id="c2caf-106">To facilitate experimentation, we are creating new Azure PowerShell modules that implement existing Azure SDK functionality in new, easier to use ways.</span></span> <span data-ttu-id="c2caf-107">A parancsmagok a legtöbb esetben pontosan megegyeznek a meglévő parancsmagokkal.</span><span class="sxs-lookup"><span data-stu-id="c2caf-107">In most cases, the cmdlets exactly mirror existing cmdlets.</span></span> <span data-ttu-id="c2caf-108">A kísérleti parancsmagok azonban olyan egyszerűsített jelölésrendszert és intelligensebb alapértelmezett értékeket kínálnak, amelyekkel könnyebben hozhatók létre és kezelhetők az Azure-erőforrások.</span><span class="sxs-lookup"><span data-stu-id="c2caf-108">However, the experimental cmdlets provide a shorthand notation and smarter default values that make it easier to create and manage Azure resources.</span></span>

<span data-ttu-id="c2caf-109">Ezek a modulok a meglévő Azure PowerShell-modulok mellett telepíthetők.</span><span class="sxs-lookup"><span data-stu-id="c2caf-109">These modules can be installed side-by-side with existing Azure PowerShell modules.</span></span> <span data-ttu-id="c2caf-110">A parancsmagneveket lerövidítettük, hogy rövidebb neveket kelljen megadni, illetve hogy elkerüljük a névütközést a meglévő, nem kísérleti parancsmagokkal.</span><span class="sxs-lookup"><span data-stu-id="c2caf-110">The cmdlet names have been shortened to provide shorter names and avoid name conflicts with existing, non-experimental cmdlets.</span></span>

<span data-ttu-id="c2caf-111">A kísérleti modulok az alábbi elnevezési szabályt követik:</span><span class="sxs-lookup"><span data-stu-id="c2caf-111">The experimental modules use the following naming convention:</span></span>

- <span data-ttu-id="c2caf-112">AzureRM.Compute.Experiments</span><span class="sxs-lookup"><span data-stu-id="c2caf-112">AzureRM.Compute.Experiments</span></span>
- <span data-ttu-id="c2caf-113">AzureRM.Websites.Experiments</span><span class="sxs-lookup"><span data-stu-id="c2caf-113">AzureRM.Websites.Experiments</span></span>

<span data-ttu-id="c2caf-114">Ez a elnevezési szabály az előzetes verziójú modulok elnevezéséhez hasonló: `AzureRM.*.Preview`.</span><span class="sxs-lookup"><span data-stu-id="c2caf-114">This naming convention is similar to the naming of Preview modules: `AzureRM.*.Preview`.</span></span> <span data-ttu-id="c2caf-115">Az előzetes verziójú modulok nem azonosak a kísérleti modulokkal.</span><span class="sxs-lookup"><span data-stu-id="c2caf-115">Preview modules differ from experimental modules.</span></span> <span data-ttu-id="c2caf-116">Az előzetes modulok az Azure-szolgáltatások olyan új funkcióit valósítják meg, amelyek csak előzetes ajánlatként érhetők el.</span><span class="sxs-lookup"><span data-stu-id="c2caf-116">Preview modules implement new functionality of Azure services that is only available as a Preview offering.</span></span> <span data-ttu-id="c2caf-117">Az előzetes verziójú modulok a meglévő Azure PowerShell-modulokat váltják fel, és ugyanazokat a parancsmag- és paraméterneveket használják.</span><span class="sxs-lookup"><span data-stu-id="c2caf-117">Preview modules replace existing Azure PowerShell modules and use the same cmdlet and parameter names.</span></span>

## <a name="how-to-install-an-experimental-module"></a><span data-ttu-id="c2caf-118">A kísérleti modulok telepítése</span><span class="sxs-lookup"><span data-stu-id="c2caf-118">How to install an experimental module</span></span>

<span data-ttu-id="c2caf-119">A kísérleti modulok a meglévő Azure PowerShell-modulokhoz hasonlóan a PowerShell-galériában vannak közzétéve.</span><span class="sxs-lookup"><span data-stu-id="c2caf-119">Experimental modules are published to the PowerShell Gallery just like the existing Azure PowerShell modules.</span></span> <span data-ttu-id="c2caf-120">A kísérleti modulok telepítéséhez használja a következő parancsokat egy emelt szintű PowerShell-munkamenetből:</span><span class="sxs-lookup"><span data-stu-id="c2caf-120">To install the experimental module, use the following commands from an elevated PowerShell session:</span></span>

```powershell
Install-Module AzureRM.Compute.Experiments
Install-Module AzureRM.Websites.Experiments
```

### <a name="documentation-and-support"></a><span data-ttu-id="c2caf-121">Dokumentáció és támogatás</span><span class="sxs-lookup"><span data-stu-id="c2caf-121">Documentation and support</span></span>

<span data-ttu-id="c2caf-122">A dokumentációt a telepítőcsomag tartalmazza, és a `Get-Help` parancsmaggal érhető el.</span><span class="sxs-lookup"><span data-stu-id="c2caf-122">Documentation is included in the install package and is accessed using the `Get-Help` cmdlet.</span></span> <span data-ttu-id="c2caf-123">A kísérleti modulokhoz nem jelenik meg hivatalos dokumentáció.</span><span class="sxs-lookup"><span data-stu-id="c2caf-123">No official documentation is published for experimental modules.</span></span>

<span data-ttu-id="c2caf-124">Javasoljuk, hogy tesztelje ezeket a modulokat.</span><span class="sxs-lookup"><span data-stu-id="c2caf-124">We encourage you to test these modules.</span></span> <span data-ttu-id="c2caf-125">A visszajelzések segítenek nekünk a modulok használhatóságának fejlesztésében és a felhasználói igények kielégítésében.</span><span class="sxs-lookup"><span data-stu-id="c2caf-125">Your feedback allows us to improve usability and respond to your needs.</span></span> <span data-ttu-id="c2caf-126">Mivel azonban ezek kísérleti modulok, csak korlátozott támogatás érhető el hozzájuk.</span><span class="sxs-lookup"><span data-stu-id="c2caf-126">However, being experimental, support for these modules is limited.</span></span> <span data-ttu-id="c2caf-127">Kérdéseit és a hibajelentéseket egy [hibajegy](https://github.com/Azure/azure-powershell/issues) létrehozásával küldheti be a GitHub-adattárban.</span><span class="sxs-lookup"><span data-stu-id="c2caf-127">Questions or problem reports can be submitted by creating an [issue](https://github.com/Azure/azure-powershell/issues) in the GitHub repository.</span></span>

## <a name="experiments-and-areas-of-improvement"></a><span data-ttu-id="c2caf-128">Kísérletek és fejlesztési területek</span><span class="sxs-lookup"><span data-stu-id="c2caf-128">Experiments and areas of improvement</span></span>

<span data-ttu-id="c2caf-129">Ezeket a fejlesztéseket a versenytársaink termékeinek főbb előnyei alapján választottuk ki.</span><span class="sxs-lookup"><span data-stu-id="c2caf-129">These improvements were selected based on key differentiators in competing products.</span></span> <span data-ttu-id="c2caf-130">Például az Azure CLI 2.0 egyik fontos eleme, hogy a parancsok _forgatókönyveken_, és nem _API felületeken_ alapulnak.</span><span class="sxs-lookup"><span data-stu-id="c2caf-130">For example, Azure CLI 2.0 has made a point of basing commands on _scenarios_ rather than _API surface area_.</span></span>
<span data-ttu-id="c2caf-131">Az Azure CLI 2.0 számos intelligens alapértelmezett értéket alkalmaz, amelyekkel az „első lépések” forgatókönyvek könnyebben használhatók a végfelhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="c2caf-131">Azure CLI 2.0 use a number of smart defaults that make "getting started" scenarios easier for end users.</span></span>

### <a name="core-improvements"></a><span data-ttu-id="c2caf-132">Központi fejlesztések</span><span class="sxs-lookup"><span data-stu-id="c2caf-132">Core improvements</span></span>

<span data-ttu-id="c2caf-133">A központi fejlesztések a „józan megfontoláson” alapulnak, és az ilyen frissítések bevezetéséhez nem sok kísérletezés szükséges.</span><span class="sxs-lookup"><span data-stu-id="c2caf-133">The core improvements are regarded as "common sense", and little experimentation is needed to move forward in implementing these updates.</span></span>

- <span data-ttu-id="c2caf-134">Forgatókönyv-alapú parancsmagok – **Minden* parancsmagot forgatókönyvek, és nem az Azure REST-szolgáltatás köré kell építeni.</span><span class="sxs-lookup"><span data-stu-id="c2caf-134">Scenario-based Cmdlets - **All*- cmdlets should be designed around scenarios, not the Azure REST service.</span></span>

- <span data-ttu-id="c2caf-135">Rövidebb nevek – Ez a parancsmagok (például: `New-AzureRmVM` => `New-AzVm`) és a paraméterek (például: `-ResourceGroupName` => `-Rg`) nevére is vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="c2caf-135">Shorter Names - Includes the names of cmdlets (for example, `New-AzureRmVM` => `New-AzVm`) and the names of parameters (for example, `-ResourceGroupName` => `-Rg`).</span></span> <span data-ttu-id="c2caf-136">A „régi” parancsmagokkal való kompatibilitás érdekében aliasok használhatók.</span><span class="sxs-lookup"><span data-stu-id="c2caf-136">Use aliases for compatibility with "old" cmdlets.</span></span> <span data-ttu-id="c2caf-137">Biztosítson _visszafelé kompatibilis_ paraméterkészleteket.</span><span class="sxs-lookup"><span data-stu-id="c2caf-137">Provide _backwards compatible_ parameter sets.</span></span>

- <span data-ttu-id="c2caf-138">Intelligens alapértékek – Adja meg a „szükséges” információkat intelligens alapértelmezett értékekkel.</span><span class="sxs-lookup"><span data-stu-id="c2caf-138">Smart Defaults - Create smart defaults to fill in "required" information.</span></span> <span data-ttu-id="c2caf-139">Példa:</span><span class="sxs-lookup"><span data-stu-id="c2caf-139">For example:</span></span>
  - <span data-ttu-id="c2caf-140">Erőforráscsoport</span><span class="sxs-lookup"><span data-stu-id="c2caf-140">Resource Group</span></span>
  - <span data-ttu-id="c2caf-141">Hely</span><span class="sxs-lookup"><span data-stu-id="c2caf-141">Location</span></span>
  - <span data-ttu-id="c2caf-142">Függő erőforrások</span><span class="sxs-lookup"><span data-stu-id="c2caf-142">Dependent resources</span></span>

### <a name="experimental-improvements"></a><span data-ttu-id="c2caf-143">Kísérleti fejlesztések</span><span class="sxs-lookup"><span data-stu-id="c2caf-143">Experimental improvements</span></span>

<span data-ttu-id="c2caf-144">A kísérleti fejlesztések segítségével a csoport kísérletezéssel tesztelheti a jelentős változásokat.</span><span class="sxs-lookup"><span data-stu-id="c2caf-144">The experimental improvements present a significant change that the team wants to validate via experimentation.</span></span>

- <span data-ttu-id="c2caf-145">Egyszerű típusok – A létrehozási forgatókönyveknek távol kell esniük az összetett típusoktól és a konfigurációs objektumoktól.</span><span class="sxs-lookup"><span data-stu-id="c2caf-145">Simple types - Create scenarios should move away from complex types and config objects.</span></span> <span data-ttu-id="c2caf-146">Egyszerűsítse a konfigurációt egy vagy két paraméterre.</span><span class="sxs-lookup"><span data-stu-id="c2caf-146">Simplify the configuration down to one or two parameters.</span></span>

- <span data-ttu-id="c2caf-147">„Intelligens létrehozás” – Az „intelligens létrehozást” megvalósító egyik létrehozási forgatókönyvhöz _sincs_ kötelező paraméter: az összes szükséges információt az Azure PowerShell választja ki a saját belátása szerint.</span><span class="sxs-lookup"><span data-stu-id="c2caf-147">"Smart Create" - All create scenarios implementing "Smart Create" would have _no_ required parameters: all necessary information would be chosen by Azure PowerShell in an opinionated fashion.</span></span>

- <span data-ttu-id="c2caf-148">Szürke paraméterek – Sok esetben néhány paraméter „szürke” vagy félig választható.</span><span class="sxs-lookup"><span data-stu-id="c2caf-148">Gray Parameters - In many cases, some parameters could be "gray" or semi-optional.</span></span> <span data-ttu-id="c2caf-149">Ha a paraméter nincs megadva, a rendszer megkérdezi a felhasználót, hogy létrejöjjön-e a paraméter.</span><span class="sxs-lookup"><span data-stu-id="c2caf-149">If the parameter is not specified, the user is asked if they want the parameter generated for them.</span></span> <span data-ttu-id="c2caf-150">Szintén célszerű, ha a szürke paraméterek a környezet alapján következtetnek ki egy értéket a felhasználó beleegyezésével.</span><span class="sxs-lookup"><span data-stu-id="c2caf-150">It also makes sense for gray parameters to infer a value based on context with the user's consent.</span></span>
  <span data-ttu-id="c2caf-151">Hasznos lehet például, ha a szürke paraméter a legutóbb használt értéket javasolja.</span><span class="sxs-lookup"><span data-stu-id="c2caf-151">For example, it may make sense to have the gray parameter suggest the most recently used value.</span></span>

- <span data-ttu-id="c2caf-152">`-Auto` kapcsoló – Az `-Auto` kapcsoló „felhasználó által aktiválható” módon biztosítja a felhasználóknak _az összes beállítás alapértelmezett értékre való állítását_, ugyanakkor fenntartja a kötelező paraméterek integritását a fő útvonalon.</span><span class="sxs-lookup"><span data-stu-id="c2caf-152">`-Auto` Switch - The `-Auto` switch would provide an "opt-in" way for users to _default all the things_ while maintaining the integrity of required parameters in the mainline path.</span></span>

### <a name="feature-specific-switches"></a><span data-ttu-id="c2caf-153">Szolgáltatásspecifikus kapcsolók</span><span class="sxs-lookup"><span data-stu-id="c2caf-153">Feature-specific switches</span></span>

<span data-ttu-id="c2caf-154">A „Webalkalmazás létrehozása” forgatókönyv például egy `-Git` vagy `-AddRemote` kapcsolóval rendelkezhet, amely automatikusan egy távoli „azure” mappát ad hozzá egy meglévő Git-adattárhoz.</span><span class="sxs-lookup"><span data-stu-id="c2caf-154">For example, the "Create web app" scenario might have a `-Git` or `-AddRemote` switch that would automatically add an "azure" remote to an existing git repository.</span></span>

- <span data-ttu-id="c2caf-155">Beállítható alapértelmezett értékek – A felhasználóknak képesnek kell lenniük arra, hogy alaphelyzetbe állítsanak bizonyos mindenütt jelenlevő paramétert (például `-ResourceGroupName` és `-Location`).</span><span class="sxs-lookup"><span data-stu-id="c2caf-155">Settable Defaults - Users should have the ability to default certain ubiquitous parameters like `-ResourceGroupName` and `-Location`.</span></span>

- <span data-ttu-id="c2caf-156">Alapértelmezett méretek – Az erőforrások „méretei” megtéveszthetik a felhasználókat, mert sok erőforrás-szolgáltató különböző neveket használ (például „\_DS1\_v2 szabvány” vagy „S1”).</span><span class="sxs-lookup"><span data-stu-id="c2caf-156">Size Defaults - Resource "sizes" can be confusing to users since many Resource Providers use different names (for example, "Standard\_DS1\_v2" or "S1").</span></span> <span data-ttu-id="c2caf-157">A legtöbb felhasználót azonban jobban érdeklik a költségek.</span><span class="sxs-lookup"><span data-stu-id="c2caf-157">However, most users care more about cost.</span></span> <span data-ttu-id="c2caf-158">Ezért logikus „univerzális” méreteket meghatározni egy díjszabási ütemezés alapján.</span><span class="sxs-lookup"><span data-stu-id="c2caf-158">Therefore, it makes sense to define "universal" sizes based on a pricing schedule.</span></span> <span data-ttu-id="c2caf-159">A felhasználók adott méretet választhatnak vagy hagyhatják, hogy az Azure PowerShell kiválassza a _legjobb lehetőséget_ az erőforrás és a költségvetés alapján.</span><span class="sxs-lookup"><span data-stu-id="c2caf-159">Users can choose a specific size or let Azure PowerShell choose the _best option_ based on the resource the budget.</span></span>

- <span data-ttu-id="c2caf-160">Kimeneti formátum – Az Azure PowerShell jelenleg `PSObject` elemeket ad vissza, és kevés konzolkimenet van.</span><span class="sxs-lookup"><span data-stu-id="c2caf-160">Output Format - Azure PowerShell currently returns `PSObject`s and there is little console output.</span></span> <span data-ttu-id="c2caf-161">Lehetséges, hogy az Azure PowerShellnek információt kell megjelenítenie a felhasználónak a használt „intelligens alapértékekről”.</span><span class="sxs-lookup"><span data-stu-id="c2caf-161">Azure PowerShell may need to display some information to the user regarding the "smart defaults" used.</span></span>

## <a name="try-using-the-experiments"></a><span data-ttu-id="c2caf-162">A kísérletek kipróbálása</span><span class="sxs-lookup"><span data-stu-id="c2caf-162">Try using the experiments</span></span>

### <a name="install"></a><span data-ttu-id="c2caf-163">Telepítés</span><span class="sxs-lookup"><span data-stu-id="c2caf-163">Install</span></span>

```powershell
Install-Module AzureRM.Compute.Experiments
```

### <a name="create-a-vm"></a><span data-ttu-id="c2caf-164">Virtuális gép létrehozása</span><span class="sxs-lookup"><span data-stu-id="c2caf-164">Create a VM</span></span>

```powershell
$job = New-AzVm -Name MyVm -AsJob
Receive-Job $job
```

### <a name="send-us-feedback"></a><span data-ttu-id="c2caf-165">Visszajelzés küldése</span><span class="sxs-lookup"><span data-stu-id="c2caf-165">Send Us Feedback</span></span>

```powershell
Send-Feedback
```

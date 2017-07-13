---
title: "<span data-ttu-id=\"229b4-101\">Az Azure PowerShell használatának első lépései | Microsoft Docs</span><span class=\"sxs-lookup\"><span data-stu-id=\"229b4-101\">Get started with Azure PowerShell | Microsoft Docs</span></span>"
description: 
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: get-started-article
ms.date: 03/30/2017
ms.openlocfilehash: 4bfa14f4f139fa8c35d4bb51ae81baea819188ce
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2017
---
# <span data-ttu-id="229b4-102">Ismerkedés az Azure PowerShell-lel</span><span class="sxs-lookup"><span data-stu-id="229b4-102">Getting started with Azure PowerShell</span></span>
<a id="getting-started-with-azure-powershell" class="xliff"></a>

<span data-ttu-id="229b4-103">Az Azure PowerShell az Azure-erőforrások parancssori kezelésére és adminisztrálására, valamint az Azure Resource Manageren futtatható automatizálási szkriptek létrehozására készült.</span><span class="sxs-lookup"><span data-stu-id="229b4-103">Azure PowerShell is designed for managing and administering Azure resources from the command line, and for building automation scripts that work against the Azure Resource Manager.</span></span> <span data-ttu-id="229b4-104">A cikk segítséget nyújt a használatának megkezdésében, és ismerteti az alapvető fogalmakat.</span><span class="sxs-lookup"><span data-stu-id="229b4-104">This article helps get you started using it, and teaches you the core concepts behind it.</span></span>


## <span data-ttu-id="229b4-105">Az Azure PowerShell telepítése</span><span class="sxs-lookup"><span data-stu-id="229b4-105">Install Azure PowerShell</span></span>
<a id="install-azure-powershell" class="xliff"></a>
<span data-ttu-id="229b4-106">Első lépésként győződjön meg róla, hogy az Azure PowerShell legújabb verziója van telepítve.</span><span class="sxs-lookup"><span data-stu-id="229b4-106">The first step is to make sure you have the latest version of the Azure PowerShell installed.</span></span>  <span data-ttu-id="229b4-107">A legújabb verzió a 4.1.0-s.</span><span class="sxs-lookup"><span data-stu-id="229b4-107">The latest version is 4.1.0.</span></span>

1. <span data-ttu-id="229b4-108">[Telepítse az Azure PowerShellt](install-azurerm-ps.md).</span><span class="sxs-lookup"><span data-stu-id="229b4-108">[Install Azure PowerShell](install-azurerm-ps.md).</span></span>

2. <span data-ttu-id="229b4-109">A telepítés sikerességének ellenőrzéséhez futtassa a `Get-Module AzureRM` parancsot a parancssorról.</span><span class="sxs-lookup"><span data-stu-id="229b4-109">To verify the installation was successful, run `Get-Module AzureRM` from your command line.</span></span>


## <span data-ttu-id="229b4-110">Jelentkezzen be az Azure-ba</span><span class="sxs-lookup"><span data-stu-id="229b4-110">Log in to Azure</span></span>
<a id="log-in-to-azure" class="xliff"></a>

<span data-ttu-id="229b4-111">Interaktív bejelentkezés:</span><span class="sxs-lookup"><span data-stu-id="229b4-111">Sign on interactively:</span></span>

1. <span data-ttu-id="229b4-112">Gépelje be: `Login-AzureRmAccount`.</span><span class="sxs-lookup"><span data-stu-id="229b4-112">Type `Login-AzureRmAccount`.</span></span>  <span data-ttu-id="229b4-113">Egy párbeszédpanel jelenik meg, amelyen meg kell adnia Azure-beli hitelesítő adatait.</span><span class="sxs-lookup"><span data-stu-id="229b4-113">You will get dialog box asking for your Azure credentials.</span></span> <span data-ttu-id="229b4-114">Az '-EnvironmentName' kapcsoló lehetővé teszi a bejelentkezést az Azure China vagy az Azure Germany szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="229b4-114">Option '-EnvironmentName' can let you login in Azure China or Azure Germany.</span></span>
   <span data-ttu-id="229b4-115">például: Login-AzureRmAccount -EnvironmentName AzureChinaCloud</span><span class="sxs-lookup"><span data-stu-id="229b4-115">e.g. Login-AzureRmAccount -EnvironmentName AzureChinaCloud</span></span>

2. <span data-ttu-id="229b4-116">Írja be a fiókjához tartozó e-mail-címet és jelszót.</span><span class="sxs-lookup"><span data-stu-id="229b4-116">Type the email address and password associated with your account.</span></span> <span data-ttu-id="229b4-117">Az Azure hitelesíti és menti a hitelesítő adatokat, majd bezárja az ablakot.</span><span class="sxs-lookup"><span data-stu-id="229b4-117">Azure authenticates and saves the credential information, and then closes the window.</span></span>

<span data-ttu-id="229b4-118">Miután bejelentkezett egy Azure-fiókba, az Azure PowerShell parancsmagjaival elérheti és kezelheti az előfizetésben lévő erőforrásokat.</span><span class="sxs-lookup"><span data-stu-id="229b4-118">Once you have signed in to an Azure account, you can use the Azure PowerShell cmdlets to access and manager the resources in your subscription.</span></span>

## <span data-ttu-id="229b4-119">Hozzon létre egy erőforráscsoportot</span><span class="sxs-lookup"><span data-stu-id="229b4-119">Create a resource group</span></span>
<a id="create-a-resource-group" class="xliff"></a>

<span data-ttu-id="229b4-120">Most, hogy mindent beállítottunk, hozzunk létre erőforrásokat az Azure-ban az Azure PowerShell használatával.</span><span class="sxs-lookup"><span data-stu-id="229b4-120">Now that we've got everything set up, let's use Azure PowerShell to create resources within Azure.</span></span>

<span data-ttu-id="229b4-121">Először is hozzon létre egy erőforráscsoportot.</span><span class="sxs-lookup"><span data-stu-id="229b4-121">First, create a Resource Group.</span></span> <span data-ttu-id="229b4-122">Az Azure erőforráscsoportjaiban együtt kezelhet több olyan erőforrást, amelyeket logikailag egy csoportba kíván foglalni.</span><span class="sxs-lookup"><span data-stu-id="229b4-122">Resource Groups in Azure provide a way to manage multiple resources that you want to logically group together.</span></span> <span data-ttu-id="229b4-123">Például létrehozhat egy erőforráscsoportot egy alkalmazáshoz vagy projekthez, majd hozzáadhat egy virtuális gépet, egy adatbázist és egy CDN-szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="229b4-123">For example, you might create a Resource Group for an application or project and add a virtual machine, a database and a CDN service within it.</span></span>

<span data-ttu-id="229b4-124">Hozzunk létre egy erőforráscsoportot „MyResourceGroup” néven az Azure westeurope (Nyugat--Európa) régiójában.</span><span class="sxs-lookup"><span data-stu-id="229b4-124">Let's create a resource group named "MyResourceGroup" in the westeurope region of Azure.</span></span> <span data-ttu-id="229b4-125">Ehhez írja be a következő parancsot:</span><span class="sxs-lookup"><span data-stu-id="229b4-125">To do so type the following command:</span></span>

```powershell
New-AzureRmResourceGroup -Name 'myResourceGroup' -Location 'westeurope'
```

```
ResourceGroupName : myResourceGroup
Location          : westeurope
ProvisioningState : Succeeded
Tags              :
ResourceId        : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/myResourceGroup
```

## <span data-ttu-id="229b4-126">Windows rendszerű virtuális gép létrehozása</span><span class="sxs-lookup"><span data-stu-id="229b4-126">Create a Windows Virtual Machine</span></span>
<a id="create-a-windows-virtual-machine" class="xliff"></a>

<span data-ttu-id="229b4-127">Most, hogy létrehoztuk az erőforráscsoportot, hozzunk létre benne egy windowsos virtuális gépet.</span><span class="sxs-lookup"><span data-stu-id="229b4-127">Now that we have our resource group, let's create a Windows VM within it.</span></span> <span data-ttu-id="229b4-128">Az új virtuális gép létrehozásához előbb létre kell hoznunk a többi szükséges erőforrást, és egy konfigurációt kell hozzájuk rendelnünk.</span><span class="sxs-lookup"><span data-stu-id="229b4-128">To create a new VM we must first create the other required resources and assign them to a configuration.</span></span> <span data-ttu-id="229b4-129">Ezután ezzel a konfigurációval létrehozhatjuk a virtuális gépet.</span><span class="sxs-lookup"><span data-stu-id="229b4-129">Then we can use that configuration to create the VM.</span></span>

### <span data-ttu-id="229b4-130">A szükséges hálózati erőforrások létrehozása</span><span class="sxs-lookup"><span data-stu-id="229b4-130">Create the required network resources</span></span>
<a id="create-the-required-network-resources" class="xliff"></a>

<span data-ttu-id="229b4-131">Először létre kell hoznunk egy alhálózati konfigurációt a virtuális hálózat létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="229b4-131">First we need to create a subnet configuration to be used with the virtual network creation process.</span></span> <span data-ttu-id="229b4-132">Létrehozunk egy nyilvános IP-címet is, hogy csatlakozhassunk a virtuális géphez.</span><span class="sxs-lookup"><span data-stu-id="229b4-132">We also create a public IP address so that we can connect to this VM.</span></span> <span data-ttu-id="229b4-133">Létrehozunk egy hálózati biztonsági csoportot, hogy biztonságossá tehessük a nyilvános cím elérését.</span><span class="sxs-lookup"><span data-stu-id="229b4-133">We create a network security group to secure access to the public address.</span></span> <span data-ttu-id="229b4-134">Végül létrehozzuk a virtuális NIC-t az összes előbbi erőforrás használatával.</span><span class="sxs-lookup"><span data-stu-id="229b4-134">Finally we create the virtual NIC using all of the previous resources.</span></span>

```powershell
# Variables for common values
$resourceGroup = "myResourceGroup"
$location = "westeurope"
$vmName = "myWindowsVM"

# Create a subnet configuration
$subnetConfig = New-AzureRmVirtualNetworkSubnetConfig -Name mySubnet1 -AddressPrefix 192.168.1.0/24

# Create a virtual network
$vnet = New-AzureRmVirtualNetwork -ResourceGroupName $resourceGroup -Location $location `
  -Name MYvNET1 -AddressPrefix 192.168.0.0/16 -Subnet $subnetConfig

# Create a public IP address and specify a DNS name
$publicIp = New-AzureRmPublicIpAddress -ResourceGroupName $resourceGroup -Location $location `
  -Name "mypublicdns$(Get-Random)" -AllocationMethod Static -IdleTimeoutInMinutes 4
$publicIp | Select-Object Name,IpAddress

# Create an inbound network security group rule for port 3389
$nsgRuleRDP = New-AzureRmNetworkSecurityRuleConfig -Name myNetworkSecurityGroupRuleRDP  -Protocol Tcp `
  -Direction Inbound -Priority 1000 -SourceAddressPrefix * -SourcePortRange * -DestinationAddressPrefix * `
  -DestinationPortRange 3389 -Access Allow

# Create a network security group
$nsg = New-AzureRmNetworkSecurityGroup -ResourceGroupName $resourceGroup -Location $location `
  -Name myNetworkSecurityGroup1 -SecurityRules $nsgRuleRDP

# Create a virtual network card and associate with public IP address and NSG
$nic = New-AzureRmNetworkInterface -Name myNic1 -ResourceGroupName $resourceGroup -Location $location `
  -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $publicIp.Id -NetworkSecurityGroupId $nsg.Id
```

### <span data-ttu-id="229b4-135">A virtuális gép létrehozása</span><span class="sxs-lookup"><span data-stu-id="229b4-135">Create the virtual machine</span></span>
<a id="create-the-virtual-machine" class="xliff"></a>

<span data-ttu-id="229b4-136">Először is szükségünk lesz az operációs rendszerhez tartozó hitelesítő adatok egy készletére.</span><span class="sxs-lookup"><span data-stu-id="229b4-136">First we need a set of credentials for the OS.</span></span>

```powershell
# Create user object
$cred = Get-Credential -Message "Enter a username and password for the virtual machine."
```

<span data-ttu-id="229b4-137">Most, hogy rendelkezünk a szükséges erőforrásokkal, létrehozhatjuk a virtuális gépet.</span><span class="sxs-lookup"><span data-stu-id="229b4-137">Now that we have the required resources we can create the VM.</span></span> <span data-ttu-id="229b4-138">Ehhez a lépéshez létrehozunk egy VM-konfigurációs objektumot, majd ezzel a konfigurációval létrehozzuk a virtuális gépet.</span><span class="sxs-lookup"><span data-stu-id="229b4-138">For this step, we create a VM configuration object, then we use the configuration to create the VM.</span></span>

```powershell
# Create a virtual machine configuration
$vmConfig = New-AzureRmVMConfig -VMName $vmName -VMSize Standard_D1 |
  Set-AzureRmVMOperatingSystem -Windows -ComputerName $vmName -Credential $cred |
  Set-AzureRmVMSourceImage -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version latest |
  Add-AzureRmVMNetworkInterface -Id $nic.Id

# Create a virtual machine
New-AzureRmVM -ResourceGroupName $resourceGroup -Location $location -VM $vmConfig
```

<span data-ttu-id="229b4-139">A `New-AzureRmVM` parancs kimeneti eredményei akkor érhetők el, amikor a virtuális gép létrejött és használatra kész.</span><span class="sxs-lookup"><span data-stu-id="229b4-139">The `New-AzureRmVM` command outputs results once the VM has been fully created and is ready to be used.</span></span>

```
RequestId IsSuccessStatusCode StatusCode ReasonPhrase
--------- ------------------- ---------- ------------
                         True         OK OK
```

<span data-ttu-id="229b4-140">Most jelentkezzen be az újonnan létrehozott Windows Server-alapú virtuális gépre a Távoli asztal szolgáltatással és a virtuális gép nyilvános IP-címével.</span><span class="sxs-lookup"><span data-stu-id="229b4-140">Now log on to your newly created Windows Server VM using Remote Desktop and the public IP address of the VM.</span></span> <span data-ttu-id="229b4-141">A következő parancs az előző szkriptben létrehozott nyilvános IP-címet jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="229b4-141">The following command displays the public IP address created in the previous script.</span></span>

```powershell
$publicIp | Select-Object Name,IpAddress
```

```
Name                  IpAddress
----                  ---------
mypublicdns1400512543 xx.xx.xx.xx
```

<span data-ttu-id="229b4-142">Windows-alapú rendszer használata esetén ezt a parancssorból az mstsc parancs használatával teheti meg:</span><span class="sxs-lookup"><span data-stu-id="229b4-142">If you are on a Windows-based system, you can do this from the command line using the mstsc command:</span></span>

```
mstsc /v:xx.xxx.xx.xxx
```

<span data-ttu-id="229b4-143">A bejelentkezéshez ugyanazt a felhasználónév–jelszó kombinációt adja meg, amelyet a virtuális gép létrehozása során használt.</span><span class="sxs-lookup"><span data-stu-id="229b4-143">Supply the same username/password combination you used when creating the VM to log in.</span></span>


## <span data-ttu-id="229b4-144">Linux rendszerű virtuális gép létrehozása</span><span class="sxs-lookup"><span data-stu-id="229b4-144">Create a Linux Virtual Machine</span></span>
<a id="create-a-linux-virtual-machine" class="xliff"></a>

<span data-ttu-id="229b4-145">Az új linuxos virtuális gép létrehozásához előbb létre kell hoznunk a többi szükséges erőforrást, és egy konfigurációt kell hozzájuk rendelnünk.</span><span class="sxs-lookup"><span data-stu-id="229b4-145">To create a new Linux VM we must first create the other required resources and assign them to a configuration.</span></span> <span data-ttu-id="229b4-146">Ezután ezzel a konfigurációval létrehozhatjuk a virtuális gépet.</span><span class="sxs-lookup"><span data-stu-id="229b4-146">Then we can use that configuration to create the VM.</span></span> <span data-ttu-id="229b4-147">Mindez feltételezi, hogy már létrehozta az erőforráscsoportot az előzőekben ismertetettek szerint.</span><span class="sxs-lookup"><span data-stu-id="229b4-147">This assumes that you have already created the resource group as previously shown.</span></span> <span data-ttu-id="229b4-148">Emellett szüksége lesz egy `id_rsa.pub` nevű nyilvános SSH-kulcsra a felhasználói profilja .ssh könyvtárában.</span><span class="sxs-lookup"><span data-stu-id="229b4-148">Also, you will need to have an SSH public key named `id_rsa.pub` in the .ssh directory of your user profile.</span></span>

### <span data-ttu-id="229b4-149">A szükséges hálózati erőforrások létrehozása</span><span class="sxs-lookup"><span data-stu-id="229b4-149">Create the required network resources</span></span>
<a id="create-the-required-network-resources" class="xliff"></a>

<span data-ttu-id="229b4-150">Először létre kell hoznunk egy alhálózati konfigurációt a virtuális hálózat létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="229b4-150">First we need to create a subnet configuration to be used with the virtual network creation process.</span></span> <span data-ttu-id="229b4-151">Létrehozunk egy nyilvános IP-címet is, hogy csatlakozhassunk a virtuális géphez.</span><span class="sxs-lookup"><span data-stu-id="229b4-151">We also create a public IP address so that we can connect to this VM.</span></span> <span data-ttu-id="229b4-152">Létrehozunk egy hálózati biztonsági csoportot, hogy biztonságossá tehessük a nyilvános cím elérését.</span><span class="sxs-lookup"><span data-stu-id="229b4-152">We create a network security group to secure access to the public address.</span></span> <span data-ttu-id="229b4-153">Végül létrehozzuk a virtuális NIC-t az összes előbbi erőforrás használatával.</span><span class="sxs-lookup"><span data-stu-id="229b4-153">Finally we create the virtual NIC using all of the previous resources.</span></span>

```powershell
# Variables for common values
$resourceGroup = "myResourceGroup"
$location = "westeurope"
$vmName = "myLinuxVM"

# Definer user name and blank password
$securePassword = ConvertTo-SecureString ' ' -AsPlainText -Force
$cred = New-Object System.Management.Automation.PSCredential ("azureuser", $securePassword)

# Create a subnet configuration
$subnetConfig = New-AzureRmVirtualNetworkSubnetConfig -Name mySubnet2 -AddressPrefix 192.168.2.0/24

# Create a virtual network
$vnet = New-AzureRmVirtualNetwork -ResourceGroupName $resourceGroup -Location $location `
  -Name MYvNET2 -AddressPrefix 192.168.0.0/16 -Subnet $subnetConfig

# Create a public IP address and specify a DNS name
$publicIp = New-AzureRmPublicIpAddress -ResourceGroupName $resourceGroup -Location $location `
  -Name "mypublicdns$(Get-Random)" -AllocationMethod Static -IdleTimeoutInMinutes 4
$publicIp | Select-Object Name,IpAddress

# Create an inbound network security group rule for port 22
$nsgRuleSSH = New-AzureRmNetworkSecurityRuleConfig -Name myNetworkSecurityGroupRuleSSH  -Protocol Tcp `
  -Direction Inbound -Priority 1000 -SourceAddressPrefix * -SourcePortRange * -DestinationAddressPrefix * `
  -DestinationPortRange 22 -Access Allow

# Create a network security group
$nsg = New-AzureRmNetworkSecurityGroup -ResourceGroupName $resourceGroup -Location $location `
  -Name myNetworkSecurityGroup2 -SecurityRules $nsgRuleSSH

# Create a virtual network card and associate with public IP address and NSG
$nic = New-AzureRmNetworkInterface -Name myNic2 -ResourceGroupName $resourceGroup -Location $location `
  -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $publicIp.Id -NetworkSecurityGroupId $nsg.Id
```

### <span data-ttu-id="229b4-154">A virtuális gép létrehozása</span><span class="sxs-lookup"><span data-stu-id="229b4-154">Create the virtual machine</span></span>
<a id="create-the-virtual-machine" class="xliff"></a>

<span data-ttu-id="229b4-155">Most, hogy rendelkezünk a szükséges erőforrásokkal, létrehozhatjuk a virtuális gépet.</span><span class="sxs-lookup"><span data-stu-id="229b4-155">Now that we have the required resources we can create the VM.</span></span> <span data-ttu-id="229b4-156">Ehhez a lépéshez létrehozunk egy VM-konfigurációs objektumot, majd ezzel a konfigurációval létrehozzuk a virtuális gépet.</span><span class="sxs-lookup"><span data-stu-id="229b4-156">For this step, we create a VM configuration object, then we use the configuration to create the VM.</span></span>

```powershell
# Create a virtual machine configuration
$vmConfig = New-AzureRmVMConfig -VMName $vmName -VMSize Standard_D1 |
  Set-AzureRmVMOperatingSystem -Linux -ComputerName $vmName -Credential $cred -DisablePasswordAuthentication |
  Set-AzureRmVMSourceImage -PublisherName Canonical -Offer UbuntuServer -Skus 14.04.2-LTS -Version latest |
  Add-AzureRmVMNetworkInterface -Id $nic.Id

# Configure SSH Keys
$sshPublicKey = Get-Content "$env:USERPROFILE\.ssh\id_rsa.pub"
Add-AzureRmVMSshPublicKey -VM $vmConfig -KeyData $sshPublicKey -Path "/home/azureuser/.ssh/authorized_keys"

# Create a virtual machine
New-AzureRmVM -ResourceGroupName $resourceGroup -Location $location -VM $vmConfig
```

<span data-ttu-id="229b4-157">Most, hogy a virtuális gép létrejött, bejelentkezhet az új Linux rendszerű virtuális gépre SSH használatával a létrehozott virtuális gép nyilvános IP-címével:</span><span class="sxs-lookup"><span data-stu-id="229b4-157">Now that the VM has been created, you can log on to your new Linux VM using SSH with the public IP address of the VM you created:</span></span>

```bash
ssh xx.xxx.xxx.xxx
```

```
Welcome to Ubuntu 14.04.4 LTS (GNU/Linux 3.19.0-65-generic x86_64)

 * Documentation:  https://help.ubuntu.com/

  System information as of Sun Feb 19 00:32:28 UTC 2017

  System load: 0.31              Memory usage: 3%   Processes:       89
  Usage of /:  39.6% of 1.94GB   Swap usage:   0%   Users logged in: 0

  Graph this data and manage this system at:
    https://landscape.canonical.com/

  Get cloud support with Ubuntu Advantage Cloud Guest:
    http://www.ubuntu.com/business/services/cloud

0 packages can be updated.
0 updates are security updates.



The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

my-login@MyLinuxVM:~$
```

## <span data-ttu-id="229b4-158">Egyéb erőforrások létrehozása az Azure-ban</span><span class="sxs-lookup"><span data-stu-id="229b4-158">Creating other resources in Azure</span></span>
<a id="creating-other-resources-in-azure" class="xliff"></a>

<span data-ttu-id="229b4-159">Bemutattuk, hogyan hozhat létre erőforráscsoportot, valamint Linux és Windows Server rendszerű virtuális gépet.</span><span class="sxs-lookup"><span data-stu-id="229b4-159">We've now walked through how to create a Resource Group, a Linux VM, and a Windows Server VM.</span></span> <span data-ttu-id="229b4-160">Számos más típusú Azure-erőforrást is létrehozhat.</span><span class="sxs-lookup"><span data-stu-id="229b4-160">You can create many other types of Azure resources as well.</span></span>

<span data-ttu-id="229b4-161">Például a következő parancs használatával létrehozhat egy Azure-beli hálózati terheléselosztót, amelyet aztán társíthat az újonnan létrehozott virtuális gépekkel:</span><span class="sxs-lookup"><span data-stu-id="229b4-161">For example, to create an Azure Network Load Balancer that we could then associate with our newly created VMs, we can use the following create command:</span></span>

```powershell
New-AzureRmLoadBalancer -Name MyLoadBalancer -ResourceGroupName myResourceGroup -Location westeurope
```

<span data-ttu-id="229b4-162">Vagy létrehozhat egy új privát virtuális hálózatot (vagy az Azure-ban gyakran használt nevén „VNetet”) az infrastruktúránkhoz a következő paranccsal:</span><span class="sxs-lookup"><span data-stu-id="229b4-162">We could also create a new private Virtual Network (commonly referred to as a "VNet" within Azure) for our infrastructure using the following command:</span></span>

```powershell
$subnetConfig = New-AzureRmVirtualNetworkSubnetConfig -Name mySubnet2 -AddressPrefix 10.0.0.0/16
$vnet = New-AzureRmVirtualNetwork -ResourceGroupName myResourceGroup -Location westeurope `
  -Name MYvNET3 -AddressPrefix 10.0.0.0/16 -Subnet $subnetConfig
```

<span data-ttu-id="229b4-163">Az Azure és az Azure PowerShell attól igazán sokoldalúak, hogy nemcsak a felhőalapú infrastruktúrához használhatók, hanem felügyelt platformszolgáltatások kialakításához is.</span><span class="sxs-lookup"><span data-stu-id="229b4-163">What makes Azure and the Azure PowerShell powerful is that we can use it not just to get cloud-based infrastructure but also to create managed platform services.</span></span> <span data-ttu-id="229b4-164">A felügyelt platformszolgáltatásokat az infrastruktúrával kombinálva még nagyobb teljesítményű megoldások építhetők ki.</span><span class="sxs-lookup"><span data-stu-id="229b4-164">The managed platform services can also be combined with infrastructure to build even more powerful solutions.</span></span>

<span data-ttu-id="229b4-165">Például az Azure PowerShell használatával létrehozhat egy Azure AppService-t.</span><span class="sxs-lookup"><span data-stu-id="229b4-165">For example, you can use the Azure PowerShell to create an Azure AppService.</span></span> <span data-ttu-id="229b4-166">Az Azure AppService egy felügyelt platformszolgáltatás, amely nagyszerű megoldás a webappok üzemeltetésére anélkül, hogy aggódnia kellene az infrastruktúra miatt.</span><span class="sxs-lookup"><span data-stu-id="229b4-166">Azure AppService is a managed platform service that provides a great way to host web apps without having to worry about infrastructure.</span></span> <span data-ttu-id="229b4-167">Az Azure AppService létrehozása után két új Azure webappot hozhat létre az AppService-ben a következő parancsokkal:</span><span class="sxs-lookup"><span data-stu-id="229b4-167">After creating the Azure AppService, you can create two new Azure Web Apps within the AppService using the following commands:</span></span>

```powershell
# Create an Azure AppService that we can host any number of web apps within
New-AzureRmAppServicePlan -Name MyAppServicePlan -Tier Basic -NumberofWorkers 2 -WorkerSize Small -ResourceGroupName myResourceGroup -Location westeurope

# Create Two Web Apps within the AppService (note: name param must be a unique DNS entry)
New-AzureRmWebApp -Name MyWebApp43432 -AppServicePlan MyAppServicePlan -ResourceGroupName myResourceGroup -Location westeurope
New-AzureRmWebApp -Name MyWebApp43433 -AppServicePlan MyAppServicePlan -ResourceGroupName myResourceGroup -Location westeurope
```

## <span data-ttu-id="229b4-168">Üzembe helyezett erőforrások listázása</span><span class="sxs-lookup"><span data-stu-id="229b4-168">Listing deployed resources</span></span>
<a id="listing-deployed-resources" class="xliff"></a>

<span data-ttu-id="229b4-169">A `Get-AzureRmResource` parancsmag használatával listázhatja az Azure-ban futó erőforrásokat.</span><span class="sxs-lookup"><span data-stu-id="229b4-169">You can use the `Get-AzureRmResource` cmdlet to list the resources running in Azure.</span></span> <span data-ttu-id="229b4-170">Az alábbi példa az új erőforráscsoportban létrehozott erőforrásokat mutatja be.</span><span class="sxs-lookup"><span data-stu-id="229b4-170">The following example shows the resources we just created in the new resource group.</span></span>

```powershell
Get-AzureRmResource |
  Where-Object ResourceGroupName -eq myResourceGroup |
    Select-Object Name,Location,ResourceType
```

```
Name                                                  Location   ResourceType
----                                                  --------   ------------
myLinuxVM_OsDisk_1_36ca038791f642ba91270879088c249a   westeurope Microsoft.Compute/disks
myWindowsVM_OsDisk_1_f627e6e2bb454c72897d72e9632adf9a westeurope Microsoft.Compute/disks
myLinuxVM                                             westeurope Microsoft.Compute/virtualMachines
myWindowsVM                                           westeurope Microsoft.Compute/virtualMachines
myWindowsVM/BGInfo                                    westeurope Microsoft.Compute/virtualMachines/extensions
myNic1                                                westeurope Microsoft.Network/networkInterfaces
myNic2                                                westeurope Microsoft.Network/networkInterfaces
myNetworkSecurityGroup1                               westeurope Microsoft.Network/networkSecurityGroups
myNetworkSecurityGroup2                               westeurope Microsoft.Network/networkSecurityGroups
mypublicdns245369171                                  westeurope Microsoft.Network/publicIPAddresses
mypublicdns779537141                                  westeurope Microsoft.Network/publicIPAddresses
MYvNET1                                               westeurope Microsoft.Network/virtualNetworks
MYvNET2                                               westeurope Microsoft.Network/virtualNetworks
micromyresomywi032907510                              westeurope Microsoft.Storage/storageAccounts
```

## <span data-ttu-id="229b4-171">Erőforrások törlése</span><span class="sxs-lookup"><span data-stu-id="229b4-171">Deleting resources</span></span>
<a id="deleting-resources" class="xliff"></a>

<span data-ttu-id="229b4-172">Az Azure-fiók tisztítása érdekében érdemes lehet törölnie a példában létrehozott erőforrásokat.</span><span class="sxs-lookup"><span data-stu-id="229b4-172">To clean up your Azure account, you want to remove the resources we created in this example.</span></span> <span data-ttu-id="229b4-173">A `Remove-AzureRm*` parancsmagokkal törölheti a már nem szükséges erőforrásokat.</span><span class="sxs-lookup"><span data-stu-id="229b4-173">You can use the `Remove-AzureRm*` cmdlets to delete the resources you no longer need.</span></span> <span data-ttu-id="229b4-174">A létrehozott Windows rendszerű virtuális gép eltávolításához futtassa az alábbi parancsot:</span><span class="sxs-lookup"><span data-stu-id="229b4-174">To remove the Windows VM we created, using the following command:</span></span>

```powershell
Remove-AzureRmVM -Name myWindowsVM -ResourceGroupName myResourceGroup
```

<span data-ttu-id="229b4-175">A rendszer rákérdez az erőforrás törlésének jóváhagyására.</span><span class="sxs-lookup"><span data-stu-id="229b4-175">You will be prompted to confirm that you want to remove the resource.</span></span>

```
Confirm
Are you sure you want to remove resource group 'myResourceGroup'
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

<span data-ttu-id="229b4-176">Egyszerre több erőforrást is törölhet.</span><span class="sxs-lookup"><span data-stu-id="229b4-176">You can also use the delete many resources at one time.</span></span> <span data-ttu-id="229b4-177">A következő parancs például törli a teljes „MyResourceGroup” erőforráscsoportot, amelyet ebben a bevezető oktatóanyagban az összes mintához használtunk.</span><span class="sxs-lookup"><span data-stu-id="229b4-177">For example, the following command deletes all the resource group "MyResourceGroup" that we've used for all the samples in this Get Started tutorial.</span></span> <span data-ttu-id="229b4-178">Törli az erőforráscsoportot, és minden benne lévő erőforrást is.</span><span class="sxs-lookup"><span data-stu-id="229b4-178">This removes the resource group and all of the resources in it.</span></span>

```powershell
Remove-AzureRmResourceGroup -Name myResourceGroup
```

```
Confirm
Are you sure you want to remove resource group 'myResourceGroup'
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

<span data-ttu-id="229b4-179">Ez több percig is eltarthat.</span><span class="sxs-lookup"><span data-stu-id="229b4-179">This can take several minutes to complete.</span></span>

## <span data-ttu-id="229b4-180">Minták letöltése</span><span class="sxs-lookup"><span data-stu-id="229b4-180">Get samples</span></span>
<a id="get-samples" class="xliff"></a>

<span data-ttu-id="229b4-181">Az Azure PowerShell használatával kapcsolatos további tudnivalókért tekintse át a [Linux rendszerű virtuális gépek](/azure/virtual-machines/virtual-machines-linux-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), a [Windows rendszerű virtuális gépek](/azure/virtual-machines/virtual-machines-windows-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), a [Web Apps-alkalmazások](/azure/app-service-web/app-service-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json) és az [SQL Database-adatbázisok](/azure/sql-database/sql-database-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json) leggyakoribb szkriptjeit.</span><span class="sxs-lookup"><span data-stu-id="229b4-181">To learn more about ways to use the Azure PowerShell, check out our most common scripts for [Linux VMs](/azure/virtual-machines/virtual-machines-linux-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), [Windows VMs](/azure/virtual-machines/virtual-machines-windows-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), [Web Apps](/azure/app-service-web/app-service-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), and [SQL Databases](/azure/sql-database/sql-database-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json).</span></span>

## <span data-ttu-id="229b4-182">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="229b4-182">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

* [<span data-ttu-id="229b4-183">Bejelentkezés az Azure PowerShell-lel</span><span class="sxs-lookup"><span data-stu-id="229b4-183">Login with Azure PowerShell</span></span>](authenticate-azureps.md)
* [<span data-ttu-id="229b4-184">Azure-előfizetések kezelése az Azure PowerShell-lel</span><span class="sxs-lookup"><span data-stu-id="229b4-184">Manage Azure subscriptions with Azure PowerShell</span></span>](manage-subscriptions-azureps.md)
* [<span data-ttu-id="229b4-185">Szolgáltatásnevek létrehozása az Azure PowerShell használatával</span><span class="sxs-lookup"><span data-stu-id="229b4-185">Create service principals in Azure using Azure PowerShell</span></span>](create-azure-service-principal-azureps.md)
* <span data-ttu-id="229b4-186">A régi kiadásokról való áttéréssel kapcsolatban olvassa át a kibocsátási megjegyzéseket: [https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes](https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes).</span><span class="sxs-lookup"><span data-stu-id="229b4-186">Read the Release notes about migrating from an older release: [https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes](https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes).</span></span>
* <span data-ttu-id="229b4-187">Segítség kérése a közösségtől:</span><span class="sxs-lookup"><span data-stu-id="229b4-187">Get help from the community:</span></span>
  + [<span data-ttu-id="229b4-188">Azure-fórum az MSDN-en</span><span class="sxs-lookup"><span data-stu-id="229b4-188">Azure forum on MSDN</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=320212)
  + [<span data-ttu-id="229b4-189">stackoverflow</span><span class="sxs-lookup"><span data-stu-id="229b4-189">stackoverflow</span></span>](http://go.microsoft.com/fwlink/?LinkId=320213)

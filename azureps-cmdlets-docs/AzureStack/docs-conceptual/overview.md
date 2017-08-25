---
title: "Az Azure Stack PowerShell áttekintése | Microsoft Docs"
description: "Az Azure Stack PowerShell telepítésének és konfigurálásának áttekintése."
author: SnehaGunda
manager: Byronr
ms.product: azure-stack
ms.service: powershell
ms.devlang: powershell
ms.topic: reference
ms.author: sngun
ms.manager: byronr
ms.openlocfilehash: 2a03697e0f3e80d63c48f2dc5615f6c99b9ef716
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2017
---
# <a name="azure-stack-powershell"></a>Azure Stack PowerShell 

Az Azure Stack a következő két PowerShell-modult igényli:  

1. Az Azure Stack szolgáltatással kompatibilis **AzureRM**-modul, amely a **2017-03-09-profile** API-verzióprofil telepítésével érhető el. A profil használatával telepített parancsmagokat az Azure Stack-felhő rendszergazdái és bérlői egyaránt használhatják. A profilban elérhető PowerShell-parancsmagokkal kapcsolatos további információkért tekintse meg a PowerShell-referenciatartalom az [AzureRM-modul 1.2.9-es verziójára](https://docs.microsoft.com/en-us/powershell/azure/overview?view=azurermps-1.2.9) vonatkozó részét.  

2. Az **AzureStack**-modul **1.2.9-es** verziója. A modul használatával telepített parancsmagokat csak az Azure Stack-felhő rendszergazdái használhatják. A rendszergazdák a modul által biztosított PowerShell-parancsmagok segítségével olyan műveleteket hajthatnak végre, mint az ajánlatok, tervek, szolgáltatások, kvóták stb. kezelése. A modulban elérhető PowerShell-parancsmagokkal kapcsolatos további információkért tekintse meg az [AzureStack](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackadmin/?view=azurestackps-1.2.9#azurerm.azurestackadmin) és [AzureStackStorage](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackstorage/?view=azurestackps-1.2.9#azurerm.azurestackstorage) referenciatartalmakat.

## <a name="next-steps"></a>Következő lépések

* [A PowerShell telepítése az Azure Stack szolgáltatáshoz](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-install?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)
* [A PowerShell konfigurálása az Azure Stack szolgáltatással való használathoz](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-configure?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)



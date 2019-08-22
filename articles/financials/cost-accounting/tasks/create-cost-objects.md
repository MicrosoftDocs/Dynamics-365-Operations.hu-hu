---
title: Költségobjektumok létrehozása
description: Ez az eljárás bemutatja, hogyan lehet költségobjektumokat létrehozni a Dynamics 365 for Finance and Operations, Enterprise kiadás költséghely pénzügyi dimenziók importálásával a Költségkönyvelésbe az adatcsatlakozón keresztül.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMAXFinancialDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8f63827977f080aa78fb385c60f757ad6b710005
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841249"
---
# <a name="create-cost-objects"></a>Költségobjektumok létrehozása 

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan lehet költségobjektumokat létrehozni a Dynamics 365 for Finance and Operations, Enterprise kiadás költséghely pénzügyi dimenziók importálásával a Költségkönyvelésbe az adatcsatlakozón keresztül. Ez az eljárás az USMF bemutatócéget használja. Ezzel az eljárással a Költségkönyvelés funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.


## <a name="create-new-cost-objects"></a>Új költségobjektumok létrehozása
1. Ugrás a Költségkönyvelés > Dimenziók > Költségobjektum-dimenziók elemre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Név mezőbe.
4. A Dimenziótagok adatcsatlakozója mezőben adjon meg, vagy válasszon ki egy értéket.
5. A Leírás mezőben adjon meg egy értéket.
6. Kattintson a Mentés gombra.

## <a name="configure-the-data-connector"></a>Az adatcsatlakozó konfigurálása
1. Kattintson a Dimenziótag-szolgáltató konfigurálása lehetőségre.
    * Válassza ki a CostCenter lehetőséget a CostCenter dimenzió importálásához a Költségkönyvelésbe.  
2. A Dimenzió neve mezőben válassza ki a Költséghelyet.
3. Kattintson az OK gombra.

## <a name="import-cost-centers"></a>Költséghelyek importálása
1. Kattintson a Dimenziótagok importálása elemre.
2. Kattintson az OK gombra.

## <a name="view-the-imported-cost-centers"></a>Az importált költséghelyek megtekintése
1. Kattintson a Dimenziótagok megtekintése elemre.


---
title: Költségösszetevők létrehozása
description: A Költségkönyvelésben számos módon a hozhatók létre költségelemek.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMAXMainAccountDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7cceec1d52e1b5b2a05525c8d96f46dece17363b
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841297"
---
# <a name="create-cost-elements"></a>Költségösszetevők létrehozása 

[!include [task guide banner](../../includes/task-guide-banner.md)]

A Költségkönyvelésben számos módon a hozhatók létre költségelemek. Ez az eljárás bemutatja, hogyan lehet költségösszetevőket létrehozni a fő számlák importálásával az adatcsatlakozón keresztül. Ez az eljárás az USMF bemutatócéget használja. Ezzel az eljárással a Költségkönyvelés funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.


## <a name="create-new-cost-elements"></a>Új költségösszetevők létrehozása
1. Ugrás a Költségkönyvelés > Dimenziók > Költségösszetevő-dimenziók elemre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Név mezőbe.
4. A Dimenziótagok adatcsatlakozója mezőben adjon meg, vagy válasszon ki egy értéket.
5. A Leírás mezőben adjon meg egy értéket.
6. Kattintson a Mentés gombra.

## <a name="configure-the-data-connector"></a>Az adatcsatlakozó konfigurálása
1. Kattintson a Dimenziótag-szolgáltató konfigurálása lehetőségre.
2. A Számlatükör mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza ki a Megosztott lehetőséget a megosztott számlatükör használatához.  
3. Kattintson az Új lehetőségre.
4. A listában jelölje meg a kiválasztott sort.
    * A számlákra szűrőket alkalmazhat, hogy megfeleljenek a feltételeinek.  
5. A fő számlából mezőben adjon meg vagy válasszon ki egy értéket.
6. A fő számlához mezőben adjon meg vagy válasszon ki egy értéket.
7. Kattintson az OK gombra.

## <a name="import-main-accounts"></a>Fő számlák importálása
1. Kattintson a Dimenziótagok importálása elemre.
    * A fő számlákat a rendszer a Költségkönyvelésbe importálja és költségösszetevőként használja.  
2. Kattintson az OK gombra.

## <a name="view-the-imported-accounts-as-cost-elements"></a>Importált számlák megjelenítése költségösszetevőként
1. Kattintson a Dimenziótagok megtekintése elemre.
    * Az importált főkönyvi számlák megtekintése költségösszetevőként, amelyre a költségek könyvelhetők.  


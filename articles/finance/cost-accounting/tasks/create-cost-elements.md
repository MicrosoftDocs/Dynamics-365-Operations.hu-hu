---
title: Költségösszetevők létrehozása
description: A Költségkönyvelésben számos módon a hozhatók létre költségelemek.
author: kfend
ms.date: 08/29/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: CAMDimension, CAMAXMainAccountDimensionMemberProviderConfiguration, CAMDimensionMember
ms.openlocfilehash: 0254f486816e852bcda52f90fe4da65c413c7032
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779689"
---
# <a name="create-cost-elements"></a>Költségösszetevők létrehozása 

[!include [banner](../../includes/banner.md)]

A Költségkönyvelésben számos módon a hozhatók létre költségelemek. Ez az eljárás bemutatja, hogyan lehet költségösszetevőket létrehozni a fő számlák importálásával az adatcsatlakozón keresztül. Ez az eljárás az USMF bemutatócéget használja. Ezzel az eljárással a Költségkönyvelés funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.


## <a name="create-new-cost-elements"></a>Új költségösszetevők létrehozása
1. Ugrás a Költség **> dimenziók > dimenzióihoz**.
2. Kattintson az **Új** elemre.
3. Írjon be egy értéket a **Név** mezőbe.
4. A dimenziótagok **Adat csatlakoztató mezőjében** adjon meg vagy válasszon ki egy értéket.
5. Írjon egy értéket a **Leírás** mezőbe.
6. Kattintson a **Mentés** gombra.

## <a name="configure-the-data-connector"></a>Az adatcsatlakozó konfigurálása
1. Kattintson a Dimenziótag-szolgáltató **konfigurálása elemre**.
2. A Számlatükre **mezőben** adjon meg vagy válasszon ki egy értéket.
    * Válassza **a Megosztott** lehetőséget a megosztott számlatükre használatára.  
3. Kattintson az **Új** elemre.
4. A listában jelölje meg a kiválasztott sort.
    * A számlákra szűrőket alkalmazhat, hogy megfeleljenek a feltételeinek.  
5. A Fő számla **létrehozása mezőben** adjon meg vagy válasszon ki egy értéket.
6. A Cél főszámla **mezőben** adjon meg vagy válasszon ki egy értéket.
7. Kattintson az **OK** gombra.

## <a name="import-main-accounts"></a>Fő számlák importálása
1. Kattintson a Dimenziótagok **importálása elemre**.
    * A fő számlákat a rendszer a Költségkönyvelésbe importálja és költségösszetevőként használja.  
2. Kattintson az **OK** gombra.

## <a name="view-the-imported-accounts-as-cost-elements"></a>Importált számlák megjelenítése költségösszetevőként
1. Kattintson a Dimenziótagok **megtekintése elemre**.
    * Az importált főkönyvi számlák megtekintése költségösszetevőként, amelyre a költségek könyvelhetők.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

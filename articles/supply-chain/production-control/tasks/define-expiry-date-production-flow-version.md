---
title: Lejárati dátum megadása termék folyamatverziójához
description: Egy termelésifolyamat-verzió érvényességének és feldolgozásának befejezéséhez egy adott időpontban, vagy egy aktív verzió új verzióra cserélésének tervezéséhez, be kell állítani a verzió lejárati idejét.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3d942f54b2739f2ca3dcc3e8b8a497166a8edb42
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3212089"
---
# <a name="define-an-expiry-date-for-a-production-flow-version"></a>Lejárati dátum megadása termék folyamatverziójához

[!include [banner](../../includes/banner.md)]

Egy termelésifolyamat-verzió érvényességének és feldolgozásának befejezéséhez egy adott időpontban, vagy egy aktív verzió új verzióra cserélésének tervezéséhez, be kell állítani a verzió lejárati idejét. Nincs szükség a verzió inaktiválására.


## <a name="set-an-expiration-date-to-end-a-production-flow-version"></a>Állítson be egy lejárati dátumot a termelésifolyamat-verzió befejezéséhez
1. Ugrás a Gyártásvezérléshez > Beállítás > Lean típusú termelési folyamat > Termelési folyamatok lehetőségre.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válassza ki bármelyik termelési folyamatot, amelyiknek már van definiált verziója.  
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. Kattintson a Szerkesztés lehetőségre.
5. A listában jelölje meg a kiválasztott sort.
6. Az Lejárati dátum mezőben adjon meg egy dátumot és időpontot.
    * A lejárati dátumon nem indul el és nem lesz aktiválva új verzió. Emellett már nem lehet létrehozni vagy elindítani feladatokat a termelési folyamathoz. Az elindított feladatok a lejárati dátum után is befejezhetők.  


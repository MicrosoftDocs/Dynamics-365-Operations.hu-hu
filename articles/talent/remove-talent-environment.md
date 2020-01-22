---
title: Talent-környezetek eltávolítása
description: Ez a témakör végigvezeti Önt a teszt vagy termelési környezet eltávolításán a Microsoft Dynamics 365 Talent számára.
author: andreabichsel
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.openlocfilehash: e752d658388fc6cb6f4b84ac83cb12a71522199b
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898110"
---
# <a name="remove-talent-environments"></a>Talent-környezetek eltávolítása

Ez a témakör végigvezeti Önt a teszt vagy termelési környezet eltávolításán a Microsoft Dynamics 365 Talent számára.

## <a name="removing-a-test-drive-environment"></a>Tesztkörnyezet eltávolítása

A Talent tesztverziók esetében 60 napos lejárati szabályt alkalmazunk. A tesztkörnyezetek tulajdonosai azonban korábban is be tudják fejezni a próbaidőszakot a következő lépések végrehajtásával. 

1. A [Power Apps Adminisztrációs központ](https://admin.businessplatform.microsoft.com/) megnyitása
2. Válassza a **Környezetek** lehetőséget.
3. Válassza ki a tesztmeghajtó-környezetet, amelynek hasonló az elnevezési mintázata ehhez: TestDrive - alias@domain
4. Válassza **Törlés** lehetőséget, és hagyja jóvá a döntést. 

A meglévő tesztkörnyezetet el fogjuk távolítani. Az eltávolítása után regisztráljon egy új tesztkörnyezetre. 

## <a name="removing-a-production-environment"></a>Éles környezet eltávolítása

Ez a témakör feltételezi, hogy a Talent rendszert felhőalapú szolgáltatón (CSP) keresztül vagy vállalati architektúra (EA) megállapodás részeként vásárolta. 

Mivel egyetlen Talent környezet „van” egyetlen Power Apps környezeten belül, két beállítást kell figyelembe venni. Az első lehetőség a teljes Power Apps környezet eltávolításával jár; a második lehetőség csak a Talent eltávolítását foglalja magában. Az első lehetőséget akkor érdemes használni, amikor a Power Apps környezetet kifejezetten a Talent létesítése céljából hozta létre, és csak most kezdi a végrehajtást, vagy nincs semmilyen megállapított integráció. A másik lehetőség csak akkor megfelelő, amikor jól beállított Power Apps környezete van multimédiás adatokkal, amelyeket a rendszer felhasznál a Power Apps és a Power Automate esetében.

> [!Important]
> A Power Apps környezet eltávolítása előtt győződjön meg róla, nincs használatban gazdag adatintegrációkhoz a Talenten kívül. Vegye figyelembe azt is, hogy az alapértelmezett Power Apps környezeteket nem lehet eltávolítani. 

Ha el szeretné távolítani a teljes Power Apps környezetet, beleértve a Talent alkalmazást és a kapcsolódó alkalmazásokat és folyamatokat:

1. A [Power Apps Adminisztrációs központ](https://admin.businessplatform.microsoft.com/) megnyitása
2. Válassza a **Környezetek** lehetőséget.
3. Jelölje ki az eltávolítani kívánt környezetet.
4. Válassza **Törlés** lehetőséget, és hagyja jóvá a döntést. 
5. Várjon, amíg be nem fejeződik a törlés.
6. Jelentkezzen be az [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) portálra azzal a fiókkal, amelyet a Talentre való előfizetéshez használt. 
7. Válassza ki a Talent projektet, amely tartalmazza a környezetet. 
8. Az LCS-projektben válassza a **Talent alkalmazás kezelése** csempét. 
9. Válassza ki azt a példányt, amelyet el szeretne távolítani. 
10. Válassz a **Példány eltávolítása** lehetőséget, és hagyja jóvá a döntést.  

A Talent környezet eltávolításához a meglévő Power Apps környezetből, hajtsa végre az alábbi lépéseket. Ne feledje, hogy a támogatás szükséges bevonása és a Talent DevOps csapatával való kapcsolatfelvétel csak ideiglenes amíg ez a funkció nincs engedélyezve a közvetlenül az LCS-ben.

1. Forduljon a támogatáshoz eltávolítási igény kezdeményezésére.
2. A támogatási csapat eltávolítási kérelmet kezdeményez a Talent DevOps csoportnál. 
3. Folytassa, miután értesült, hogy a környezet eltávolításra került.
4.  Jelentkezzen be az LCS-be azzal a fiókkal, amelyet a Talentre való előfizetéshez használt. 
5. Válassza ki a Talent projektet, amely tartalmazza a környezetet. 
6. Az LCS-projektben válassza a **Talent alkalmazás kezelése** csempét. 
7. Válassza ki a példányt, amelyet el szeretné távolítani, amelynél fel kell tüntetni a telepítés állapotát **Nem sikerült** állapottal.
8. Válassz a **Példány eltávolítása** lehetőséget, és hagyja jóvá a döntést. 


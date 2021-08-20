---
title: Példány eltávolítása
description: Ez a cikk végigvezeti Önt a teszt- vagy éles környezet eltávolításán a Microsoft Dynamics 365 Human Resources esetében.
author: andreabichsel
ms.date: 08/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 978bbbe9ecd57c8a80cfc0c17f1a3e2d8422482fddc1c4f2ea0bc8ac91d6615c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740815"
---
# <a name="remove-an-instance"></a>Példány eltávolítása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a cikk végigvezeti Önt a teszt- vagy éles környezet eltávolításán a Microsoft Dynamics 365 Human Resources esetében.

## <a name="remove-a-test-drive-environment"></a>Tesztkörnyezet eltávolítása

A Human Resources tesztverziói esetében 60 napos lejárati szabályt alkalmazunk. A tesztkörnyezetek tulajdonosai azonban korábban is be tudják fejezni a próbaidőszakot a következő lépések végrehajtásával. 

1. A [Power Apps Adminisztrációs központ](https://admin.businessplatform.microsoft.com/) megnyitása
2. Válassza a **Környezetek** lehetőséget.
3. Válassza ki a tesztmeghajtó-környezetet, amelynek hasonló az elnevezési mintázata ehhez: TestDrive - alias@domain
4. Válassza **Törlés** lehetőséget, és hagyja jóvá a döntést. 

A meglévő tesztkörnyezetet el fogjuk távolítani. Az eltávolítása után regisztráljon egy új tesztkörnyezetre. 

## <a name="remove-a-production-environment"></a>Éles környezet eltávolítása

Ez a cikk feltételezi, hogy a Human Resources rendszert felhőalapú szolgáltatón (CSP) keresztül vagy vállalati architektúra (EA) megállapodás részeként vásárolta. 

Mivel egyetlen Human Resources-környezet van egyetlen Power Apps környezeten belül, két lehetőséget kell figyelembe venni. Az első lehetőség a teljes Power Apps környezet eltávolításával jár; a második lehetőség csak a Human Resources eltávolítását foglalja magában. Az első lehetőséget akkor érdemes használni, amikor a Power Apps környezetet kifejezetten a Human Resources létesítése céljából hozta létre, és csak most kezdi a végrehajtást, vagy nincs semmilyen megállapított integráció. A másik lehetőség csak akkor megfelelő, amikor jól beállított Power Apps környezete van multimédiás adatokkal, amelyeket a rendszer felhasznál a Power Apps és a Power Automate esetében.

> [!Important]
> A Power Apps környezet eltávolítása előtt győződjön meg róla, nincs használatban gazdag adatintegrációkhoz a Human Resources alkalmazáson kívül. Vegye figyelembe azt is, hogy az alapértelmezett Power Apps környezeteket nem lehet eltávolítani. 

Ha el szeretné távolítani a teljes Power Apps környezetet, beleértve a Human Resources alkalmazást és a társított alkalmazásokat és folyamatokat:

1. A [Power Apps Adminisztrációs központ](https://admin.businessplatform.microsoft.com/) megnyitása
2. Válassza a **Környezetek** lehetőséget.
3. Jelölje ki az eltávolítani kívánt környezetet.
4. Válassza **Törlés** lehetőséget, és hagyja jóvá a döntést. 
5. Várjon, amíg be nem fejeződik a törlés.
6. Jelentkezzen be a [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) portálra azzal a fiókkal, amelyet a Human Resources alkalmazásra való feliratkozáshoz használt. 
7. Válassza ki a Human Resources projektet, amely tartalmazza a környezetet. 
8. Az LCS-projektben válassza a **Human Resources alkalmazás kezelése** csempét. 
9. Válassza ki azt a példányt, amelyet el szeretne távolítani. 
10. Válassz a **Példány eltávolítása** lehetőséget, és hagyja jóvá a döntést.  

A Human Resources-környezet meglévő Power Apps környezetből való eltávolításához hajtsa végre az alábbi lépéseket. Ne feledje, hogy a támogatás szükséges bevonása és a Human Resources DevOps csapatával való kapcsolatfelvétel csak addig ideiglenes, amíg ez a funkció nincs engedélyezve a közvetlenül az LCS-ben.

1. Forduljon a támogatáshoz eltávolítási igény kezdeményezésére.
2. A támogatási csapat eltávolítási kérelmet kezdeményez a Human Resources DevOps csapatnál. 
3. Folytassa, miután értesült, hogy a környezet eltávolításra került.
4. Jelentkezzen be az LCS-be azzal a fiókkal, amelyet a Human Resources alkalmazásba való feliratkozáshoz használt. 
5. Válassza ki azt a Human Resources-projektet, amely tartalmazza a környezetet. 
6. Az LCS-projektben válassza a **Human Resources alkalmazás kezelése** csempét. 
7. Válassza ki az eltávolítani kívánt példányt, amelynél fel kell tüntetni a telepítés állapotát **Törölt** állapottal.
8. Válassz a **Példány eltávolítása** lehetőséget, és hagyja jóvá a döntést. 

## <a name="recover-a-soft-deleted-environment"></a>A részben törölt környezet helyreállítása

Ha törli azt a Power Apps környezetet, amelyhez a Emberi erőforrások környezete csatlakozik, akkor a Lifecycle Services Emberi erőforrások környezetének állapota **részben törlődik**. Ebben az esetben a felhasználók nem tudnak az Emberi erőforrásokhoz csatlakozni.

A környezet helyreállítása:

1. Kövesse a [Power Apps környzete visszaállítása](/power-platform/admin/recover-environment.md) részben található utasításokat.

2. Az Emberi erőforrások környezet helyreállításához forduljon a támogatáshoz. További információért lásd a [Támogatás kérése](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md) lehetőséget.

> [!Warning]
> A Power Apps környezeteket a törlést követően csak hét napig mentik. A környezetet a 7 napos időszakon belül kell helyreállítania.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
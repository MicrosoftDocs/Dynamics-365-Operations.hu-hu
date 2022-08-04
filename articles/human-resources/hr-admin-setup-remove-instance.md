---
title: Példány eltávolítása
description: Ez a témakör azt mutatja be, hogyan lehet eltávolítani a Microsoft teszt meghajtóját vagy éles környezetét Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0ce676c93e133cc04ad9c49417ed2ca0d6791e93
ms.sourcegitcommit: 1401d66b6b64c590ca1f8f339d622e922920cf15
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/20/2022
ms.locfileid: "9178472"
---
# <a name="remove-an-instance"></a>Példány eltávolítása

_**Érvényes:** Emberi erőforrások a különálló infrastruktúrán_ 

> [!NOTE]
> 2022 júliusa óta nem lehet új emberi erőforrások környezeteket létesítni a különálló emberi erőforrások infrastruktúrájára, Microsoft Dynamics és nem lehet új Lifecycle Services -projekteket létrehozni rajta. A vevők az emberi erőforrások környezetét telepítheti a pénzügyi és a műveleti infrastruktúrára. A további tudnivalókat lásd [az Emberi erőforrások biztosítása a pénzügyi és a műveleti infrastruktúra területén](/hr-admin-setup-provision-fo.md).

> [!IMPORTANT]
> A pénzügyek és a műveletek alkalmazás-infrastruktúrája támogatja a környezet törlését. A környezetek törlésével kapcsolatos további tudnivalókat [lásd: Környezet törlése](../fin-ops-core/dev-itpro/deployment/deployenvironment-newinfrastructure.md#delete-an-environment).

Ez a cikk bemutatja a Tesztelési meghajtó vagy a Microsoft éles környezetének eltávolítását Dynamics 365 Human Resources.

## <a name="remove-a-test-drive-environment"></a>Tesztkörnyezet eltávolítása

A Human Resources tesztverziói esetében 60 napos lejárati szabályt alkalmazunk. A tesztkörnyezetek tulajdonosai azonban korábban is be tudják fejezni a próbaidőszakot a következő lépések végrehajtásával. 

1. A [Power Apps Adminisztrációs központ](https://admin.businessplatform.microsoft.com/) megnyitása
2. Válassza a **Környezetek** lehetőséget.
3. Válassza ki a tesztmeghajtó-környezetet, amelynek hasonló az elnevezési mintázata ehhez: TestDrive - alias@domain
4. Válassza **Törlés** lehetőséget, és hagyja jóvá a döntést. 

A meglévő tesztkörnyezetet el fogjuk távolítani. Az eltávolítása után regisztráljon egy új tesztkörnyezetre. 

## <a name="remove-a-production-environment"></a>Éles környezet eltávolítása

Ez a cikk feltételezi, hogy a Human Resources rendszert felhőalapú szolgáltatón (CSP) keresztül vagy vállalati architektúra (EA) megállapodás részeként vásárolta. 

Mivel egyetlen emberi erőforrás környezet egyetlen Power Apps környezetben található, két lehetőség van, ezeket figyelembe kell venni a környezet eltávolításakor: 
- **Az egész környezet Power Apps eltávolítása.** Ez a beállítás akkor Power Apps javasolt, amikor a környezetet az Emberi erőforrások létrehozása céljából hozták létre, vagy a megvalósítás csak most kezdődik, vagy ha nincs bevetve integráció.  
- **Csak az Emberi erőforrások eltávolítása** Ez a beállítás akkor megfelelő, ha van Power Apps egy olyan környezet, amely a használt adatokkal van feltöltve, és Microsoft Power Apps Power Automate a.


> [!Important]
> A környezet eltávolítása Power Apps előtt győződjön meg arról, hogy nincs használatban az Emberi erőforrások hatókörán kívüli adatintegrációhoz. Vegye figyelembe azt is, hogy az alapértelmezett Power Apps környezeteket nem lehet eltávolítani. 

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

Ha törli azt a Power Apps környezetet, amelybe az emberi erőforrások környezete csatlakozik, az LCS-ben **az Emberi erőforrások környezet állapota törölve lesz**. Ebben az esetben a felhasználók nem tudnak az Emberi erőforrásokhoz csatlakozni.

A környezet helyreállítása:

1. Kövesse a [Power Apps környzete visszaállítása](/power-platform/admin/recover-environment) részben található utasításokat.

2. Az Emberi erőforrások környezet helyreállításához forduljon a támogatáshoz. További információért lásd a [Támogatás kérése](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md) lehetőséget.

> [!Warning]
> A Power Apps környezeteket a törlést követően csak hét napig mentik. A környezetet a hét napos időszakon belül vissza kell állítani.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

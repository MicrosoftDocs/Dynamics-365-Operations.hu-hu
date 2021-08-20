---
title: Munkarendelések létrehozása
description: Ez a cikk azt mutatja be, hogyan lehet munkarendeléseket létrehozni az Eszközkezelés modulban.
author: johanhoffmann
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetMaintenancePlan, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePoolsOpen
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: c1477e3c1b99172d84d2cdc64fc0ed01c057e0fa59422b30c17868ca400de4d0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6743698"
---
# <a name="creating-work-orders"></a>Munkarendelések létrehozása

[!include [banner](../../includes/banner.md)]

A megelőző karbantartási feladatok ütemezése után a következő lépés a feladatok munkarendeléseinek létrehozása. Ezt a lépést a karbantartási ütemezések egyikének használatával lehet végrehajtani. A karbantartási ütemezésben szereplő ütemezett feladatok különböző hivatkozási típusokkal rendelkezhetnek, ahogy azt a következő táblázat ismerteti:

| Hivatkozás típusa | Leírás |
|---|---|
| Karbantartási tervek | Megelőző karbantartási feladatok az *Idő* vagy a *Számláló* típusú karbantartási konstrukciók alapján. |
| Karbantartási körök | Olyan megelőző karbantartási feladatok, amelyek számos, hasonló típusú karbantartást igénylő eszközt tartalmaznak. |
| Karbantartási kérés | Manuálisan létrehozott kérés egy eszköz karbantartására vagy javítására. Ez a kérés munkarendelésre konvertálható. |

## <a name="create-work-orders-based-on-your-maintenance-schedule"></a>Munkarendelések létrehozása a karbantartási ütemezés alapján

A karbantartási ütemezésen alapuló munkarendelések létrehozásához kövesse ezeket a lépéseket.

1. Attól függően, hogy hogyan szeretné kiválasztani a munkarendelések ütemezési elemeit, a következő lapok valamelyikét nyitja meg:

    - Minden karbantartási ütemezés (**Eszközkezelés \> Ütemezéskezelés \> Minden karbantartási ütemezés**)
    - Nyitott karbantartási ütemezési sorok (**Eszközkezelés \> Ütemezéskezelés \> Nyitott karbantartási ütemezési sorok**)
    - Nyitott karbantartási ütemezési csoportok (**Eszközkezelés \> Ütemezéskezelés \> Nyitott karbantartási ütemezési csoportok**)

1. Jelölje be a rácsban mindegyik ütemezett karbantartási feladat jelölőnégyzetét, amely számára munkarendelést szeretne létrehozni. Majd a műveleti ablaktáblán válassza ki a **Munkarendelés** elemet.

    Megjelenik a **Munkarendelések létrehozása** párbeszédpanel. A kiválasztott sorokhoz tartozó összes előrejelzési órák száma a **Karbantartási előrejelzési órák** mezőben látható.

    ![Megjelenik a munkarendelések létrehozása párbeszédpanel.](media/18-preventive-maintenance.png)

1. A **Paraméterek** szakaszban adja meg a létrehozni kívánt munkarendelések számát. Válasszon a következő lehetőségek közül:

    - **Soronként egy munkarendelés** – karbantartási ütemezési soronként egy munkarendelést hoz létre.
    - **Egy munkarendelés per** – olyan munkarendelések létrehozása, amelyek a beállítás kiválasztásakor elérhetővé váló egyéb beállításoknak megfelelően csoportosítva vannak.

1. A **Munkarendelés típusa** mezőben válassza ki az összes létrehozott munkarendeléshez használni kívánt munkarendelés-típust.
1. A munkarendeléseknek a beállításoknak megfelelő létrehozásához kattintson az **OK** gombra.

## <a name="group-work-order-lines-that-are-automatically-created-while-a-maintenance-plan-runs"></a>A karbantartási terv futtatásakor automatikusan létrehozott munkarendeléssorok csoportosítása

Ezzel a funkcióval szabályokat határozhat meg a munkarendeléssorok egyetlen munkarendelés alá csoportosítására, ha a rendszer úgy van beállítva, hogy a karbantartási terv alapján automatikusan generálja a munkarendeléseket. Korábban az automatikusan generált munkarendelések csak egy sort tartalmazhattak. A munkarendeléseket azonban csoportosíthatja például eszköz, eszköztípus vagy működési hely szerint. (A manuálisan generált munkarendelések már csoportosíthatóak a témakör előző részében leírtak szerint.)

### <a name="enable-grouping-for-automatically-generated-work-orders"></a>Csoportosítás engedélyezése az automatikusan létrehozott munkarendelések számára

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [funkciókezelési](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Tárgyieszköz-kezelés*
- **Funkciónév:** *A munkarendelések karbantartási terv futtatása közbeni csoportosítására vonatkozó szabályok alkalmazása*

### <a name="set-up-grouping-for-automatically-generated-work-orders"></a>Csoportosítás beállítása az automatikusan létrehozott munkarendelések számára

Kövesse ezeket a lépéseket a csoportosítás beállításához az automatikusan létrehozott munkarendelések számára.

1. Lépjen az **Eszközkezelés \> Beállítások \> Megelőző karbantartás \> Karbantartási tervek** elemre.
1. Minden olyan tervnél, ahol csoportosított munkarendeléseket szeretne létrehozni, hajtsa végre a következő lépéseket:

    1. A lista ablaktáblán válassza ki a kívánt tervet.
    1. A **Sorok** gyorslapon győződjön meg arról, hogy minden sorban be legyen jelölve az **Automatikus létrehozás** jelölőnégyzet.

1. Lépjen az **Eszközkezelés \> Időszakos \> Megelőző karbantartás \> Karbantartási tervek ütemezése** elemre.
1. A **Karbantartási tervek ütemezése** párbeszédpanel **Időszak** szakaszában adja meg a terv időhatárát (mennyire kell előre látni, amikor olyan ütemezett karbantartási feladatokat keres, amelyekhez munkát hoz létre).
1. A **Munkarendelés automatikus létrehozása ütemezés alapján** beállítás legyen *Igen*.
1. A **Munkarendelés** szakaszban válasszon a következő lehetőségek közül:

    - **Soronként egy munkarendelés** – karbantartási ütemezési soronként egy munkarendelést hoz létre. (Ez a beállítás ugyanazt a funkciót biztosítja, mint amely akkor érhető el, ha *A munkarendelések karbantartási terv futtatása közbeni csoportosítására vonatkozó szabályok alkalmazása* funkció ki van kapcsolva.)
    - **Egy munkarendelés per** – olyan munkarendelések létrehozása, amelyek a beállítás kiválasztásakor elérhetővé váló egyéb beállításoknak megfelelően csoportosítva vannak.

1. Ha a karbantartási tervek közül csak néhány futtatásakor szeretné alkalmazni a beállításokat, akkor a **Szerepeltetni kívánt rekordok** gyorslapon igény szerint adja meg a szükséges szűrőket, akár csak a Microsoft Dynamics 365 Supply Chain Management más kötegelt munkáinál.
1. A **Futtatás a háttérben** gyorslapon adja meg a kívánt köteg- és ütemezési beállításokat, akár csak az Supply Chain Management többi kötegelt feladatához.
1. A kiválasztott karbantartási tervek futtatásához és/vagy ütemezéséhez kattintson az **OK** gombra.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
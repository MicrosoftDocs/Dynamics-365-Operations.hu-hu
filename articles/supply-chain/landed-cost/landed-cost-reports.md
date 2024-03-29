---
title: Partraszállítási költség jelentései
description: Ez a témakör leírja, hogyan lehet megtalálni és használni a Partra áras költség modulban elérhető különféle típusú jelentéseket.
author: Weijiesa
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-02-21
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 836d6b538b32d818ed3b825000d004b005ce95d8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905950"
---
# <a name="landed-cost-reports"></a>Partraszállítási költség jelentései

[!include [banner](../../includes/banner.md)]

## <a name="outstanding-invoices"></a>Kiegyenlítetlen számlák

A kinnlévő számlák jelentése felsorolja az összes hajóúthoz kapcsolódó különféle költségszintek függőben kinnlévő számláit. A hajóút és hajóútköltségek rendszeres egyeztetésére használatos a főkönyvi tranzakciók listájával. A járulékos költségek számlázása után törlődik a jelentésből.

Egy kinnlévő számlák jelentés létrehozásához hajtsa végre az alábbi lépéseket.

1. Lépjen a **Partraszállítási költség \> Jelentések \> Követés \> Kinnlévő számlák** menüpontra.
1. A **Kinnlévő számlák** párbeszédpanel **Dátum szerint** mezőjében adjon meg egy dátumot. A kimenetben szerepelni fog minden olyan számla, amely az adott napon vagy azelőtt kinnlévő volt.
1. A **Megjelenítés** területen válasszon az alábbi lehetőségek közül:

    - **Nem számlázott költség** – A becsült költségértékkel, de tényleges költségekkel nem rendelkező számlázott szállítmányok költségeinek beszámítása.
    - **Nem számlázott készlet** – Tartalmazza azokat a költségeket, amelyek számlázva lettek, de a beszerzési rendelés még nem érkezett be hozzájuk.
    - **Összes nem számlázott** – A **Nem számlázott költség** beállítás és a **Nem számlázott készlet beállítás** eredményének beszámítása.

1. Állítsa *Igen* értékre az **Új költségek beszámítása** lehetőséget az olyan költségek beszámításához, amelyekhez még nem tartozik tényleges költség, és amelyekhez készlet még nincs bevételezve. Ha *Nem* beállításra adja meg, a jelentés csak a már számlázott költségeket fogja tartalmazni.
1. A **Nézet** szakaszban engedélyezze a jelentésben szerepeltetni kívánt összes részlettípust.
1. Ahogy a Microsoft Dynamics 365 Supply Chain Management más típusú jelentéseinél is tenné, a **Cél** gyorslap segítségével válassza ki a jelentés kimeneti formátumát.
1. Ahogy a Supply Chain Management más típusú jelentéseinél tenné, a **Belefoglalandó rekordok** gyorslap segítségével korlátozza tovább a jelentésben szerepeltetendő rekordokat.
1. A jelentés előállításához válassza az **OK** gombot.

## <a name="activityprovider-analysis-reports"></a>Tevékenység/szolgáltató elemzési jelentései

A tevékenység/szolgáltató elemzési jelentésekben áttekintheti az egyes szolgáltatókra vonatkozó időbecsléseinek pontosságát.

Egy tevékenység/szolgáltató elemzési jelentés létrehozásához hajtsa végre az alábbi lépéseket.

1. A létrehozni kívánt jelentés típusától függően hajtsa végre a következő lépések valamelyikét:

    - Lépjen a **Partraszállítási költség \> Jelentések \> Tevékenység/szolgáltató tevékenység szerinti elemzése** pontra. Ebben az esetben az időbecslések tevékenység szerint lesznek csoportosítva.
    - Lépjen a **Partraszállítási költség \> Jelentések \> Tevékenység/szolgáltató szolgáltató szerinti elemzése** pontra. Ebben az esetben az időbecslések szolgáltató szerint lesznek csoportosítva.

    Megjelenik a **Tevékenység/szolgáltató tevékenység szerinti elemzése** párbeszédpanel vagy a **Tevékenység/szolgáltató szolgáltató szerinti elemzése** párbeszédpanel. Mindkét párbeszédpanelen ugyanazok a beállítások jelennek meg.

1. Ahogy a Supply Chain Management más típusú jelentéseinél is tenné, a **Cél** gyorslap segítségével válassza ki a jelentés kimeneti formátumát.
1. Ahogy a Supply Chain Management más típusú jelentéseinél tenné, a **Belefoglalandó rekordok** gyorslap segítségével korlátozza tovább a jelentésben szerepeltetendő rekordokat.
1. A jelentés előállításához válassza az **OK** gombot.

## <a name="voyage-costing-reports"></a>Hajóút költségszámítási jelentései

A hajóút költségszámítási jelentései mutatják a cikkek költségét és a csomagonkénti, szállítókonténerenkénti vagy hajóútonkénti importálási költségeket, attól függően, hogy milyen beállításokat választ ki a jelentés generálása során. Minden hajóút költségszámítási jelentése lehetővé teszi egy hajóút becsült költségének a tényleges költséggel való összehasonlítását, és több azonosító tényező szerint bontható le.

A hajóút költségszámítása jelentés létrehozásához hajtsa végre az alábbi lépéseket.

1. A létrehozni kívánt jelentés típusától függően hajtsa végre a következő lépések valamelyikét:

    - Lépjen a **Partraszállítási költség \> Jelentések \> Költségszámítás \> Hajóút költségszámítása egyéni költség szerint** elemre. Ebben az esetben az egyedi költség beállítás a költségtípuskódonkénti költségterületenkénti importálási költségeket mutatja.
    - Lépjen a **Partraszállítási költség \> Jelentések \> Költségszámítás \> Hajóút költségszámítása jelentési kategória szerint** elemre. Ebben az esetben az importálási költség le lesz bontva a különböző jelentési kategóriákra. A költségtípusok jelentési kategóriák szerint vannak csoportosítva.

    Megjelenik a **Hajóút költségszámítása egyéni költség szerint** párbeszédpanel, vagy a **Hajóút költségszámítása jelentési kategória szerint** párbeszédpanel. Ezek a párbeszédpanelek hasonlók. Az esetleges eltéréseket az eljárás többi részében is figyelembe kell venni.

1. Ha a **Hajóút költségszámítása jelentési kategória szerint** párbeszédpanelt nyitotta meg, a **Költség** mezőben válasszon a következő értékek közül:

    - **Költségérték** – Az érték számítása vagy automatikus költségek használatával történik, vagy kézzel kell létrehozni a költségterületen.
    - **Becsült** – Az áruk bevételezése után a becsült költség be lesz állítva.
    - **Tényleges** – A rendelés számlázása után a tényleges költség a számlán szereplő költségre lesz állítva.
    - **Legjobb** – A rendszer az előző három lehetőség közül a pontosabbat fogja használni. (Javasoljuk, hogy ezt a beállítást válassza.)

1. A **Cikkenként** beállítás *Igen* értékre állítása az egyes cikkek költségét mutatja. Állítsa *Nem* beállításra az hajóútonkénti költségek megjelenítése érdekében.
1. A **Nézet** szakaszban válassza ki azokat a kategóriákat, amelyek szerint lebontja a költséget.
1. A **Dimenziók** szakaszban válassza ki a jelentésben szerepeletni kívánt dimenziókat.
1. Ahogy a Supply Chain Management más típusú jelentéseinél is tenné, a **Cél** gyorslap segítségével válassza ki a jelentés kimeneti formátumát.
1. Ahogy a Supply Chain Management más típusú jelentéseinél tenné, a **Belefoglalandó rekordok** gyorslap segítségével korlátozza tovább a jelentésben szerepeltetendő rekordokat.
1. A jelentés előállításához válassza az **OK** gombot.

## <a name="shipping-container-receipts-list"></a>Szállítási konténer nyugtáinak listája

A szállítókonténer bevételezési listája tartalmaz minden olyan be nem vételezett mennyiséget, amely egy várható dátumra vagy azelőtt esedékes. A raktári munkatársak ezzel a jelentéssel azonosítják a szállítókonténerben várható árukat. Az áruk kézi érvényesítésére is használható, a szállítókonténeren való bevételezésük során.

A következő lépések szerint generálhat szállítókonténer-bevételezési listát.

1. Lépjen a **Partraszállítási költség \> Jelentések \> Követés \> Szállítókonténer-bevételezési lista** lehetőségre.
1. A **Szállítókonténer-bevételezési lista** párbeszédpanel **Várt dátum** mezőjében adjon meg egy dátumot. A kimenetben szerepelni fog minden olyan számla mennyiség, amely az adott napon vagy azelőtt nem bevételezettként szerepel.
1. A **Dimenziók** szakaszban válassza ki a jelentésben szerepeletni kívánt dimenziókat.
1. Ahogy a Supply Chain Management más típusú jelentéseinél is tenné, a **Cél** gyorslap segítségével válassza ki a jelentés kimeneti formátumát.
1. Ahogy a Supply Chain Management más típusú jelentéseinél tenné, a **Belefoglalandó rekordok** gyorslap segítségével korlátozza tovább a jelentésben szerepeltetendő rekordokat.
1. A jelentés előállításához válassza az **OK** gombot.

## <a name="expected-delivery-report"></a>Várható szállítási jelentés

A várható szállítási jelentés alapvető információkat tartalmaz a hajóútról, a szállítókonténerről, a levélről, a cikkekről, valamint a szállítás várható dátumáról.

Egy várható szállítási jelentés létrehozásához hajtsa végre az alábbi lépéseket.

1. Lépjen a **Partraszállítási költség \> Jelentések \> Követés \> Várható szállítás** menüpontra.
1. A **Várható szállítás** párbeszédpanel **Várható dátum** mezőjében válassza ki azt a dátumot, amikor az árukat várhatóan a végső célraktárba szállítják. A kimenetben szerepelni fog minden olyan hajóútsor, amely az adott napon vagy azelőtt várható, de még nem lett bevételezve.
1. Nem kötelező: A **Szállítói számla** mezőben válassza ki azt a szállítói számlát, amely a csak egy bizonyos szállítótól való kiszállításokat tartalmazza.
1. A **Dimenziók** szakaszban válassza ki a jelentésben szerepeletni kívánt dimenziókat.
1. Ahogy a Supply Chain Management más típusú jelentéseinél is tenné, a **Cél** gyorslap segítségével válassza ki a jelentés kimeneti formátumát.
1. Ahogy a Supply Chain Management más típusú jelentéseinél tenné, a **Belefoglalandó rekordok** gyorslap segítségével korlátozza tovább a jelentésben szerepeltetendő rekordokat.
1. A jelentés előállításához válassza az **OK** gombot.

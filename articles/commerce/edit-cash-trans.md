---
title: Készpénzzel fizetett, azonnal átvett és készpénzkezelési tranzakciók szerkesztése és auditálása
description: Ez a témakör azt ismerteti, hogy miként szerkesztheti és auditálhatja a készpénzzel fizetett, azonnal átvett és készpénzkezelési tranzakciókat a Microsoft Dynamics 365 Commerce szolgáltatásban.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7a9086da036712fc8c63498d95dc9f71f32f75c6
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792729"
---
# <a name="edit-and-audit-cash-and-carry-and-cash-management-transactions"></a>Készpénzzel fizetett, azonnal átvett és készpénzkezelési tranzakciók szerkesztése és auditálása

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogy miként szerkesztheti és auditálhatja a készpénzzel fizetett, azonnal átvett és készpénzkezelési tranzakciókat a Microsoft Dynamics 365 Commerce szolgáltatásban.

## <a name="overview"></a>Áttekintés

A Dynamics 365 Commerce ügyfelei belső pénztár (POS) alkalmazásokat, valamint külső pénztár (POS) alkalmazásokat is használnak. A belső alkalmazások esetén az üzleti tranzakciókat a rendszer a csatornákból kötegfolyamattal húzza be a Commerce központi felületére. A külső féltől származó alkalmazások esetében a tranzakciókat a rendszer integrációval húzza be a Commerce központi felületére. Mindkét esetben, miután a rendszer behúzta a tranzakciókat a Commerce központi felületére, konzisztencia-ellenőrzési folyamatot kell végrehajtani. Ez a folyamat több ellenőrzést futtat a tranzakciókon, és csak a sikeresen érvényesített tranzakciók kerülnek be a kivonatba, hogy közzé lehessen őket tenni a Commerce központi felületén.

A Commerce tranzakciók különböző okokból nem felelhetnek meg az ellenőrzésen. Az integrációs kód vagy a POS-alkalmazás hibája inkonzisztens adatokat okozhat. Másik lehetőségként egy felhasználói hiba is inkonzisztens adatokat okozhat. Például, ha a felhasználó töröl egy terméket, miután szinkronizálta a csatornával, vagy a felhasználó lezárja a pénzügyi időszakot anélkül, hogy az adott időszakra vonatkozó tranzakciókat feladta volna. Bár ezeket a tranzakciókat a rendszer megjelöli, és kizárja a kimutatásokból, zavart okoznak a vevő napi folyamataiban, amikor a napi értékesítést feladják a pénzügyi adatokba. A Commerce szolgáltatásban lehetősége nyílik azon tranzakciók szerkesztésére, amelyek nem feleltek meg az ellenőrzésen, és eközben a módosítások naplózása folyamatos maradhat.

## <a name="edit-transactions"></a>Tranzakciók módosítása

A Commerce 10.0.5-ös verziójában csak a készpénzzel fizetett, azonnal átvett tranzakciók – mint az értékesítés és a visszáruk – szerkeszthetők. A vevői rendelések és az online rendelések nem szerkeszthetők. A Commerce 10.0.6-os és újabb verziójában a készpénzkezelési tranzakciók is szerkeszthetők.

A tranzakciók szerkesztéséhez a Commerce központi felületén kövesse az alábbi lépéseket.

1. Telepítse a [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview) programot.
1. A Commerce központi felületén nyissa meg az **Üzlet pénzügyi adatai** munkaterületet. A **Tranzakció-ellenőrzési hibák** csempén azon tranzakció oldalának előre szűrt nézete látható, amely egy vagy több ellenőrzési szabálynak nem felelt meg.
1. Nyissa meg a tranzakció oldalt, válassza ki a rekordot, amely nem felelt meg az ellenőrzésen, válassza ki az **Office-bővítmény**, majd a **Kiválasztott tranzakció szerkesztése** lehetőséget. Megnyílik egy Excel-fájl, amely a kijelölt tranzakció részleteit mutatja. Ez a fájl a következő munkalapokat tartalmazza:

    - **Sorok** – Ezen a munkalapon szerepel a fejléc és a terméksorok a tranzakcióhoz, valamint a tranzakció kapcsolódó adatai.
    - **Fizetések** – Ez a munkalap a tranzakció fizetési sorainak részleteit tartalmazza.
    - **Engedmények** – Ezen a munkalapon szerepelnek a tranzakció engedménnyel kapcsolatos részletei.
    - **Adók** – Ezen a munkalapon szerepelnek a tranzakció adókkal kapcsolatos részletei.
    - **Költségek** – Ezen a munkalapon szerepelnek a tranzakció költségekkel kapcsolatos adatai.

1. Az Excel-fájlban módosítsa a megfelelő mezőket, majd töltse vissza az adatokat a Commerce központi felületére a Dynamics Excel-bővítmény közzétételi funkciója segítségével. Az adatok közzététel után a módosítások a rendszerben is megjelennek. A közzététel során a rendszer nem végez ellenőrzést a felhasználó által végrehajtott módosításokra.
1. A módosítások teljeskörű auditnaplóját megtekintheti, ha kiválasztja a **Kiskereskedelmi tranzakció** fejlécben (fejlécszintű adatok esetén) vagy az adott tranzakció oldalán a megfelelő szakaszban és rekordnál az **Auditnapló megtekintése** lehetőséget. Például az értékesítési sorokhoz kapcsolódó összes változás megjelenik az **Értékesítési tranzakciók** lapon, és a kifizetésekhez kapcsolódó összes változás megjelenik a **Fizetési tranzakciók** lapon. A módosításokra vonatkozóan a következő auditadatokat tartjuk meg:

    - Módosítás dátuma és időpontja
    - Mező
    - Régi érték
    - Új érték
    - Módosította

1. Miután elvégezte és közzétette a módosításokat, futtassa az **Üzlet tranzakcióinak ellenőrzése** lehetőséget, amellyel ellenőrizheti, hogy az elvégzett módosítások konzisztensek és érvényesek.

> [!NOTE]
> Csak azokat a tranzakciókat szerkesztheti, amelyek nem feleltek meg az ellenőrzésen. Ha az ellenőrzésen megfelelt tranzakciót szeretné szerkeszteni, módosítsa a tranzakció ellenőrzési állapotát **Hiba** vagy **Egyik sem** értékre, majd tegye közzé a módosítást. Ezután szerkesztheti a fejlécben vagy a tranzakció bármely más gyermekrekordjában lévő adatokat, és közzéteheti a fejlécet vagy rekordokat.

## <a name="bulk-edit-transactions-that-are-linked-to-a-statement"></a>Kivonathoz csatolt tranzakciók tömeges szerkesztése

A Commerce 10.0.6-os és újabb verzióiban a program támogatja a kimutatási szinten a tranzakciók tömeges szerkesztését.

A kivonathoz csatolt tranzakciók tömeges szerkesztéséhez a Commerce központi felületén kövesse az alábbi lépéseket.

1. Nyissa meg a **Kimutatások** lapot, és válassza ki a szerkesztendő tranzakciókat tartalmazó kimutatást.
1. Válassza a **Megnyitás Microsoft Office-ban** gombot.
1. Attól függően, hogy mit kell szerkesztenie, válasszon az alábbi lehetőségek közül:

    - **Készpénzzel fizetett, azonnal átvett tranzakciók szerkesztése** – Ezzel a lehetőséggel a kimutatásban szereplő összes készpénzben fizetett és azonnal átvett tranzakciót szerkesztheti. A következő Excel-munkalapok állnak rendelkezésre:

        - **Tranzakció** – Ez a munkalap az értékesítési tranzakciók összes fejlécszintű adatát tartalmazza.
        - **Értékesítési tranzakció** – Ez a munkalap az értékesítési tranzakciók összes sorszintű adatát tartalmazza.
        - **Fizetési tranzakciók** – Ez a munkalap az értékesítési tranzakciók összes fizetési sorának adatát tartalmazza.
        - **Engedményes tranzakciók** – Ez a munkalap az értékesítési tranzakciók összes engedménysorának adatát tartalmazza.
        - **Adótranzakciók** – Ez a munkalap az értékesítési tranzakciók összes adósorának adatát tartalmazza.
        - **Költségtranzakciók** – Ez a munkalap az értékesítési tranzakciók összes költségsorának adatát tartalmazza.

    - **Készpénzkezelési tranzakciók szerkesztése** – Ezzel a lehetőséggel a kimutatásban szereplő összes készpénzkezelési tranzakciót szerkesztheti. A következő Excel-munkalapok állnak rendelkezésre:

        - **Tranzakció** – Ez a munkalap a készpénzkezelési tranzakciók összes fejlécszintű adatát tartalmazza.
        - **Banki fizetőeszközzel történt tranzakciók** – Ez a munkalap az összes banki befizetéssel kapcsolatos tranzakció részleteit tartalmazza.
        - **Széfes fizetőeszközzel történt tranzakciók** – Ez a munkalap az összes széfes befizetéssel kapcsolatos tranzakció részleteit tartalmazza.
        - **Fizetőeszköz-elszámolás** – Ez a munkalap az összes fizetőeszköz-elszámolással kapcsolatos tranzakció részleteit tartalmazza.
        - **Bevételi/kiadási tranzakciók** – Ez a munkalap minden bevétel-kiadási tranzakció soradatait tartalmazza.
        - **Fizetési tranzakciók** – Ez a munkalap az összes fizetéssel kapcsolatos információt tartalmazza a **Számlafizetés** művelethez, valamint a bevétel-kiadási tranzakcióhoz.

1. Szerkessze a szükséges tranzakciókat.

    > [!NOTE]
    > A rendszer nem végez ellenőrzést a tömeges szerkesztésen átesett tranzakciók közzétételekor. Meg kell győződnie arról, hogy a módosítások pontosak, és megőrizte az adatok hűségét a munkalapok között. Ha például módosítani szeretné a tranzakció dátumát az olyan esetek kezelése érdekében, ahol a nyitott tranzakciók pénzügyi vagy készletperiódusa már lezárult, az összes olyan Excel-munkalapon módosítania kell a dátumot, amelyen szerepel az **Üzleti dátum** oszlop. Ha ellenőrizni szeretné a tranzakciókat a szerkesztés után, válassza ki a **Kimutatások** oldal **Tranzakciók ismételt ellenőrzése** lehetőségét. Várja meg az ellenőrzés befejeződését mielőtt közzétenné a kimutatást.

1. Ha a rendszer már létrehozta az összesítést, nyissa meg az **Összesített tranzakciók** lapot, és válassza az **Értékesítési rendelés xmlének újragenerálása** lehetőséget.

## <a name="bulk-edit-transactions-that-arent-linked-to-a-statement"></a>Kivonathoz nem csatolt tranzakciók tömeges szerkesztése

A Commerce 10.0.10-es és későbbi verzióban a program támogatja azon tranzakciók tömeges szerkesztését, amelyek nem felelnek meg az ellenőrzésen, de nincsenek kivonathoz csatolva.

A kivonathoz nem csatolt tranzakciók tömeges szerkesztéséhez a Commerce központi felületén kövesse az alábbi lépéseket.

1. Nyissa meg a **Minden üzlet** lapot, és válassza ki azt az üzletet, amely esetében a tranzakciókat szerkeszteni kell.
1. Válassza a **Megnyitás Microsoft Office-ban** gombot, majd a **Készpénzzel fizetett, azonnal átvett tranzakciók szerkesztése** lehetőséget.
1. Szerkessze a szükséges tranzakciókat, majd tegye közzé őket.

## <a name="additional-resources"></a>További erőforrások

[Online rendeléses és aszinkron vevői rendeléses tranzakciók szerkesztése és auditálása](edit-order-trans.md)

[Kiskereskedelmi tranzakciók pénzügyi dimenzióinak szerkesztése](edit-financial-dim.md)

[Excel-munkafüzet létrehozása a kiskereskedelmi tranzakciók szerkesztéséhez](create-excel-edit.md)

[Mezők hozzáadása Excel-munkafüzethez a kiskereskedelmi tranzakciók szerkesztéséhez](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
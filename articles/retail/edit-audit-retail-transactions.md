---
title: Kiskereskedelmi üzleti tranzakciók szerkesztése és naplózása
description: Ez a témakör a kiskereskedelmi üzleti tranzakciók szerkesztésével és naplózásával kapcsolatos funkciókat ismerteti.
author: josaw1
manager: AnnBe
ms.date: 10/14/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: b0201d31cd83b4360f96a7d8e2113caf9d913715
ms.sourcegitcommit: 0262a19e32b2c0c84c731d9f4fbe8ba91822afa3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/15/2019
ms.locfileid: "2622527"
---
# <a name="edit-and-audit-retail-store-transactions"></a>Kiskereskedelmi üzleti tranzakciók szerkesztése és naplózása

[!include [banner](includes/banner.md)]

[!include [banner](includes/preview-banner.md)]

A Dynamics 365 Retail ügyfelei belső, valamint külső pénztár (POS) alkalmazásokat is használnak. A belső pénztáralkalmazások esetén a kiskereskedelmi üzleti tranzakciókat a rendszer a csatornákból kötegfolyamattal húzza be a Retail Headquarters felületére. A külső féltől származó alkalmazások esetében a tranzakciókat integrációs folyamattal húzza be a rendszer a Retail Headquarters alkalmazásba. Mindkét esetben a tranzakciók Retail Headquarters szolgáltatásba való behúzása után végre kell hajtani egy konzisztencia-ellenőrzési folyamatot, ami számos ellenőrzést végez a tranzakciókon annak érdekében, hogy csak a sikeresen ellenőrzött tranzakciók kerüljenek be a Retail Headquarters szolgáltatásban feladandó kimutatásba. 

A kiskereskedelmi tranzakciók különböző okokból nem felelhetnek meg az ellenőrzésen. Előfordulhat például, hogy az integrációs kódban vagy a pénztáralkalmazásban található hiba inkonzisztens adatokat eredményez, vagy egy felhasználói hiba tehető felelőssé az inkonzisztenciáért, például ha a csatornára való szinkronizálás után töröltek egy terméket, vagy a kiskereskedelmi tranzakciók feladása nélkül zártak le egy pénzügyi időszakot.

Míg ezeket a tranzakciókat a rendszer megjelöli, és kizárja a kimutatásokból, a tranzakciók zavart okoznak a vevő napi folyamataiban, amikor a napi kiskereskedelmi értékesítést feladják a pénzügyi adatokba.

A Retail szolgáltatásban lehetősége nyílik azon specifikus kiskereskedelmi tranzakciók szerkesztésére, amelyek nem feleltek meg az ellenőrzésen, és eközben a módosítások naplózása folyamatos maradhat. 

## <a name="edit-and-audit-transactions"></a>Tranzakciók szerkesztése és naplózása

A Retail 10.0.5-ös verziójában csak a készpénzes és átviteli tranzakciók – mint az értékesítés és a visszáruk – szerkeszthetők. A vevői rendelések és az online rendelések szerkesztése nem támogatott. A Retail 10.0.6-os és újabb verzióiban már a készpénzkezelési tranzakciók szerkesztése is támogatott.

1. Telepítse a Dynamics Excel-bővítményt.

2. Nyissa meg a **Kiskereskedelmi üzlet pénzügyi adatai** munkaterületet. A **Tranzakció-ellenőrzési hibák** csempén azon Kiskereskedelmi tranzakció űrlapjának előre szűrt nézete látható, amely egy vagy több ellenőrzési szabálynak nem felelt meg.
 
3. Nyissa meg az űrlapot. Kattintson az ellenőrzésen meg nem felelt rekordra, majd az **Office-bővítmény** lehetőségre, és a **Kiválasztott tranzakciók szerkesztése** elemre. Megnyílik a kijelölt tranzakció részletes adatait tartalmazó Excel-fájl, a következő munkalapokkal:

    - Sorok: Ezen a munkalapon szerepel a fejléc, valamint a terméksorok és tranzakció kapcsolódó adatai.
    - Fizetések: Ez a munkalap a tranzakció fizetési sorainak részleteit tartalmazza.
    - Engedmények: Ezen a munkalapon szerepelnek a tranzakció engedménnyel kapcsolatos részletei.
    - Adók: Ezen a munkalapon szerepelnek a tranzakció adókkal kapcsolatos részletei.
    - Költségek: Ezen a munkalapon szerepelnek a tranzakció költségekkel kapcsolatos adatai.

4. Az Excel-fájlban módosíthatja a megfelelő mezőket, majd visszatöltheti az adatokat a Retail Headquarters rendszerébe a Dynamics Excel-bővítmény közzétételi funkciója segítségével. A közzététel után a módosítások a rendszerben is megjelennek. A közzététel során a rendszer nem végez ellenőrzést a felhasználó által végrehajtott módosításokon.

5. A módosítások teljeskörű auditnaplóját megtekintheti, ha a **Kiskereskedelmi tranzakció** fejlécben (fejlécszintű adatok esetén) vagy az adott tranzakció oldalán a megfelelő szakaszban és rekordnál az **Auditnapló megtekintése** lehetőségre kattint. Például az értékesítési sorokkal kapcsolatos módosítások az **Értékesítési tranzakciók** oldalon jelennek meg, a fizetéseken végzett változtatások a **Fizetési tranzakciók** oldalon szerepelnek stb. A módosítással kapcsolatosan megtartott naplózási információk a következők.

   - Módosítás dátuma és időpontja
   - Mező 
   - Régi érték
   - Új érték
   - Módosította:

6. Miután elvégezte és közzétette a módosításokat, futtassa újra az **Üzlet tranzakcióinak ellenőrzése** lehetőséget, amellyel ellenőrizheti, hogy az elvégzett módosítások konzisztensek és érvényesek.

> [!NOTE]
> Csak azokat a tranzakciókat szerkesztheti, amelyek nem feleltek meg az ellenőrzésen. Ha az ellenőrzésen megfelelt tranzakciókat szeretné szerkeszteni, módosítsa a módosítani kívánt tranzakció ellenőrzési állapotát **Hiba** vagy **Egyik sem** értékre, így képes lesz a szerkesztésre. 


## <a name="bulk-edit-transactions"></a>Tranzakciók tömeges módosítása

A Retail 10.0.6-os és újabb verzióiban a program támogatja a kimutatási szinten a kiskereskedelmi tranzakciók tömeges szerkesztését. 

1. Az Excel-bővítmény segítségével nyissa meg azt a kimutatást, amelynek tranzakcióit módosítani szeretné a fent leírt 1-3. lépéssel.

2. Válasszon az alábbi lehetőségek közül.

    - **Készpénzzel fizetett, azonnal átvett tranzakciók szerkesztése**. Ezzel a lehetőséggel a kimutatásban szereplő összes készpénzben fizetett és azonnal átvett tranzakciót szerkesztheti. A következő Excel-munkalapok állnak rendelkezésre.
    
       - **Tranzakció**: Ez a munkalap az értékesítési tranzakciók összes fejlécszintű adatát tartalmazza.
       - **Értékesítési tranzakció**: Ez a munkalap az értékesítési tranzakciók összes sorszintű adatát tartalmazza.
       - **Fizetési tranzakciók**: Ez a munkalap az értékesítési tranzakciók összes fizetési sorának adatát tartalmazza.
       - **Engedményes tranzakciók**: Ez a munkalap az értékesítési tranzakciók összes engedménysorának adatát tartalmazza.
       - **Adótranzakciók**: Ez a munkalap az értékesítési tranzakciók összes adósorának adatát tartalmazza.
       - **Költségtranzakciók**: Ez a munkalap az értékesítési tranzakciók összes költségsorának adatát tartalmazza.

    - **Készpénzkezelési tranzakciók szerkesztése**. Ezzel a lehetőséggel a kimutatásban szereplő összes készpénzkezelési tranzakciót szerkesztheti. A következő Excel-munkalapok állnak rendelkezésre.
     
       - **Tranzakció**: Ez a munkalap a készpénzkezelési tranzakciók összes fejlécszintű adatát tartalmazza.
       - **Banki fizetőeszközzel történt tranzakciók**: Ez a munkalap az összes banki befizetéssel kapcsolatos tranzakció részleteit tartalmazza.
       - **Széfes fizetőeszközzel történt tranzakciók**: Ez a munkalap az összes széfes befizetéssel kapcsolatos tranzakció részleteit tartalmazza.
       - **Fizetőeszköz-elszámolás**: Ez a munkalap az összes fizetőeszköz-elszámolással kapcsolatos tranzakció részleteit tartalmazza.
       - **Bevételi/kiadási tranzakciók**: Ez a munkalap minden bevétel-kiadási tranzakció soradatait tartalmazza.
       - **Fizetési tranzakciók**: Ez a munkalap az összes fizetéssel kapcsolatos információt tartalmazza a **Számlafizetés** művelethez, valamint a bevétel-kiadási tranzakcióhoz.

3.  A rendszer nem végez ellenőrzést a tömeges szerkesztésen átesett tranzakciók közzététele során. Meg kell győződnie arról, hogy a módosítások pontosak, és megőrizte az adatok hűségét a munkalapok között. Ha például módosítani szeretné a tranzakció dátumát az olyan esetek kezelése érdekében, ahol a nyitott kiskereskedelmi tranzakciók pénzügyi vagy készletperiódusa már lezárult, az összes olyan Excel-munkalapon módosítania kell a dátumot, amelyen szerepel az **Üzleti dátum** oszlop. Ha ellenőrizni szeretné a tranzakciókat a szerkesztés után, használja a **Kiskereskedelmi kimutatások** oldal **Tranzakciók ismételt ellenőrzése** lehetőségét.

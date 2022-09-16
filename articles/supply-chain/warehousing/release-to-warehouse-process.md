---
title: Kiadás raktárba
description: Ez a cikk a raktárba való kiadás folyamatának részleteit tartalmazza. Olyan entitásokat ír le, amelyek akkor jönnek létre, amikor egy rendelést kiadnak a raktárnak, valamint azokat a beállításokat, amelyek a folyamat inicializálására használhatók.
author: Mirzaab
ms.date: 8/13/2021
ms.topic: article
ms.search.form: WHSReleaseToWarehouse, WHSReleaseToWarehouseSalesOrder, WHSReleaseToWarehouseTransferOrder, WHSLoadPlanningWorkbench, WHSWaveTemplateTable, WHSWorkTemplateTable, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-13
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: caa38c4ed1c7fb8cf1ead3ba6534f8405a5ff57f
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428036"
---
# <a name="release-to-warehouse"></a>Kiadás raktárba

[!include [banner](../../includes/banner.md)]

Ez a cikk a raktárba való kiadás folyamatának részleteit tartalmazza. Olyan entitásokat ír le, amelyek akkor jönnek létre, amikor egy rendelést kiadnak a raktárnak, valamint azokat a beállításokat, amelyek a folyamat inicializálására használhatók.

## <a name="release-to-warehouse-overview"></a>Raktárba kiadás áttekintése

A raktárba történő kiadás az a folyamat, amellyel a készletet felkészítik a kiszállási feldolgozásra. A rendelés raktárba való kiadásakor a rendszer rakománysorokat és szállítmányokat hoz létre. Ha be van állítva az automatikus hullámfeldolgozás, létrejönnek a rakományok és a szükséges munka is. Az érintett entitások konfigurációja a rendszer beállításaitól függ. A cikknek ez a szakasza áttekinti a raktári kiadási folyamat során létrehozott entitásokat és az azokat meghatározó rendszerbeállításokat.

A *szállítmány* az ugyanannak a vevőnek vagy ugyanannak a szállítási címnek megfelelő értékesítésirendelés-sorok vagy átmozgatásirendelési-sorok csoportja.

A *rakomány* az értékesítésirendelés- vagy átmozgatásirendelés-sorok egy csoportja, amely csoportosítva van, és általában egy teherautóval, vasúti kocsival vagy más szállítási móddal küldik el. Egy rakományhoz egy vagy több szállítmány is tartozhat. A rakományt úgy hozhatja létre manuálisan, hogy rendeléssorokat ad hozzá egy új rakományhoz. Ebben az esetben a rendeléssorok még a raktárba való kiadás folyamatának kezdeményezése előtt hozzá vannak rendelve a rakományhoz, és csak a **Rakománytervezés munkaterület** oldalról lehet őket kiadni.

A raktári *munka* bármilyen raktári művelet, amelyet egy raktári dolgozó hajt végre. Általában a raktári műveletek legalább két egymást követő műveletből állnak: egy raktári dolgozó felveszi az aktuális készletet az egyik helyen, majd eltárolja a készletet egy másik helyen.

A rendelések raktárba való kiadásakor a rendszer *rakománysorokat* hoz létre, és szállítmányokba csoportosítja őket. A szállítmánykonszolidáció folyamata lehetővé teszi az automatikus szállítmánykonszolidációt a raktárba történő kiadás folyamat során. A további tudnivalókat lásd a Szállítmánykonszolidáció [irányelveinek áttekintésében](about-shipment-consolidation-policies.md).

A rendszer a *hullámok* segítségével hozza létre a kitárolási munkát és a szállítmányhoz szükséges rakományokat. A *hullámsablonnak* elérhetőnek kell lennie a létrehozni kívánt hullámtípushoz és a rendelési sor raktárához. A *Szállítás* típusú hullámsablonok értékesítési rendelések és átmozgatási rendelések cikkeinek szállításaihoz használható.

Minden hullámsablon tartalmaz *hullámmetódusokat*. A hullámmetódusok olyan műveleteket hajtanak végre, mint például munka létrehozása a hullámhoz vagy rakomány létrehozása. A szállítási hullám sablonja tartalmazhat például rakományokat létrehozó és sorokat hullámokba osztó módszereket, feltöltést, de akár kitárolási munkát is létrehozhat a hullámban. A hullámsablon számos beállítást hoz létre a hullám létrehozásának és feldolgozásának meghatározásához, beleértve azt is, hogy mely lépéseket kell manuálisan elvégezni, és melyeket automatikusan. További tájékoztatás: [Hullámsablonok](wave-templates.md). A hullámsablon konfigurációjától függően tehát a rendelés raktárba való kiadásakor a rendszer automatikusan létrehoz, feldolgoz és kiad egy hullámot, vagy a raktárba való kiadás után ezeknek a műveleteknek egy része vagy egésze manuálisan történik meg.

A hullám feldolgozásakor a rendszer a megfelelő *munkasablon* és *helyi irányelv* alapján kitárolási munkát hoz létre, és ezt a munkát mobileszközökön teszi elérhetővé. A munkasablon határozza meg, hogy hogyan történik a munka az egyes raktári folyamatokban, és a helyi irányelv határozza meg a készletmozgások kitárolási és betárolási helyeit. Bővebb információkért lásd: [Raktári munka ellenőrzése munkasablonok és helyutasítások használatával](control-warehouse-location-directives.md).

> [!NOTE]
> Alapértelmezés szerint a hullámok feldolgozása kötegelt módban történik.

A hullámfeldolgozás során a rendszer általában új rakományt hoz létre minden olyan szállítmányhoz, amelyhez nincs rakomány hozzárendelve. Ha azt szeretné, hogy a rendszer inkább meglévő rakományokhoz rendeljen hozzá nem hozzárendelt szállítmányokat, használhatja a speciális hullámrakomány-összeállítási funkciókat. A további tudnivalókat lásd: [Speciális rakomány-összeállítás hullám közben](advanced-load-building-during-wave.md).

Az **Értékesítési rendelések** és **Átmozgatási rendelések** oldalakon áttekintheti a rendeléssorokhoz a raktárba történő kiadás folyamata során létrehozott entitásokat.

- **Értékesítési rendelések** oldala:

    - Az **Értékesítésirendelés-sorok** gyorslapon válassza a **Raktár** elemet, majd a menüben válassza a **Szállítmány részletei** eemet a kapcsolódó szállítmányok megnyitásához, a **Rakomány részletei** elemet a kapcsolódó rakományok megnyitásához, vagy a **Munka részletei** elemet a kapcsolódó munka részleteinek megnyitásához.
    - A **Sor részletei** gyorslapon válassza a **Rakomány** lapot a kapcsolódó rakományok ellenőrzéshez.

- **Átmozgatási rendelések** oldala:

    - A műveleti ablaktábla **Szállítás** lapján válassza a **Szállítmány részletei** elemet a kapcsolódó szállítmányok megnyitásához, vagy a **Rakomány részletei** elemet a kapcsolódó rakományok megnyitásához.
    - Az **Átmozgatásirendelés-sorok** gyorslapon válassza a **Munka részletei** elemet a kapcsolódó munka részleteinek megnyitásához.

Összegzés: amikor egy rendelést kiadtak a raktárba, a legtöbb automatizált folyamat a következőképpen működik:

1. A rendszer létrehoz egy szállítmányt a rendeléshez és egy hullámot.
1. A hullám feldolgozása megtörténik.
1. A rendszer létrehoz egy rakományt és egy munkaazonosítót.

A hullámsablonok, munkasablonok és helyi irányelvek beállításaitól függően az folyamat egyes lépései manuálisak lehetnek. A teljes folyamat ugyanakkor változatlan marad.

A rendelés raktárba való kiadására számos lehetőség áll rendelkezésre. A műveletet manuálisan is végrehajthatja, illetve kötegelt feladatot is be lehet állítani. A cikk további részei részletesen áttekintik, hogy milyen módon lehet raktári kiadási műveletet végrehajtani.

## <a name="manual-release-to-the-warehouse-from-the-sales-orders-and-transfer-orders-pages"></a>Manuális kiadás a raktárba az Értékesítési rendelések és Átmozgatási rendelések lapról

A rendelést közvetlenül az **Értékesítési rendelések** vagy az **Átmozgatási rendelések** oldalról lehet a raktárba kiadni, ha a **Kiadás a raktárba** elemet választja.

- Az **Értékesítési rendelések** oldalon a gomb a műveleti ablaktábla **Raktár** lapján található.
- Az **Átmozgatási rendelések** oldalon a gomb a műveleti ablaktábla **Szállítás** lapján található.

Az **Értékesítési rendelések** oldalon egyszerre több értékesítési rendelés is kiadható.

## <a name="manual-release-to-the-warehouse-from-the-release-to-warehouse-pages"></a>Manuális kiadás a raktárba a Kiadás a raktárba oldalakról

A rendszer jelenleg három oldalt biztosít, ahol áttekintheti több rendelés sorait, és kiadhatja őket a raktárnak:

- **Kiadás raktárba** (**Warehouse Management \> Kiadás raktárba \> Kiadás raktárba**) - Ezen az oldalon értékesítési rendeléseket és átmozgatási rendeléseket is használhat. Ugyanakkor lassabb teljesítményt nyújt, mint a többi két oldal. Ez a lap hamarosan elavult lesz.
- **Értékesítési rendelések kiadása raktárba** (**Warehouse Management \> Kiadás raktárba \> Értékesítési rendelések kiadása raktárba**) - Ezen az oldalon csak értékesítési rendeléseket használhat. Ugyanakkor jobb teljesítményt nyújt, mint a **Kiadás raktárba** oldal.
- **Átmozgatási rendelések kiadása raktárba** (**Warehouse Management \> Kiadás raktárba \> Átmozgatási rendelések kiadása raktárba**) - Ezen az oldalon csak átmozgatási rendeléseket használhat. Ugyanakkor jobb teljesítményt nyújt, mint a **Kiadás raktárba** oldal.

Mind a három lap hasonló funkciókat tartalmaz, a fejezet többi részében leírtaknak megfelelő módon. Mindegyik lehetőséget ad a rendeléssorok vagy teljes rendelések kiválasztására, majd a raktárba való kiadására.

Minden egyes lap egy felső részből áll, ahol ki lehet választani a rendeléssorokat, és egy alsó részből, ahol kezdeményezheti a raktárba való kiadás folyamatát. A felső szakaszban szűrők használatával lehet keresni a kiadni kívánt értékesítésirendelés-sorok között. A **Kiadás raktárba** külön lapot tartalmaz az értékesítési rendelésekhez és az átmozgatási rendelésekhez a felső szakaszban, míg a másik két oldal csak egy fajta rendelést jelenít csak meg.

A felső rész eszköztára a következő gombokat tartalmazza, amelyek a raktárba kiadható rendeléssorok kiválasztására használhatók:

- **Hozzáadás** – Válasszon ki egy vagy több rendeléssort a felső szakaszban, majd válassza ezt a gombot a sorok alsó szakaszba való mozgatásához.
- **Az összes hozzáadása** – A felső szakasz minden sorának hozzáadása az alsó szakaszhoz.
- **Rendelés hozzáadása** – válasszon egy rendelést, majd válassza ezt a gombot, és adja hozzá a rendelés összes sorát az alsó szakaszhoz.

Miután befejezte a sorok hozzáadását az alsó részhez, jelöljön meg minden kiadni kívánt sort. Ezután az eszköztár **Kiadás raktárba** beállítását választva adja ki a sorokat a raktárba.

## <a name="manual-release-to-the-warehouse-from-the-load-planning-workbench-page"></a>Manuális kiadás a raktárba a Rakománytervezési munkaterület oldaláról

A rendelések manuálisan is kiadhatók a raktárba a **Rakománytervezés munkaterület** oldalán. Ezen a lapon a rendeléssorokat rakományokba rendezheti, majd ezeket a rakományokat kiadhatja a raktárba.

A **Rakománytervezés munkaterület** oldalának megnyitásához lépjen ide: **Warehouse Management \> Rakományok**. Ez megnyitható az **Értékesítési rendelések** és az **Átmozgatási rendelések** oldalról. Az oldal felső részén kiválaszthatja az **Értékesítési sorok** lapon az értékesítésirendelés-sorokat, az **Átmozgatási sorok** lapon pedig átmozgatásirendelés-sorokat, majd ezeket a sorokat hozzáadhatja egy új vagy meglévő rakományhoz.

A **Kínálat és kereslet** lapon a műveleti ablaktáblán a következő gombokkal adhat hozzá rendelési sorokat a felső részen egy rakományhoz:

- **Új rakományhoz** – Válasszon ki egy vagy több rendeléssort a felső szakaszban, majd válassza ezt a gombot új rakomány létrehozásához, és az adott sorok hozzáadásához.
- **Meglévő rakományhoz** – Válasszon ki egy vagy több rendeléssort a felső szakaszban, majd válassza ezt a gombot az adott sorok meglévő rakományhoz való hozzáadásához.
- **Teljes rendelés új rakományhoz** – Válasszon rendeléseket, majd válassza ezt a gombot új rakomány létrehozásához, és az adott rendelések összes sorának hozzáadásához.
- **Teljes rendelés meglévő rakományhoz** – Válasszon egy rendelést, majd válassza ezt a gombot az adott rendelés összes sorának egy meglévő rakományhoz hozzáadásához.

Az alsó szakaszban áttekintheti a létrehozott rakományokat. A rakományok raktárba való kiadásához válassza ki őket, majd válassza a **Kiadás \> Kiadás raktárba** elemet az eszköztáron. Ha automatikus hullámfeldolgozást használ, mivel a rakományok már hozzá vannak rendelve a rendelési sorokhoz, a rendszer szállítmányokat és munkaazonosítókat hoz létre, amikor a kiadás a raktárba műveletet végrehajtja.

## <a name="automatic-release-to-the-warehouse"></a>Automatikus kiadás a raktárba

A rendelések raktárba való automatikus kiadásához használja az **Értékesítési rendelések automatikus kiadása** és **Átmozgatási rendelések automatikus kiadása** feladatokat.

Értékesítési rendeléseket kiadó kötegelt feladat beállításához kövesse ezeket a lépéseket.

1. Nyissa meg a **Raktárkezelés \> Kiadás a raktárba \> Értékesítési rendelések automatikus kiadása** elemet.
1. Az **Értékesítési rendelések automatikus kiadása** párbeszédpanel **Paraméterek** gyorslapján állítsa be a következő mezőket:

    - A **Kiadni kívánt mennyiség** – Válassza ki, hogy a teljes mennyiséget vagy csak a ténylegesen lefoglalt mennyiséget kell kiadni a raktárba.
    - **Részlegesen kiadott rendelések kiadásának engedélyezése** – Adja meg, hogy a részlegesen kiadott rendelések fennmaradó mennyiségét ki kell-e adni a raktárba.
    - **Foglalások megtartása sikertelen kiadás esetén** – Adja meg, hogy az értékesítési rendelésekhez automatikusan lefoglalt mennyiségek megmaradnak-e, ha a raktárba való kiadás folyamata sikertelen.
    - **Csoportos kiadás vevő szerint** – adja meg, hogy a rendszer feldolgozta-e a raktári műveletek kiadását minden vevőnél, vagy egyszerre adja ki az összes értékesítési rendelést. Ha ez a beállítás *Igen*, a rendszer összegyűjti a kiválasztott vevő összes értékesítésirendelés-sorát, kiadja a rendeléseket a raktárba, majd feldolgozja a következő vevőt. Ha ez a beállítás *Nem*, a rendszer egyetlen raktári kiadási műveletben az összes elérhető értékesítésirendelés-sort kiadja. A beállítás engedélyezésével javítható a raktárba való kiadás folyamata teljesítményének és minőségének javítása. Ugyanakkor ügyelnie kell arra, hogy ezt a lehetőséget olyan hullámsablonokkal együtt használja, amelyek a hullámok raktárba való kiadáskor való feldolgozására vannak beállítva, mivel ez a kombináció több egy vevői hullámot generálhat, amelyek mindegyikét csak az ügyfél számára generálták. Ha olyan munkát szeretne létrehozni, amely több vevő szállítását egyesiti, akkor vagy ki kell kapcsolnia a Csoport kiadása vevő *szerint beállítást,* vagy ha a hullámsablonokat úgy szeretné beállítani, hogy a halasztott feldolgozást használja.
    - **Zárolt rendelések kezelése** – Válassza ki, hogyan kezelje a rendszer azokat az értékesítési rendeléseket, amelyek jelenleg zárolva vannak, mert más felhasználók vagy folyamatok szerkesztik őket:

        - *Várja meg a rendelések zárolásának feloldását* – A rendszernek meg kell várnia a rendelések zárolásának feloldását, mielőtt a raktárba kiadja azokat. Ebben az esetben a raktárba való kiadás folyamata több időt is igénybe vehet.
        - *Zárolt rendelések kihagyása* – A rendszernek ki kell hagynia a zárolt rendeléseket.

    - **Érvényes rendeléstípusok** – A kötegben szerepeletni kívánt értékesítési rendelések típusának kiválasztása.
    - **Hitelkeret típusa** – Itt kiválaszthatja, hogy kell-e hitelkeret-ellenőrzést végezni a raktári kiadási folyamat során, és ha az ellenőrzéseket végre kell hajtani, akkor milyen tranzakcióadatok szerepeljenek benne.

1. A feldolgozható rendelések szabályozásához válassza a **Szerepeltetni kívánt rekordok** gyorslapon a **Szűrés** lehetőséget. Megjelenik egy standard lekérdezési párbeszédpanel, ahol meghatározhatja a kiválasztási feltételeket, a rendezési feltételeket és az illesztéseket. A mezők ugyanúgy működnek, mint a Microsoft Dynamics 365 Supply Chain Management más lekérdezéstípusai.
1. A **Futtatás a háttérben** gyorslapon válassza ki, hogy a feladat kötegelt módban fusson-e, és/vagy állítson be egy ismétlődő ütemezést. A mezők ugyanúgy működnek, mint a Supply Chain Management más, [háttérben futó feladattípusai](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).
1. A beállítások alkalmazásához, valamint a kiadás a raktárba folyamat elindításához kattintson az **OK** gombra.

Átmozgatási rendeléseket kiadó kötegelt feladat beállításához kövesse a lépéseket.

1. Lépjen a **Raktárkezelés \> Kiadás a raktárba \> Értékesítési rendelések automatikus kiadása** elemre.
1. Az **Átmozgatási rendelések automatikus kiadása** párbeszédpanel **Paraméterek** gyorslapján állítsa be a következő mezőket:

    - A **Kiadni kívánt mennyiség** – Válassza ki, hogy a teljes mennyiséget vagy csak a ténylegesen lefoglalt mennyiséget kell kiadni a raktárba.
    - **Részlegesen kiadott rendelések kiadásának engedélyezése** – Adja meg, hogy a részlegesen kiadott rendelések fennmaradó mennyiségét ki kell-e adni a raktárba.
    - **Kiadások csoportosítása célraktár szerint** – Adja meg, hogy a rendszer egyszerre adja-e ki az összes átmozgatási rendelést, vagyhogy az átmozgatásirendelés-sorokat célraktár szerint csoportosítsa, és ezután az egyes csoportokat külön adja ki a raktárba.

1. A feldolgozható rendelések szabályozásához válassza a **Szerepeltetni kívánt rekordok** gyorslapon a **Szűrés** lehetőséget. Megjelenik egy standard lekérdezési párbeszédpanel, ahol meghatározhatja a kiválasztási feltételeket, a rendezési feltételeket és az illesztéseket. A mezők ugyanúgy működnek, mint a Supply Chain Management más lekérdezéstípusai.
1. A **Futtatás a háttérben** gyorslapon válassza ki, hogy a feladat kötegelt módban fusson-e, és/vagy állítson be egy ismétlődő ütemezést. A mezők ugyanúgy működnek, mint a Supply Chain Management más, [háttérben futó feladattípusai](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).
1. A beállítások alkalmazásához, valamint a kiadás a raktárba folyamat elindításához kattintson az **OK** gombra.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

---
title: Készletérték-jelentések
description: Ez a témakör bemutatja a készletérték-jelentések beállítását, előállítását és használatát. Ezek a jelentések részletes adatokat szolgáltatnak a tényleges készletről, valamint a pénzügyi mennyiségekről és összegekről.
author: banluo-ms
ms.date: 10/19/2021
ms.topic: article
ms.search.form: InventValueProcess, InventValueReportSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: banluo
ms.search.validFrom: 2021-10-19
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 7978c7b326ef1b62f76711ac187c28539eb1f449
ms.sourcegitcommit: ba10ba2cd4fb4267afb5aacae4f6a52aa2456e7e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/11/2021
ms.locfileid: "7798321"
---
# <a name="inventory-value-reports"></a>Készletérték-jelentések

[!include [banner](../includes/banner.md)]

A készletérték-jelentések részletes adatokat tartalmaznak a tényleges és pénzügyi készletmennyiségről és -összegekről. A jelentéseket többféleképpen lehet megtekinteni. Meg lehet például mutatni az összegeket vagy a tranzakciókat, vagy cikk vagy időtartomány szerint szűrni lehet a szűrést. Megtekintheti az eladott áruk (ELÁBÉ) értékeit vagy a folyamatban lévő munka értékeit, és egyéb beállításokat is meg lehet adni.

A készletérték-jelentések a következő feladatok elvégzésére adnak lehetőségeket:

- Egyeztetést kell tenni a főkönyv és a készlet között.
- Az adott időszak aktuális készletének és értékeinek egyeztetése.
- Adott célra testreszabott jelentéskonfigurációk létrehozása.
- A jelentéskonfigurációk mentése, hogy többször is használhatók legyen.
- Tartományok hozzáadása az adatok szűréséhez a jelentés futtatásakor.

## <a name="types-of-inventory-value-report"></a>Készletérték-jelentés típusai

Kétféle típusú készletérték-jelentés létezik: készletérték (a szokásos jelentés) és a **·** **készletérték-jelentés tárolása**.

### <a name="standard-inventory-value-report"></a>Normál készletérték-jelentés

A normál **készletérték-jelentés egy egyszerű jelentés, amellyel kiválaszthatja a jelentésben szereplő információkat, és meg tudja jelenni** a képernyőn. Nem menti az eredményeket. Emellett nem tartalmaz interaktív funkciókat szűréshez, leásáshoz, böngészéshez vagy exportáláshoz. Ezért a legtöbb esetben ajánlott a Készletérték-jelentés tárolási **·** jelentését használni.

### <a name="inventory-value-report-storage-report"></a>Készletérték-jelentés tárolási jelentése

A Készletérték-jelentés tárolási jelentése interaktív lapként szolgáltatja a kimenetet a Microsoft számára, vagy exportált dokumentumként, **·** többféle Dynamics 365 Supply Chain Management formátumban.

Ha a jelentést a böngészőben tekinti meg, az oszlopok és az összesítő egyenlegek dinamikusan módosulnak a konfigurált elrendezéstől függően. Lehetőség van az eredmények rendezésére, szűrésére, az adatok leásására és további részletekre.

A jelentés eredményeit a rendszer a **Készletérték** adatentitásban tárolja. Ezért az eredményeket a következő formátumra szűrheti, illetve exportálhatja: vesszővel tagolt értékek (CSV) vagy Microsoft Excel-formátum.

A **Készletérték-jelentés** tárolási jelentése hasznos, ha a kimenet több sort tartalmaz. Tegyük fel például, hogy 50 000 cikket tartalmaz, és a 300 üzleteket raktárakként hozták létre. Ebben az esetben, ha a készletzáró egyenlegeket cikkek, telephely és raktár szerint állítja be, akkor a kimenet számos sort tartalmaz.

> [!NOTE]
> A Készletérték-jelentés tárolási jelentése nem tartalmazza a jelentéselrendezésben **·** meghatározott részösszegeket. Nem tartalmazza a főkönyvi egyenlegeket sem, még akkor sem, ha azok az egyenlegek meg vannak határozva a jelentés elrendezésében. A főkönyvvel való egyeztetést a főkönyvi kivonatok segítségével kell végrehajtani. A szokásos készletérték-jelentés azonban tartalmazza ezeket a részösszegeket **·** és egyenlegeket.

## <a name="turn-on-the-inventory-value-report-storage-feature"></a>A Készletérték-jelentés tárolási funkció bekapcsolva

A normál **·** készletérték-jelentés alapértelmezés szerint engedélyezve van. Ha azonban a speciális készletérték-jelentés tárolási jelentését szeretné létrehozni, be kell kapcsolnia a funkciót a **·** rendszerben. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Költséggazdálkodás*
- **Funkció neve:** *Készletérték-jelentés tárolása*

## <a name="define-inventory-value-report-configurations"></a><a name="report-configuration"></a> Készletérték-jelentés konfigurációk meghatározása

A Készletérték-jelentések lapon lehet beállítani a különböző típusú készletérték-jelentésekben **·** szereplő tartalmat. A jelentéstípusok száma bármely lehet. Minden alkalommal, amikor valamelyik típusú készletérték-jelentést létrehozza, ki kell választania egy jelentéstípust.

1. Ugrás a **Készletkezelés \> készletkönyvelési irányelveinek beállítása – \> Készletérték-jelentések**
1. Tegye a következők egyikét:

    - Meglévő jelentés szerkesztéséhez jelölje ki azt a listaablakban, majd a **·** munkaablakban válassza a Szerkesztés lehetőséget.
    - Új jelentés létrehozásához válassza az Új lehetőséget a **·** munkaablakban.

1. Az új vagy kiválasztott jelentés fejlécében állítsa be a következő mezőket:

    - **Azonosító** – adja meg a jelentés rövid azonosítóját. Ennek az értéknek egyedinek kell lennie minden készletérték-jelentési konfiguráció között. Az új konfiguráció mentése után nem szerkeszthető.
    - **Név** – adja meg a jelentés jól leíró nevét.

1. Ha új jelentéskonfigurációt hoz létre, a fennmaradó mezők elérhetővé tenni a Mentés a **·** munkaablakban gombra kattintva.
1. Az **Általános** gyorslapon állítsa be a következő mezőket:

    - **·** Dátumintervallum – válasszon egy előre megadott dátumintervallumot. A jelentés futtatásakor felülbírálhatja ezt a dátumintervallumot.
    - **Tartomány – a feladási dátum vagy a tranzakció időpontja közül választhat attól függően, hogy a jelentés rekordjainak beolvassa azt a dátumot és időpontot, amikor rekordokat** *kell* *·* beolvasni.
    - **Dimenziókészlet** – annak a dimenziókészletnek a kiválasztása, amelyről az adatokat futtatni kell. (A dimenziók a főkönyvben vannak meghatározva.) Futtathatja például a fő számla vagy a Fő számla + Üzleti egység *·* *·* adatokat. A kiválasztott dimenziókészletnek nem lehet kettőnél több dimenziója. A további tudnivalókat [lásd: Pénzügyi](../../finance/general-ledger/financial-dimension-sets.md) dimenziókészletek.

1. Az Oszlopok **gyors területen állítsa be a következő** mezőket. Ezek a mezők vezérlők a jelentés oszlopai és az oszlopokban található adatok típusait.

    - **Készlet** – a készletértékek megjelenítése igenre *·* állítva. Ezt követően egyeztetheti ezeket az értékeket a főkönyvi számla egyenlegeivel.
    - **Folyamatban lévő** termelés – a folyamatban lévő termelés értékeinek megjelenítése *igenre* állítva. Ezt követően egyeztetheti ezeket az értékeket a folyamatban lévő munka főkönyvi számlaegyenlegeivel. Ha Igen beállításra választja ezt a beállítást, a jelentés csak a tényleges mennyiségeket és a folyamatban lévő raktározási állapotú *·* készletmennyiségeket mutatja. Azok a termelési rendelések, amelyek folyamatban lévő termelés állapotúak, ki vannak szedve vagy készként jelentve, de még nincsenek befejezve.
    - **Elhalasztott ELÁBÉ – a halasztott ELÁBÉ tényleges mennyiségeket és készletmennyiségeket megjelenítő oszlop megjelenítéséhez állítsa Igen** *·* beállításra. A halasztott ELÁBÉ tényleges mennyiségek és összegek felhasználásával jelenik meg, mivel ellentételként használja a csomagjegyzéken megjelenő mennyiségeket és összegeket.
    - **ELÁBÉ – a beállítás Igen beállítással megjeleníthető az ELÁBÉ pénzügyi mennyiségei** *és* összegei. Az ELÁBÉ pénzügyi mennyiségek és összegek felhasználásával jelenik meg, mivel ellentételét a számla mennyiségei és összegei.
    - **Eredmény – a beállítás Igen beállítással a készlet eredményszámláira feladott pénzügyi összegeket megjelenítő oszlop** *jelenik* meg.
    - **Összesített számlaértékek nyomtatása összehasonlításhoz – a főkönyvi számla egyenlegét megjelenítő oszlop megjelenítéséhez állítsa** *Igen* beállításra. Így nem kell ellenőriznie a csekkegyenleget. Ez a beállítás csak a szokásos **készletérték-jelentéssel** működik, a Készletérték-jelentés **tárolási** jelentésével nem. Ha igenre beállította ezt a beállítást, a következő mezők használatával kell megadnia az összes listához használni kívánt főkönyvi számlát, az engedélyezett pénzügyi *·* **pozícióbeállításoktól** függően.

        > [!NOTE]
        > Ha bármelyik mezőhöz teljes számlát választ, mind az összeg számlán szereplő készletszámla összege, mind az összegszámla *·* összege megjelenik.

        - **Készletszámla** – adja meg azt a főkönyvi számlát, amelynél a készletinformációk megmutatjak. (Mindkettő **Az összehasonlítási beállításhoz a készlet beállítást és az összesített számlaértékek nyomtatását** **Igen** értéken kell *·* beállítani.)
        - **Folyamatban lévő ásszámla – adja meg azt a** főkönyvi számlát, amelyről a folyamatban lévő adatokat meg kell jelenni. (Mindkettő **A folyamatban lévő feladat beállítás és az összehasonlítási beállítás összegző számlaértékének** **·** nyomtatása beállítást Igen beállításra kell *·* állítani.)
        - **Elhalasztott ELÁBÉ-számla – adja meg azt a főkönyvi számlát, amely** a halasztott ELÁBÉ-adatokat mutatja. (Mindkettő **A Halasztott ELÁBÉ beállítás és az összehasonlítási beállítás összegző számlaértékének nyomtatása beállítást Igen értéken** **kell** *·* beállítani.)
        - **ELÁBÉ-számla – adja meg** azt a főkönyvi számlát, amely számára meg kell jelenni az ELÁBÉ-adatok. (Mindkettő **Az ELÁBÉ beállítás és az összehasonlítási beállítás összegző számlaértékének nyomtatása** **beállítást Igen** beállításra kell *·* állítani.)

    - **A tényleges és a pénzügyi értékek összesítése – a beállítás Igen beállítással a teljes készletmennyiséget és készletmennyiséget (a tényleges és a pénzügyi készletértékek összefoglalását) tartalmazó oszlop jelenik** *·* meg. Ha ez a beállítás Nem, a jelentés a tényleges és a pénzügyi *·* készletértékeket is mutatja.
    - **A főkönyvbe fel nem adott tranzakciók megjelenítése: A beállítás Igen beállítással megjeleníthető a főkönyvbe fel nem adott** *·* tranzakciókat megjelenítő oszlop. Előfordulhat, hogy a következő típusú cikkek tranzakcióit nem lehet feladva a főkönyvbe:

        - A beérkezett, de még nem számlázott cikkek, ha a Tényleges készlet feladása beállítás törölve van a megfelelő **·** cikkmodellcsoportnál.
        - Bevételezéssel rendelkező, de még nem számlázott cikkek, ha a Termékbevételezés feladása a főkönyvbe beállítás törlődik, a Rendszer törli a termékbevételezés gyorslapját a Kötelezettségek paraméterei lap Általános lapján (Kötelezettségek beállítása – Kötelezettségek **·** **·** **·** **·** **\>\>** paraméterei).

    - **Átlagos egységköltség számítása – Az Átlagos egységköltség oszlop megjelenítéséhez állítsa** *Igen* beállításra. Az átlagos egységköltség a teljes mennyiség és a teljes összeg osztva.
    - **Összes mennyiség és érték – Igen értékre állítva a tényleges készlet (és pénzügyi mennyiségek) teljes mennyiségét és a tényleges készlet teljes összegét (és pénzügyi összegeket) megjelenítő oszlopok jelennek** *·* meg. Ez a beállítás csak akkor választható Igen beállításra, ha a Tényleges és pénzügyi értékek összesítése beállítás Értéke *·* **·** *·* Nem.
    - **Készletdimenziók – ebben a rácsban jelölje be a Nézet jelölőnégyzetet minden olyan dimenzió mellett, amely meg szeretné tekinteni** **a** jelentésen. Csak azok a dimenziók mutassanak a jelentésben, amelyeknél engedélyezve van a Pénzügyi készlet **·** beállítás. A többi dimenzióban csak az üres oszlopok fognak láthatók. A látni kívánt dimenzióknál bejelenheti az Összesítés jelölőnégyzetet, hogy az **·** összegek is szerepeljenek a mezőben.
    - **Erőforrás-azonosító – a Nézet lehetőség Igen beállítással megjeleníthető egy oszlop, amely azonosítja a cikket** **az egyes** *·* sorokban. Az Összesítés **lehetőség** beállítása Igen *·* beállítással az összegeket is tartalmazhatja. Az egyes sorokban felsorolt cikkek típusától függően az oszlop az alábbi típusú információkat jeleníti meg:

        - **Anyag – az oszlop a megfelelő anyagrekord**`ItemID` mezőértékét mutatja.
        - **Munka** – az oszlop a megfelelő `WorkCenterID` munkarekord mezőértékét mutatja.
        - **Közvetett költség** – az oszlop a megfelelő `CodeID` költségrekord mezőértékét mutatja.

        Ha a Nézet beállítás Nem értékre van állítva mind az Erőforrásazonosító, mind az Erőforráscsoport mezőben, akkor csak a kiválasztott készletdimenziókon alapuló teljes készletérték **·** *·* **·** **·** látható.

    - **Erőforráscsoport – a Nézet lehetőség Igen** **·** beállítással megjeleníthető az egyes sorok erőforráscsoportját *·* azonosító oszlop. Az Összesítés **lehetőség** beállítása Igen *·* beállítással az összegeket is tartalmazhatja. Az egyes sorokban felsorolt cikkek típusától függően az oszlop az alábbi típusú információkat jeleníti meg:

        - **Anyag – az oszlop a megfelelő anyagrekord**`ItemGroup` mezőértékét mutatja.
        - **Munka** – az oszlop a megfelelő `WorkcenterGroup` munkarekord mezőértékét mutatja.
        - **Közvetett költség** – az oszlop a megfelelő `CostGroup` költségrekord mezőértékét mutatja. (Az `CostGroupType` értéknek közvetettnek *kell* lennie.)

        Ha a Nézet beállítás Nem értékre van állítva mind az Erőforrásazonosító, mind az Erőforráscsoport mezőben, akkor csak a kiválasztott készletdimenziókon alapuló teljes készletérték **·** *·* **·** **·** látható.

1. A Sorok **gyors területen állítsa be a következő** mezőket. Ezekkel a mezőkkel a folyamatban lévő okkal kapcsolatos alszakaszokat adhat hozzá a jelentéshez, illetve eltávolíthatja azokat.

    - **Anyag** – állítsa Igen *·* beállításra az anyagokra vonatkozó információk megjelenítése érdekében. *Az anyag egy alapértelmezett erőforrástípus, mivel a megbízható kimenet létrehozásához az anyagokat minden* jelentéskonfigurációban szerepelnie kell.
    - **Munka – a folyamatban lévő munka munkaköltségének megjelenítése az** *Igen* beállítással.
    - **Közvetett költség – a folyamatban lévő tevékenység közvetett költségeinek megjelenítése** *igenre* állítva.
    - **Közvetlen kiszervezés – a folyamatban lévő termelés közvetlen kiszervezési költségeinek megjelenítése igenre** *·* állítva. Ez az információ alvállalkozói szerződésekhez hasznos.
    - **Részletező** szint – a jelentés megtekintési beállításának kiválasztása:

        - *Tranzakciók* – a jelentés minden vonatkozó tranzakcióinak megjelenítése. Ne feledje, hogy teljesítménybeli problémákat tapasztalhat, amikor nagy mennyiségű tranzakciót tartalmazó jelentéseket megtekint. Ezért ha ezt a nézet lehetőséget szeretné használni, javasoljuk, hogy használja a Készletérték-jelentés **tárolási** jelentését.
        - *Összegek* – a teljes eredmény megtekintése.

    - **Kezdő egyenleggel – a kezdő egyenleg megjelenítése igenre** *·* állítva. Ez a lehetőség csak akkor érhető el, ha a Részletes **szint** mező beállítása *·* Tranzakciók.

## <a name="generate-an-inventory-value-report-storage-report"></a>"Készletérték-jelentés" tárolási jelentés készítése

A következő lépések szerint hozhatja létre és tárolhat **készletérték-jelentés tárolási** jelentést.

1. Lépjen a **Költséggazdálkodás \> Lekérdezések és jelentések \> Készletérték jelentés tárhelye**.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A Készletérték párbeszédpanel Paraméterek gyorspanelén **állítsa be a következő** **·** mezőket:

    - **Név** – adja meg a jelentés egyedi nevét.
    - **Azonosító** – a [készletérték-jelentés](#report-configuration) konfigurációjának kiválasztása a jelentéshez. A jelentésbe bevetni kívánt oszlopok és sorok konfigurációs beállításai.
    - **·** Dátumintervallum – ennek a szakasznak a mezőivel adhatja meg, hogy mely rekordok szerepelnek a jelentésben. A dátumtartomány meghatározásához válasszon egyelőre beállított tartományt (a jelentés létrehozási dátumához képest) a **Dátumtartomány kódja** mezőben, vagy válasszon meghatározott dátumokat a **Kezdő dátum** és **Záró dátum** mezőkben.

1. A Gyorsjelentést is beveendő rekordokban állítsa be a szűrőket és megszorításokat, amelyek meghatározzák, hogy mely adatok **·** szerepeljenek a jelentésben. Válassza a Szűrő lehetőséget, ha meg szeretne nyitni egy szokásos lekérdezésszerkesztő párbeszédpanelt, ahol kiválasztási **·** feltételeket, rendezési feltételeket és illesztéseket határozhat meg. A mezők ugyanúgy működnek, mint a Supply Chain Management más lekérdezéstípusai. Ezeket a szűrőket a program a készlettranzakciókra alkalmazza, a főkönyvi egyenlegre nem. A szűrők beállításakor tartsa szem előtt ezt a viselkedést. Ellenkező esetben eltérés mutatkozhat a készlet és a főkönyv között.
1. A **Futtatás a háttérben** gyorslapon adja meg hogyan, mikor és milyen gyakran jöjjön létre a jelentés. A mezők ugyanúgy működnek, mint a Supply Chain Management más, [háttérben futó feladattípusai](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).

    > [!NOTE]
    > Ez a jelentés mindig a kötegelt feladat részeként futtatható.

1. Az **OK** gombra kattintva alkalmazza a beállításokat, és zárja be a párbeszédpanelt.

A kötegelt feladat befejezése után a jelentés megjelenik a **készletérték jelentés tárhelye** lapján. A jelentés megtekintéséhez előfordulhat, hogy frissíteni kell az oldalt.

> [!IMPORTANT]
> A kiválasztott készletérték-jelentés konfigurációjában előfordulhat, hogy helytelen a kezdő egyenleg, ha ugyanazt a dátumot a Kezdő dátum és a Kezdő dátum mezőben is bejeleni, és ha a Kezdő egyenleg be van állítva Igen értékre **·** **·** **·** *·* is.

## <a name="explore-an-inventory-value-report-storage-report"></a>Készletérték-jelentés tárolási jelentésének fedezheti fel

Miután létrehozta a jelentést, a következő lépések végrehajtásával bármikor megtekintheti és kivizsgálhatja:

1. Lépjen a **Költséggazdálkodás \> Lekérdezések és jelentések \> Készletérték jelentés tárhelye**.
1. A listában válasszon ki egy jelentést. Ez a lap a kiválasztott jelentés előállításához használt készletérték-jelentés [...](#report-configuration) konfigurációjának részleteit jeleníti meg.
1. A munkaablakban válassza a Részletek **megtekintése lehetőséget a jelentés** tartalmának megtekintéséhez.
1. A jelentés a következő lépések bármelyikével vizsgálható:

    - A Supply Chain Management legtöbb szabványos képernyőjén válassza ki majdnem bármely oszlop fejlécét úgy, hogy az adott oszlopban szereplő értékek alapján rendezze vagy szűrje a rácsot.
    - A **szűrő** mező használatával a jelentés tetszőleges értékkel szűrheti a különböző elérhető oszlopok bármelyikét.
    - Használja a Nézet menüt (a **szűrő** mező felett) a rendezési és szűrési beállítások kedvenc kombinációinak mentéséhez és betöltéséhez.

## <a name="export-an-inventory-value-report-storage-report"></a>Készletérték-jelentés tárolási jelentésének exportálása

A rendszer minden létrehozott jelentést a **Készletérték** adatentitásban tárol. A Supply Chain Management szabványos adatkezelési funkcióival exportálhat adatokat ebből az entitásból bármely támogatott adatformátumba, például CSV- vagy Excel-formátumba.

A következő példa bemutatja, hogyan lehet exportálni egy **készletérték-jelentés tárolási** jelentését.

1. Ugrás a **Rendszerfelügyelet \> Munkaterületek \> Adatkezelés** elemre.
1. Az **Importálás és exportálás** területen válassza az **exportálás** csempét.
1. A megjelenő **exportálás** oldalon be kell állítani az exportálási feladatot. Először adjon nevet a feladatnak.
1. A **kiválasztott entitások** területen válassza az **entitás hozzáadása** elemet.
1. A megjelenő párbeszédpanelen a következő mezőket állítsa be:

    - **Entitás neve** – Válassza a *Készletérték* elemet.
    - **Cél-adatformátum** – válassza ki azt a formátumot, amelybe az adatokat exportálni szeretné.

1. A **Hozzáadás** gomb kiválasztásával új sort adhat hozzá, majd a **Bezárás** paranccsal bezárhatja a párbeszédpanelt.
1. Általában egyszerre csak egy jelentést exportál. Egyetlen jelentés exportálásához állítsa be azt a sort, amelyet a **lekérdezés** párbeszédpaneléhez hozzáadott. Ily módon meghatározhatja, hogy melyik jelentés szerepeljen a **készletérték** entitásból az exportálásban. Kövesse ezeket a lépéseket, hogy egyetlen jelentés exportálásához adja meg a következő szűrőbeállításokat:

    1. A **tartomány** lapon válassza a **Hozzáadás** lehetőséget sor hozzáadásához.
    2. A **Tábla** mezőt állítsa *Készletérték* értékre.
    3. A **Származtatott tábla** mezőt állítsa *Készletérték* értékre.
    4. Állítsa a **Mező** mező értékét a szűréshez használt mezőre. Általában a **végrehajtás neve** mezőt és/vagy a **végrehajtási idő** mezőt fogja használni.
    5. A **feltételek** mezőt a kiválasztott mezőben keresendő értékre állíthatja. (Ha az előző lépésben bejelölte a **Végrehajtás neve** mezőt, ez az érték lesz a jelentés neve. Ha bejelölte a **végrehajtási idő** mezőt, akkor ez az az időpont, amikor a jelentés létrejött.)
    6. Vegyen fel több sort szükség szerint a **Tartomány** lapra addig, amíg nem egyedileg azonosította a keresett jelentést.

1. Az **OK** gombra kattintva mentse a beállításokat, és zárja be a párbeszédpanelt.
1. Az exportálási beállítások mentéséhez válassza a **Mentés** elemet.
1. Az **Exportálási beállítások** lapon válassza az **Exportálás most** lehetőséget az exportfájl létrehozásához.
1. Megjelenik a **Végrehajtási összesítés** lap, amelyen megtekintheti az exportálási feladat állapotát, valamint az exportált entitások listáját. Válassza az **Entitásfeldolgozái állapot** szakaszban a **Készletérték** entitást a listájából, majd válassza a **Fájl letöltése** elemet az adott entitásból exportált adatok letöltéséhez.

Ha további tájékoztatást szeretne arról, hogyan lehet az adatkezelést az adatok exportálására használni, akkor lásd: [Adatimportálási és-exportálási feladatok – áttekintés](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).

## <a name="generate-a-standard-inventory-value-report"></a>Normál készletérték-jelentés készítése

A következő eljárás szerint hozzon létre egy normál **·** készletérték-jelentést.

1. Ugrás a Költségkezelés – Lekérdezések és jelentések – Készletkönyvelés **\> – \> állapotjelentések - \> Készletérték**
1. A Készletérték-jelentés párbeszédpanel Paraméterek gyorsablakában állítsa be a **·** következő **·** mezőket:

    - **Név** – adja meg a jelentés egyedi nevét.
    - **Azonosító** – a [készletérték-jelentés](#report-configuration) konfigurációjának kiválasztása a jelentéshez. A jelentésben szerepeltetni kívánt oszlopok és sorok konfigurációs konfigurációs beállításai.
    - **·** Dátumintervallum – ennek a szakasznak a mezőivel adhatja meg, hogy mely rekordok szerepelnek a jelentésben. A dátumtartomány meghatározásához válasszon egyelőre beállított tartományt (a jelentés létrehozási dátumához képest) a **Dátumtartomány kódja** mezőben, vagy válasszon meghatározott dátumokat a **Kezdő dátum** és **Záró dátum** mezőkben.

1. A Gyorsjelentést is beveendő rekordokban állítsa be a szűrőket és megszorításokat, amelyek meghatározzák, hogy mely adatok **·** szerepeljenek a jelentésben. Válassza a Szűrő lehetőséget, ha meg szeretne nyitni egy szokásos lekérdezésszerkesztő párbeszédpanelt, ahol kiválasztási **·** feltételeket, rendezési feltételeket és illesztéseket határozhat meg. A mezők ugyanúgy működnek, mint a Supply Chain Management más lekérdezéstípusai.
1. A **Futtatás a háttérben** gyorslapon adja meg hogyan, mikor és milyen gyakran jöjjön létre a jelentés. A mezők ugyanúgy működnek, mint a Supply Chain Management más, [háttérben futó feladattípusai](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).
1. Az **OK** gombra kattintva alkalmazza a beállításokat, és zárja be a párbeszédpanelt. Megjelenik a jelentés.

## <a name="reading-inventory-value-reports"></a>Készletérték-jelentések olvasása

Ez a szakasz útmutatást ad a készletérték-jelentések olvasására és áttekintéséhez.

Az Ellátásilánc-kezelés a készletállapottal kapcsolatban a következő két fontos fogalomon keresztül támogatott:

- **Pénzügyileg frissített – ez a fogalom azt jelzi, hogy a készlettranzakciók** már ki vannak számlázva. A termelési rendelések a termelési rendelés végét jelzik.
- **Tényleges frissítés – ez a fogalom azt jelzi, hogy a készlettranzakciók még nincsenek számlázva, de már át vannak** fogadták vagy szállították. A termelési rendelések azt jelzik, hogy az anyagok ki vannak szedve, vagy a termelési rendelés készként van jelentve.

E két fogalom megértően könnyen megérthető a jelentés kimenetének következő oszlopai:

- **Készlet: pénzügyi mennyiség** – a pénzügyileg frissített mennyiség.
- **Készlet: pénzügyi összeg – a készlet pénzügyileg frissített** összege.
- **Készlet: feladott tényleges** mennyiség – a fizikailag frissített mennyiség.
- **Készlet: feladott tényleges összeg – a tényleges frissítésen áteső** készlet összege.
- **Készlet: fel nem adott tényleges mennyiség – az a mennyiség, amely készlettranzakciókat könyvel, de még nincs feladva a** főkönyvbe. Például van egy olyan cikkmodellcsoport, ahol a Tényleges készlet és a Pénzügyi készlet feladása beállítás törölve van, és van egy cikk, amely az adott csoporthoz **·** van **·** kapcsolva. Ezt követően létrehoz egy beszerzési rendelést, fogadja és kiszámláz. Ezen a ponton, ha áttekinti a cikk készletérték-jelentését, látni fogja, hogy a mennyiség és a beszerzési rendelés értéke megjelenik a Készlet: Fel nem adott tényleges mennyiség és készlet: Tényleges fel nem adott mennyiség **·** **·** oszlopban.
- **Készlet: fel nem adott tényleges összeg – be lehet állítani, hogy a jelentések fel nem adott összegeket** mutassanak. Ha viszont készletegyeztetésre használja a jelentést, ne használja ezt az értéket. Ellenkező esetben az összeg nem lesz feladva a főkönyvbe.
- **Készlet: mennyiség – a jelentés mennyiségi oszlopainak** teljes mennyisége.
- **Készlet: összeg – a jelentés** összegoszlopainak teljes mennyisége. Készletegyeztetés során ne használja ezt az oszlopot, ha a jelentésben szerepel a Készlet: Fel nem adott tényleges összeg **·** oszlop. Ebben az esetben ki kell zárnia a készletet: a fel nem adott tényleges összeg **·** a teljes összegből.
- **Átlagos egységköltség** – a teljes összeg osztva a teljes mennyiséggel.

A készletérték-jelentések általában a készletérték és a mennyiség megtekintésére használhatók. Időnként azonban a jelentés nem mutatja az összes vonatkozó készletdimenziót. Ha nem látja a várt dimenziókat, ellenőrizze a következő beállításokat:

- A cikk tárolási és nyomon követési dimenziócsoportjának áttekintése. Csak azok a dimenziók jelennek meg a jelentésben, amelyeknél engedélyezve van a Pénzügyi **·** készlet beállítás.
- Menjen a Költséggazdálkodás készletkönyvelési irányelveinek beállításához - Készletérték-jelentések, válassza ki a jelentés létrehozásához használt jelentéskonfigurációt, és győződjön meg arról, hogy a szükséges készletdimenziók ki vannak választva a **\> Nézet \>** **·** oszlopban.

Van például egy olyan cikk, amely az *A0001 cikkszámmal* rendelkezik. A tárolási dimenziók csoportjában csak a hely van engedélyezve a pénzügyi készlethez. A hely és a raktár is engedélyezve van a tényleges készlethez. A nyomon követési dimenziócsoportban a kötegszám engedélyezve van tényleges készlethez, pénzügyi készlethez azonban nem. Ezután egy olyan jelentéskonfigurációt kell használni, ahol a hely, a raktár és a kötegszám ki van választva. A jelentés megtekintésekor csak a helyhez látható érték. A raktár és a kötegszám oszlopai üresek. A példa bemutatja, hogy a készletérték-jelentéseken csak a pénzügyi készlethez engedélyezett készletdimenziók mutatnak.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

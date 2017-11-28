---
title: "Értékesítés és marketing"
description: "Az értékesítés és marketing segítségével beszerzése, tárolhatók és használhatók a különböző típusú adatokat az értékesítési folyamat. Ezt az adatot tartalmaz, az eredeti értékesítési kezdeményezés jövőbeli intézkedést és kiegészítő értékesítési."
author: kfend
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 92303
ms.assetid: 65ca9992-bbfa-4224-bf0e-067a25c7e6a4
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: da48a9eef118a7a369343c986e4b67f53266f7e1
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="sales-and-marketing"></a>Értékesítés és marketing

[!include[banner](../includes/banner.md)]


Az értékesítés és marketing segítségével beszerzése, tárolhatók és használhatók a különböző típusú adatokat az értékesítési folyamat. Ezt az adatot tartalmaz, az eredeti értékesítési kezdeményezés jövőbeli intézkedést és kiegészítő értékesítési.

<a name="marketing"></a>Marketing
---------

Marketing kampányok és tevékenységek segítségével megtalálhatja a potenciális ügyfeleket, valamint kapcsolatokat építhet ki velük, így a kezdeti interakciók üzleti kapcsolatokká fejlődhetnek. A következő folyamatábra a marketinghez kapcsolódó üzleti folyamatokat ábrázolja. [![Marketinghez kapcsolódó üzleti folyamatok](./media/marketing01.jpg)](./media/marketing01.jpg)

### <a name="relationships"></a>Kapcsolatok

Az értékesítés és marketing folyamán a potenciális ügyfelekkel való kapcsolat kezdeti kialakítása számos módon lehetséges. Előfordulhat például, hogy egy kereskedelmi bemutatón talál rá a leendő vevőire, vagy az is lehetséges, hogy a vállalat által indított tömeges levélkampány után válnak a vevők érdeklődőkké. Nagyon fontos megérteni egy adott fél entitásváltozásainak folyamatát, amelynek végén az illető fél vevővé válik. Az alábbi ábra az entitáskapcsolatok alakulását mutatja egy potenciális vevő tényleges vevővé válása során. [![SalesandMarketing01](./media/salesandmarketing01.jpg)](./media/salesandmarketing01.jpg)

### <a name="campaigns"></a>Kampányok

A kampányok az Ön által részvételre kiválasztott potenciális vevőkhöz, érdeklődőkhöz, lehetőségekhez, valamint vevőkhöz tartozó kapcsolatokat célozzák. A Microsoft Dynamics 365 for Finance and Operations rendszerben a vevői potenciál maximalizálása érdekében többféle kampányt is létrehozhat, többek között telemarketing-, levél- és e-mail-kampányokat. A kampány előrehaladása során, pozitív visszajelzések beérkezése esetén megkezdheti az értékesítési folyamatot a pozitív választ adó ügyfelekkel.

## <a name="sales"></a>Értékesítés
Az értékesítési funkció segítségével árajánlatokat, új és meglévő ügyfeleknek történő értéknövelt és párhuzamos értékesítéseket, továbbá értékesítési rendeléseket hozhat létre, valamint értékesítési számlákat készíthet a vevők számára. A következő folyamatábra az értékesítéshez kapcsolódó üzleti folyamatokat ábrázolja. [![Értékesítéshez kapcsolódó üzleti folyamatok](./media/sales01.jpg)](./media/sales01.jpg)

### <a name="sales-quotations"></a>Értékesítési ajánlatok

Értékesítési ajánlatok létrehozásával árajánlatot mutathat be a vevőknek az Ön által kínált árukra, szolgáltatásokra vonatkozóan. Lehetséges, hogy egy vevő kifejezetten árajánlatot kér, de árajánlat létrehozható egy potenciális vagy meglévő vevő egyéb kérésére adott válaszként is. Miután a vevő jóváhagyta az értékesítési ajánlatot, az értékesítési rendeléssé alakítható.

### <a name="up-sellcross-sell"></a>Párhuzamos értékesítés

Az értéknövelt, illetve a párhuzamos értékesítési technikák akkor alkalmazhatók, amikor bevisznek egy adott vevőhöz tartozó rendelést. Értéknövelt értékesítés esetén az aktuális termék helyett egy másikat javasolnak. Párhuzamos értékesítés esetén pedig az aktuális termék mellé javasolnak egy másikat. Terméklisták beállításakor egyedi szabályokat hozhat létre annak jelzésére, hogy mikor kell egy terméket párhuzamos vagy értéknövelt értékesítésre javasolni.

### <a name="sales-orders"></a>Értékesítési rendelés

Új értékesítési rendelés létrehozásakor ki kell választania az értékesítési rendelés típusát. Öt lehetőség között válogathat. **Megjegyzés:** Bármely rendeléstípus megváltoztatható az értékesítési rendelés létrehozása után, kivéve a **Cikkszükséglet** típust, amennyiben az értékesítési rendelés állapota **Teljesítve**.

| Értékesítési rendelés típusa  | Leírás                                                                                                                                                                                                                                                                                            |
|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Napló           | Ezt a típust értékesítési rendelések vázlataként érdemes használni. Nincs hatással a raktári mennyiségekre, és nem generál cikktranzakciókat.                                                                                                                                                                    |
| Előfizetés      | Ezt a típust ismétlődő rendelések esetén érdemes használni. A rendelés számlázása esetén a rendelés állapota automatikusan nyitott megrendelés lesz. A program frissíti a számlázott, kiszállított mennyiséget és a hátralévő kiszállításokat. Nem használhatja ezt az értékesítési rendeléstípust, ha a Raktárkezelés funkció használatban van. |
| Értékesítési rendelés       | Válassza ezt a típust, ha egy vevő rendelést küldött vagy igazolt vissza.                                                                                                                                                                                                                                        |
| Visszaküldött rendelés    | Akkor válassza ezt a típust, ha egy vevő visszaküldött egy cikket. A program automatikusan visszáru-cikkszámot (RMA-számot) hoz létre az esethez.                                                                                                                                                                                            |
| Cikkszükséglet | Ez a típus automatikusan létrejön, ha egy projekten keresztül cikkértékesítést végez.                                                                                                                                                                                                                       |

### <a name="sales-agreements"></a>Értékesítési szerződések

Az értékesítési szerződés olyan szerződés, amelyben egy vevő vállalja, hogy adott termékből időben elosztva egy bizonyos mennyiséget vagy összegnyit vásárol, különleges árak és engedmények ellenében. Az értékesítési szerződésben foglalt árak és engedmények felülírják a többi létező kereskedelmi megállapodásokban beállított árak és engedmények mértékét. Az értékesítési szerződések meghatározott időtartamra érvényesek. Az **Értékesítési rendelés** oldalon megadott, kért szállítási dátumnak az érvényességi időszakon belülre kell esnie. Az értékesítési szerződések alapértelmezés szerint várakoztatott állapotba kerülnek. Az értékesítési szerződésből csak akkor rendelhet, ha annak beállítása **Hatályos**.

### <a name="backorders"></a>Teljesítetlen rendelések

Rendelések rögzítésekor és érvényesítésekor szükség lehet teljesítetlen rendelések és kivételek kezelésére ahhoz, hogy az értékesítés megtörténhessen. A teljesítetlen rendelések lehetnek szállítótól még be nem érkezett beszerzési rendelések, vagy vevőnek még nem kézbesített értékesítési rendelések. A teljesítetlen rendelések nyomonkövetése igen fontos. Ha például késnek a szállítóktól érkező cikkek, lehet, hogy módosítani kell a vevőknek történő szállítás időpontját, és tájékoztatni kell a vevőket a késésről. A teljesítetlen rendelések cikk, vevő, illetve szállító szerint is megtekinthetőek.

#### <a name="viewing-backorders-by-item"></a>Teljesítetlen rendelések megtekintése cikkek szerint

Ha cikkek szerint tekinti meg a teljesítetlen rendeléseket, következtethet egy bizonyos cikk jövőbeni várható forgalmára. Ellenőrizheti például a következő adatokat:

-   Egy adott cikkre vonatkozó értékesítési rendelések száma.
-   Találhatóak-e még olyan cikkek, amelyeket a szállító még nem kézbesített?
-   Az értékesítési rendelések időben történő teljesítéséhez szükséges-e további cikkeket rendelni?

Ennek az ellenőrzésnek az elvégzése lehetővé teszi, hogy meg tudja válaszolni a vevők kiszállítási időpontra vonatkozó kérdéseit. Ezenkívül megadhatja a teljesítetlen értékesítési rendelések prioritási sorrendjét, és a készleten lévő cikkeket eloszthatja a rendelések között.

#### <a name="viewing-backorders-by-customer"></a>Teljesítetlen rendelések megtekintése vevő szerint

A teljesítetlen rendelések vevők szerinti áttekintésén láthatja a vevő hátralévő rendeléseinek az állapotát. Ez a jelölőnégyzet akkor hasznos, ha késésben lévő rendelésre váró vevőknek kell válaszolnia.

#### <a name="viewing-backorders-by-vendor"></a>Teljesítetlen rendelések megtekintése szállító szerint

A teljesítetlen rendelések szállítók szerinti áttekintésén a hiányzó szállításokat és a szállítások várható dátumát tekintheti meg. A jelölőnégyzet a függő szállítású cikkek prioritásának a beállítására is használható, ha cikkek érkeznek a szállítóktól, és ki kell választani a szállítandó értékesítési rendeléseket.

### <a name="invoices"></a>Számlák

Az értékesítési folyamat során három típusú számlát hozhat létre:

-   Vevői számla
-   Szabadszöveges számla
-   Proforma számla

#### <a name="customer-invoice"></a>Vevői számla

Az vevői számla olyan bizonylat, amelyet egy szervezet valamilyen eladás kapcsán ad át a vevő részére. A vevői számlát a fejlécet valamint a cikkekre vagy szolgáltatásokra vonatkozó, egy vagy több sort tartalmazó értékesítési rendelés alapján hozhatja létre. A vevői számla fejezi be az értékesítési rendelésből, a szállítólevélből és az értékesítési számlából álló ciklust.  

Feladhat és nyomtathat egyetlen vevői számlát vagy értékesítési rendelés, vagy csomagjegyzék és dátum alapján. Több vevői számlát feladhat és nyomtathat együttesen a szállítólevelek és a dátum alapján Egyetlen vevői számla értékesítési rendelés használatával való feladásakor a **Kiszámlázott hátralék** mező mennyisége minden cikkre vonatkozóan frissül a választott értékesítési rendelésen szereplő számlázott mennyiségek összegével.  

Ha az értékesítési rendelésen található összes cikknél 0 (nulla) a **Kiszámlázott hátralék** és a **Fennmaradó szállítása** értéke, az értékesítési rendelés **Számlázott** állapotú lesz. Ha egyik mező mennyisége sem nulla, az értékesítési rendelés állapota nem frissítődik, és további számlákat lehet hozzá felvinni. Ha egy vagy több, szállítólevél alapú vevői számla feladását és nyomtatását tervezi, legalább már egy szállítólevelet fel kellet adnia minden értékesítési rendelésnél. A vevői számla ezeken a szállítóleveleken alapul, és azok mennyiségeit tükrözi.  

A csomagjegyzék eddig kiszállított cikksorai alapján lehet vevői számlát készíteni még abban az esetben is, ha egy adott értékesítési rendelés összes cikke még nincs kiszállítva. Akkor lehet például ezt tenni, ha a jogi személy minden hónapban ad ki számlát a vevő számára, amely az adott havi összes szállítást tartalmazza. Mindegyik csomagjegyzék az értékesítési rendelésen található cikkek részleges vagy teljes kiszállítását képviseli.  

A számla feladásakor az egyes cikkekhez tartozó **Számlahátralék** értékét frissíti a program a kijelölt csomagjegyzékeken található, kiszállított mennyiségek összesítésével. Ha az értékesítési rendelésen található összes cikknél 0 (nulla) a **Számlahátralék** és a **Fennmaradó szállítása** értéke, az értékesítési rendelés **Számlázott** állapotú lesz. Ha a mennyiség nem nulla, az értékesítési rendelés állapota nem frissítődik, és további számlákat lehet hozzá felvinni. A készlettranzakciók a számla számával frissítődnek, míg az értékesítési rendelés sorának értéke **Számlázva** állapotra vált.

#### <a name="free-text-invoice"></a>Szabadszöveges számla

Egy szabadszöveges számla egy olyan számla, amely nincs kapcsolatban értékesítési rendeléssel. Olyan rendelési sorokat tartalmaz, amelyek főkönyvi számlákat, szabadszöveges leírásokat és értékesítési mennyiséget foglalnak magukban. Az ilyen típusú számlákon nem adhat meg cikkszámot, viszont meg kell adnia a forgalmi adóra vonatkozó megfelelő adatokat. Minden számlasoron fel van tüntetve a fő számla az értékesítéshez. A vevői egyenleg is feladásra kerül az összegző számlához a szabadszöveges számla esetében használt feladási profilból.

#### <a name="pro-forma-invoice"></a>Proforma számla

A pro forma számla olyan számla, amely a tényleges számla mennyiségének becsléseként készül el a számla feladása előtt. Pro forma számlát vevői és szabadszöveges számlához is ki lehet nyomtatni.





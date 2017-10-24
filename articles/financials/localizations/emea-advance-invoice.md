---
title: "Előlegszámlák Kelet-Európa számára"
description: "Az előlegszámla egy vevő vagy szállító számára létrehozott dokumentum. Azt az összeget tartalmazza, amelyet előre meg kell fizetni egy értékesítési rendelésre. Ez a témakör a kelet-európai előlegszámlákkal kapcsolatban tartalmaz tájékoztatást."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 272643
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: epopov
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2b2bd1c8768426ebadef0922cf629e0b41921978
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="advance-invoices-for-eastern-europe"></a>Előlegszámlák Kelet-Európa számára

[!include[banner](../includes/banner.md)]


Az előlegszámla egy vevő vagy szállító számára létrehozott dokumentum. Azt az összeget tartalmazza, amelyet előre meg kell fizetni egy értékesítési rendelésre. Ez a témakör a kelet-európai előlegszámlákkal kapcsolatban tartalmaz tájékoztatást.

Az előlegszámlák funkció a következő műveletek végrehajtását teszi lehetővé :

-   Előlegszámlák kiállítása vevők számára, és ezen előlegszámlák állapotának követése (**Nyitott**, **Részben fizetve** vagy **Lezárt**).
-   Előzetes számlatranzakciók és általános forgalmi adóval kapcsolatos (áfa-) tranzakciók (csak Lengyelország) feladása.
-   Kifizetési naplósorok automatikus létrehozása egy előlegszámla alapján.
-   A vevőktől kapott előlegek csatolása előlegszámlákhoz (az előleg feladása előtt vagy után).
-   A feladott előlegek áfafeladásának módosítása (például előleg átalakítása kifizetéssé vagy a kifizetés átalakítása előleggé, vagy a feladási dátum, az adó mértéke vagy az összeg módosítása).
-   Adóbizonylat létrehozása az áfaköteles szállítások esetében (kizárólag Csehország).

## <a name="advance-invoices-for-poland"></a>Előlegszámlák Lengyelország számára
Az előlegeket is átvevő lengyel vállalatoknak az előlegről is ki kell állítaniuk számlát a vevőnek. Ezt az előlegszámlát a főkönyvben kell feladni, és az áfaadózási célok kötelező dokumentuma. Az előlegszámlán kiszámított adót jelenteni kell az adóhatóságnak. Az áruk végleges eladása után az előlegszámlát meg kell adni az értékesítési számlán. Az értékesítés teljes összegének tartalmaznia kell az előlegeket. Az értékesítési számla feladásakor a program sztornírozza a kiegyenlített előlegszámlákat. Az eredeti előlegszámla kiegyenlítése egy előlegszámla sztornírozásával történik.

## <a name="set-up-accounts-receivable-for-advance-invoices"></a>A Kinnlevőségek előlegszámlákhoz történő beállítása
A **Kinnlevőségek paraméterei** lap **Frissítés** lapján adja meg a következő paramétereket.

|Gyorslap|Paraméter|Leírás|
|------|----------|------------|
|Előlegszámla  |Feladási profil|Válassza ki az előlegszámlával használandó feladási profilt (csak Lengyelország). **Fontos:** Csehország és Magyarország esetében a program az előlegszámlákat nem könyvelési és adóbizonylatokként kezeli, és nem a főkönyvbe adja fel őket. Ezért hagyja üresen ezt a mezőt ezen országok esetében, hogy megakadályozza az előlegszámlák főkönyvbe történő feladását.
|
|Előlegszámla  |Ki|számla beállítása        |Válassza ki az előlegszámlázáshoz használandó alapértelmezett ellenszámlát.|
|Előlegszámla  |Áfacsoport        |Válassza ki, hogy melyik áfacsoportot kell használni, amikor az áfát az előlegszámlázáshoz számítja ki.|
|Előlegszámla  |Helyesbítőként sztornírozás |Jelölje be ezt a jelölőnégyzetet, ha az előlegszámla sztornírozását helyesbítésnek kell tekinteni.|
|Előlegszámla  |Sztornírozás számlanapon|Ezen jelölőnégyzet bejelölésével sztornírozhatja az előleget a számla feladásának dátumán.|
|Fizetés          |Több előlegfizetési dátum|A következő lehetőségek közül választhat: **Elfogadás**, **Figyelmeztetés** vagy **Hiba**.|
|Fizetés          |Dátumeltérés          |A következő lehetőségek közül választhat: **Elfogadás**, **Figyelmeztetés** vagy **Hiba**.|
|Fizetés          |Összegeltérés        |A következő lehetőségek közül választhat: **Elfogadás**, **Figyelmeztetés** vagy **Hiba**.|
|Fizetés          |Kapcsolás feladott előlegszámlához|A következő lehetőségek közül választhat: **Elfogadás**, **Figyelmeztetés** vagy **Hiba**.|
|Fizetés          |(CZE), (POL) Előleg kezelése|Válassza a **Speciális** lehetőséget.|

A **Számsorozatok** lapon állítsa be az alábbi hivatkozások számsorozatkódját:

-   Adóbizonylat
-   Adójóváírás
-   Előlegszámla
-   Előlegszámla-jóváírás
-   Előlegszámla sztornírozása
-   Előlegszámla bizonylata
-   Előlegszámla-jóváírás bizonylata
-   Előlegszámla sztornírozási bizonylata

## <a name="create-a-customer-advance-invoice"></a>Vevői előlegszámla létrehozása
Kattintson a **Kinnlevőségek** &gt; **Közös** &gt; **Előlegszámlák** &gt; **Minden előlegszámla** lehetőségre. Új előlegszámla létrehozásához a Műveleti ablaktáblán az **Előlegszámla** lapon kattintson az **Előlegszámla** elemre. Adja meg a szükséges adatokat, majd kattintson a **Feladás** elemre az előleszámla feladásához. Az előlegszámla az alábbi állapotokkal rendelkezhet: **Megnyitva**, **Részben fizetve** vagy **Lezárt**. Manuálisan módosíthatja a feladott előlegszámla állapotát. Kattintson az **Állapot** lehetőségre, majd az **Előlegszámla állapotának módosítása** lapon az **Új állapot** mezőben válassza ki az előlegszámla új állapotát. **Megjegyzés:** Egy előlegszámla állapota bármikor módosítható. Zárt előlegszámlákat tranzakciókban nem lehet feldolgozni. **Megjegyzés:** Lengyelország esetében előzetes számlatranzakciók jönnek létre, ha a Kinnlevőségek paramétereiben állított be feladási profilt. A feladott tranzakciók megtekintéséhez az **Előlegszámla** lapon kattintson a **Bizonylat** lehetőségre.

## <a name="vat-on-advance-invoices"></a>Előlegszámlák áfája
A vállalatoknak kötelező áfát figyelembe venniük a vevőktől kapott előlegekre annak ellenére, hogy az értékesítés még nem történt meg. Az előleg áfájának feladásához hozzáadhat egy sort, amely tartalmazza előlegszámla áfa-specifikációit. Az előlegszámla több sort tartalmazhat, és a sorok az értékesítési rendelési sorokból vett áfa-specifikációkat tartalmazhatnak. Ezért az előleg áfáját szigorúan az értékesítési rendelési soroknak megfelelően adhatja fel. **Megjegyzés:** Az áfa-specifikációk csak akkor másolódnak az előlegszámla soraiba, ha az **Adótípus** mező az **Áfakódok** lapon **Normál áfa** vagy **Csökkentett áfa** értékre van állítva. Ellenkező esetben a sor úgy kerül rá az előlegszámlára, mintha az áfa összege 0 (nulla) lenne.

## <a name="link-an-advance-invoice-to-a-sales-order-or-a-free-text-invoice"></a>Előlegszámla csatolása értékesítési rendeléshez vagy szabadszöveges számlához
Minden egyes előlegszámla egyszerre csak egy értékesítési rendeléshez vagy szabadszöveges számlához csatolható. Egy meglévő előlegszámlát is hozzárendelhet egy másik értékesítési rendeléshez vagy egy szabadszöveges számlához, feltéve, hogy nem kapcsolódnak előlegek az előlegszámlához. Előlegszámla értékesítési rendeléshez történő csatolásakor a **Minden előlegszámla** lapon válassza ki az előlegszámlát. A Műveleti ablaktáblán kattintson az **Előlegszámla** lehetőségre, majd az **Értékesítési rendelés** lehetőségre. Válassza ki az előlegszámlához csatolni kívánt értékesítési rendelést, és kattintson az **OK** gombra. Előlegszámla szabadszöveget számlához történő csatolásakor a **Minden előlegszámla** lapon válassza ki az előlegszámlát. A Műveleti ablaktáblán kattintson az **Előlegszámla** lehetőségre, majd a **Szabadszöveges számla** lehetőségre. Válassza ki az előlegszámlához csatolni kívánt szabadszöveges számlát, és kattintson az **OK** gombra.

## <a name="create-a-customer-advance-invoice-from-a-sales-order"></a>Vevői előlegszámla készítése értékesítési rendelésből
Hozzon létre értékesítési rendelést, vagy válasszon ki egy létező értékesítési rendelést. Kattintson a **Számla** lehetőségre, majd kattintson a **Létrehozás** &gt; **Előlegszámla** lehetőségre. Az **Előlegszámla létrehozása** lapon állítsa be a következő mezőket.

| Mező                                           | Leírás                                                                                                                                                                                                                               |
|-------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Százalék                                         | Adja meg az értékesítési rendelés előlegének százalékát.                                                                                                                                                                             |
| Ellenszámla                                  | Válassza ki az előlegszámlázáshoz használandó alapértelmezett ellenszámlát.                                                                                                                                                                         |
| Rendelés frissítése                                    | Válasszon a következő lehetőségek közül: **Mind**, **Szállítás most**, **Kitárolva**, **Szállítólevél** vagy **Kitárolt mennyiség és nem raktározott termékek**. Az előlegszámla összegét a program a cikkek értékesítési rendelési összegei alapján számítja ki. |
| Áfa feladása                                        | Adja meg, hogy fel akarja-e adni az áfát az előzetes számla feladása során.                                                                                                                                                                      |
| Áfadátum feladása                                   | Adja meg az áfa feladásának dátumát.                                                                                                                                                                                                         |
| Feladási profil az előlegnapló-bizonylathoz | Adja meg az előleghez tartozó feladási profilt.                                                                                                                                                                                           |
| Adódokumentum létrehozása                             | Adja meg, hogy létrejöjjön-e adóbizonylat.                                                                                                                                                                                         |

> [!MEGJEGYZÉS} Lengyelország esetében előzetes számlatranzakciók jönnek létre, ha a Kinnlevőségek paramétereiben állított be feladási profilt.

## <a name="create-a-customer-advance-invoice-from-a-free-text-invoice"></a>Vevői előlegszámla létrehozása szabadszöveges számlából
Hozzon létre szabadszöveges számlát, vagy válasszon ki egy létező szabadszöveges számlát. A **Számla** lapon az **Új** szakaszban kattintson az **Előlegszámla** lehetőségre. Ezt követően létrehozhatja a szabadszöveges számlához kapcsolódó új előlegszámlát. **Megjegyzés:** Lengyelország esetében előzetes számlatranzakciók jönnek létre, ha a Kinnlevőségek paramétereiben állított be feladási profilt.

## <a name="print-an-advance-invoice"></a>Előlegszámla nyomtatása
Előlegszámla nyomtatásához at **Előlegszámla** lapon kattintson a **Nyomtatás** lehetőségre. Lengyelország esetében kinyomtathatja a pénzügyi bizonylat előlegszámla-bizonylatát. Válasszon ki egy beállítást az előlegszámla feladása során. Lengyelország esetében az értékesítési számláknak és a szabadszöveges számladokumentumoknak tartalmazniuk kell az elszámolandó előlegszámlával kapcsolatos következő információkat:

-   Előlegszámla száma
-   Előlegszámla dátuma
-   Áfa nélküli összeg, áfa összege, összeg áfával és pénznem
-   Adó (%)

Az áfaösszegek összesítésének tartalmaznia kell az **Előlegszámla adója** pontot. Az esedékes összeget csökkenteni kell az előlegszámla összegével.

## <a name="create-a-payment-proposal-from-an-advance-invoice"></a>Fizetési javaslat létrehozása előlegszámlából
Automatikusan létrehozhat kifizetési naplósorokat egy előlegszámla alapján. Amikor új kifizetési naplót hoz létre, a **Fizetési napló** lapon válassza az **Előlegnapló-bizonylat** lehetőséget, majd kattintson a **Sorok** lehetőségre. A **Naplóbizonylat** lapon kattinthat a **Kifizetési javaslat** &gt; **Kifizetési javaslat előlegszámlából** lehetőségre egy kifizetési javaslat előlegszámlákból történő létrehozásához. A feladási profil és az áfacsoportok adatai az előlegszámlából származnak. **Megjegyzés:** Az új előlegfizetések automatikusan az előlegszámlákhoz lesznek kapcsolva, ha az **Előlegek csatolása** és az **Állapot módosítása** beállítások vannak kijelölve a **Fizetési javaslat létrehozása előlegszámlákból** lapon.

## <a name="link-a-prepayment-to-an-advance-invoice"></a>Előleg csatolása előlegszámlához
Ha egy előleget szeretne kapcsolni egy előlegszámlához a kifizetési naplóból, nyissa meg a kifizetési naplót, válassza ki az előleget tartalmazó sort, és kattintson a **Funkciók** &gt; **Csatolás előlegszámlákhoz** lehetőségre. Ha az előleget a **Vevőtranzakciók** lapon levő előlegszámlához szeretné csatolni, kattintson a **Minden vevő** &gt; **Vevő** &gt; **Tranzakciók** lehetőségre. Válassza ki a kifizetési naplót, válassza ki az előleget tartalmazó sort, majd kattintson a **Funkciók** &gt; **Csatolás előlegszámlákhoz** lehetőségre.

## <a name="link-an-advance-invoice-to-a-prepayment"></a>Előlegszámla csatolása előleghez
Előlegszámla előlegsorhoz történő csatolásakor a **Minden előlegszámla** lapon válassza ki az előlegszámlát. A Műveleti ablaktáblán kattintson az **Előlegszámla** lehetőségre, majd az **Előleg** lehetőségre. Válassza ki az előlegszámlához csatolni kívánt előlegsort, és kattintson az **OK** gombra.

## <a name="advance-invoice-credit-note"></a>Előlegszámla-jóváírás
-   (POL) Előlegszámla érvénytelenítéséhez létrehozhat egy előlegszámla-jóváírást, és feladhatja azt a főkönyvbe.
-   A jóváírás létrehozásához létrehozhat egy új előlegszámlát, majd kattintson a **Jóváírás** lehetőségre. Ezután kiválaszthatja az érvénytelenítendő előlegszámlát.
-   Előlegszámla kiegyenlítéséhez kapcsolódó értékesítésiszámla-jóváírást is létrehozhat.
-   Az előlegszámla-jóváírás elrendezése a korrekció előtti és utáni sorok adatait tartalmazza.
-   (POL) Főkönyvi tranzakciók előlegszámla jóváírásának feladása után jönnek létre.

## <a name="cze-tax-documents"></a>(CZE) Adóbizonylatok
A Cseh Köztársaság esetében létrehozhat egy olyan adóbizonylatot, amely az áfaköteles szállításra vonatkozó előlegadatokon alapul. Az előleg lapon létrehozhatja, létrehozhatja és megjelenítheti, valamint létrehozhatja és kinyomtathatja az adóbizonylatot. Kattintson a **Funkciók** &gt; **Adóbizonylag** elemre, és válasszon a következő lehetőségek közül. Az adóbizonylat tartalmazza az áfa részletes adatait, például az áfa típusát és értékét, valamint annak alapját a könyvelési pénznemben és a tranzakció pénznemében.

## <a name="set-up-accounts-payable-for-advance-invoices"></a>A Kötelezettségek előlegszámlákhoz történő beállítása
A **Kötelezettségek paraméterei** lapon a **Számsorozatok** lapon határozza meg az előlegszámlák számsorozatát.

## <a name="create-a-vendor-advance-invoice"></a>Szállítói előlegszámla létrehozása
Manuálisan létrehozhat előlegszámlát. Másik lehetőségként az új előlegszámla egy meglévő beszerzési rendelésen alapulhat.

## <a name="manually-create-a-vendor-advance-invoice"></a>Szállítói előlegszámla manuális létrehozása
Kattintson a **Kötelezettségek** &gt; **Közös** &gt; **Előlegszámlák** &gt; **Minden előlegszámla** lehetőségre. Új előlegszámla létrehozásához a Műveleti ablaktáblán az **Előlegszámla** lapon kattintson az **Előlegszámla** elemre. Ezután adja meg a szükséges adatokat, majd kattintson a **Feladás** elemre az előleszámla feladásához. Az előlegszámla az alábbi állapotokkal rendelkezhet: **Megnyitva**, **Részben fizetve** vagy **Lezárt**. Manuálisan módosíthatja a feladott előlegszámla állapotát. Kattintson az **Állapot** lehetőségre, majd az **Előlegszámla állapotának módosítása** lapon az **Új állapot** mezőben válassza ki az előlegszámla új állapotát. **Megjegyzés:** Egy előlegszámla állapota bármikor módosítható. Zárt előlegszámlákat tranzakciókban nem lehet feldolgozni. **Megjegyzés:** Az áfa-specifikációk csak akkor másolódnak az előlegszámla soraiba, ha az **Adótípus** mező az **Áfakódok** lapon **Normál áfa** vagy **Csökkentett áfa** értékre van állítva. Ellenkező esetben a sor úgy kerül rá az előlegszámlára, mintha az áfa összege 0 (nulla) lenne.

## <a name="link-an-advance-invoice-to-a-purchase-order"></a>Előlegszámla csatolása beszerzési rendeléshez
Minden egyes előlegszámla egyszerre csak egy beszerzési rendeléshez csatolható. Egy meglévő előlegszámlát is hozzárendelhet egy másik beszerzési rendeléshez, feltéve, hogy nem kapcsolódnak előlegek az előlegszámlához. Előlegszámla beszerzési rendeléshez történő csatolásakor a **Minden előlegszámla** lapon válassza ki az előlegszámlát. A Műveleti ablaktáblán kattintson az **Előlegszámla** lehetőségre, majd a **Beszerzési rendelés** lehetőségre. Válassza ki az előlegszámlához csatolni kívánt beszerzési rendelést, és kattintson az **OK** gombra.

## <a name="create-a-vendor-advance-invoice-from-a-purchase-order"></a>Szállítói előlegszámla létrehozása beszerzési rendelés alapján
Hozzon létre egy beszerzési rendelést, vagy válasszon ki egy meglévő beszerzési rendelést. Kattintson a **Számla** lehetőségre, majd kattintson a **Létrehozás** &gt; **Előlegszámla** lehetőségre. Az **Előlegszámla létrehozása** lapon állítsa be a következő mezőket.

| Mező                                           | Leírás                                                                                                              |
|-------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| Százalék                                         | Adja meg a beszerzési rendelés előlegének százalékát.                                                         |
| Beszerzés frissítése                                 | A következő lehetőségek közül választhat. Az előlegszámla összegét a program a cikkek beszerzési rendelési összege alapján számítja ki. |
| Feladási profil az előlegnapló-bizonylathoz | Adja meg az előleghez tartozó feladási profilt.                                                                          |








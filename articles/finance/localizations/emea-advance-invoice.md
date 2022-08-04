---
title: Előlegszámlák Kelet-Európa számára
description: Ez a cikk a kelet-európai előlegszámlákról nyújt tájékoztatást. Az előlegszámla egy vevő vagy szállító számára létrehozott dokumentum. Azt az összeget tartalmazza, amelyet előre meg kell fizetni egy értékesítési rendelésre.
author: EvgenyPopovMBS
ms.date: 07/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustParameters
audience: Application User
ms.reviewer: kfend
ms.custom: 272643
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: epopov
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: bcf8424b311b595a114d3429fa7a3252e47e643d
ms.sourcegitcommit: 6b209919de39c15e0ebe4abc9cbcd30618f2af0b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/11/2022
ms.locfileid: "9135927"
---
# <a name="advance-invoices-for-eastern-europe"></a>Előlegszámlák Kelet-Európa számára

[!include [banner](../includes/banner.md)]

Ez a cikk a kelet-európai előlegszámlákról nyújt tájékoztatást. Az előlegszámla egy vevő vagy szállító számára létrehozott dokumentum. Azt az összeget tartalmazza, amelyet előre meg kell fizetni egy értékesítési rendelésre. 

> [!NOTE]
> Egy másik lehetőség az előlegszámla funkció használata. Microsoft Dynamics A 10.0.28-as pénzügyi verzió 365-ös verziójától ezt a funkciót a Kötelezettségek beállítási paraméterei főkönyv és áfa modulban lehet használni, **·** &gt; **·** &gt; **·** &gt; **·** **·** **és** az Előlegszámla gyorsgombon az Előlegszámla használata gombra kell beállítani az "Előlegszámla használata" beállítást.**·** További tájékoztatás: [Előlegszámlák és előlegek](../accounts-payable/prepayments-invoices-vs-prepayments.md).

Az előlegszámlák funkció a következő műveletek végrehajtását teszi lehetővé :

- Előlegszámlák kiállítása vevők számára, és ezen előlegszámlák állapotának követése (**Nyitott**, **Részben fizetve** vagy **Lezárt**).
- *Csak Lengyelország esetében:* előlegszámla-tranzakciók és áfatranzakciók feladása.
- Kifizetésinapló-sorok automatikus létrehozása előlegszámla alapján.
- A vevőktől kapott előlegek csatolása előlegszámlákhoz (az előleg feladása előtt vagy után).
- A feladott előlegek áfafeladásának módosítása (például előleg átalakítása kifizetéssé vagy a kifizetés átalakítása előleggé, vagy a feladási dátum, az adó mértéke vagy az összeg módosítása).
- *Csak Cseh Köztársaság esetében:* Adódokumentum létrehozása az áfamentes szállításhoz.

A cikk a következő szakaszokat tartalmazza:

- [Előlegszámlák Lengyelország számára](#advance-invoices-for-poland)
- [A Kinnlevőségek előlegszámlákhoz történő beállítása](#set-up-accounts-receivable-for-advance-invoices)
- [Vevői előlegszámla létrehozása](#create-a-customer-advance-invoice)
- [Előlegszámlák áfája](#vat-on-advance-invoices)
- [Előlegszámla csatolása értékesítési rendeléshez vagy szabadszöveges számlához](#link-an-advance-invoice-to-a-sales-order-or-a-free-text-invoice)
- [Vevői előlegszámla készítése értékesítési rendelésből](#create-a-customer-advance-invoice-from-a-sales-order)
- [Vevői előlegszámla létrehozása szabadszöveges számlából](#create-a-customer-advance-invoice-from-a-free-text-invoice)
- [Előlegszámla nyomtatása](#print-an-advance-invoice)
- [Fizetési javaslat létrehozása előlegszámlából](#create-a-payment-proposal-from-an-advance-invoice)
- [Előleg csatolása előlegszámlához](#link-a-prepayment-to-an-advance-invoice)
- [Előlegszámla csatolása előleghez](#link-an-advance-invoice-to-a-prepayment)
- [Előlegszámla jóváírása](#advance-invoice-credit-notes)
- [Cseh Köztársaság adódokumentumai](#tax-documents-for-the-czech-republic)
- [A Kötelezettségek előlegszámlákhoz történő beállítása](#set-up-accounts-payable-for-advance-invoices)
- [Szállítói előlegszámla létrehozása](#create-a-vendor-advance-invoice)
- [Az Előlegszámla és előleg kezelése funkció használata](#use-the-advance-invoice-and-prepayment-handling-functionality)
- [Cseh Köztársaság áfaösszegének megfordítása](#reversing-sales-tax-amounts-for-czech-republic)

## <a name="advance-invoices-for-poland"></a>Előlegszámlák Lengyelország számára

Az előlegeket is átvevő lengyel vállalatoknak az előlegről is ki kell állítaniuk számlát a vevőnek. Ezt az előlegszámlát a főkönyvben kell feladni, és az áfaadózási célok kötelező dokumentuma. Az előlegszámlán kiszámított adót jelenteni kell az adóhatóságnak.

Az áruk végleges eladása után az előlegszámlát meg kell adni az értékesítési számlán. Az értékesítés teljes összegének tartalmaznia kell az előlegeket.

Az értékesítési számla feladása esetén a kiegyenlített előlegszámla sztornírozva lesz. Az eredeti előlegszámla egy előlegszámla-ellenszámlával van kiegyenlítve.

## <a name="set-up-accounts-receivable-for-advance-invoices"></a>A Kinnlevőségek előlegszámlákhoz történő beállítása

1. Állítsa be **a következő mezőket** **·** **a Kinnlevőségek paraméterei lap Frissítések lapján, az Előlegszámla gyorslapon.**

    | Mező | Leírás |
    |-------|-------------|
    | Feladási profil | <p>*Csak Lengyelország esetében:* Válassza ki az előleg számlázásakor használt feladási profilt.</p><p>**Fontos:** Csehország és Magyarország esetében a program az előlegszámlákat nem könyvelési és adóbizonylatokként kezeli, és nem a főkönyvbe adja fel őket. Emiatt ezeknek az országoknak a esetében üresen kell hagynia ezt a mezőt, hogy megakadályozza az előlegszámlák főkönyvbe való feladását.</p> |
    | Ellenszámla | Válassza ki az ellenszámlát. |
    | Áfacsoport | Válassza ki, hogy melyik áfacsoportot kell használni, amikor az áfát az előlegszámlázáshoz számítja ki. |
    | Helyesbítőként sztornírozás | Akkor jelölje be ezt a jelölőnégyzetet, ha az előlegszámla visszaszét adása javításnak tekinthető. |
    | Sztornírozás számlanapon | Akkor jelölje be ezt a jelölőnégyzetet, ha a számla feladási dátumán vissza kell sztornírozni az előleget. |

1. A Fizetés **gyors** területen állítsa be a következő mezőket.

    | Mező | Leírás |
    |-------|-------------|
    | Több előlegfizetési dátum | Válassza az **Elfogadás**, **a Figyelmeztetés** vagy a **Hiba lehetőséget**. |
    | Dátumeltérés | Válassza az **Elfogadás**, **a Figyelmeztetés** vagy a **Hiba lehetőséget**. |
    | Összegeltérés | Válassza az **Elfogadás**, **a Figyelmeztetés** vagy a **Hiba lehetőséget**. |
    | Kapcsolás feladott előlegszámlához | Válassza az **Elfogadás**, **a Figyelmeztetés** vagy a **Hiba lehetőséget**. |
    | (CZE), (POL) Előleg kezelése | Válassza a **Speciális** lehetőséget. |

1. A **Számsorozatok** lapon állítsa be az alábbi hivatkozások számsorozatkódját:

    - Adóbizonylat
    - Adójóváírás
    - Előlegszámla
    - Előlegszámla-jóváírás
    - Előlegszámla sztornírozása
    - Előlegszámla bizonylata
    - Előlegszámla-jóváírás bizonylata
    - Előlegszámla sztornírozási bizonylata

## <a name="create-a-customer-advance-invoice"></a>Vevői előlegszámla létrehozása

1. Ugrás a **Kinnlevőségek** &gt; **közös** &gt; **előlegszámlákhoz** &gt; **– Minden előlegszámla**
1. A műveletpanel Előlegszámla lapján **válassza** **ki az Előlegszámla** lehetőséget előlegszámla létrehozásához.
1. Írja be a szükséges adatokat, majd a **Post** lehetőséget választva adja fel az előlegszámlát.

Az előlegszámla az alábbi állapotokkal rendelkezhet: **Megnyitva**, **Részben fizetve** vagy **Lezárt**. Manuálisan módosíthatja a feladott előlegszámla állapotát. Válassza **az Állapot** lehetőséget, majd **az** **Előlegszámla állapotának módosítása lapon az Új állapot** mezőben válassza ki az előlegszámla új állapotát.

> [!NOTE]
> Az előlegszámla állapota bármikor megváltoztatható. Zárt előlegszámlákat tranzakciókban nem lehet feldolgozni.
> 
> *Csak Lengyelország esetében:* Előlegszámla-tranzakciók akkor jönnek létre, ha beállít egy feladási profilt az előlegszámlákhoz a Kinnlevőségek paraméterei között. A feladott tranzakciók megtekintéséhez válassza a Bizonylat **lehetőséget** az Előlegszámla **lapon**.

## <a name="vat-on-advance-invoices"></a>Előlegszámlák áfája

A vállalatoknak kötelező áfát figyelembe venniük a vevőktől kapott előlegekre annak ellenére, hogy az értékesítés még nem történt meg. Az előleg áfájának feladásához hozzáadhat egy sort, amely tartalmazza előlegszámla áfa-specifikációit. Az előlegszámlának több sora is lehet, és ezek a sorok az értékesítési rendelés soraiból származó áfaadatokat tartalmazhatnak. Így az előlegek áfát szigorúan az értékesítésirendelés-sorokkal összhangban lehet feladódni.

> [!NOTE]
> Az áfa meghatározásai csak akkor másolhatók az előlegszámla **soraiba** **·** **, ha az Áfakódok lap Adótípus mezőjének beállítása Normál áfa** **vagy Csökkentett áfa.** Ellenkező esetben úgy másolja őket a program az előlegszámla soraiba, mintha az áfa összege nulla lenne.

## <a name="link-an-advance-invoice-to-a-sales-order-or-a-free-text-invoice"></a>Előlegszámla csatolása értékesítési rendeléshez vagy szabadszöveges számlához

Minden előlegszámla egyszerre csak egy értékesítési rendeléshez vagy szabadszöveges számlához kapcsolható. Egy meglévő előlegszámlát is hozzárendelhet egy másik értékesítési rendeléshez vagy egy szabadszöveges számlához, feltéve, hogy nem kapcsolódnak előlegek az előlegszámlához.

Az alábbi lépésekkel lehet előlegszámlát értékesítési rendeléshez rendelni.

1. A Minden **előlegszámla lapon** jelölje ki az előlegszámlát.
1. Válassza ki a műveletpanelen az **Előlegszámla**, majd az Értékesítési **rendelés lehetőséget**.
1. Válassza ki azt az értékesítési rendelést, amely az előlegszámlához csatolva van, majd válassza az **OK gombra.**

A következő lépésekkel lehet előlegszámlát szabadszöveges számlához csatolni.

1. A Minden **előlegszámla lapon** jelölje ki az előlegszámlát.
1. A műveletpanelen válassza ki az **Előlegszámla**, majd a **Szabadszöveges számla lehetőséget**.
1. Válassza ki az előlegszámlához csatolni kívánt szabadszöveges számlát, majd válassza az **OK gombra**.

## <a name="create-a-customer-advance-invoice-from-a-sales-order"></a>Vevői előlegszámla készítése értékesítési rendelésből

1. Hozzon létre értékesítési rendelést, vagy válasszon ki egy létező értékesítési rendelést.
1. Válassza ki a **Számlát**, majd válassza **az**&gt; Előlegszámla **létrehozása lehetőséget**.
1. Az Előlegszámla **létrehozása** lapon állítsa be a következő mezőket.

    | Mező | Leírás |
    |-------|-------------|
    | Százalék | Adja meg az értékesítési rendelés előlegének százalékát. |
    | Ellenszámla | Az előlegszámlázáshoz használt alapértelmezett ellenszámla kiválasztása. |
    | Rendelés frissítése | Válassza **ki az Összes**, **a Szállítás most**, a **Kivetve**, **a Szállítólevél** vagy a **Ki nem választott mennyiséget és a nem raktárkészleten szereplő termékeket**. A program a cikkek értékesítési rendelési összegei alapján számítja ki az előlegszámla összegét. |
    | Áfa feladása | Adja meg, hogy fel akarja-e adni az áfát az előzetes számla feladása során. |
    | Áfadátum feladása | Adja meg az áfa feladási dátumát. |
    | Feladási profil az előlegnapló-bizonylathoz | Adja meg az előleghez tartozó feladási profilt. |
    | Adódokumentum létrehozása | Adja meg, hogy létrejöjjön-e adóbizonylat. |

> [!NOTE]
> *Csak Lengyelország esetében:* Előlegszámla-tranzakciók akkor jönnek létre, ha beállít egy feladási profilt az előlegszámlákhoz a Kinnlevőségek paraméterei között.

## <a name="create-a-customer-advance-invoice-from-a-free-text-invoice"></a>Vevői előlegszámla létrehozása szabadszöveges számlából

1. Hozzon létre szabadszöveges számlát, vagy válasszon ki egy létező szabadszöveges számlát.
1. Válassza az Előlegszámla **lehetőséget** **a Számla lap Új** **szakaszában**.

    Most létrehozhat egy új előlegszámlát, amely a szabadszöveges számlához lesz kapcsolva.

> [!NOTE]
> *Csak Lengyelország esetében:* Előlegszámla-tranzakciók akkor jönnek létre, ha beállít egy feladási profilt az előlegszámlákhoz a Kinnlevőségek paraméterei között.

## <a name="print-an-advance-invoice"></a>Előlegszámla nyomtatása

- Az Előlegszámla **lapon** válassza a Nyomtatás **lehetőséget**. 

*Csak Lengyelország esetében:* A pénzügyi bizonylathoz előlegszámla-bizonylatot nyomtathat. Válasszon ki egy beállítást az előlegszámla feladása során.

*Csak Lengyelország esetében:* Az értékesítési számlák és a szabadszöveges számladokumentumok elrendezésének a kiegyenlített előlegszámlával kapcsolatban a következő adatokat kell tartalmaznia:

- Előlegszámla száma
- Előlegszámla dátuma
- Áfa nélküli összeg, áfa összege, összeg áfával és pénznem
- Adókulcs

Az áfaösszegek összegzésének tartalmaznia kell az Előlegszámla **adója mezőt**. Az esedékes összeget csökkenteni kell az előlegszámla összegével.

## <a name="create-a-payment-proposal-from-an-advance-invoice"></a>Fizetési javaslat létrehozása előlegszámlából

Új kifizetési napló létrehozásakor előlegszámla alapján automatikusan létrehozhat kifizetésinapló-sorokat.

1. A Kifizetési **napló lapon** válassza az **Előlegnapló bizonylata** beállítást, majd válassza a Sorok **lehetőséget**.
1. Válassza ki a **Naplóbizonylat** lapon **·** &gt; **az** előlegszámláról származó fizetési javaslat kifizetési javaslatát, hogy az előlegszámlákból kifizetési javaslatot hozzon létre. A feladási profil és az áfacsoportok adatai az előlegszámlából származnak.

> [!NOTE]
> Az **előlegszámlákhoz** **·** **automatikusan új előlegek lesznek kapcsolva, ha az Előlegek csatolása és az Állapot módosítása beállítás van megjelölve az Előlegjavaslat létrehozása előlegszámlák** alapján lapon.

## <a name="link-a-prepayment-to-an-advance-invoice"></a>Előleg csatolása előlegszámlához

Az előleg kifizetési naplóból származó előlegszámlához való kapcsolása a következő lépésekkel követhető.

- Nyissa meg a kifizetési naplót, válassza ki az előleget mutató sort, **majd válassza a Függvények** &gt; **csatolása előlegszámlákhoz lehetőséget.**

Az előlegnek a Vevői tranzakciók lapon **található** előlegszámlához való kapcsolása a következő lépésekkel követhető.

1. Az összes **vevői vevői** &gt; **tranzakció kijelölése** &gt; **·**
1. Válassza ki a kifizetési naplót, válassza ki azt a sort, amely tartalmazza az előleget, **majd válassza a Függvények** &gt; **csatolása előlegszámlákhoz lehetőséget.**

## <a name="link-an-advance-invoice-to-a-prepayment"></a>Előlegszámla csatolása előleghez

A következő lépésekkel lehet előlegszámlát előlegsorhoz hozzárendelni.

1. A Minden **előlegszámla lapon** jelölje ki az előlegszámlát.
1. A műveletpanelen válassza ki az **Előlegszámla**, majd az **Előleg lehetőséget**.
1. Válassza ki az előlegszámlához csatolni kívánt előlegsort, majd válassza az **OK gombra.**

## <a name="advance-invoice-credit-notes"></a>Előlegszámla jóváírása

- *Csak Lengyelország esetében:* Előlegszámlát úgy érvénytelenhet, hogy létrehoz egy előlegszámlához tartozó jóváírást, és fel tudja adni a főkönyvbe.
- Jóváírás létrehozásához létrehozhat új előlegszámlát, és kiválaszthatja a **Jóváírást**. Ezután kiválaszthatja az érvénytelenítendő előlegszámlát.
- Jóváírást előlegszámla kiegyenlítését lehetővé tő értékesítési számlához is létrehozhat.
- Az előlegszámla-jóváírás elrendezése a korrekció előtti és utáni sorok adatait tartalmazza.
- *Csak Lengyelország esetében:* az előlegszámla jóváírásának feladása után létrejönnek a főkönyvi tranzakciók.

## <a name="tax-documents-for-the-czech-republic"></a>Cseh Köztársaság adódokumentumai

A Cseh Köztársaság esetében létrehozhat egy olyan adóbizonylatot, amely az áfaköteles szállításra vonatkozó előlegadatokon alapul. Az adódokumentumot az előlegoldalon hozhatja létre, **hozhatja létre és hozhatja létre, illetve nyomtathatja ki úgy, hogy kiválasztja a Funkciók** &gt; **adódokumentumát**, majd kiválasztja az egyik lehetőséget. Az adóbizonylat tartalmazza az áfa részletes adatait, például az áfa típusát és értékét, valamint annak alapját a könyvelési pénznemben és a tranzakció pénznemében.

## <a name="set-up-accounts-payable-for-advance-invoices"></a>A Kötelezettségek előlegszámlákhoz történő beállítása

- A **Kötelezettségek paraméterei** lapon a **Számsorozatok** lapon határozza meg az előlegszámlák számsorozatát.

## <a name="create-a-vendor-advance-invoice"></a>Szállítói előlegszámla létrehozása

Manuálisan létrehozhat előlegszámlát. Másik lehetőségként az új előlegszámla egy meglévő beszerzési rendelésen alapulhat.

### <a name="manually-create-a-vendor-advance-invoice"></a>Szállítói előlegszámla manuális létrehozása

1. Ugrás a **Kötelezettségek közös** &gt; **·** &gt; **előlegszámlákhoz** &gt; **Minden előlegszámla**
1. A műveletpanel Előlegszámla lapján **válassza** **ki az Előlegszámla** lehetőséget előlegszámla létrehozásához.
1. Írja be a szükséges adatokat, majd a **Post** lehetőséget választva adja fel az előlegszámlát.

Az előlegszámla az alábbi állapotokkal rendelkezhet: **Megnyitva**, **Részben fizetve** vagy **Lezárt**. Manuálisan módosíthatja a feladott előlegszámla állapotát. Válassza **az Állapot** lehetőséget, majd **az** **Előlegszámla állapotának módosítása lapon az Új állapot** mezőben válassza ki az előlegszámla új állapotát.

> [!NOTE]
> Az előlegszámla állapota bármikor megváltoztatható. Zárt előlegszámlákat tranzakciókban nem lehet feldolgozni.
>
> Az áfa meghatározásai csak akkor másolhatók az előlegszámla **soraiba** **·** **, ha az Áfakódok lap Adótípus mezőjének beállítása Normál áfa** **vagy Csökkentett áfa.** Ellenkező esetben úgy másolja őket a program az előlegszámla soraiba, mintha az áfa összege nulla lenne.

### <a name="link-an-advance-invoice-to-a-purchase-order"></a>Előlegszámla csatolása beszerzési rendeléshez

Minden előlegszámla egyszerre csak egy beszerzési rendeléshez kapcsolható. Egy meglévő előlegszámlát is hozzárendelhet egy másik beszerzési rendeléshez, feltéve, hogy nem kapcsolódnak előlegek az előlegszámlához.

A következő lépésekkel lehet előlegszámlát beszerzési rendeléshez rendelni.

1. A Minden **előlegszámla lapon** jelölje ki az előlegszámlát.
1. Válassza ki a műveletpanelen az **Előlegszámla**, majd a Beszerzési **rendelés lehetőséget**.
1. Válassza ki azt a beszerzési rendelést, amely az előlegszámlához csatolva van, majd válassza az **OK gombra.**

### <a name="create-a-vendor-advance-invoice-from-a-purchase-order"></a>Szállítói előlegszámla létrehozása beszerzési rendelés alapján

1. Hozzon létre egy beszerzési rendelést, vagy válasszon ki egy meglévő beszerzési rendelést.
1. Válassza ki a **Számlát**, majd válassza **az**&gt; Előlegszámla **létrehozása lehetőséget**.
1. Az Előlegszámla **létrehozása** lapon állítsa be a következő mezőket.

    | Mező | Leírás |
    |-------|-------------|
    | Százalék | Adja meg a beszerzési rendelés előlegének százalékát. |
    | Beszerzés frissítése | Válasszon egy lehetőséget. A program a cikkek beszerzési rendelési összege alapján számítja ki az előlegszámla összegét. |
    | Feladási profil az előlegnapló-bizonylathoz | Adja meg az előleghez tartozó feladási profilt. |

## <a name="use-the-advance-invoice-and-prepayment-handling-functionality"></a>Az Előlegszámla és előleg kezelése funkció használata

Az üzleti folyamat **során** **használhatja** az Előlegszámla és előleg kezelése funkciót. Egy példa:

1. A felhasználó előlegfizetésért előleget küld el a vevőnek áfával. Az előlegszámla nincs feladva a főkönyvbe.
2. A felhasználó áfa nélkül hozza létre és hozza létre az előleget.
3. A felhasználó létrehoz egy előlegkezelést, és az előlegszámlához viszonyja azt. A felhasználó ezt követően felszámláz az előlegkezelést, és létrehozza az adódokumentumot. A rendszer az áfát a főkönyvbe feladása után az előleghez viszonyja.

> [!NOTE]
> Törölje a feladási profil mező **értékét** **az Előlegszámla gyorslap Kinnlevőségek** **paramétereinek** Frissítése lapján.**·** Az előlegszámla létrehozásakor állítsa Az adó post beállítását **Igen beállításra** **.**

Az előlegkezelés létrehozásához és előlegszámlához csatolása a következő lépéseket kell követni.

1. Menjen a Kinnlevőségek **– Vevőkhöz** \> **·**, és keresse meg és nyissa meg a vevőrekordot.
2. A műveletpanelen válassza ki a Vevői **tranzakciók** \> **lehetőséget**, válassza ki az előlegtranzakciót, majd válassza **az Előleg kezelése lehetőséget.**
3. Állítsa az **Átalakítás fizetési módba** beállítást Nem **beállításra**.
4. Válassza ki **az előlegszámlát**, ha az előlegkezelést az előlegszámlához csatolja. A rendszer automatikusan létrehozza az áfasorokat az előlegszámlából.
5. Az előleg kezelésének feladása. A rendszer automatikusan létrehozza az előleg áfatranzakcióit.

## <a name="reversing-sales-tax-amounts-for-czech-republic"></a>Cseh Köztársaság áfaösszegének megfordítása

Az áfaösszegek **előlegkezelési funkción alapuló kézi definiálása érdekében engedélyezze a manuális** beviteles áfaösszegek funkciót (Csehország). A funkciók engedélyezéséről a Funkciókezelés [áttekintése nyújt tájékoztatást](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

> [!NOTE]
> Ez a funkció csak a Kötelezettségek esetében érhető el.

Ha egy kifizetéssel szemben egy számlatranzakciót jelöl meg kiegyenlítésre, **·** **a sztornírozási áfaösszegeket a Tranzakció kiegyenlítése lap Sztornírozási áfaösszegek lapján frissítheti.** Ha szükséges, az adóösszegeket frissítheti a kiegyenlítés **adóösszege mezőben**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

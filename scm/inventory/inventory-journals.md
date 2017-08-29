---
title: "Készletnaplók"
description: "Ez a cikk leírja, hogyan kell alkalmazni a készletnaplót különböző típusú fizikai készlet tranzakciók közzétételéhez."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalBOM, InventJournalCount, InventJournalCountTag, InventJournalLossProfit, InventJournalMovement, InventJournalTransfer, WMSJournalTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 51631
ms.assetid: 3fedeaaf-502f-483c-93d2-ab266828189e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: d549f38b9278eed222a1318c51962b248149c569
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---

# <a name="inventory-journals"></a>Készletnaplók

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


Ez a cikk leírja, hogyan kell alkalmazni a készletnaplót különböző típusú fizikai készlet tranzakciók közzétételéhez. 

A Microsoft Dynamics 365 for Finance and Operations rendszerben a készletnaplókkal különböző típusú készlettranzakciók adhatók fel, például kiadások és bevételek feladása, készletmozgások, anyagjegyzékek (BOM) létrehozása és a fizikai készlet egyeztetése. Ezek a készletnaplók hasonló módon használhatók, de különböző típusúak.

## <a name="types-of-inventory-journals"></a>Készletnaplók típusai
Az alábbi készletnaplótípusok állnak rendelkezésre:

-   Áthelyezés
-   Készlethelyesbítés
-   Áthelyezés
-   Anyagjegyzék
-   Cikk érkezése
-   Termelések beérkezése
-   Számlálás
-   Címkeleltár

### <a name="movement"></a>Áthelyezés

Amikor készletmozgatási naplót használ, akkor egy cikkhez megadhat költséget a készlet hozzáadásakor, de manuálisan kell el kell különítenie további költséget egy külön főkönyvi számlára, ahol meg kell adni egy főkönyvi kiegyenlítési számlát a napló létrehozásakor. Ez a készletnapló típus hasznos, ha költségként akar elszámolni egy cikket egy másik részlegnek, vagy ha cikkeket akar eltávolítani a kiadási célú készletből.

### <a name="inventory-adjustment"></a>Készlethelyesbítés

Ha készlethelyesbítési naplót használ, akkor hozzárendelhet költséget egy cikket amikor hozzáadja a készletet. A további költséget a program automatikusan feladja a cikkcsoport feladási profilban megadott beállítások alapján meghatározott főkönyvi számlára. Ezzel a készletnapló típussal frissítheti a nyereségeket és veszteségeket a készletmennyiségekben, ha egy cikknek tartania kell az alapértelmezett főkönyvi ellenszámláját. Az készlethelyesbítési napló feladásakor a rendszer egy készletbevételezést vagy készletkiadást ad fel, módosítja a készletértéket, és főkönyvi tranzakciókat hoz létre.

### <a name="transfer"></a>Áthelyezés

Használhat transzfernaplókat cikkek átvitelére tarolási helyszínek, kötegek vagy termékváltozat között, bármilyen költségkövetkezmény hozzárendelése nélkül. Például cikkeket vihet át egyik raktárból a másikba ugyanazon a vállalaton belül. Ha transzfernaplót használ akkor meg kell adnia a „honnan” és „hová” készletdimenziókat (pl. Hely és raktár). Az meghatározott aktuális készlet megjelenítésének készletdimenziója ennek megfelelően változik. A készlettranzakciókban azonnal látható az anyagmozgás. Átmozgatás közben nincs készletkövetés. Ha tranzitraktár készletet kell követni, használjon inkább az átmozgatási rendelést. Ha transzfernaplót ad fel, akkor két készlettranzakció jön létre az egyes naplósorokhoz:

-   Egy készletkiadás a „kezdő” helyen
-   Egy készlet bevételezés a „cél” helyen

### <a name="bom"></a>Anyagjegyzék

Ha egy anyagjegyzéket készként jelent, akkor létrehozhatja az anyagjegyzék-naplót. Az anyagjegyzéknaplóval közvetlenül tudja feladni az anyagjegyzéket. Ez a feladás készlet bevételezést hoz létre a termékről, egy társított anyagjegyzékkel és egy készletkiadással a termékekről, amelyek az anyagjegyzékben vannak. Ez a készletnapló típus hasznos egyszerű vagy nagy volumenű termelési esetekben, ahol nincs szükség utakra.

### <a name="item-arrival"></a>Cikk érkezése

A cikkérkezési napló segítségével regisztrálhatja a cikkek bevételezését (például beszerzési rendelésből). Egy cikkérkezési napló létrehozható az érkezési kezelés részeként **Érkeztetés áttekintése** oldalon, vagy manuálisan létrehozhat egy naplóbejegyzést a **Cikk érkeztetés** oldalon. Ha engedélyezi a cikknaplónévnek a kitárolási helyek ellenőrzését, akkor a Dynamics 365 for Finance and Operations rendszer egy helyet keres a beérkezett cikkeknek és ha van hely, akkor célhelyet hoz létre a beérkező cikkeknek.

### <a name="production-input"></a>Termelések beérkezése

A termelési bemenet naplók úgy működnek, mint a cikkérkezési naplók, de termelési rendelésekhez használatosak.

### <a name="counting"></a>Számlálás

Leltárnaplók segítségével javítsa ki az aktuális készleteket amelyek cikkekhez vagy cikkcsoportokhoz vannak regisztrálva és adja fel az aktuális fizikai mennyiséget, így elvégezheti a különbségek egyeztetetéséhez szükséges kiigazítást. Társíthat leltár irányelveket leltárcsoportokkal, így könnyebb eltérő tulajdonságú cikkeket csoportosítani, emiatt a cikkek hozzáadhatók a leltárnaplóhoz. Például beállíthat leltárcsoportokat, olyan cikkek leltárazásához, amelyek adott gyakorisággal rendelkeznek, vagy ha a készlet egy adott szintre csökken. További információért a leltárcsoportok meghatározásával kapcsolatban, lásd [Leltárazási folyamatok meghatározása (Feladat-útmutató)](/dynamics365/unified-operations/supply-chain/inventory/tasks/define-inventory-counting-processes).

### <a name="tag-counting"></a>Címkeleltár

A címke leltárnaplók segítségével egy számozott címke rendelhető hozzá egy leltáradaghoz. A címkének tartalmaznia kell címkeszámot, cikkszámot és cikkmennyiséget. Annak érdekében, hogy a címkét csak egyszer használják fel, és hogy az összes címke felhasználásra kerüljön minden cikkszámnak egyedi címkékkel kell rendelkeznie, amelyben megtalálható a saját számsorozata. Az egyes címkékhez három állapot-érték állítható be:

-   **Felhasználva** – A címkén szereplő cikkszám leltárba van véve.
-   **Érvénytelenítve** – A címkén szereplő cikkszám érvénytelen.
-   **Hiányzó** – A címkén szereplő cikkszám hiányzik.

A címkeleltárnapló feladásakor a címkeleltárnapló-sorok alapján új leltárnapló jön létre. További információért a címkeleltárral kapcsolatban, lásd [Készlet címkeleltár](inventory-tag-counting.md).

## <a name="working-with-journals"></a>Naplók használata
Egy naplósorhoz egyszerre csak egy felhasználó férhet hozzá. Ha egyszerre több felhasználónak kell hozzáférnie a naplókhoz hogy sorokat készítsen, akkor a felhasználóknak ki kell választaniuk az adott pillanatban éppen nem használt naplókat az információk felülírásának elkerülése érdekében. Olyan helyzetekben, ahol több részleg használja ugyanazt a naplótípust hasznos, ha több naplónév van (pl. részlegenként egy). Hasznos lehet a naplók elosztása is, hogy minden feladási funkció a saját készletnaplójába kerüljön. Készlettranzakciókhoz társított feladási funkciók esetén hozzon létre egy naplót az ismétlődő készlethelyesbítésekhez, és egy másikat a készletleltározáshoz.

## <a name="posting-journal-lines"></a>Naplósorok feladása
Feladhat naplósorokat, amelyeket bármikor létrehozhat, amíg nem rögzített egy cikket további tranzakciókból. A naplóba beírt adatok mindig megmaradnak a naplóban, még akkor is, ha a sorok feladása nélkül zárja be a naplót.





---
title: Készletnaplók
description: Ez a témakör leírja, hogyan kell alkalmazni a készletnaplót különböző típusú fizikai készlet tranzakciók közzétételéhez.
author: perlynne
manager: AnnBe
ms.date: 04/05/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalBOM, InventJournalCount, InventJournalCountTag, InventJournalLossProfit, InventJournalMovement, InventJournalTransfer, WMSJournalTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 51631
ms.assetid: 3fedeaaf-502f-483c-93d2-ab266828189e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1c4a2696b015611f4430ad5dfa1c61c1c4f913a9
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570794"
---
# <a name="inventory-journals"></a>Készletnaplók

[!include [banner](../includes/banner.md)]

Ez a témakör leírja, hogyan kell alkalmazni a készletnaplót különböző típusú fizikai készlet tranzakciók közzétételéhez.

A Supply Chain Management rendszerben a készletnaplókkal különböző típusú készlettranzakciók adhatók fel, például kiadások és bevételek feladása, készletmozgások, anyagjegyzékek (BOM) létrehozása és a fizikai készlet egyeztetése. Ezek a készletnaplók hasonló módon használhatók, de különböző típusúak.

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

Amikor készletmozgatási naplót használ, akkor egy cikkhez megadhat költséget a készlet hozzáadásakor, de manuálisan kell el kell különítenie további költséget egy külön főkönyvi számlára, ahol meg kell adni egy főkönyvi kiegyenlítési számlát a napló létrehozásakor. Ez a készletnapló-típus akkor hasznos, ha szeretné felülírni az alapértelmezett feladási számlákat.

### <a name="inventory-adjustment"></a>Készlethelyesbítés

Ha készlethelyesbítési naplót használ, akkor hozzárendelhet költséget egy cikket amikor hozzáadja a készletet. A további költséget a program automatikusan feladja a cikkcsoport feladási profilban megadott beállítások alapján meghatározott főkönyvi számlára. Ezzel a készletnapló típussal frissítheti a nyereségeket és veszteségeket a készletmennyiségekben, ha egy cikknek tartania kell az alapértelmezett főkönyvi ellenszámláját. Az készlethelyesbítési napló feladásakor a rendszer egy készletbevételezést vagy készletkiadást ad fel, módosítja a készletértéket, és főkönyvi tranzakciókat hoz létre.

### <a name="transfer"></a>Áthelyezés

Használhat transzfernaplókat cikkek átvitelére tarolási helyszínek, kötegek vagy termékváltozat között, bármilyen költségkövetkezmény hozzárendelése nélkül. Például cikkeket vihet át egyik raktárból a másikba ugyanazon a vállalaton belül. Ha transzfernaplót használ akkor meg kell adnia a „honnan” és „hová” készletdimenziókat (pl. Hely és raktár). Az meghatározott aktuális készlet megjelenítésének készletdimenziója ennek megfelelően változik. A készlettranzakciókban azonnal látható az anyagmozgás. Átmozgatás közben nincs készletkövetés. Ha tranzitraktár készletet kell követni, használjon inkább az átmozgatási rendelést. Ha transzfernaplót ad fel, akkor két készlettranzakció jön létre az egyes naplósorokhoz:

-   Egy készletkiadás a „kezdő” helyen.
-   Egy készlet bevételezés a „cél” helyen.

### <a name="bom"></a>Anyagjegyzék

Ha egy anyagjegyzéket készként jelent, akkor létrehozhatja az anyagjegyzék-naplót. Az anyagjegyzéknaplóval közvetlenül tudja feladni az anyagjegyzéket. Ez a feladás készlet bevételezést hoz létre a termékről, egy társított anyagjegyzékkel és egy készletkiadással a termékekről, amelyek az anyagjegyzékben vannak. Ez a készletnapló típus hasznos egyszerű vagy nagy volumenű termelési esetekben, ahol nincs szükség utakra.

### <a name="item-arrival"></a>Cikk érkezése

A cikkérkezési napló segítségével regisztrálhatja a cikkek bevételezését (például beszerzési rendelésből). Egy cikkérkezési napló létrehozható az érkezési kezelés részeként **Érkeztetés áttekintése** oldalon, vagy manuálisan létrehozhat egy naplóbejegyzést a **Cikk érkeztetés** oldalon. Ha engedélyezi a cikknaplónévnek a kitárolási helyek ellenőrzését, akkor a Supply Chain Management rendszer egy helyet keres a beérkezett cikkeknek és ha van hely, akkor célhelyet hoz létre a beérkező cikkeknek.

### <a name="production-input"></a>Termelések beérkezése

A termelési bemenet naplók úgy működnek, mint a cikkérkezési naplók, de termelési rendelésekhez használatosak.

### <a name="counting"></a>Számlálás

Leltárnaplók segítségével javítsa ki az aktuális készleteket amelyek cikkekhez vagy cikkcsoportokhoz vannak regisztrálva, és adja fel az aktuális fizikai mennyiséget, így elvégezheti a különbségek egyeztetetéséhez szükséges kiigazítást. Társíthat leltár irányelveket leltárcsoportokkal, így könnyebb eltérő tulajdonságú cikkeket csoportosítani, emiatt a cikkek hozzáadhatók a leltárnaplóhoz. Például beállíthat leltárcsoportokat, olyan cikkek leltárazásához, amelyek adott gyakorisággal rendelkeznek, vagy ha a készlet egy adott szintre csökken. További információért a leltárcsoportok meghatározásával kapcsolatban, lásd [Leltárazási folyamatok meghatározása (Feladat-útmutató)](tasks/define-inventory-counting-processes.md).

### <a name="tag-counting"></a>Címkeleltár

A címke leltárnaplók segítségével egy számozott címke rendelhető hozzá egy leltáradaghoz. A címkének tartalmaznia kell címkeszámot, cikkszámot és cikkmennyiséget. Annak érdekében, hogy a címkét csak egyszer használják fel, és hogy az összes címke felhasználásra kerüljön, minden cikkszámnak egyedi címkékkel kell rendelkeznie, amelyben megtalálható a saját számsorozata. Az egyes címkékhez három állapot-érték állítható be:

-   **Felhasználva** – A címkén szereplő cikkszám leltárba van véve.
-   **Érvénytelenítve** – A címkén szereplő cikkszám érvénytelen.
-   **Hiányzó** – A címkén szereplő cikkszám hiányzik.

A címkeleltárnapló feladásakor a címkeleltárnapló-sorok alapján új leltárnapló jön létre. További információért a címkeleltárral kapcsolatban, lásd [Készlet címkeleltár](inventory-tag-counting.md).

## <a name="working-with-journals"></a>Naplók használata
Egy naplósorhoz egyszerre csak egy felhasználó férhet hozzá. Ha egyszerre több felhasználónak kell hozzáférnie a naplókhoz hogy sorokat készítsen, akkor a felhasználóknak ki kell választaniuk az adott pillanatban éppen nem használt naplókat az információk felülírásának elkerülése érdekében. Olyan helyzetekben, ahol több részleg használja ugyanazt a naplótípust hasznos, ha több naplónév van (pl. részlegenként egy). Hasznos lehet a naplók elosztása is, hogy minden feladási funkció a saját készletnaplójába kerüljön. Készlettranzakciókhoz társított feladási funkciók esetén hozzon létre egy naplót az ismétlődő készlethelyesbítésekhez, és egy másikat a készletleltározáshoz.

## <a name="posting-journal-lines"></a>Naplósorok feladása
Feladhat naplósorokat, amelyeket bármikor létrehozhat, amíg nem rögzített egy cikket további tranzakciókból. A naplóba beírt adatok mindig megmaradnak a naplóban, még akkor is, ha a sorok feladása nélkül zárja be a naplót.

## <a name="data-entity-support-for-inventory-journals"></a>Adatentitás-támogatás készletnaplókhoz

Az adatentitások a következő típusú integrációs forgatókönyveket támogatják:
-    Párhuzamos szolgáltatás (OData)
-  Aszinkron integráció

További tudnivalókért lásd: [Adatentitások](../../dev-itpro/data-entities/data-entities.md).

> [!NOTE]
> Nem minden készletnaplók OData-kompatibilis, ezért nem használható az Excel adatcsatlakozó az adatok közzétételéhez, frissítése, valamint a Supply Chain Management rendszerbe való visszaimportálásához. 

A naplóentitások közötti másik különbség az összetett entitások használhatósága, amelyek a fejléc és a sor adatait is tartalmazzák. Az összetett entitások jelenleg a következőkre használhatók:
-   Készlethelyesbítési napló
-   Készletmozgási napló

Ez a két készletnapló csak a *Készlet inicializálása* helyzetet támogatja az adatkezelési importálási projekt részeként:
-  Ha a napló fejlécének száma nincs megadva, de egy számsorozat van megadva a naplótípushoz, az importálási feladat automatikusan létrehozza a naplófejléceket 1000 soronként. Ha például 2020 sort importál, a következő három naplófejlécet kapjuk:
    -  1. fejléc: 1000 sort fog tartalmazni.
    -  2. fejléc: 1000 sort fog tartalmazni.
    -  3. fejléc: 20 sort fog tartalmazni.
-  A feltételezés az, hogy készletdimenziónként léteznek egyedi soradatok, amely lehetnek termék, tárolási és nyomon követési dimenzió. Ezért nem lehet importálni a naplósorokat, ahol csak a dátummező tér el a sorokban ugyanabban az importálási projektben.

## <a name="additional-resources"></a>További erőforrások

[Adatentitások](../../dev-itpro/data-entities/data-entities.md)

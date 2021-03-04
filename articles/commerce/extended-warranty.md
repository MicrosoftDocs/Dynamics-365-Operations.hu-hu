---
title: Kiterjesztett garancia létrehozása és konfigurálása
description: Ez a témakör a kiterjesztett garanciával foglalkozik, és bemutatja, hogy hogyan lehet ezeket létrehozni és konfigurálni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: sijoshi
manager: annbe
ms.date: 06/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: sijoshi
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: a875343d9b93f5ebf2c2992fba8b2f182310461e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412753"
---
# <a name="create-and-configure-extended-warranties"></a>Kiterjesztett garancia létrehozása és konfigurálása

[!include [banner](includes/banner.md)]

Ez a témakör a kiterjesztett garanciával foglalkozik, és bemutatja, hogy hogyan lehet ezeket létrehozni és konfigurálni a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A vevők egyre gyakrabban választják ki a kiterjesztett garanciát és szolgáltatásokat, amikor termékeket vásárolnak, különösen az olyan termékek esetében, amelyeket magasabb áron értékesítenek (például telefonok és számítógépek). Ha kiterjesztett garanciát ajánlanak fel a vásárlás során, azzal kiskereskedők elősegíthetik a vevői hűség létrehozását. A kiterjesztett garancia lehetővé teszik a vevők számára, hogy tudják, hová fordulhatnak szolgáltatásokért és támogatásért. Ennélfogva bízhatnak abban, hogy a problémáik hatékonyan lesznek kezelve.

A kiterjesztett garanciát a termékvásárlás során egy kiskereskedelmi csatornában lehet értékesíteni a vevők számára. A vásárlást követően korlátozott ideig is értékesíthetők még.

### <a name="warranty-item-setup"></a>Garanciacikkek beállítása

Dynamics 365 Commerce olyan funkciókat tartalmaz, amelyek lehetővé teszik a garanciacikkek létrehozását és az azokhoz tartozó attribútumok beállítását. Ezek az attribútumok tartalmazzák a termék és a garanciacikk közötti társítást, a garancia árát és a garancia időtartamát. Miután a garanciacikk be van állítva, és a szervezeti egységhez van adva, a kiskereskedő a Modern Point of Sale (MPOS) pénztárakban, az online áruházakban és más kiskereskedelmi csatornákon keresztül értékesítheti a garanciát.

### <a name="warranty-item-sales"></a>Garanciacikkek értékesítése

A kiterjesztett garanciát a termékvásárlás során egy kiskereskedelmi csatornában lehet értékesíteni. A vásárlást követően korlátozott ideig is értékesíthetők még.

A pénztárnál (POS) a program rákérdez az értékesítőnél, hogy hozzáad-e kiterjesztett garanciát, amikor egy kapcsolódó terméket hozzáadnak a vevő kosarához. Ennek megfelelően egy felülértékesítési vagy a párhuzamos értékesítési lehetőség jelenik meg az értékesítő számára az értékesítési folyamat részeként.

A vevők később is visszatérhetnek, és egy korábban megvásárolt termékre vonatkozó kiterjesztett garanciát vásárolhatnak. Ezekben az esetekben egy értékesítési munkatárs megkeresheti az eredeti tranzakciót, és értékesítheti a vevőnek a kapcsolódó kiterjesztettgarancia-cikket.

### <a name="warranty-terminology"></a>Garanciaterminológia

A következő táblázat néhány garanciával kapcsolatos kifejezést ismertet.

| Kifejezés | Leírás |
|------------------------------|--------------|
| Kiterjesztett garancia/garancia | A *kiterjesztett garancia* egy olyan szolgáltatási szerződésre vagy szerződésre vonatkozik, amely meghosszabbított garanciát nyújt a vevők számára. A kiterjesztett garancia a kiterjesztett garancia fedezeti időszaka alatt a termék cseréjével vagy javításával kapcsolatos további szolgáltatásokat tartalmaz. |
| Gyártói garancia | A *gyártói garancia* (amelyre gyakran *korlátozott garancia* néven hivatkoznak) az a garancia, amelyet a vevők a termék megvásárlásakor kapnak. Az alábbiakban a gyártói garancia néhány szolgáltatását találhatja meg:<ul><li>A garancia költsége szerepel a termék költségében. A vevőknek nem kell további összeget fizetniük a gyártói jótállásért.</li><li>A termékkategóriától függően gyártói garancia általában 30 napot, hat hónapot vagy egy évet tart. (A legtöbb elektronikai termék esetében a garancia egy év).</li><li>A jótállás a mechanikai vagy elektromos meghibásodások által okozott hibákra vonatkozik. A fedezet korlátozott, és nem vonatkozik a vásárolt termék véletlen károsodására. Azoknak a vevőknek, akik szeretnék megvédeni a vásárolt termékeket a mindennapi sérülésekkel szemben, kiterjesztett garanciát kell vásároljanak. A kiterjesztett garanciák két–tíz évre szólnak, attól függően, hogy mi a termékkategória. Szélesebb fedezetet biztosíthatnak, kiterjedhetnek például mindennapi balesetekre, például a leejtésre, leöntésre és foltokra.</li></ul> |
| Garanciacikk | A *garanciacikkek* olyan kiterjesztettgarancia-cikkek, amelyek a garanciális cikkekhez értékesíthetők. Ez a példa egy kétéves, véletlen sérülésekre vonatkozó terv hordozható számítógépekhez. |
| Garanciára jogosult cikk | A *garanciára jogosult cikk* egy szerializált termék, amelyhez garanciát értékesítenek. Egy hordozható számítógép például egy olyan garanciára jogosult cikk, amelyhez a két éves és a hároméves meghosszabbított garancia értékesíthető. |
| Garanciacsoport | A *garanciacsoport* garanciacikkek és a garanciára jogosult cikkek közötti kapcsolat. A pénztár garanciacsoportokat használ annak meghatározására, hogy az értékesítő számára mely garanciacikk hozzáadását javasolja a rendszer, amikor egy garanciára jogosult cikket adnak a vásárló kosarához. |
| Garancia-irányelv | A *garanciaszerződés* olyan entitások, amelyek egy garanciaszerződés eladása esetén a Commerce-ben jönnek létre. A garanciaszerződés olyan információkat tartalmaz, mint a beszerzett garanciacikk kezdő és befejező dátuma, a szerződési feltételek és a garanciára jogosult termék sorozatszáma. A garanciaszerződés száma megosztható a vevőkkel, így hivatkozhatnak a megvásárolt kiterjesztettgarancia-cikkre, amelyet megvásároltak. |

## <a name="create-a-warranty-item"></a>Garanciacikk létrehozása

A garanciacikk létrehozásához a Commerce rendszerben hajtsa végre az alábbi lépéseket.

1. Nyissa meg a **Kiskereskedelem és kereskedelem \> Termékek és kategóriák \> Termékek** lehetőséget.
1. Válassza ki az **Új** lehetőséget egy új garanciacikk létrehozásához.
1. Válassza ki az **Új termék** párbeszédpanel **Terméktípus** mezőjében a **Szolgáltatás** elemet.
1. A **Termékaltípus** mezőben válassza a **Termék** lehetőséget.
1. A **Termékszolgáltatás típusa** mezőben válassza a **Szolgáltatása** lehetőséget.
1. A **Termék neve** mezőbe írja be a terméknevet.
1. A **Kiskereskedelmi kategória** mezőben válasszon ki egy értéket a legördülő párbeszédpanelen, majd kattintson az **OK** gombra.
1. A **Termékszám** mezőbe írja be a termékszámot.
1. Válassza ki az **OK** lehetőséget.
1. A **Termék adatai** lap **Garancia** gyorslapján állítsa be az **Időegység** és az **Időtartam** mezőket.

    | Mezőnév | Érték | Leírás |
    |------------|-------|-------------|
    | Időegység | **Nap(ok)**, **Hét/hetek**, **Hónap(ok)** vagy **Év(ek)** | Ez a mező a jótálláshoz használt időegységet határozza meg. |
    | Időtartam hossza | Pozitív egész érték | Ez a mező a jótállás időtartamát határozza meg a kiválasztott időegységben. |

    Ha például két éves a garancia van, akkor az **Időegység** mezőt **Év(ek)** értékre, míg az **Időtartam** mezőt **2** értékre állítsa. Azt is megteheti, hogy az **Időegység** mezőt **Hónap(ok)** értékre állítja, és az **Időtartam** mezőt **24** értékre állítja , ahogy az a következő ábrán látható.

    ![Egy garanciacikk termékazonosító lapja](./media/ew-time-properties.png)

1. A garanciacikk mentéséhez válassza a **Mentés** parancsot.
1. A garanciatermék kiadása a vállalatnak, hogy el lehessen azt adni. További információért lásd: [Kiskereskedelmi termékek beállítása](set-up-retail-products.md).
1. A **Kiadott termék részletei** lap **Garancia** gyorslapján állítsa be az **Ártartomány alapja**, az **Alsó határ** és a **Felső határ** mezőket.

    | Mezőnév | Érték | Leírás |
    |------------|-------|-------------|
    | Ártartomány alapja | **Nincs**, **Alapár** vagy **Eladási ár** | <ul><li>**Nincs** – Az ártartományok **Alsó határ és** **Felső határ** értékei nem vonatkoznak.</li><li>**Alapár** – Egy adott garancia akkor alkalmazható, ha a garanciára jogosult cikk alapára (azaz a kedvezmények nélküli ár) az itt megadott **Alsó határérték** és **Felső határérték** között van a garanciára jogosult cikk árának alapján.</li><li>**Eladási ár** – Ez az érték későbbi használatra van fenntartva.</li></ul> |
    | Alsó határérték, felső határérték | Pozitív egész érték | Ezek a mezők határozzák meg a garanciára jogosult cikkek alsó és felső árkorlátját valamint azt, hogy hogyan alkalmazható az aktuális garanciacikket a garanciára jogosult cikkre. Ezek a határértékek a garanciára jogosult cikk alapárán (más néven a gyártó javasolt kiskereskedelmi ára \[MSRP\]) alapulnak. Ha az **Ártartomány alapja** mező az **Alapár** értékre van állítva , akkor csak az **Alsó határérték** és a **Felső határérték** közötti alapárral rendelkező indítja el a garanciacikk hozzáadását a pénztárnál. |

    A következő ábra például azt mutatja, hogy az **Ártartomány alapja** mező **Alapár** értékre van állítva , az **Alsó határ** mező értéke 500 dollár, és a **Felső határ** mező értéke 1000 dollár.
    
    ![Egy garanciacikk kiadott-termékazonosító lapja](./media/ew-release-product-details.png)

1. A garanciacikk hozzárendelése a csatornához, ahol az értékesítés történik. További információ: [Szortimentek beállítása](set-up-assortments.md).

### <a name="example"></a>Példa

A laptop garanciára jogosult cikknek (termék) alapára 999 dollár és két hordozható számítógép garanciacikk van:

- Az 1.\_garancia alsó határa 500 dollár és a 1000 felső határa dollár, és az **Ártartomány** alapja mező értéke **Alapár**.
- Az 2.\_garancia alsó határa 1001 dollár és a felső határa 2000 dollár, és az **Ártartomány** alapja mező értéke **Alapár**.

Ebben az esetben, ha laptop garanciára jogosult cikket adnak a vásárló kosarához akkor az 1.\_garancia hozzáadására irányuló figyelmeztetés jelenik meg a pénztárban, mivel a hordozható számítógép ára az 1.\_garancia alsó és felső határa között van.

> [!NOTE]
> Ha ebben a példában az 1.\_garancia és a 2.\_garancia alapján is meg szeretné jeleníteni a figyelmeztetést, akkor a garanciára jogosult cikk árának figyelembevételével az **Árkategória alapja** mezőt **Nincs** értékre kell állítania.

## <a name="configure-channel-specific-settings"></a>Csatornaspecifikus beállítások konfigurálása

A csatornaspecifikus beállításokkal megadhatja, hogy egy garanciacikk hozzáadására irányuló figyelmeztetést meg kell-e jeleníteni a POS-nál, amikor a vevői kosárba egy garanciára jogosult elem kerül.

A csatornaspecifikus beállítások konfigurálásához a Commerce alkalmazásban hajtsa végre az alábbi lépéseket.

1. Menjen a **Kiskereskedelem és kereskedelem \> Termékek és kategóriák \> Garancia \> Garancia beállításai** helyre.
1. Hajtsa végre a következő lépések valamelyikét a **Csatornaspecifikus** lap **Garanciával kapcsolatos figyelmeztetés** oszlopában:

    - Jelölje be a jelölőnégyzetet, ha a garanciacikkel kapcsolatos figyelmeztetésnek meg kell jelennie a pénztárnál, amikor garanciára jogosult cikket adnak hozzá a kosárhoz.
    - Törölje a jelölést, ha a garanciacikkel kapcsolatos figyelmeztetésnek nem kell megjelennie a pénztárnál, amikor garanciára jogosult cikket adnak hozzá a kosárhoz.

1. Az **1070-es** feladat futtatásával szinkronizálhatja az adatokat a csatornával.

## <a name="configure-a-number-sequence-for-warranty-policies"></a>A garanciafeltételek számsorozatának konfigurálása

Minden garanciaszerződést egyedileg azonosít egy garanciaszerződés szám, amelyet egy számsorozat generál. A számsorozatokkal kapcsolatos további információkat lásd: [Számsorozatok áttekintése](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).

A Commerce rendszerbeli garanciaszerződések számsorozatának konfigurálásához kövesse az alábbi lépéseket.

1. Menjen a **Kiskereskedelem és kereskedelem \> Termékek és kategóriák \> Garancia \> Garancia beállításai** helyre.
1. A **Számsorozatok** lap **Garanciaszerződés** hivatkozásának sorában adja meg vagy válassza ki a kívánt értéket a **Számsorozat kódja** mezőben.

## <a name="set-up-a-warranty-group"></a>Garanciacsoport beállítása

A garanciacsoport garanciacikkek és a garanciára jogosult cikkek közötti kapcsolat. A pénztár garanciacsoportokat használ annak meghatározására, hogy az értékesítő számára mely garanciacikk hozzáadását javasolja a rendszer, amikor egy garanciára jogosult cikket adnak a vásárló kosarához.

A garanciacsoport beállításához a Commerce alkalmazásban tegye a következőket.

1. Menjen a **Kiskereskedelem és kereskedelem \> Termékek és kategóriák \> Garancia \> Garanciacsoportok** helyre.
1. Válassza ki az **Új** lehetőséget egy új garanciacsoport létrehozásához.
1. A **Név** mezőben adja meg az új csoport nevét.
1. Az **Általános** gyorslapon a **Leírás** mezőben adja meg a csoport leírását.
1. A **Garanciacikkek** gyorslapon válassza a **Sor hozzáadása** parancsot egy garanciacikk hozzáadásához.
1. A **Megjelenítés sorrendje** mezőben adjon meg egy számot, amely rangsorolja a garanciacsoportot a pénztárban. A pénztár a garanciacikkeket csökkenő sorrendben jelenik meg a garanciával kapcsolatos figyelmeztetésben.
1. A **Garanciára jogosult cikkek** gyorslapon válassza a **Sor hozzáadása** parancsot garanciára jogosult termékek hozzáadásához.
1. Ha a garanciacikk garanciára jogosult cikkek (termékek) egy teljes kategóriára vonatkozik, válassza ki a kategóriát a **Kategória** mezőben. Ha a garanciacikk egy adott garanciára jogosult cikkre (termékre) vonatkozik, válassza ki a terméket a **Termék** mezőben.
1. A **Vonatozó csatornák** gyorslapon válassza a **Sor hozzáadása** parancsot annak a csatornának a hozzáadásához, amelyben értékesíteni szeretné a garanciacikket.
1. A konfiguráció mentéséhez válassza a **Mentés** parancsot.
1. A garanciacsoport közzétételéhez válassza a **Közzététel** lehetőséget.
1. Az **1040-es** feladat futtatásával szinkronizálhatja az adatokat a csatornával.

## <a name="sell-warranty-items-at-the-pos"></a>Garanciacikkek értékesítése a pénztárban

Két pénztárművelet teszi lehetővé, hogy az értékesítési munkatársak vevők vásárlásához kapcsolódó munkafolyamat során garanciacikkeket értékesítsenek:

- **Garancia hozzáadása** – Ezzel a művelettel egy olyan figyelmeztetés jelenik meg, amely megfelelő garanciákat jelenít meg a kosárban kiválasztott garanciára jogosult cikkek esetében.
- **Garancia hozzáadása meglévő tranzakcióhoz** – ennek a műveletnek a segítségével az értékesítők garanciát értékesíthetnek korábban értékesített, garanciára jogosult cikkekhez. Az értékesítők a tranzakció nyugtájának száma megadásával megkereshetik az eredeti tranzakciót a garanciára jogosult cikkhez.

A következő ábra példát mutat be egy POS terminál lapjára, amelyen egy üzenet azt kérdezi, hogy hozzá szeretne-e adni egy garanciacikket az aktuálisan vásárolt garanciára jogosult cikkhez.

![Példa egy garanciacikk hozzáadásával kapcsolatos üzenetre az aktuális vásárláshoz](./media/ew-sell-warranty.png)

A következő ábra egy példát mutat be arra a funkcióra, amelyben garanciacikket lehet hozzáadni egy korábban vásárolt garanciára jogosult cikkhez.

![Példa arra a funkcióra, amellyel garanciacikket adhat hozzá egy korábban értékesített garanciára jogosult cikkhez](./media/ew-add-warranty-existing.png)

## <a name="process-warranty-transactions"></a>Garanciatranzakciók feldolgozása

Amikor a garanciákat cash-and-carry típusú tranzakciókban értékesítik, a tranzakciók feladását követően a Commerce-központba a Commerce-felhasználók futtathatják a **Garanciatranzakciók feldolgozása** feladatot a garanciatranzakciók feldolgozásához és a garanciaszerződések létrehozásához.

Garanciatranzakciók feldolgozásához a Commerce-központban hajtsa végre az alábbi lépéseket.

1. Menjen a **Kiskereskedelem és kereskedelem \> Termékek és kategóriák \> Garancia \> Garanciatranzakciók feldolgozása** helyre.
1. Válasszon ki egy értéket a **Szervezeti csomópontok kiválasztása** párbeszédpanel **Szervezeti hierarchia** mezőjében.
1. A **Rendelkezésre álló szervezeti csomópontok** listán válasszon ki az egy adott üzletet, vagy , ha egy üzletek egy csoportjához szeretné létrehozni egy kötegelt feladatot, egy csomópontot.
1. A jobbra mutató nyíl használatával adhatja hozzá a kiválasztottakat a **Kiválasztott szervezeti csomópontok** listához.
1. Válassza a **Futtatás a háttérben** lapot.
1. A **Kötegelt feldolgozás** beállítást állítsa **Igen** értékre, majd válassza ki az **Ismétlődés** elemet.
1. Az **Ismétlődés definiálása** párbeszédpanel **Kezdő dátum** mezőjében válassza ki vagy adja meg az ismétlődés kezdő dátumát.
1. A **Kezdés ideje** mezőben válassza ki vagy adja meg az ismétlődés kezdő időpontját.
1. Tegye a következők egyikét:

    - Jelölje be a **Nincs záró dátum** beállítást, ha azt szeretné, hogy az ismétlődés soha ne érjen véget.
    - Válassza ki a **Befejezés ezt követően** lehetőséget ha azt szeretné, hogy az ismétlődés egy meghatározott számú futtatást követően fejeződjön be. Ha ezt a lehetőséget választja, adja meg a futások számát.
    - Jelölje be a **Befejezés ekkor:** beállítást, ha azt szeretné, hogy az ismétlődés egy megadott dátumon érjen véget. Ha ezt a lehetőséget választja, válassza ki vagy írja be a dátumot.

1. Válassza ki az **OK** lehetőséget.
1. Válassza ki az **OK** lehetőséget.

## <a name="warranty-policies"></a>Garanciaszerződések

Egy kiterjesztett garancia értékesítésekor a program automatikusan létrehozza egy garanciaszerződés entitást. A garanciaszerződés száma megosztható a vevőkkel, így hivatkozhatnak a megvásárolt garancia-cikkre, amelyet megvásároltak. A garanciaszerződés tulajdonságai között szerepel a jótállás hatályának kezdő dátuma és lejárati dátuma, a szerződési feltételek valamint annak a garanciára jogosult terméknek a sorozatszáma, amelyhez eladták a garanciát.

> [!NOTE]
> A garancia tulajdonságait a rendszer automatikusan generálja a garanciaszerződés-entitások létrehozásakor. Jelenleg nem lehetnek manuálisan konfigurálni vagy szerkeszteni ezeket.

A következő táblázat leírja a garanciaszerződés jellemzőit és azok értékeit. A Commerce központ alkalmazásban az adatbázistábla neve WARRANTYPOLICY.

| Tulajdonság neve | Érték | Leírás |
|---------------|-------|-------------|
| PolicyNumber | Egy karakterlánc (legfeljebb 20 karakterből állhat) | A garanciaszerződés száma |
| WarrantiedItemId | Egy karakterlánc (legfeljebb 20 karakterből állhat) | A garanciára jogosult cikk azonosítója |
| WarrantiedInventoryLotId | Egy karakterlánc (legfeljebb 20 karakterből állhat) | A garanciára jogosult cikk készletadag-azonosítója |
| WarrantiedSerialNumber | Egy karakterlánc (legfeljebb 20 karakterből állhat) | A garanciára jogosult cikk sorozatszámának megtekintése |
| WarrantiedFulfilledDate | Egy dátum | A garanciára jogosult cikk teljesítési dátuma |
| WarrantyItemId | Egy karakterlánc (legfeljebb 20 karakterből állhat) | A garanciacikk azonosítója |
| WarrantyInventoryLotId | Egy karakterlánc (legfeljebb 20 karakterből állhat) | A garancia cikk készletadag-azonosítója |
| WarrantySalesDate | Egy dátum | A garanciacikk értékesítésének dátuma |
| WarrantyEffectiveDate | Egy dátum | A garanciaszerződés érvényességi dátuma |
| WarrantyExpirationDate | Egy dátum | A garanciaszerződés lejárati dátuma |
| CustAccount | Egy karakterlánc (legfeljebb 20 karakterből állhat) | A vevő számlaszáma |
| Állapot | **Létrehozva**, **Érvénytelenítve**, **Hatályos** vagy **Lejárt** | A garanciaszerződés állapota |
| Jegyzetek | Egy karakterlánc (legfeljebb 255 karakterből állhat) | Megjegyzések a garanciaszerződéshez, például a feltételek |

## <a name="frequently-asked-questions-faq"></a>Gyakori kérdések (GYIK)

**Miért nem jelenik meg a garanciával kapcsolatos figyelmeztetés a pénztárban?**

Győződjön meg róla, hogy a garanciacikk hozzá van rendelve egy csatornához. Győződjön meg arról is, hogy a jótállási csoport úgy van beállítva, hogy az tartalmazza a megfelelő csatornát.

**Amikor egy létező tranzakcióhoz egy garanciát próbálok hozzáadni, és megadom vevői vásárlás nyugtájának a számát, akkor miért nem látok a tranzakciósor-cikkeket?**

A nyugta csak akkor érhető el, ha a nyugta a Commerce központba történő feltöltéséhez egy lekéréses feladatot (P-feladat) futtat. A P-feladat futtatásához nyissa meg a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem IT \> Leosztási ütemezés** lehetőséget, válassza ki a **P-0001** feladatot, majd válassza a **Futtatás most** parancsot.

**Miért csak a szerializált termékekre vonatkozik a garancia funkció?**

A garancia egy olyan szolgáltatás, amely egy konkrét, egyedi termékekre vonatkozik. A Dynamics 365 alkalmazásban egy terméket csak egy sorozatszám alapján lehet egyedileg azonosítani.

## <a name="additional-resources"></a>További erőforrások

[Retail termékek beállítása](set-up-retail-products.md)

[Szortimentek beállítása](set-up-assortments.md)

[Számsorozatok áttekintése](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
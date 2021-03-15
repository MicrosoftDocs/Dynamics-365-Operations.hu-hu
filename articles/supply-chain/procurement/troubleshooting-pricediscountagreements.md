---
title: Árak, engedmények, szerződések és visszatérítések hibaelhárítása
description: Ez a témakör azt mutatja be, hogyan lehet javítani az árak, engedmények, megállapodások és visszatérítések használata során felmerülő problémákat.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 14fdddabde7739cbf9ba0fcee0fa0b8b816e74dd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007366"
---
# <a name="troubleshoot-prices-discounts-agreements-and-rebates"></a>Árak, engedmények, szerződések és visszatérítések hibaelhárítása

Ez a témakör azt mutatja be, hogyan lehet javítani az árak, engedmények, megállapodások és visszatérítések használata során felmerülő problémákat.

## <a name="i-cant-link-a-purchase-agreement-to-a-purchase-order-line-after-the-purchase-order-is-created"></a>A beszerzési rendelés létrehozása után nem lehet beszerzési szerződést kapcsolni egy beszerzési rendelés sorához.

A beszerzési rendelés létrehozása során lehet beszerzési szerződést kapcsolni a beszerzési rendelés egy sorához. Ellenkező esetben a beszerzésirendelés-sorok nem társíthatók a beszerzési szerződés soraival.

## <a name="what-check-triggers-the-update-prices-and-discounts-entered-manually-or-external-document-message"></a>Milyen ellenőrzés váltja ki az „Manuálisan megadott árak és engedmények frissítése vagy külső dokumentum” üzenetet?

A szállítási dátum módosításakor a következő üzenet jelenik meg: „Manuálisan megadott árak és engedmények frissítése vagy külső dokumentum”. Ez az üzenet akkor jelenik meg, ha a szállítási dátum megváltozik, egy másik kereskedelmi vagy értékesítési szerződés lesz meghívva, és ez árváltozást okozhat. A szállítási dátum módosítása hatással lehet a raktári ütemezésekre és más kapcsolódó információkra is.

Az üzenet akkor jelenik meg, ha bármely dátum vagy más paraméter módosul. Az üzenet célja, hogy biztosan tisztában legyen azzal, a változtatások miatt előfordulhat az árak módosulása.

Az üzenet a kereskedelmi megállapodás értékelése (TAE) figyelmeztetés. A teljes leírást lásd: [Kereskedelmi szerződés értékelési irányelvei](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).

## <a name="a-purchase-order-receipt-doesnt-include-all-charges"></a>A beszerzési rendelés nyugtája nem tartalmaz minden költséget.

### <a name="reproduce-the-issue"></a>A hiba reprodukálása

A következő eljárás bemutatja a hiba reprodukálásának egyik módját.

1. A **Beszerzés és forrás paraméterei lap** **Szállítás** lapján győződjön meg arról, hogy a **Díjak generálása terméknyugtán** beállítás *Igen* értékre van állítva.
1. Hozzon létre egy költségeket tartalmazó beszerzési rendelést.
1. Erősítse meg a beszerzési rendelést.
1. Fogadja a beszerzési rendelést.
1. Tekintse meg a nyugta összegét, és hasonlítsa össze a várt összeggel.
1. Figyelje meg, hogy nem minden költség szerepel a beszerzési rendelés nyugtáján.

### <a name="issue-resolution"></a>Probléma megoldása

A megoldás a vegyes költségek beállításának módjától függ. A vegyes költségnek az igények teljesítése céljából történő beállításával kapcsolatos további tudnivalókat lásd a következő blogbejegyzésben: a [Vegyes költségek feladása terméknyugta időpontjában](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).

## <a name="trade-agreement-prices-and-discounts-arent-applied-on-sales-or-purchase-order-lines-that-are-imported-through-data-management"></a>A kereskedelmi megállapodási árak és engedmények nincsenek alkalmazva az adatkezeléssel importált értékesítési és beszerzési rendelési sorokra.

### <a name="issue-description"></a>Probléma leírása

Az értékesítési vagy beszerzésirendelés-sorokra vonatkozó kereskedelmi megállapodások nincsenek alkalmazva az adatkezeléssel importált értékesítési és beszerzési rendelési sorokra. Ugyanezek a kereskedelmi megállapodások azonban olyan értékesítési vagy beszerzésirendelés-sorokra vonatkoznak, amelyek manuálisan jönnek létre.

### <a name="reason-for-the-issue"></a>A probléma oka

Ha az adatkezelésen keresztül importált beszerzésirendelés-sorok már tartalmazzák az árak adatait, akkor a kereskedelmi megállapodás nem lesz újraértékelve ezekhez a sorokhoz. Ha például a **Sorengedmény százaléka** vagy az ár-és az engedményértékeket bármelyike egy sorhoz be van állítva, akkor a kereskedelmi megállapodásokat nem keresi a program ehhez a sorhoz.

### <a name="issue-workaround"></a>Probléma megoldása

Ez a viselkedés várható, és az értékesítési rendelésekhez és a beszerzési rendelésekhez hasonló.

Megoldásként importálja a beszerzési rendelés sorait az áradatok megadása nélkül. A kereskedelmi megállapodások ekkor alkalmazva lesznek, és a beszerzési rendelési sorok a meghatározott kereskedelmi megállapodások alapján lesznek frissítve.

## <a name="a-vendor-rebate-isnt-cumulated-based-on-invoices"></a>A szállítói visszatérítés nem halmozott a számlák alapján.

### <a name="issue-description"></a>Probléma leírása

Ha a feladott számlák különböző esedékességi dátummal rendelkeznek, akkor ezek a számlák nem tükröződnek a belőlük létrejövő szállítói visszatérítésekben.

### <a name="issue-resolution"></a>Probléma megoldása

Tervezése alapján a program nem veszi figyelembe a határidőt a szállítói visszatérítés kiszámításakor. Fontolja meg a rendszer testreszabását úgy, hogy a fizetési határidő és a számlához való viszonya jobban látható legyen a szállító tényleges visszatérítése kapcsán.

## <a name="unit-prices-on-purchase-orders-arent-calculated-based-on-the-unit-conversion"></a>A beszerzési rendeléseken szereplő egységárak számítása nem a mértékegység-átváltás alapján történik.

### <a name="issue-description"></a>Probléma leírása

Amikor egy egység megváltozik egy beszerzési rendelésen, a kereskedelmi megállapodás árai nem lesznek újraszámítva a mértékegység-átváltás definíciói szerint.

### <a name="issue-resolution"></a>Probléma megoldása

Az árak mindig a kereskedelmi megállapodásokból (vagy a rendszerben szereplő egyéb áraktól, például az értékesítési megállapodások vagy a cikkek áraiból) vannak lekérve, és egy mértékegységhez vannak beállítva.

Ha egy rendelési sorban módosul az egység, a rendszer az új árat keres az egységhez, és ezt az árat alkalmazza. Ha nem talál árat a egységhez, akkor a rendszer nem alkalmaz árat. A mértékegység-átalakítás nem használható az ár másik egységbe történő átszámítására. Elméletileg a tíz dobozt tartalmazó egység ára nem biztos, hogy tízszerese egy doboz árának.

### <a name="issue-workaround"></a>Probléma megoldása

A probléma megkerülésének egyik módja annak ellenőrzése, hogy vannak-e kereskedelmi megállapodások azokhoz az egységekhez, amelyek várhatóan használva lesznek a cikk rendelési soraihoz.

## <a name="currency-conversion-issues-occur-with-trade-agreements"></a>Pénznem-átváltási problémák tapasztalhatók a kereskedelmi megállapodásoknál.

A kereskedelmi megállapodás árait nem számítja újra a program a beszerzési rendelés pénzneme használatával, ha az eltérő.

Az *Általános pénznem* funkció lehetővé teszi az árak és engedmények definiálását egy pénznemben. Ezt követően a szükséges módon konvertálhat más pénznemekre. Ezenkívül az átváltás után a funkcióval automatikusan alkalmazhat intelligens kerekítést.

## <a name="when-i-open-the-purchase-agreement-page-in-a-line-view-mode-i-cant-personalize-the-page-by-adding-the-price-unit-field-in-the-overview-of-the-line"></a>Amikor a Beszerzési szerződés lapját egy sor nézet módban nyitom meg, akkor nem lehet személyre szabni a lapot az Egységár mező hozzáadásával a sor áttekintésében.

A szerződési keretrendszer néhány megosztott mezője nem vonható be a személyre szabásokba. Ez a korlátozás az alkalmazott adatmodell miatt következik be. Ezért nem lehet személyre szabni az **Egységár** mezőt.

## <a name="the-maximum-limit-from-a-purchase-agreement-isnt-effective-on-a-purchase-requisition"></a>A beszerzési szerződésből származó maximális határérték nem érvényes egy beszerzési igénylésre.

### <a name="issue-description"></a>Probléma leírása

Amikor egy beszerzési igénylés egy beszerzési szerződéshez van kapcsolva, a beszerzési szerződés maximálisan megengedett határértéke nem érvényes a beszerzési igénylésre. A program helyesen írja be az alapértelmezett árat, de a beszerzési megállapodásban szereplő maximális korlátozásnál többet is lehetséges rendelni a beszerzési igénylésben.

### <a name="issue-resolution"></a>Probléma megoldása

Ez a viselkedés várható. Mivel az igényléseket nem mindig hagyják jóvá, egy mennyiséget vagy összeget nem szabad lefoglalni a beszerzési szerződésen. Ennélfogva nem fogja elérni a beszerzési szerződés maximális határértékét.

## <a name="trade-agreements-can-be-created-from-rejected-rfqs-therefore-the-system-doesnt-prevent-trade-agreement-journals-from-being-created-if-the-rfq-line-hasnt-been-accepted"></a>A kereskedelmi megállapodásokat elutasított ajánlatkérésből létre lehet hozni. Ezért a rendszer nem akadályozza meg a kereskedelmi megállapodási naplók létrehozását, ha a ajánlatkérés sor nem lett elfogadva.

Az ajánlatkérésre adott válaszokhoz kereskedelmi megállapodásokat hozhat létre, függetlenül attól, hogy elfogadták vagy elutasították azokat. További információkért lásd: [Ajánlatkérések (RFQ-k) áttekintése](request-quotations.md).



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
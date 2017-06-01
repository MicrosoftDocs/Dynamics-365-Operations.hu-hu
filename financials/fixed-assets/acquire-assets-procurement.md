---
title: "Eszközök vételezése beszerzésen keresztül"
description: "Ez a cikk azt mutatja be, hogyan állíthatja be a Tárgyi eszközök és a Kötelezettségek modul integrálásával az automatikusan létrehozható tárgyi eszközöket beszerzési megrendelésekből vagy szállítói számlákból, illetve automatikusan feladható tárgyi eszközökre vonatkozó beszerzési és beszerzés-helyesbítési tranzakciókat."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetParameters
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3481
ms.assetid: d4e73a3f-633b-48b2-b8db-7a4a59a4d7ec
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: aa5598ddd0d397314b42c6ac0c1b0d02eb95ebb4
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="acquire-assets-through-procurement"></a>Eszközök vételezése beszerzésen keresztül

[!include[banner](../includes/banner.md)]


Ez a cikk azt mutatja be, hogyan állíthatja be a Tárgyi eszközök és a Kötelezettségek modul integrálásával az automatikusan létrehozható tárgyi eszközöket beszerzési megrendelésekből vagy szállítói számlákból, illetve automatikusan feladható tárgyi eszközökre vonatkozó beszerzési és beszerzés-helyesbítési tranzakciókat.

 A Tárgyi eszközök és a Kötelezettségek modul integrálására a következő módszerek állnak rendelkezésre; minden tárgyi eszköz esetében ugyanazt a módszert kell alkalmazni:
-   Manuálisan létrehoz egy tárgyi eszközt, mielőtt megadná a tárgyi eszköz számát a beszerzési rendelés vagy a szállítói számla sorában. A szállítói számla feladásakor a rendszer automatikusan felad egy beszerzési tranzakciót a tárgyi eszközre. Ez az alapértelmezett módszer.
-   Manuálisan létrehoz egy tárgyi eszközt, mielőtt megadná a tárgyi eszköz számát a beszerzési rendelés vagy a szállítói számla sorában. A szállítói számla feladásakor a rendszer nem ad fel automatikusan beszerzési tranzakciót a tárgyi eszközre.
-   Ha olyan termékbevételezést vagy szállítói számlát ad fel, amelynél be van jelölve az Új tárgyi eszköz létrehozása jelölőnégyzet, a rendszer automatikusan létrehoz egy új tárgyi eszközt. A szállítói számla feladásakor a rendszer automatikusan felad egy beszerzési tranzakciót a tárgyi eszközre.
-   Ha olyan termékbevételezést vagy szállítói számlát ad fel, amelynél be van jelölve az Új tárgyi eszköz létrehozása jelölőnégyzet, a rendszer automatikusan létrehoz egy új tárgyi eszközt. A szállítói számla feladásakor a rendszer nem ad fel automatikusan beszerzési tranzakciót a tárgyi eszközre.

Válassza az első két módszer egyikét, ha a tárgyi eszközöket inkább manuálisan szereti létrehozni, és aztán a tárgyi eszköz számát a beszerzési rendeléshez vagy szállítói számlához hozzárendelni. Válasszon egyet a következő két módszer közül, ha egy rugalmasabb megközelítést szeretne: a tárgyi eszközöket létrehozhatja manuálisan is, és időnként automatikusan létrehozhat egy tárgyi eszközt a sor adatai között megtalálható tárgyieszköz-információk alapján is. 

Amikor manuálisan hoz létre tárgyi eszközöket, vagy valamelyik rugalmasabb megközelítést alkalmazza, el kell döntenie, hogy a beszerzési tranzakciót csak a Tárgyi eszközökhöz lehet-e feladni, vagy feladható-e a szállítói számla feladásakor. Egyes szervezetek előnyben részesítik, ha a felhasználók manuálisan hozzák létre a beszerzéseket és a beszerzési tranzakciókat a Tárgyi eszközök modulban manuális naplóbejegyzések vagy -javaslatok használatával. 

Ez a témakör az egyes módszerekről nyújt részletes tájékoztatást.

## <a name="methods-for-manually-creating-fixed-assets"></a> Módszerek tárgyi eszközök manuális létrehozásához
Olyan szállítói számla feladásakor, amelynél a sorokban tárgyieszközszám van megadva, amennyiben a Tárgyi eszközök paraméterei oldalon a Tárgyi beszerzés engedélyezése a Beszerzéstől jelölőnégyzet be van jelölve, a beszerzés feladása automatikusan megtörténik, és az eszköz állapota Nyitott értékre változik. 

Ha egy beszerzést nem lehet feladni, vagy manuálisan be lehet vinni egy beszerzési tranzakciót a Tárgyi eszközök modulban, vagy beszerzési javaslat használatával a Tárgyi eszközök naplóban egyszerre létre lehet hozni több beszerzési tranzakciót is.

> [!NOTE]                                                                                                                              
> Ha a Tárgyi eszközök úgy vannak beállítva, hogy a beszerzési tranzakciók feladását egy bizonyos felhasználói csoportra korlátozzák, a beszerzési tranzakciók számlából való feladásához az adott felhasználói csoport tagjának kell lennie.

## <a name="methods-for-automatically-creating-fixed-assets"></a> Módszerek tárgyi eszközök automatikus létrehozásához
Ha egy olyan termékbevételezést ad fel, amely egy sorra vonatkozóan rendelkezik az Új tárgyi eszköz létrehozása opcióval, egy új tárgyi eszköz jön létre, amelynek állapota Még nem beszerzett lesz. Aztán amikor új tárgyi eszközzel szállítói számlafeladás történik, az új eszközhöz beszerzési tranzakciót ad fel a rendszer, és az eszköz Nyitott állapotúra változik, amennyiben a Tárgyi eszközök úgy vannak beállítva, hogy engedélyezzék az eszközbeszerzéseket a Követelések modulból, és a felhasználó tagja annak a felhasználói csoportnak, amelynek számára engedélyezett a beszerzési tranzakciók feladása. 

Ha a beszerzési soron a termékbevételezés feladásakor nem volt bejelölve az Új tárgyi eszköz? opció, de a szállítói számla feladásakor igen, létrejön az új tárgyi eszköz, és Nyitott állapottal beszerzetté válik, amennyiben a Tárgyi eszközök beállítása lehetővé teszi a létrehozást és a beszerzést. Szállítói számla feladásakor nem jön létre további eszköz, ha a termékbevételezés feladásakor már megtörtént egy eszköz létrehozása.

### <a name="capitalization-threshold"></a>Tőkésítési küszöbérték

Olyan módszer alkalmazása esetén, amelynél automatikusan történik meg az eszköz létrehozása és beszerzetté tétele, a rendszer beállítható annak ellenőrzésére, hogy a tárgyi eszköz beszerzési összege megfelel-e az eszközök értékcsökkenéséhez megadott tőkésítési küszöbértéknek. Ha igen, az eszközhöz tartozó könyvekben be lesz jelölve az Értékcsökkenés jelölőnégyzet, amikor az eszköz létrejön a Kötelezettségek modulból. 

A tőkésítési küszöbérték egy adott pénznemben megadott összeg, amely meghatározza, hogy az eszközöknél a megadott összeg teljesülése esetén van-e értékcsökkenés. Ha például egy eszköz megvásárlása esetén a beszerzési összeg kisebb mind a tőkésítési küszöbérték, az eszköz nem lesz beállítva értékcsökkenésre, ha viszont a beszerzési összeg eléri vagy meghaladja a küszöbértéket, az eszköz be van állítva értékcsökkenés tárgyaként. 

A tőkésítési küszöbértéket a Tárgyi eszköz csoportok képernyőn lehet beállítani.

## <a name="scenario"></a>Eset
A következő helyzet a Tárgyi eszközök és a Kötelezettségek integrálásának egy teljes ciklusát mutatja be. Látható egy mintabeállítás, és szerepel a beszerzési javaslatok használatának leírása is. 

Ebben a helyzetben a rendszer beállítása a következő:

-   Az eszközök a termékbevételezés vagy a szállítói számla feladásakor automatikusan létrejönnek, de a Tárgyi eszközök úgy vannak beállítva, hogy nem engedik a beszerzési tranzakciók feladását a Kötelezettségek modulból.
-   Tárgyi eszköz bizonylat esetében a számlák a Számlatípus mezőben, míg a Tárgyi eszköz kiadásai számlatípusok a Cikkcsoport oldalon vannak megadva.
-   A számítógépek csoport (COMP) tőkésítési küszöbértéke 1500.
-   A feladat beírni a beszerzési megrendelést egy új hordozható számítógépre, amelyet egy alkalmazott fog használni, feladni a beszerzési rendelést, ellenőrizni, hogy a szállítási adminisztrátor feladjon egy termékbevételezést, feladni a szállítói számlát, aztán ellenőrizni, hogy a könyvelő Nyitott állapotra frissítse a hordozható számítógép eszközt.

Első lépésként a Beszerzési rendelés képernyő használatával be kell vinni a hordozható számítógép adatait, a gép ára 1600. A beszerzési rendelés soraiban ki kell választani az Új tárgyi eszköz opciót a Tárgyi eszközök gyorslapon, ki kell választani tárgyieszköz-csoportként a COMP csoportot, és menteni kell a beszerzési rendelést. 

A hordozható számítógép megérkezésekor egy szállítási adminisztrátor bevisz és felad egy termékbevételezést, ezzel rögzíti a hordozható számítógép bevételezését. A hordozható számítógép eszköz létrejön, és Még nem beszerzett állapotot kap. Azösszeg nagyobb a tőkésítési küszöbértéknél. Emiatt az Értékcsökkenés beállítás ki van választva a laptop eszközhöz tartozó könyvekben. A következő tranzakciók történtek.

| Leírás                               | Fiók             | Terhelés    | Követelés   |
|-------------------------------------------|---------------------|----------|----------|
| Beszerzés, termékbevételezési számla        | Számlázatlan bevételezések | 1600,00 |          |
| Beszerzés, termékbevételezési beszerzés ellentétele | Könyvelt beszerzések   |          | 1600,00 |

A következő lépés a laptophoz tartozó szállítói számla feladása. A laptop állapota nem változik, mivel a Tárgyi Eszközök úgy vannak beállítva, hogy feladott szállítói számla esetén ne engedje eszközbeszerzési tranzakció feladását. Az Új tárgyi eszköz létrehozása opció be volt jelölve a szállítói számla feladásakor. Emiatt a tárgyieszköz-bevételezési számla volt használva. A Tárgyi eszköz kiadási számlát nem kellett használni, mert nem történt beszerzés feladása; ezt később használja a rendszer, amikor a könyvelő beszerzési javaslatok segítségével beszerzési tranzakciót ad fel a Tárgyi eszközök modulban. 

A következő tranzakciók történtek.

| Leírás                               | Fiók             | Terhelés    | Követelés   |
|-------------------------------------------|---------------------|----------|----------|
| Beszerzés, termékbevételezési beszerzés ellentétele | Könyvelt beszerzések   | 1600,00 |          |
| Szállítói egyenleg                            | Kötelezettségek    |          | 1600,00 |
| Beszerzés, Tárgyi eszköz bevételezése             | Számítógép költség    | 1600,00 |          |
| Beszerzés, termékbevételezési számla        | Számlázatlan bevételezések |          | 1600,00 |

Végül a könyvelő áttekinti a Még nem beszerzett állapotú tárgyi eszközöket. Emiatt az új laptop eszköz át lesz tekintve. A könyvelő megnyitja a Beszerzési javaslat képernyőt a Tárgyi eszközök napló soraiból, majd beszerzési tranzakciókat hoz létre az összes eszközhöz, amelyekhez tartozik számla, de még mindig Még be nem szerezett állapotúak. A napló feladásakor a laptop eszköz állapota Nyitottra módosul. A Tárgyi eszköz kiadási készlet számlára követelés lesz bejegyezve és az eszközbeszerzési számla terhelve lesz. 

Az alábbiak az előző helyzet variációi:

-   Ha a Tárgyi eszközök úgy vannak beállítva, hogy feladott szállítói számlánál megengedjék az eszközbeszerzési tranzakciók feladását, a könyvelőnek nem kell beszerzési javaslatokat alkalmaznia a Tárgyi eszközök modulban, mivel már létrejött a beszerzési tranzakció. Továbbá a számla feladásakor megtörténik a különböző szállítói számlák frissítése. Számítógépköltség helyett a Tárgyi eszköz bizonylati készletszámlája lesz terhelve, és két további tranzakció történik: az eszközbeszerzési számla terhelve lesz, és a Tárgyi eszköz kiadási készlet számlára követelés lesz bejegyezve.
-   Ha a termékbevételezés feladásakor nincs bejelölve az Új tárgyi eszköz létrehozása jelölőnégyzet, akkor nem jön létre abban az időben eszköz. Ha bejelöli az Új tárgyi eszköz létrehozása beállítást, mielőtt feladná a szállítói számlát, a tárgyi eszköz létrejön Még nem beszerzett állapottal, vagy Nyitott állapottal, amennyiben szállítói számla feladásakor beszerzési tranzakciót is felad.
-   Ha a laptop ára 1600 helyett 1400, a tőkésítési küszöbérték nem lesz elérve. Ezért a tárgyi eszköz létrejön, és az Értékcsökkenés jelölőnégyzet nem lesz bejelölve.
-   Számlaregiszter használata esetén a Számlajóváhagyási napló lapot kell használni a számlaregiszter feladása után a bizonylat beolvasásához, a szállítói számlához kell kapcsolni a beszerzési rendelést, be kell jelölni az Új tárgyi eszköz létrehozása jelölőnégyzetet, és aztán fel kell adni a számlát. Ha a felhasználó olyan felhasználói csoport tagja, amely létrehozhat beszerzési tranzakciókat, létrejön a beszerzés, és az eszköz Nyitott állapotú lesz.
-   Ha a mennyiségnek csak egy része érkezik meg, az első szállítói számlához a felhasználói csoport korlátozásai miatt nem jön létre eszközbeszerzés. Beszerzés feladására egyedül a megrendelt mennyiséget teljesítő második szállítói számlához van mód, amennyiben az első szállítói számlához megtörtént a beszerzési tranzakció megadása, és a felhasználó tagja a beszerzések feladására engedélyezett felhasználói csoportnak.


További tudnivalókért lásd: [Tárgyieszköz-integráció](fixed-asset-integration.md).





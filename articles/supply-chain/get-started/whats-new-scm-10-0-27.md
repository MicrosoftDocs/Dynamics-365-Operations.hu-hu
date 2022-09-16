---
title: A Dynamics 365 Supply Chain Management 10.0.27 új vagy módosult elemei (2022. július)
description: Ez a témakör a Microsoft Dynamics 365 Supply Chain Management 10.0.27 rendszer új vagy módosult funkcióit ismerteti.
author: kamaybac
ms.date: 04/22/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 3ce3b2f3524dbeb043717ed9ef5429ea0eea4b8a
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/08/2022
ms.locfileid: "9427800"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10027-july-2022"></a>A Dynamics 365 Supply Chain Management 10.0.27 új vagy módosult elemei (2022. július)

[!include [banner](../includes/banner.md)]

Ez a cikk felsorolja azokat a funkciókat, amelyek vagy újak, vagy módosulnak a Microsoft Dynamics 365 Supply Chain Management 10.0.27-es verziójában. Ennek a verziónak a buildszáma több 10.0.1227, és a következő ütemezésben érhető el:

- **Előzetes kiadás**: 2022. április
- **A kiadás általános elérhetővé tétele (saját frissítés):** 2022. június
- **A kiadás általános elérhetővé tétele (automatikus frissítés):** 2022. július

## <a name="features-included-in-this-release"></a>A verzióban található funkciók

Ez a kiadás a következő táblázatban felsorolt funkciókat tartalmazza: Előfordulhat, hogy a cikk frissítése a cikk eredeti közzététele után a buildhez hozzáadott funkciókat is tartalmazza.

| Szolgáltatásterület | Szolgáltatás | További információ | Engedélyezte:   |
|---|---|---|---|
| Készlet és logisztika | [Készletfelosztás a készlet láthatósági bővítménye számára](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/inventory-allocation-inventory-visibility-add-in) | [Inventory Visibility – készlet felosztása](../inventory/inventory-visibility-allocation.md) | Alapértelmezés szerint engedélyezve |
| Gyártás | Saját nap nézet a termelési üzem végrehajtási felületéhez | [Hogyan használják a dolgozók a termelés-végrehajtási felületet](../production-control/production-floor-execution-use.md)[és a szabadságegyenlegek megjelenítése a termelés emeletének végrehajtási felületén](../production-control/production-floor-execution-payroll-stats.md) | Funkciókezelés:<br>*Saját nap nézet a termelési üzem végrehajtási felületéhez* |
| Tervezés | [Tervezési optimalizálás támogatása alvállalkozói szerződésekhez](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-subcontracting) | [Gyártás területén végzett alvállalkozói munka kezelése](../production-control/manage-subcontract-work-production.md) | Alapértelmezés szerint engedélyezve |

## <a name="feature-enhancements-included-in-this-release"></a>A kiadásban található funkciófejlesztések

Ez a kiadás a következő táblázatban felsorolt funkciófejlesztéseket tartalmazza: Ezek közül mindegyik fejlesztés egy már meglévő funkciót fejleszt tovább. Mivel fejlesztésekről van szó, nem szerepelnek a [kiadási tervben](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Alapértelmezés szerint mindegyik fejlesztés ki van kapcsolva (hacsak nincs másképpen jelezve), így biztos lehet abban, hogy nem ütköznek a meglévő testreszabásokkal vagy beállításokkal.

Ha bármelyik funkciót be szeretné kapcsolni, akkor ezt a [funkciókezelésben kell megtenni.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)

| Modul | Funkcióneve a funkciókezelésben | További információ |
|---|---|---|
| Alaptervezés | Készlet átfutási idejének figyelembe vétele tervezett átmozgatási rendelés létrehozásakor | *·* *Tervezett* átátviteli rendelés létrehozásakor a rendszer a Nincs vagy Értékesítés típus átfutási idejeként kiszámítja a tervezett át rendelés bevételi dátumának számítása során a cikk alapértelmezett rendelési beállításainál megadott készletátfutási időt. Amikor meg van adva az átfutási idő, a rendszer az értékét használja a bevételezési dátum kiszámításához, és a szállítási napokat figyelmen kívül hagyja. |
| Beszerzés és forrás | Alapértelmezett ügynöki szerződés adóinformációi a szállítói számlasorokban | Ez a funkció bemutatja **az** **ügynöki** szerződésben szereplő szállítói számlasorok Áfa és cikk áfa mezőiben szereplő alapértelmezett értékek beállításának logikáját. Ez a logika csak akkor alkalmazható, ha az ügynöki szerződés sorában a költségtípus főkönyv/főkönyv. A cikk áfacsoportja az alapértelmezett értéket vagy az ügynöki beszerzés kategóriájából (amennyiben be van állítva), vagy a költségtípusból veszi át. Az áfacsoport a szállítói számláról veszi át az alapértelmezett értéket. |
| Beszerzés és forrás | A beszerzésirendelési-sorok számának korlátozása kötegelt feladatonként | Ez a funkció segít optimalizálni a rendszer teljesítményét a visszaigazolások és a termékbevételezések feladása során. Hozzáad egy új beállítást, amely **feladatonkénti sorokat** **·** **a Beszerzés és forrás paraméterei lap Szállítás lapjára** ad hozzá. Ezzel az új beállítással korlátozhatja az egyes kötegelt feladatok által feldolgozható beszerzésirendelés-sorok számát. Ennek megfelelően megakadályozhatja a nagy kötegfeladatok lelassulása a rendszert. |
| Termékinformációk kezelése | Termékattribútum-értékek feltöltése | Ez a funkció hozzáad egy ismétlődő feladatot, amely a Termékattribútum-értékek *feltöltése* nevű feladat. Ez az új időszakos feladat létrehozza a hiányzó termékattribútum-értékrekordokat az olyan attribútumok számára, amelyek termékkategórián keresztül vannak a termékekhez társítva. |
| Gyártásvezérlés | További konfigurációk a termelési üzem végrehajtási felületén | <p>Ez a funkció a következő beállításokat teszi elérhetővá a Termelési **emelet végrehajtási konfigurálása lapon**:</p><ul><li>**Az indítási párbeszédpanel** automatikus megnyitása a keresés befejezésekor – ha ez a beállítás engedélyezve van, a rendszer automatikusan megnyitja a Feladat kezdete párbeszédpanelt, **amikor** a dolgozók a keresősávon keresi meg a feladatot.</li><li>**A jelentés folyamatjelző párbeszédpanelének** automatikus megnyitása a keresés befejezésekor – ha ez a beállítás engedélyezve van, automatikusan megnyílik a feladat Jelentés állapota párbeszédpanelje, **amikor** a dolgozók a keresősávon keresi a feladatot.</li><li>**A jelentés folyamatjelző** párbeszédpanelen fennmaradó alapértelmezett mennyiség – ha ez a beállítás engedélyezve van, **a** Jelentés állapota párbeszédpanel mutatja a termelési feladathoz bejelentett maradék mennyiséget.</li></ul><p>A további tudnivalókat lásd [a Termelési üzem végrehajtási felületének konfigurálása.](../production-control/production-floor-execution-configure.md)</p> |
| Gyártásvezérlés | Termelési csapatok a termelési üzem végrehajtási felületében | <p>Ha ugyanannak a termelési feladatnak több dolgozója van, most egy dolgozót jelölhet meg pilotként. A többi dolgozó automatikusan a vezető asszisztense lesz. Az eredményül kapott csapatnál csak az első csapatnak kell regisztrálnia a feladat állapotát, míg az időrekordok minden csapattagra érvényesek. Ez a funkció egy segítő erőforrásnak nevezett *helyzetet is támogat*. Ebben az esetben egy dolgozó asszisztensként regisztrálhat egy másik dolgozót, aki aztán az újonnan létrehozott csoport vezetője lesz.</p><p>A további tudnivalókat lásd [: Hogyan használják a dolgozók a termelés emeletének végrehajtási felületét](../production-control/production-floor-execution-use.md).</p> |
| Gyártásvezérlés | Jelentés a tervezési cikkekről a termelési üzem végrehajtási felületében | Ez a funkció egyszerűbbé teszi a kötegrendelések jelentéskészítését a cikkeknek a termelés-végrehajtási felületen történő tervezése során. Ha olyan termékhez hoz létre kötegrendelést, amely Tervezés típusú termék, akkor csak *az* adott kötegrendelés társ- és társtermékére lehet készként jelenteni. A cikkek tervezésére használt kötegrendeléseket jellemzően a szétszerelés folyamatainak támogatására használják, ahol a nyersanyagot több egyedi termékre szétbontják. Amikor egy dolgozó készként jelenti egy tervezési cikk kötegrendelését, **a Jelentés állapota** párbeszédpanelen csak a társ- és a társtermékek jelennek meg. Korábban a tervezési cikket is mutatja, és ez a viselkedés segíthet a dolgozókban. |

## <a name="new-and-updated-documentation-resources"></a>Új és frissített dokumentáció-erőforrások

Nemrégiben hozzáadta vagy jelentősen frissítettük a következő súgócikkeket. Ezek a cikkek nem feltétlenül kapcsolódnak az ehhez a verzióhoz hozzáadott új funkciókhoz, mint azt az előző szakaszok felsorolják. Ugyanakkor előfordulhat, hogy a meglévő szolgáltatásokból többet lehet kihozni.

| Szolgáltatásterület | Új vagy frissített cikkek |
|---|---|
| Költségkezelés | [Dátummal súlyozott átlag a tényleges értékkel és a jelöléssel együtt](../cost-management/weighted-average-date.md) |
| Elosztott hibrid topológia | [Skálázási egységek kipróbálása osztott hibrid topológiában](../cloud-edge/cloud-edge-try-out.md) |
| Kettős írás | [Igény szerinti szinkronizálás a Supply Chain Management árképzés motorral](../../fin-ops-core/dev-itpro/data-entities/dual-write/pricing-engine.md) |
| Raktárkezelés | [Kiadás raktárba](../warehousing/release-to-warehouse-process.md) |

## <a name="additional-resources"></a>További erőforrások

### <a name="platform-updates-for-finance-and-operations-apps"></a>A pénzügyi és az üzemeltetési alkalmazások platformfrissítései

A Microsoft Dynamics 365 Supply Chain Management 10.0.27 platformfrissítéseket tartalmaz. A további [tudnivalókat lásd a Pénzügyi és üzemeltetési alkalmazások 10.0.27-es verziójának Platformfrissítései (2022. július)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-27.md).

### <a name="bug-fixes"></a>Hibajavítások

Ha további tájékoztatást szeretne kapni a 10.0.27 részét képező frissítésekben található hibajavításokról, lépjen be a Lifecycle Services (LCS) szolgáltatásokba, és tekintse meg a [Tudásbázis cikket](https://fix.lcs.dynamics.com/Issue/Details?bugId=673271).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 és ipari felhők: 2022-es 1. kiadási hullám csomag

Kíváncsi a bármelyik üzleti alkalmazásával vagy platformjával kapcsolatos, közelgő és a közelmúltban bevezetett lehetőségekre?

Tekintse meg a [Dynamics 365 és ipari felhők: 2022-es 1. kiadási hullám csomag](/dynamics365-release-plan/2022wave1/) tartalmát. A részleteket minden apró információmorzsáig bezárólag egyetlen dokumentumban rögzítettük, amelyet felhasználhat a tervezés során.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Eltávolított és elavult Supply Chain Management szolgáltatások

A [cikk Eltávolított Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) vagy elavult funkciói olyan funkciókat írnak le, amelyek már el vannak távolítva, illetve amelyek már el vannak távolítva vagy elavultak az Ellátásilánc-kezeléshez.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Mielőtt a funkciót eltávolítanának a termékből, [Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) az értékcsökkenési értesítés 12 hónappal az eltávolítás előtt törlődik az Eltávolított vagy elavult funkciókból.

Olyan módosítások esetén, amelyek csak a fordítási időt érintik, de binárisan kompatibilisek a tesztkörnyezettel és a termelési környezettel, az elavulási idő 12 hónapnál rövidebb lesz. Ezek általában olyan funkcionális frissítések, amelyeket a fordítón kell elvégezni.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]


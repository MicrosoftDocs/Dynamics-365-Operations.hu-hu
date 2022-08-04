---
title: Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.28 szolgáltatásban (2022. augusztus)
description: Ez a témakör a Microsoft Dynamics 365 Supply Chain Management 10.0.28 verziójában új vagy módosult funkciókat ismerteti.
author: kamaybac
ms.date: 05/27/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2022-05-27
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 7e17127ff6ef6c52034b8aa5e0c8404772363ca9
ms.sourcegitcommit: 529fc10074b06f4c4dc52f2b4dc1f159c36e8dbc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/22/2022
ms.locfileid: "9186519"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10028-august-2022"></a>Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.28 szolgáltatásban (2022. augusztus)

[!include [banner](../includes/banner.md)]

Ez a cikk felsorolja azokat a funkciókat, amelyek vagy újak, vagy módosulnak a Microsoft Dynamics 365 Supply Chain Management 10.0.28-as verziójában. Ennek a verziónak a buildszáma több 10.0.1264, és a következő ütemezésben érhető el:

- **Kiadás előzetes verziója:** 2022. május
- **A kiadás általános elérhetővé tétele (saját frissítés):** 2022. július
- **A kiadás általános elérhetővé tétele (automatikus frissítés):** 2022. július

## <a name="features-included-in-this-release"></a>A verzióban található funkciók

Ez a kiadás a következő táblázatban felsorolt funkciókat tartalmazza: Előfordulhat, hogy a cikk frissítése a cikk eredeti közzététele után a buildhez hozzáadott funkciókat is tartalmazza.

| Szolgáltatásterület | Szolgáltatás | További információ | Engedélyezte:   |
|---|---|---|---|
| Készlet és logisztika | [Partraszállítási költségintegrációs entitások harmadik fél fuvarozói számára](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/landed-cost-integration-third-party-freight-forwarders) | [Partraszállási költség entitásai – áttekintés](../landed-cost/landed-cost-entities-overview.md) | Alapértelmezés szerint engedélyezve |
| Tervezés | [Igényvezérelt anyagigény-tervezés (DDMRP)](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/demand-driven-material-requirements-planning-ddmrp) | [Igényvezérelt anyagigény-tervezés – áttekintés](../master-planning/planning-optimization/ddmrp-overview.md) | Funkciókezelés:<br>*(Előzetes verzió) DDMRP a Tervezési optimalizáláshoz* |
| Tervezés | [Tervezési optimalizálás támogatása ígérő (CTP) funkciókhoz](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-capable-to-promise-ctp) | Hamarosan | Funkciókezelés:<br>*(Előzetes verzió) CTP a Tervezési optimalizáláshoz* |
| Tervezés | [Tervezési optimalizálás támogatása eltarthatósági idő esetén](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-shelf-life) | Hamarosan | Alapértelmezés szerint engedélyezve |

## <a name="feature-enhancements-included-in-this-release"></a>A kiadásban található funkciófejlesztések

Ez a kiadás a következő táblázatban felsorolt funkciófejlesztéseket tartalmazza: Ezek közül mindegyik fejlesztés egy már meglévő funkciót fejleszt tovább. Mivel fejlesztésekről van szó, nem szerepelnek a [kiadási tervben](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Alapértelmezés szerint mindegyik fejlesztés ki van kapcsolva (hacsak nincs másképpen jelezve), így biztos lehet abban, hogy nem ütköznek a meglévő testreszabásokkal vagy beállításokkal.

Ha bármelyik funkciót be szeretné kapcsolni, akkor ezt a [funkciókezelésben kell megtenni.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)

| Modul | Funkcióneve a funkciókezelésben | További információ |
|---|---|---|
| Készlet- és raktárkezelés | Annak engedélyezése, hogy a vállalatok közötti aktuális készlet csak nem nulla mennyiséget mutathasson | Ezzel a funkcióval eldöntheti, hogy a nulla készletmennyiségű cikkek is bekerülnek-e a vállalatközi készlet listájába. Ezt a **beállítást** úgy lehet szabályozni, hogy a vállalatközi aktuális lista beállításában a nulla aktuális készletmennyiségű cikkek ne mutassanak, **ez** a funkció hozzáadja a Készlet- és raktárkezelési paraméterek laphoz. |
| Készlet- és raktárkezelés | (India) A transzferár-szabályoknál hagyja figyelmen kívül a helyet, ha a „Feladó raktár kódja” beállítása „Mind” | <p>Ez a funkció csak az indiai honosításra vonatkozik. Ez teszi a készletátvitel során a cikkek transzferárának beállítását még inkább.</p><p>Az át transzferárakat az egyes cikkek áthozó árképzési szabályokkal való beállításával lehet beállítani. Ennek a konfigurálásnak az egyik módja, ha egy olyan szabálysort is beállít, amelyben a **Cél** raktárkód mező az Összes beállításra *van állítva*. Ez a beállítás azt jelzi, hogy a sorban meghatározott áthozott árnak attól függetlenül érvényesnek kell lennie, hogy a cikket kitárlják. Ha ez a funkció engedélyezve van, **·** *akkor* az olyan árszabályok átvitele, amelyekben a Cél raktárkód mező beállítása Mind, figyelmen kívül hagyja a Hely **beállítást.** Ennek megfelelően a szabály az átrendelésen megadott helytől függetlenül érvényes lesz. Valószínűleg ez a viselkedés várható, mivel a hely a tárolási dimenzióhierarchiában a raktár alatt van.</p><p>E szolgáltatás nélkül a rendszer csak akkor alkalmazza az ilyen típusú szabályokat, ha az átrendelt rendelés helye pontosan megegyezik azzal a helyről, amely a szabályhoz be van állítva. (Ha a szabályhoz üres hely van beállítva, a rendszer csak azokra az átvitelrendelésre alkalmazza a szabályt, amelyeknél a hely üres értékkel még be van állítva.)</p> |
| Készlet- és raktárkezelés | Aktuális készlet jelentés adatainak tisztítása | Ez a funkció lehetőséget nyújt az *Aktuális készlet jelentés tárolási jelentésének létrehozásához használt adatok tisztítására*. |
| Gyártásvezérlés | Projekttevékenységek hozzárendelése szolgáltatási szerződéshez és szervizrendelési sorhoz | Ez a funkció hozzáad egy Projekttevékenység nevű mezőt a **szolgáltatási** szerződéshez és a szervizrendeléssorhoz, így beállíthatja számukra a projekttevékenységet. A funkció segít megakadályozni a blokkolási hibákat, amikor feladja a szolgáltatáskezelési projekt olyan naplóit, amelyekhez projekttevékenységet kell beállítani.  |
| Raktárkezelés | Manuális transzfersor kitárolási szolgáltatása felügyeleti vagy hasonló megbízható felhasználók számára | Ez a funkció lehetővé teszi a rendszergazdák számára, hogy manuálisan kitárják az áthozott sorokhoz kapcsolódó készlettranzakciókat. A sorok olyan sorokat tartalmaznak, amelyek már ki vannak adva a raktárba. A rendszergazdáknak csak kivételes esetekben szabad ezt a kitárolást tenni, például ha a rendszer sérült állapotban van. |

## <a name="new-and-updated-documentation-resources"></a>Új és frissített dokumentáció-erőforrások

Nemrégiben hozzáadta vagy jelentősen frissítettük a következő súgócikkeket. Ezek a cikkek nem feltétlenül kapcsolódnak az ehhez a verzióhoz hozzáadott új funkciókhoz, mint azt az előző szakaszok felsorolják. Ugyanakkor előfordulhat, hogy a meglévő szolgáltatásokból többet lehet kihozni.

| Szolgáltatásterület | Új vagy frissített cikkek |
|---|---|
| Költségkezelés | [Rögzített bevételezési ár](../cost-management/fixed-receipt-price.md) |
| Költségkezelés | [Készlet költségszámítása – gyakran ismételt kérdések](../cost-management/inventory-costing-faq.md) |
| Költségkezelés | [Feladás költségszámlára könyvelési elv](../cost-management/post-to-charge-account-accounting-principle.md) |
| Készletgazdálkodás | [Készlettranzakció részletei](../inventory/inventory-transactions-details.md) |

## <a name="additional-resources"></a>További erőforrások

### <a name="platform-updates-for-finance-and-operations-apps"></a>A pénzügyi és az üzemeltetési alkalmazások platformfrissítései

A Microsoft Dynamics 365 Supply Chain Management 10.0.28 platformfrissítéseket tartalmaz. A további [tudnivalókat lásd a Pénzügyi és üzemeltetési alkalmazások 10.0.28-as verziójának Platformfrissítései (június 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-28.md).

### <a name="bug-fixes"></a>Hibajavítások

Ha további tájékoztatást szeretne kapni a 10.0.28 részét képező frissítésekben található hibajavításokról, lépjen be a Lifecycle Services (LCS) szolgáltatásokba, és tekintse meg a [Tudásbázis cikket](https://fix.lcs.dynamics.com/Issue/Details?bugId=694438).

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


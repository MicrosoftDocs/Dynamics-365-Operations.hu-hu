---
title: Hitelkeretet a vevőknek
description: Ez a cikk a Dynamics 365 Supply Chain Management rendszer hitelkereteinek működéséről nyújt tájékoztatást.
author: Henrikan
ms.date: 09/15/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f7f15c0f15302c271fac7199b21b7bcd3dcfe88a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903869"
---
# <a name="credit-limits-for-customers"></a>Hitelkeretet a vevőknek

[!include [banner](../includes/banner.md)]

A hitelkeret beállítása lehetővé teszi maximális hitelösszeg meghatározását a vevők számára. Ha meg van adva a hitelkeretet, a rendszer automatikusan ellenőrzi, amikor egy felhasználó megpróbál frissíti egy dokumentumot. A hitelkeret túllépésekor egy üzenet jelenik meg a felhasználó számára. Ebben a cikkben áttekintés olvasható arról, hogyan működik a hitelkeret, és megválaszolja az alábbi kérdéseket:

-   Milyen dokumentumokhoz és folyamatokhoz ellenőrizhetem a hitelkeretet?

-   Hol konfigurálhatom a vevő fennmaradó hitelkeretének számítási módját?

-   Hol használja fel a rendszer a vevő fennmaradó hitelkeretével kapcsolatos adatokat?

-   Hol adhatom meg, hogy azonosításra legyen-e szükség a hitel megadásához a vevőnek, illetve azt a hitelkeret-összeget, amely megköveteli az azonosítást?

-   Hol határozhatom meg, hogy figyelmeztetés vagy hibaüzenet jelenjen-e meg a hitelkeret túllépésekor?

-   Hogyan adhatom meg az adott vevőhöz tartozó hitelkeret?

-   Hogyan ellenőrizhetem manuálisan az értékesítési rendelések hitelkeretét?

**Milyen dokumentumokhoz és folyamatokhoz ellenőrizhetem a hitelkeretet?**

Használja a **Kinnlevőségek paraméterei** képernyőt annak a megadásához, hogy mely dokumentumokhoz történjen meg a hitelkeret ellenőrzése. A képernyő módosításához a rendszeradminisztrátor (- SYSADMIN-) biztonsági szerepkör tagjának kell lennie. A következő dokumentumokhoz és folyamatokhoz ellenőrizheti a hitelkeretet:

-   Értékesítési rendelési számlák, a számlák feladásakor

-   Értékesítési rendelések szállítólevelei, a szállítólevél frissítésekor

-   Értékesítési rendelések sorok hozzáadásakor az **Értékesítési rendelés** képernyőn

-   Értékesítési rendelések, szolgáltatáson keresztül létrehozásakor

-   Szabadszöveges számlák, számlák feladásakor

Automatikus hitelkeret-ellenőrzés történik, ha a következők valamelyike be van állítva:

-   A **Kinnlevőségek paraméterei** képernyőn a **Hitelkeret típusa** mező értéke bármi más, mint **Nincs**. Minden vevő esetében történik hitelkeret-ellenőrzés.

-   A **Kinnlevőségek paraméterei** képernyőn a **Hitelkeret típusa** mező értéke **Nincs**, de a **Kötelező hitelkeret** be van jelölve a vevőhöz a **Vevők** képernyőn. Csak bizonyos vevők esetében történik hitelkeret-ellenőrzés.

Hitelkeretek ellenőrzéséhez a következő dokumentumok esetében további beállításokat is meg kell adnia.

|    Bizonylat                                    |    További beállítás                                                                                                             |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
|    Szabadszöveges számla                         |    A Kinnlevőségek paraméterei képernyőn, a Hitelminősítés területen jelölje ki ezt: Hitelkeret ellenőrzése a szabadszövegű számlán.     |
|    Értékesítési rendelés (manuálisan kell megadni)            |    A Kinnlevőségek paraméterei képernyőn, a Hitelminősítés területen jelölje ki ezt: Hitelkeret ellenőrzése az értékesítési rendeléseknél.           |
|    Értékesítési rendelés (elektronikusan bevételezett)     |    A Kinnlevőségek paraméterei képernyőn, az AIF területen jelölje ki ezt: Hitelkeret ellenőrzése az értékesítési rendeléseknél.                     |

**Hol konfigurálhatom egy vevő fennmaradó hitelkeretének számítási módját?**

A vevő fennmaradó hitelkeretének kiszámítására a következő módokon állíthatja be a Dynamics 365 megoldást:

-   A hitelkeret összevetése a vevői egyenleggel.

-   A hitelkeret összevetése a vevői egyenleggel és a szállítólevélen szereplő összegekkel.

-   A hitelkeret összevetése a vevői egyenleggel és minden nyitott tranzakciós tevékenységgel. Ebbe beletartoznak a szállítólevélen és az értékesítési rendelésen szereplő összegek.

Használja a **Kinnlevőségek paraméterei** képernyőt az összehasonlítandó adatok megadásához. A képernyő módosításához a rendszeradminisztrátor (- SYSADMIN-) biztonsági szerepkör tagjának kell lennie. A **Hitelkeret típusa** mezőben válassza ki, hogy történjen-e hitelkeret-ellenőrzés, és hogy milyen tranzakcióinformációkat kell felvenni a hitelkeret ellenőrzésekor. Válasszon a következő lehetőségek közül:

-   **Nincs** – Nem ellenőrzi a hitelkeretet. Ezt a beállítást felül lehet bírálni egy adott vevő esetében a **Kötelező hitelkeret** jelölőnégyzet bejelölésével a **Vevők** képernyőn. Ha ezt teszi, a hitelkeret ellenőrzése a vevői egyenleggel szemben történik.

-   **Egyenleg** – A rendszer összeveti a vevő egyenlegét a hitelkerettel.

-   **Egyenleg + szállítólevél vagy termékbevételezési bizonylat** – A hitelkeret összevetése a vevői egyenleggel és a szállításokkal.

-   **Egyenleg + Minden** – A hitelkeret összevetése a vevői egyenleggel, a szállításokkal és a nyitott rendelésekkel.

**Hol használja fel a rendszer a vevő fennmaradó hitelkeretével kapcsolatos adatokat?**

A vevő egyenlegével és a fennmaradó hitel összegével kapcsolatos információk kiszámítása és tárolása a korosítási pillanatkép létrehozásakor történik meg, és a **Beszedések** képernyőn jelenik meg. Az összegek, amelyek megjelennek a **Beszedések** képernyőn, nem tartalmazzák feltétlenül az összes tranzakciós tevékenységet, amíg létre nem jön egy új korosítási pillanatkép. További tudnivalókért lásd: [Beszedések és követelések a Kinnlevőségek modulban](/dynamicsax-2012/appuser-itpro/collections-and-credit-in-accounts-receivable).

A kijelölt dokumentumoktól függően a vevő egyenlegével és a fennmaradó hitel összegével kapcsolatos információk kiszámítása az értékesítési rendelés, a szállítólevél és a vevői számla frissítésekor történik meg. Ha az éppen használt dokumentum összege a hitelkeret túllépését okozna, egy üzenet jelenik meg.

**Hol adhatom meg, hogy azonosításra legyen-e szükség a hitel megadásához a vevőnek, illetve azt a hitelkeretet, amely megköveteli az azonosítást?**

Használja a **Kinnlevőségek paraméterei** képernyőt annak a megadásához, hogy szükséges-e azonosító, illetve az azonosítót megkövetelő hitelkeretösszeg megadásához.
A képernyő módosításához a rendszeradminisztrátor (- SYSADMIN-) biztonsági szerepkör tagjának kell lennie.

|    Mező                                    |    Leírás                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|---------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    A hitelhez azonosítás szükséges     |    Annak az azonosítástípusnak a kiválasztása, amelyet meg kell adni azoknál a vevőknél, amelyeknek a jogi személye hitelez. A mezőben kiválasztott lehetőség meghatározza, hogy mikor és milyen típusú információt kell megadni a Személyi szám mezőben a Vevők képernyőn: Nem – nincs szükség államilag kiállított azonosítóra, függetlenül a vevő hitelkeretétől.     Igen – egy államilag kiállított engedélyszámra vagy más államilag kiállított azonosítóra van szükség, ha a vevő hitelkerete nagyobb vagy egyenlő nullánál.     Minimumhatár – egy államilag kiállított engedélyszámra vagy más államilag kiállított azonosítóra van szükség, ha a vevő hitelkerete nagyobb vagy egyenlő annál a keretnél, amelyet ugyanennek a képernyőnek a vevő hitelkerete nagyobb vagy egyenlő annál a keretnél, amelyet ugyanennek a képernyőnek a mezőjében megadott.        |
|    Korlát                                    |    Annak a hitelkeretnek a megadása, amely felett a vevőknek államilag kiállított engedélyszámot vagy más azonosítót kell bemutatni.    Például a 2000 érték beírásával kötelezővé teheti, hogy a 2000 vagy nagyobb értékű hitelkerettel rendelkező vevők megadjanak egy azonosító számot, például a vezetői engedélyük számát.    Ez a mező akkor áll rendelkezésre, ha bejelölte a Minimumhatár lehetőséget a a hitelkártya-mező A hitelhez azonosítás szükséges mezőben.                                                                                                                                                                                                                                                                                                                                                                                                                                         |

**Hol határozhatom meg, hogy figyelmeztetés vagy hibaüzenet jelenjen-e meg a hitelkeret túllépésekor?**

Használja a **Kinnlevőségek paraméterei** képernyőt annak a megadásához, hogy figyelmeztetés vagy hibaüzenet jelenjen-e meg a hitelkeret túllépésekor. Ez a figyelmeztetés vagy hibaüzenet jelenik meg a felhasználói információbevitelkor vagy -feladáskor, vagy bekerül egy naplóba, ha egy elektronikus szolgáltatás dolgozza fel a dokumentumokat. A képernyő módosításához a rendszeradminisztrátor (- SYSADMIN-) biztonsági szerepkör tagjának kell lennie.

|    Mező                                                               |    Leírás                                                                                                                                                                                                                                                                                                                                                                                        |
|------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Hitelkeret túllépéséről értesítő üzenet (a Hitelminősítés területen)     |    Válassza ki a felhasználók számára a hitelkeret túllépése esetén küldött üzenetek megjelenítési módját. A következő lehetőségek közül választhat: Hiba – hibaüzenet jelenik meg. Ez általában leállítja az aktuális műveletet, és a konfliktust fel kell oldani, addig nem mehet tovább a folyamat.     A. figyelmeztetés – figyelmeztető üzenet jelenik meg, de a folyamat mehet tovább.                     |
|    Hitelkeret túllépéséről értesítő üzenet (az AIF területen)               |    Adja meg, hogyan legyenek továbbítva a túllépett hitelkeretre vonatkozó üzenetek a naplóba. A következő lehetőségek közül választhat: Hiba – hibaüzenet jelenik meg a Kivételek képernyőn, és a dokumentumot nem lehet feldolgozni, amíg a hiba meg nem oldódott.     A. figyelmeztetés – figyelmeztető üzenet jelenik meg a Kivételek képernyőn, de a folyamat mehet tovább.        |

**Hogyan adhatom meg az adott vevőhöz tartozó hitelkeret összegét?**

Használja a **Vevők** képernyőt az adott vevőhöz tartozó hitelkeret összegének megadására. A Vevő alapadatainak karbantartása (CustCustomersMaintain) feladat hozzárendelésével rendelkező biztonsági szerepkör tagjának kell lennie ahhoz, hogy ezen a képernyőn módosításokat végzhessen.

1.  Kattintson a következőre: **Kinnlevőségek** \> **Közös** \> **Vevők** \> **Minden vevő**. Kattintson duplán egy vevőkódra.

2.  A **Vevők** képernyő Művelet ablakában kattintson a **Szerkesztés** elemre.

3.  A **Hitelkeret** mezőben adjon meg egy devizaösszeget. Az értéknek magasabbnak kell lennie, mint nulla (0), és a hitelkeret összegeként lesz használva.

4.  Ha szükséges, írjon be licencszámot vagy más államilag kiállított azonosítót a **Személyi szám** mezőbe.

> [!NOTE]
> A **Kinnlevőségek paraméterei** képernyőn, általában ki van választva egy hitelkerettípus. Ha azonban a hitelkerettípus beállítása **Nincs**, be kell jelölnie a **Kötelező hitelkeret** jelölőnégyzetet is a **Vevők** képernyőn a vevő hitelkeretének összevetéséhez a vevői egyenleggel. A hitelkártyatípusokkal kapcsolatos további tudnivalókat lásd: „Milyen dokumentumokhoz és folyamatokhoz ellenőrizhetem a hitelkeretet?” Ebben a cikkben. 

**Hogyan ellenőrizhetem manuálisan az értékesítési rendelések hitelkeretét?**

Néha előfordulhat, hogy manuálisan kell ellenőrizni a vevő hitelkeretét. Például előfordulhat, hogy manuálisan ellenőrzi egy vevő hitelkeretét az értékesítési rendelés létrehozának megkezdése előtt. Használhatja az **Értékesítési rendelés** képernyőt a hitelkeret manuális ellenőrzéséhez. Az Értékesítési rendelés karbantartása (SalesOrderMaintain) feladat hozzárendelésével rendelkező biztonsági szerepkör tagjának kell lennie ahhoz, hogy ezen a képernyőn módosításokat végzhessen.

1.  Kattintson ide: **Értékesítés és marketing** \> **Közös** \> **Értékesítési rendelések** \> **Minden értékesítési rendelés**. Kattintson duplán egy értékesítési rendelésre.

2.  Az **Értékesítési rendelés** képernyőn, a Művelet ablakban, a **Kezelés** lapon, kattintson a **Hitelkeretének ellenőrzése** elemre.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
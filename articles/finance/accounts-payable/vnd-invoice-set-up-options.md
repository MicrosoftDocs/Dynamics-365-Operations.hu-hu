---
title: A szállítói számla automatizálásának beállítási lehetőségei (előzetes verzió)
description: Ez a témakör a szállítóiszámla-automatizálás beállításának és konfigurálásának lehetőségeit ismerteti.
author: sunfzam
ms.date: 10/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-30
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 8e5aac8f108cf9a46c80c61891b057b8dc2b4672
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/23/2021
ms.locfileid: "7675469"
---
# <a name="setup-options-for-vendor-invoice-automation"></a>A szállítói számla automatizálásának beállítási lehetőségei

[!include [banner](../includes/banner.md)]

Ez a témakör a szállítóiszámla-automatizálás beállításának és konfigurálásának lehetőségeit ismerteti. A számlázásautomatizáló szolgáltatások a következő típusú beállítási paramétereket használják:

- Az előlegek automatikus alkalmazásának paraméterei az importált számlákon.
- Az importált szállítói számlák munkafolyamat-rendszerbe történő beküldésének paraméterei és a feladott terméknyugta sorainak egyeztetése a függőben lévő szállítói számlák soraival.
- Az automatizálás háttérfeladatok feldolgozásának paraméterei. A folyamatautomatizálási keretrendszer segítségével importált szállítói számlákat küldhet a munkafolyamat-rendszerbe. A program a feladott szállítólevél sorainak a függőben lévő szállítói számlasorok számára történő automatikus egyeztetését, valamint a termék-visszaigazolási sorokhoz automatikusan egyeztetett manuális számlákhoz kapcsolódó számlaegyeztetési ellenőrzések végrehajtását is használja. A különböző üzleti folyamatok ezt a keretrendszert alkalmazzák annak meghatározására, hogy a kiválasztott folyamat milyen gyakorisággal fusson. A **terméknyugta egyeztetése a számlasorokkal** és a **Szállítói számlák beküldése a munkafolyamatba** háttérfolyamatokhoz elérhető gyakoriságok az **Óra** és a **Napi**.

Egy adott háttérfeladat beállításához vagy azzal kapcsolatos információk megtekintéséhez lépjen a **Rendszerfelügyelet \> Beállítás \> Folyamatautomatizációk** felületre, majd válassza ki a **Háttérfeladat** fület.

Az importálás folyamatától a szállítói számla feladásáig teljes körű automatizálás megvalósításához be kell állítania egy szállítóiszámla-munkafolyamatot. A munkafolyamat beállításához lépjen a **Kötelezettségek > Beállítás > Kötelezettségek munkafolyamatai** felületre. Ha azt szeretné, hogy a számla manuális beavatkozás nélkül is feldolgozható legyen az elejétől a végéig, akkor a munkafolyamat-konfigurációban szerepelnie kell egy automatikus feladási feladatnak.

## <a name="parameters-for-automatically-applying-prepayments-in-imported-invoices"></a>Az előlegek automatikus alkalmazásának paraméterei az importált számlákon

- **Előleg automatikus alkalmazása az importált számlákra** – Ha ez a beállítás **Igen**, a rendszer a szállítói számlák importálása esetén automatikusan keresi a megfelelő beszerzési rendelés meglévő előlegeit. Ha alkalmazható előlegek találhatók, egy további sor hozzáadódik az előlegek alkalmazáshoz az importált szállítói számlákon.
- **Követési automatizálási folyamat letiltása sikertelen előlegalkalmazás esetén** – Ha ez a beállítás **Igen**, akkor a program letiltja a számlákat, ha nem lehet előleget alkalmazni. A többi automatizált folyamathoz, például a nyugtaegyeztetési folyamathoz és a munkafolyamatba történő küldéséhez hasonló módon a számlaautomatizálási folyamat addig nem felveszi a zárolt számlákat, amíg az előleget nem manuálisan nem alkalmazzák. 

## <a name="parameters-for-submitting-imported-vendor-invoices-to-the-workflow-system"></a>Az importált szállítói számlák munkafolyamat-rendszerbe történő elküldésének paraméterei

Az importált szállítói számlák munkafolyamat-rendszerbe történő elküldéséhez speciális paramétereket kell használni. Egyes paraméterek ezenkívül a feladott terméknyugta sorainak a függőben lévő szállítói számlák soraival való egyeztetésére szolgálnak. A **Kötelezettségek paraméterei oldal** **Szállítói számla automatizálása** lapján a beállítandó paramétereket a következő szakaszok között kell elosztani:

- Szállítói számlák munkafolyamata
- Termékbevételezési bizonylatok automatikus egyeztetése

A következő paraméterek állnak rendelkezésre:

- **Importált számlák automatikus elküldése a munkafolyamatba** – Ha ezt a beállítást **Igen** értékűre állítja, akkor a program az importált számlákat automatikusan beküldi a munkafolyamat-rendszerbe. Ha a beállítás értéke **Nem**, akkor a számlákat manuálisan kell elküldenie. Ha ezt a beállítást **Igen** értékre állítja, akkor az eredmények importálásától a feladásig engedélyezheti az érintés nélküli folyamatot.

    Ez a beállítás csak akkor állítható **Igen** értékre, ha az Ön szervezetéhez aktív szállítóiszámla-munkafolyamatot állítottak be. A munkafolyamat beállításához lépjen a **Kötelezettségek \> Beállítás \> Kötelezettségek munkafolyamatai** felületre.

- **Terméknyugták egyeztetése a számlasorokkal az automatikus beküldés előtt** – Ha ezt a beállítást **Igen** értékűre állítja, akkor az importált számla nem küldhető be automatikusan a munkafolyamat-rendszerbe mindaddig, amíg az egyeztetett terméknyugta mennyisége nem egyezik meg a számla szerinti mennyiséggel. Ha ezt a beállítást **Igen** értékre állítja, akkor engedélyezi a feladott terméknyugták automatikus egyeztetését olyan számlasorok esetében, amelyekhez háromirányú egyeztetési irányelvet határoztak meg. Ez a folyamat addig fog futni, amíg az egyeztetett terméknyugták mennyisége nem egyezik meg a számla szerinti mennyiséggel. Ezen a ponton a program automatikusan elküldi a számlát a munkafolyamat-rendszernek.

    A „Terméknyugták egyeztetése a számlasorokkal az automatikus beküldés előtt” lehetőség akkor érhető el, ha a **Számlaegyeztetés érvényesítésének engedélyezése** beállítást kiválasztotta. Ha ezt a lehetőséget kiválasztotta, akkor a **Terméknyugták automatikus egyeztetése a számlasorokkal** beállítás automatikusan kiválasztottá válik.

- **Számított összegek egyezzenek az automatikus munkafolyamatba küldéshez tartozó importált összegekkel** – Ha ezt a beállítást **Igen** értékre állítja, akkor a számla nem küldhető el automatikusan a munkafolyamat-rendszerbe mindaddig, amíg a számlára kiszámított összegek nem egyeznek az importált összegekkel. Ha ezt a beállítást **Nem** értékre állítja, akkor a számla automatikusan elküldhető a munkafolyamat-rendszerbe, de nem lehet feladni addig, amíg a kiszámított összegeket nem korrigálja úgy, hogy egyezzenek az importált összegekkel. Ha nem importálja a számlaösszeget vagy az áfaösszeget, akkor ezt a beállítást **Nem** értékre kell állítani.
- **Terméknyugták automatikus egyeztetése a számlasorokkal** – Ha ezt a beállítást **Igen** értékűre állítja, akkor a háttérben történő feldolgozással elvégezhető a feladott terméknyugták automatikus egyeztetése azokkal a számlasorokkal, amelyekhez háromirányú egyeztetési irányelvet határoztak meg. Ezt a folyamatot addig futtatja a program, amíg az egyeztetett terméknyugta mennyisége nem egyezik a számla mennyiségével, vagy amíg az **Automatikus egyeztetési próbálkozások száma** mezőben megadott értéket el nem éri. A folyamat addig futtatható, amíg a számlát el nem küldik a munkafolyamat-rendszernek.

    Ez a mező csak akkor elérhető, ha a **Számlaegyeztetés ellenőrzésének engedélyezése** lehetőséget kiválasztotta.

    Ha a **Terméknyugták egyeztetése a számlasorokkal az automatikus beküldés előtt** lehetőséget **Igen** értékűre állítja, akkor ez a beállítás nem állítható **Nem** értékre. Ahhoz, hogy ezt a beállítást **Nem** értékűre állítsa, először a **Terméknyugták egyeztetése a számlasorokkal az automatikus beküldés előtt** lehetőséget **Nem** értékűre kell állítania.

- **Automatikus egyeztetési próbálkozások száma** – Kiválaszthatja, hogy hány alkalommal próbálja meg a rendszer egyeztetni a terméknyugtákat egy adott számlasorral, mielőtt a folyamatot sikertelenként lezárná. Ha a rendszer eléri a megadott próbálkozásszámot, a számla törlődik az automatizált feldolgozásból.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]

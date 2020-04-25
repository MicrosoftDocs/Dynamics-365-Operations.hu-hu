---
title: Azonosítótábla fogadása a Raktárkezelő mobilalkalmazáson keresztül
description: Ez a témakör azt mutatja be, hogyan lehet beállítani a Raktárkezelő mobilalkalmazást a tényleges készlet fogadására használt azonosítótábla-feldolgozási folyamathoz.
author: perlynne
manager: tfehr
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-03-31
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 98cd608edea1d5365d0d3532244f1fcdb6293d3c
ms.sourcegitcommit: 3a823444005d316bd95fc663e2dbc8252ac7d93a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261338"
---
# <a name="license-plate-receiving-via-the-warehousing-mobile-app"></a>Azonosítótábla fogadása a Raktárkezelő mobilalkalmazáson keresztül

Ez a témakör azt mutatja be, hogyan lehet beállítani a Raktárkezelő mobilalkalmazást a tényleges készlet fogadására használt azonosítótábla-feldolgozási folyamat támogatásához.

Ezen funkció segítségével gyorsan rögzítheti az előzetes kiszállítási értesítéshez (ASN) kapcsolódó bejövő készlet bevételezését. A rendszer automatikusan létrehoz egy ASN-t, amikor a raktárkezelési folyamatokat egy átmozgatási rendelés szállítására használják. A beszerzési rendelés folyamatahoz egy ASN manuálisan is rögzíthető, vagy automatikusan importálható a bejövő ASN adatentitás folyamata segítségével.

Az ASN-adatok a rakományokhoz és a szállítmányokhoz a *csomagolási struktúrákon* keresztül kapcsolhatók, ahol a raklapok (a szülő azonosítótáblák) tartalmazhatnak eseteket (beágyazott azonosítótáblák).

> [!NOTE]
> Hogy csökkentse a készlettranzakciók számát, amikor beágyazott azonosítótáblákkal rendelkező csomagolási struktúrák vannak használatban a rendszer rögzíti a fizikai aktuális készletet a szülő azonosítótáblára. Ha azt szeretné, hogy a rendszer a tényleges aktuális készletet a szülő rendszámtábla és a beágyazott rendszámtábla között a csomagolási struktúra adatainak megfelelően mozgassa, a mobileszköznek egy olyan menüelemet kell biztosítania, amely a *Csomagolás beágyazott azonosítótáblákhoz* munkalétrehozási folyamaton alapul.

<!-- To be used later (will require further editing):
## Warehousing mobile device app processing

When a worker scans an incoming license plate ID, the system initializes a license plate receiving process. Based on this information, the content of the license plate (data coming from the ASN) gets physically registered at the inbound dock location. The flows that follow will depend your business process needs.

## Work policies

As with (for example) the *Report as finished* mobile device menu item process, the license plate receiving process supports several workflows based on the defined setup.

### Work policies with work creation

Registration of physical on-hand where either the same warehouse worker immediately process a put-away work process following the inbound receiving (License plate receiving and put away) or where the registration and put away process gets handled as two different warehouse operations (License plate receiving) following the processing of the put-away work by using the existing work process via another mobile device menu item.

## Work policies without work creation

You can use the license plate receiving process without creating work by using the *License plate receiving without creating work* feature.

By defining **Work policies** with a **Work order type** of *Transfer receipt* and/or *Purchase orders*, and using the **Process** for **License plate receiving (and put away)**, the two Warehousing app process:

- License plate receiving
- License plate receiving and put away

will not create work, but only register the inbound physical inventory on the license plate at the inbound receiving dock.

For more information about the *Report as finished* production scenario, see the [Warehouse work policies overview](warehouse-work-policies.md).

-->

## <a name="show-or-skip-the-receiving-summary-page"></a>A bevételezési összesítő lap megjelenítése vagy kihagyása

Az *Annak szabályzása, hogy meg legyen-e jelenítve egy fogadás összegzése lap a mobileszközökön* funkció használatával kihasználhatja egy további részletes Raktári alkalmazásfolyamat előnyeit az azonosítótábla-fogadási folyamat részeként.

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához. A **Funkció kezelése** munkaterületen ez a funkció a következő módon van listázva:

- **Modul:** *Raktárkezelés*
- **Funkció neve:** *Annak beállítása hogy megjelenjen-e bevételezési összesítő lap a mobileszközökön*

Ha ez a funkció be van kapcsolva, akkor az azonosítótábla fogadására és betárolására szolgáló menüelemek tartalmazzák a **Fogadó összesítő lap megjelenítése** beállítást. Ez a beállítás a következő lehetőségeket biztosítja:

- **Részletes összefoglalás megjelenítése** – Az azonosítótábla fogadása során a dolgozók egy külön lapot fognak látni, amely a teljes ASN-információt jeleníti meg.
- **Az összefoglalás kihagyása** – A dolgozók nem fogják látni a teljes ASN-információt. A raktári dolgozók nem állíthatnak be intézkedési kódot sem, illetve kivételeket adhatnak meg a bevételezési folyamat során.

## <a name="prevent-transfer-ordershipped-license-plates-from-being-used-at-warehouses-other-than-the-destination-warehouse"></a>Átmozgatási rendeléssel szállított azonosítótáblák használatának megakadályozása a célraktártól eltérő raktárban

Az azonosítótábla-bevételezési folyamat nem használható, ha az ASN tartalmaz egy rendszámtábla-azonosítót, amely már létezik, és tényleges aktuális adatokkal rendelkezik egy olyan raktári helyen, amely nem az a raktári hely, ahol az azonosítótábla regisztrációja történik.

Az átmozgatási rendelés esetében, amikor az átmozgatási raktár nem követi nyomon az azonosítótáblákat (és ezért nem követi a tényleges aktuális készletet azonosítótáblánként) használhatja a *Átmozgatási rendeléssel szállított azonosítótáblák használatának megakadályozása a célraktártól eltérő raktárban* funkciót, amellyel megakadályozható az átvitel alatt lévő azonosítótáblák tényleges aktuális frissítése.

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához. A **Funkció kezelése** munkaterületen ez a funkció a következő módon van listázva:

- **Modul:** *Raktárkezelés*
- **Funkció neve:** *Átmozgatási rendeléssel szállított azonosítótáblák használatának megakadályozása a célraktártól eltérő raktárakban*

Ha elérhetővé szeretné tenni ezt a funkciót, hajtsa végre az alábbi lépéseket.

1. Lépjen a **Raktárkezelés \> Beállítás \> Raktárkezelési paraméterek** részre.
1. Az **Általános** lap **Azonosítótáblák** gyorslapján a következő értékek valamelyikére állítsa be a **Tranzitraktár azonosítótábla-irányelvei** mezőt:

    - **Nem nyomon követett rendszámtábla újrafelhasználásának engedélyezése** – A rendszer ugyanúgy működik, mint amikor a *Átmozgatási rendeléssel szállított azonosítótáblák használatának megakadályozása a célraktártól eltérő raktárakban* funkció nem érhető el. Ez az érték az alapértelmezett beállítás a funkció első aktiválása alkalmával.
    - **Nem nyomon követett azonosítótáblák újrahasznosításának megakadályozása** – Csak a szállítót azonosítótáblákhoz kapcsolódó aktuális frissítések engedélyezettek a cél raktárban mindaddig, amíg az átmozgatási rendelés nem érkezett meg.

## <a name="more-information"></a>További információ

<!-- To read more about inbound loads, see [Link for Inbound load (Olga's doc.)] -->

A mobileszköz-menüelemek beállításával kapcsolatos további tudnivalókat lásd: [Mobileszközök beállítása raktári munkához](configure-mobile-devices-warehouse.md).

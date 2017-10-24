---
title: "Rendelésfeldolgozási beállítások meghatározása"
description: "Ez a témakör a következővel kapcsolatban kínál információkat: hívásközpontoknak szóló rendelések feldolgozása a Microsoft Dynamics 365 for Retail használatával."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 78973
ms.assetid: 09fca083-ac0d-4f30-baf2-bb00a626be12
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: a0f3d1aea49f0251ecc68e70b4b6054e1813c8ad
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-order-processing-options"></a>Rendelésfeldolgozási beállítások meghatározása

[!include[banner](includes/banner.md)]


Ez a témakör a következővel kapcsolatban kínál információkat: hívásközpontoknak szóló rendelések feldolgozása a Microsoft Dynamics 365 for Retail használatával. 

A Retail számos kiskereskedelmi csatornát támogat, például online áruházakat, online piactereket, fizikailag létező üzleteket és hívásközpontokat. Egy telefonos ügyfélszolgálattól dolgozók telefonon végrehajtása a vevői rendelések és értékesítési rendelések létrehozása. Ez a témakör leírja, hogyan egy telefonos ügyfélszolgálattól létrehozására és konfigurálására a hívás beállításai. Minden egyes hívásközpont lehet a saját felhasználói, fizetési módok, árcsoportok, pénzügyi dimenziók és szállítási módok. Beállítható, hogy ezek a beállítások a hívásközpont létrehozásakor. **Fontos:** Mielőtt használni lehetne a hívásközpont munkafolyamatait, amikor a felhasználó értékesítési rendeléseket hoz létre, a felhasználót hozzá kell rendelni a hívásközponthoz hívásközpont felhasználójaként. A **Hívásközpont** oldal használatával engedélyezheti vagy letilthatja a csak a hívásközpontokra jellemző funkciócsoportokat. A következő szolgáltatáscsoportok engedélyezhető:

-   **Rendelés teljesítése**– Ebbe a csoportba tartoznak a fizetéshez és a rendelés teljesítéséhez kötődő funkciók az **Értékesítési rendelés** oldalon.
-   **Irányított eladás** – Ebbe a csoportba tartoznak a forráskódokhoz, parancsfájlokhoz és a katalógus kérelmekhez kötődő funkciók.

Miután engedélyezte ezeket a funkciókat a hívásközpont beállításainál, elérhetővé válnak az **Értékesítési rendelés** oldalon azon felhasználók számára, akiket a hívásközponthoz társítottak. A legtöbb szolgáltatás szükséges további beállítási, használat előtt. A képek és parancsfájlok engedélyezettek a konkrét hívásközpont irányított eladási beállításának részeként. Ha ezen funkciók engedélyezve vannak, a parancsfájlok és termékképek megjelennek az adatterület-panelen, az **Értékesítési rendelés** oldalon. A termék beállított alapértelmezett kép jelenik meg. A parancsfájlok egy cikkhez, katalógushoz, vevőhöz vagy egy katalógus kontextusában szereplő cikkhez konfigurálhatók. A hívásközpont-rendelések további részleteket is megjeleníthetnek egy adott rendelési sorhoz tartozó ár származtatásáról. Például a rendelések mutatják az alkalmazott kedvezményeket. Ezt a funkciót a **Kinnlevőségek** &gt; **Beállítás** &gt; **Kinnlevőségek paraméterei** &gt; **Árak** &gt; **Ár részletei** menüpontban engedélyezheti. Az **Ár részletei** oldalhoz az **Értékesítésirendelés-sor** legördülőlistából férhet hozzá. A rendelési esemény nyomon követését használhatja ellenőrzési célokra, a műveletek megtekintéséhez, amelyek a rendelés életciklusának során történnek vagy egy adott felhasználó által végzett műveletek nyomon követésére. Például rögzítheti a műveletet minden alkalommal, amikor egy felhasználó létrehoz egy értékesítési rendelést, felfüggeszt egy rendelést, felülírja a költséget vagy frissít egy rendelési sort. A rendelési eseményeket beállíthatja, hogy nyomon tudja követni az adott felhasználók, felhasználói csoportok, vagy minden felhasználó műveleteit egy adott időszak során. Megtekintheti azokat a műveleteket, amelyek egy dokumentumon történtek a **Rendelési események** oldal megnyitásával a Műveleti ablaktáblán az adott dokumentum oldalán. A rendelési eseményeket az **Értékesítés és marketing** &gt; **Beállítás** &gt; **Események** &gt; **Rendelési események** részben lehet konfigurálni. Ha egy vevői rendelés nem szállítható időben, a vállalat automatikusan küldhet értesítést e-mail-üzeneteken keresztül a vevőnek a rendelési állapot indoklására, és hogy lehetővé tegye a vevő számára a rendelés visszamondását. Ha a késedelmet túlnyúlik a meghatározott küszöbértéket, a rendelés automatikusan lehet visszavonni. Legfeljebb három e-mail üzenet küldhető megadott időközönként:

1.  **Első visszamondási értesítés** – a vevő eldöntheti, hogy visszamondja-e a rendelést.
2.  **Második visszamondási értesítés** – a vevő eldöntheti, hogy visszamondja-e a rendelést.
3.  **Végleges visszamondási értesítés** – a rendszer érvényteleníti a rendelést, és a vevő erről értesítést kap.

Az áfamentességi az egyes vevőkkel és az Automatikus értesítés és érvénytelenítés folyamat termékek. A haszonkulcs-figyelmeztetés akkor jelenik meg, amikor a rendeléshez hozzáad egy cikket. A figyelmeztetésben fontos információk vannak a cikkről, többek között az árrés és a cikknyereségesség. Ennek az információnak a segítségével dönthet az esetleges árfelülvizsgálatról egy cikk értékesítési rendeléshez való hozzáadásakor. Beállítja például a kereskedelmi árrések küszöbértékét úgy, hogy legalább 40 százalék feletti költség legyen elfogadható egy cikkhez, de a 20-39 százalékos költség feletti küszöbérték megkérdőjelezhető. Ebben az esetben minden olyan cikk figyelmeztetést vált ki, amely 20 és 39 százalék közötti küszöbértékkel rendelkezik . Egyetlen cikk sem értékesíthető, amelynek kevesebb mint 20 százalék a költség feletti küszöbértéke, illetve ilyen esetben a cikk ára nem módosítható. A haszonkulcs-figyelmeztetések a **Kinnlevőségek** &gt; **Beállítás** &gt; **Kinnlevőségek paraméterei** &gt; **Haszonkulcs-figyelmeztetések** részben konfigurálhatók. Az alapértelmezett szabályok alapján a forgalmi adó-hozzárendelés beállításakor meghatározhatja a megfeleltetési prioritás cím elemeit. Megadhatja például, hogy az áfacsoport irányítószám szerinti megfeleltetése magasabb prioritást kapjon mint az áfacsoport állam szerinti megfeleltetése. Új vevőcímbejegyzések beírásakor az áfacsoport automatikusan hozzárendelésre kerül annak alapján, hogy a vevő címe hogyan felel meg az alapértelmezett szabályoknak és a meghatározott prioritás megfeleltetés szerint. Ezt a funkciót a **Főkönyvi paraméterek** oldalon konfigurálhatja.





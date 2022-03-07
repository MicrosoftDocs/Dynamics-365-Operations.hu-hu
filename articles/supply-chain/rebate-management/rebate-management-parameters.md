---
title: Visszatérítés-kezelés paraméterei
description: Ez a témakör a Visszatérítés-kezelési paraméterek oldalt ismerteti. Ez az oldal olyan beállításokat tartalmaz, amelyek befolyásolják a közzétételt, az állapotfrissítéseket, a számsorozatokat és egyéb viselkedéseket.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 0665ce41233308c814a514fccf3b73e20de64098
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576688"
---
# <a name="rebate-management-parameters"></a>Visszatérítés-kezelés paraméterei

[!include [banner](../includes/banner.md)]

A **Visszatérítés-kezelés paraméterei** oldal a **Visszatérítés-kezelés** modulban érvényes beállítások meghatározására használható. Ezek a beállítások befolyásolják a közzétételt, az állapotfrissítéseket, a számsorozatokat és egyéb viselkedéseket. Az ezen a lapon található beállítás megosztásra kerül jogi személyek között, és a megfelelő biztonsági engedélyekkel rendelkező felhasználók módosíthatják őket.

A **Visszatérítés-kezelés paraméterei** oldal megnyitásához lépjen a **Visszatérítés-kezelés \> Beállítások \> Visszatérítés-kezelés paraméterei** részre. Ezután állítsa be a következő alszakaszokban leírt módon a mezőket.

## <a name="rebate-management-tab"></a>Visszatérítés-kezelés lap

A következő táblázat felsorolja azokat a mezőket, amelyek elérhetők a **Visszatérítés-kezelés paraméterei** oldal **Visszatérítés-kezelés** lapján.

| Mező | Leírás |
|---|---|
| Alapértelmezett állapot | Válassza ki az összes új ajánlat alapértelmezett állapotát. A kiválasztáshoz rendelkezésre álló állapotértékek készletének meghatározásához használja a [**Visszatérítési állapotok** oldalt](rebate-statuses.md). |
| Feldolgozás dimenzió szerint | Adja meg, hogy a fedezeti, visszatérítési és leírási tranzakciókat pénzügyi dimenzió szerint kell-e feldolgozni. Ha ez a beállítás be van kapcsolva, a rendszer a forrástranzakciókból származó pénzügyi dimenziókat használ a céltranzakciókban. |
| Ellenőrizze, hogy korábban feladásra került-e | <p>Válassza ki a rendszer viselkedését, ha a fel nem adott visszatérítési tranzakciók feldolgozása ugyanazon időszakhoz többször történik:</p><ul><li>**Figyelmeztetés** – A rendszer lehetővé teszi a felhasználók számára, hogy felülbírálják az eredeti tranzakciósorokat, de figyelmeztetés jelenik meg.</li><li>**Hiba** – A rendszer megakadályozza, hogy a felhasználók felülbírálják az eredeti tranzakciósorokat, és hibaüzenet jelenik meg. |
| Naplók automatikus feladása | Adja meg, hogy a rendszer automatikusan feladja-e a javasolt naplókat. Ezek a naplók magukban foglalják a fedezetekhez és vevői levonásokhoz használt napi naplókat, valamint a szállítói adószámlanaplókat. |
| Szabadszöveges számlák automatikus feladása | Adja meg, hogy a rendszer automatikusan feladja-e a szabadszöveges számlákat. Ez a beállítás csak azokra a szabadszöveges számlákra vonatkozik, amelyek fizetési típusa *Adószámla vevői levonásai*. |
| Visszatérítési cikk rendelési hivatkozása | Válassza ki a visszatérítési folyamatból generált értékesítési és beszerzési rendelésekhez használható visszatérítési hivatkozást (*Nincs*, *Visszatérítés-kezelési ajánlat*, *Visszatérítés-kezelési szám*, *Visszatérítési tranzakció száma* vagy *Bizonylat megjegyzései*). |
| Igénylési folyamat használata | <p>Az igénylési folyamat használatához állítsa a beállítást *Igen* értékre. Ily módon megjelölheti a visszatérítés-kezelés által igényeltként vagy nem igényeltként létrehozott tranzakciókat, majd feladhatja csak az igényelt tranzakciókat.</p><p>Például kiszámíthatja a visszatérítéseket egy hónapnyi tranzakcióra, de a vevő két napot nem igényelten hagyott. Ebben az esetben a nem igényelt tranzakciók újra létrejönnek a *Feldolgozás* funkció következő időszakra történő következő futtatásakor.</p><p>Ha ezt a beállítást *Nem* értékre állítja, az összes igénylési tranzakció fel lesz adva.</p> |
| Rendeléstípus naplójának tartalmazása | Azokban az ügyletekben vagy ügyletsorokban, ahol a tranzakciótípus *Rendelés* értékre van állítva, ez a beállítás határozza meg, hogy a *Napló* típusú értékesítési rendelés szerepeljen-e. Rugalmasságot biztosít, ha az ilyen típusú rendeléseket olyan esetekben használják, amikor a visszatérítést még nem kell alkalmazni. |

## <a name="number-sequences-tab"></a>Számsorozatok lap

A **Visszatérítés-kezelés paraméterei** oldal **Számsorozatok** lapján számsorozatkódokat rendelhet a visszatérítés-kezelés által használt különböző számsorozatokhoz. Az alábbi táblázat az egyes számsorozatok célját ismerteti. A számsorozatokról a [Számsorozatok áttekintése](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md) és a kapcsolódó témakörökben olvashat bővebben.

| Hivatkozás | Leírás |
|---|---|
| Visszatérítés-kezelési ajánlat | A számsorozat minden visszatérítési ajánlathoz egyedi kulcsértéket rendel. Ez a kulcs az ajánlatok létrehozásakor használható. |
| Visszatérítés-kezelési szám | A számsorozat minden visszatérítéshez egyedi kulcsértéket rendel. Ez a kulcs a visszatérítési kapcsolatok azonosítására használható. |
| Visszatérítési tranzakció száma | A számsorozat minden visszatérítési tranzakcióhoz egyedi kulcsértéket rendel. Ez a kulcs a visszatérítési tranzakciók azonosítására használható. |
| Adószámla | A számsorozat minden visszatérítési számlához egyedi kulcsértéket rendel. Ezt a kulcsot a program a visszatérítési naplók automatikus feladásakor használja. |

## <a name="feature-visibility-tab"></a>Funkció láthatósága lap

A visszatérítés-kezelés a Microsoft Dynamics 365 Supply Chain Management számos gyakran használt oldalán biztosít szolgáltatásokat (mezőket és funkciókat). Ezek az oldalak értékesítési rendelésekhez és értékesítési ajánlatokhoz kapcsolódó oldalakat tartalmaznak. Ha visszatérítés-kezelést használ, akkor ezeket a funkciókat minden helyen láthatóvá kell tenni, mielőtt azokból haszna lenne. Ha nem használja a visszatérítés-kezelést, elrejtheti a funkciókat, hogy ne legyenek útban.

A **Visszatérítés-kezelés paraméterei** oldal **Funkció láthatósága** lapján állítsa az **Aktiválás** lehetőséget *Igen* beállításra, hogy a visszatérítés-kezelés funkciói minden helyen láthatók legyenek, ahol elérhetők. Állítsa *Nem* beállításra, ha el kell rejteni a **Visszatérítés-kezelés** modulon kívüli gyakori lapokon a funkciókat. Ugyanakkor, még ha *Nem* beállítás is van megadva, maga a modul, beleértve a **Visszatérítés-kezelés paraméterei** oldalt is, elérhető marad a hozzáféréshez megfelelő engedélyekkel rendelkező felhasználók számára.

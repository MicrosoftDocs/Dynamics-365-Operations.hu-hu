---
title: A Global Inventory Accounting által támogatott üzleti dokumentumok
description: Ez a témakör felsorolja azokat az üzleti dokumentumokat, amelyeket a Global Inventory Accounting támogat. Részletes példát mutat a beszerzési rendelés dokumentumokra is.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: cdb2d119e9b49887bb66fa737f97c3d91e5b793ceea1b2389072a02b5c463ba9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6726863"
---
# <a name="business-documents-supported-by-global-inventory-accounting"></a>A Global Inventory Accounting által támogatott üzleti dokumentumok

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Miután a Global Inventory Accounting bővítmény teljes mértékben be van állítva, készen áll a Microsoft Dynamics 365 Supply Chain Management szolgáltatásba bevitt készlettel kapcsolatos dokumentumok feldolgozására .

## <a name="supported-business-documents"></a>Támogatott üzleti dokumentumok

Az üzleti műveleteket két típusra osztjuk:

- **Naplóval rendelkező dokumentumok** – Ezek a dokumentumok tartalmazzák a termék nyugtát, a vásárlási számlát, a szállítólevelet és az értékesítési számla dokumentumait.
- **Naplóval nem rendelkező dokumentumok** – Ezek a dokumentumok tartalmazzák a számlálási, mozgatási és készletkorrekciós dokumentumokat.

A téma későbbi szakaszában a beszerzési megbízások lesznek példaként a folyamat szemléltetésére.

Az alábbi táblázat felsorolja azokat a dokumentumokat, amelyeket az aktuális kiadás támogat.

| Bizonylat típusa      | Dokumentum        |
|--------------------|-----------------|
| Beszerzési rendelés     | Termékbevételezés |
| Beszerzési rendelés     | Számla         |
| Értékesítési rendelés        | Szállítólevél    |
| Értékesítési rendelés        | Számla         |
| Készletnaplók | Mozgás        |
| Készletnaplók | Korrekció      |
| Készletnaplók | Leltár        |
| Készletnaplók | Átutalás        |
| Átmozgatási rendelés     | Szállítmány        |
| Átmozgatási rendelés     | Bevételezés         |

> [!IMPORTANT]
> A Global Inventory Accounting aszinkron módon dolgozza fel a Supply Chain Managementbe bevitt dokumentumokat. A problémás dokumentumok esetében nem jelennek meg hibaüzenetek.

## <a name="example-purchase-order"></a>Példa: Beszerzési rendelés

### <a name="product-receipt"></a>Termékbevételezés

A termék nyugtáinak feladása a szokásos módon. A **Minden beszerzési rendelés** lapon válassza ki a megrendelést, majd a Műveletablakban, a **Fogadás** lapon válassza a **Termék nyugta** parancsát a **Termék átvételi napló** oldalának megnyitásához. Minden sorhoz egy műveleti esemény és egy Global Invntroy Accounting esemény jön létre. Ezért válassza a **Sorok** lapot, majd válassza a **Készlet \> Események és mérések** lehetőséget az **Események és mérések** lap megnyitásához.

A Global Inventory Accounting egy eseményeken és méréseken alapuló számviteli rendszer. Az **Események és mérések** oldalon található mérési vonalrács a mérések listáját mutatja. Minden mérésnek van egy dimenziólistája.

Minden egyes működési eseményhez kétféle mérés létezik:

- **Műveletek mérése** – Ezek a mérések általánosan írják le az üzleti dokumentumokat. Az egyik mérés a termékmennyiség a dokumentumban használt mértékegység használatával. Vannak olyan mérések is, amelyek befolyásolják a készlet értékét, például a kiterjesztett árat, a kedvezményt, a kedvezmény százalékát és a vonali díjat.
- **Erőforrás-számviteli mérések** – Ezek a mérések a készletnyilvántartás szempontjából készülnek. Ismertetik a dokumentumnak az intézkedési egységben lévő készletre gyakorolt hatását. Ha több készletregisztráció van, több sor erőforrás-könyvelési mérés is létezik.

A méretek a következő módon vannak rendszerve:

- **Dualitás** – Dualitás leírja az ügynököket, akik részt vesznek a gazdasági eseményekben. A külső üzleti dokumentumok esetében az elsődleges dimenziók azt a jogi felet írják le, ahol a dokumentumot beírják, míg a kettős dimenziók az eladót, az ügyfelet és így tovább. Belső üzleti dokumentumok (például átutalási megbízások) esetében a kettős dimenziók írják le a partnerraktárt.
- **Dimenziótípus** – A dimenziótípusok kategorizálják a méreteket.
- **Dimenzió** – A dimenzió neve.
- **Dimenzióérték** – A dimenzióérték neve.

### <a name="global-inventory-accounting-event"></a>Globális Inventory Accounting esemény

A Global Inventory Accounting a működési eseményeket és méréseket inputként veszi figyelembe. Ezután elvégzi az egyes kapcsolódó főkönyvek megfelelő könyvelését a csatolt pénznem és konvenció alapján. A **Global inventory accounting esemény megtekintéséhez kiválaszthatja a Globális készletkönyvelési eseményeket és méréseket**. A Global Inventory Accounting esemény ugyanazt a módszertant követi, mint az operatív események, de különböző méréseket használ. Három fő mérési típus létezik: a termékköltség mennyisége, a termék költsége és a variancia.

Az analitikus számlákat a mérések további osztályzására használják. Lehet, hogy több főkönyv is van. Ezek a főkönyvek ahhoz a jogi személyhez kapcsolódnak, ahol a dokumentumot rögzítették. Az egyes főkönyvek eseményeit és méréseit a **Főkönyvi** mező értékének módosításával tekintheti meg.

### <a name="cost-element"></a>Költségösszetevő

A főkönyvhöz csatolt költségelem-házirend alapján a rendszer költségelemet rendel minden elszámolt műveletesemény-méréshez, amely befolyásolja a készletköltséget. Ezek a mérések magukban foglalják a kiterjesztett árat, a kedvezményt, a kedvezmény százalékát és a vonali díjat.

### <a name="measurement-line-details"></a>Mértéksor részletei

Az **Áttekintés** lapon a csatolt házirendek részletei láthatók. A költségobjektum méretei a költségobjektumot mutatják a költségobjektum-irányelv alapján. A konkrét azonosító méretek a tételszámot mutatják, ha a költségáramlás feltételezése *Specifikus – köteg*.

### <a name="purchase-invoice"></a>Beszerzési számla

A nyugták feladása a szokásos módon. Ezután a Műveletpanelen, a **Számla** lapon, a **Naplók** csoportban válassza a **Számla** lehetőséget a számlanapló megnyitásához. Minden sorhoz egy műveleti esemény és egy Global Inventroy Accounting esemény jön létre. Ezért válassza a **Sorok** lapot, majd válassza a **Készlet \> Események és mérések** lehetőséget az **Események és mérések** lap megnyitásához. Az **Események és mérések** oldalon ugyanaz a mértékegység látható. Mivel azonban az oldal más intézkedési szerepet és intézkedésmódosítót mutat, az ügynökre (jogi személyre) gyakorolt hatás eltérő.

Válassza a Global inventory accounting esemény megtekintéséhez a **Global inventory accounting eseményeket és méréseket**. A készletmennyiség és költség most a *Nem érkezett számlázott készlet* analitikus és a *Vásárolt áruk* analitikus fiókból áramlik ki.

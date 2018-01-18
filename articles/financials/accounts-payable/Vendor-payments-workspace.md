---
title: "Szállítói kifizetések munkaterület"
description: "Ez a témakör a Szállítói kifizetések munkaterülettel kapcsolatban tartalmaz tájékoztatást. A Szállítói kifizetések munkaterület a szállítói kifizetések feldolgozásához kapcsolódó információkat jeleníti meg."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/09/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendPaymentWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.assetid: 
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: cb5a674472936a52b624c548fd37079d57eb6cb7
ms.openlocfilehash: fa8ddf52d34c3662e120509156ab0b343bb4cc16
ms.contentlocale: hu-hu
ms.lasthandoff: 12/14/2017

---

# <a name="vendor-payments-workspace"></a>Szállítói kifizetések munkaterület

[!include[banner](../includes/banner.md)]

A **Szállítói kifizetések** munkaterület a szállítói kifizetések feldolgozásához kapcsolódó információkat jeleníti meg. A munkaterület egy **Saját munka** és egy **Elemzés** nézetet tartalmaz. A **Saját munka** nézet összesítő lapokat, szállítói tranzakciórácsokat és a kapcsolódó szállítói adatokat jeleníti meg. Az **Elemzés** lap a Microsoft power BI lehetőségeit kihasználva a szállítói kifizetésekkel kapcsolatos vizualizációkat jeleníti meg.

## <a name="my-work-view"></a>Saját munka nézet

### <a name="summary-tiles"></a>Összesítő csempék

Az **Összefoglaló** szakasz lapjai áttekintést nyújtanak a fizetési adatainak állapotáról. Láthatja a még nem feladott fizetési naplókat, az elmaradt számlákat, az összes szállítót és a várakoztatott szállítókat. Az **Összefoglaló** szakaszban létrehozhat egy új fizetési időszakot.

Az **Összefoglaló** szakaszban levő információk arra a vállalatra vonatkoznak, amellyel be van jelentkezve.

### <a name="vendor-transactions-grids"></a>Szállítói tranzakciók rácsai

A **Szállítói tranzakciók** szakasz tartalmazza azok a rácsokat, amelyek a késedelmes és ki nem egyenlített számlákat jelenítik meg. A **Késedelmes számlák** rácson megtekintheti a kijelölt számlához tartozó kiegyenlítési előzményeket. A **Ki nem egyenlített kifizetések** rácson megtekintheti a kijelölt számlához tartozó kiegyenlítési előzményeket, és kiegyenlítheti a számlát.

A központosított kifizetési ügyintézők egy olyan szűrőt használhatnak, amely megjelenik minden rács tetején a vállalat kiválasztásához. Ezután a rácsot kell szűrni úgy, hogy csak azokat a központosított kifizetéssel szervezeti hierarchiába tartozó vállalatokat jelenítse meg, amelyek megtekintéséhez a központosított kifizetési ügyintézőnek jogosultsága van.

A **Tranzakciók keresése** fül a **Szállítói tranzakciók** szakaszban lehetővé teszi egy szállítói tranzakció megkeresését.

### <a name="related-information"></a>Kapcsolódó információ

Megtekintheti a **Szállító korosítása** jelentést és a **Fizetés összesítése dátum szerint** jelentést a munkaterület **Kapcsolódó információk** szakaszában.

## <a name="analytics-page"></a>Elemzés lap

Az **Elemzés** lap fontos mérőszámokat jelenít meg, például a késedelmes szállítói számlákat és a jövőben esedékes szállítói számlákat. Ezen a lapon kilenc jelentéslap található. Egyik lapon egy áttekintés található, a többi nyolc lap a Kötelezettségek kifizetési mérőszámokkal kapcsolatos részletes adatokat tartalmaz.

Az alábbi táblázat mutatja be az egyes jelentésoldalakon rendelkezésre álló megjelenítéseket.

| Jelentéslap | Megjelenítés |
|-------------|---------------|
| Szállítói fizetések áttekintése | <ul><li>Lejárt határidejű számlák</li><li>Ma esedékes számlák</li><li>Alkalmazott engedmények és elvesztett engedmények</li><li>Jövőben esedékes számlák készpénzfizetési engedmény dátuma szerint</li><li>Jövőben esedékes számlák határidő szerint</li><li>Késéssel kifizetett számlák és időben kifizetett számlák</li><li>Kifizetési munkafolyamat hozzárendelése</li><li>Vevő és szállító egyenlege</li><li>Nyitott számlák fizetési várakoztatással</li></ul> |
| Lejárt határidejű számlák | <ul><li>Lejárt határidejű számlák</li><li>Késedelmes számlák részletei</li><li>Összes nyitott számla</li><li>Késedelmes számlák szállítói csoport szerint</li><li>Késedelmes számlák vállalatonként</li></ul> |
| Ma esedékes számlák | <ul><li>Ma esedékes számlák</li><li>Ma esedékes számlák részletei</li><li>Ma esedékes számlák vállalatonként</li><li>Ma esedékes számlák szállítói csoport szerint</li></ul> |
| Alkalmazott engedmények és elvesztett engedmények | <ul><li>Alkalmazott engedmények és elvesztett engedmény</li><li>Alkalmazott engedmények és elvesztett engedmény részletei</li><li>Alkalmazott engedmények és elvesztett engedmény vállalatok szerint</li><li>Alkalmazott engedmények és elvesztett engedmény szállítói csoport szerint</li></ul> |
| Jövőben esedékes számlák | <ul><li>Jövőben esedékes számlák</li><li>Jövőben esedékes számlák részletei</li><li>Jövőben esedékes számlák vállalatok szerint</li><li>Jövőben esedékes számlák szállítói csoport szerint</li><li>Jövőben esedékes számlák készpénzfizetési engedmény dátuma szerint</li><li>Jövőben esedékes számlák határidő szerint</li></ul> |
| Késedelmesen kifizetett számlák | <ul><li>Határidő után kifizetett számlák</li><li>Határidő után kifizetett számlák részletei</li><li>Határidő után kifizetett számlák vállalatok szerint</li><li>Határidő után kifizetett számlák szállítói csoport szerint</li><li>Késedelmesen kifizetett számlák és időben kifizetett számlák</li></ul> |
| Kifizetési munkafolyamat | <ul><li>Szállítói kifizetési munkafolyamat-példányok</li><li>Szállítói kifizetési munkafolyamat-példányok jóváhagyók szerint</li><li>Szállítói kifizetési munkafolyamat-példányok vállalatok szerint</li><li>Átlagos napok a munkafolyamatban a jóváhagyó szerint</li></ul> |
| Vevő és szállító egyenlege | <ul><li>Vevő és szállító egyenlege</li><li>Vevő és szállító egyenlege vállalatok szerint</li><li>Vevő és szállító egyenlege (részletek)</li></ul> |
| Számlák fizetési várakoztatással | <ul><li>Számlák fizetési várakoztatással</li><li>Nyitott számlák fizetési várakoztatással (részletek)</li><li>Nyitott számlák fizetési várakoztatással vállalatok szerint</li><li>Nyitott számlák fizetési várakoztatással szállítói csoport szerint</li></ul> |


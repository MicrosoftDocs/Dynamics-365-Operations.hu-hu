---
title: Szállítói kifizetések munkaterület
description: Ez a témakör a Szállítói kifizetések munkaterülettel kapcsolatban tartalmaz tájékoztatást. A Szállítói kifizetések munkaterület a szállítói kifizetések feldolgozásához kapcsolódó információkat jeleníti meg.
author: abruer
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendPaymentWorkspace
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 2b9a562738a18e9d83ed37730b167028c4b983cb
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823143"
---
# <a name="vendor-payments-workspace"></a>Szállítói kifizetések munkaterület

[!include [banner](../includes/banner.md)]

A **Szállítói kifizetések** munkaterület a szállítói kifizetések feldolgozásához kapcsolódó információkat jeleníti meg. A munkaterület egy **Saját munka** és egy **Elemzés** nézetet tartalmaz. A **Saját munka** nézet összesítő lapokat, szállítói tranzakciórácsokat és a kapcsolódó szállítói adatokat jeleníti meg. Az **Elemzés** lap a Microsoft Power BI lehetőségeit kihasználva a szállítói kifizetésekkel kapcsolatos vizualizációkat jeleníti meg.

## <a name="setup-needed-to-view-power-bi-content"></a>A Power BI-tartalom megtekintéséhez beállítás szükséges

A következő beállításokat meg kell adni, hogy az adatok megjelenjenek a **Szállítói kifizetések** között, a Power BI vizuális elemei között.
1. Nyissa meg a **Rendszeradminisztráció > Beállítás > Rendszerparaméterek** pontot a **Rendszerpénznem** és a **Rendszerváltási árfolyam** beállításához.
2. Lépjen a **Főkönyv > Naptárak > Pénzügyi naptárak** részre, hogy ellenőrizze az aktív időszakhoz hozzárendelt pénzügyi naptár dátumait.
3. Lépjen a **Főkönyv > Beállítás > Főkönyv** részre a **Könyvelési pénznem** és az **Árfolyamtípus** beállításához. 
4. Adja meg az árfolyamokat a tranzakció pénznemei és a könyvelési pénznem, a könyvelési pénznem és a rendszer pénzneme között. Lépjen ide: **Főkönyv > Pénznemek > Pénznemek árfolyamtípusai**.
5. Lépjen a **Rendszerfelügyelet > Beállítás > Entitástár** részre a **VendPaymentBIMeasureV2** összesítő mérték frissítéséhez.

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


|            Jelentéslap            |                                                                                                                                                                                Megjelenítés                                                                                                                                                                                |
|-----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     Szállítói fizetések áttekintése      | <ul><li>Lejárt határidejű számlák</li><li>Ma esedékes számlák</li><li>Alkalmazott engedmények és elvesztett engedmények</li><li>Jövőben esedékes számlák készpénzfizetési engedmény dátuma szerint</li><li>Jövőben esedékes számlák határidő szerint</li><li>Késéssel kifizetett számlák és időben kifizetett számlák</li><li>Kifizetési munkafolyamat hozzárendelése</li><li>Vevő és szállító egyenlege</li><li>Nyitott számlák fizetési várakoztatással</li></ul> |
|         Lejárt határidejű számlák         |                                                                                             <ul><li>Lejárt határidejű számlák</li><li>Késedelmes számlák részletei</li><li>Összes nyitott számla</li><li>Késedelmes számlák szállítói csoport szerint</li><li>Késedelmes számlák vállalatonként</li></ul>                                                                                              |
|        Ma esedékes számlák         |                                                                                                         <ul><li>Ma esedékes számlák</li><li>Ma esedékes számlák részletei</li><li>Ma esedékes számlák vállalatonként</li><li>Ma esedékes számlák szállítói csoport szerint</li></ul>                                                                                                          |
| Alkalmazott engedmények és elvesztett engedmények |                                                                             <ul><li>Alkalmazott engedmények és elvesztett engedmény</li><li>Alkalmazott engedmények és elvesztett engedmény részletei</li><li>Alkalmazott engedmények és elvesztett engedmény vállalatok szerint</li><li>Alkalmazott engedmények és elvesztett engedmény szállítói csoport szerint</li></ul>                                                                              |
|      Jövőben esedékes számlák       |                                                 <ul><li>Jövőben esedékes számlák</li><li>Jövőben esedékes számlák részletei</li><li>Jövőben esedékes számlák vállalatok szerint</li><li>Jövőben esedékes számlák szállítói csoport szerint</li><li>Jövőben esedékes számlák készpénzfizetési engedmény dátuma szerint</li><li>Jövőben esedékes számlák határidő szerint</li></ul>                                                  |
|        Késedelmesen kifizetett számlák         |                                                         <ul><li>Határidő után kifizetett számlák</li><li>Határidő után kifizetett számlák részletei</li><li>Határidő után kifizetett számlák vállalatok szerint</li><li>Határidő után kifizetett számlák szállítói csoport szerint</li><li>Késedelmesen kifizetett számlák és időben kifizetett számlák</li></ul>                                                          |
|         Kifizetési munkafolyamat          |                                                                                <ul><li>Szállítói kifizetési munkafolyamat-példányok</li><li>Szállítói kifizetési munkafolyamat-példányok jóváhagyók szerint</li><li>Szállítói kifizetési munkafolyamat-példányok vállalatok szerint</li><li>Átlagos napok a munkafolyamatban a jóváhagyó szerint</li></ul>                                                                                |
|    Vevő és szállító egyenlege     |                                                                                                                   <ul><li>Vevő és szállító egyenlege</li><li>Vevő és szállító egyenlege vállalatok szerint</li><li>Vevő és szállító egyenlege (részletek)</li></ul>                                                                                                                    |
|    Számlák fizetési várakoztatással     |                                                                                         <ul><li>Számlák fizetési várakoztatással</li><li>Nyitott számlák fizetési várakoztatással (részletek)</li><li>Nyitott számlák fizetési várakoztatással vállalatok szerint</li><li>Nyitott számlák fizetési várakoztatással szállítói csoport szerint</li></ul>                                                                                          |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
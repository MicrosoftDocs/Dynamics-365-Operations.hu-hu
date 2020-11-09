---
title: Betekintés az anyagkivételekbe
description: Ez a témakör leírja, hogyan nyerhet jobb betekintést a nyersanyagkivételekbe a termelési rendelések és a kötegrendelések esetében.
author: johanhoffmann
manager: tfehr
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgShopSupervisorWorkspace, WHSProdWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 0c17997d9dd04559fb7022fe39bb2b961c1cfc4a
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016585"
---
# <a name="visibility-into-material-exceptions"></a>Betekintés az anyagkivételekbe

[!include [banner](../includes/banner.md)]

A **Termelési üzem kezelése** munkaterületen három csempe ad jobb betekintést a nyersanyagkivételekbe a termelési rendelések és a kötegrendelések esetében:

- Figyelmet igénylő ki nem adott anyagsorok
- Figyelmet igénylő feldolgozatlan hullámok
- Figyelmet igénylő nyitott raktári munka

A rendszer a három csempe mindegyikénél az anyagjegyzéksorok és a receptúrasorok nyersanyagdátumát hasonlítja össze a munkaterület dátumával, valamint a **Termelési egység** , **Erőforráscsoport** és **Erőforrás** szűrőkkel, amelyek a **Munkaterület konfigurálása** menüben vannak beállítva. Alapértelmezés szerint a munkaterület dátuma az aktuális dátumra van beállítva, de ez módosítható.

Egy kiadatlan anyagjegyzéksor vagy receptúrasor figyelmet igényel, ha a sor nyersanyagdátuma megegyezik a munkaterület dátumával, vagy korábbi ennél, és ha megfelel a feltételeknek, amelyeket a munkaterület szűrői határoznak meg.

Az alábbi ábrán a kék sáv az erőforráson ütemezett termelési feladatot jelenti. A feladat ütemezése szerint az indulás dátuma 2017. május 1. (2017/05/01). Ez a dátum a nyersanyag dátuma. Ez azt jelenti, hogy az anyagjegyzék- és receptúrasorokban a feladathoz rendelt anyagoknak készen kell lenniük ezen a dátumon. Az ábrán látható másik dátum – 2017. május 6. (2017/05/06) – a munkaterület-dátumot jelöli. Ebben a példában a nyersanyag dátuma a munkaterület-dátumnál korábbra esik. Ennek megfelelően a nyersanyag-felhasználás tervezett kezdő dátuma már elmúlt, és az anyagjegyzék- és receptúrasorok megfelelnek a figyelmet igénylő állapothoz szükséges feltételeknek.

![Példa termelési feladatra, ahol a nyersanyag dátuma a munkaterület-dátumnál korábbra esik.](./media/improved-visibility.png)

## <a name="unreleased-material-lines-needing-attention"></a>Figyelmet igénylő ki nem adott anyagsorok

Egy anyagjegyzék- vagy receptúrasort háromféle módon lehet kiadni a raktárba:

- Egy termelési rendelés vagy kötegrendelés kiadásának részeként
- Kézi kiadásként
- Automatikusan, egy kötegelt feladat részeként

További tudnivalókért lásd: [Anyagjegyzék- és receptúrasorok kiadása a raktárba](releasing-bom-and-formula-lines-to-warehouse.md). 

Ha az anyagjegyzék- vagy receptúrasora még nem lett kiadva, vagy csak részben lett kiadva, és a munkaterület dátum- és szűrési feltétele teljesül, a sor része annak a számnak a számításának, amelyik a **Figyelmet igénylő ki nem adott anyagsorok** csempén szerepel.

Amikor kiválasztja a csempét, megnyílik a **Kiadás raktárba** lap. Ezen a lapon a kiadatlan anyagjegyzék- és receptúrasorok száma szerepel, ezt a számot a csempe száma mutatja. A kiadatlan sorok a felső rácson jelennek meg. Ez a rács azt a mennyiséget mutatja, amelyet eredetileg becsültek a sorra, a mennyiséget, amely már ki van adva, és a fennmaradó mennyiséget, amelyet még ki kell adni. Sorokat adhat a felső rácsról az alsó rácshoz. Az alsó rácsból aztán kiadhatja a kijelölt sorokat a raktárba. Az alsó rácsban a kiadandó mennyiséget is beállíthatja, hogy csak a mennyiség egy része legyen kiadva.

## <a name="unprocessed-waves-needing-attention"></a>Figyelmet igénylő feldolgozatlan hullámok

Az anyagjegyzék- vagy receptúrasor a kiadásakor hozzáadódik egy új termelési hullámhoz vagy egy meglévő nyitott hullámhoz, a termelési hullám sablonjában konfiguráltaktól függően. A hullám sablonjának beállítása révén úgy is beállíthat egy hullámot, hogy automatikus legyen a feldolgozása, amikor egy anyagjegyzék- vagy receptúrasort kiadnak. A hullám feldolgozásakor létrejön a nyersanyag-kitárolási raktári munka. Ha a hullám sablonja úgy van beállítva, hogy a hullámokat a kiadás alkalmával nem kell feldolgozni, akkor a hullám feldolgozatlan állapotban marad. A **Figyelmet igénylő feldolgozatlan hullámok** csempe azoknak az anyagjegyzék- és receptúrasoroknak a számát jeleníti meg, amelyek feldolgozatlan hullámokkal lettek kiadva a raktárba, és olyan nyersanyagdátumuk van, amely korábbi vagy ugyanaz, mint a munkaterület dátuma. A sorokatat egy művelet-erőforrásnak is fel kell dolgoznia, amely a munkaterület szűrőjére vonatkozik.

A csempe kijelölésekor megnyílik a **Minden termelési hullám** lap. Ezt a lapot azoknak a nyitott hullámsoroknak a száma szűri, amelyek a csempe a feltételeinek megfelelő kiadott anyagjegyzék- és receptúrasorokból származó hullámsorokat tartalmaznak. A **Minden termelési hullám** lapon manuálisan fel lehet dolgozni a hullámot.

## <a name="open-warehouse-work-needing-attention"></a>Figyelmet igénylő nyitott raktári munka

A **Figyelmet igénylő nyitott raktári munka** csempe azoknak az anyagjegyzék- és receptúrasoroknak a számát jeleníti meg, amelyekhez feldolgozatlan munka tartozik, és olyan nyersanyagdátumuk van, amely korábbi vagy ugyanaz, mint a munkaterület dátuma. A sorokatat egy művelet-erőforrásnak is fel kell dolgoznia, amely a munkaterület szűrőjére vonatkozik.

A csempe kijelölésekor megnyílik a **Minden munka** lap. Ezt a lapot azoknak a nyitott munkafejléceknek a száma szűri, amelyek a csempe a feltételeinek megfelelő kiadott anyagjegyzék- és receptúrasorokból származó munkasorokat tartalmaznak. A **Minden munka** lapon manuálisan fel lehet dolgozni a munkát.

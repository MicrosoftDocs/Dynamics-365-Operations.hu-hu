---
title: Termelési rendelések kiadása
description: A kiadott termelési rendelés olyan rendelés, amely engedélyt kapott termelésre. A „Kiadva” kifejezés, egy a termelés rendelési ciklus állapotát leíró elnevezés. Jelentése, hogy a termelési rendelés készen áll a raktári folyamatokra és az értékesítésre.
author: johanhoffmann
ms.date: 03/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdParmRelease
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2414
ms.assetid: 50c2257b-2924-44f5-b7c1-11f498092053
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 740ac516ffa01d8930aedabb9873834b07b7debf700dc61b14d93ac8d6dcd086
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718870"
---
# <a name="release-production-orders"></a>Termelési rendelések kiadása

[!include [banner](../includes/banner.md)]

A kiadott termelési rendelés olyan rendelés, amely engedélyt kapott termelésre. A „Kiadva” kifejezés, egy a termelés rendelési ciklus állapotát leíró elnevezés. Jelentése, hogy a termelési rendelés készen áll a raktári folyamatokra és az értékesítésre.

## <a name="characteristics-of-the-released-state"></a>A Kiadott állapot szerinti jellemzők

A **Kiadott** folyamatállapot a termelési rendelés életciklusának egy állapota. A termelési rendelések, melyek **Kiadott** állapotban vannak, végrehajtásra elérhetők a termelési üzem és a raktárkezelési folyamatok számára. A **Kiadott** állapotát a következő jellemzőkkel rendelkezik:

- A termelési rendelést a **Kiadott** állapotra vagy a termelési rendelés, vagy a kötegfolyamat használatával lehet módosítani. A termelési rendelés is automatikusan is frissíthető a tervezett termelési rendelésekből, amelyeket a **Megerősítési időkorlát** mezőben az **Alapterv** oldalon lehet megerősíteni.
- A **Kiadott** folyamatállapot jelzi, hogy az üzemi dolgozók (operátorok) elindíthatják a termelési feladatokat az üzemben.
- Termelési dokumentumok, például útvonalkártyák, útvonalfeladatok és a feladatkártyák a termelési feladatokkal kapcsolatban tartalmaznak tájékoztatást, és kiállíthatók.
- A ténylegesen lefoglalt anyagok esetében raktár munka generálódik, hogy az anyagokat ki lehessen tárolni a termelési rendeléshez.

## <a name="releasing-jobs-to-the-shop-floor"></a>Feladatok kiadása az üzem számára

Egy termelési rendelést kiadását követően, a hozzá kapcsolódó termelési feladatok láthatók, és készen állnak a regisztrációra. A kezelők feladatregisztrációkat végezhetnek – például indítás, leállítás és befejezés – a **Feladatkártya-terminál** vagy a **Feladatkártya-eszköz** lapon. A regisztrált idő és mennyiség automatikusan átkerül a regisztrációs lapokról a termelési naplókba, hogy nyomon követhető legyen a felhasznált idő és mennyiség.

## <a name="route-cards"></a>Útvonalkártyák

Az útvonalkártya áttekintő információt tartalmaz az útvonal és a művelet beállítása, illetve a feladatütemezési módszerek alapján.

## <a name="route-jobs"></a>Munkatervek

Az útvonalfeladat egy művelet mindegyik feladatát részletesen felsorolja, és tartalmazza a beállítási, feldolgozási, várakozási és szállítási időket is. Például egy festési művelethez olyan egyéni feladatok lehetnek szükségesek, mint a beállítási és a futási idő a festési feladathoz, és a várakozási idő a száradáshoz.

## <a name="job-cards"></a>Feladatkártyák

A feladatkártya egy adott művelet egyéni feladatszámait sorolja fel. Egy feladat jelenik meg minden oldalon. A feladatkártyán szereplő feladatok és becsült idejük az útvonal és a művelet beállítási adataiból származik. A feladatkártyáról megnyithatók a **Termelésinapló-sorok**, a **Feladatkártya** oldalon. A műveleti erőforrásokat működtető emberek visszajelzést adhatnak a termelési folyamatról. Vannak olyan mezők, ahol felhasználási statisztikai adatokat és egyéb információkat adhatnak meg, például a hibák mennyiségét.

## <a name="warehouse-work-for-raw-material-picking"></a>Raktári munka a nyersanyag-kitároláshoz.

A nyersanyag-kitárolási munka a kiadás során jön létre. A munka csak ahhoz az anyagmennyiséghez jön létre, amelyet ténylegesen lefoglaltak a termelési rendeléshez a rendelés kiadása előtt. A következő beállítás szükséges raktári munka létrehozásához a nyersanyag-kitároláshoz:

- A nyersanyag-kitárolási helyutasítás azt határozza meg, hogy melyik helyen lévő raktárból legyenek az anyagok kitárolva.
- Hullámsablon nyersanyagok számára, ahol a raktári munka végrehajtásához szükséges szabályok konfigurálódnak.
- Termelések beérkezési helye, amely meghatározza, hogy hová teszik az anyagokat

Az azonosítótáblával szabályozott helyek használata esetén eldöntheti, hogy a megrendelt mennyiséget vagy a cikk teljes elérhető mennyiségét ki kell-e tárolni a nyersanyag-kitárolási munka feldolgozásakor. Ennek a beállításához:

1. Kattintson ide: **Termékinformációk kezelése \> Termékek \> Kiadott termékek**, és nyissa meg a releváns cikket.
1. Bontsa ki a **Raktár** gyorslapot.
1. Válasszon a következő lehetőségek közül az **Anyagkitárolás az azonosítótábla-helyeken** mezőben:
    - *Rendelés kitárolása*: Kizárólag a megrendelt mennyiség kerülhet kitárolásra.
    - *Előkészítés*: Amikor csak lehetséges, az azonosítótáblánál elérhető teljes mennyiséget kell kitárolni. Ahhoz, hogy a dolgozó a teljes azonosítótábla mennyiségét kitárolhassa, az azonosítótábla nem tartalmazhat vegyes tételeket és nem lehet vegyes dimenziójú. Ha az azonosítótábla vegyes dimenziókat vagy cikkeket tartalmaz, a kitárolás úgy folytatódik, mintha a *Rendelés kitárolása* értékre lenne beállítva.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
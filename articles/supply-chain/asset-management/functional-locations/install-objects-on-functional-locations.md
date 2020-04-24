---
title: Eszközök telepítése munkavégzési helyszínekre
description: Ez a cikk azt ismerteti, hogyan telepíthetők eszközök a munkavégzési helyszínekre az Eszközök kezelése szolgáltatásban.
author: josaw1
manager: tfehr
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6d46c3c43b2f9cbae4c3584244261e8ef1547ffe
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205405"
---
# <a name="install-assets-on-functional-locations"></a>Eszközök telepítése munkavégzési helyszínekre

[!include [banner](../../includes/banner.md)]

 

A munkavégzési helyszínek struktúrájának kialakítása után eszközöket kell telepíteni a releváns munkavégzési helyszínekre. Ez a cikk azt ismerteti, hogyan telepíthetők eszközök ezekre a munkavégzési helyszínekre az Eszközök kezelése szolgáltatásban. Az eszközök létrehozásáról a [Bevezetés: eszközök](../objects/introduction-to-objects.md) cikkben talál további információt.

Ha hozott létre eszközstruktúrát, a teljes struktúrát telepíteni kell a munkavégzési helyszíneken. Ennek megfelelően egy munkavégzési helyszínen csak fölérendelt eszközök (fölérendelt eszközzel nem rendelkező felső szintű eszközök) telepíthetők. Minden összekapcsolt alárendelt eszköz (aleszköz) a munkavégzési helyszínen is települ. Amikor eszközöket telepít egy munkavégzési helyszínen, a munkavégzési helyszín pénzügyi dimenziói – a munkavégzési helyszín típusának beállításától függően – automatikusan átkerülhetnek az eszközre. A munkavégzési helyszínek típusainak beállításáról a [Munkavégzési helyszínek típusai](../setup-for-functional-locations/functional-location-types.md) című cikkben talál további információt.

> [!NOTE]
> Az eszköztípusok beállíthatók munkavégzési helyszínek típusához. Ebben az esetben ha eszközt telepít a munkavégzési helyszínen, csak az ugyanolyan eszköztípusú fölérendelt eszközök jelennek meg a munkavégzési helyszínen telepíthető eszközök listájában.

Miután telepített eszközöket a munkavégzési helyszíneken, a kívánt módon cserélheti le a fölérendelt eszközt vagy az eszközstruktúrát. Amikor eszközöket telepít, kiválaszthatja a lecserélendő fölérendelt eszközt. Valamennyi összekapcsolt alárendelt eszköz is le lesz cserélve. 


## <a name="install-an-asset-structure-on-a-functional-location"></a>Eszközstruktúra telepítése egy munkavégzési helyszínen

1. Válassza az **Eszközök kezelése** \> **Közös** \> **Munkavégzési helyszínek** \> **Összes munkavégzési helyszín** vagy **Aktív munkavégzési helyszínek** lehetőséget.
2. Válassza ki, hogy melyik munkavégzési helyszínen szeretné telepíteni az eszközt.
3. Válassza az **Eszköz telepítése** lehetőséget.

    Az **Attribútumok** szakaszban láthatók az eszközattribútumok olyan követelményei, amelyek be vannak állítva a munkavégzési helyszín kiválasztott típusához. Az attribútumok csak tájékoztató jellegűek. A rendszer nem veti össze az attribútumokat az éppen telepített eszközön beállított eszközattribútumokkal. Az érvényesítést Önnek kell elvégeznie az eszköz **Eszköz** mezőben történő kiválasztása után.

4. Az **Eszköz** mezőben válassza ki a telepítendő fölérendelt eszközt. Minden összekapcsolt alárendelt eszköz automatikusan felkerül a telepítési listára.

    Az eszközlistától jobbra lévő **Eszközattribútumok** szakaszban láthatók a kiválasztott eszközzel összekapcsolt eszközattribútumok.

5. A **Hatályos** mezőben válassza ki a dátumot és időpontot, amelytől érvényes az eszköz telepítése. Az adott dátum és időpont után az eszköz és az összekapcsolt aleszközök költségei össze lesznek kapcsolva a munkavégzési helyszínnel.

    > [!NOTE]
    > Az eszközhöz beállított eszközattribútumok bekerülnek az **Attribútumok** szakaszba. Tegyük fel, hogy a **Tömeg** attribútumkövetelményt mind az eszközhöz, mind a munkavégzési helyszínhez felvette követelményként. Ha az eszköz és a munkavégzési helyszín attribútumkövetelményei egyeznek, az eszköz attribútumkövetelményei bekerülnek az **Érték** mezőkbe. Így ellenőrizheti az eszköz értékeit és a munkavégzési helyszínhez beállított eszközattribútumokat. A munkavégzési helyszínhez beállított eszközattribútumokat pipa jelöli.

6. Válassza ki az **OK** lehetőséget.

    > [!NOTE]
    > Ha egy eszközt új munkavégzési helyszínen telepít, hajtsa végre ennek az eljárásnak az 1–6. lépését. Amikor új munkavégzési helyszínen telepít egy eszközt, a rendszer automatikusan eltávolítja a korábbi munkavégzési helyszínről. Az eszköz új munkavégzési helyszínen való telepítése előtt létrehozott karbantartási kérések vagy munkarendelések **nem** kerülnek át automatikusan az új munkavégzési helyszínre. Ha ezekre a karbantartási kérésekre és munkarendelésekre továbbra is szükség van az eszköznél, akkor manuálisan újra létre kell hozni őket, miután az új helyen telepítette az eszközt.

7. A munkavégzési helyszínen telepített eszközök (és az aleszközök) listájának megtekintéséhez válassza ki a munkavégzési helyszínt az **Összes munkavégzési helyszín** oldalon, majd válassza az **Eszközök** lehetőséget.
8. A munkavégzési helyszínen telepített eszközökkel összekapcsolt karbantartási kérések, aktív munkarendelések vagy hibás regisztrációk listájának megtekintéséhez válassza ki a munkavégzési helyszínt az **Összes munkavégzési helyszín** oldalon, majd válassza a **Kérelmek**, a **Munkarendelések** vagy a **Hibák** lehetőséget.

> [!NOTE]
> Amikor módosulnak az eszközhöz kapcsolódó adatok, a részletek automatikusan frissülnek azon a munkavégzési helyszínen, amelyen az eszköz telepítve van. Ez az automatikus frissítés a karbantartási kérések, a munkarendelések, az eszközhiba-regisztrációk, a karbantartás miatti üzemkimaradások regisztrációja és az eszközmérések regisztrációja esetében működik.

## <a name="automatically-create-one-asset-on-a-functional-location"></a>Egy eszköz automatikus létrehozása egy munkavégzési helyszínen

A munkavégzési helyszínek állapotai és típusai beállíthatók úgy, hogy kezeljék *egy* eszköz automatikus létrehozását egy munkavégzési helyszínen. Az eszköz ugyanazt az azonosítót és nevet kapja majd, mint a munkavégzési helyszín. Ez a funkció akkor lehet hasznos, ha nagy, statikus eszközön (pl. épületen) kell karbantartást kezelni.

Az eszköz munkavégzési helyszínen történő automatikus létrehozása előtt elérhetőnek kell lennie a következő beállítási adatoknak:

- Hozzon létre új típust a munkavégzési helyszínhez, amellyel megoldható az eszközök automatikus létrehozása. Az **Eszköztípus** mezőben válasszon ki egy eszköztípust. További információ: [Munkavégzési helyszínek típusai](../setup-for-functional-locations/functional-location-types.md).
- Hozzon létre új életciklus-állapotot a munkavégzési helyszínhez, amellyel megoldható az eszközök automatikus létrehozása. Állítsa az **Eszköz létrehozása** beállítást **Igen** értékre. További információ: [Munkavégzési helyszínek életciklus-állapotai](../setup-for-functional-locations/functional-location-stages.md).

Ha a beállítási adatok elérhetők, létrehozhatja az eszközöket.

1. Az **Összes munkavégzési helyszín** oldalon ellenőrizze, hogy az a munkavégzési helyszín, amelyen automatikusan létre szeretné hozni az eszközt, az erre a célra létrehozott típusba tartozik-e.
2. Válassza ki a munkavégzési helyszínt a listában.
3. Válassza ki a **Munkavégzési helyszín állapotának frissítése** lehetőséget, majd az erre a célra létrehozott életciklus-állapotot. Egy eszköz automatikusan települ a munkavégzési helyszínen. Az eszköz neve megegyezik majd a munkavégzési helyszínével.

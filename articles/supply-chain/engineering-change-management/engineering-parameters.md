---
title: Tervezési változáskezelés paraméterei
description: Ez a témakör bemutatja, hogyan lehet mérnöki módosításkezelési funkciókat konfigurálni a Microsoft Dynamics 365 Supply Chain Management rendszerhez.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: dbe51e9e44cbdbf71d02e84c3a8634750f45ffa13b213fc1306a1047fb9e0b63
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6725746"
---
# <a name="engineering-change-management-parameters"></a>Tervezési változáskezelés paraméterei

[!include [banner](../includes/banner.md)]

A **Mérnöki módosításkezelési paraméterek** oldal olyan beállítási paramétereket tartalmaz, amelyek módosítják a kiadási termék struktúrájához és a mérnöki módosítások kezelési folyamataihoz kapcsolódó alapértelmezett viselkedést.

## <a name="open-the-engineering-change-management-parameters-page"></a>A mérnöki módosításkezelési paraméterek oldal megnyitása

A **Mérnöki módosításkezelési paraméterek** oldal megnyitásához nyissa meg a **Mérnöki módosítások kezelése \> Beállítás \> Mérnöki módosításkezelési paraméterek** lehetőséget. Ezt követően a mezőket a téma hátralévő szakaszaiban leírtak szerint lehet megadni.

## <a name="release-control-tab"></a>Kiadásellenőrzés lap

A következő táblázat felsorolja azokat a mezőket, amelyek elérhetők a **Mérnöki módosításkezelési paraméterek** oldal **Kiadásellenőrzés** lapján. Ezek a mezők hatással vannak a kiadási termék struktúrájának feldolgozására.

| Mező | Leírás |
|---|---|
| Cikkszámszabály | Válassza ki, hogyan kell megadni a cikkszámot a termék jogi személynek történő kiadásakor. Válassza a *Mérnöki termékszám* lehetőséget ha a fogadó jogi személy termékszámának meg kell egyeznie a mérnöki vállalat termékszámával. Válassza ki a *Helyi cikkszámsorozat* lehetőséget, ha a terméknek a fogadó jogi személynél a termékszámok sorozatában a következő számot kell felvennie. |
| Darabjegyzék névszabálya | Válassza ki, hogy milyen módon határozza meg a program az anyagjegyzék (AJ) nevét, ha a termék bevételezése (kiadása) egy jogi személyben történik. Válassza ki a *Mérnöki név* vagy a *Bevételezési cikkszám* lehetőséget. |
| Útvonal névszabálya | Válassza ki, hogy milyen módon határozza meg a program az útvonal nevét, ha a termék útvonalának bevételezése (kiadása) egy jogi személyben történik. Válassza ki a *Mérnöki név* vagy a *Bevételezési cikkszám* lehetőséget. |
| Darabjegyzék-ellenőrzés futtatása | Válassza ki, hogy futtatásra kerüljön-e anyagjegyzék-ellenőrzés a terméknek a jogi személyhez történő bevételezésekor (kiadásakor). |
| Inaktív darabjegyzék kiadási viselkedése | Annak megadása, hogy a termék kiadható-e, ha inaktív anyagjegyzékkel rendelkezik. Válassza az *Elfogadás*, a *Csak figyelmeztetés* vagy a *Nem megengedett* beállítást. |
| Inaktív útvonal kiadási viselkedése | Annak megadása, hogy a termék kiadható-e, ha inaktív útvonallal rendelkezik. Válassza az *Elfogadás*, a *Csak figyelmeztetés* vagy a *Nem megengedett* beállítást.|
| Termék elfogadása | Annak megadása, hogy az elfogadáshoz egy további lépés szükséges-e, mielőtt a terméket ki lehetne adni a jogi személyben. Az elfogadási lépés hozzáadásához adja meg a *Manuális* beállítást. Ebben az esetben a **Nyitott termékkiadások** oldal megmutatja a termékeket. Az *Automatikus* beállítás választása esetén a termék közvetlenül a cél jogi személy **Kiadott termékek** oldalán látható, rögtön azután, hogy a termék kiadásra kerül a kiadási szerkezeti struktúrájával együtt. |

## <a name="engineering-change-management-tab"></a>Mérnöki módosítások kezelése lap

A következő táblázat felsorolja azokat a mezőket, amelyek elérhetők a **Mérnöki módosításkezelési paraméterek** oldal **Mérnöki módosítások kezelése** lapján. Ezek a beállítások hatással vannak a mérnöki módosítások kezelési folyamatára.

| Mező | Leírás |
|---|---|
| Kategória | A mérnöki módosítások iránti kérelem létrehozásakor használt alapértelmezett kategória. |
| Prioritás | A mérnöki módosítások iránti kérelem létrehozásakor használt alapértelmezett prioritás. |
| Súlyossági szabály | Válassza ki, hogyan legyen meghatározva egy mérnöki módosítási rendelés súlyossága. Válassza ki a *Manuális* beállítást, ha a felhasználónak be kell írnia egy értéket a **Súlyosság** mezőbe. Válassza a *Számítás* lehetőséget, ha azt szeretné, hogy a rendszer kiszámítsa a **Súlyosság** mező értékét, amikor a mérnöki módosítási rendelés művelet ablaktábláján kiválasztja a **Súlyosság számítása** lehetőséget. Ebben az esetben a rendszer a **Súlyossági szabálykészlet** oldalon megadott súlyossági szabályokat fogja használni. Válassza az *Automatikus számítás* lehetőséget, ha azt szeretné, hogy a program automatikusan kiszámítsa a **Súlyosság** mező értékét, és kitöltse a súlyossági szabályok alapján. |
| Érintett termékek újbóli kiadása | Ez a mező akkor használható, ha a termékeket egy mérnöki módosítási rendelésen keresztül újra kiadják. Megadhatja, hogy az összes termék vagy csak az érintett termékek szerepeljenek-e javaslatként a **Kiadások** párbeszédpanelen. |
| Kiadandó anyagjegyzékszintek | A kiadandó anyagjegyzék szintjének mélysége. Ha az anyagjegyzéknek több szintje van (azaz ha ez mélyebb), mint az itt megadott érték, akkor a program csak a megadott értéknek megfelelő szinteket adja ki. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
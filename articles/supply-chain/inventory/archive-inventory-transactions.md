---
title: Készlettranzakciók archiválása
description: Ez a témakör azt ismerteti, hogyan lehet archiválni a készlettranzakciók adatait a rendszer teljesítményének javítása érdekében.
author: sherry-zheng
ms.date: 03/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTransArchiveProcessForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-03-01
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 0526eb42a886817d50e1ecfd252a6e971875ba92
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956058"
---
# <a name="archive-inventory-transactions"></a>Készlettranzakciók archiválása

[!include [banner](../../includes/banner.md)]

Az idő folyamán a készlettranzakciók táblája (`InventTrans`) tovább nő és több adatbázisterületet foglal el. Emiatt a táblába küldött lekérdezések fokozatosan lelassulnak. Ez a témakör azt írja le, hogy hogyan archiválhatja a *Készlettranzakciók archívuma* funkcióval a készlettranzakciók adatait, hogy ezzel javítsa a rendszer teljesítményét.

> [!NOTE]
> Csak a pénzügyileg frissített készlettranzakciók archiválhatók a kiválasztott lezárt főkönyvi időszakban. Az archiváláshoz a pénzügyileg frissített kimenő készlettranzakciók kiadási állapotának *Eladva* értéknek kell lennie, a bejövő készlettranzakcióknak *Beszerzett* bevételezési állapotúnak kell lennie.

A készlettranzakciók archiválásakor minden kapcsolódó tranzakció az `InventTransArchive` táblába kerül. A készletkiadási tranzakciók és a készletbevételezési tranzakciók archiválása külön történik, a cikkazonosító (`itemId`) és a készletdimenzió-azonosító (`inventDimId`) kombinációja alapján, és a rendszer összesített kiadási és összesített bevételezési tranzakciók közé sorolja őket.

Ha egy `itemId` és `inventDimId` kombináció csak egy bevételezési vagy kibocsátási tranzakciót tartalmaz, a tranzakció nem lesz archiválva.

## <a name="turn-on-the-feature-in-your-system"></a>A funkció bekapcsolása a rendszerben

Ha a rendszer még nem tartalmazza az ebben a témakörben leírt funkciókat, lépjen a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) lehetőségre, és a kapcsolja be az *Készlettranzakciók archívuma* funkciót. Ne feledje, hogy ezt a funkciót engedélyezés után nem lehet letiltani.

## <a name="things-to-consider-before-you-archive-inventory-transactions"></a>Megfontolandó szempontok a készlettranzakciók archiválását megelőzően

A készlettranzakciók archiválását megelőzően figyelembe kell vennie a következő üzleti eseteket, mivel azok hatással lesznek a műveletre:

- Amikor a kapcsolódó dokumentumokból – például beszerzésirendelés-sorokból – könyvvizsgálati készlettranzakciókat végez, azok archiváltként jelennek meg. Az archivált tranzakciók ellenőrzéséhez lépjen a **Készletkezelés \> Időszakos feladatok \> Adattisztítás \> Készlettranzakciók archívuma** pontra.
- Archivált időszakok esetén nem érvénytelen lehet készletzárást visszavonni. Készletzárás visszavonása előtt az adott időszakra vonatkozóan sztornírozni kell a készlettranzakció-archívumot.
- Archivált időszakokra nem lehet elszámolóárra való átalakítást végezni. Elszámolóárra való átalakítás előtt az adott időszakra vonatkozóan sztornírozni kell a készlettranzakció-archívumot.
- A készlettranzakciókból származó készletjelentéseket befolyásolja a készlettranzakciók archiválása. Ezek a jelentések tartalmazzák a készletkorosítási jelentést és a készletérték-jelentéseket.
- A készlet-előrejelzésekre hatással lehet, ha az archivált időszakok időhorizontja alatt futnak.

## <a name="prerequisites"></a>Előfeltételek

A készlettranzakciók csak olyan időszakokban archiválhatók, ahol teljesülnek a következő feltételek:

- A főkönyvi időszakot le kell zárni.
- A készletzárást az archívum záró dátumán vagy azt követően kell futtatni.
- Az időszaknak legalább egy évvel az archívum időszakának kezdési dátuma előtt kell lennie.
- Nem létezhetnek meglévő készlet-újraszámítások.

## <a name="archive-inventory-transactions"></a>Készlettranzakciók archiválása

Készlettranzakciók archiválásához kövesse az alábbi lépéseket.

1. Lépjen a **Készletkezelés** \> **Időszakos feladatok** \> **Adattisztítás** \> **Készlettranzakció archívuma** pontra.

    Megjelenik a **Készlettranzakciók archívuma** oldal, és megjeleníti az archivált folyamatrekordok listáját.

    ![Készlettranzakciók archívumának oldala](media/archive-inventory-empty.png "Készlettranzakciók archívumának oldala")

1. A műveletpanelen válassza ki a **Készlettranzakciók archívumát** készlettranzakció-archívum létrehozásához.
1. A **Készlettranzakciók archívuma** párbeszédpanel **Paraméterek** gyorslapján állítsa be a következő mezőket:

    - **Kezdési dátum lezárt főkönyvi időszakban** – Válassza ki a legkorábbi tranzakció dátumát, amit szerepeltetni szeretne az archívumban.
    - **Záró dátum lezárt főkönyvi időszakban** – Válassza ki a legkésőbbi tranzakció dátumát, amit szerepeltetni szeretne az archívumban.

    ![Készlettranzakciók archívumának párbeszédablaka](media/archive-inventory-dates.png "Készlettranzakciók archívumának párbeszédablaka")

    > [!NOTE]
    > Csak az [előfeltételeknek](#prerequisites) megfelelő időszakok választhatók ki.

1. A **Futtatás a háttérben** gyorslapon az igényeinek megfelelően állítsa be a kötegelt feldolgozás részleteit. Kövesse a Microsoft Dynamics 365 Supply Chain Management kötegelt feladatokkal kapcsolatos általános lépéseit.
1. Válassza ki az **OK** lehetőséget.
1. Egy üzenet jelenik meg, amely arra kéri, hogy erősítse meg a folytatást. Olvassa el alaposan az üzenetet, majd kattintson az **Igen** gombra, ha folytatni szeretné.

    Egy üzenet jelenik meg, amely jelzi, hogy a készlettranzakciók archiválási feladata felkerült a köteg feldolgozási sorára. A feladat elindul a kijelölt időszak készlettranzakcióinak archiválására.

## <a name="view-archived-inventory-transactions"></a>Archivált készlettranzakciók megtekintése

A **Készlettranzakciók archívuma** oldal a teljes archiválási előzményeket mutatja. A rács minden sorában olyan adatok láthatók, mint például az archívum létrehozási dátuma, az a felhasználó, aki létrehozta, valamint annak állapota.

![Készlettranzakciók archívumának oldalán található archiválási előzmények](media/archive-inventory-full.png "Készlettranzakciók archívumának oldalán található archiválási előzmények")

Az oldal tetején lévő legördülő listából válasszon a következő értékek közül a rácsban látható archívum szűréséhez:

- **Aktív** – Csak az aktív archívumok megjelenítése, a sztornírozott archívumok nem.
- **Összes** – Minden archívum megjelenítése, aktív és sztornírozva is.

A rács minden egyes archívumához a következő információk biztosítanak:

- **Aktív** – A bejelölés jelzi, hogy az archívum aktív.
- **Kezdési dátum** – Az archívumba kerülő legrégebbi tranzakció dátuma.
- **Záró dátum** – Az archívumba kerülő legújabb tranzakció dátuma.
- **Ütemezte** – Az archívumot létrehozó felhasználói fiók.
- **Végrehajtva** – Az archívum létrehozásának dátuma.
- **Sztornírozás** – A jelölés azt jelzi, hogy az archívum sztornózva lett.
- **Aktuális frissítés leállítása** - A jelölés azt jelzi, hogy az archívum folyamatban van, de szünetel.
- **Állapot** – Az archívum feldolgozási állapota. A lehetséges értékek: *Várakozás*, *Folyamatban* és *Kész*.

A rács feletti eszköztár a következő gombokat tartalmazza, amelyek a kiválasztott archívummal való munkára használhatók:

- **Archivált tranzakciók** – a kijelölt archívum részletes megjelenítése. A megjelenő **Archivált tranzakciók** oldal az archívum összes tranzakcióját megjeleníti.

    ![Archivált tranzakciók oldala](media/archive-inventory-transactions.png "Archivált tranzakciók oldala")

    Ha az **Archivált tranzakciók** lapon egy adott tranzakcióval kapcsolatban további információkat is meg kell jeleníteni, jelölje ki azt a rácsban, majd a műveleti ablaktáblán válassza ki az **Archivált tranzakció részletei** elemet. A megjelenő **Archivált tranzakció részletei** oldalon olyan adatok jelennek meg, mint a főkönyvi elszámolás, a kapcsolódó részfőkönyv hivatkozásai és a pénzügyi dimenziók.

- **Az archiválás szüneteltetése** – A jelenleg feldolgozás alatt álló kijelölt archívum szüneteltetése. A szünet csak az archiválási feladat létrehozása után lép életbe. Emiatt előfordulhat egy kis késés a szünet hatályba lépése előtt. Ha egy archívum szünetel, az **Aktuális frissítés leállítása** mezőben megjelenik egy pipa.
- **Az archiválás folytatása** – A jelenleg szünetelő kijelölt archívum feldolgozásának folytatása.
- **Sztornírozás** – A kijelölt archívum sztornírozása. Az archívum csak akkor sztornírozható, ha az **Állapot** mező beállítása *Kész*. Ha egy archívum sztornírozva van, a **Sztornírozás** mezőben megjelenik egy pipa.

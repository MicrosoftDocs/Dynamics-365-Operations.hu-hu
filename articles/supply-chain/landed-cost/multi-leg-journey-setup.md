---
title: Többszakaszos út beállítása
description: Ez a témakör azt ismerteti, hogyan lehet többszakaszos utakat beállítani a Partraszállítási költség modulhoz.
author: Weijiesa
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMLegTable, ITMJourneyTable, ITMActivityTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: c65a3d3971593ccf832a6af3c8c27d56a68b46c8
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689719"
---
# <a name="multi-leg-journey-setup"></a>Többszakaszos út beállítása

[!include [banner](../../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet többszakaszos utakat beállítani a **Partraszállítási költség** modulhoz.

## <a name="legs"></a>Szakaszok

A szakaszokat a hajóút különböző részeinek azonosítására használják. Minden egyes szakasz úgy épül fel, hogy kiválasztják a kiindulási és a célkikötőket, valamint az adott szakaszhoz használt szállítási módot. Az egyes szakaszokhoz átfutási idők társíthatók. Az átfutási idők a szállítmányok nyomon követését segítik, és felhasználhatók a hajóúton szállított áru becsült szállítási dátumának kiszámításához is. Ezenkívül amikor befejeződik egy út szakasza, a hajóút, a szállítókonténer és a kapcsolódó beszerzési rendelési sorok állapota a nyomonkövetési ellenőrzés beállításával frissíthető. A szakaszokat egyetlen hajóútsablonnal is használhatja, vagy akár több hajóútsablonnal is újrafelhasználhatja. A konténer berakodása, a vámkezelés és a helyi szállítás általában szakaszokként vannak beállítva, és ezekhez egy nem meghatározott szállítási kikötőt használnak.

A szakaszok használatához lépjen ide: **Partraszállítási költség \> Többszakaszos út beállítása \> Szakaszok**. Itt lehet megtekinteni, megnyitni, létrehozni és törölni a szakaszok rekordjait. Az alábbi táblázat bemutatja az egyes rekordokhoz rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Szakasz | Adja meg a hajóút szakaszának egyedi azonosító nevét/számát. |
| Leírás | Adja meg a hajóút szakaszának leírását. Ez a leírás általában azonosítja a kiindulási kikötőt és a célkikötőt, illetve a hajóút szakaszát. |
| Kiindulási kikötő | Adja meg a szakasz során szállított áruk származási pontját. |
| Célkikötő | Adja meg a szakasz során szállított áruk rendeltetési pontját. |
| Kézbesítési mód | Adja meg a szakasz szállítási módját. |

## <a name="journey-templates"></a>Utazássablonok

A hajóútsablon meghatározza a két kikötő közötti többszakaszos utat, amelyet az áruk egy hajóút során megtesznek. Az útszakaszok egyesítve vannak azon idő meghatározásához, ami ahhoz szükséges, hogy az áruk a szállító származási pontjától a végső raktárig eljussanak. Ha a szakaszokat egy meghatározott sorrendben helyezik a hajóútsablonba, az átfutási idők azonosítják a hajóút egyes szakaszainak, konténereinek és beszerzési sorainak dátumát. A [Követési vezérlőközpont](delivery-information-setup.md) segítségével beállíthatja a hajóútsablont alkotó szakaszokhoz kapcsolódó átfutási időket. A hajóútsablont akkor is használja a rendszer, amikor be van állítva egy hajóút automatikus költsége. Hajóút meghatározásakor az áruk szállításával járó költség meghatározható az automatikus költségek oldalon.

A hajóútsablonok használatához lépjen ide: **Partraszállítási költség \> Többszakaszos út beállítása \> Hajóútsablonok**. Itt lehet megtekinteni, megnyitni, létrehozni és törölni a hajóútsablonokat.

Mindegyik hajóútsablonhoz állítsa be a következő mezőket a fejlécben.

| Mező | Leírás |
|---|---|
| Utazássablon | Adja meg a hajóútsablon egyedi azonosító nevét/számát. A hajóútsablon általában a hajóút kiindulási pontját és rendeltetési pontját írja le. |
| Leírás | Adja meg a hajóútsablon leírását. A leírás általában a kiindulási kikötőt és a célkikötőt, valamint a hajóút típusát jelzi. |

A **Sorok** szakaszban adjon hozzá egy sort a hajóút minden szakasza számára, és helyezze a sorokat sorba. Az eszköztár **Fel** és **Le** nyílgombjaival módosíthatja a sorok sorrendjét. Az alábbi táblázat bemutatja az egyes sorokhoz rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Szakasz | Válassza ki a hajóúthoz hozzáadni kívánt szakaszt. |
| Leírás | A szakasz leírása. |
| Kiindulási kikötő | A szakasz során szállított áruk származási pontjának számító kikötő. Ez a kikötő a hajóút automatikus költségeinek meghatározására használt célkikötő. |
| Célkikötő | A szakasz során szállított áruk célkikötője. |
| Szállítás módja | Az adott szakaszhoz használatos szállítási mód. |
| Utazás kiindulási kikötője | Ha a szakaszhoz megadott kikötő használatos az automatikus költségek meghatározására, jelölje be ezt a jelölőnégyzetet, ha azt szeretné, hogy ez legyen a kiindulási kikötő. Ez a kikötő jelenik meg a hajóút fejlécében. |
| Utazás célkikötője | Ha a szakaszhoz megadott kikötő használatos az automatikus költségek meghatározására, jelölje be ezt a jelölőnégyzetet, ha azt szeretné, hogy ez legyen a célkikötő. Ez a kikötő jelenik meg a hajóút fejlécében. |
| Szállítmányozási vállalat | Válassza ki a szakaszhoz használt szállítmányozó vállalatot. |

## <a name="activities"></a>Tevékenységek

A **Tevékenységek** oldalon megadott beállítások meghatározzák a szakasz célkikötőjénél potenciálisan előforduló tevékenységek típusait. Azok a felhasználók, akik az **Összes szállítókonténer** oldalon dolgoznak, akkor választhatnak ezen az értékek közül, amikor meg tudják becsülni az egyes tevékenységek időtartamát, és összehasonlítási célból rögzíteni tudják a tényleges időtartamot.

A tevékenységek beállításához kattintson a **Partraszállítási költség \> Többszakaszos út beállítása \> Tevékenységek** lehetőségre. A műveleti ablaktábla gombjaival lehet tevékenységeket hozzáadni, eltávolítani és szerkeszteni.

Az alábbi táblázat bemutatja a rácsban az egyes tevékenységhez rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Tevékenység | A tevékenység neve. |
| Leírás | A tevékenység leírása. |
| Szállítmányozási vállalat | A tevékenységhez társított szállítóvállalat szállítói számlája. |

---
title: Globális mobileszköz-paraméterek
description: Ez a témakör bemutatja a mobileszköz beállításának módját a Raktárkezelési paraméterek lapon.
author: HuberIvan
ms.date: 08/13/2021
ms.topic: article
ms.search.form: WHS
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-huberivan
ms.search.validFrom: 2021-08-13
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 03c10232d55c99c73e625170797f89f6c77e812b
ms.sourcegitcommit: 99bde425ade701ef244c6bca6d411aef94a59b3c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/20/2021
ms.locfileid: "7505573"
---
# <a name="global-mobile-device-parameters"></a>Globális mobileszköz-paraméterek

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogy hogyan lehet beállítani a globális raktárkezelési paramétereket, amelyek a rendszer és a mobileszköz kapcsolatát befolyásolják.

A raktári dolgozók beállításának további tudnivalókat lásd a [Raktári dolgozó kezelése](manage-warehouse-workers.md) oldalon. Az azonosítótáblák kezelésével mobileszközön kapcsolatos részletes információk: [Azonosítótábla-bevételezés a Warehouse Management mobilalkalmazás használatával](warehousing-mobile-device-app-license-plate-receiving.md). A ciklikus leltározási folyamatokkal kapcsolatos további tudnivalókat lásd a [Ciklikus leltározás](cycle-counting.md) és a [Ciklikus leltározás példahelyzetek](cycle-counting-scenarios.md) részben.

## <a name="open-the-warehouse-management-parameters-page"></a>Nyissa meg a Raktárkezelési paraméterek engedélyezése oldalt

A **Raktárkezelési paraméterek oldal** megnyitásához menjen a **Raktárkezelés \> Beállítások \> Raktárkezelési paraméterek** szakaszba. Ezután beállíthatja a mobileszközön végzett munkához kapcsolódó mezőket a témakör következő részében leírt módon.

## <a name="mobile-device-fasttab-on-the-general-tab"></a>A Mobileszköz gyorslapja az Általános lapon

A globális mobileszköz-beállítások a **Raktárkezelési paraméterek** oldal **Általános** lapján, a **Mobileszköz** gyorslapon találhatók. Az alábbi mezők állnak rendelkezésre.

| Mező | Leírás |
|---|---|
| Mobileszköz megjegyzéstípusa | Válassza ki az értékesítési rendelések kiadásakor a dolgozóknak megjelenített információtípust. |
| Beolvasott mennyiség korlátja | Adja meg azt a maximális cikkmennyiséget, amelyet a dolgozó beolvashat az egyes munkamenetek során egy olyan mobileszköz-menüelem segítségével, amelynek **Munkalétrehozási folyamat** értéke *Igazítás be*. Ez a mező nincs hatással semmilyen más típusú menüelem használatával végzett beolvasásokra. |
| Mobileszköz-munkamenetek naplózása | A dolgozó bejelentkezési előzményeit naplóként is meg lehet tartani *Igen* beállítással. A napló megtekintéséhez lépjen a **Munka felhasználói munkamenetek \> Lekérdezések és jelentések \> Mobileszköznaplók \> Munkafelhasználói munkamenetek**. |
| Tárolt hibák száma | Adja meg, hogy legfeljebb hány hibarekordot kell tárolnia a rendszernek. A hibanapló megtekintéséhez lépjen a **Munkafelhasználói munkamenetek \> Lekérdezések és jelentések \> Mobileszköznaplók \> Munkafelhasználói munkamenetek**. |
| Alapértelmezett raktári átmozgatási napló | Annak a naplónak a kiválasztása, amely akkor használatos, amikor a dolgozók mobileszköz használatával áthelyezik a termékeket az egyik raktárból a másikba. |
| Beszerzési rendelés sorregisztrációjának engedélyezése külső ellenőrzéskor | Akkor állítsa *Igen* értékűre ezt a beállítást, ha a dolgozóknak mobileszköz használatával kell regisztrálniuk a **Külső ellenőrzés alatt** *Jóváhagyási állapot* értékkel megadott beszerzési rendelési sorait. Állítsa *Nem* beállításra ezt a beállítást, ha meg szeretné akadályozni, hogy a dolgozók sorokat regisztráljanak a külső ellenőrzésen áteső beszerzési rendelésekhez. |
| RSAT-támogatás engedélyezése | Ez a mező engedélyezi a Warehouse Management mobilalkalmazás feladat érvényesítőjét, amely naplózza és ellenőrzi az alkalmazás által végrehajtani kívánt műveleteket. Mivel ez a folyamat jelentősen csökkentheti a rendszer teljesítményét, csak tesztelés közben engedélyezze az érvényesítőt. Soha ne engedélyezze éles környezetben. |

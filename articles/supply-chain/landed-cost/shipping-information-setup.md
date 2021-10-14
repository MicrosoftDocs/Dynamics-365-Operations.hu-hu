---
title: Szállítási adatok beállítása
description: Ez a témakör azt ismerteti, hogyan lehet szállítási adatokat beállítani a Partraszállítási költség modulhoz.
author: sherry-zheng
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMGoodsDescriptionTable, ITMVesselTable, ITMExporterTable, ITMCommodityCodeTable, ITMCustomsDescription
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 86350acfd056be2b43fc856e3b76b1632989a804
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579688"
---
# <a name="shipping-information-setup"></a>Szállítási adatok beállítása

[!include [banner](../../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet szállítási adatokat beállítani a **Partraszállítási költség** modulhoz.

## <a name="description-of-goods"></a><a name="description-of-goods"></a>Áruk leírása

Az áruk leírása elősegíti a hajóút, a szállítókonténer vagy az árulevelek és a benne lévő áruk azonosítását. Az áruk leírása a szállítókonténer fejlécében vagy az árulevél fejlécében választható ki.

Az áruk leírásával a **Partraszállítási költség \> Szállítási adatok beállítása \> Áruk leírása** részben dolgozhat. Itt lehet megtekinteni, megnyitni, létrehozni és törölni az áruk leírásait. Az alábbi táblázat bemutatja az egyes rekordokhoz rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Áruk leírása | Adjon meg egyedi azonosító nevet / számot a leírást használó árutípushoz. |
| Leírás | Adja meg az ebbe a kategóriába tartozó árutípus leírását. |

## <a name="vessels"></a><a name="vessels"></a>Hajók

A hajó annak a hajónakaz egyedi neve, amelyet a szállítmányozó vállalat vagy ügynökség használ. Hajóút létrehozása során mindig ki kell választani vagy be kell írni egy hajót. Ha gyakran ugyanazokat a hajókat használja, gyorsabban és egyszerűbben hozhat létre új hajóútakat, ha mindegyikhez egy hajórekordot hoz létre, ezáltal lehetővé téve a felhasználók számára, hogy a listáról kiválasszák a hajó nevét vagy számát, és ne minden alkalommal manuálisan kell beírják a nevet vagy a számot.

A hajókkal a **Partraszállítási költség \> Szállítási adatok beállítása \> Hajók** részben dolgozhat. Itt lehet megtekinteni, megnyitni, létrehozni és törölni a hajórekordokat. Az alábbi táblázat bemutatja az egyes rekordokhoz rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Hajó | Adja meg azon hajó egyedi azonosító nevét/számát, amelyet egy hajóúton áruszállításra használ. |
| Leírás | Adja meg a hajó leírását. Ez a leírás általában azonosítja a hajó nevét és a szállítmányozó vállalat/ügynök nevét. |
| Szállítás módja | Válassza ki a hajó által használt szállítási módot (például _Légi_, _Tengeri_ vagy _Vonat_). |

## <a name="exporters"></a>Exportőrök

Minden exportőrrekord egy szállítót vagy exportőrt azonosít, amely a hajóútért felelős szállítóként definiálható. Az exportőr társítható hajóúthoz és jelentéskészítésre használható.

Az exportőrökkel a **Partraszállítási költség \> Szállítási adatok beállítása \> Exportőrök** részben dolgozhat. Itt lehet megtekinteni, megnyitni, létrehozni és törölni az exportőröket. Az alábbi táblázat bemutatja az egyes rekordokhoz rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Exportőr | Adja meg azon exportőr egyedi azonosító nevét/számát, amelyet egy hajóúton használ. |
| Leírás | Adja meg az exportőr leírását. Ez a leírás általában azonosítja a szállítmányozó vállalat/ügynök teljes nevét. |

## <a name="commodity-codes"></a>Árucikk-kódok

Az árucikk-kódok segítséget segítenek a vámügyi azonosításban és a hajóúton érintett áruk vámtételének kiszámításában. A **Kiadott termékek** oldalon kiválaszthatja az árucikk-kódokat.

Az árucikk-kódokkal a **Partraszállítási költség \> Szállítási adatok beállítása \> Árucikk-kódok** részben dolgozhat. Itt lehet megtekinteni, megnyitni, létrehozni és törölni az árucikk-kódokat. Az alábbi táblázat bemutatja az egyes rekordokhoz rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Árucikk-kód | Adjon meg egy egyedi kódot az ilyen típusú árucikkhez. |
| Leírás | Adja meg az árucikktípus leírását. |

## <a name="customs-description"></a>Vámügyi leírás

A vámügyi leírások segítik a vámkezelés által érintett áruk azonosítását. Vámügyi leírást a **Kiadott termékek** oldalon vagy a beszerzési rendelés sorainál választhat ki.

A vámügyi leírásokkal a **Partraszállítási költség \> Szállítási adatok beállítása \> Vámügyi leírás** részben dolgozhat. Itt lehet megtekinteni, megnyitni, létrehozni és törölni a vámügyi leírásokat. Az alábbi táblázat bemutatja az egyes rekordokhoz rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Vámügyi leírás | Adjon meg egy egyedi kódot az ilyen típusú vámügyi besoroláshoz. Ez a kód gyakran a vámhatóság által az áruk leírására és kvalitatív értékére vonatkozó hivatalos leírás lesz. |
| Leírás | Adja meg a vámügyi besorolás leírását. |

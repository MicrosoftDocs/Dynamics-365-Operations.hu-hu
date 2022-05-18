---
title: Hajóút állapotának beállítása
description: Ez a témakör leírja, hogyan lehet megállapítani a felhasználók által hajóutakhoz rendelhető állapotértékeket.
author: Weijiesa
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMStatusTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 5a6741085f0244166fc46aa14a031d3550d11d9d
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8691159"
---
# <a name="voyage-status-setup"></a>Hajóút állapotának beállítása

[!include [banner](../../includes/banner.md)]

A **Hajóút állapota** oldalon meghatározza a felhasználók által a hajóutakhoz rendelhető állapotértékeket. A felhasználók a hajóút minden szintjéhez hozzárendelhetnek egy állapotot: hajóút, szállítókonténer, árulevél, beszerzési rendelés és cikk (vásárlási sorok és átmozgatási rendelési sorok). Ezeknek két céljuk van:

- A felhasználó tájékoztatása a hajóút, a szállítókonténer, az árulevél, a beszerzési rendelés vagy a cikk állapotáról (beszerzési sorok és átmozgatási rendelési sorok).
- A költségterület használatának korlátozása a módosítás vagy törlés megakadályozásával.

A hajóút állapotának beállításához lépjen a **Partraszállítási költség \> Hajóút beállítása \> Hajóút állapota** lehetőségre. A műveleti ablaktábla gombjaival lehet állapotokat hozzáadni, eltávolítani és szerkeszteni.

Minden költségterületnek saját hajóállapot-hierarchiája és készlete van. Ezért a **Hajóút állapota** oldalon a **Költségterület** mezőben ki kell választania azt a költségterületet, amelyhez kapcsolódóan hajóút-állapotokat szeretne megtekinteni vagy létrehozni. Ezután szükség szerint minden hajóút állapota esetén állítsa be a következő táblázatban leírt mezőket. Ne feledje, hogy a hajóút állapotát a rendszeresemények automatikusan módosíthatják, például a követési központ használatával meghatározott szabályok.

| Mező | Leírás |
|---|---|
| Út állapota | Adja meg a hajóút állapotának nevét. |
| Leírás | Adja meg a hajóút állapotának leírását. |
| Módosítás | Jelölje be ezt a jelölőnégyzetet, ha a felhasználók módosíthatják az ilyen állapotú hajóutakat. |
| Eltávolítás | Jelölje be ezt a jelölőnégyzetet, ha a felhasználók törölhetik az ilyen állapotú hajóutakat. |
| Kötelező | Jelölje be ezt a jelölőnégyzetet, ha kötelezővé teszi a hajóút állapotát, hogy ne legyen átugorható. |
| Szülő | Ezzel a mezővel hierarchiát hozhat létre az állapotértékek között. A hajóút-állapotok (manuálisan vagy automatikusan) csak lefelé módosíthatók a hierarchiában szülőállapotról az egyik gyermekállapotra.

> [!NOTE]
> Csak a szervezete által használt hajóút-állapotokat kell beállítani. A jellemző hajóút-állapotok a következők: *Visszaigazolva*, *Úton lévő áruk*, *Beérkezett*, *Költségszámításra kész* és *Költség elszámolva*. Előfordulhatnak azonban más állapotok is.

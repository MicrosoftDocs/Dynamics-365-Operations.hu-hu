---
title: Partraszállítási költséghez hozzáadott szállítói beállítások
description: Ez a témakör a Landed költség modul engedélyezésekor a meglévő Szállítók laphoz hozzáadott új mezőket írja le. Ezekkel a mezőkkel állíthatja be a Partraszállási költség funkcióival együtt használt szállítókat.
author: Weijiesa
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 84d1dee0815b036a3d411eabff49d8a08249bed3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882576"
---
# <a name="vendor-settings-added-for-landed-cost"></a>Partraszállítási költséghez hozzáadott szállítói beállítások

[!include [banner](../../includes/banner.md)]

A **Partraszállítási költség** modul engedélyezésekor a rendszer számos új mezőt ad hozzá a meglévő **Szállítók** oldalhoz. Ezekkel a mezőkkel állíthatja be a Partraszállási költség funkcióival együtt használt szállítókat.

A megfelelő mezők beállítása: **Beszerzés és forrás \> Szállítók \> Minden szállító**. Nyisson meg egy meglévő szállítót vagy hozzon létre egy új szállítót, majd válassza a **Vegyes részletek** gyorslapot. A **Partraszállítási költség** modul által hozzáadott új mezők a **Hajóutak** fejléc alatt jelennek meg. Az alábbi táblázatban részletes leírás található ezekről a mezőkről.

| Mező | Leírás |
|---|---|
| Szállítás típusa | <p>Válassza ki a szállító szerepkörét a Partraszállítási költséggel kapcsolatban:</p><ul><li>**Nincs** – a szállítónak nincs olyan konkrét szerepköre, amely a Partraszállítási költséghez kapcsolódik. Ez az alapértelmezett beállítás, mivel a legtöbb szállítónak valószínűleg nincs konkrét szerepköre.</li><li>**Szállítmányozó vállalat** – a szállító egy szállítmányozó vállalat. Az ilyen típusú szállítmányozók elérhetők a **Szállítmányozó vállalat** mezőben találhatók a **Hajóutak** oldalon.</li><li>**Vámügynök** – a szállító egy vámügynök. Az ilyen típusú szállítmányozók elérhetők a **Vámügynök** mezőben találhatók az **Árulevelek** oldalon.</li><li>**Ügynök** – a szállító egy ügynök. Az ilyen típusú szállítmányozók elérhetők az **Ügynök** mezőben találhatók a **Szállítók** és a **Beszerzési rendelések** oldalon.</li></ul> |
| Költségtípuscsoport | Az [automatikus költségek](auto-cost-setup.md) kiválasztása céljából rendelje hozzá a szállítót egy költségtípuscsoporthoz. |
| Kiindulási kikötő | Válassza ki a hajóút származási kikötőjét. |
| Ügynök | A szállítótól való beszerzések alapértelmezett ügynöke. |
| Importálással kapcsolatos költségszámításhoz tartozó szállító | <p>Annak jelzése, hogy a szállító Partraszállítási költség típusú szállító-e.</p><p>**Tipp:** Ez a mező a rekordszintű biztonsággal együtt korlátozhatja a hajóút létrehozásakor megjelenő beszerzési rendeléseket.</p> |
| Szállítmányozási vállalat | Válassza ki a szállító beszerzési rendeléseinek létrehozásakor használt alapértelmezett szállítmányozó vállalatot. |
| Szolgáltató | Annak jelzése, hogy a szállító szolgáltató-e. |
| Túl-/alulteljesítési tűréshatár szerinti csoport | Válassza ki a szállító alapértelmezett túl-/alulteljesítési tűréshatár szerinti csoportját. |

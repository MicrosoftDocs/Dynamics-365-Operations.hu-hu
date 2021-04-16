---
title: Tárgyi eszköz áthelyezése leltárba
description: Ez a cikk azt a Magyarországra vonatkozó országspecifikus funkciót írja le, amely lehetővé teszi a tárgyi eszközök készletbe való átvitelét a nettó könyv szerinti értéken. A tárgyi eszköz állapota „Selejtezett” lesz, a nettó könyv szerinti érték pedig 0 (nulla). Ezenkívül a készletben lévő termék mennyisége 1-re van állítva, és az önköltségi ár a tárgyi eszköz nettó könyv szerinti értékére van beállítva.
author: Anasyash
ms.date: 04/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalAsset
audience: Application User
ms.reviewer: kfend
ms.custom: 274423
ms.search.region: Hungary
ms.author: anasyash
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: bdd7b81a2563b86cda5fa04025d958e8b23062ba
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815017"
---
# <a name="move-a-fixed-asset-to-inventory"></a>Tárgyi eszköz áthelyezése leltárba

[!include [banner](../includes/banner.md)]

Ez a cikk azt a Magyarországra vonatkozó országspecifikus funkciót írja le, amely lehetővé teszi a tárgyi eszközök készletbe való átvitelét a nettó könyv szerinti értéken. A tárgyi eszköz állapota „Selejtezett” lesz, a nettó könyv szerinti érték pedig 0 (nulla). Ezenkívül a készletben lévő termék mennyisége 1-re van állítva, és az önköltségi ár a tárgyi eszköz nettó könyv szerinti értékére van beállítva.

Tárgyi eszközöket helyezhet át a készletbe a nettó könyv szerinti értéken. Az átvitel nyomán a tárgyi eszköz állapota **Selejtezett** lesz, a nettó könyv szerinti érték pedig **0** (nulla). Ezenkívül a készletben lévő termék mennyisége **1**-re van állítva, és az önköltségi ár a tárgyi eszköz nettó könyv szerinti értékére van beállítva. Használja a szokásos Készlet a tárgyi eszközökhöz naplót arra, hogy átvigye a tárgyi eszközöket a készletbe. 

Tárgyi eszköz készletbe való áthelyezéséhez kövesse az alábbi lépéseket.

1.  Ellenőrizze, hogy a tárgyi eszköz értékcsökkenése fel van-e adva legkésőbb az átvitel napján.
2.  Hozzon létre egy új készletet a tárgyi eszközök naplójához.
3.  A naplóvonalakon válassza ki az átadandó eszközt és a fogadott terméket.
4.  Adjon meg egy negatív mennyiséget.
5.  Ellenőrizze, hogy az **Önköltségi ár** mezőben szerepel a **Nettó könyv szerinti** érték.
6.  Napló feladása.
7.  Ellenőrizze, hogy a tárgyi eszköz és a készletügyletek helyesen lettek-e létrehozva.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
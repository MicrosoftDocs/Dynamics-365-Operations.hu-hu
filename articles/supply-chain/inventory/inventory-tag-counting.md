---
title: "Készletcímke számlálása"
description: "Ez a cikk tájékoztatást ad a címkeszámlálásról, ami akkor használatos, amikor egy raktár tényleges tartalmát hasonlítja össze az aktuális készlettel."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalCount, InventJournalCountTag
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 11594
ms.assetid: 03772d0e-5c37-454c-ab85-82bc8b60a76d
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 1b1281c41e3427148cdbd7bd874f3408056e3df1
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---

# <a name="inventory-tag-counting"></a>Készletcímke számlálása

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

Ez a cikk tájékoztatást ad a címkeszámlálásról, ami akkor használatos, amikor egy raktár tényleges tartalmát hasonlítja össze az aktuális készlettel.

A **Címkeleltár** lapon sorok létrehozásával minden készletcikkre szám formájú - például 1 és 500 közötti - címke kerül. A leltár során adja meg a cikkszámot és a mennyiséget a megfelelő címkén. A címke majd használható az alapja a címke számbavételi napló bevitt adatokat. A címkeleltárnapló feladásakor a címkeleltárnapló-sorok alapján új leltárnapló jön létre a **Számlálás** oldalon. A címkeleltárnapló feladásakor a címkeleltárnapló-sorok alapján új leltárnapló jön létre. Címke száma egy adott készletdimenzió elemek, jelölje be a dimenzió a a **Megjelenítendő dimenzió** látható a címke számbavételi napló létrehozásakor. Ha például egy adott raktárban található cikkek száma, jelölje be a **Raktár** négyzet jelölését. Ha a **Cikkek zárolása leltár közben** csúszka a **Készlet- és raktárkezelési paraméterek** négyzet be van jelölve, a cikkek ténylegesen nem frissíthető leltározás közben. Azonban címkeleltárnaplókban szereplő cikkek a leltár során nincs zárolva. Nem jönnek létre készlettranzakciók, amíg a címkenaplósorokat át nem vitték egy leltárnaplóba a feladás során. Ha a címkék bevitele véletlenszerűen történik, és szeretné azonosítani a hiányzó címkéket, akkor a sorok rendezéséhez kattintson a **Címke** mezőre.

<a name="additional-resources"></a>További erőforrások
--------

[Ciklikus leltározás](../warehousing/cycle-counting.md)


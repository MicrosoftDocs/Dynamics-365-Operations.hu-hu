---
title: "Készletcímke számlálása"
description: "Ez a cikk tájékoztatást ad a címkeszámlálásról, ami akkor használatos, amikor egy raktár tényleges tartalmát hasonlítja össze az aktuális készlettel."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventJournalCount, InventJournalCountTag
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 11594
ms.assetid: 03772d0e-5c37-454c-ab85-82bc8b60a76d
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 896b91647b65843bf67211cab68b4dd08e379b18
ms.lasthandoff: 03/31/2017


---

# <a name="inventory-tag-counting"></a>Készletcímke számlálása

[!include[banner](../includes/banner.md)]


Ez a cikk tájékoztatást ad a címkeszámlálásról, ami akkor használatos, amikor egy raktár tényleges tartalmát hasonlítja össze az aktuális készlettel. 

A **Címkeleltár** lapon sorok létrehozásával minden készletcikkre szám formájú - például 1 és 500 közötti - címke kerül. A leltár során adja meg a cikkszámot és a mennyiséget a megfelelő címkén. A címke majd használható az alapja a címke számbavételi napló bevitt adatokat. A címkeleltárnapló feladásakor a címkeleltárnapló-sorok alapján új leltárnapló jön létre a **Számlálás** oldalon. A címkeleltárnapló feladásakor a címkeleltárnapló-sorok alapján új leltárnapló jön létre. Címke száma egy adott készletdimenzió elemek, jelölje be a dimenzió a a **Megjelenítendő dimenzió** látható a címke számbavételi napló létrehozásakor. Ha például egy adott raktárban található cikkek száma, jelölje be a **Raktár** négyzet jelölését. Ha a **Cikkek zárolása leltár közben** csúszka a **Készlet- és raktárkezelési paraméterek** négyzet be van jelölve, a cikkek ténylegesen nem frissíthető leltározás közben. Azonban címkeleltárnaplókban szereplő cikkek a leltár során nincs zárolva. Nem jönnek létre készlettranzakciók, amíg a címkenaplósorokat át nem vitték egy leltárnaplóba a feladás során. Ha a címkék bevitele véletlenszerűen történik, és szeretné azonosítani a hiányzó címkéket, akkor a sorok rendezéséhez kattintson a **Címke** mezőre.

<a name="see-also"></a>Lásd még
--------

[Ciklikus leltározás](../warehousing/cycle-counting.md)





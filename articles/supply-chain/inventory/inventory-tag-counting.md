---
title: Készletcímke számlálása
description: Ez a témakör tájékoztatást ad a címkeszámlálásról, ami akkor használatos, amikor egy raktár tényleges tartalmát hasonlítja össze az aktuális készlettel.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCountTag
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Retail
ms.custom: 11594
ms.assetid: 03772d0e-5c37-454c-ab85-82bc8b60a76d
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: efb555cdfbcf3fd0c10ec0e2abcdbe7f4a90d82d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429274"
---
# <a name="inventory-tag-counting"></a>Készletcímke számlálása

[!include [banner](../includes/banner.md)]

Ez a témakör tájékoztatást ad a címkeszámlálásról, ami akkor használatos, amikor egy raktár tényleges tartalmát hasonlítja össze az aktuális készlettel.

A **Címkeleltár** lapon sorok létrehozásával minden készletcikkre szám formájú - például 1 és 500 közötti - címke kerül. A leltár során adja meg a cikkszámot és a mennyiséget a megfelelő címkén. A címke majd használható az alapja a címke számbavételi napló bevitt adatokat. A címkeleltárnapló feladásakor a címkeleltárnapló-sorok alapján új leltárnapló jön létre a **Számlálás** oldalon. A címkeleltárnapló feladásakor a címkeleltárnapló-sorok alapján új leltárnapló jön létre. Címke száma egy adott készletdimenzió elemek, jelölje be a dimenzió a a **Megjelenítendő dimenzió** látható a címke számbavételi napló létrehozásakor. Ha például egy adott raktárban található cikkek száma, jelölje be a **Raktár** négyzet jelölését. Ha a **Cikkek zárolása leltár közben** csúszka a **Készlet- és raktárkezelési paraméterek** négyzet be van jelölve, a cikkek ténylegesen nem frissíthető leltározás közben. Azonban címkeleltárnaplókban szereplő cikkek a leltár során nincs zárolva. Nem jönnek létre készlettranzakciók, amíg a címkenaplósorokat át nem vitték egy leltárnaplóba a feladás során. Ha a címkék bevitele véletlenszerűen történik, és szeretné azonosítani a hiányzó címkéket, akkor a sorok rendezéséhez kattintson a **Címke** mezőre.

## <a name="additional-resources"></a>További erőforrások

[Ciklikus leltározás](../warehousing/cycle-counting.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
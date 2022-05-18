---
title: Szállításkezelésből származó vegyes költségek
description: Ez a témakör azt mutatja be, hogyan kell társítani a szállítás által generált költséget a költségkódhoz.
author: Weijiesa
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e54c94baeba487ccd8fe26e58d3e891e5e3a1088
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672598"
---
# <a name="transportation-management-miscellaneous-charges"></a>Szállításkezelésből származó vegyes költségek

[!include [banner](../includes/banner.md)]

Mint minden vegyes költségnél, a szállítás által generált költséghez is hozzá kell társítani a költségkódot. Ellenkező esetben nem kerülnek a rendelésbe vegyes költségként. A **Költségek kódja** határozza meg, hogyan történik a költség elszámolása annál a rendelésnél és rendelési sornál, amelyhez hozzá lett adva.

Menjen a **Szállításkezelés > Beállítás > Minősítés > Vegyes költségek** lehetőségre, és határozza meg a minősítési feltételeket, amelyek meghatározzák, hogy mikor alkalmaznak egy adott **Költségkódot** a költségnél.

Legalább egy beállítást ki kell választania minden olyan releváns **Költségmodul** beállításhoz (*Ügyfél* és *Szállító*), amelyben a **Vegyes költség típusa** *Egyik sem* értékre van állítva. Ha nincs megadva, a vegyes költséget *nem* adja hozzá a program a rendeléshez.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
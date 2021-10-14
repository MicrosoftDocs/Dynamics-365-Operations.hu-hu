---
title: Szállításkezelésből származó vegyes költségek
description: Ez a témakör azt mutatja be, hogyan kell társítani a szállítás által generált költséget a költségkódhoz.
author: Henrikan
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 776c73b1a29666e393bed7c40059a578fe86cb0d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576184"
---
# <a name="transportation-management-miscellaneous-charges"></a>Szállításkezelésből származó vegyes költségek

[!include [banner](../includes/banner.md)]

Mint minden vegyes költségnél, a szállítás által generált költséghez is hozzá kell társítani a költségkódot. Ellenkező esetben nem kerülnek a rendelésbe vegyes költségként. A **Költségek kódja** határozza meg, hogyan történik a költség elszámolása annál a rendelésnél és rendelési sornál, amelyhez hozzá lett adva.

Menjen a **Szállításkezelés > Beállítás > Minősítés > Vegyes költségek** lehetőségre, és határozza meg a minősítési feltételeket, amelyek meghatározzák, hogy mikor alkalmaznak egy adott **Költségkódot** a költségnél.

Legalább egy beállítást ki kell választania minden olyan releváns **Költségmodul** beállításhoz (*Ügyfél* és *Szállító*), amelyben a **Vegyes költség típusa** *Egyik sem* értékre van állítva. Ha nincs megadva, a vegyes költséget *nem* adja hozzá a program a rendeléshez.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
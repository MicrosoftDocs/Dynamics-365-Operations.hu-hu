---
title: Szállításkezelésből származó vegyes költségek
description: Ez a témakör azt mutatja be, hogyan kell társítani a szállítás által generált költséget a költségkódhoz.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 2b703d770c7f9ea684716368cf1e7dbe5fec8710
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2020
ms.locfileid: "4429988"
---
# <a name="transportation-management-miscellaneous-charges"></a>Szállításkezelésből származó vegyes költségek

[!include [banner](../includes/banner.md)]

Mint minden vegyes költségnél, a szállítás által generált költséghez is hozzá kell társítani a költségkódot. Ellenkező esetben nem kerülnek a rendelésbe vegyes költségként. A **Költségek kódja** határozza meg, hogyan történik a költség elszámolása annál a rendelésnél és rendelési sornál, amelyhez hozzá lett adva.

Menjen a **Szállításkezelés > Beállítás > Minősítés > Vegyes költségek** lehetőségre, és határozza meg a minősítési feltételeket, amelyek meghatározzák, hogy mikor alkalmaznak egy adott **Költségkódot** a költségnél.

Legalább egy beállítást ki kell választania minden olyan releváns **Költségmodul** beállításhoz (*Ügyfél* és *Szállító*), amelyben a **Vegyes költség típusa** *Egyik sem* értékre van állítva. Ha nincs megadva, a vegyes költséget *nem* adja hozzá a program a rendeléshez.

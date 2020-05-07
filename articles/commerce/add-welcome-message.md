---
title: Üdvözlő üzenet hozzáadása
description: Ez a témakör azt mutatja be, hogyan lehet hozzáadni üdvözlő üzenetet a Microsoft Dynamics 365 Commerce-webhelyéhez.
author: psimolin
manager: annbe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d2a125b4e71016ad620f128af2e3c9f29aa04f4c
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269613"
---
# <a name="add-a-welcome-message"></a>Üdvözlő üzenet hozzáadása


[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet hozzáadni üdvözlő üzenetet a Microsoft Dynamics 365 Commerce-webhelyéhez.

## <a name="overview"></a>Áttekintés

Az e-kereskedelmi webhely üdvözlő üzenete tájékoztatja a látogatókat a folyamatban lévő akciókról, a webhely frissítéseiről, illetve az idényjellegű gyűjtemények elérhetőségéről. Az üdvözlő üzenetet a figyelmeztetési modul segítségével lehet beállítani.

A figyelmeztetési modult hozzá kell adni a fejléctöredék **Hiba/Tájékoztató üzenetek** helyéhez. A figyelmeztetési modul segítségével megadhatja a megjelenített szöveget, a szöveg színét és az igazítását. Azt is megadhatja, hogy a webhely látogatói figyelmen kívül tudják-e hagyni az üzenetet.

Amikor egy üdvözlő üzenetet egy megosztott fejléctöredékhez adnak hozzá, ez minden olyan oldalon megjelenik, amely azt a sablont használja, amelyen a megosztott fejléctöredék szerepel.

Ha új üdvözlő üzenetet szeretne hozzáadni a webhelyhez, hajtsa végre az alábbi lépéseket.

1. Nyissa meg a webhelyét a Commerce webhelykészítőben.
1. Válassza ki a **Töredékek** pontot.
1. Válassza ki azt a fejléctöredéket, amelyhez hozzá szeretné adni az üzenetet.
1. Az oldalstruktúra-fában bontsa ki a **Hibaüzenetek/Tájékoztató üzenetek** elemet.
1. Válassza ki a figyelmeztetési modult, majd kattintson az **OK** gombra. Ha a figyelmeztető modul még nem létezik, akkor először válassza a három pont gombot (**…**) a **Hibaüzenetek/Tájékoztató üzenetek** elemet, majd a **Modul hozzáadása** lehetőséget.
1. Válassza ki a jobb oldali ablaktáblában az **Adatok** lap **Adatforrás hozzáadása** elemét, majd a **Tartalom** lehetőséget.
1. A **Beviteli szöveg** mezőbe írja be az üdvözlő üzenet szövegét.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a fejléctöredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez. 

A kiválasztott fejléctöredéket használó összes webhelyoldal tetején megjelenik az üdvözlő üzenet.

## <a name="additional-resources"></a>További erőforrások

[Embléma hozzáadása](add-logo.md)

[Webhely témájának kiválasztása](select-site-theme.md)

[A CSS felülíró fájljainak használata](css-override-files.md)

[Kedvencek ikon hozzáadása](add-favicon.md)

[Szerzői jogi értesítés hozzáadása](add-copyright-notice.md)

[Nyelvek hozzáadása a webhelyhez](add-languages-to-site.md)

[Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához](add-telemetry.md)


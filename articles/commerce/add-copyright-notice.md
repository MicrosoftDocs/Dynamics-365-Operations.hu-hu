---
title: Szerzői jogi értesítés hozzáadása
description: Ez a témakör azt mutatja be, hogyan lehet az e-kereskedelmi webhelyhez szerzői jogi nyilatkozatot hozzáadni.
author: psimolin
manager: AnnBe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 2ea04854636fdd0c2b3223bb19d5f06a19836151
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206367"
---
# <a name="add-a-copyright-notice"></a>Szerzői jogi értesítés hozzáadása

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet az e-kereskedelmi webhelyhez szerzői jogi nyilatkozatot hozzáadni.

## <a name="prerequisites"></a>Előfeltételek

Ahhoz, hogy szerzői jogi nyilatkozatot adhasson a webhelyhez, a következő elemeket kell megadnia:

- Közös lábléctöredéket tartalmazó sablon.
- Az adott sablont használó oldal.

## <a name="add-a-copyright-notice"></a>Szerzői jogi értesítés hozzáadása

A következő lépésekkel lehet hozzáadni egy szerzői jogi nyilatkozatot az összes olyan oldal aljához, amely egy adott sablont használ.

1. Lépjen a **Töredékek** pontra, majd válassza az **Új** lehetőséget.
1. Az **Új töredék** párbeszédpanelen válassza ki a **Lábléc** modult, és nevezze át a töredéket. Írja be például a **Lábléc-Szerzői jog** értéket.
1. Válassza ki az **OK** lehetőséget.
1. A navigációs panelen válassza ki az válassza ki a **Lábléc** melletti három pontot (**…**) majd válassza a **Modul hozzáadása** elemet.
1. A párbeszédpanelen válassza ki a **Lábléc-kategória** elemet, majd kattintson az **OK** gombra.
1. A navigációs panelen válassza ki az válassza ki a **Lábléc-kategória** melletti három pontot, majd válassza a **Modul hozzáadása** elemet.
1. A párbeszédpanelen válassza ki a **Szövegblokk** elemet, majd kattintson az **OK** gombra.
1. A navigációs ablakban válassza ki a **Szövegblokk** elemet.
1. A jobb oldali Tulajdonságok ablaktáblában, a **Bekezdés** mezőbe vegye fel a szerzői joggal kapcsolatos üzenetet. Írja be például a következőt: **(C) Fabrikam 2019**.
1. Válassza a **Mentés** parancsot, majd a **Szerkesztés befejezése** elemet végül a **Közzététel** lehetőséget.
1. Nyissa meg a **Sablonokat** elemet, válasszon ki egy sablont, majd válassza a **Szerkesztés** parancsot.
1. Az **Oldalstruktúra** alatt bontsa ki a **Szövegtörzs** elemet, majd az **Alapértelmezett oldal** lehetőséget.
1. Válassza ki a **Lábléchely** hely melletti három pont gombot, majd válassza a **Töredék hozzáadása** elemet.
1. Válassza ki a korábban létrehozott töredéket, majd válassza a **Kiválasztás** parancsot.
1. Válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

A szerzői jogi nyilatkozatot tartalmazó lábléc automatikusan megjelenik a kijelölt sablont használó oldalak alján.

## <a name="additional-resources"></a>További erőforrások

[Embléma hozzáadása](add-logo.md)

[Webhely témájának kiválasztása](select-site-theme.md)

[A CSS felülíró fájljainak használata](css-override-files.md)

[Kedvencek ikon hozzáadása](add-favicon.md)

[Üdvözlő üzenet hozzáadása](add-welcome-message.md)

[Nyelvek hozzáadása a webhelyhez](add-languages-to-site.md)

[Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
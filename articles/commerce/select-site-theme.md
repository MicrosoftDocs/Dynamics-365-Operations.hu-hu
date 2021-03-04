---
title: Webhely témájának kiválasztása
description: Ez a témakör azt mutatja be, hogyan lehet egy webhely témáját beállítani vagy módosítani a Microsoft Dynamics 365 Commerce megoldásban.
author: bicyclingfool
manager: annbe
ms.date: 09/15/2020
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
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c54a3e9471fdeb56f27fe7c567c7cd7f0b7fd218
ms.sourcegitcommit: 2ef23dcd4e42362186b9951e675010d97d55c6bd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4556429"
---
# <a name="select-a-site-theme"></a>Webhely témájának kiválasztása

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet egy webhely témáját beállítani vagy módosítani a Microsoft Dynamics 365 Commerce megoldásban.

## <a name="overview"></a>Áttekintés

A webhely elrendezését és stílusát (például a betűtípusokat, a méreteket és a színeket) a kiválasztott téma határozza meg, amely a webhelyre alkalmazva van. A témát a vállalat fejlesztője hozza létre és telepíti. A témák áttekintését a [Témahasználat áttekintése](e-commerce-extensibility/theming.md)című témakörben tekintheti meg. További információ a témák létrehozásáról és telepítéséről: [Új téma létrehozása](e-commerce-extensibility/create-theme.md).

Alapértelmezés szerint,m amikor először létrehoz egy webhelyet, az a **Gyár** elnevezésű témát használja. Ez az alapértelmezett téma a Commerce modulkönyvtár részeként érhető el. Miután telepítette további témákat a webhelyhez, konfigurálhatja úgy a webhelyet, hogy valamelyiket használja ehelyett.

## <a name="select-the-site-theme"></a>A webhely témájának kiválasztása

Ha ki szeretné választani a webhelyre alkalmazott témát, hajtsa végre az alábbi lépéseket.

1. A webhelyszerkesztő környezetben menjen a weboldalához.
1. Lépjen a **Webhely kezelése** \> **Bővíthetőség** lehetőségre.
1. A **Téma** területen válasszon ki egy témát a legördülő menüből.
1. Ha a kiválasztott témát a webhelyre szeretné alkalmazni , válassza a **Mentés és közzététel** parancsot.

> [!NOTE]
> A kiválasztott témát a program közzéteszi a webhelyen, mihelyt a **Mentés és közzététel** lehetőséget választja a **Bővíthetőség** oldalon. Ha azt szeretné megtekintené egy téma előnézetét a webhelyen, anélkül, hogy alkalmazná azt akkor használhatja a fejlesztői vagy a védőfal-környezetet.

## <a name="additional-resources"></a>További erőforrások

[Embléma hozzáadása](add-logo.md)

[A CSS felülíró fájljainak használata](css-override-files.md)

[Kedvencek ikon hozzáadása](add-favicon.md)

[Üdvözlő üzenet hozzáadása](add-welcome-message.md)

[Szerzői jogi értesítés hozzáadása](add-copyright-notice.md)

[Nyelvek hozzáadása a webhelyhez](add-languages-to-site.md)

[Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához](add-telemetry.md)

[Témahasználat áttekintése](e-commerce-extensibility/theming.md)

[Új téma létrehozása](e-commerce-extensibility/create-theme.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
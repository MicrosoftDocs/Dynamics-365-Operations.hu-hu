---
title: Webhely témájának kiválasztása
description: Ez a témakör azt ismerteti, hogyan lehet beállítani vagy módosítani a webhely témacsoportját a témakörben Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b038dc996c571d54dce3f2aec679f7af8af85074
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900386"
---
# <a name="select-a-site-theme"></a>Webhely témájának kiválasztása

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet beállítani vagy módosítani a webhely témacsoportját a témakörben Microsoft Dynamics 365 Commerce.

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

[Szerzői jogi értesítés hozzáadása](add-copyright-notice.md)

[Nyelvek hozzáadása a webhelyhez](add-languages-to-site.md)

[Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához](add-telemetry.md)

[Témahasználat áttekintése](e-commerce-extensibility/theming.md)

[Új téma létrehozása](e-commerce-extensibility/create-theme.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]

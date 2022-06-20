---
title: Embléma hozzáadása
description: Ez a témakör azt ismerteti, hogyan lehet emblémát adni a webhelyhez Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 624cd6f7000f5038b9996eb94caf79719d07f99f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871780"
---
# <a name="add-a-logo"></a>Embléma hozzáadása

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet emblémát adni a webhelyhez Microsoft Dynamics 365 Commerce.

Amikor felépíti a webhelyét, valószínűleg az első dolgai egyike lesz hozzáadni a vállalata vagy márkája logóját a webhely fejlécéhez. A Dynamics 365 Commerce online modulkönyvtár tartalmaz egy modult ennek a megkönnyítéséhez.

Hozzáadhat egy logót közvetlenül egy sablonhoz, elrendezéshez vagy oldalhoz. Így egyszerűen módosíthatja az adott oldalakon vagy oldalcsoportokon megjelenő logót. Ez a cikk azonban a leggyakrabban előforduló esetet tartalmazza, amikor az emblémát egy fejlécrészlethez kell hozzáadni, amely a webhely összes lapokon újra felhasználható.

## <a name="prerequisites"></a>Előfeltételek

Mielőtt hozzáadná a logót a webhely összes oldalához, végre kell hajtania ezeket a feladatokat.

1. Töltse fel az emblémát a médiatárba.
1. Fejléctöredék létrehozása A töredékek létrehozásával és használatával kapcsolatos további tudnivalókért tanulmányozza a [Töredékek használata](work-with-fragments.md) című témakört.
1. Adja meg a fejléctöredéket abban a sablonban, amelyet webhelyének oldalai használnak az elrendezéshez és a modulbeállításokhoz. A sablonokkal kapcsolatos további információkért lásd: [Sablonok használata](work-with-templates.md).

## <a name="add-a-logo-to-a-header-fragment"></a>Logó hozzáadása a fejléctöredékhez

A logó hozzáadásához a webhelye fejléctöredékéhez, kövesse az alábbi lépéseket.

1. A bal oldali navigációs ablakban válassza ki a **Töredékek** lehetőséget.
1. Válassza ki a létrehozott fejléctöredéket, majd válassza a **Szerkesztés** parancsot.
1. Nyissa meg a fejléc modult.
1. A fejléc modul tulajdonságpanelján adjon meg egy képet és egy hivatkozást az emblémát. 
1. Mentse az oldaltöredéket, fejezze be a szerkesztését, majd tegye közzé.

A frissített fejléctöredék közzététele után a webhely összes olyan oldala, amely a fejléctöredéket tartalmazó sablont használja, megjeleníti a logót.

## <a name="additional-resources"></a>További erőforrások

[Webhely témájának kiválasztása](select-site-theme.md)

[A CSS felülíró fájljainak használata](css-override-files.md)

[Kedvencek ikon hozzáadása](add-favicon.md)

[Szerzői jogi értesítés hozzáadása](add-copyright-notice.md)

[Nyelvek hozzáadása a webhelyhez](add-languages-to-site.md)

[Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]

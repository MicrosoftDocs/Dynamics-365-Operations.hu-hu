---
title: Embléma hozzáadása
description: Ez a témakör azt mutatja be, hogyan adhat hozzá logót a webhelyéhez a Microsoft Dynamics 365 Commerce alkalmazásban.
author: bicyclingfool
manager: AnnBe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: 073c3d6f8d5ee88d51efb41f6b9c1a204b82fa12
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980307"
---
# <a name="add-a-logo"></a>Embléma hozzáadása

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan adhat hozzá logót a webhelyéhez a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

Amikor felépíti a webhelyét, valószínűleg az első dolgai egyike lesz hozzáadni a vállalata vagy márkája logóját a webhely fejlécéhez. A Dynamics 365 Commerce online modulkönyvtár tartalmaz egy modult ennek a megkönnyítéséhez.

Hozzáadhat egy logót közvetlenül egy sablonhoz, elrendezéshez vagy oldalhoz. Így egyszerűen módosíthatja az adott oldalakon vagy oldalcsoportokon megjelenő logót. Ez a témakör azonban a leggyakrabban előforduló forgatókönyvet tartalmazza, ahol a logót egy olyan fejléctöredékhez adja hozzá, amely a webhely összes oldalán felhasználható.

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

[Üdvözlő üzenet hozzáadása](add-welcome-message.md)

[Szerzői jogi értesítés hozzáadása](add-copyright-notice.md)

[Nyelvek hozzáadása a webhelyhez](add-languages-to-site.md)

[Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
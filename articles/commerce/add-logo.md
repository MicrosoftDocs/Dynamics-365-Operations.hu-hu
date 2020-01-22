---
title: Embléma hozzáadása
description: Ez a témakör azt mutatja be, hogyan adhat hozzá logót a webhelyéhez a Microsoft Dynamics 365 Commerce alkalmazásban.
author: bicyclingfool
manager: AnnBe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 23bac9aae6beb59912bbc9e1f2c6958c007550b0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914621"
---
# <a name="add-a-logo"></a>Embléma hozzáadása

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan adhat hozzá logót a webhelyéhez a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

Amikor felépíti a webhelyét, valószínűleg az első dolgai egyike lesz hozzáadni a vállalata vagy márkája logóját a webhely fejlécéhez. A Dynamics 365 Commerce online kezdőszett tartalmaz egy modult ennek a megkönnyítéséhez.

Hozzáadhat egy logót közvetlenül egy sablonhoz, elrendezéshez vagy oldalhoz. Így egyszerűen módosíthatja az adott oldalakon vagy oldalcsoportokon megjelenő logót. Ez a témakör azonban a leggyakrabban előforduló forgatókönyvet tartalmazza, ahol a logót egy olyan fejléctöredékhez adja hozzá, amely a webhely összes oldalán felhasználható.

## <a name="prerequisites"></a>Előfeltételek

Mielőtt hozzáadná a logót a webhely összes oldalához, végre kell hajtania ezeket a feladatokat.

1. Töltse fel a logóját a digitáliseszköz-kezelőbe, amelyet az **Eszközök** oldalról érhet el.
1. Fejléctöredék létrehozása A töredékek létrehozásával és használatával kapcsolatos további tudnivalókért tanulmányozza a [Töredékek használata](work-with-fragments.md) című témakört.
1. Adja meg a fejléctöredéket abban a sablonban, amelyet webhelyének oldalai használnak az elrendezéshez és a modulbeállításokhoz. A sablonokkal kapcsolatos további információkért lásd: [Sablonok használata](work-with-templates.md).

## <a name="add-a-logo-to-a-header-fragment"></a>Logó hozzáadása a fejléctöredékhez

A logó hozzáadásához a webhelye fejléctöredékéhez, kövesse az alábbi lépéseket.

1. A bal oldali navigációs panelen jelölje ki a **Töredékek** lehetőséget, majd válassza ki a létrehozott fejléctöredéket.
2. Válassza a **Kivétel** lehetőséget.
3. Bontsa ki a **Fejléc** helyet és a **Logó** helyet.
4. Válassza ki a **Logó** helyhez tartozó három pont gombot (**...**), majd válassza a **Modul hozzáadása** elemet.
5. Válassza ki a logó modult.
6. A jobb oldali tulajdonságok panelen konfigurálja a logó modult, hogy az Ön logóját jelenítse meg.
7. Mentse a fejléctöredéket, adja be és tegye közzé.

A frissített fejléctöredék közzététele után a webhely összes olyan oldala, amely a fejléctöredéket tartalmazó sablont használja, megjeleníti a logót.

## <a name="additional-resources"></a>További erőforrások

[Webhely témájának kiválasztása](select-site-theme.md)

[A CSS felülíró fájljainak használata](css-override-files.md)

[Kedvencek ikon hozzáadása](add-favicon.md)

[Üdvözlő üzenet hozzáadása](add-welcome-message.md)

[Szerzői jogi értesítés hozzáadása](add-copyright-notice.md)

[Nyelvek hozzáadása a webhelyhez](add-languages-to-site.md)

[Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához](add-telemetry.md)


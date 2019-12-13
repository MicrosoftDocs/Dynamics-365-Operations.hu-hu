---
title: Kedvencek ikon hozzáadása
description: Ez a témakör azt mutatja be, hogyan lehet egy kedvencek ikont hozzáadni a webhelyhez.
author: bicyclingfool
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: 58cb6c592351a96876532ef53d5d477ff93fafa1
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2019
ms.locfileid: "2696991"
---
# <a name="add-a-favicon"></a>Kedvencek ikon hozzáadása

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet egy kedvencek ikont hozzáadni a webhelyhez.

## <a name="overview"></a>Áttekintés

A kedvencek ikon egy kis grafikai fájl, amely a webböngésző lapján, a címsorban, a böngészési előzményekben, a könyvjelzők vagy a Kedvencek között jelenik meg sok más hely mellett. Javasoljuk, hogy adjon kedvencek ikont webhelyéhez, mert ezzel a saját márkáját képviseli és megerősíti, valamint segít megkülönböztetni a webhelyet a vevők által látogatott egyéb helyektől.

Bár több, különböző méretű és fájltípusú kedvencek ikont is webhelxéhez adhat, ebben a témakörben az egyetlen kedvencek ikon hozzáadását mutatjuk be. Ugyanakkor ugyanaz a folyamat és a hely több kedvencek ikon hozzáadására is használható.

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a>Kedvencek ikon feltöltése a webhely eszközgyűjteménybe

Kedvencek ikon a webhely eszközgyűjteményébe való feltöltéséhez kövesse az alábbi lépéseket.

1. Ugorjon az **Eszközök \> Feltöltés \> Eszközök feltöltése** pontra.
1. Keresse meg és válassza ki a kedvencek ikont a helyi fájlrendszerben.
1. Adja meg a címet, majd kattintson az **OK** gombra. 
1. A jobb oldali Tulajdonságok ablaktáblán másolja a kedvencek ikon nyilvános URL-jét.

> [!NOTE]
> Ha nem jelöli be az **Eszközök közzététele a feltöltés után** beállítás jelölőnégyzetét, akkor vissza kell térnie az **eszközök** oldalra, és manuálisan kell közzétennie a kedvencek ikont később.

## <a name="create-the-html-for-the-favicon"></a>A HTML létrehozása a kedvencek ikon számára

A kedvencek ikon HTML-kódjának létrehozásához használja a következő HTML-kódrészletet. A **href** attribútum esetében cserélje le a **„Nyilvános\_URL\_a\_kedvencek\_ikonhoz”** értékét a korábban kimásolt nyilvános URL-címre.

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="add-the-html-for-the-favicon-to-the-head-element-of-your-pages"></a>Adja hozzá a kedvencek ikon HTML-kódját az oldalak \<fejléc\> eleméhez

Egy kedvencek ikon a webhelyhez történő hozzáadásához használja ugyanazt az eljárást, amellyel bármilyen típusú HTML-kódot vagy parancsfájlt hozzáadhat a webhelyoldalak **\<fejléc\>** eleméhez.

## <a name="additional-resources"></a>További erőforrások

[Embléma hozzáadása](add-logo.md)

[Webhely témájának kiválasztása](select-site-theme.md)

[Üdvözlő üzenet hozzáadása](add-welcome-message.md)

[Szerzői jogi értesítés hozzáadása](add-copyright-notice.md)

[Nyelvek hozzáadása a webhelyhez](add-languages-to-site.md)

[Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához](add-telemetry.md)


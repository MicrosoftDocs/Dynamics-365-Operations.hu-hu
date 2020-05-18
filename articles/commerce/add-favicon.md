---
title: Kedvencek ikon hozzáadása
description: Ez a témakör azt mutatja be, hogyan lehet egy kedvencek ikont hozzáadni a webhelyhez.
author: bicyclingfool
manager: annbe
ms.date: 04/27/2020
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
ms.openlocfilehash: 2d95e8b799c3b89418657342868e0ec7e94a86f9
ms.sourcegitcommit: ce79fb570e299a26a644e29da7ceb5a57a1374e6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/28/2020
ms.locfileid: "3295080"
---
# <a name="add-a-favicon"></a>Kedvencek ikon hozzáadása

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet egy kedvencek ikont hozzáadni a webhelyhez.

## <a name="overview"></a>Áttekintés

A kedvencek ikon egy kis grafikai fájl, amely a webböngésző lapján, a címsorban, a böngészési előzményekben, a könyvjelzők vagy a Kedvencek között jelenik meg sok más hely mellett. Javasoljuk, hogy adjon kedvencek ikont webhelyéhez, mert ezzel a saját márkáját képviseli és megerősíti, valamint segít megkülönböztetni a webhelyet a vevők által látogatott egyéb helyektől.

Bár több, különböző méretű és fájltípusú kedvencek ikont is webhelxéhez adhat, ebben a témakörben az egyetlen kedvencek ikon hozzáadását mutatjuk be. Ugyanakkor ugyanaz a folyamat és a hely több kedvencek ikon hozzáadására is használható.

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a>Kedvencek ikon feltöltése a webhely eszközgyűjteménybe

Kedvencek ikon a webhely eszközgyűjteményébe való feltöltéséhez kövesse az alábbi lépéseket.

1. A bal oldali navigációs ablakban válassza ki a **Médiatár** lehetőséget.
1. A parancssávon válassza a **Feltöltés \> Médiaelemek feltöltése**.
1. A Fájlkezelő ablakában tallózzon a feltölteni kívánt kedvencek ikon képfájljához jelölje ki, majd válassza a **Megnyitás** lehetőséget.
1. A **médiaelem feltöltése** párbeszédpanelen írja be a szükséges címet és a helyettesítő szöveget.
1. Ha azonnal közzétenné a képet a feltöltés után, jelölje be a **Médiatartalom közzététele a feltöltés után** jelölőnégyzetet.

    > [!NOTE]
    > Ha nem jelöli be az **Médiaelemek közzététele a feltöltés után** jelölőnégyzetét, akkor vissza kell térnie az **Médiaelemek** oldalra, és manuálisan kell közzé tennie a kedvencek ikont később.

1. Válassza ki az **OK** lehetőséget.
1. A jobb oldali Tulajdonságok ablaktáblán másolja a kedvencek ikon nyilvános URL-jét. Ezt az URL-címet fogja később használni.

## <a name="create-the-html-for-your-favicon"></a>A HTML létrehozása a kedvencek ikonja számára

A kedvencek ikon HTML-kódjának létrehozásához használja a következő HTML-karakterláncot. A **href** attribútum esetében cserélje le a **Nyilvános\_URL\_a\_kedvencek\_ikonhoz** értékét a korábban kimásolt nyilvános URL-címre.

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="create-a-page-fragment-that-contains-a-metatag-for-your-favicon"></a>Hozzon létre egy oldaltöredékét, amely metataget tartalmaz a kedvenc ikonjához

Az oldaltöredék létrehozásához, amely metacímkét tartalmaz a kedvenc ikonjához kövesse az alábbi lépéseket.

1. Lépjen az **Oldaltöredékek** pontra, és válassza az **Új** lehetőséget.
1. Az **Új oldaltöredék** párbeszédpanelen válassza ki **Metacímkék** annak a modulnak, amelyen az oldaltöredék alapul.
1. Írja be az oldaltöredék nevét, majd kattintson az **OK** gombra.
1. A töredék hierarchiafájában válassza ki az **Alapértelmezett metacímkék** gyermekét.
1. A jobb oldali panelen a **Metacímkék** területen válassza a **Hozzáadás** lehetőséget, majd adja meg a kedvencek ikonhoz korábban létrehozott HTML-karakterláncot. 
1. Válassza a **Szerkesztés befejezése** parancsot, majd a **Közzététel** elemet az oldaltöredék közzétételhez.

## <a name="add-the-metatag-page-fragment-to-the-html-head-section-of-your-pages"></a>A metacímke oldaltöredékének hozzáadása az oldalak HTML-fejléc szakaszához

A metacímke oldaltöredékének hozzáadásához az oldalak HTML **fejléc** szakaszához kövesse az alábbi lépéseket.

1. Nyissa mega **Sablonok** pontot, majd nyissa meg azon oldalakhoz tartozó sablont, amelyhez hozzá szeretné adni a kedvencek ikont, majd válassza a **Szerkesztés** lehetőséget.
1. A sablonhierarchia-fában válassza ki a **HTML-fejléc** tárolójának jobb oldalán található három pont (**…**) gombot, majd válassza az **Oldal töredék hozzáadása** lehetőséget.
1. Az **Oldaltöredék kiválasztása** párbeszédpanelen válassza ki a metacímke oldaltöredékét, amelyet korábban hozott létre majd kattintson az **OK** gombra.
1. Válassza a **Szerkesztés befejezése** parancsot, majd a **Közzététel** elemet a sablon közzétételhez.

> [!NOTE]
> Ha a webhely egynél több sablont használ, akkor mindegyikhez hozzá kell adnia a metacímkék oldaltöredékét.

Ha megtekinti azon lapok előnézetét, amelyek azon a sablonon alapulnak, amelyhez hozzáadta a metacímkék oldaltöredékét, immár látható a kedvencek ikon a böngészőlapon.

## <a name="additional-resources"></a>További erőforrások

[Embléma hozzáadása](add-logo.md)

[Webhely témájának kiválasztása](select-site-theme.md)

[A CSS felülíró fájljainak használata](css-override-files.md)

[Üdvözlő üzenet hozzáadása](add-welcome-message.md)

[Szerzői jogi értesítés hozzáadása](add-copyright-notice.md)

[Nyelvek hozzáadása a webhelyhez](add-languages-to-site.md)

[Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához](add-telemetry.md)


---
title: Weblapikon hozzáadása
description: Ez a cikk bemutatja, hogyan lehet fa egy webhelyhez adva.
author: bicyclingfool
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 41d6d8f823c7364f9206fd0f7588e35b6f0a018a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270437"
---
# <a name="add-a-favicon"></a>Weblapikon hozzáadása

[!include [banner](includes/banner.md)]

Ez a cikk bemutatja, hogyan lehet fa egy webhelyhez adva.

A kedvencek ikon egy kis grafikai fájl, amely a webböngésző lapján, a címsorban, a böngészési előzményekben, a könyvjelzők vagy a Kedvencek között jelenik meg sok más hely mellett. Javasoljuk, hogy adjon kedvencek ikont webhelyéhez, mert ezzel a saját márkáját képviseli és megerősíti, valamint segít megkülönböztetni a webhelyet a vevők által látogatott egyéb helyektől.

Bár a webhelyhez több különböző méretű és fájltípusú favovoon is hozzáadhat, ez a cikk bemutatja, hogyan lehet egyetlen faterjesztést hozzáadni. Ugyanakkor ugyanaz a folyamat és a hely több kedvencek ikon hozzáadására is használható.

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

## <a name="create-a-fragment-that-contains-a-metatag-for-your-favicon"></a>Hozzon létre egy töredékét, amely metataget tartalmaz a kedvenc ikonjához

A töredék létrehozásához, amely metacímkét tartalmaz a kedvenc ikonjához kövesse az alábbi lépéseket.

1. Lépjen a **Töredékek** pontra, és válassza az **Új** lehetőséget.
1. Az **Új töredék** párbeszédpanelen válassza ki **Metacímkék** lehetőséget azon modulként, melyen a töredék alapszik.
1. Írja be a töredék nevét, majd kattintson az **OK** gombra.
1. A töredék hierarchiafájában válassza ki az **Alapértelmezett metacímkék** gyermekét.
1. A jobb oldali panelen a **Metacímkék** területen válassza a **Hozzáadás** lehetőséget, majd adja meg a kedvencek ikonhoz korábban létrehozott HTML-karakterláncot. 
1. Válassza a **Szerkesztés befejezése** parancsot, majd a **Közzététel** elemet a töredék közzétételhez.

## <a name="add-the-metatag-fragment-to-the-html-head-section-of-your-pages"></a>A metacímke töredékének hozzáadása az oldalak HTML-fejléc szakaszához

A metacímke töredékének hozzáadásához az oldalak HTML **fejléc** szakaszához kövesse az alábbi lépéseket.

1. Nyissa mega **Sablonok** pontot, majd nyissa meg azon oldalakhoz tartozó sablont, amelyhez hozzá szeretné adni a kedvencek ikont, majd válassza a **Szerkesztés** lehetőséget.
1. A sablonhierarchia-fában válassza ki a **HTML-fejléc** tárolójának jobb oldalán található három pont (**…**) gombot, majd válassza az **Töredék hozzáadása** lehetőséget.
1. A **Töredék kiválasztása** párbeszédpanelen válassza ki a metacímke töredékét, melyet korábban hozott létre majd kattintson az **OK** gombra.
1. Válassza a **Szerkesztés befejezése** parancsot, majd a **Közzététel** elemet a sablon közzétételhez.

> [!NOTE]
> Ha a webhely egynél több sablont használ, akkor mindegyikhez hozzá kell adnia a metacímkék töredékét.

Ha megtekinti azon lapok előnézetét, amelyek azon a sablonon alapulnak, amelyhez hozzáadta a metacímkék töredékét, immár látható a kedvencek ikon a böngészőlapon.

## <a name="additional-resources"></a>További erőforrások

[Embléma hozzáadása](add-logo.md)

[Webhely témájának kiválasztása](select-site-theme.md)

[A CSS felülíró fájljainak használata](css-override-files.md)

[Szerzői jogi értesítés hozzáadása](add-copyright-notice.md)

[Nyelvek hozzáadása a webhelyhez](add-languages-to-site.md)

[Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Oldaltartalom hozzáférhetőségének ellenőrzése
description: Ez a témakör azt írja le, hogyan lehet ellenőrizni, hogy a lap tartalma elérhető-e a következőben:Microsoft Dynamics 365 Commerce
author: josaw1
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-12-19
ms.dyn365.ops.version: Release 10.0.8
ms.search.industry: retail
ms.search.form: ''
ms.openlocfilehash: 686ec37f24cf68902c4dd918c0ca8aea7612e1a9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291973"
---
# <a name="verify-page-content-accessibility"></a>Oldaltartalom hozzáférhetőségének ellenőrzése

[!include [banner](includes/banner.md)]

Ez a témakör azt írja le, hogyan lehet ellenőrizni, hogy a lap tartalma elérhető-e a következőben:Microsoft Dynamics 365 Commerce

Amikor befejezte egy oldal módosítását, győződjön meg arról, hogy a tartalom mindenki számára elérhető a weben. A Commerce szerkesztőeszközök könnyen ellenőrizhető az oldal tartalmának hozzáférhetősége az integrált [Microsoft hozzáférhetőségi információk](https://accessibilityinsights.io/) szolgáltatás használatával. Ez a szolgáltatás ellenőrzi az oldal tartalmát a legfrissebb [World Wide Web CONSORTIUM (W3C) akadálymentesítési](https://www.w3.org/standards/webdesign/accessibility) irányelvei alapján.

A [Microsoft hozzáférhetőségi információk](https://accessibilityinsights.io/) integrálásának használatához be kell azt kapcsolni a bérlő vagy a webhely szintjén.

## <a name="turn-on-microsoft-accessibility-insights-for-all-the-sites-in-your-tenant"></a>A Microsoft hozzáférhetőségi információk bekapcsolása a bérlő összes webhelyén

A [Microsoft hozzáférhetőségi információk](https://accessibilityinsights.io/) integráció bekapcsolásához a bérlő összes Commerce-webhelyén, kövesse az alábbi lépéseket.

> [!NOTE]
> A bérlői beállítások eléréséhez be kell jelentkeznie a Commerce alkalmazásba rendszergazdaként.

1. Rendszergazdaként jelentkezzen be a Commerce rendszerbe.
1. A bal oldali navigációs ablaktáblán válassza ki a **Bérlői beállítások** (a fogaskerék szimbólum mellett) lehetőséget a kibontáshoz.
1. A **Bérlői beállítások** részben válassza a **Funkciók** lehetőséget.
1. Állítsa a **Hozzáférhetőség ellenőrzése** beállítást **Be** értékre.

## <a name="turn-on-microsoft-accessibility-insights-for-a-single-site"></a>A Microsoft hozzáférhetőségi információk bekapcsolása egyetlen webhelyhez

A [Microsoft hozzáférhetőségi információk](https://accessibilityinsights.io/) integráció bekapcsolásához a egyetlen Commerce-webhelyen, kövesse az alábbi lépéseket.

1. A **Webhelyek** alatt válassza a **Fabrikam** (vagy a webhelye neve) lehetőséget.
1. A bal oldali navigációs panelen válassza a **Webhelybeállítások** elemet a kibontáshoz.
1. A **Webhelybeállítások** részben válassza a **Funkciók** lehetőséget.
1. Állítsa a **Hozzáférhetőség ellenőrzése** beállítást **Be** értékre.

## <a name="verify-the-accessibility-of-the-content-on-the-home-page"></a>A kezdőlapon lévő tartalom hozzáférhetőségének ellenőrzése

Ha az integrált [Microsoft hozzáférhetőségi információk](https://accessibilityinsights.io/) szolgáltatást szeretné használni a Commerce kezdőlapja tartalmának ellenőrzéséhez, kövesse az alábbi lépéseket.

1. A **Webhelyek** alatt válassza a **Fabrikam** (vagy a webhelye neve) lehetőséget.
1. A bal oldali navigációs ablakban válassza ki a **Oldalak** lehetőséget.
1. Keresse meg és válassza ki a kezdőlapot a megnyitáshoz a lapszerkesztőben.
1. Válassza a parancssáv **Hozzáférhetőség ellenőrzése** elemét. Megjelenik a **Hozzáférhetőség ellenőrzése** oldal.
1. A vizsgálat befejezését követően tekintse át a jelentés tartalmát.
1. Ha valamelyik ellenőrzés sikertelen, jelölje ki az egyes sikertelen elemeket a kibontáshoz, így további részleteket is meg tud tekinteni.
1. Ha az áttekintést követően be szeretné zárni a jelentést, görgessen a **Hozzáférhetőség ellenőrzése** oldal aljára, és válassza az **OK** gombot.

## <a name="additional-resources"></a>További erőforrások

[Meglévő webhelyoldal módosítása](modify-existing-page.md)

[Új webhelyoldal hozzáadása](add-new-page.md)

[Oldalelrendezések kiválasztása](select-page-layouts.md)

[SEO-metaadatok kezelése](manage-seo-metadata.md)

[Oldal mentése, megtekintése és közzététele](save-preview-publish-page.md)

[A termékoldal bővítése](enrich-product-page.md)

[Kategória céloldalának bővítése](enrich-category-page.md)

[Dinamikus e-kereskedelmi oldalak létrehozása URL-paraméterek alapján](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

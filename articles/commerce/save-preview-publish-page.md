---
title: Oldal mentése, megtekintése és közzététele
description: Ez a témakör azt ismerteti, hogyan lehet egy oldalt menteni, előnézetben menteni és közzétenni Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: bf9cc4eb916976ed0c87f27cf8df7c0d52d07ef0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280214"
---
# <a name="save-preview-and-publish-a-page"></a>Oldal mentése, megtekintése és közzététele

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet egy oldalt menteni, előnézetben menteni és közzétenni Microsoft Dynamics 365 Commerce.

## <a name="save-a-page"></a>Egy lap mentése

Lap mentéséhez ki kell vennie azt, és meg kell nyitnia azt a lapszerkesztőben. Egy oldal kivételéhet válassza a **Szerkesztés** parancsot a parancssávon. Miután befejezte egy oldal szerkesztését, azonnal mentse azt, hogy garantálni lehessen azt, hogy a módosítások tárolva legyenek.

A lapok mentésekor a módosítások csak az Ön számára láthatók. A mentési művelet elsősorban a módosítások tárolására szolgál, amíg a lap még nincs készen a beadásra. Amikor befejezte a lap módosítását, ajánlott beadni azt, hogy a módosítások mások számára is láthatóvá váljanak. Ezen a ponton a lapot más olyan felhasználók is kivehetik, akik módosítania szeretnék azt.

## <a name="preview-a-page"></a>Egy lap előnézetének megtekintése

A szerkesztő eszköz kétféle előnézeti funkciót kínál: vizuális oldalkészítő, amely egy „valós megjelenítésű” (WYSIWYG) előnézeti ablak a lap szerkesztőjében, és egy külön előnézeti ablak.

A lapszerkesztő használata közben a központ ablaktáblájában megjelenik a „valós megejelenítésű” (WYSIWYG) előnézet. A program automatikusan frissíti ezt az előnézetet a lap mentésekor. A parancssori **Frissítés** lehetőséget kiválaszva manuálisan is frissítheti ezt. Az előnézet ugyanúgy jeleníti meg a lapot, ahogy a webhely felhasználói látni fogják, de felette láthatók a szerkesztői segédeszközök.

Ha befejezte a lap módosítását, megtekintheti előnézetét, tehát azt, hogy a vásárlók mit fognak látni. A lap előnézetéhez válassza a parancssáv **Előnézet** elemét. Az előnézet egy külön böngészőablakban fog megjelenni. Az előnézeti ablak lapja ugyanúgy jelenik meg, ahogy a webhely felhasználója látni fogja azt. Az ablak átméretezésével meggyőződhet arról, hogy a reszponzív modulok helyesen legyenek megjelenítve minden nézetben.

> [!NOTE]
> A nem közzétett tartalom előnézetéhez hitelesítés és megfelelő engedélyek szükségesek. Ezért ha megosztja az előnézeti URL-címet valakivel, akkor az adott személynek rendelkeznie kell a tartalom eléréséhez szükséges engedélyekkel.

## <a name="publish-a-page"></a>Oldal közzététele

Amikor elkészült a lap, a következő lépés a közzététel, hogy a külső felhasználók megtekinthessék a tartalmat. A lap közzététele előtt be kell küldenie azt a parancssáv **Szerkesztés befejezése** elemének kiválasztásához.

A lapokat akár a lapvizsgálóból és a lapszerkesztőből is közzéteheti vagy megszüntetheti a közzétételt. A lapvizsgáló megjeleníti a lapok listáját, és kötegelt művelteket is lehetővé tesz. A lapszerkesztőben csak azokat a lapokat lehet közzétenni vagy a közzétételt megszüntetni, amelyek meg vannak nyitva.

Ha egy vagy több oldalt szeretne közzétenni a lapvizsgálóból, jelölje ki a lapokat, győződjön meg arról, hogy be vannak küldve, majd válassza a **Közzététel** parancsot. A program közzéteszi a lapokat, és értesítést kap a műveletről a szerkesztőeszközben.

Ha egyetlen lapot szeretne közzétenni a lapszerkesztőből, akkor az eljárás hasonló. Amíg a lap meg van nyitva a lapszerkesztőben, győződjön meg arról, hogy az be van küldve, majd válassza a **Közzététel** elemet a parancssoron. A program közzéteszi a lapot, és értesítést kap a műveletről a szerkesztőeszközben.

Amikor közzétesz egy oldalt, csak az oldal tartalmát teszi közzé a program. Ön és a többi felhasználó csak azután tekintheti meg a lapot, ha ahhoz társítottak egy URL-címet. Az URL-címet külön kell közzé tenni.

> [!IMPORTANT]
> A lap közzététele előtt minden olyan képet vagy töredéket is közzé kell tenni, amelyre a lap hivatkozik.

## <a name="save-preview-and-publish-a-home-page"></a>Kezdőlap mentése, megtekintése és közzététele

Kezdőlap mentéséhez, előnézetéhez és közzétételéhez hajtsa végre az alábbi lépéseket.

1. A **Webhelyek** alatt válassza a **Fabrikam** (vagy a webhelye neve) lehetőséget.
1. A bal oldali navigációs ablakban válassza ki a **Oldalak** lehetőséget.
1. Keresse meg és válassza ki a kezdőlapot a megnyitáshoz a lapszerkesztőben.
1. Válassza ki a **Szerkesztés** opciót.
1. Igény szerint módosítsa a lapot.
1. Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.
1. A **Megjegyzések** mezőbe írja be a végrehajtott változtatásokkal kapcsolatos megjegyzését, majd kattintson az **OK** gombra.
1. A oldal előnézetének megjelenítéséhez válassza az **Előnézet** lehetőséget. Ha befejezte, zárja be az előnézeti lapot, és térjen vissza a szerkesztési eszközhöz.
1. Válassza a **Közzététel** lehetőséget.

## <a name="publish-a-url"></a>URL-cím közzététele

Egy URL-cím közzétételéhez kövesse az alábbi lépéseket.

1. A **Webhelyek** alatt válassza a **Fabrikam** (vagy a webhelye neve) lehetőséget.
1. A bal oldali navigációs ablakban válassza ki az **URL-címek** lehetőséget.
1. Keresse meg és válassza ki a közzétenni kívánt URL-címet.
1. Válassza a parancssáv **Közzététel** elemét.

## <a name="additional-resources"></a>További erőforrások

[Meglévő webhelyoldal módosítása](modify-existing-page.md)

[Új webhelyoldal hozzáadása](add-new-page.md)

[Oldalelrendezések kiválasztása](select-page-layouts.md)

[SEO-metaadatok kezelése](manage-seo-metadata.md)

[A termékoldal bővítése](enrich-product-page.md)

[Kategória céloldalának bővítése](enrich-category-page.md)

[Oldaltartalom hozzáférhetőségének ellenőrzése](verify-accessibility.md)

[Dinamikus e-kereskedelmi oldalak létrehozása URL-paraméterek alapján](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

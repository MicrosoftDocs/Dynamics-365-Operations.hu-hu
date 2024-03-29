---
title: Adatvédelmi irányelv oldalának hozzáadása
description: Ez a témakör azt ismerteti, hogyan lehet adatvédelmi irányelveket felvenni a webhelyre Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: a874272fe5158dd213a69c7ba996e0d28c7ed15a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272071"
---
# <a name="add-a-privacy-policy-page"></a>Adatvédelmi irányelv oldalának hozzáadása

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet adatvédelmi irányelveket felvenni a webhelyre Microsoft Dynamics 365 Commerce.

Az adatvédelmi előírásoknak való megfelelés olyan szervezeti intézkedéseket is tartalmaz, amelyek tájékoztatják a webhely felhasználóit az adatok gyűjtésének és kezelésének módjáról. A felhasználók ezután eldönthetik, hogyan kívánják személyes adataikat kezelni, és megfelelő lépéseket tehetnek.

## <a name="review-the-microsoft-privacy-statement-in-dynamics-365-commerce"></a>A Microsoft adatvédelmi nyilatkozatának áttekintése a Dynamics 365 Commerce alkalmazásban

Ha szeretné áttekinteni a Microsoft adatvédelmi nyilatkozatát, amikor be van jelentkezve a Dynamics 365 Commerce szerkesztőeszközökre, válassza a jobb felső sarokban található **Súgó** (**?**) gombot, majd válassza az **Adatvédelem és cookie-k** lehetőséget. Megnyílik egy új lap, amely hivatkozást tartalmaz a [Microsoft adatvédelmi nyilatkozatra](https://privacy.microsoft.com/privacystatement).

## <a name="build-a-privacy-policy-page-for-your-site"></a>Adatvédelmi irányelv oldal összeállítása a webhelyéhez

A Dynamics 365 Commerce alkalmazásban többféle módon adhat hozzáférést a webhelye felhasználóinak az adatvédelmi irányelveihez. Ez a szakasz bemutatja, hogyan lehet egy adatvédelmi irányelv oldalt létrehozni, majd egy élőlábtöredék segítségével hivatkozni a lapra.

Az alábbi útmutatás bemutatja, hogyan lehet egy Commerce-webhely általános adatvédelmi irányelv oldalát létrehozni. Ön felelős az olyan adatvédelmi irányelv oldal tervezéséért és megvalósításáért, amely a legjobban megfelel vállalata jogi követelményeinek.

Kezdésként a szerkesztőeszközökben keresse meg azt a webhelyet, amelyhez fel kívánja építeni az adatvédelmi irányelv oldalát.

### <a name="create-a-template"></a>Sablon létrehozása

> [!NOTE]
> Ha már létrehoztak olyan sablont, ami használható az adatvédelmi irányelv oldal létrehozásához, ugorjon előre az [Adatvédelmi irányelv oldal összeállítása](#build-a-privacy-policy-page) szakaszra.

Sablon létrehozásához kövesse az alábbi lépéseket.

1. Lépjen a **Sablonok** pontra, majd oldalsablon készítéséhez válassza az **Új** elemet.
1. Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a **promóciós szalagcím sablon** elemet, majd válassza az **OK** gombot.
1. A sablonban adja hozzá a szükséges modulokat a megfelelő oldalhelyekhez. Útmutatásért vigye az egérmutatót a piros felkiáltójelek fölé. (A **HTML-fejléc** tárolóhelyen például szükség lehet az **Alapértelmezett külső parancsfájl** modulra.)
1. Adja hozzá a **Törzs** tárolóhelyen az **Alapértelmezett lap** modult.
1. Az **Alapértelmezett lap** modul **Fő** helyén adjon hozzá egy **Tartalomgazdag blokk** modult.
1. A **Tartalomgazdag blokk** modulban adja hozzá a **Tartalomgazdag blokkelem** modult.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

### <a name="build-a-privacy-policy-page"></a>Adatvédelmi irányelv oldalának összeállítása

Az adatvédelmi irányelvek oldalának létrehozásához kövesse az alábbi lépéseket.

1. Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget az oldal létrehozásához.
1. A **Sablon kiválasztása** párbeszédablakban válassza ki az adatvédelmi irányelv oldalának sablonját.
1. Adja meg az oldal nevét és az oldal URL-t, majd kattintson az **OK** gombra. 
1. Az új lap **Fő** helyén adjon hozzá egy **Tartalomgazdag blokk** modult.
1. A **Tartalomgazdag blokk** modulban adja hozzá a **Tartalomgazdag blokkelem** modult.
1. A **Tartalomgazdag blokk** modul tulajdonságpanelén válassza az **Adatforrás hozzáadása** parancsot, majd válassza a **Rich Text tartalom** menüpontot.
1. A rich text szerkesztőben adja meg az adatvédelmi irányelvek oldal tartalmát. Szükség esetén bontsa ki a rich text szerkesztőt teljes képernyős módra.
1. Miután befejezte a tartalom bevitelével, az **Előnézet** lehetőséget kiválasztva tekintheti meg az oldal előnézetét a webböngészőben.
1. Végezze el az oldal és a modul tulajdonságainak minden hátralévő kiegészítését.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

Az adatvédelmi irányelvek oldal URL-címének közzétételéhez kövesse az alábbi lépéseket.

1. Lépjen az **URL-címek** részhez, és válassza ki az adatvédelmi irányelv oldal URL-címét.
1. A kiválasztott URL-cím közzétételéhez válassza a **közzététel** lehetőséget.

### <a name="create-a-link-to-the-privacy-policy-page-in-a-footer"></a>Az adatvédelmi irányelv oldalra mutató hivatkozás létrehozása láblécben

Az adatvédelmi irányelvek oldalra mutató hivatkozást hozzáadhatja egy töredékhez. Ezzel a módszerrel megoszthatja a hivatkozást, és a töredékre hivatkozva több webhelyoldalon is frissítheti azt. Ez a példa bemutatja, hogyan lehet az adatvédelmi irányelv oldalra mutató hivatkozást hozzáadni egy lábléctöredékhez.

A hivatkozás hozzáadásához egy lábléctöredékhez tegye a következőket.

1. Lépjen a **Töredékek** pontra, majd válassza az **Új** lehetőséget az oldaltöredék létrehozásához.
1. Az **Új töredék** párbeszédpanelen válassza ki a **Lábléc** modult.
1. A **Töredék neve** pontban adja meg a töredék nevét, majd válassza ki az **OK** lehetőséget.
1. A **Lábléc-kategória** bővítőhelyen adja hozzá a **Láblécelem** modult.
1. A jobb oldali tulajdonságok panelen válassza a **Hivatkozás szövege** lehetőséget.
1. A **Hivatkozás szövege** párbeszédpanelen adja meg az adatvédelmi irányelv oldal hivatkozásszövegét és hivatkozási célját, majd kattintson az **OK** gombra.
1. Az adatvédelmi irányelv URL-címének lekéréséhez lépjen az **Oldalak** részre, nyissa meg az adatvédelmi irányelv oldalát, és másolja az URL-címet a tulajdonságok ablaktáblából.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a töredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Megtekintheti a töredék előnézetét, és tesztelheti az adatvédelmi irányelvek oldalra mutató hivatkozást.

A töredék már hivatkozható más webhelyoldalak sablonjaiban. Ha erre a töredékre egy sablon **Lábléc** moduljában hivatkoznak, akkor a hivatkozás minden olyan oldalon megjelenik, amely az adott sablon használatával készült.

## <a name="additional-resources"></a>További erőforrások

[Megfelelőség áttekintése](compliance-overview.md)

[Kisegítő funkciók és lehetőségek](accessibility.md)

[Cookie-k megfelelősége](cookie-compliance.md)

[Nyomon követett tartalmi változásokhoz társított felhasználói azonosítók kicserélése](replace-IDs-tracked-changes.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

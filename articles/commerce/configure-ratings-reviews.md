---
title: Minősítések és értékelések konfigurálása
description: Ez a témakör azt mutatja be, hogyan lehet konfigurálni az e-kereskedelmi webhelyet a vevőértékelések megjelenítésére a Microsoft Dynamics 365 Commerce alkalmazásban.
author: gvrmohanreddy
manager: annbe
ms.date: 02/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: edd2082b5d2cafcb955f8e3c7762bcba523ac479
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412764"
---
# <a name="configure-ratings-and-reviews"></a>Minősítések és értékelések konfigurálása

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet konfigurálni az e-kereskedelmi webhelyet a vevőértékelések megjelenítésére a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

Az e-kereskedelmi webhelyek minősítései és értékelései segítik a vevőket a termékek beszerzési döntés előtt történő megismerésében, és megmutatják, hogy egyéb vevők mit gondolnak ezekről a termékekről. Az e-kereskedelmi webhelyek esetében a minősítések és értékelések a termékekkel kapcsolatos vevői visszajelzések összegyűjtésének mechanizmusai is egyben. 

## <a name="configure-a-site-to-show-ratings-and-reviews"></a>A webhely konfigurálása értékelések és vélemények megjelenítésére

Az értékelések és vélemények értékeinek konfigurációs értékei, például a bérlőazonosító, a vélemény szövegének hossza és a vélemény címének hossza, a webhely szintjén konfigurálhatók. 

Tegye a következőket a webhely konfigurálásához az értékelések és vélemények megjelenítésére. 

1. Lépjen a **Kezdőlap \> Webhelyek** elemre.
1. Válassza ki a webhely nevét. 
1. Ugrás a **Webhelybeállítások \> Bővítmények** pontra. 
1. A **Vélemény szövegének maximális hossza** mezőbe írja be, hogy a vélemények szövege legfeljebb hány karakterből állhat (például **1000**). 
1. A **Vélemény címének maximális hossza** mezőbe írja be, hogy a vélemények címei legfeljebb hány karakterből állhatnak (például **55**). 
1. Válassza a **Mentés és közzététel** lehetőséget. 

Az alábbi ábra azt mutatja, hogyan néz ki ez a konfiguráció a Dynamics 365 Commerce alkalmazásban.

![Webhely konfigurálása értékelések és vélemények megjelenítésére](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a>Termékértékelés hivatkozása egy PDP Vélemények szakaszához.

A termékértékelés a termék címe alatt jelenik meg a PDP felső részén. A termékértékelés konfigurálható úgy, hogy az ugyanannak a PDP-nek az **Vélemények** szakaszához legyen társítva. 

Egy termékértékelésnek a PDP **Vélemények** szakaszához való társításához kövesse az alábbi lépéseket.

1. Nyissa meg a PDP-sablont. 
1. Lépjen a **Vásárlásmező tárolómoduljának beállításai** lehetőségre.
1. A **Vásárlásmező** alatt válassza ki a **Termékértékelések** elemet, majd válassza a **Kattintás hivatkozása a teljes vélemények modulhoz** jelölőnégyzetet.

Az alábbi ábra azt mutatja, hogyan néz ki ez a konfiguráció a Dynamics 365 Commerce alkalmazásban.

![Termékértékelés hivatkozása egy PDP Vélemények szakaszához](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a>Az adatvédelem és irányelvek lap hivatkozásának konfigurálása

Az adatvédelem és irányelvek lap hivatkozásának konfigurálásához kövesse az alábbi lépéseket.

1. Lépjen a **Kezdőlap \> Webhelyek** elemre.
1. Válassza ki a webhely nevét. 
1. Ugrás a **Webhelybeállítások \> Bővítmények** pontra.
1. Az **Útvonalak** lapon az **RNR adatvédelem és irányelvek** alatt válassza a **Hivatkozás hozzáadása** lehetőséget. Ha már meg van adva egy hivatkozás, és ki szeretné cserélni, válassza ki a hivatkozást. 
1. A **Hivatkozás hozzáadása** párbeszédpanelen jelölje ki az adatvédelem és irányelvek lap hivatkozását, majd kattintson az **OK** gombra. 
1. Válassza a **Mentés és közzététel** lehetőséget. 

Az alábbi ábra azt mutatja, hogyan néz ki ez a konfiguráció a Dynamics 365 Commerce alkalmazásban.

![Az adatvédelem és irányelvek lap hivatkozásának konfigurálása](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="configure-ratings-and-reviews-modules-on-product-details-pages"></a>A Minősítések és értékelések modulok konfigurálása a termék részletes oldalain

A Minősítések és értékelések modulok a termék részletei oldalain történő beállításával kapcsolatos tudnivalókat lásd a [Minősítések és értékelések](ratings-reviews-modules.md) modulban.

## <a name="additional-resources"></a>További erőforrások

[Minősítések és értékelések áttekintése](ratings-reviews-overview.md)

[A minősítések és értékelések használatának bekapcsolása](opt-in-ratings-reviews.md)

[Minősítések és értékelések kezelése](manage-reviews.md)

[A Minősítések és értékelések modulok konfigurálása a termék részletes oldalain](ratings-reviews-modules.md)

[A termék minősítések szinkronizálása a következőben: Dynamics 365 Retail](sync-product-ratings.md)

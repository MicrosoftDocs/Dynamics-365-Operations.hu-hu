---
title: Minősítések és értékelések konfigurálása
description: Ez a témakör azt mutatja be, hogyan lehet konfigurálni az e-kereskedelmi webhelyet a vevőértékelések megjelenítésére a Microsoft Dynamics 365 Commerce alkalmazásban.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
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
ms.openlocfilehash: 0612b32e7751b32ad851f627a53bce2ac491870f
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770481"
---
# <a name="configure-ratings-and-reviews"></a>Minősítések és értékelések konfigurálása

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet konfigurálni az e-kereskedelmi webhelyet a vevőértékelések megjelenítésére a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

Az e-kereskedelmi webhelyek minősítései és értékelései segítik a vevőket a termékek beszerzési döntés előtt történő megismerésében, és megmutatják, hogy egyéb vevők mit gondolnak ezekről a termékekről. Az e-kereskedelmi webhelyek esetében a minősítések és értékelések a termékekkel kapcsolatos vevői visszajelzések összegyűjtésének mechanizmusai is egyben. 

Az értékelések a termék listaoldalakon, kategória listaoldalakon, a keresési találatok oldalain és a webhely más oldalain jelennek meg. Az értékelési hisztogramok és a termékértékelések a termék részletes lapjain (PDP-k) jelennek meg. A **Vélemény írása** gombra kattintva a vevők elküldhetik a termékkel kapcsolatos értékeléseket és véleményeket.

## <a name="ratings-and-reviews-modules-on-pdps"></a>Értékelések és vélemények modulok a PDP-ken 

Három modul mutatja az értékelések és vélemények összesítését a PDP-ken:

- Vélemény írása modul
- Termékvélemény-lista modul
- Értékelési hisztogram modul
 
A következő ábra bemutatja, hogyan jelennek meg az értékelések és vélemények modulok egy PDP-n.

![Értékelések és vélemények modulok a PDP-ken](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> Ha további tájékoztatást szeretne kapni a PDP-sablonok és -elrendezések optimalizálásával kapcsolatban, hogy az e-kereskedelmi webhelyének több PDP-je között megoszthassa az értékelések és vélemények modulok konfigurációit, tekintse meg a következőt: [Sablonok és elrendezések áttekintése](templates-layouts-overview.md).

A következő ábra bemutatja, hogyan mutatja be a **Modul hozzáadása** párbeszédpanel az értékelések és vélemények modulokat a Dynamics 365 Commerce alkalmazásban.

![Modul hozzáadása párbeszédpanel](media/rnr-eCommerce-pdp-adding-rnr-modules.png)

### <a name="write-review-module"></a>Vélemény írása modul

A vélemény írása modul egy **Vélemény írása** gombot tartalmaz, amely lehetővé teszi a felhasználók számára a bejelentkezést, egy értékelés hozzárendelését és a termékkel kapcsolatos vélemény megírását. Ez a modul azt is lehetővé teszi, hogy a felhasználók szerkesszék a korábban elküldött értékelést vagy véleményt. Ez a modul általában az értékelési hisztogram és a termékvélemények listájának moduljai fölött jelenik meg a PDP-ben.

A következő ábra bemutatja, hogyan jeleníti meg a **Vélemény írása** párbeszédpanel, amikor a vevő a **Vélemény írása** lehetőséget választja. A vevő ezt a párbeszédpanelt használhatja az értékelés és vélemény elküldésére.

![Vélemény írása párbeszédpanel](media/rnr-eCommerce-write-review-module.png)

A következő táblázat bemutatja a vélemény írása modul tulajdonságot, amelyet a szerkesztési eszközben konfigurálni kell.

| Tulajdonság neve | Érték        | Tulajdonság leírása                 |
|---------------|--------------|--------------------------------------|
| Név          | Vélemény írása | A vélemény írása modul neve. |

### <a name="ratings-histogram-module"></a>Értékelési hisztogram modul

Az értékelési hisztogram modul az értékelések hisztogramját jeleníti meg. Ez a modul általában a vélemény írása modul és a termékvélemények listája modul között jelenik meg a PDP-n.

Az értékelési hisztogram modul nem igényel konfigurációt. Csak fel kell vennie a modult a PDP-sablonba. 

A következő illusztrációk azt mutatják, hogy milyen egy PDP-sablon a Dynamics 365 Commerce alkalmazásban, amikor az értékelések és vélemények modulok a PDP-ken való megjelenítésre vannak konfigurálva.

![PDP-sablon, ha az értékelések és vélemények a PDP-n történő megjelenítésre vannak konfigurálva.](media/rnr-eCommerce-pdp-reviews-modules.png)

### <a name="product-reviews-list-module"></a>Termékvélemény-lista modul

A termékvélemények listája modul felsorolja a termékkel kapcsolatos véleményeket rendezési, szűrési és tördelési beállításokkal együtt. Ez a modul a PDP-n általában egy értékelési hisztogram modul után jelenik meg.

A következő táblázat bemutatja a termékvélemények listája modul tulajdonságokat, amelyeket a szerkesztési eszközben konfigurálni kell.

| Tulajdonság neve              | Érték | Tulajdonság leírása |
|----------------------------|-------| ---------------------|
| Az egyes oldalakon megjelenített vélemények | 10    | Egy PDP-n egyidejűleg megjelenített vélemények száma. A **Következő** és **Előző** gomb segítségével a felhasználók a véleményeket tartalmazó lapok között navigálhatnak. |

#### <a name="ratings-histogram--summary-view"></a>Értékelési hisztogram – Összesítő nézet

A termékvélemények listája modul tartalmaz egy olyan helyet, ahol hozzáadhat egy értékelési hisztogram modult. A következő ábra azt mutatja be, hogyan lehet az értékelési hisztogram modult hozzáadni a termékvélemények listája modulhoz a Dynamics 365 Commerce alkalmazásban.

![Értékelési hisztogram modul hozzáadása egy termékvélemények listája modulhoz](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="configure-a-site-to-show-ratings-and-reviews"></a>A webhely konfigurálása értékelések és vélemények megjelenítésére

Az értékelések és vélemények értékeinek konfigurációs értékei, például a bérlőazonosító, a vélemény szövegének hossza és a vélemény címének hossza, a webhely szintjén konfigurálhatók. 

Tegye a következőket a webhely konfigurálásához az értékelések és vélemények megjelenítésére. 

1. Lépjen a **Kezdőlap \> Webhelyek** elemre.
1. Válassza ki a webhely nevét. 
1. Lépjen a **Webhely kezelése \> Bővíthetőség** lehetőségre. 
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
1. Lépjen a **Webhely kezelése \> Bővíthetőség** lehetőségre
1. Az **Útvonalak** lapon az **RNR adatvédelem és irányelvek** alatt válassza a **Hivatkozás hozzáadása** lehetőséget. Ha már meg van adva egy hivatkozás, és ki szeretné cserélni, válassza ki a hivatkozást. 
1. A **Hivatkozás hozzáadása** párbeszédpanelen jelölje ki az adatvédelem és irányelvek lap hivatkozását, majd kattintson az **OK** gombra. 
1. Válassza a **Mentés és közzététel** lehetőséget. 

Az alábbi ábra azt mutatja, hogyan néz ki ez a konfiguráció a Dynamics 365 Commerce alkalmazásban.

![Az adatvédelem és irányelvek lap hivatkozásának konfigurálása](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="additional-resources"></a>További erőforrások

[Minősítések és értékelések áttekintése](ratings-reviews-overview.md)

[A minősítések és ellenőrzések használatának kiválasztása](opt-in-ratings-reviews.md)

[Minősítések és értékelések kezelése](manage-reviews.md)

[A termék minősítések szinkronizálása a következőben: Dynamics 365 Retail](sync-product-ratings.md)

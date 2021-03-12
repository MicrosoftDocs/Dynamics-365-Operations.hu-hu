---
title: Értékelések és vélemények modulok
description: Ez a témakör a Microsoft Dynamics 365 Commerce termékrészletek oldalain használt minősítési és az értékelési modulokat tárgyalja.
author: gvrmohanreddy
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: Release 10.0.6
ms.openlocfilehash: b17e986c2e30134c334cd547a85a1dd682172a0e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979803"
---
# <a name="ratings-and-reviews-modules"></a>Értékelések és vélemények modulok

[!include [banner](includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Commerce termékrészletek oldalain (PDP-k) használt minősítési és az értékelési modulokat tárgyalja.

## <a name="overview"></a>Áttekintés

Az e-kereskedelmi webhelyek minősítései és értékelései segítik a vevőket a termékek beszerzési döntés előtt történő megismerésében, ugyanakkor egy módszert jelentenek a termékkel kapcsolatos ügyfél-visszajelzések gyűjtésére. 

Az értékelések a termék listaoldalakon, kategória listaoldalakon, a keresési találatok oldalain és a webhely más oldalain jelennek meg. 

Az értékelési hisztogramok és a termékértékelések a PDP-ken jelennek meg. A **Vélemény írása** gombra kattintva a vevők elküldhetik a termékkel kapcsolatos értékeléseket és véleményeket. Ezeket a PDP-funkciókat a minősítési és a felülvizsgálati modulok vezérlik.

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
![Értékelés írása párbeszédablak](media/rnr-eCommerce-write-review-module.png) A következő táblázat bemutatja a vélemény írása modul tulajdonságot, amelyet a szerkesztési eszközben konfigurálni kell.
| Tulajdonság neve | Érték        | Tulajdonság leírása                 |
|---------------|--------------|--------------------------------------|
| Név          | Vélemény írása | A vélemény írása modul neve. |

### <a name="ratings-histogram-module"></a>Értékelési hisztogram modul

Az értékelési hisztogram modul az értékelések hisztogramját jeleníti meg. Ez a modul általában a vélemény írása modul és a termékvélemények listája modul között jelenik meg a PDP-n.
Az értékelési hisztogram modul nem igényel konfigurációt. Csak fel kell vennie a modult a PDP-sablonba. A következő illusztrációk azt mutatják, hogy milyen egy PDP-sablon a Dynamics 365 Commerce alkalmazásban, amikor az értékelések és vélemények modulok a PDP-ken való megjelenítésre vannak konfigurálva.
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

## <a name="additional-resources"></a>További erőforrások

[Modulkönyvtár – áttekintés](starter-kit-overview.md)

[Tárolómodul](add-container-module.md)

[Kosármodul](add-cart-module.md)

[Pénztármodul](add-checkout-module.md)

[Rendelésmegerősítési modul](order-confirmation-module.md)

[Fejlécmodul](author-header-module.md)

[Láblécmodul](author-footer-module.md)

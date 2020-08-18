---
title: Modul feltérképezése
description: Ez a témakör a feltérképezési modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket konfigurálni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: a0f5d902289c5867095e34a135c50d342f3c4f13
ms.sourcegitcommit: 078befcd7f3531073ab2c08b365bcf132d6477b0
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/31/2020
ms.locfileid: "3646950"
---
# <a name="map-module"></a>Modul feltérképezése

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a témakör a feltérképezési modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket konfigurálni a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A modul feltérképezése egy interaktív térképen jeleníti meg az üzleteket, amelyeket a [8. verziós Bing Térképek webes vezérlő](https://docs.microsoft.com/bingmaps/v8-web-control/) használatával renderelnek. A Bing Maps API-kulcsot kötelező megadni, és hozzá kell adni a Commerce központ megosztott paraméterei oldalhoz. A modul feltérképezése különböző nézeteket nyújt – például közúti, légi és utcai –, amelyekkel a felhasználók megtekinthetik a leképezési helyeket. Olyan interakciókat is lehetővé tesznek, mint például a nagyítás és a felhasználó helyének használata.

A modul feltérképezése az üzletválasztó modullal együtt dolgozik a térképeken megjelenített üzletek földrajzi helyeinek meghatározásában. Az üzletválasztó és a modul feltérképezések akkor lépnek interakcióba, ha a felhasználó a webhely egyik moduljában kiválaszt egy üzletet. A modul feltérképezések az üzletválasztó modulokkal való interakción túl más forgatókönyvek esetén is kiterjeszthetőek. Azonban a modul testreszabása kötelező.

A modul feltérképezése a Commerce 10.0.13 verziójában lett bevezetve.

A következő kép egy üzlet oldalán használt letérképezési modul egy példáját jeleníti meg.

![Példa egy üzletválasztó modulra](./media/ecommerce-Storelocator.PNG)

## <a name="module-properties"></a>Modul tulajdonságai

| Tulajdonság neve             | Érték                 | Leírás |
|---------------------------|-----------------------|-------------|
| Címsor | Szöveg | A modul címe. |
| A gombostű beállításai: alapértelmezett ikon | Kép | A térképeken megjelenített üzletekhez használandó gombostű szimbólum képe. |
| A gombostű beállításai: aktív ikon | Kép | A térképeken kiválasztott üzlethez használandó gombostű szimbólum képe. |
| A gombostű beállításai: alapértelmezett ikon színe | Karaktersztring | A gombostű szimbólumok színének szöveges vagy hexadecimális értékének beállítása a térképen. |
| A gombostű beállításai: aktív ikon színe | Karaktersztring | A kiválasztott gombostű szimbólumok színének szöveges vagy hexadecimális értékének beállítása a térképen. |
| Index megjelenítése | **Igaz** vagy **Hamis** | Ha ez a tulajdonság **Igaz** értékre van állítva, akkor az üzletet jelző összes gombostű szimbóluma egy indexet jelenít meg. Ez az index megegyezik azzal a listanézet-mutatóval, amelyre az üzletválasztó modul mutat. |

## <a name="add-allowed-mapping-urls-to-a-sites-content-security-policy-directives"></a>Engedélyezett leképezési URL-címek hozzáadása a webhely tartalmának biztonsági házirendjéhez

Annak érdekében, hogy a térképek modul együttműködjön a Bing Maps szolgáltatással, gondoskodni kell arról, hogy a webhely tartalmának biztonsági házirendjében (CSP) a következő leképezési URL-címeket engedélyezzék (más néven „engedélyezési listához adva”). Ez a beállítás a Commerce webhelykészítőben végezhető el azzal, ha engedélyezett URL-címeket ad különböző webhely CSP-utasításokhoz (például **img-src**). További információ: [Tartalomra vonatkozó biztonsági irányelv (CSP)](manage-csp.md). 

- A **connect-src** utasításhoz adja hozzá a **&#42;.bing.com** kiterjesztést.
- Az **img-src** utasításhoz adja hozzá a **&#42;virtualearth.net** kiterjesztést.
- A **script-src** utasításhoz adja hozzá a **&#42;.bing.com, &#42;.virtualearth.net** kiterjesztést.
- A **script style-src** utasításhoz adja hozzá a **&#42;.bing.com** kiterjesztést.

## <a name="add-a-map-module-to-a-page"></a>Térképmodul felvétele egy oldalra

A térképmodul oldalon lévő konfigurálásával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Üzletválasztó modul](store-selector.md). 
 
## <a name="additional-resources"></a>További erőforrások

[Kezdőcsomag áttekintése](starter-kit-overview.md)

[Vásárlásmező-modul](add-buy-box.md)

[Kosármodul](add-cart-module.md)

[Áruházválasztó modul](store-selector.md)

[A szervezetéhez tartozó Bing Térképek kezelése](./dev-itpro/manage-bing-maps.md)

[8. verziós Bing Maps webes vezérlő](https://docs.microsoft.com/bingmaps/v8-web-control/)

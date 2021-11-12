---
title: Ország/régió kiválasztómodulja
description: Ez a témakör az ország/régió kiválasztómodulját ismerteti, és bemutatja, hogyan konfigurálhatjuk a Microsoft Dynamics 365 Commerce alkalmazásban.
author: stuharg
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2021-08-12
ms.dyn365.ops.version: Release 10.0.22
ms.openlocfilehash: 35d78cdcc356d35776940147e9b0afee0f0be2a2
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/23/2021
ms.locfileid: "7674723"
---
# <a name="countryregion-picker-module"></a>Ország/régió kiválasztómodulja

[!include [banner](includes/banner.md)]

Ez a témakör az ország/régió kiválasztómodulját ismerteti, és bemutatja, hogyan konfigurálhatjuk a Microsoft Dynamics 365 Commerce alkalmazásban.

Az ország/régió kiválasztómodulja a [földrajzi észlelés és átirányítás](geo-detection-redirection.md) funkció használatával mutatja meg azoknak a vevőknek az ajánlott URL-címeit, akik olyan e-kereskedelmi webhely URL-címét kérik, amely nincs az adott országhoz vagy a Dynamics 365 Commerce területhez társítva.

Egy kanadai vevő például olyan webhely URL-címét kéri, amely nincs Kanadához társítva. Ebben az esetben az ország/régió kiválasztómodulban megjelenik egy párbeszédpanel, amely a Kanadához társított webhely-URL-címeket ajánlja fel. A következő ábrán egy példát láthat az ország/régió kiválasztómodul párbeszédpanelről.

![Példa egy ország/régió kiválasztó párbeszédpanelére egy honlapon.](./media/Geo_country-region-module-insitu.png)

## <a name="countryregion-picker-module-properties"></a>Ország/régió kiválasztómoduljának tulajdonságai

| Tulajdonság neve              | Érték       | Leírás |
| -------------------------- | ----------- | ----------- |
| Fejléc                    | Szöveg        | A párbeszédpanel tetején megjelenő fejléc. |
| Alcímsor                 | Szöveg        | A fejléc alatt megjelenő alfejléc. |
| Ország: Megjelenítési sztring    | Szöveg        | Egy URL-lehetőség megjelenítendő neve (például "Kanada"). |
| Ország: Megjelenítési alsztring | Szöveg        | Egy URL-beállítás (például "angol" vagy "francia") megjelenítési alsztringje. |
| Ország: Ország képe     | Médiaeszköz | Nem kötelező kép, amely egy URL-beállításhoz van társítva (például a kanadai zászló képe). |
| Ország: Ország URL-címe       | Szöveg        | Az URL-cím, amely megfelel annak a csatornának és területi beállításnak, amely az országhoz vagy régióhoz be van állítva a Commerce webhelyszerkesztő **Csatornák** lapján (**Webhely-beállítások \> Csatornák**). Ennek az URL-címnek pontosan meg kell egyeznie a **Csatornák** lapon beállított URL-címmel. |
| Művelethivatkozás                | Művelethivatkozás | A párbeszédpanel alján megjelenő opcionális hivatkozás. Ez a hivatkozás például egy olyan belső oldalra mutathat, amely felsorolja azokat az országokat és régiókat, amelyeket a webhely támogat. |

## <a name="add-a-countryregion-picker-module-to-a-page"></a>Ország/régió kiválasztómodul hozzáadása egy laphoz

Az ország/régió kiválasztómodul közvetlenül vagy közös töredék útján hozzáadható a fejlécmodulhoz. További tájékoztatás a fejlécmodulokról: [Fejlécmodul](author-header-module.md).

## <a name="configure-the-countryregion-picker-module-in-commerce-site-builder"></a>Az ország/régió kiválasztómodul konfigurálása a Commerce webhelyszerkesztőben

> [!NOTE]
> A vevőknek ajánlott URL-címeket országobjektumként kell konfigurálni az ország/régió kiválasztómodulban.

Minden olyan URL-cím esetében, amelyet meg szeretne mutatni és ajánlani a vevőknek, kövesse az alábbi lépéseket a Commerce webhelyszerkesztőben.

1. Válassza ki az ország/régió kiválasztómoduljának helyét.
1. A tulajdonságok ablak **Országlista** területén válassza ki az **Ország hozzáadása** lehetőséget.
1. Jelölje be az új **Ország** négyzetet.
1. A **Megjelenítési sztring** mezőben adjon meg egy megjelenítendő nevet (például **Kanada**).
1. Nem kötelező: A **Megjelenítési alsztring** mezőben adjon meg egy megjelenítési alsztringet (például **francia** vagy **fr-ca**).
1. Nem kötelező: Válasszon ki egy képet a médiatárból.
1. Az **Ország URL-je** mezőben adja meg az URL-címet. Ennek az URL-címnek pontosan meg kell egyeznie a **Csatornák** lapon megjelenő és a csatornához rendelt URL-címekkel, beleértve az országhoz vagy régióhoz társított helyet is.
1. Válassza ki az **OK** lehetőséget.
1. Ismételje meg ezeket a lépéseket minden olyan ország URL-címénél, amelyeknél meg szeretné jeleníteni az ország/régió kiválasztómodulját.

## <a name="additional-resources"></a>További erőforrások

[Földrajzi észlelés és átirányítás beállítása](geo-detection-redirection.md)

[Modultár áttekintése](starter-kit-overview.md)

[Fejlécmodul](author-header-module.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

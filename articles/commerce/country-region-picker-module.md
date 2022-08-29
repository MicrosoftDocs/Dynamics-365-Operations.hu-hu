---
title: Ország/régió kiválasztómodulja
description: Ez a témakör az ország-/régióválasztó modult ismerteti, és bemutatja, hogyan kell konfigurálni a modulban Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 04/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-08-12
ms.dyn365.ops.version: Release 10.0.22
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 203a8e17e075f15b7ae3cceb98d24ced75539a01
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270291"
---
# <a name="countryregion-picker-module"></a>Ország/régió kiválasztómodulja

[!include [banner](includes/banner.md)]

Ez a témakör az ország-/régióválasztó modult ismerteti, és bemutatja, hogyan kell konfigurálni a modulban Microsoft Dynamics 365 Commerce.

Az Dynamics 365 Commerce ország/régió választó modul a [földrajzi észlelési és átirányítási](geo-detection-redirection.md) funkciók használatával mutatja meg a javasolt webhelyeket azoknak a vevőknek, akik olyan e-commerce webhely URL-címét kérik, amely nincs az adott országhoz vagy területhez társítva.

Például egy kanadai vevő egy olyan webhely URL-címét kéri, amely nem Kanadához tartozik. Ebben az esetben az ország/régió kiválasztómodulban megjelenik egy párbeszédpanel, amely a Kanadához társított webhely-URL-címeket ajánlja fel. 

## <a name="how-it-works"></a>Hogyan működik?

Ha egy webhelyen engedélyezve van a földrajzi észlelés és az átirányítás, és a vevő URL-címet kér a webhelytől, akkor a rendszer a vevő számára észlelt országot és a kért URL-címet használja annak meghatározására, hogy az ADOTT URL-cím ahhoz az országhoz van-e hozzárendelve, ahol a vevő található. Az URL-címek és az országok/régiók közötti megfeleltetést **a Commerce** **Webhely**-szerkesztő Webhely beállításai területén, a Csatornák lapon lehet meghatározni. 

Ha a kérés URL-címe nem felel meg egyetlen URL-címnek sem, amely a vevő országához van hozzárendelve, a válaszban az adott országra leképezett egy vagy több URL-cím listája is megjelenik. Az ország/régióválasztó a listán található összes URL-címet összeveti az ország/régió modulban beállított URL-címekkel. Az ország/régió választó minden pontos egyezés esetén megjeleníti az adott URL-cím megjelenítési fejlécét, alfejlécét és képét, és az URL használatával hivatkozással jeleníti meg ezeket az elemeket.

Ha egy vevő az ország/régió választó egyik beállítását választja, akkor a rendszer a hivatkozásként megadott URL-címre használja a beállításokat. Az URL-cím az **\_ msdyn365\_\_\_\_** webhelyi süteménybe van írva, hogy a vevő által preferált webhelyként használható legyen. Ezután amikor a vevő legközelebb a saját országához vagy régiójához nem társított URL-címet kéri, automatikusan átirányítja őket a preferált országba. Ezért javasoljuk, [hogy](site-selector.md) az e-commerce webhelyen is használja a webhelyválasztó modult, hogy a vevők felülbírálják vagy frissítsék a webhely beállításait. 

Ha egy vevő bezárja az ország/régió választó párbeszédpanelt, a program nem írja a süteményt, és a vevő továbbra is az aktuális webhelyen marad. 

A következő ábrán egy példát láthat az ország/régió kiválasztómodul párbeszédpanelről.

![Példa egy ország/régió kiválasztó párbeszédpanelére egy honlapon.](./media/Geo_country-region-module-insitu.png)

## <a name="countryregion-picker-module-properties"></a>Ország/régió kiválasztómoduljának tulajdonságai

| Tulajdonság neve              | Érték       | Leírás                                                  |
| -------------------------- | ----------- | ------------------------------------------------------------ |
| Fejléc                    | Szöveg        | A párbeszédpanel tetején megjelenő fejléc.       |
| Alcímsor                 | Szöveg        | A fejléc alatt megjelenő alfejléc.               |
| Ország: Megjelenítési sztring    | Szöveg        | Egy URL-lehetőség megjelenítendő neve (például "Kanada").   |
| Ország: Megjelenítési alsztring | Szöveg        | Egy URL-beállítás (például "angol" vagy "francia") megjelenítési alsztringje. |
| Ország: Ország képe     | Médiaeszköz | Nem kötelező kép, amely egy URL-beállításhoz van társítva (például a kanadai zászló képe). |
| Ország: Ország URL-címe       | Szöveg        | A konfigurált ország/régió webhelyének URL-címe. Ennek az URL-címnek pontosan meg kell egyeznie az adott országhoz/**·** **régióhoz** megadott URL-címekkel a Commerce Webhely beállításai területen található Csatornák lapon. Ezenkívül az **URL** **tartományának** a Csatornák lap Tartomány egyeztetése mezőjében megadott egyéni tartománynak kell lennie, nem pedig a Commerce által az e-commerce környezet létrehozásakor megadott munkacímnek (például az URL-címnek).`https://<yourcompany>.commerce.dynamics.com/` |
| Művelethivatkozás                | Művelethivatkozás | A párbeszédpanel alján megjelenő opcionális hivatkozás. Ez a hivatkozás például egy olyan belső oldalra mutathat, amely felsorolja azokat az országokat és régiókat, amelyeket a webhely támogat. |

## <a name="add-a-countryregion-picker-module-to-a-page"></a>Ország/régió kiválasztómodul hozzáadása egy laphoz

Az ország/régió kiválasztómodul közvetlenül vagy közös töredék útján hozzáadható a fejlécmodulhoz. További tájékoztatás a fejlécmodulokról: [Fejlécmodul](author-header-module.md).

## <a name="configure-the-countryregion-picker-module-in-commerce-site-builder"></a>Az ország/régió kiválasztómodul konfigurálása a Commerce webhelyszerkesztőben

> [!NOTE]
> A vevőknek ajánlott URL-címeket országobjektumként kell konfigurálni az ország/régió kiválasztómodulban.

Minden egyes webhely URL-címének megjelenítése és ajánlása a Commerce Webhelyszerkesztőben található.

1. Válassza ki az ország/régió kiválasztómoduljának helyét.
1. A tulajdonságok ablak **Országlista** területén válassza ki az **Ország hozzáadása** lehetőséget.
1. Jelölje be az új **Ország** négyzetet.
1. A **Megjelenítési sztring** mezőben adjon meg egy megjelenítendő nevet (például **Kanada**).
1. Nem kötelező: A **Megjelenítési alsztring** mezőben adjon meg egy megjelenítési alsztringet (például **francia** vagy **fr-ca**).
1. Nem kötelező: Válasszon ki egy képet a médiatárból.
1. Az **Ország URL-je** mezőben adja meg az URL-címet. Ennek az URL-címnek pontosan meg kell egyeznie a Csatornák lapon megjelenő, **a** csatornához rendelt URL-sel, valamint az országhoz vagy területhez társított területi helyhez. 
1. Válassza ki az **OK** lehetőséget.
1. Ismételje meg ezeket a lépéseket minden olyan ország URL-címénél, amelyeknél meg szeretné jeleníteni az ország/régió kiválasztómodulját.

## <a name="additional-resources"></a>További erőforrások

[Földrajzi észlelés és átirányítás beállítása](geo-detection-redirection.md)

[Modultár áttekintése](starter-kit-overview.md)

[Fejlécmodul](author-header-module.md)

[Webhelyválasztó modul](site-selector.md)

[Útkövetési modul](add-breadcrumb.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

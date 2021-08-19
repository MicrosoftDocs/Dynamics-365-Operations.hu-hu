---
title: Navigációs menü modulja
description: Ez a témakör a navigációs menü modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 01/28/2021
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 486f20c26f97c236dfde2cbaedd8df434fe762947a6caa1c7cc03e4d244f4d47
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6761586"
---
# <a name="navigation-menu-module"></a>Navigációs menü modul

[!include [banner](includes/banner.md)]

Ez a témakör a navigációs menü modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

A navigációs menü modulok elsődleges célja, hogy a webhely felhasználói a Dynamics 365 Commerce központban megadott csatorna-navigációs hierarchia alapján böngésszék a termékeket és a weboldalakat. A navigációs menü modulban konfigurált cikkek a webhely fejlécének navigációs részeként jelennek meg. A navigációs menü modulok olyan statikus menüelemeket is támogatnak, amelyek az e-commerce webhely más lapjaira hivatkoznak.

A navigációs menü modul hozzáadható a lap fejlécmoduljához. A Fabrikam témában a navigációs menü alapértelmezés szerint két szintet mutat. A Keudő témában a navigációs menü alapértelmezés szerint három szintet mutat. Ha módosítani szeretné a szintek számát, a témában egy nézetbővítmény szükséges.

A következő ábra egy navigációs menüt mutat be a Fabrikam, webhelyen, amely két szintű kategória-hierarchiát és néhány statikus menüelemet jelenít meg.
![Példa egy navigációs menü modulra.](./media/ecommerce-header.png)

## <a name="navigation-menu-module-properties"></a>Navigációs menü moduljának tulajdonságai

| Tulajdonság neve             | Érték                 | Leírás |
|---------------------------|-----------------------|-------------|
| Forrás                  | **Kiskereskedelem**, **Kézi szerkesztés**, **Kiskereskedelem és kézi készítés** | A **Kiskereskedelem** érték lehetővé teszi a csatorna navigációs hierarchiájának megjelenítését a Commerce központból a navigációs menüben. A **Manuális szerkesztés** érték lehetővé teszi a statikus menüelemek válogatását. A **Kiskereskedelem és a manuális szerkesztés** érték a kettő kombinációját is lehetővé teszi. |
| Kategóriaképek megjelenítése | **Igaz** vagy **Hamis**    | Ha ez a tulajdonság engedélyezve van, megjeleníti a kategóriaképeket a navigációs menüben, ahogy az definiálva van a Commerce központban az egyes kategóriákhoz. Hozzáadva a Commerce 10.0.14-es kiadásában. |
| Promóciók megjelenítése | **Igaz** vagy **Hamis** | Ha ez a tulajdonság engedélyezve van, a promóciók képekkel, hivatkozásokkal és szövegekkel konfigurálhatók. Ezt a tulajdonságot a Commerce rendszer 10.0.17-es kiadásában adták hozzá. |
| Promóciók hozzáadása | Szöveg, kép vagy hivatkozás | Ha a **Promóciók megjelenítése** tulajdonság engedélyezve van, a navigációs menüben felvehet szöveget, képet vagy hivatkozást promóciós tartalomként. |
| Többszintű navigációs menü engedélyezése | **Igaz** vagy **Hamis** | Ha ezt a tulajdonságot engedélyezi, a navigációs menü több szinten is megjelenítheti a navigációs hierarchiát. Ez a funkció elérhető a Commerce alkalmazás 10.0.15-ös kiadásában. |
| Szintek száma | egész szám | Ez a tulajdonság határozza meg a szintek számát, amelyeket meg kell jeleníteni, ha a **Többszintű navigációs menü engedélyezése** tulajdonság értéke **Igaz**. |
| Statikus menüelem| Értékek tömbje| A statikus menüelemek menüelemek nevét társítják egy statikus webhely-lapra mutató hivatkozással. A menüelemek más menüelemek alatt is létrehozhatók. Alapértelmezés szerint a statikus menük a gyökér szintjén jelennek meg, és a csatorna navigációs hierarchiához lesznek hozzáfűzve, ha van ilyen. |
| Gyökérmenü megjelenítése | **Igaz** vagy **Hamis** | Ha ezt a tulajdonságot engedélyezte, a navigációs menü definiálható egy egyéni gyökér (például a **Vásárlás most**) alapján is. Ez a funkció a Dynamics 365 Commerce 10.0.15 kiadásban elérhető. |
| Gyökérmenü | karakterlánc | Ez a tulajdonság használható egy egyéni gyökér szövegének meghatározására, ha a **Gyökérmenü megjelenítése** tulajdonság értéke **Igaz**. |

A következő ábra egy példát mutat be egy kategóriakép megjelenítésére a Fabrikam webhely navigációs menüjében.
![Példa egy navigációs menü moduljára a kategóriaképekkel.](./media/ecommerce-categoryimages.PNG)

## <a name="add-a-navigation-menu-module-to-a-header-module"></a>Navigációs menümodul hozzáadása a fejléc modulhoz

A navigációs menü modulnak a fejléc-modulba való felvételével kapcsolatos részleteket lásd a [Fejléc modul](author-header-module.md) részben.

## <a name="additional-resources"></a>További erőforrások

[Modultár áttekintése](starter-kit-overview.md)

[Útkövetési modul](add-breadcrumb.md)

[Oldalválasztó modul](site-selector.md)

[Vásárlásmező-modul](add-buy-box.md)

[Cookie-k megfelelősége](cookie-compliance.md)

[Fejlécmodul](author-header-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

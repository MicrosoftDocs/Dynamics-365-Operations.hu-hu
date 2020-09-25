---
title: Navigációs menü modulja
description: Ez a témakör a navigációs menü modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 08/31/2020
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 9f66bbe7bf436ab6360dda7d92d6d51e47eedf16
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761394"
---
# <a name="navigation-menu-module"></a>Navigációs menü modulja

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a témakör a navigációs menü modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A navigációs menü modulok elsődleges célja, hogy a webhely felhasználói a Dynamics 365 Commerce központban megadott csatorna-navigációs hierarchia alapján böngésszék a termékeket és a weboldalakat. A navigációs menü modulban konfigurált cikkek a webhely fejlécének navigációs részeként jelennek meg. A navigációs menü modulok olyan statikus menüelemeket is támogatnak, amelyek az e-commerce webhely más lapjaira hivatkoznak.

A navigációs menü modul hozzáadható a lap fejlécmoduljához. A Fabrikam témában a navigációs menü alapértelmezés szerint két szintet mutat. A Keudő témában a navigációs menü alapértelmezés szerint három szintet mutat. Ha módosítani szeretné a szintek számát, a témában egy nézetbővítmény szükséges.

A következő ábra egy navigációs menüt mutat be a Fabrikam, webhelyen, amely két szintű kategória-hierarchiát és néhány statikus menüelemet jelenít meg.
![Példa egy navigációs menü modulra](./media/ecommerce-header.png)

## <a name="navigation-menu-module-properties"></a>Navigációs menü moduljának tulajdonságai

| Tulajdonság neve             | Érték                 | Leírás |
|---------------------------|-----------------------|-------------|
| Forrás                  | **Kiskereskedelem**, **Kézi szerkesztés**, **Kiskereskedelem és kézi készítés** | A **Kiskereskedelem** érték lehetővé teszi a csatorna navigációs hierarchiájának megjelenítését a Commerce központból a navigációs menüben. A **Manuális szerkesztés** érték lehetővé teszi a statikus menüelemek válogatását. A **Kiskereskedelem és a manuális szerkesztés** érték a kettő kombinációját is lehetővé teszi. |
| Kategóriaképek megjelenítése | **Igaz** vagy **Hamis**    | Ha ez a tulajdonság engedélyezve van, megjeleníti a kategóriaképeket a navigációs menüben, ahogy az definiálva van a Commerce központban az egyes kategóriákhoz. Hozzáadva a Commerce 10.0.14-es kiadásában. |
| Statikus menüelem| Értékek tömbje| A statikus menüelemek menüelemek nevét társítják egy statikus webhely-lapra mutató hivatkozással. A menüelemek más menüelemek alatt is létrehozhatók. Alapértelmezés szerint a statikus menük a gyökér szintjén jelennek meg, és a csatorna navigációs hierarchiához lesznek hozzáfűzve, ha van ilyen. |

A következő ábra egy példát mutat be egy kategóriakép megjelenítésére a Fabrikam webhely navigációs menüjében.
![Példa egy navigációs menü moduljára a kategóriaképekkel](./media/ecommerce-categoryimages.PNG)

## <a name="add-a-navigation-menu-module-to-a-header-module"></a>Navigációs menümodul hozzáadása a fejléc modulhoz

A navigációs menü modulnak a fejléc-modulba való felvételével kapcsolatos részleteket lásd a [Fejléc modul](author-header-module.md) részben.

## <a name="additional-resources"></a>További erőforrások

[Kezdőcsomag áttekintése](starter-kit-overview.md)

[Vásárlásmező-modul](add-buy-box.md)

[Cookie-k megfelelősége](cookie-compliance.md)

[Fejlécmodul](author-header-module.md)
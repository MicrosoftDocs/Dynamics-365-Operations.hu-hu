---
title: Termékek és kategóriák hiányoznak környezeti másolás után
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújt abban az esetben, ha termékek és kategóriák hiányoznak, miután egy webhelyet környezetek között vagy ugyanazon környezeten belül másolt.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 4964b9623a91286d4f8260bcae7941feb48f8962
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022398"
---
# <a name="products-and-categories-missing-after-environment-copy"></a>Termékek és kategóriák hiányoznak környezeti másolás után

[!include [banner](../../includes/banner.md)]

Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújt abban az esetben, ha termékek és kategóriák hiányoznak, miután egy webhelyet környezetek között vagy ugyanazon környezeten belül másolt.

## <a name="description"></a>Leírás

Miután a webhelyet átmásolták az egyik környezetből a másikba, vagy a másolás ugyanabban a környezetben történt, termékek és a kategóriák hiányoznak a webhelyről. A termékek és kategóriák az e-kereskedelmi üzletből és a Commerce webhelyszerkesztő **Termékek** lapjáról hiányoznak.

## <a name="resolution"></a>Felbontás

### <a name="map-the-channel-operating-unit-number-to-a-newly-copied-site-in-commerce-site-builder"></a>A csatorna üzemiegység-számának hozzárendelése egy újonnan másolt webhelyre a Commerce webhelyszerkesztőben

Kövesse az alábbi lépéseket a csatorna üzemiegység-számának (OUN) egy újonnan másolt webhelyre való hozzárendeléséhez a Commerce webhelyszerkesztőben.

1. Válassza ki az újonnan másolt webhelyet.
1. A **Webhely beállításai** pontban válassza ki a **Csatornák** elemet.
1. A csatorna neve mellett válassza ki a három pontot (**...**), majd válassza az **Online áruházcsatorna módosítása** lehetőséget.
1. Az **Online áruházcsatorna módosítása** párbeszédpanelen válassza ki az újonnan másolt webhelyhez hozzárendelni kívánt csatornát, majd kattintson az **OK** gombra.
1. Válassza a **Mentés és közzététel** lehetőséget.

## <a name="additional-resources"></a>További erőforrások

[Dynamics 365 Commerce webhely társítása online csatornával](../associate-site-online-store.md)

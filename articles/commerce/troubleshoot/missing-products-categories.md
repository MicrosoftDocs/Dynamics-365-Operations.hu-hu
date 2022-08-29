---
title: Termékek és kategóriák hiányoznak környezeti másolás után
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújtanak abban az esetben, ha egy hely hiányzik a környezetek vagy az adott környezet között történt másolás után.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: d8df3f4cca6a7aaad98ffb7f2d284211a4f9589b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277906"
---
# <a name="products-and-categories-missing-after-environment-copy"></a>Termékek és kategóriák hiányoznak környezeti másolás után

[!include [banner](../../includes/banner.md)]

Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújtanak abban az esetben, ha egy hely hiányzik a környezetek vagy az adott környezet között történt másolás után.

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

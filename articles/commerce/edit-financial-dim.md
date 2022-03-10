---
title: Kiskereskedelmi tranzakciók pénzügyi dimenzióinak szerkesztése
description: Ez a témakör azt ismerteti, hogyan szerkeszti a Microsoft kiskereskedelmi tranzakcióinak pénzügyi dimenzióit a Microsoft Dynamics 365 Commerce szolgáltatásban.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: d5fee5f5dfee73ddb9fbcf8a33df66c29f9438b49136181633b989d1a02ef4f5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765314"
---
# <a name="edit-financial-dimensions-for-retail-transactions"></a>Kiskereskedelmi tranzakciók pénzügyi dimenzióinak szerkesztése

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan szerkeszti a Microsoft kiskereskedelmi tranzakcióinak pénzügyi dimenzióit a Microsoft Dynamics 365 Commerce szolgáltatásban.

## <a name="edit-financial-dimensions"></a>Pénzügyi dimenziók szerkesztése

A kiskereskedelmi tranzakcióik pénzügyi dimenzióinak szerkesztéséhez a Commerce központi felületén kövesse az alábbi lépéseket.

1. Nyissa meg a **Pénzügyi dimenziók konfigurációja alkalmazások integrálásához** oldalt.
1. Válassza ki az aktív **Alapértelmezett dimenzióintegráció** rekordot.
1. A **Pénzügyi dimenziók** gyorslapon győződjön meg arról, hogy az Excel-munkalapon szerkeszteni kívánt összes dimenzió megtalálható a **Kijelölt** listában. További tudnivalókért lásd: [Adatentitások](../fin-ops-core/dev-itpro/financial/financial-dimension-configuration-integration.md#data-entities).
1. Töltse le és nyissa meg az Excel-fájlt a **Kimutatások** lapról, a **Kiskereskedelmi tranzakciók** lapról vagy a **Tranzakció-ellenőrzési hibák** csempéről az **Üzlet pénzügyi adatai** munkaterületen.
1. A tranzakció pénzügyi dimenziójának módosításához válassza a **Tervezés** lehetőséget, majd a **Tranzakció (auditálható)** sor melletti ceruza szimbólumot.
1. Keresse meg, és jelölje ki a **FinancialDimensionDisplayValue** mezőt, jelöljön ki egy cellát az Excel-munkalap fejlécrészében, majd válassza a **Címke hozzáadása** lehetőséget.
1. Jelöljön ki egy cellát az előző lépésben kijelölt cella alatt, válassza az **Érték hozzáadása**, majd a **Frissítés** lehetőséget. A rendszer hozzáadja a pénzügyi dimenziókat az Excel munkalaphoz, amelyek ezután szerkeszthetők és közzétehetők.
1. A tranzakciósorok dimenzióinak módosításához jelölje ki az **Értékesítési tranzakciók (auditálható)** sort, jelölje ki a ceruza szimbólumot, majd ismételje meg a 6. és 7. lépést.
1. A fizetési sorok dimenzióinak módosításához jelölje ki a **Fizetési tranzakciók (auditálható)** sort, jelölje ki a ceruza szimbólumot, majd ismételje meg a 6. és 7. lépést.

## <a name="additional-resources"></a>További erőforrások

[Készpénzzel fizetett, azonnal átvett és készpénzkezelési tranzakciók szerkesztése és auditálása](edit-cash-trans.md)

[Online rendeléses és aszinkron vevői rendeléses tranzakciók szerkesztése és auditálása](edit-order-trans.md)

[Excel-munkafüzet létrehozása a kiskereskedelmi tranzakciók szerkesztéséhez](create-excel-edit.md)

[Mezők hozzáadása Excel-munkafüzethez a kiskereskedelmi tranzakciók szerkesztéséhez](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
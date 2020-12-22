---
title: Kiskereskedelmi tranzakciók pénzügyi dimenzióinak szerkesztése
description: Ez a témakör azt ismerteti, hogyan szerkeszti a Microsoft kiskereskedelmi tranzakcióinak pénzügyi dimenzióit a Microsoft Dynamics 365 Commerce szolgáltatásban.
author: josaw1
manager: AnnBe
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: e26bd4eb53fa44330f15c7cda004cb3d19dfec6d
ms.sourcegitcommit: ce51ff2b6099c75dceb99de6dea9d53baf99772d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/04/2020
ms.locfileid: "4459198"
---
# <a name="edit-financial-dimensions-for-retail-transactions"></a>Kiskereskedelmi tranzakciók pénzügyi dimenzióinak szerkesztése

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan szerkeszti a Microsoft kiskereskedelmi tranzakcióinak pénzügyi dimenzióit a Microsoft Dynamics 365 Commerce szolgáltatásban.

## <a name="edit-financial-dimensions"></a>Pénzügyi dimenziók szerkesztése

A kiskereskedelmi tranzakcióik pénzügyi dimenzióinak szerkesztéséhez a Commerce központi felületén kövesse az alábbi lépéseket.

1. Nyissa meg a **Pénzügyi dimenziók konfigurációja alkalmazások integrálásához** oldalt.
1. Válassza ki az aktív **Alapértelmezett dimenzióintegráció** rekordot.
1. A **Pénzügyi dimenziók** gyorslapon győződjön meg arról, hogy az Excel-munkalapon szerkeszteni kívánt összes dimenzió megtalálható a **Kijelölt** listában. További tudnivalókért lásd: [Adatentitások](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/financial/financial-dimension-configuration-integration#data-entities).
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

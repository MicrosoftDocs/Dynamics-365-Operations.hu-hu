---
title: Bérlista-integrációs paraméterek
description: Ez a témakör a Dynamics 365 Human Resources bérszámfejtés integrációs paramétereit írja le.
author: marcelbf
ms.date: 06/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-17
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 37d4dc52e7fe5ddd95f43d98267db819a275bd92
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8069857"
---
# <a name="payroll-integration-parameters"></a>Bérlista-integrációs paraméterek


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A Dynamics 365 Human Resources bérlista-integráció használata előtt be kell állítania az ebben a témakörben leírt paramétereket.

## <a name="enable-payroll-address"></a>Bérlista címének engedélyezése

A bérlista címének használatához engedélyeznie kell a címet a [megosztott paraméterek űrlapjáról](hr-setup-shared-parameters.md) a Bérlista-integráció lapon.

## <a name="define-the-identification-type"></a>Az azonosító típusának megadása

Ahhoz, hogy a [bérlista alkalmazotti entitásában](hr-admin-integration-payroll-api-payroll-employee.md) megjelenjen az azonosítótípus azonosítója, minden vállalathoz be kell állítani az [emberi erőforrások konfigurációs paramétereit](hr-setup-shared-parameters.md) paramétereit.

1. A **Juttatások kezelése** munkaterületen a hivatkozások alatt válassza a **Human Resources paraméterei** lehetőséget. 
2. A **Bérlista-integráció** lapon adja meg a következő mezők értékét.

| Mező | Leírás |
| --- | --- |
| Azonosítótípusok használata a bérlista feldolgozásában | Ha ez a beállítás be van jelölve, akkor a kiválasztott típusazonosító látható lesz a bérlista alkalmazotti entitásában. |
| Azonosító típusa | A [bérlista alkalmazotti entitásának](hr-admin-integration-payroll-api-payroll-employee.md)  **mshr_payrollemployeeentityid** mezőjében megjelenítendő azonosítótípus. |

## <a name="see-also"></a>Lásd még

[Bérlista-integrációs API bemutatása](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

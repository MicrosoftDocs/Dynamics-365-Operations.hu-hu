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
ms.openlocfilehash: 0c489b99d5d05ddac46d222e701512288aeb10583a5e829212e0e1c924622f16
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6712073"
---
# <a name="payroll-integration-parameters"></a>Bérlista-integrációs paraméterek

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

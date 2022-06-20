---
title: Bérlista-integrációs paraméterek
description: Ez a cikk a bérlista-integráció Dynamics 365 Human Resources paramétereit írja le.
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
ms.openlocfilehash: 7d784909fc8c5fa05557566b62b19802cd2acece
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896097"
---
# <a name="payroll-integration-parameters"></a>Bérlista-integrációs paraméterek


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A Bérlista integráció Dynamics 365 Human Resources használata előtt be kell állítania az ebben a cikkben ismertetett paramétereket.

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

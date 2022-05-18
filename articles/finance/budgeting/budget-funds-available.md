---
title: Rendelkezésre álló költségvetési források
description: Ez a témakör bemutatja a rendelkezésre álló költségvetési alapok funkciót, és olyan információkat tartalmaz, amelyek segítséget nyújtnak a költségvetés-ellenőrzésnek a szervezet pénzügyi erőforrásainak kezelésére való konfigurálásában.
author: RyanCCarlson2
ms.date: 11/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetControlConfiguration
audience: Application User
ms.reviewer: kfend
ms.custom:
- "60493"
- intro-internal
ms.assetid: be964167-43bc-431d-9adb-48bff32d68d5
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2021-11-28
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: 1e7b2bf7ef7bd1bca6db27371f87dfddcdceef89
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/05/2022
ms.locfileid: "8710249"
---
# <a name="budget-funds-available"></a>Rendelkezésre álló költségvetési források

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a témakör bemutatja a rendelkezésre álló költségvetési alapok funkciót, és olyan információkat tartalmaz, amelyek segítséget nyújtnak a költségvetés-ellenőrzésnek a szervezet pénzügyi erőforrásainak kezelésére való konfigurálásában.

## <a name="enhanced-calculation-feature-for-budget-funds-available"></a>Továbbfejlesztett számítási funkció az elérhető költségvetési alapokhoz

A **Rendelkezésre álló költségvetési** **alapok számítási funkció csak a rendelkezésre álló összegek nyomon követésére használható. A dokumentumtípusokhoz és -államokhoz használt, a Költségvetés-ellenőrzési paraméterek megadása lapon megadott beállításoknak megfelelő költségvetés-ellenőrzési táblák nyomon követhetők**.

A költségvetés-ellenőrzés egyes konfigurációs beállításainak meghatározott beállításokkal kell rendelkezik ahhoz, hogy a funkció megfelelően működjön. Ezek a lehetőségek a Költségvetés-ellenőrzési **·** **paraméterek megadása lap Rendelkezésre álló költségvetési alapok lapján választhatók ki vagy törlődnek**. Az alábbi táblázat bemutatja a rendelkezésre álló költségvetési alapok funkcióhoz szükséges beállításokat.

| Ha ez a beállítás be van jelölve | Ezt a beállítást is ki kell választani. |
| ------------------------- | -------------------------------- |
| Költségvetési zárolások az előzetes kötelezettségvállalásokhoz | Költségvetési foglalások a kötelezettségvállaláshoz és *a tényleges* kiadásokhoz |
| Költségvetési zárolások a kötelezettségvállalásokhoz | Tényleges kiadások |
| Költségvetési foglalások a Beszerzési igénylés típusú dokumentumokkal kapcsolatos kötelezettségvállaláshoz | Költségvetési zárolások az előzetes kötelezettségvállalásokhoz |

Ez a funkció csak az új dokumentumokat érinti. A meglévő dokumentumok összegeit a rendszer továbbra is nyomon követi és mutatja a költségvetés-ellenőrzési statisztikai lekérdezésben, amíg a rendelkezésre álló költségvetési alapok beállítása meg nem változik, és az új költségvetés-ellenőrzési konfigurációt aktiválják. Ezen a ponton a rendelkezésre álló költségvetési alapok számításaiból eltávolított dokumentumok költségvetés-követési adatai törlődnek.

Javasoljuk, hogy hagyja a **Fel nem adott tényleges kiadások beállítást**. Ha be van jelölve, a feladatlan dokumentumokon, például a függőben lévő szállítói számlákon időigényes költségvetés-ellenőrzési számítás történik.

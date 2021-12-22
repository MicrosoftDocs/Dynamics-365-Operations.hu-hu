---
title: Rendelkezésre álló költségvetési források
description: Ez a témakör bemutatja a rendelkezésre álló költségvetési alapok funkciót, és olyan információkat tartalmaz, amelyek segítséget nyújtnak a költségvetés-ellenőrzésnek a szervezet pénzügyi erőforrásainak kezelésére való konfigurálásában.
author: rcarlson
ms.date: 11/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetControlConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "60493"
- intro-internal
ms.assetid: be964167-43bc-431d-9adb-48bff32d68d5
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2021-11-28
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: a8279ae9b08c7537548c1c8b71e6e978fee2b8a1
ms.sourcegitcommit: c85eac17fbfbd311288b50664f9e2bae101c1fe6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/03/2021
ms.locfileid: "7891356"
---
# <a name="budget-funds-available"></a>Rendelkezésre álló költségvetési források

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a témakör bemutatja a rendelkezésre álló költségvetési alapok funkciót, és olyan információkat tartalmaz, amelyek segítséget nyújtnak a költségvetés-ellenőrzésnek a szervezet pénzügyi erőforrásainak kezelésére való konfigurálásában.

## <a name="enhanced-calculation-feature-for-budget-funds-available"></a>Továbbfejlesztett számítási funkció az elérhető költségvetési alapokhoz

A Rendelkezésre álló költségvetési alapok számítási funkció csak a rendelkezésre álló összegek nyomon követésére használható. A dokumentumtípusokhoz és -államokhoz használt, a Költségvetés-ellenőrzési paraméterek megadása lapon megadott beállításoknak megfelelő költségvetés-ellenőrzési táblák **nyomon** **követhetők**.

A költségvetés-ellenőrzés egyes konfigurációs beállításainak meghatározott beállításokkal kell rendelkezik ahhoz, hogy a funkció megfelelően működjön. Ezek a lehetőségek a Költségvetés-ellenőrzési paraméterek megadása lap Rendelkezésre álló költségvetési alapok lapján választhatók ki **vagy** **törlődnek**. Az alábbi táblázat bemutatja a rendelkezésre álló költségvetési alapok funkcióhoz szükséges beállításokat.

| Ha ez a beállítás be van jelölve | Ezt a beállítást is ki kell választani. |
| ------------------------- | -------------------------------- |
| Költségvetési zárolások az előzetes kötelezettségvállalásokhoz | Költségvetési foglalások a kötelezettségvállaláshoz és *a* tényleges kiadásokhoz |
| Költségvetési zárolások a kötelezettségvállalásokhoz | Tényleges kiadások |
| Költségvetési foglalások a Beszerzési igénylés típusú dokumentumokkal kapcsolatos kötelezettségvállaláshoz | Költségvetési zárolások az előzetes kötelezettségvállalásokhoz |

Ez a funkció csak az új dokumentumokat érinti. A meglévő dokumentumok összegeit a rendszer továbbra is nyomon követi és mutatja a költségvetés-ellenőrzési statisztikai lekérdezésben, amíg a rendelkezésre álló költségvetési alapok beállítása meg nem változik, és az új költségvetés-ellenőrzési konfigurációt aktiválják. Ezen a ponton a rendelkezésre álló költségvetési alapok számításaiból eltávolított dokumentumok költségvetés-követési adatai törlődnek.

Javasoljuk, hogy hagyja a Fel nem adott **tényleges kiadások** beállítást. Ha be van jelölve, a feladatlan dokumentumokon, például a függőben lévő szállítói számlákon időigényes költségvetés-ellenőrzési számítás történik.

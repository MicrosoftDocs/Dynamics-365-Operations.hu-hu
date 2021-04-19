---
title: Áru minőségének ellenőrzése
description: Ez a cikk a minőségi rendelések feldolgozását ismerteti.
author: perlynne
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 47e7156e5c57d5f983564cc966b4108f1180ff8d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825915"
---
# <a name="inspect-the-quality-of-goods"></a>Áru minőségének ellenőrzése

[!include [banner](../../includes/banner.md)]

Ez a cikk a minőségi rendelések feldolgozását ismerteti. Ezt az útmutatót lefuttathatja az USMF bemutatócégen. A példaeljárás megkezdése előtt erősítse meg a „000016” beszerzési rendelést, és adja fel a termékbevételezést. Ez automatikusan létrehoz egy minőségi rendelést. A minőségvizsgálatokat általában minőségadminisztrátorok végzik.


## <a name="select-a-quality-order"></a>Minőségi rendelés kiválasztása
1. A navigációs ablaktáblán lépjen a **Modulok > Készletgazdálkodás > Időszakos feladatok > Minőségkezelés > Minőségi rendelések** részre.
2. Válassza ki az eljárás megkezdése előtt létrehozott minőségi rendelést.  

## <a name="record-test-results"></a>Teszteredmények rögzítése
1. Válassza az **Eredmények** lehetőséget.
2. Válassza ki a **Szerkesztés** opciót.
3. Az **Eredmény mennyisége** mezőben adjon meg egy számot.
4. Az **Eredmény** mező legördülő mezőjében válassza ki a kívánt rekordot.  
- Ebben a példában az eredményt egy előre meghatározott eredmény alapul. Általában speciálisabb teszteredményeket rögzít majd, például egy méretet vagy más dimenziót.  
5. Válassza a **Mentés** lehetőséget.
6. Zárja be a lapot.

## <a name="validate-the-quality-order"></a>A minőségi rendelés ellenőrzése
1. A **Validálás** kiválasztása.
2. Az **Ellenőrzést végezte** mező legördülő mezőjében válassza ki a vizsgálatot végző felhasználót.  
3. Kattintson a **Kiválasztás** lehetőségre.
4. Válassza ki az **OK** lehetőséget.
5. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
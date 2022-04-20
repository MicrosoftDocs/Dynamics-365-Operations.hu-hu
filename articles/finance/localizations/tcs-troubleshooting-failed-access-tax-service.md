---
title: Nem sikerült hozzáférni az adószolgáltatáshoz
description: Ez a témakör leírja, hogyan lehet elhárítani az adószámítási szolgáltatás elérésének sikertelenségét.
author: hangwan
ms.date: 03/04/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: hangwan
ms.search.validFrom: 02/16/2022
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: f4682b83405071b4ad7647958122ab2b4e082133
ms.sourcegitcommit: 2977e92a76211875421e608555311c363cfbdc25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2022
ms.locfileid: "8612316"
---
# <a name="failed-to-access-tax-service"></a>Nem sikerült hozzáférni az adószolgáltatáshoz

[!include [banner](../includes/banner.md)]


Ez a témakör leírja, hogyan lehet kijavítani az adószámítási szolgáltatás "Nem lehet elérni az adószolgáltatást" hibaüzenetét.

## <a name="symptoms"></a>Tünetek

A Microsoft Dynamics 365 Pénzügyben az Adóbeállítási **adó** \> **·** \> **konfigurációs** \> **adó szolgáltatás paraméterei gombra kell ugrást beállítani.** Az Általános **lapon** lehet engedélyezni az Adószámítás **engedélyezése** beállítást. Ha ezután kiválaszt egy értéket a **Funkcióbeállítás** neve mezőben, hiba történik. A hibaüzenetben a következő szöveg jelenik meg: "Nem sikerült elérni az adószolgáltatást."

## <a name="cause"></a>Ok

Ez a hiba azért fordul elő, mert a Pénzügy nem fér hozzá az Adószámítás szolgáltatáshoz.

## <a name="resolution"></a>Megoldás 

1. Jelentkezzen be a Microsoft Dynamics LifeCycle Services (LCS) szolgáltatásba.
2. Keresse meg **az** Adószámítás **·** **cikket** a Környezet bővítmények lapon, és tekintse át az állapotát. Az állapotnak a telepítésnek vagy **telepítésnek** kell **lennie**. Ha nincs telepítve az Adószámítás szolgáltatás bővítménye, hibaüzenet jelenik meg.

## <a name="mitigation"></a>Kockázatcsökkentés

1. Az LCS rendszer **Pénzügyi lapján,** a Power Platform **integrációja szakaszban válassza** az Új bővítmény telepítése **lehetőséget**.
2. Görgetés a lap aljára, **és** a telepítéshez válassza ki az Adószámítás bővítményt.
3. Térjen vissza a Pénzügyi környezethez, és próbálja meg elérni az Adószámítás szolgáltatást.

> [!NOTE]
> Az Adószámítás szolgáltatás telepítése előtt ellenőrizze az Adószámítási [szolgáltatás előfeltételeit](global-get-started-with-tax-calculation-service.md#prerequisites).
> 
> Ha nem tudja telepíteni a bővítményt **, mert a Power Platform** integrációja szakasz nem érhető el, [tekintse át a bővítmény áttekintését](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Ha a bővítmény telepítése után is hibát észlelt, forduljon a rendszergazdához.

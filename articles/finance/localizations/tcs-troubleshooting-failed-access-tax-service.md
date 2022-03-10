---
title: Nem sikerült elérni az adószolgáltatást.
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
ms.openlocfilehash: 48a75cd0c1d91c3b3d9c3fb2e6cab93a76756532
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2022
ms.locfileid: "8389124"
---
# <a name="failed-to-access-tax-service"></a>Nem sikerült elérni az adószolgáltatást.

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Ez a témakör leírja, hogyan lehet kijavítani az adószámítási szolgáltatás "Nem lehet elérni az adószolgáltatást" hibaüzenetét.

## <a name="symptoms"></a>Tünetek

A Microsoft Dynamics 365 Finance az Adóbeállítási **adó** \> **·** \> **konfigurációs adó szolgáltatás** \> **paramétereinél 2019.** Az Általános **lapon** lehet engedélyezni az Adószámítás **engedélyezése** beállítást. Ha ezután kiválaszt egy értéket a **Funkcióbeállítás** neve mezőben, hiba történik. A hibaüzenetben a következő szöveg jelenik meg: "Nem sikerült elérni az adószolgáltatást."

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

---
title: Meghirdetési típusok és pontozási kritériumok létrehozása az ajánlatkérésekhez
description: Ez az útmutató bemutatja, hogyan hozhat létre meghirdetési típust, és hogyan társíthatja azt pontozási módszerrel.
author: GalynaFedorova
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchRFQSolicitationType, PurchRFQCaseTableListPage, PurchCreateRFQCase, PurchRFQCaseTable, PurchRFQScoringRFQCaseCriteria, PurchRFQScoringCriteriaCopy
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 69d62941629d0b1321a714df5ce6d81c6f94b9f5
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8678659"
---
# <a name="create-solicitation-types-and-scoring-criteria-for-rfqs"></a>Meghirdetési típusok és pontozási kritériumok létrehozása az ajánlatkérésekhez

[!include [banner](../../includes/banner.md)]

Ez az útmutató bemutatja, hogyan hozhat létre meghirdetési típust, és hogyan társíthatja azt pontozási módszerrel. Tárgyalja a meghirdetési típus ajánlatkérésen való használatát is, amely meghatározza az alapértelmezett pontozási módszert. Ezeket a feladatokat jellemzően egy beszerzési vezető végezné el. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja. A kezdéshez rendelkeznie kell egy elérhető pontozási módszerrel.


## <a name="create-a-solicitation-type"></a>Ajánlatkérési típus létrehozása
1. Navigáljon a következő helyre: Beszerzés és forrás > Beállítás > Ajánlatkérés > Meghirdetés típusa.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Név mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. A Pontozási módszer mezőben válassza ki azt a pontozási módszert, amelyet az adott meghirdetési típusnál használni kíván.
6. Kattintson a Mentés gombra.
7. Zárja be a lapot.

## <a name="use-the-solicitation-type"></a>A meghirdetési típus használata
1. Ugorjon a Beszerzés és forrás > Ajánlatkérések > Összes ajánlatkérés pontra.
2. Kattintson az Új lehetőségre.
3. A Meghirdetés típusa mezőjében válassza ki az előzőleg létrehozott meghirdetési típust. 
    *   
4. Kattintson az OK gombra.
5. Kattintson a Pontozási feltételek lehetőségre.
    * Abból a pontozási módszerből jelennek meg a pontozási feltétek, amelyet a meghirdetés típusához társított. Ezen a lapon lehetősége van feltételek hozzáadására vagy törlésére. Új feltételeket más pontozási módszerből való másolással is hozzáadhat.  
6. Kattintson a Feltételek másolása lehetőségre.
7. A Pontozási módszer mezőben adjon meg vagy válasszon ki egy értéket.
8. Kattintson az OK gombra.
9. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
---
title: Munkaidő és jelenlét bérlistafolyamatának engedélyezése
description: Ez az eljárás bemutatja, hogyan lehet engedélyezni a munkaidő és jelenlét bérlistafolyamatát.
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgPayTable, JmgPayRate, JmgPayAgreementTable, JmgPayAgreementLine, HcmWorker
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2df4695b796b4e96e01fe5dac538b344cb76b910
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146721"
---
# <a name="enable-the-payroll-process-for-time-and-attendance"></a>Munkaidő és jelenlét bérlistafolyamatának engedélyezése

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan lehet engedélyezni a munkaidő és jelenlét bérlistafolyamatát. Ez az eljárás az USMF bemutatócéget használja.


## <a name="create-a-pay-type-with-a-related-pay-rate"></a>Új fizetési típus létrehozása kapcsolódó díjalappal
1. Idő és jelenlét > Beállítás > Bérlista > Fizetési típusok
2. Kattintson az Új lehetőségre.
3. Érték beírása a Fizetési típus mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. Kattintson a Mentés gombra.
6. Kattintson a Díjazásokra.
    * A kifizetési típusok különböző díjait meghatározott időintervallumokhoz lehet beállítani, és az egyes alkalmazottakhoz különböző díjazást lehet létrehozni. Nem mindig szükséges a díjakat létrehozni a kifizetési típusokhoz idő és jelenlét tekintetében. Ez az adat már szerepelhet az alkalmazotti bérek létrehozásához használt bérszámfejtő rendszerben.  
7. Kattintson az Új lehetőségre.
8. A listában jelölje meg a kiválasztott sort.
9. Adjon meg egy számot a Díjazás mezőben.
10. Kattintson a Mentés gombra.

## <a name="create-a-pay-agreement"></a>Fizetési megállapodás létrehozása
1. Zárja be a lapot.
2. Zárja be a lapot.
3. Ugrás a Fizetési megállapodásokra.
    * Idő és jelenlét > Beállítás > Kifizetési megállapodások  
4. Kattintson az Új lehetőségre.
5. Érték beírása a Fizetési megállapodás mezőbe.
6. A Leírás mezőben adjon meg egy értéket.
7. Kattintson a Mentés gombra.
8. Kattintson a szerződéssorokra.
9. Kattintson az Új lehetőségre.
10. A listában jelölje meg a kiválasztott sort.
11. A Profiltípus mezőben adjon meg vagy válasszon ki egy értéket.
12. A Kifizetési típus mezőben adjon meg vagy válasszon ki egy értéket.

## <a name="set-up-pay-agreement-for-time-and-registration-worker"></a>Fizetési megállapodás beállítása dolgozói idő és nyilvántartás alapján
1. Zárja be a lapot.
2. Zárja be a lapot.
3. Ugrás az Időnyilvántartás-dolgozókra.
    * Idő és jelenlét > Beállítás > Munkaidő-nyilvántartási dolgozók  
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. Kattintson a Foglalkoztatás lapra.
6. Bontsa ki az Időnyilvántartás szakaszt.
7. Kattintson a Szerkesztés lehetőségre.
8. A Fizetési megállapodás mezőben adjon meg vagy válasszon ki egy értéket.


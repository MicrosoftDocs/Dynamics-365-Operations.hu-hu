---
title: Vállalatközi költségek
description: Egy dolgozó, aki a szervezeten belüli egy jogi személy alkalmazottja, esetenként végezhet munkát az adott szervezeten belüli másik jogi személy számára. Ebben az esetben a vállalatközi költségek funkciót használhatja ahhoz, hogy a dolgozói költségeket hozzárendelje ahhoz a jogi személyhez, amelynek számára a munka el lett végezve.
author: ShylaThompson
manager: AnnBe
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0967f23e4e1f8e0431c55d4d54554e7e90e2451c
ms.sourcegitcommit: 07e425707eb20730f10246a27799f4deeef93f97
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/21/2020
ms.locfileid: "3390884"
---
# <a name="intercompany-expenses"></a>Vállalatközi költségek

[!include [banner](../includes/banner.md)]

Egy dolgozó, aki a szervezeten belüli egy jogi személy alkalmazottja, esetenként végezhet munkát az adott szervezeten belüli másik jogi személy számára. Ebben az esetben a vállalatközi költségek funkciót használhatja ahhoz, hogy a dolgozói költségeket hozzárendelje ahhoz a jogi személyhez, amelynek számára a munka el lett végezve. A dolgozót foglalkoztató jogi személy neve kölcsönbe adó jogi személy. A jogi személy, amelynél a dolgozóval kapcsolatos költségek felmerülnek, a kölcsönbe vevő jogi személy. 

Mielőtt a dolgozó létrehozhatna és benyújthatna költségeket egy másik jogi személynek végrehajtott munkához, a kölcsönbe adó jogi személynél a **Költséggazdálkodási paraméterek** oldalon ki kell válasszalasztani a **Vállalatközi költségsorok engedélyezése** paramétert. 

## <a name="tax-posting-for-intercompany-expenses"></a>Vállalatközi költségek adójának feladása

[!include [banner](../includes/banner.md)]

Ha a kölcsönadó (forrás) jogi személyhez társított adócsoportokat szeretné használni a kölcsönfelvevő (cél) jogi személyé helyett a költségjelentésben, akkor ezt be kell állítania a Főkönyvi forgalmi adójának beállításában. Amikor a Főkönyv **Vállalatközi adó feladásának jogi személye** paramétere a **Forrás** értékre van beállítva és az **Áfaadózási szabályok alkalmazása** beállítás számára a **Nem** érték van megadva, akkor a kölcsönadó jogi személyhez tartozó adózási kombinációt fogja használni a rendszer. Ha ugyanaz a paraméter a **Cél** értékre van állítva, akkor a rendszer a kölcsönfelvevő jogi személyhez tartozó adózási kombinációt fogja használni. Az Egyesült Államokban bejegyzett jogi személyek esetében, ha a paraméter **Forrás** értékre van beállítva, akkor a **Visszaigényelhető áfa** mezőt is az új **Főkönyvi feladási csoportok** lapon kell beállítani. A könyvelési motor az ebből a mezőből származó adatokat fogja használni az adóval kapcsolatos könyvelési bejegyzésekhez.   
A viselkedés összhangban van a projekttel vagy anélkül feladott kiadási sorokkal.  

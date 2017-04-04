---
title: "Fuvarlevél létrehozása"
description: "Ez a témakör ismerteti, hogy hogyan hozhat létre fuvarlevelet a raktárkezelési folyamatok használata közben."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WHSBillOfLading, WHSLoadPlanningWorkbench
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 193583
ms.assetid: 1ad0c1cb-4346-4042-a59b-923115fac03e
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: b88679f1be00d6a7168c8976f0d7db894c7e77fc
ms.lasthandoff: 03/31/2017


---

# <a name="create-a-bill-of-lading"></a>Fuvarlevél létrehozása

Ez a témakör ismerteti, hogy hogyan hozhat létre fuvarlevelet a raktárkezelési folyamatok használata közben.  

A fuvarlevél egy jogi dokumentum a cikkeket leszállító vállalat és a szállítmányozó között. A dokumentum a szállított cikkeket kíséri, és a cikkek célhelyen történő megérkezésekor a kiszáLlítás bizonylataként szolgál. Raktárkezelés használatakor kétféleképpen lehet fuvarlevelet létrehozni:

  -   A jelentés létrehozása manuálisan, a **fuvarlevél** oldalon.
  -   Jelentés készítése a **Rakománytervező munkaterületről**.

Ha a fuvarlevelet a **rakománytervező munkaterületről** hozza létre, a rakomány állapota legyen: **kiszállítva.** Ha a terhelés több részletben, a fuvarlevél minden egyes szállítmányhoz jön létre. Fuvarlevél létrehozása akkor után is módosíthatja azt a a **fuvarlevél** oldalon.

## <a name="master-bill-of-lading"></a>Fő fuvarlevél
Ha egynél több szállítmány tartozik a rakományhoz, akkor létrehozhat egy fő fuvarlevelet. Ennek elrendezése és a rajta szereplő információ megegyezik a fuvarlevéllel, de tartalmazza az összes szállítás összesített tartalmát. Ha a **Hozzon létre fő fuvarlevelet, ha egynél több szállítmány van a rakományban** lehetőség **Igenre** van állítva a **Szállításkezelési paraméterek** lapon, és egynél több szállítmány van, akkor a fő fuvarlevél a fuvarlevél létrehozásakor automatikusan létrejön a **Rakománytervező munkaterületről**. Gombra kattintva a fuvarlevél listáját is kaphat **kapcsolódó információk**&gt;**fuvarlevél**. Ha a fuvarleveleket manuálisan hozza létre, létrehozhat egy fő fuvarlevelet a **Fuvarlevél** oldalon.



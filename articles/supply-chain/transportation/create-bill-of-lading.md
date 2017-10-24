---
title: "Fuvarlevél létrehozása"
description: "Ez a témakör ismerteti, hogy hogyan hozhat létre fuvarlevelet a raktárkezelési folyamatok használata közben."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSBillOfLading, WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 193583
ms.assetid: 1ad0c1cb-4346-4042-a59b-923115fac03e
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b274ff572d2be9a71b91d533023b95be98591e4f
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="create-a-bill-of-lading"></a>Fuvarlevél létrehozása

[!include[banner](../includes/banner.md)]


Ez a témakör ismerteti, hogy hogyan hozhat létre fuvarlevelet a raktárkezelési folyamatok használata közben.  

A fuvarlevél egy jogi dokumentum a cikkeket leszállító vállalat és a szállítmányozó között. A dokumentum a szállított cikkeket kíséri, és a cikkek célhelyen történő megérkezésekor a kiszáLlítás bizonylataként szolgál. Raktárkezelés használatakor kétféleképpen lehet fuvarlevelet létrehozni:

  -   A jelentés létrehozása manuálisan, a **fuvarlevél** oldalon.
  -   Jelentés készítése a **Rakománytervező munkaterületről**.

Ha a fuvarlevelet a **rakománytervező munkaterületről** hozza létre, a rakomány állapota legyen: **kiszállítva.** Ha egynél több szállítmány szerepel a rakományban, a fuvarlevél minden egyes szállítmányhoz létrejön. Fuvarlevél létrehozását követően módosíthatja azt a **Fuvarlevél** oldalon.

## <a name="master-bill-of-lading"></a>Fő fuvarlevél
Ha egynél több szállítmány tartozik a rakományhoz, akkor létrehozhat egy fő fuvarlevelet. Ennek elrendezése és a rajta szereplő információ megegyezik a fuvarlevéllel, de tartalmazza az összes szállítás összesített tartalmát. Ha a **Hozzon létre fő fuvarlevelet, ha egynél több szállítmány van a rakományban** lehetőség **Igenre** van állítva a **Szállításkezelési paraméterek** lapon, és egynél több szállítmány van, akkor a fő fuvarlevél a fuvarlevél létrehozásakor automatikusan létrejön a **Rakománytervező munkaterületről**. Elérheti a fuvarlevelek listáját a következő lehetőségekre kattintva: **Kapcsolódó információk** &gt; **Fuvarlevél**. Ha a fuvarleveleket manuálisan hozza létre, létrehozhat egy fő fuvarlevelet a **Fuvarlevél** oldalon.





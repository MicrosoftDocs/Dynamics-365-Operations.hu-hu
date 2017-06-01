---
title: "Készletállapotok"
description: "A cikk leírja hogyan alkalmazza a készletállapotokat a készlet nyomon követésének és kategorizálásának érdekében."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, WHSInventStatus
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 21331
ms.assetid: b35f495f-de4f-48a0-9d09-4d06781d7650
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 1565b7738260270a986b515dfd21931296ce83bd
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="inventory-statuses"></a>Készletállapotok

[!include[banner](../includes/banner.md)]


A cikk leírja hogyan alkalmazza a készletállapotokat a készlet nyomon követésének és kategorizálásának érdekében.

A készletállapotok a készlet csoportosítására használhatók. Ezután a elindíthatja a szükséges műveleteket, például a feltöltést vagy betárolási munkát. 

Íme néhány példa készletállapotok használatára:

-   Készletállapotok létrehozása aktuális készlethez, bejövő és kimenő tranzakciókhoz.
-   Adjon meg egy alapértelmezett készletállapot a raktár tranzakciókhoz.
-   Cikkek készletállapotának módosítása érkezés előtt, érkezés során, vagy a cikkek készletmozgással történő betárolása során.
-   Használhat készletállapotot a visszárucikkek árképzéséhez, illetve a cikkfedezet megtervezéséhez az alaptervezés folyamatában.

A készletállapot a tárolásidimenzió-csoport dimenziói közé tartozik. Készletállapotok kategóriája lehet elérhető vagy nem elérhető, és használhatja a **Készletzárolás** paramétert a nem elérhető állapotú cikkek blokkolására. A zárolt állapotú cikkek tényleges készletnek tekinthetők, és nem használhatók termelési rendelésben, értékesítési rendelésben, átmozgatási rendelésben vagy kimenő tranzakcióban. 

Bejövő munkához elérhető vagy nem elérhető készletállapotú cikkeket is használhat. Például létrehozhat egy elérhető állapotot, amely neve **Kész**, nem elérhető állapotot, amely neve **Sérült**, és zárolt állapotot, amely neve **Zárolva**. Bevételezett, vagy visszaküldött cikkek beszerzési rendelésének létrehozásakor, ha a cikkek megsérültek vagy eltörtek, a készlet állapotát módosíthatja **Sérült**értékre a beszerzési rendelésen. A cikkek bevételezése után, az állapot értéke automatikusan **Zárolva**. Ha mobileszköz használatával olvas be a sérült cikkeket, a Microsoft Dynamics 365 for Operations rendszer használhat helyutasításokat és munkasablonokat, hogy mutassa a megfelelő helyet és helytartományokat, ahova be lehet tárolni azokat a cikkeket. Visszaküldött cikkekhez **Foglalás** kiadástpus jön létre a **Készlettranzakciók** oldalon. 

Kimenő munka esetén mindig elérhető készletállapotú cikkeket használjon. Ha **Törött** állapotú cikkekkel futtat alaptervezést, a rendszer hiányzónak fogja tekinteni őket, és automatikusan feltölti a készletet. 

Készletállapotok létrehozása után beállíthatja, hogy ez legyen az alapértelmezett készletállapot egy adott telephelyre, cikkre vagy raktárra vonatkozóan. Értékesítéshez, átadáshoz és beszerzési rendeléshez is létrehozhat alapértelmezett állapotot. Az értékesítési rendelések és a kimenő átmozgatási rendelések esetén a **Készletzárolás** alapértelmezett állapota nem lehet **Igen**. A raktár, cikk, beszerzési rendelés, átmozgatási rendelés vagy értékesítési rendelés alapértelmezett beállításaiból örökölt készletállapotot a mobileszköz, beszerzési rendelés, értékesítési rendelés, vagy átmozgatási rendelés sor segítségével lehet módosítani. 

Rendelkezésre álló készlet állapotú cikkek fedezeti tervének elkészítéséhez jelölje be a **Fedezeti terv dimenziónként** lehetőséget tárolási dimenziónak, a **Tárolási dimenziócsoportok** oldalon. A **Cikkfedezet**varázsló megnyitásakor, az elérhető állapotú cikkek jelenjenek meg az **Állapot** oldalon. A cikkekre vonatkozó fedezeti beállítások létrehozásához válassza ki a készletállapot azonosítóját a rendelkezésre álló készletállapotok közül. A fedezeti beállítások alapján számíthatja ki a cikkszükségletet és jelezheti előre az elérhető cikkekre vonatkozó kínálatot és kereslete az alaptervezés során. Zárolt készletállapottal nem lehet cikkfedezeti beállítás létrehozni. A cikkfedezeti paraméterek létrehozásához vagy módosításához használhatja az **Cikk fedezete** képernyőt is.





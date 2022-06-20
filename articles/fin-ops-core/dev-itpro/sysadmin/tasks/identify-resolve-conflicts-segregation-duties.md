---
title: Feladatkörök szétválasztásával kapcsolatos ütközések azonosítása és feloldása
description: Ez a cikk bemutatja, hogy hogyan lehet azonosítani és megoldani a feladatkörök szétválasztásának ütközéseit.
author: peakerbl
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesConflict, SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fd36db5df2b6871d410bb1feaae825909ec9b3ff
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883477"
---
# <a name="identify-and-resolve-conflicts-in-segregation-of-duties"></a>Feladatkörök szétválasztásával kapcsolatos ütközések azonosítása és feloldása

[!include [banner](../../includes/banner.md)]

Ez a cikk bemutatja, hogy hogyan lehet azonosítani és megoldani a feladatkörök szétválasztásának ütközéseit. Beállíthat szabályokat a más felhasználók által elvégzendő feladatok elválasztásához. Ezt a fogalmat a feladatkörök szétválasztásának nevezzük. Ha a biztonsági szerepkör definíciója vagy a felhasználói szerepkör-hozzárendelés megszegi a szabályokat, a rendszer naplózza az ütközést. Az ütközéseket a rendszergazdának kell feloldania. Kövesse az alábbi lépéseket az ütközések azonosítása és megoldása érdekében.

A szabály hozzáadása után ellenőrizze, hogy az összes meglévő szerepkör megfelelő-e. 

## <a name="verify-that-existing-roles-and-duties-comply-with-new-rules-for-segregation-of-duties"></a>Ellenőrizze, hogy a meglévő szerepkörök és feladatok megfelelnek-e a feladatkörök szétválasztására vonatkozó új szabályoknak
1. Ugrás a **Rendszerfelügyelet** > **Biztonság** > **Feladatkörök szétválasztása** > **Feladatkör-szétválasztási szabályok** elemre.
3. Válassza a **Feladatkörök és szerepkörök érvényesítése** lehetőséget. Ha valamely szerepkör sérti a szabályokat, egy üzenet jelenik meg, amely tartalmazza a szabályt, a szerepkör nevét és az ütköző feladatok nevét. Az ütköző szerepköröket módosítani kell a **Biztonsági konfiguráció** használatával, és nem tartalmazhatnak ütköző feladatokat. Ha nincs olyan szerepkör, amely sérti a kiválasztott szabályt, egy üzenet jelzi, hogy minden szerepkör megfelel.   

> [!NOTE]
> Az érvényesítés csak a kiválasztott szabályra kerül végrehajtásra. A megfelelést fontos ellenőrizni minden szabály esetén.   

Szerepkör létrehozásakor vagy módosításakor a feladatkörök szétválasztására vonatkozó szabályok automatikusan ki vannak kényszerítve. Nem rendelhet hozzá ütköző feladatokat egy szerepkörhöz.

Ezután ellenőrizze, hogy minden meglévő szerepkör-hozzárendelés megfelelő-e.

## <a name="verify-that-user-role-assignments-comply-with-new-rules-for-segregation-of-duties"></a>Ellenőrizze, hogy a felhasználói szerepkör-hozzárendelések megfelelnek-e a feladatkörök szétválasztására vonatkozó új szabályoknak
1. Ugrás a **Rendszerfelügyelet > Biztonság > Feladatkörök szétválasztása > Felhasználók szerepkörökhöz rendelésének megfelelőségi ellenőrzése** elemre.
2. Válassza ki az **OK** lehetőséget. Egy értesítés megjeleníti az ellenőrzés eredményeit. A rendszer a **Feladatkörök szétválasztásának feloldatlan ütközései** lapon is naplózza az ütközéseket.   

Felhasználók szerepkörökhöz rendelésekor a feladatkörök szétválasztására vonatkozó szabályok automatikusan ki vannak kényszerítve. Ha ütköző feladatokat tartalmazó szerepkörökhöz próbál hozzárendelni egy felhasználót, hibaüzenetet kap. Ezt követően úgy kell feloldani az ütközést, hogy megtagadja vagy engedélyezi a további szerepkör-hozzárendelést. A további szerepkör a hozzárendelés engedélyezése után rendelhető hozzá a felhasználóhoz. 

> [!NOTE]
> A rendszer jelenleg nem ellenőrzi az ütközéseket az Active Directory-tartománycsoportok alapján szerepkörhöz rendelt felhasználók esetében.

## <a name="view-and-resolve-conflicting-user-role-assignments"></a>Az ütköző felhasználói szerepkör-hozzárendelések megtekintése
1. Ugrás a **Rendszerfelügyelet** > **Biztonság** > **Feladatkörök szétválasztása** > **Feladatkör-szétválasztási feloldatlan ütközések** elemre. 
2. Válasszon ki egy ütközést, majd válassza ki a következő műveletek egyikét: 

  - **Hozzárendelés megtagadása**: Ez megtagadja a hozzárendelést a felhasználó számára a további biztonsági szerepkörre vonatkozóan. Ha megtagad egy automatikus szerepkör-hozzárendelést, a felhasználót a rendszer kizárja a szerepkörből. A kizárt felhasználó nem rendelkezik majd a szerepkörhöz társított hozzáféréssel, és a felhasználót nem lehet hozzárendelni a szerepkörhöz mindaddig, amíg a rendszergazda törli a kizárást. 
-  **Hozzárendelés engedélyezése** – Felülbírálja az ütközést, és engedélyezi a felhasználó további biztonsági szerepkörhöz való hozzárendelését. Ha felülbírál egy ütközést, a **Felülbírálás oka** mezőt is ki kell töltenie. Minden felülbírált szerepkör-hozzárendelés áttekinthető a **Feladatkör-szétválasztási ütközések** oldalon.  

> [!NOTE]
> Ha ugyanannak a felhasználónak több ütközése van, jelölje ki a felhasználói rekordot, és értékelje ki a hozzárendelt szerepköröket a **Felhasználók** oldalon. Az ütközés elkerülése érdekében a szabályok hozzáadása vagy módosítása után ellenőrizze őket.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
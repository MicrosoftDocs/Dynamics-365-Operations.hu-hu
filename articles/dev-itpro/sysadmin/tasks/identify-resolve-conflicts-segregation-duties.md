--- 
title: "Feladatkörök szétválasztásával kapcsolatos ütközések azonosítása és feloldása"
description: "Beállíthat szabályokat a más felhasználók által elvégzendő feladatok elválasztásához."
author: maertenm
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c3a366ea4b558ba4e4af7336992dbb091b0b1414
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="identify-and-resolve-conflicts-in-segregation-of-duties"></a>Feladatkörök szétválasztásával kapcsolatos ütközések azonosítása és feloldása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Beállíthat szabályokat a más felhasználók által elvégzendő feladatok elválasztásához. Ezt a fogalmat a feladatkörök szétválasztásának nevezzük. Ha a biztonsági szerepkör definíciója vagy a felhasználói szerepkör-hozzárendelés megszegi a szabályokat, a rendszer naplózza az ütközést. Az ütközéseket a rendszergazdának kell feloldania. Kövesse az alábbi lépéseket az ütközések azonosítása és megoldása érdekében. Ez az eljárás az USMF bemutatócéget használja.


## <a name="verify-whether-user-role-assignments-comply-with-new-rules-for-segregation-of-duties"></a>Ellenőrizze, hogy a felhasználói szerepkör-hozzárendelések megfelelnek-e a feladatkörök szétválasztására vonatkozó új szabályoknak.
1. Ugrás a Rendszerfelügyelet > Biztonság > Feladatkörök szétválasztása > Felhasználók szerepkörökhöz rendelésének megfelelőségi ellenőrzése elemre.
2. Kattintson az OK gombra.
    * Egy értesítés megjeleníti az ellenőrzés eredményeit.     Ha ütközés van, nyissa meg a Felhasználók lapot és módosítsa a felhasználói szerepkör-hozzárendeléseket. Az ütközéseket a Feladatkörök szétválasztásával kapcsolatos ütközések című oldalon is naplózza a rendszer.     Ha az ellenőrzési folyamatot kötegelt feladatként szeretné futtatni, jelölje be a kötegelt feldolgozást, és adja meg a kötegelt feladat paramétereit. A kötegelt feladat futtatása után az ütközést a Feladatkörök szétválasztási ütközése lapon tekintheti meg.  

## <a name="view-and-resolve-conflicting-user-role-assignments"></a>Az ütköző felhasználói szerepkör-hozzárendelések megtekintése
1. Ugrás a Rendszerfelügyelet > Biztonság > Feladatkörök szétválasztása > Feladatkör-szétválasztási ütközések elemre.
    * Jelöljön ki egy ütközést, és kattintson a következő gombok egyikére: Hozzárendelés megtagadása – Hozzárendelés megtagadása a felhasználó számára további biztonsági szerepkörre vonatkozóan. Ha megtagad egy automatikus szerepkör-hozzárendelést, a felhasználót a rendszer kizárja a szerepkörből. A kizárt felhasználó nem rendelkezik majd a szerepkörhöz társított hozzáféréssel, és a felhasználót nem lehet hozzárendelni a szerepkörhöz mindaddig, amíg a rendszergazda törli a kizárást.     Hozzárendelés engedélyezése – Felülbírálja az ütközést, és engedélyezi a felhasználó számára a biztonsági szerepkörökhöz való hozzárendelést. Egy ütközés felülbírálásakor a Felülbírálás oka nevű mezőt ki kell töltenie.  
2. Zárja be a lapot.
3. Ugrás a Rendszerfelügyelet > Biztonság > Feladatkörök szétválasztása > Feladatkör-szétválasztási feloldatlan ütközések elemre.
    * Jelöljön ki egy ütközést, és kattintson a következő gombok egyikére: Hozzárendelés megtagadása – Hozzárendelés megtagadása a felhasználó számára további biztonsági szerepkörre vonatkozóan. Ha megtagad egy automatikus szerepkör-hozzárendelést, a felhasználót a rendszer kizárja a szerepkörből. A kizárt felhasználó nem rendelkezik majd a szerepkörhöz társított hozzáféréssel, és a felhasználót nem lehet hozzárendelni a szerepkörhöz mindaddig, amíg a rendszergazda törli a kizárást.     Hozzárendelés engedélyezése – Felülbírálja az ütközést, és engedélyezi a felhasználó számára a biztonsági szerepkörökhöz való hozzárendelést. Egy ütközés felülbírálásakor a Felülbírálás oka nevű mezőt ki kell töltenie.    
4. Zárja be a lapot.

## <a name="verify-whether-existing-roles-comply-with-new-rules-for-segregation-of-duties"></a>Ellenőrizze, hogy a meglévő szerepkörök megfelelnek-e a feladatkörök szétválasztására vonatkozó új szabályoknak.
1. Ugrás a Rendszerfelügyelet > Biztonság > Feladatkörök szétválasztása > Feladatkör-szétválasztási szabályok elemre.
    * Válasszon ki egy szabályt.  
2. Kattintson a Feladatkörök és szerepkörök érvényesítése elemre.
    * Ha valamely meglévő szerepkör sérti a kiválasztott szabályt, egy üzenet jelenik meg, amely tartalmazza a szerepkör nevét és az ütköző feladatok nevét. A rendszergazdának meg kell adnia vagy a biztonsági kockázat mérséklését, vagy módosítania kell a szerepkört, hogy az ne sértse a feladatkörök szétválasztására vonatkozó szabályokat.     Ha nincs olyan szerepkör, amely sérti a kiválasztott szabályt, egy üzenet jelzi, hogy minden szerepkör megfelel.  



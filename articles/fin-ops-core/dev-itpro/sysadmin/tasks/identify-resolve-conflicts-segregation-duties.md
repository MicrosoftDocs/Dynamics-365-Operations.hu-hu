---
title: Feladatkörök szétválasztásával kapcsolatos ütközések azonosítása és feloldása
description: Ez a cikk a feladatkörök szétválasztásával kapcsolatos ütközések azonosítását és feloldását ismerteti.
author: maertenm
manager: AnnBe
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesConflict, SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 70fe3bb707f2f204cda92ec979fe9fe1a3b96bac
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143604"
---
# <a name="identify-and-resolve-conflicts-in-segregation-of-duties"></a>Feladatkörök szétválasztásával kapcsolatos ütközések azonosítása és feloldása

[!include [banner](../../includes/banner.md)]

Ez a cikk a feladatkörök szétválasztásával kapcsolatos ütközések azonosítását és feloldását ismerteti. Beállíthat szabályokat a más felhasználók által elvégzendő feladatok elválasztásához. Ezt a fogalmat a feladatkörök szétválasztásának nevezzük. Ha a biztonsági szerepkör definíciója vagy a felhasználói szerepkör-hozzárendelés megszegi a szabályokat, a rendszer naplózza az ütközést. Az ütközéseket a rendszergazdának kell feloldania. Kövesse az alábbi lépéseket az ütközések azonosítása és megoldása érdekében. Ez az eljárás az USMF bemutatócéget használja.


## <a name="verify-whether-user-role-assignments-comply-with-new-rules-for-segregation-of-duties"></a>Ellenőrizze, hogy a felhasználói szerepkör-hozzárendelések megfelelnek-e a feladatkörök szétválasztására vonatkozó új szabályoknak.
1. Lépjen a **Navigációs ablaktábla > Modulok > Rendszerfelügyelet > Biztonság > Feladatkörök szétválasztása > Felhasználók szerepkörökhöz rendelésének megfelelőségi ellenőrzése** részre.
2. Válassza ki az **OK** lehetőséget. Egy értesítés megjeleníti az ellenőrzés eredményeit. Ha ütközés van, a **Felhasználók** lapon módosítsa a felhasználói szerepkörök hozzárendelését. A rendszer a **Feladatköri ütközések szétválasztása** lapon is naplózza az ütközéseket. Az ellenőrzés kötegelt feladatként való futtatásához válassza a **Kötegelt feldolgozás** lehetőséget, és adja meg a többi kötegparamétert. A kötegelt feladat lefutása után a **Feladatköri ütközések szétválasztása** tekintheti át az ütközéseket.  

## <a name="view-and-resolve-conflicting-user-role-assignments"></a>Az ütköző felhasználói szerepkör-hozzárendelések megtekintése
1. Lépjen a **Navigációs ablaktábla > Modulok > Rendszerfelügyelet > Biztonság > Feladatkörök szétválasztása > Feladatköri ütközések szétválasztása** részre. Válasszon ki egy ütközést, és kattintson a következő gombok egyikére: **Hozzárendelés megtagadása – A felhasználó további biztonsági szerepkörökhöz való hozzárendelésének megtagadása**. Ha megtagad egy automatikus szerepkör-hozzárendelést, a felhasználót a rendszer kizárja a szerepkörből. A kizárt felhasználó nem rendelkezik majd a szerepkörhöz társított hozzáféréssel, és a felhasználót nem lehet hozzárendelni a szerepkörhöz mindaddig, amíg a rendszergazda törli a kizárást. Hozzárendelés engedélyezése – **Felülbírálja** az ütközést, és engedélyezi a felhasználó mindkét biztonsági szerepkörhöz való hozzárendelését. Ha felülbírál egy ütközést, a **Felülbírálás oka** mezőt is ki kell töltenie.  
2. Zárja be a lapot.
3. Lépjen a **Navigációs ablaktábla > Modulok > Rendszerfelügyelet > Biztonság > Feladatkörök szétválasztása > Feladatkörök szétválasztásának feloldatlan ütközései** részre. Válasszon ki egy ütközést, és kattintson a következő gombok egyikére: **Hozzárendelés megtagadása – A felhasználó további biztonsági szerepkörökhöz való hozzárendelésének megtagadása**. Ha megtagad egy automatikus szerepkör-hozzárendelést, a felhasználót a rendszer kizárja a szerepkörből. A kizárt felhasználó nem rendelkezik majd a szerepkörhöz társított hozzáféréssel, és a felhasználót nem lehet hozzárendelni a szerepkörhöz mindaddig, amíg a rendszergazda törli a kizárást. Hozzárendelés engedélyezése – **Felülbírálja** az ütközést, és engedélyezi a felhasználó mindkét biztonsági szerepkörhöz való hozzárendelését. Ha felülbírál egy ütközést, a **Felülbírálás oka** mezőt is ki kell töltenie.    
4. Zárja be a lapot.

## <a name="verify-whether-existing-roles-comply-with-new-rules-for-segregation-of-duties"></a>Ellenőrizze, hogy a meglévő szerepkörök megfelelnek-e a feladatkörök szétválasztására vonatkozó új szabályoknak.
1. Lépjen a **Navigációs ablaktábla > Modulok > Rendszerfelügyelet > Biztonság > Feladatkörök szétválasztása > Feladatkörök szétválasztási szabályai** részre. Válasszon ki egy szabályt.  
2. Válassza a **Feladatkörök és szerepkörök érvényesítése** lehetőséget. Ha valamely meglévő szerepkör sérti a kiválasztott szabályt, egy üzenet jelenik meg, amely tartalmazza a szerepkör nevét és az ütköző feladatok nevét. A rendszergazdának meg kell adnia vagy a biztonsági kockázat mérséklését, vagy módosítania kell a szerepkört, hogy az ne sértse a feladatkörök szétválasztására vonatkozó szabályokat. Ha nincs olyan szerepkör, amely sérti a kiválasztott szabályt, egy üzenet jelzi, hogy minden szerepkör megfelel.  


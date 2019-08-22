---
title: Felhasználók hozzárendelése a biztonsági szerepkörökhöz
description: A Microsoft Dynamics 365 for Finance and Operations, Enterprise kiadás eléréséhez hozzá kell rendelni a felhasználókat a biztonsági szerepkörökhöz.
author: maertenm
manager: AnnBe
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4c0afd0f5754e59307a82af9c9700b36c31edcc4
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/02/2019
ms.locfileid: "1851359"
---
# <a name="assign-users-to-security-roles"></a>Felhasználók hozzárendelése a biztonsági szerepkörökhöz

[!include [task guide banner](../../includes/task-guide-banner.md)]

A Microsoft Dynamics 365 for Finance and Operations, Enterprise kiadás eléréséhez hozzá kell rendelni a felhasználókat a biztonsági szerepkörökhöz. Ez az eljárás bemutatja, hogy hogyan lehet hozzárendelni automatikusan a szerepkörökhöz az üzleti adatokon alapuló rendszergazdákat. Ez az eljárás az USMF bemutatócéget használja.


## <a name="automatically-assign-users-to-roles"></a>Felhasználók automatikus hozzárendelése a szerepkörökhöz
1. Ugorjon a **Navigációs lap > Modulok > Rendszerfelügyelet > Biztonság > Felhasználók szerepkörökhöz rendelése** pontra.
2. Válassza ki a fastruktúrában a „Számviteli felügyelő” lehetőséget. Válassza ki azt a szerepkört, amelyre vonatkozóan konfigurálni kívánja a szabályt. Ebben a példában válassza ki a Számviteli felügyelő lehetőséget. 
3. Kattintson a **Szabály hozzáadása** lehetőségre a legördülő párbeszédpanel megnyitásához.
4. A kívánt rekord megkeresése és kijelölése a **Lekérdezés kiválasztása** listában. Válassza ki a lekérdezést ezen szabály használatához.  
5. A **Tagsági szabály neve** listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Kattintson a **Lekérdezés szerkesztése** elemre. Igény szerint módosítsa a lekérdezést.  
7. Kattintson az **OK** gombra.

## <a name="exclude-users-from-automatic-role-assignment"></a>A felhasználók kizárása az Automatikus szerepkör-hozzárendelésből
1. Zárja be a lapot.
2. Ugorjon a **Navigációs lap > Modulok > Rendszerfelügyelet > Biztonság > Felhasználók szerepkörökhöz rendelése** pontra.
3. Válassza ki a fastruktúrában a „Számviteli felügyelő” lehetőséget. Szerepkör választása. Például, válassza ki a Számviteli felügyelő lehetőséget.  
4. A **Szerepkörhöz rendelt felhasználók** menüben válassza ki a **Felhasználók manuális hozzárendelését/kizárását**.
5. A **Felhasználók szerepkörhöz rendelése vagy kizárása onnan** listában jelölje meg a kiválasztott sorokat. Felhasználó kiválasztása  
6. A **Műveleti ablaktáblán** kattintson a **Kizárás szerepkörből** elemre.
    
    Kattintson a **Kizárás szerepkörből** lehetőségre a kiválasztott felhasználók szerepkörből történő kizárásához. A kivételek eltávolításához jelölje ki azokat a felhasználókat, akikre vonatkozóan el szeretné távolítani a kizárásokat, majd ezt követően kattintson az **Állapot visszaállítása** lehetőségre. Amikor eltávolít egy kizárást a felhasználói állapot visszaállításával, a rendszer ismét automatikusan hozzárendeli a felhasználó szerepkört. Azonban a rendszer a felhasználót nem rendeli hozzá automatikusan a szerepkörhöz és kizárja a szerepkörből, amikor a rendszer visszaállítja az állapotát. A rendszer ehelyett a felhasználót vagy hozzárendeli a szerepkörhöz vagy eltávolítja a szerepkörből a következő alkalommal, hogy az automatikus szerepkör-hozzárendelési szabályokat futtassa a rendszer.  

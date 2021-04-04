---
title: Felhasználók hozzárendelése a biztonsági szerepkörökhöz
description: A Finance and Operations alkalmazások eléréséhez hozzá kell rendelni a felhasználókat a biztonsági szerepkörökhöz.
author: Peakerbl
manager: AnnBe
ms.date: 05/06/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1a6d904ae3df23dd1c602cfdfecc40411aba5724
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569874"
---
# <a name="assign-users-to-security-roles"></a>Felhasználók hozzárendelése a biztonsági szerepkörökhöz

[!include [banner](../../includes/banner.md)]

Az általános képességeken túl más képességek használatához a Finance and Operations alkalmazásokban felhasználóknak biztonsági szerepkörökhöz kell lenniük társítva. A felhasználókat automatikusan, a szabályok és az üzleti adatok alapján rendelheti hozzá a szerepkörökhöz, kizárhatja a felhasználókat az automatikus szerepkör-hozzárendelésből, vagy manuálisan is hozzáadhat felhasználókat a szerepkörökhöz.

## <a name="automatically-assign-users-to-roles"></a>Felhasználók automatikus hozzárendelése a szerepkörökhöz
Ez az eljárás bemutatja, hogy hogyan lehet hozzárendelni automatikusan a szerepkörökhöz az üzleti adatokon alapuló rendszergazdákat. 
1. Ugorjon a **Navigációs lap > Modulok > Rendszerfelügyelet > Biztonság > Felhasználók szerepkörökhöz rendelése** pontra.
2. Válassza ki a fastruktúrában a „Számviteli felügyelő” lehetőséget. Válassza ki azt a szerepkört, amelyre vonatkozóan konfigurálni kívánja a szabályt. Ebben a példában válassza ki a Számviteli felügyelő lehetőséget. 
3. Válassza a **Szabály hozzáadása** lehetőséget a párbeszédmenü megnyitásához.
4. Keresse meg és jelölje ki a kívánt rekordot a **Lekérdezés kiválasztása** listában. Válassza ki a lekérdezést ezen szabály használatához.  
5. A **Tagsági szabály neve** listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Válassza ki a **Lekérdezés szerkesztése** lehetőséget. Igény szerint módosítsa a lekérdezést.  
7. Válassza ki az **OK** lehetőséget.
8. Válassza az **Automatikus szerepkör-hozzárendelés futtatása** elemet.
9. Lépjen a **Navigációs ablaktábla > Modulok > Rendszerfelügyelet > Felhasználók > Felhasználók** részre (lehetőleg másik böngészőlapon).
10. Tekintse át a különböző felhasználókhoz rendelt szerepköröket, és győződjön meg arról, hogy a szerepkör-hozzárendelési lekérdezés helyes volt. Szükség esetén módosítsa, majd futtassa újra.

## <a name="exclude-users-from-automatic-role-assignment"></a>A felhasználók kizárása az Automatikus szerepkör-hozzárendelésből
1. Zárja be a lapot.
2. Ugorjon a **Navigációs lap > Modulok > Rendszerfelügyelet > Biztonság > Felhasználók szerepkörökhöz rendelése** pontra.
3. Válassza ki a fastruktúrában a „Számviteli felügyelő” lehetőséget. Szerepkör választása. Például, válassza ki a Számviteli felügyelő lehetőséget.  
4. A **Szerepkörhöz rendelt felhasználók** menüben válassza ki a **Felhasználók manuális hozzárendelését/kizárását**.
5. A **Felhasználók szerepkörhöz rendelése vagy kizárása onnan** listában jelölje meg a kiválasztott sorokat. Felhasználó kiválasztása  
6. A **Műveleti ablaktáblán** kattintson a **Kizárás szerepkörből** elemre.
7. Válassza a **Kizárás szerepkörből** lehetőséget a kiválasztott felhasználók szerepkörből történő kizárásához. A kivételek eltávolításához jelölje ki azokat a felhasználókat, akikre vonatkozóan el szeretné távolítani a kizárásokat, majd ezt követően kattintson az **Állapot visszaállítása** lehetőségre. Amikor eltávolít egy kizárást a felhasználói állapot visszaállításával, a rendszer automatikusan hozzárendeli a felhasználó szerepkört. Azonban a rendszer a felhasználót nem rendeli hozzá automatikusan a szerepkörhöz és kizárja a szerepkörből, amikor a rendszer visszaállítja az állapotát. A rendszer ehelyett a felhasználót vagy hozzárendeli a szerepkörhöz vagy eltávolítja a szerepkörből a következő alkalommal, hogy az automatikus szerepkör-hozzárendelési szabályokat futtassa a rendszer.  

## <a name="manually-assign-users-to-roles"></a>Felhasználók manuális hozzárendelése szerepkörökhöz
A biztonsági szerepkörökhöz manuálisan hozzárendelt felhasználókat a rendszergazdának is manuálisan kell eltávolítaniuk. Ezeket a felhasználókat nem távolítja el a rendszer a szerepkörökből az automatikus szerepkör-hozzárendelés szabályai alapján.

1. Ugorjon a **Navigációs lap > Modulok > Rendszerfelügyelet > Biztonság > Felhasználók szerepkörökhöz rendelése** pontra.
2. A fán válasszon ki egy szerepkört, és a **Szerepkörhöz rendelt felhasználók** menüben válassza ki a **Felhasználók manuális hozzárendelését/kizárását**.
4. A **Felhasználók szerepkörhöz rendelése vagy kizárása onnan** helyen azok a felhasználók, akik nincsenek hozzárendelve a szerepkörhöz **Hozzárendelési mód** értéke **Nincs**. Jelöljön ki egy vagy több felhasználót, akit társítani kell a szerepkörhöz.
5. A **Műveleti ablaktáblán** válassza a **Hozzárendelés szerepkörhöz** lehetőséget. A **Hozzárendelési módot** a program **Manuális** értékre frissíti, és a felhasználókhoz egy új szerepkör van hozzárendelve.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
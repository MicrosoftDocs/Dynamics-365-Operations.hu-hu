---
title: Felhasználók hozzárendelése biztonsági szerepkörökhöz
description: A pénzügyi és műveleti alkalmazások eléréséhez a felhasználókat hozzá kell rendelni a biztonsági szerepkörökhöz.
author: Peakerbl
ms.date: 02/09/2022
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
ms.openlocfilehash: b5e69a79f123daff3f85d0100647615ad818288e
ms.sourcegitcommit: 12b3dbee905f8b2eb2e6c383c822a0fc9fccf063
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2022
ms.locfileid: "9103868"
---
# <a name="manage-users-and-security-roles"></a>Felhasználók és biztonsági szerepkörök kezelése

[!include [banner](../../includes/banner.md)]

Ahhoz, hogy a pénzügyek és műveletek alkalmazásában a gyakori lehetőségeken kívül más funkciókat is használni tud, a felhasználókat hozzá kell rendelni a biztonsági szerepkörökhöz. A felhasználókat automatikusan, a szabályok és az üzleti adatok alapján rendelheti hozzá a szerepkörökhöz, kizárhatja a felhasználókat az automatikus szerepkör-hozzárendelésből, vagy manuálisan is hozzáadhat felhasználókat a szerepkörökhöz.

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
Ez az eljárás bemutatja, hogyan lehet kizárni felhasználókat az automatikus szerepkör-hozzárendelésből.

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

## <a name="manually-remove-users-from-roles"></a>Felhasználók manuális eltávolítása a szerepkörökből
A biztonsági szerepkörökhöz manuálisan hozzárendelt felhasználókat a rendszergazdának is manuálisan kell eltávolítaniuk. Ezeket a felhasználókat nem távolítja el a rendszer a szerepkörökből az automatikus szerepkör-hozzárendelés szabályai alapján.

1. Ugorjon a **Navigációs lap > Modulok > Rendszerfelügyelet > Biztonság > Felhasználók szerepkörökhöz rendelése** pontra.
2. Egy felhasználó eltávolításához hajtsa végre a következő lépéseket:
   1. Válasszon szerepkört a fán. 
   2. Válassza ki **a szerepkörterülethez hozzárendelt** felhasználók közül azt a felhasználót, akitől el kell távolítani.
   3. Válassza az **Eltávolítás** lehetőséget, és a rendszer eltávolítja a felhasználót a szerepkörből.
3. Ha több felhasználót szeretne eltávolítani, kövesse a következő lépéseket:
   1. Válasszon szerepkört a fán. 
   2. A szerepkörterülethez **hozzárendelt felhasználók** területen válassza **a Felhasználók kézi hozzárendelése/kizárása lehetőséget**.
   3. A felhasználók hozzárendelése a **szerepköroldalhoz, illetve a felhasználók kizárása lapon azok a felhasználók, akik nincsenek a szerepkörhöz rendelve,** **·** **a Hozzárendelési mód oszlopban vannak .** Jelölje ki a szerepkörből kizárni kívánt felhasználókat.
   4. A **Műveleti ablaktáblán** kattintson a **Kizárás szerepkörből** elemre. A **hozzárendelési mód** oszlopa most Manuális **beállításra frissül,** és a felhasználók ki vannak zárva a szerepkörből.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]


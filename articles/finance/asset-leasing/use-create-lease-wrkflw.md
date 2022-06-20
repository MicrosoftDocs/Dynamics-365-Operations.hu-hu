---
title: Lízingjóváhagyási munkafolyamatok használata
description: Ez a cikk bemutatja, hogy hogyan lehet munkafolyamatokat használni az eszközbérletek jóváhagyására, és hogyan lehet nyomon követni a munkafolyamatok állapotát és előzményeit.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4205b83919f0b3c30a4b5d8e3290af230f538f39
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906442"
---
# <a name="use-lease-approval-workflows"></a>Lízingjóváhagyási munkafolyamatok használata

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogy hogyan lehet munkafolyamatokat használni az eszközbérletek jóváhagyására, és hogyan lehet nyomon követni a munkafolyamatok állapotát és előzményeit. A munkafolyamatok segítenek a lízingjóváhagyások kezelésének konzisztenciáját a jóváhagyási lépések szabványos készletének biztosításával és a folyamat egyes lépéseit jóváhagyó felhasználók hozzárendelésével. A jóváhagyó jóváhagyhatja a lízinget, elutasíthatja, módosíthatja azt, vagy hozzárendelheti egy másik felhasználóhoz jóváhagyásra. A munkafolyamatok nagyobb betekintést nyerhetnek a jóváhagyási folyamatba azáltal, hogy nyomon követhetik azok állapotát és előzményeit. Ezenkívül megtekinthet egy központi munkalistát, amely felsorolja az adott jóváhagyókhoz rendelt feladatokat és jóváhagyásokat.

Az eljárás használata előtt győződjön meg arról, hogy legalább a lízingjóváhagyási munkafolyamat létrejött. Ha nem létezik munkafolyamat, hozzon létre egyet. A munkafolyamat beállításáról a [Lízingjóváhagyási munkafolyamatok beállítása](set-up-lease-wrkflw.md) című témakörben talál további információt.

1. Lízing küldése jóváhagyásra. A lízing **Könyv részletei** lapon válassza a **Munkafolyamat** lehetőséget, majd a **Küldés** elemet.
2. A megjelenő párbeszédpanelen megjegyzést fűzhet hozzá. A kijelölt jóváhagyó ezt a megjegyzést a lízinggel együtt fogja látni. Ha befejezte a megjegyzés beírását, válassza a **Küldés** lehetőséget. A lízing elküldésre kerül a munkafolyamat-rendszerbe, és a jóváhagyó jóváhagyásra megkapja azt.
3. A jóváhagyásra kijelölt lízingek megtekintéséhez nyissa meg a **Modulok \> Közös \> Munkaelemek \> Hozzám rendelt munkaelemek** lehetőséget.
4. A **Hozzám rendelt munkaelemek** lapon válassza a megtekinteni kívánt **Lízingazonosító** hivatkozást. A megjelenő lap a lízingkönyvektől és a lízing részleteitől függ, amelyekhez hozzáférése van.
5. Ha befejezte a lízing megtekintését, válassza a **Munkafolyamat** lehetőséget, és döntse el, hogy milyen műveletet kell végrehajtania. A lehetőségek a következők: **Jóváhagyás**, **Elutasított**, **Módosítás kérése**, **Delegálás** és **Visszavont**. Az **Előzmények megtekintése** lehetőséget választva megtekintheti a kijelölt lízingjóváhagyási előzményeit is.
6. Miután kijelölt egy műveletet, írjon be egy megjegyzést a művelet leírásához. Ha befejezte a megjegyzés beírását, válassza a **Jóváhagyott** műveletet a listában.
7. A jóváhagyási műveletek megtekintéséhez lépjen vissza a **Lízing részletei** lapra a **Lízing összegzése** lapon, majd válassza a **Munkafolyamat \> Előzmények megtekintése**.

    A munkafolyamat-tevékenységeket a **Munkafolyamat-előzmény** lapon tekintheti meg. Ez a lap az adott lízingen végrehajtott munkafolyamat-lépéseket mutatja be. A **Munkaelemek** mezővel a hozzárendelt munkaelemek állapotát is megtekintheti.

8. Munkafolyamat leállításához a **Munkafolyamat előzményei** lapon válassza a **Visszahívás** lehetőséget. Megjelenik a párbeszédpanel, adjon meg egy hozzászólást, majd kattintson az **OK** gombra.
9. A munkafolyamat inaktiválásához vagy egy korábban létrehozott munkafolyamat aktiválásához nyissa meg az **Eszközlízing \> Beállítás \> Lízingmunkafolyamat** lehetőséget. Ezután a **Lízingmunkafolyamat** lapon válassza a **Munkafolyamat \> Verziók** lehetőséget. Az aktuális munkafolyamat inaktívvá állításához jelölje ki az aktív lízinget a lízingverzió párbeszédpanelén, majd kattintson az **Inaktívvá váltás** lehetőséget. Meglévő munkafolyamat aktívvá tételéhez jelölje ki a munkafolyamatot, majd válassza az **Aktívvá tétel** lehetőséget.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

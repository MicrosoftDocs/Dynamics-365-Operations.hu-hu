---
title: Távollétkérelem
description: Távollétkérelem küldése.
author: twheeloc
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ESSLeaveofAbsenceRequestEntry, EssWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e6c98246e94670dd5f882fcbbd1f269e57f66faf
ms.sourcegitcommit: e88ecaccd82afa3a915e41df1d4287d99da6a48a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/29/2022
ms.locfileid: "9805287"
---
# <a name="request-a-leave-of-absence"></a>Távollétkérelem

>[!Important]
>Az ebben a cikkben említett funkciók jelenleg csak a különálló Dynamics 365 Human Resources rendszerében lévő vevőknek érhetők el. A funkciók egy része vagy egésze a Finance infrastruktúra jövőbeni kiadásának részeként lesz elérhető a Finance 10.0.26-ös kiadása után.


[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Távollétre vonatkozó kérelmet küldhet, és megtekintheti a szabadságkérelmek állapotát a Dynamics 365 Human Resources alkalmazásban.

## <a name="request-a-leave-of-absence"></a>Távollétkérelem

1. Az **Alkalmazotti önkiszolgáló rendszer** munkaterületen válassza a **Részletek** (...) lehetőséget a **Szabadságegyenlegek** csempén.

2. Távollétkérelem küldéséhez jelölje be a **Távollétkérelem** lehetőséget.

3. Adja meg a megfelelő adatot a **Szabadság típusa**, a **Kezdő dátum** és a **Záró dátum** mezőben.

4. Ha be bármilyen kiegészítő dokumentációt kell elküldenie, akkor a **Mellékletek** beállításnál válassza a **Feltöltés** elemet.

5. A **Megjegyzés** mezőbe írjon megjegyzést, ha szükséges.

6. Ha elkészült, válassza a **Küldés** elemet a kérés elküldéséhez. Ellenkező esetben válassza a **Mentés vázlatként** elemet.


## <a name="view-leave-of-absence-request-status"></a>Távollétkérelem állapotának megtekintése

1. Az **Alkalmazotti önkiszolgáló rendszer** munkaterületen válassza a **Részletek** (...) lehetőséget a **Szabadságegyenlegek** csempén.

2. A távollétkérelmeinek megtekintéséhez válassza a **Távollét megtekintése** lehetőséget.

## <a name="update-a-leave-of-absence-request"></a>Távolléti kérelem frissítése

1. Az Alkalmazott – **önkiszolgáló rendszer** munkaterületÉn **·**, a Távollét csempe további **tudnivalókat (...) jelöljön be**.
2. Válassza ki a frissíteni kívánt távolléti kérelmet, majd válassza **a Távollét frissítése lehetőséget**.
3. A Záró **dátum mezőben** szükség szerint frissítse az értéket a távollét meghosszabbítása vagy lerövidítása érdekében.
4. Ha a záró dátumot visszaigazolják, állítsa **a Záró dátum megerősítése** beállítást Igen **beállításra**.
5. Miután a Záró **dátum megerősítése** beállítás Igen **beállításra** van állítva, fel lehet tölteni a munkára való visszatérésről szóló értesítést. Ezt követően jelölje be a jelölőnégyzetet, ha meg kell erősíteni, hogy fel lett töltve a munkára való visszatérésről szóló értesítés.
6. A **távolléti** kérelem frissítéséhez válassza a Küldés lehetőséget.

## <a name="cancel-a-leave-of-absence-request"></a>Távolléti kérelem visszavonása

1. Az Alkalmazott – **önkiszolgáló rendszer** munkaterületÉn **·**, a Távollét csempe további **tudnivalókat (...) jelöljön be**.
2. Válassza ki a visszavonni kívánt távolléti kérelmet, majd válassza **a Távollét frissítése lehetőséget**.
3. Állítsa a Szabadság **visszavonása lehetőséget** Igen **gombra**.
4. A **távolléti** kérelem megszakításhoz válassza a Küldés lehetőséget.

## <a name="importing-leave-requests-from-other-systems-or-older-systems"></a>Szabadságkérések importálása más rendszerekből vagy régebbi rendszerekből

Szabadságkérelmek importálásához egy másik rendszerből végig kell mennie a szokásos munkafolyamaton, hogy létrehozza a megfelelő szabadságtranzakciókat. Arra is lehetőség van, hogy szabadságbanki tranzakciókat és a szabadságkérelmeket befejezett állapotban importálja. Ne feledje, hogy a szabadságbanki tranzakciók nem jön létre automatikusan, ha csak a szabadságkéréseket importálja.

## <a name="see-also"></a>Lásd még

[Szabadság felfüggesztése](hr-leave-and-absence-suspend-leave.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

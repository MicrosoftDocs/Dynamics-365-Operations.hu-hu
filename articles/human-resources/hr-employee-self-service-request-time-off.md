---
title: Távollét kérelmezése
description: Szabadság kérése a Dynamics 365 Human Resources rendszerben.
author: twheeloc
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7d06c1d40416d2644499723317c0adfd805126b5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882895"
---
# <a name="request-time-off"></a>Távollét kérelmezése

>[!Important]
>Az ebben a cikkben említett funkciók jelenleg önálló vevők számára érhetők el Dynamics 365 Human Resources. A funkciók egy része vagy egésze a Finance infrastruktúra jövőbeni kiadásának részeként lesz elérhető a Finance 10.0.26-ös kiadása után.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A Dynamics 365 Human Resources rendszerben elküldheti a szabadságra vonatkozó kéréseit, megtekintheti a szabadságának és a távollétének egyenlegét, valamint ellenőrizheti a szabadságra vonatkozó kérések állapotát.

## <a name="request-time-off"></a>Szabadság kérése

1. Az **Alkalmazotti önkiszolgáló rendszer** munkaterületen válassza a **Szabadság kérése** lehetőséget a **Szabadságegyenlegek** csempén.

2. Adja meg a megfelelő adatot a **Szabadság típusa**, az **Okkód**, a **Kezdő dátum** és a **Záró dátum** mezőben.

3. A **Dátumok** beállításnál válassza ki a szabadságkérelem dátumait.

4. Ha be bármilyen kiegészítő dokumentációt kell elküldenie, akkor a **Mellékletek** beállításnál válassza a **Feltöltés** elemet.

5. A **Megjegyzés** mezőbe írjon megjegyzést, ha szükséges.

6. Ha elkészült, válassza a **Küldés** elemet a kérés elküldéséhez. Ellenkező esetben válassza a **Mentés vázlatként** elemet.

Azok az alkalmazottak, akik új szabadságkérelmet nyújtanak be különböző szabadságtípusokat választanak ki a szabadságkérelem létrehozásához. Az egy szabadságkérés részeként kiválasztott összes szabadságtípushoz azonban ugyanazt a szabadságegységet kell választani. Az alkalmazottak a Szabadság kérelmezve **lapon megtekinthetik az egyes szabadságtípusokkal mértékegységeket**.

## <a name="add-an-attachment-to-an-existing-request"></a>Melléklet hozzáadása egy meglévő kéréshez

Ha egy már létező szabadságkérést frissít, hozzáadhat egy mellékletet. Az adott dátumra vonatkozó összes kérelem is látható.

## <a name="view-leave-balances"></a>Szabadságegyenlegek megjelenítése

1. Az **Alkalmazotti önkiszolgáló rendszer** munkaterületen válassza a **Részletek** (...) lehetőséget a **Szabadságegyenlegek** csempén.

2. Válassza az **Egyenlegek** lehetőséget.

## <a name="view-leave-request-status"></a>Szabadságkérelem állapotának megtekintése

1. Az **Alkalmazotti önkiszolgáló rendszer** munkaterületen válassza a **Részletek** (...) lehetőséget a **Szabadságegyenlegek** csempén.

2. A jóváhagyott idő-/idő-időigénylések megtekintéséhez válassza a Jóváhagyva **időkorét lehetőséget**. A függőben lévő időkorrek mertek megtekintéséhez válassza az Idő-idő **igénylések lehetőséget**.

## <a name="cancel-time-off-requests"></a>Idő-/idő-visszavonási kérelmek

1. Az **Alkalmazotti önkiszolgáló rendszer** munkaterületen válassza a **Szabadság megtekintése** lehetőséget a **Szabadságegyenlegek** csempén.

2. Az Idő **szerint oldalon** válassza ki a visszavonni kívánt idő-idő igényléseket.

3. Kattintson a **Törlés** gombra.

4. A **Törlés részletei** ablakban adjon meg egy megjegyzést, majd válassza a **Küldés** lehetőséget.

   ![Szabadságkérelem törlése.](media/hr-leave-and-absence-cancel.png)

## <a name="see-also"></a>Lásd még

- [Szabadság és távollét áttekintése](hr-leave-and-absence-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

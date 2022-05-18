---
title: Olyan feldolgozás beállítása és futtatása, amely egyszerű exportálási ER-formátumot hív le egy Excel-jelentés létrehozásához
description: Ez a témakör egy olyan példát mutat be, amely az elektronikus üzenetek beállítását és használatát szemlélteti.
author: liza-golub
ms.date: 07/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: c2735df09ecf029503ae96a88a523ea40197da8f
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/10/2022
ms.locfileid: "8734999"
---
# <a name="set-up-and-run-processing-to-call-a-simple-exporting-er-format-to-generate-an-excel-report"></a>Olyan feldolgozás beállítása és futtatása, amely egyszerű exportálási ER-formátumot hív le egy Excel-jelentés létrehozásához

[!include [banner](../includes/banner.md)]

Miután létrehozta az ER-formátumát, az adatforrásokhoz társította és befejezte, lefuttathatja az **Elektronikus jelentéskészítés** munkaterületről. A jelentést a létrehozása után helyben mentheti.

Be kell állítania az elektronikus üzenetfeldolgozást, ha szeretné szabályozni a jelentéskészítési folyamat következő aspektusait:

- Naplóinformáció a jelentés létrehozójáról.
- Naplóinformáció a jelentés létrehozásának idejéről.
- A jelentések mentése, amelyet korábbi időszakokra hoztak létre.

Az alábbi példa azt mutatja be, hogyan lehet elektronikus üzenetet beállítani egy Microsoft Excelhez tartozó exportálási ER-formátumon alapuló jelentés létrehozására. A példa követéséhez az Excel ER-formátumot előre létre kell hoznia, adatforrásokhoz kell társítania, valamint be kell fejeznie. Ezenfelül, az elektronikus üzenetekhez már be kell állítani egy számsorozatot.

A feldolgozás készítési során hasznos, ha először meghatározza a feldolgozási műveleteket és az állapotokat, amiket be fog állítani. Az alábbi ábra mutatja a példa esetén történő feldolgozást.

![Feldolgozási séma](media/processing-scheme.png)

## <a name="create-message-statuses"></a>Üzenetállapotok létrehozása

1. Lépjen az **Adó** \> **Beállítás** \> **Elektronikus üzenetek** \> **Üzenetállapotok** menüpontba.
2. Hozza létre a következő üzenetállapotokat:

    - Új
    - Előkészítve
    - Létrehozva

    ![Üzenetállapotok](media/message-statuses.png)

3. Az **Új** állapothoz tartozó sorban jelölje be a **Törlés engedélyezése** jelölőnégyzetet, hogy a felhasználók törölhessenek olyan üzeneteket, amelyek ezzel az állapottal rendelkeznek.

## <a name="create-additional-fields"></a>További mezők létrehozása

1. Lépjen az **Adó** \> **Beállítás** \> **Elektronikus üzenetek** \> **További mezők** menüpontra.
2. Adjon hozzá egy további mezőt és ennek értékeit.
3. Állítsa a **Felhasználói szerkesztés** beállítást **Igen** értékre, hogy a felhasználók szerkeszthessék a mezőt.

![További mezők](media/additional-fields.png)

## <a name="create-message-processing-actions"></a>Üzenetfeldolgozási műveletek létrehozása

Ebben a példában az alábbi üzenetfeldolgozási műveleteket fogja létrehozni:

- **Üzenet létrehozása**
- **Frissítés Előkészítve értékre**
- **Jelentés létrehozása**
- **Frissítés kiindulási állapotra** (nem kötelező)

Műveletek létrehozásához kövesse az alábbi lépéseket.

1. Lépjen az **Adó** \> **Beállítás** \> **Elektronikus üzenetek** \> **Üzenetfeldolgozási műveletek** menüpontba.
2. Hozzon létre egy műveletet, amelynek a neve **Üzenet létrehozása**. Az **Általános** gyorslapon a **Művelettípus** mezőben válassza az **Üzenet létrehozása** lehetőséget.
3. Hozzon létre egy **Frissítés Előkészítve értékre**, majd állítsa be a következő mezőket:

    - Az **Általános** gyorslapon a **Művelettípus** mezőben válassza az **Üzenetszint felhasználói feldolgozás** lehetőséget.
    - A **Kiindulási állapotok** gyorslapon az **Üzenetállapot** mezőben válassza az **Új** lehetőséget.
    - Az **Eredményállapotok** gyorslapon az **Üzenetállapot** mezőben válassza az **Előkészítve** lehetőséget. A **Választípus** mezőben adja meg a **Sikeresen végrehajtva** lehetőséget.

4. Hozzon létre egy **Jelentés létrehozása**, majd állítsa be a következő mezőket:

    - Az **Általános** gyorslapon a **Művelettípus** mezőben válassza az **Elektronikus jelentéskészítés exportálása** lehetőséget. A **Formátumleképezés** mezőben válassza ki az exportálási ER-formátumot. A lehetőségek a következők: **Excel**, **XML**, **JSON**, **Szöveg** és **Egyéb**.
    - A **Kiindulási állapotok** gyorslapon az **Üzenetállapot** mezőben válassza az **Előkészítve** lehetőséget.
    - Az **Eredményállapotok** gyorslapon az **Üzenetállapot** mezőben válassza a **Létrehozva** lehetőséget. A **Választípus** mezőben adja meg a **Sikeresen végrehajtva** lehetőséget.

    ![Jelentés létrehozása művelet](media/generate-report-action.png)

5. Nem kötelező: Annak érdekében, hogy a felhasználók ugyanazt a jelentést több alkalommal ismételten létrehozhassák, hozzon létre **Frissítés kiindulási állapotra** nevű műveletet, és állítsa be az alábbi mezőket:

    - Az **Általános** gyorslapon a **Művelettípus** mezőben válassza az **Üzenetszint felhasználói feldolgozás** lehetőséget.
    - A **Kiindulási állapotok** gyorslapon az **Üzenetállapot** mezőben válassza a **Létrehozva** lehetőséget.
    - Az **Eredményállapotok** gyorslapon adjon hozzá külön sort mindkét üzenetállapothoz (**Előkészítve** és **Új**). Mindkét sorban állítsa a **Választípus** mezőt **Sikeresen végrehajtva** értékre.

## <a name="electronic-message-processing"></a>Elektronikus üzenetek feldolgozása

Ebben a példában az össze műveletet úgy kell beállítani, hogy egymástól külön is tudjanak futni. Az a feltételezés, hogy minden műveletet a felhasználó kezdeményez majd.

1. Lépjen az **Adó** \> **Beállítás** \> **Elektronikus üzenetek** \> **Elektronikus üzenetfeldolgozás** menüpontba.
2. Adjon hozzá egy rekordot a feldolgozáshoz, és adja hozzá az összes korábban meghatározott műveletet és egy további mezőt.
3. Választható: A **Biztonsági szerepkörök** gyorslapon határozza meg a biztonsági szerepköröket a feldolgozáshoz, hogy azzal korlátozza a meghatározott jelentéskészítéshez való hozzáférést.
4. Lépjen az **Adó** \> **Lekérdezések és jelentések** \> **Elektronikus üzenetek** \> **Elektronikus üzenetek** menüpontba.
5. Válassza az **Új** lehetőséget egy üzenet létrehozásához. Ezen a ponton adhat hozzá dátumokat és leírást. Ekkor szükség szerint a további mező értékét is frissítheti.

    ![Elektronikus üzenet létrehozása](media/create-electronic-message.png)

    A **Műveletnapló** gyorslapon a rács automatikusan kitöltésre kerül az adott üzeneten elvégzett összes művelet naplója.

    Most törölheti vagy frissítheti az üzenet állapotát. 

6. Ha frissíteni szeretné egy üzenet állapotát, válassza az **Üzenetállapot** lehetőséget. Az **Új állapot** mezőben válassza az **Előkészítve** lehetőséget, majd az **OK** gombot.

    ![Az üzenet állapotának frissítése](media/update-status.png)

    Az üzenet **Előkészített** állapotúra módosul.

7. Hozza létre a jelentést a **Jelentés létrehozása** lehetőséget választva.

    A jelentés létrejött, az üzenet állapota és a műveletnapló pedig frissült.

8. A létrehozott jelentés megtekintéséhez válassza a **Melléklet** gombot (gemkapocs jel) az oldal jobb felső sarkában.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

---
title: Kötegelt feladat létrehozása
description: A kötegelt feladat egy Alkalmazásobjektum-kiszolgáló (AOS) példányához elküldött feladatcsoport az automatikus feldolgozáshoz.
author: matapg007
ms.date: 11/22/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: matgupta
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
ms.openlocfilehash: 06fb9a18e70c316be97645ba76f9462cd3ccc729
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292450"
---
# <a name="create-a-batch-job"></a>Kötegelt feladat létrehozása

[!include [banner](../../includes/banner.md)]

A kötegelt feladat egy Alkalmazásobjektum-kiszolgáló (AOS) példányához elküldött feladatcsoport az automatikus feldolgozáshoz. A Kötegelt feladatok futtatása a feladatot létrehozó felhasználó biztonsági hitelesítő adatainak használatával történik. A következő eljárásokkal lehet meghatározni a kötegelt feladatot. Ez az eljárás az USMF bemutatócéget használja.


## <a name="create-the-batch-job"></a>Kötegelt feladat létrehozása
1. Ugorjon a **Navigációs lap > Modulok > Rendszerfelügyelet > Lekérdezések > Kötegelt feladatok** pontra.
2. Válassza az **Új** lehetőséget.
3. A Feladat **leírása mezőbe** írja be a kötegelt feladat leírását.
4. Az Ütemezett **kezdő dátum/** idő mezőbe írja be a kötegelt feladat futtatásának dátumát és időpontját.
5. Válassza a **Mentés** lehetőséget.

## <a name="create-a-recurrence"></a>Ismétlődés létrehozása
1. A munkaablakban válassza ki a Kötegelt **feladatot**.
2. **Ismétlődés** kiválasztása. E beállítások segítségével megadhatja az ismétlődés tartományát és a mintáját.  
3. Válassza ki az **OK** lehetőséget.

## <a name="add-alerts"></a>Figyelmeztetések hozzáadása
1. A munkaablakban válassza ki a Kötegelt **feladatot**.
2. Figyelmeztetések **kiválasztása**. Jelezze, ha szeretne figyelmeztető üzenetet kapni a kötegelt feladat befejeződése, meghibásodása vagy törlődése esetén. Adja meg, ha azt szeretné, hogy a figyelmeztetések előugró üzenetekként jelenjenek meg.   
3. Válassza ki az **OK** lehetőséget.

## <a name="add-a-task-to-a-batch-job"></a>Művelet hozzáadása kötegelt feladathoz
1.  A Kötegelt **feladatok lapon** válassza a Feladatok **megtekintése lehetőséget**.
2.  Feladat **létrehozásához nyomja le a CTRL+N** billentyűkombinációt.
3.  Adja meg a kötegelt feladat leírását.
4.  A Vállalati **számlák mezőben** válassza ki azt a vállalati adatbázist, amelybe a feladatot futtatni kell.
5.  Az Osztálynév **mezőben** válassza ki, hogy a feladatnak mit kell futtatnia. 
6.  Szükség szerint válasszon egy kötegcsoportot a feladathoz.

    Az ügyfélfeladatokat kötegcsoporthoz kell rendelni. A program automatikusan az alapértelmezett kötegcsoporthoz (más néven Üres kötegcsoporthoz) rendeli hozzá őket.

7.  Mentse a **feladatot a CTRL+S** billentyűkombináció lenyomásával.
8.  Ha a kiválasztott feladattól a feladatban található másik feladattól szeretne függeni, **jelölje** be a Feltételek rácsát, majd hajtsa végre a következő lépéseket minden definiálni kívánt feltételnél:

    1. Feltétel létrehozásához **nyomja le a CTRL+N** billentyűkombinációt.
    2. Válassza ki a szülőfeladat feladatazonosítóját.
    3. Válassza ki, hogy a szülőfeladatnak el kell érnie az állapotot, mielőtt a függő feladat futhat.
    4. Mentse a **feltételt a Ctrl+S** billentyűkombináció lenyomásával.

    Ha egynél több feltételt ad meg, *és* a függő feladat csak akkor futhat, ha az összes feltételnek teljesülnie kell, válassza a **Mind feltételtípust**. Ha a függő feladat bármelyik *feltétel* teljesülését követően futtatható, válassza a **Bármelyik feltételtípust**.

9.  Válassza ki, hogyan kell kezelni a feladathibákat. Ha figyelmen kívül hagyja egy adott feladat sikertelenségét, **·** **akkor** az Általános lapon jelölje be a Feladathiba figyelmen kívül hagyása lehetőséget. Ha ez a beállítás be van jelölve, a feladat sikertelen lesz, és a feladat nem fog leállni. A Maximális újratárgyalások **mező** használatával megadhatja azt is, hogy a rendszer hányszor ássa újra a feladatot, mielőtt a rendszer sikertelennek tekintheti. Javasoljuk, **hogy ne állítsa a Maximális újraküldő** **értékek értékét 5-nél nagyobb értékre**.

    A kötegelt újraküldő feladatokkal kapcsolatos további [tudnivalókat lásd: Köteg-újraküldetek engedélyezése](../retryable-batch.md).

## <a name="adjust-batch-job-status"></a>Kötegelt feladat állapotának beállítása
1. Ugorjon a **Rendszerfelügyelet > Lekérdezések > Kötegelt feladatok** pontra.
2. Jelölje ki a megfelelő kötegelt feladatokat.
3. Válassza ki a műveletpanelEn **a Kötegelt > funkció > állapot módosítása lehetőséget**.
4. Válassza ki a megfelelő állapotot.
    - **Visszatartás**: A kötegelt feladat **visszatartási** értékre állítása, így a kötegelt munkaütemezőből visszatartható. A *leállítással* egyenértékű.
    - **Várakozás**: A kötegelt feladat **várakozásra** történő beállítása, így a kötegelt munkaütemező által elindítható. A *mehettel* egyenértékű.
5. Válassza ki az **OK** lehetőséget.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

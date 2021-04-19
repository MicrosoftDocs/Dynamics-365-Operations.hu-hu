---
title: Preferált karbantartási dolgozók beállítása
description: Ez a témakör azt mutatja be, hogyan lehet előnyben részesített karbantartási dolgozókat beállítani az Eszközkezelés modulban.
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkerPreferred
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5b044e4616555559be51b0846327b1d55bfe47b3
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822539"
---
# <a name="set-up-preferred-maintenance-workers"></a>Preferált karbantartási dolgozók beállítása

[!include [banner](../../includes/banner.md)]

 

Amikor a program a munkarendelés ütemezésekor kiosztja a dolgozókat a munkarendeléshez lehetőség van arra, hogy megadja, melyik karbantartási dolgozót vagy dolgozócsoportot szeretné előnyben részesíteni. A funkció használata nem kötelező, de a dolgozó tudásának és szakértelme alapján a legalkalmasabb karbantartási dolgozót tudja kiválasztani egy feladatra. A program csak az ütemezés időpontban rendelkezésre álló karbantartási dolgozókat ütemezi. Ha egy előnyben részesített karbantartási dolgozó beállítása egyezik egy munkarendeléssel az ütemezés során, de a karbantartási dolgozó más feladatokra van beosztva, akkor a munkarendelést egy másik, rendelkezésre álló karbantartási dolgozó fogja megkapni.

Mielőtt beállítja a karbantartási dolgozókat, először be kell állítania a karbantartási dolgozókat és a dolgozói csoportokat. A karbantartási dolgozók és dolgozói csoportok beállításával kapcsolatosan a [Karbantartási dolgozók és dolgozói csoportok](../setup-for-objects/workers-and-worker-groups.md) című cikkben talál további információt.

## <a name="set-up-preferred-workers"></a>Előnyben részesített dolgozók beállítása

A preferált karbantartási dolgozók vagy dolgozói csoportok kapcsolódhatnak következők közül egyhez vagy többhöz:

- kereskedelem  
- karbantartási feladattípus változata  
- karbantartási feladat típusa  
- karbantartási feladattípus kategóriája  
- eszköz  
- eszköztípus  

Minél több lehetőséget választ ki egy rekordhoz, annál konkrétabb lesz a beállítás.

1. Kattintson az **Eszközkezelés** > **Beállítások** > **Dolgozók** > **Preferált karbantartási dolgozók** elemre.

2. Hozzon létre egy új rekordot az **Új** gombra kattintva.

3. Kezdjen egy „alapértelmezett” karbantartási dolgozói vagy dolgozói csoport létrehozásával. Ez azt jelenti, hogy csak a **Preferált karbantartási dolgozói csoport** vagy a **Preferált karbantartási dolgozó** mezőben lett kiválasztva. Az alábbi képernyőfotón egy példa látható az első rekordra, amelyben a „Kérések” lett kijelölve **Preferált karbantartási dolgozói csoportként**.

    [!NOTE] A program az alapértelmezett beállítást használja a munkarendelés-ütemezés során, ha nincs más konkrétabb kombináció, amely jobban megfelel a munkarendelés tartalmának.

4. Új rekord létrehozásához ismételje meg a 2. lépést. A preferált dolgozótól vagy dolgozó csoporttól függően válassza ki a kívánt beállításokat. 

    *Példa:* Az alábbi képernyőfotón, a hatodik rekordban, Shawn Richardson karbantartási dolgozó van kiválasztva preferált dolgozóként. Ha az ütemezés időpontjában szabad, a CH-BP1-03-02 eszközt és a „Létesítményértékelés” típusú karbantartás feladattípust tartalmazó munkarendelés ütemezése során automatikusan ki lesz választva.

    [!NOTE] Általában amikor a munkarendelés ütemezésekor egy preferált karbantartási dolgozó lesz kiválasztva, az Eszközkezelés ellenőrzi a **Preferált karbantartási dolgozók** rekordokban az esetleges egyezéseket. A rendszer a legkonkrétabb kombinációt ellenőrzi elsőként. Ha nem talál egyezést, akkor az olyan „alapértelmezett” rekordot használja, amelyik meg lett adva a **Preferált karbantartási dolgozói csoport** vagy a **Preferált karbantartási dolgozó** mezőben.

![1. ábra](media/02-work-order-scheduling.png)

Beállíthat *felelős* karbantartási dolgozókat is, akiket ki lehet választani egy karbantartási kérés vagy munkarendelés létrehozásakor. Az **Összes munkarendelés** és az **Összes karbantartási kérés** részen szükség szerint szerkesztheti a kijelölést. További információért lásd: [Felelős karbantartási dolgozók](../setup-for-maintenance-requests/responsible-workers.md).

A munkarendelés ütemezése során a program különböző pontszámokat számít ki annak meghatározására, hogy melyik dolgozók kapják a munkarendeléshez kapcsolódó feladatokat (ezeket a pontszámokat az **Eszközkezelés paraméterei** > **Munkarendelés ütemezése** hivatkozásra kattintva tekintheti meg). Ha a munkarendelés ütemezése során több preferált karbantartási dolgozó vagy felelős karbantartási dolgozó kap ugyanakkora pontszámot, akkor a rendszer véletlenszerűen választ. Ellenkező mindig a legmagasabb pontszámú dolgozó lesz hozzárendelve a munkarendeléshez.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
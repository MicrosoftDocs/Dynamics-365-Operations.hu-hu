---
title: Nyílt végű távollét létrehozása
description: Ez a cikk bemutatja, hogyan lehet nyílt végű távollétet létrehozni a Microsoftban Dynamics 365 Human Resources.
author: twheeloc
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 08231d4139209387c3c76923fafdd2061fceb280
ms.sourcegitcommit: e88ecaccd82afa3a915e41df1d4287d99da6a48a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/29/2022
ms.locfileid: "9805423"
---
# <a name="create-an-open-ended-leave-of-absence"></a>Nyílt végű távollét létrehozása

> [!IMPORTANT]
> Az ebben a részben ismertetett funkciók a pénzügyi infrastruktúra 10.0.31-es kiadásának 365-ös kiadása után lesznek elérhetők a Microsoft Dynamics pénzügyi infrastruktúra területén.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A nyílt végű távolléti kérelmeket be lehet nyújtani, és meg lehet tekinteni a szabadságra vonatkozó kérelmek állapotát Dynamics 365 Human Resources.

## <a name="prerequisites"></a>Előfeltételek

1. A **Funkciókezelés** funkcióban győződjön meg arról, hogy a Nyitott **végű** szabadság funkció be van kapcsolva.

    > [!IMPORTANT]
    > A funkció bekapcsolt használata után nem lehet kikapcsolni.

2. Távolléti szabadság típusának létrehozása.
3. Adja meg a részleteket, például a szabadság típusát, leírását és a munkafolyamat azonosítóját.
4. A Kérelemtípus **mezőben** válassza a Távollét **lehetőséget**.
5. A részletek szakaszban a nyitott végű levelek esetén **állítsa a Nyitott vége beállítást** Igen **beállításra**.
6. Állítsa a Vissza **a munka értesítéshez lehetőséget** Igen **vagy** Nem **beállításra**.
7. A nyílt végű távolléti kérelmekhez szükség lehet a munkára való visszatérésről szóló értesítésre is.

> [!NOTE]
> A funkció engedélyezése után elérhető lesz **a Melléklet szükséges** szolgáltatás.

## <a name="request-an-open-ended-leave-of-absence"></a>Nyílt végű távollét kérelmezve

1. Válassza a **More (...) lehetőséget az Alkalmazotti**  **önkiszolgáló rendszer munkaterületÉnek Időkiegyenlülési csempe**  **.**
2. Távolléti kérelem benyújtásához jelölje be a Távolléti **kérelem lehetőséget**.
3. Adja meg az adatokat a **Szabadság típusa és**  **a Kezdő dátum mezőben** . A Záró **dátum mezőbe** írja be a feltételes záró dátumot.
4. Ha el kell nyújtania a támogató dokumentációt, a Mellékletek **mezőben** válassza a Feltöltés **lehetőséget**.
5. Ha készen áll a kérés elküldését, válassza a Küldés **lehetőséget**. Ellenkező esetben válassza a **Mentés vázlatként** elemet.
6. Egy nyitott végű szabadságra vonatkozó kérelem frissítéséhez válassza ki a kérést, adjon meg egy záró dátumot a **Záró dátum mezőben,**  **állítsa** a Záró dátum megerősítése beállítást Igen **beállításra, és töltse fel a dokumentációt.**
7.  **Ha a Vissza**  **a** munka értesítéshez beállítás Igen, **válassza** a Feltöltés lehetőséget, majd jelölje be a jelölőnégyzetet, hogy meggyőződjön arról, hogy érvényes munkára való visszajelzett értesítés van feltöltve.
8. Ha minden adatot megadott, válassza a Küldés **lehetőséget**.

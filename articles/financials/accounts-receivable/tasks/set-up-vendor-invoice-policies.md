---
title: Szállítói számla irányelveinek beállítása
description: Ez a témakör azt mutatja be, hogyan lehet beállítani a Dynamics 365-ben a Finance and Operations szolgáltatás szállítói számlákra vonatkozó irányelveit.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 328aafd16496fdbb963c9aa40a5c13005be7a382
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1842809"
---
# <a name="set-up-vendor-invoice-policies"></a>Szállítói számla irányelveinek beállítása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez a témakör azt mutatja be, hogyan lehet beállítani a Dynamics 365-ben a Finance and Operations szolgáltatás szállítói számlákra vonatkozó irányelveit. A Szállítói számlára vonatkozó irányelvek akkor futnak, amikor a szállítói számla oldal használatával ad fel egy szállítói számlát, és amikor megnyitja a szállítói számlára vonatkozó irányelv megszegéseinek lapját. A szállítói számla munkafolyamatát is beállíthatja úgy, hogy a valahányszor számlát küld egy munkafolyamathoz, futtatja a szállítói számlára vonatkozó irányelveket. 

- A szállítói számla irányelvek nem vonatkoznak azokra a számlákra, amelyek a számlajegyzékben vagy a számlanaplóban jöttek létre.  
- A számlaegyeztetés érvényesítése nem használja a szállítói számla irányelveket, ehelyett egy Kötelezettségek paraméterei oldalt hoz létre.  
- Ez a felvétel az USMF bemutatócéget használja. A kötelezettségeket kezelő vezető vagy a könyvelésért felelős vezető ezeket a lépéseket hajtja végre. Mielőtt elkezdené a beállítást, győződjön meg arról, hogy a Számlaegyeztetés konfigurációs kulcs be van állítva.


## <a name="prepare-to-create-vendor-invoice-policies"></a>Felkészülés a szállítói számlára vonatkozó irányelvek létrehozására
1. Ugorjon a **Navigációs ablaktábla > Modulok > Kötelezettségek > Beállítás > Kötelezettségek paraméterei** lehetőségre.
2. Kattintson a **Számlaegyeztetés** fülre.
3. Válassza ki vagy állítsa alaphelyzetbe a **Számlafejléc automatikus frissítése** állapot jelölőnégyzetét.
4. Válassza ki az **OK** lehetőséget.
5. A **Számlafeladás eltérésekkel** mezőben válasszon a lehetőségek közül.
6. Zárja be a lapot.
7. Ugorjon a **Navigációs ablaktábla > Modulok > Kötelezettségek > Irányelv beállítása > Szállítói számla irányelvei** elemre.
8. Válassza ki a **Paraméterek** elemet.
9. Válassza a **Hozzáadás** lehetőséget.
10. A kezdőlaphoz való visszatéréshez zárja be az oldalt.

## <a name="create-policy-rule-types-for-vendor-invoices"></a>Szállítói számla irányelvszabály-típusainak létrehozása szállítói számlákhoz
1. Ugorjon a **Navigációs ablaktábla > Modulok > Kötelezettségek > Irányelv beállítása > Szállítói számla irányelvszabály-típusai** elemre.
2. Válassza az **Új** lehetőséget.
3. Töltse ki a **Szabály neve** és a **Leírás** mezőt.
4. A **Lekérdezés neve** mezőben válassza ki a legördülő gombot a keresés megnyitásához, majd válassza ki a kívánt rekordot.
5. Válassza a **Mentés** lehetőséget.
6. A kezdőlaphoz való visszatéréshez zárja be az oldalt.

## <a name="define-a-vendor-invoice-policy"></a>Adjon meg egy Szállítói számlára vonatkozó irányelvet
1. Ugorjon a **Navigációs ablaktábla > Modulok > Kötelezettségek > Irányelv beállítása > Szállítói számla irányelvei** elemre.
2. Válassza az **Új** lehetőséget.
3. Töltse ki a **Név** és a **Leírás** mezőt.
4. Csukja be vagy bontsa ki az **Irányelv szervezetei** szakaszt.
5. A fán válassza ki a **Contoso Entertainment System USA** lehetőséget.
6. Válassza a **Hozzáadás** lehetőséget.
7. Csukja be vagy bontsa ki az **Irányelvszabályok** szakaszt.
8. Válassza ki az **Irányelvszabály létrehozása** lehetőséget.
9. Írjon be egy értéket az **Irányelvszabály leírása** mezőbe.
10. Válassza ki a **Szűrő** elemet.
11. Válassza a **Hozzáadás** lehetőséget. Válassza ki a kívánt rekordot.
12. A **Táblában**, a **Származtatott táblában**és a **Mező** mezőben válassza ki vagy adja meg a beállításokat a legördülő menükből.
13. Zárja be a lapot.
14. Adjon meg egy értéket a **Feltétel** mezőben.
15. Válassza ki az **OK** lehetőséget.
16. Válassza ki az **OK** lehetőséget.
17. A kezdőlaphoz való visszatéréshez zárja be az oldalakat.


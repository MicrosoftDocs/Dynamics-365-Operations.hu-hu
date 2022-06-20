---
title: Szállítói számla irányelveinek beállítása
description: Ez a cikk bemutatja a szállítói számlákra vonatkozó irányelvek beállítását.
author: ShivamPandey-msft
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 049b38b6feba5f4369d79b89b4c81a8195dd7758
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904730"
---
# <a name="set-up-vendor-invoice-policies"></a>Szállítói számla irányelveinek beállítása

[!include [banner](../../includes/banner.md)]

Ez a cikk bemutatja a szállítói számlákra vonatkozó irányelvek beállítását. A szállítói számlákra vonatkozó irányelvek akkor futnak le, amikor szállítói számlát **a** **Szállítói számla lapon felad, és amikor megnyitja a szállítói számla irányelvének megszegése lapot.** A szállítói számla munkafolyamatát is beállíthatja úgy, hogy a valahányszor számlát küld egy munkafolyamathoz, futtatja a szállítói számlára vonatkozó irányelveket. 

- A szállítói számla irányelvek nem vonatkoznak azokra a számlákra, amelyek a számlajegyzékben vagy a számlanaplóban jöttek létre.  
- A számlaegyeztetés érvényesítése nem használ szállítói számla irányelveket, **hanem a Kötelezettségek paraméterei lapon van beállítva**.  
- Ez a felvétel az USMF bemutatócéget használja. A kötelezettségeket kezelő vezető vagy a könyvelésért felelős vezető ezeket a lépéseket hajtja végre. Mielőtt hozzákezd, győződjön meg arról, hogy ki van **választva a Számlaegyeztetés** konfigurációs kulcs.


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
12. A **Táblában**, a **Származtatott táblában** és a **Mező** mezőben válassza ki vagy adja meg a beállításokat a legördülő menükből.
13. Zárja be a lapot.
14. Adjon meg egy értéket a **Feltétel** mezőben.
15. Válassza ki az **OK** lehetőséget.
16. Válassza ki az **OK** lehetőséget.
17. A kezdőlaphoz való visszatéréshez zárja be az oldalakat.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

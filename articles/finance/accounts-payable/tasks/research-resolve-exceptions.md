---
title: Kivételek kivizsgálása/feloldása
description: A Szállítói számlára vonatkozó irányelvek akkor futnak, amikor a szállítói számla oldal használatával ad fel egy szállítói számlát, és amikor megnyitja a szállítói számlára vonatkozó irányelv megszegéseinek lapját.
author: abruer
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 32ff53198f61e1d1af3c437e9488c2a246cf820a
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2022
ms.locfileid: "8110019"
---
# <a name="research-or-resolve-exceptions"></a>Kivételek kivizsgálása/feloldása

[!include [banner](../../includes/banner.md)]

A szállítói számlákra vonatkozó irányelvek akkor futnak le, amikor szállítói számlát **a** **Szállítói számla lapon felad, és amikor megnyitja a szállítói számla irányelvének megszegése lapot.** A szállítói számla munkafolyamatát is beállíthatja úgy, hogy a valahányszor számlát küld egy munkafolyamathoz, futtatja a szállítói számlára vonatkozó irányelveket. 

A szállítói számla irányelvei nem vonatkoznak a számlajegyzékben vagy **a** **számlanaplóban létrehozott számlákra**. 

A számlaegyeztetés érvényesítése nem használ szállítói számla irányelveket, **hanem a Kötelezettségek paraméterei oldalon van beállítva**.

Ez a felvétel az USMF bemutatócéget használja. A kötelezettségeket kezelő vezető vagy a könyvelésért felelős vezető ezeket a lépéseket hajtja végre. Mielőtt hozzákezd, győződjön meg arról, hogy ki van **választva a Számlaegyeztetés** konfigurációs kulcs.


## <a name="prepare-to-create-vendor-invoice-policies"></a>Felkészülés a szállítói számlára vonatkozó irányelvek létrehozására
1. Lépjen a **Kötelezettségek > Beállítás > Kötelezettségek paraméterei** részre.
2. Kattintson a Számlaellenőrzés **fülre**.
3. Jelölje be a Számlafejléc automatikus **frissítése állapot jelölőnégyzetet, vagy törölje a jelölést** a jelölőnégyzetből.
4. Kattintson az **OK** gombra.
5. A **Számlafeladás eltérésekkel** mezőben válasszon a lehetőségek közül.
6. Zárja be a lapot.
7. Menjen a **Kötelezettségek > irányelveinek és > irányelveihez**.
8. Kattintson a **paraméterekre**.
9. Kattintson a **Hozzáadás** parancsra.
10. Zárja be a lapot.

## <a name="create-policy-rule-types-for-vendor-invoices"></a>Szállítói számla irányelvszabály-típusainak létrehozása szállítói számlákhoz
1. Menjen a Kötelezettségek **> irányelvbeállítási > a Szállítói számla irányelvszabály-típusaihoz**.
2. Kattintson az **Új** elemre.
3. Írjon be egy értéket a **Szabály neve** mezőbe.
4. Írjon egy értéket a **Leírás** mezőbe.
5. A Lekérdezés **neve mezőben** kattintson a legördülő gombra a keresés megnyitásához.
6. Keresse meg és jelölje ki a kívánt rekordot a listán.
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.
8. Kattintson a **Mentés** gombra.
9. Zárja be a lapot.

## <a name="define-a-vendor-invoice-policy"></a>Adjon meg egy Szállítói számlára vonatkozó irányelvet
1. Menjen a **Kötelezettségek > irányelveinek és > irányelveihez**.
2. Kattintson az **Új** elemre.
3. Írjon be egy értéket a **Név** mezőbe.
4. Írjon egy értéket a **Leírás** mezőbe.
5. Csukja be vagy bontsa ki az **Irányelv szervezetei** szakaszt.
6. A fán válassza ki a „Contoso Szórakozás rendszer USA” lehetőséget.
7. Kattintson a **Hozzáadás** parancsra.
8. Csukja be vagy bontsa ki az **Irányelvszabályok** szakaszt.
9. Kattintson az **Irányelvszabályra** elemre.
10. Írjon be egy értéket az **Irányelvszabály leírása** mezőbe.
11. Kattintson a **Szűrő** parancsra.
12. Kattintson a **Hozzáadás** parancsra.
13. A listában jelölje meg a kiválasztott sort.
14. A Táblázat **mezőben** kattintson a legördülő gombra a keresés megnyitásához.
15. A listában kattintson a kijelölt sorban lévő hivatkozásra.
16. A Származtatott **tábla** mezőben kattintson a legördülő gombra a keresés megnyitásához.
17. A listában kattintson a kijelölt sorban lévő hivatkozásra.
18. A Mező **mezőben** kattintson a legördülő gombra a keresés megnyitásához.
19. A Mező **mezőbe** írjon be egy értéket.
20. Zárja be a lapot.
21. Adjon meg egy értéket a **Feltétel** mezőben.
22. Kattintson az **OK** gombra.
23. Kattintson az **OK** gombra.
24. Zárja be a lapot.
25. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

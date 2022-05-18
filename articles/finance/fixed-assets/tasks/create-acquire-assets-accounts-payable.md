---
title: Eszközök létrehozása és beszerzése a Követelések modulból
description: Ez az eljárás végigkíséri a tárgyi eszköz létrehozását és beszerzését a beszerzési folyamattal együtt.
author: moaamer
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetParameters, VendInvoiceWorkspace, VendEditInvoice, VendTableLookup, InventItemIdLookupSimple, AssetTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4290ced6bcf4432583cffc9122a4bba86266a559
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/05/2022
ms.locfileid: "8713613"
---
# <a name="create-and-acquire-assets-from-accounts-payable"></a>Eszközök létrehozása és beszerzése a Követelések modulból

[!include [banner](../../includes/banner.md)]

Ez az eljárás végigkíséri a tárgyi eszköz létrehozását és beszerzését a beszerzési folyamattal együtt.  A Könyvelő és Kötelezettségek ügyintézőket és a bemutató USMF vállalatot használja.


## <a name="set-fixed-assets-parameters"></a>Tárgyi eszközök paramétereinek beállítása
1. A **navigációs ablaktáblán** ugorjon a **Modulok > Tárgyi eszközök > Beállítás > Tárgyi eszközök paraméterei** elemre.
2. Bontsa ki a **Beszerzési rendelések** gyorslapot.
3. Jelölje be a **Beszerzés modulból való tárgyieszköz-beszerzés engedélyezése** négyzetet.
4. Jelölje be a **Tárgyi eszköz létrehozása termékbevételezés vagy számla feladása közben** négyzetet.

## <a name="create-a-new-vendor-invoice"></a>Új szállítói számla létrehozása
1. Ugorjon a **Navigációs ablaktábla** – **Modulok > Kötelezettségek > Munkaterületek > Szállítói számla bevitele** elemre.
2. Kattintson az **Új szállítói számla** gombra.
3. A **Számlafiók** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. Adjon meg egy értéket a **Szám** mezőben.
6. A **Feladási dátum** mezőben adjon meg egy dátumot.
7. Kattintson az **Új sor hozzáadása** elemre.
8. A **Cikkszám** mezőben kattintson a legördülő gombra a keresés megnyitásához. Nem raktározott cikkek vagy beszerzési kategóriák használhatók tárgyieszköz-beszerzésekhez is.  
9. A listában kattintson a kijelölt sorban lévő hivatkozásra.
10. Adjon meg egy számot a **Mennyiség** mezőben. Egy számlasor csak egy tárgyi eszközt hoz létre a mennyiségtől függetlenül. A számlamennyiség mező értékét átviszi a tárgyi eszköz mennyiségbe.  
11. Adjon meg egy számot az **Egységár** mezőben.
12. Bontsa ki a **Soradatok** gyorslapot.
13. Kattintson a **Tárgyi eszközök** lapra.
14. Jelölje be az **Új tárgyi eszköz létrehozása** jelölőnégyzetet.
15. A **Tárgyieszköz-csoport** mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
16. A listából válassza ki az új tárgyi eszköz létrehozásakor használni kívánt tárgyieszköz-csoportot.
17. A listában kattintson a kijelölt sorban lévő hivatkozásra.
18. Kattintson a **Bejegyzés** lehetőségre. A tárgyi eszköz létrejön, és átkerül a számla feladásakor.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

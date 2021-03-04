---
title: Eszközök létrehozása és beszerzése a Követelések modulból
description: A feladat-útmutató végigvezeti a tárgyi eszköz létrehozásán és a beszerzésén a beszerzési folyamaton keresztül.
author: saraschi2
manager: AnnBe
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters, VendInvoiceWorkspace, VendEditInvoice, VendTableLookup, InventItemIdLookupSimple, AssetTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7cb9a37c65fb8eab4db6084b91a71c13a45ba42c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444009"
---
# <a name="create-and-acquire-assets-from-accounts-payable"></a>Eszközök létrehozása és beszerzése a Követelések modulból

[!include [banner](../../includes/banner.md)]

A feladat-útmutató végigvezeti a tárgyi eszköz létrehozásán és a beszerzésén a beszerzési folyamaton keresztül.  A Könyvelő és Kötelezettségek ügyintézőket és a bemutató USMF vállalatot használja.


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
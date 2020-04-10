---
title: Munka és kiadások elszámolóárainak konfigurálása
description: Ez a témakör elmagyarázza, hogyan állítható be egy projekt munkához és kiadásokhoz tartozó elszámolóára.
author: KimANelson
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCostPriceHour, ProjSalesPriceHour, ProjCostPriceExpense, ProjSalesPriceCost
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 51bbe52d70bae11cb0c95e9544f951f0fcc605f5
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140093"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a>Munka és kiadások elszámolóárainak konfigurálása

[!include [banner](../../includes/banner.md)]

Ez a témakör elmagyarázza, hogyan állítható be egy projekt munkához és kiadásokhoz tartozó elszámolóára. Ez a feladat az USSI-adatkészletet használja.

1. A navigációs ablakban lépjen a **Modulok > Projektvezetés és könyvelés > Beállítás > Árak > Önköltségi ár (óra)** részre.
2. Válassza az **Új** lehetőséget.
3. Adja meg a dátumot az **Érvényesség dátuma** mezőben.
4. Adjon meg egy számot az **Önköltségi ár** mezőben. A projektkategóriához megadható elszámolóár, de megadható az önköltségi ár dolgozószám, projektszám, kategória, dátum vagy ezek tetszőleges kombinációja alapján is. A rendszer a legnagyobb részletességű szinten létező önköltségi árat alkalmazza.  
5. Válassza a **Mentés** lehetőséget.
6. A navigációs ablakban lépjen a **Modulok > Projektvezetés és könyvelés > Beállítás > Árak > Eladási ár (óra)** részre.
7. Válassza az **Új** lehetőséget.
8. Adja meg a dátumot az **Érvényesség dátuma** mezőben.
9. Az **Érvényes** mezőben válasszon ki egy lehetőséget.
10. Adjon meg egy számot az **Árazás** mezőben. Beállítható az óratranzakciók és projektkategóriák szokásos eladási ára. Szintén be lehet állítani dolgozók száma, projekt száma, kategória, tranzakció dátuma vagy ezek bármely kombinációja szerinti eladási árakat. Amikor a dolgozó az óranaplóban beviszi a tranzakciót, a legrészletesebb szintű eladási ár lesz az aktuális eladási ár. Ha például egy általános és egy dolgozóra vonatkozó eladási ár is be van állítva, akkor a rendszer a dolgozóra vonatkozó eladási árat választja.  
11. Válassza a **Mentés** lehetőséget.
12. Zárja be a lapot.
13. A navigációs ablakban lépjen a **Modulok > Projektvezetés és könyvelés > Beállítás > Árak > Önköltségi ár (költség)** részre.
14. Válassza az **Új** lehetőséget.
15. Adja meg a dátumot az **Érvényesség dátuma** mezőben.
16. Adjon meg egy számot az **Önköltségi ár** mezőben. Több mező is kitölthető, de ez a minimálisan szükséges a rekord mentéséhez.  
17. Válassza a **Mentés** lehetőséget.
18. A navigációs ablakban lépjen a **Modulok > Projektvezetés és könyvelés > Beállítás > Árak > Eladási ár (költség)** részre.
19. Válassza az **Új** lehetőséget.
20. Adja meg a dátumot az **Érvényesség dátuma** mezőben.
21. Az **Érvényes** mezőben válasszon ki egy lehetőséget.
22. Adjon meg egy számot az **Árazás** mezőben. Amikor a dolgozó a költségnaplóba beviszi a tranzakciót, a legrészletesebb szintű eladási ár lesz az aktuális eladási ár. Ha például egy általános és egy dolgozóra vonatkozó eladási ár is be van állítva, akkor a rendszer a dolgozóra vonatkozó eladási árat választja.  
23. Válassza a **Mentés** lehetőséget.


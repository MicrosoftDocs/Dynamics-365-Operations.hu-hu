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
ms.openlocfilehash: 60ab8eb94d4a8a0fb2c1e732ec7b25bfd5e7611e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185405"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a>Munka és kiadások elszámolóárainak konfigurálása

[!include [task guide banner](../../includes/task-guide-banner.md)]

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


--- 
title: "Főkönyvi felosztási napló feldolgozása"
description: "A Felosztási kérés feldolgozása lapon létrehozhat egy felosztási naplót, amelyet a főkönyvbe történő feladás előtt átnézhet és jóváhagyhat. Ha erre nincs szükség, a tranzakciókat közvetlenül is feladhatja a főkönyvbe."
author: aprilolson
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 1189ffeae052c72542b3b403a6b7a6e415b005c4
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="process-ledger-allocation-journal"></a>Főkönyvi felosztási napló feldolgozása

[!include[task guide banner](../../includes/task-guide-banner.md)]

A Felosztási kérés feldolgozása lapon létrehozhat egy felosztási naplót, amelyet a főkönyvbe történő feladás előtt átnézhet és jóváhagyhat. Ha erre nincs szükség, a tranzakciókat közvetlenül is feladhatja a főkönyvbe. Felosztási napló létrehozásához előtt legalább egy aktív Főkönyvi felosztási szabályt be kell állítani. Ez a feladat az USMF bemutatócéget használja.

1. Ugorjon a Főkönyv > Felosztások > Felosztási kérelem feldolgozása pontra.
2. A Szabály mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
3. A kívánt rekord megkeresése és kijelölése a listán
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. A Dátum szerint mezőbe írjon be egy dátumot.
    * A Dátum szerint nagyon fontos, ha a szabályhoz tartozó adatforrás a Főkönyv. Ez a dátum vezérli, hogy mely főkönyvi egyenlegeket szeretné felvenni a felosztáshoz.     A Nulla forrásmezőben válassza ki a Stop elemet. Ezzel a felosztási folyamatot leállítja, és egy üzenet megjelenik arról, hogy a kiválasztott forrás összege nulla.  
6. A Javaslati beállítások mezőben válassza ki a „Csak javaslat” elemet.
    * Válassza a Csak javaslat lehetőséget, ha áttekintené és esetleg jóváhagyná a Felosztási naplók eredményét, mielőtt a felosztást a főkönyvbe feladja.  
7. A GL feladási dátum mezőben adjon meg egy dátumot.
8. Kattintson az OK gombra.
9. Ugorjon a Főkönyv > Felosztások > Felosztási naplók pontra.
10. Kattintson a Sorok pontra.
11. Kattintson a Feladás lehetőségre.
12. Kattintson a Feladás lehetőségre.



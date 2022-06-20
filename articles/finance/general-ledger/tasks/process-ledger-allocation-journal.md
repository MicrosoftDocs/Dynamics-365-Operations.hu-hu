---
title: Főkönyvi felosztási napló feldolgozása
description: Ez a cikk bemutatja a felosztási kérések feldolgozását a Dynamics 365 Pénzügyben.
author: aprilolson
ms.date: 07/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b86f8f5d090d624e812d9e7e6c0bc0212e5e9716
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902429"
---
# <a name="process-ledger-allocation-journal"></a>Főkönyvi felosztási napló feldolgozása

[!include [banner](../../includes/banner.md)]

Ez a cikk bemutatja a felosztási kérések feldolgozását. A Felosztási kérés feldolgozása lapon létrehozhat egy felosztási naplót, amelyet a főkönyvbe történő feladás előtt átnézhet és jóváhagyhat. Ha erre nincs szükség, a tranzakciókat közvetlenül is feladhatja a főkönyvbe. Felosztási napló létrehozásához előtt legalább egy aktív Főkönyvi felosztási szabályt be kell állítani. Ez a feladat az USMF bemutatócéget használja.

1. A navigációs ablakban kattintson **a Főkönyv modul felosztási > és > a Felosztási kérés feldolgozása elemre**.
2. A **Szabály** mező legördülő mezőjében válassza ki a kívánt rekordot.
3. A **Dátum szerint** mezőbe írjon be egy dátumot.

    - A **Dátum szerint** beállítás nagyon fontos, ha a szabályhoz tartozó adatforrás a főkönyv. Ez a dátum vezérli, hogy mely főkönyvi egyenlegeket szeretné felvenni a felosztáshoz.  
    - A **Nulla forrás** mezőben válassza ki a **Leállítás** elemet. Ezzel leállítja a felosztási folyamatot, és egy üzenet jelenik meg arról, hogy a forrás kiválasztott összege nulla.  

4. A **Javaslatbeállítások** mezőben válassza a **Csak javaslat** lehetőséget. Akkor válassza a **Csak javaslat** lehetőséget, ha áttekintené és esetleg jóváhagyná a Felosztási naplók eredményét, mielőtt feladja a felosztást a főkönyvbe.  
5. A GL feladási dátum mezőben adjon meg egy dátumot.
6. Válassza ki az **OK** lehetőséget.
7. A navigációs ablakban lépjen a **Modulok > Főkönyv > Felosztások > Felosztási naplók** részre.
8. **Sorok** kiválasztása.
9. Válassza a **Feladás** parancsot.
10. Válassza a **Feladás** parancsot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

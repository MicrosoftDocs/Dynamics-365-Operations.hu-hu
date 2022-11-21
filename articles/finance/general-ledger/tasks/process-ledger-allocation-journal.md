---
title: Főkönyvi felosztási napló feldolgozása
description: Ez a cikk bemutatja a felosztási kérések feldolgozását a Dynamics 365 Pénzügyben.
author: aprilolson
ms.date: 11/15/2022
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
ms.openlocfilehash: 1f22b5042e0e3726afcb1061852fdbd8de770c61
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779392"
---
# <a name="process-ledger-allocation-journal"></a>Főkönyvi felosztási napló feldolgozása

[!include [banner](../../includes/banner.md)]

Ez a cikk bemutatja a felosztási kérések feldolgozását. A Felosztási **kérés** feldolgozása lapon létrehozhat egy felosztási naplót, amely áttekinthető és jóváhagyható a főkönyvbe történő feladás előtt, illetve amely közvetlenül a főkönyvbe is feladható. Felosztási napló létrehozásához előtt legalább egy aktív Főkönyvi felosztási szabályt be kell állítani. Ez a feladat az USMF bemutatócéget használja.

1. A navigációs ablakban kattintson **a Főkönyv modul felosztási > és > a Felosztási kérés feldolgozása elemre**.
2. A **Szabály** mező legördülő mezőjében válassza ki a kívánt rekordot.
3. A **Dátum szerint** mezőbe írjon be egy dátumot.

    - A **Dátum szerint** beállítás nagyon fontos, ha a szabályhoz tartozó adatforrás a főkönyv. Ez a dátum vezérli, hogy mely főkönyvi egyenlegeket szeretné felvenni a felosztáshoz.  
    - A **Nulla forrás** mezőben válassza ki a **Leállítás** elemet. Ezzel leállítja a felosztási folyamatot, és egy üzenet jelenik meg arról, hogy a forrás kiválasztott összege nulla.  

4. A **Javaslatbeállítások** mezőben válassza a **Csak javaslat** lehetőséget. Csak **a Felosztási** naplók eredményének **a** főkönyvbe történő feladása előtt válassza a Javaslat lehetőséget, és tetszés szerint hagyja jóvá az eredményt.  
5. Adjon meg egy dátumot a főkönyvi **feladási** dátum mezőben.
6. Válassza ki az **OK** lehetőséget.
7. A navigációs ablakban lépjen a **Modulok > Főkönyv > Felosztások > Felosztási naplók** részre.
8. **Sorok** kiválasztása.
9. Válassza a **Feladás** parancsot.
10. Válassza a **Feladás** parancsot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

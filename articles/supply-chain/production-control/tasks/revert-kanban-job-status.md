--- 
title: "Kanbanfeladat állapotának visszaállítása"
description: "Ez az eljárás egy helytelen kanbanfeladat-állapot visszaállítására irányul."
author: ShylaThompson
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 55d359232da5f3087b1e6baed182a20da09aeff7
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="revert-kanban-job-status"></a>Kanbanfeladat állapotának visszaállítása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás egy helytelen kanbanfeladat-állapot visszaállítására irányul. Ez abban az esetben hasznos, ha egy hiba folytán a gépkezelő rossz feladatot frissít vagy rossz állapotot állít be. Ebben az eljárásban a kanbanfeladat egy hiba folytán előkészítettként lett rögzítve, ez az állapot kerül visszaállításra. Ez az eljárás az USMF bemutatócéget használja. Ez az eljárás egy lean manufacturing vállalatban dolgozó művezető vagy gépkezelő számára javasolt.


## <a name="open-process-board-for-the-work-cell"></a>Nyissa meg a munkacella feldolgozási tábláját
1. Ugorjon a feldolgozási feladatok kanbantáblájára.
2. A Munkacella mezőben adjon meg vagy válasszon ki egy értéket.
    * Jelölje ki az 1260 munkacellát.  

## <a name="prepare-kanban-job"></a>Kanbanfeladat előkészítése
1. Kattintson az Előkészítés lehetőségre.
    * Ha nem tud az Előkészítés gombra kattint, mert az beszűrkített, győződjön meg arról, hogy a kijelölt kanbanfeladat állapota tervezett, amelyet az üres kanban ikon mutat. Ha az Előkészítés sikertelen, győződjön meg arról, hogy elérhető-e az összes anyag a kitárolási listában.  
2. Válassza ki a listában az előkészített feladatot.
    * Válassza ki az első, most elkészített feladatot.  
    * Figyelje meg, hogy a feladat előkészített állapotba került, amelyet a kanban ikonjában megjelenő háromszög jelez.  

## <a name="revert-the-status-of-the-prepared-kanban-job"></a>Az előkészített kanbanfeladat állapotának visszaállítása
1. A listában jelölje meg a kiválasztott sort.
    * Válassza ki az első elkészített feladatot.  
2. A Művelet panelen kattintson a Gyártás elemre.
3. Kattintson az Állapot visszaállítása lehetőségre.
    * Alternatív kanbanszabály abban az esetben alkalmazható, ha teljesülnek a következő feltételek: – A feltöltési stratégia a két szabály esetén megegyezik.  - A termelési folyamat verziója a két szabály esetén megegyezik.  - A megadott termék a két szabály esetén megegyezik.  - A két szabály esetén meg kell egyeznie minden, a kanbanszabályok utolsó műveletére konfigurált lefelé irányuló tevékenységnek.  - Mindkét szabály esetén ugyanazokat a megadott készletdimenziókat kell beállítani.  - Az anyagkezelési egység állapota legyen Nincs hozzárendelve.  - Az eseménykanbanok konfigurációjának azonosnak kell lennie.  
    * Győződjön meg róla, hogy az új állapot: Tervezett.  
4. Kattintson az OK gombra.
5. A listában szüntesse meg a kiválasztott sor megjelölését.
    * Válassza ki ugyanazt a feladatot.  
    * Figyelje meg, hogy a feladat visszaállt Tervezett állapotba, amelyet az üres kanban ikon jelez.  



--- 
title: " POS-engedélycsoportok létrehozása"
description: "Ez az eljárás bemutatja, hogyan hozhat létre új POS-engedélycsoportot."
author: scott-tucker
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
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: b0c930e3722d1d0b1fff8efad7a785a153436b6d
ms.contentlocale: hu-hu
ms.lasthandoff: 07/28/2017

---
# <a name="create-pos-permission-groups"></a> POS-engedélycsoportok létrehozása

[!include[task guide banner](../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan hozhat létre új POS-engedélycsoportot. A feladat létrehozásához az USRT bemutató vállalatot használtuk példaként. A feladat a Kiskereskedelmi üzemeltetési vezető szerepkör számára készült.

1. Nyissa meg a következőt: Engedélycsoportok.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a POS-engedélycsoport azonosítója mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. Válassza ki az Igen lehetőséget a Blokkolóóra bejegyzéseinek megtekintése mezőben.
    * Most engedélyezheti vagy a letilthatja a POS-engedélycsoport különféle engedélyeit. Egyes engedélyekhez beállíthat egy értéket, amely meghatározza, hogy a pénztári felhasználó végrehajthatja-e az adott műveletet.  Ez a feladat-útmutató beállít néhány, pénztárosoknak adható engedélyt.  
6. Válassza ki az Igen lehetőséget a Rendelés létrehozásának engedélyezése mezőben.
7. Válassza ki az Igen lehetőséget a Rendelés szerkesztésének engedélyezése mezőben.
8. Válassza ki az Igen lehetőséget a Rendelés beolvasásának engedélyezése mezőben.
9. Válassza ki az Igen lehetőséget a Jelszómódosítás engedélyezése mezőben.
10. Válassza ki az Igen lehetőséget a Számlálás nélküli zárás engedélyezése mezőben.
11. Kattintson a Mentés gombra.
    * A módosítások mentése után futtatnia kell a Személyzetelosztási ütemezést, hogy leküldje a változtatásokat a kiskereskedelmi csatornákba.  
12. Zárja be a lapot.
13. Nyissa meg a következőt: Feladatok.
    * A következőkben hozzárendelünk egy POS-engedélycsoportot egy Feladathoz.  
14. Keresse meg és jelölje ki a kívánt rekordot a listán.
15. A listában kattintson a kijelölt sorban lévő hivatkozásra.
16. Kattintson a Szerkesztés lehetőségre.
17. Bontsa ki a Munkaköri besorolás szakaszt.
18. A POS-engedélycsoport mezőben adjon meg, vagy válasszon ki egy értéket.
    * Minden, ehhez a Feladathoz rendelt Pozícióban lévő Dolgozó ennek a POS-engedélycsoportnak a beállításait fogja használni, kivéve, ha a dolgozók POS-engedélyeit a Pozíció szintjén felülbírálták.  
19. Kattintson a Mentés gombra.
    * A módosítások mentése után futtatnia kell a Személyzetelosztási ütemezést, hogy leküldje a változtatásokat a kiskereskedelmi csatornákba.  



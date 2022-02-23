---
title: Feladatkörök szétválasztásának beállítása
description: Beállíthat szabályokat a más felhasználók által elvégzendő feladatok elválasztásához.
author: peakerbl
manager: AnnBe
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bcbd32131f9980a4f55e91b9d7ad48171069f72e
ms.sourcegitcommit: 316200579dd5b04ad76f276a2ed6b0f55fa8c812
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/05/2021
ms.locfileid: "4826394"
---
# <a name="set-up-segregation-of-duties"></a>Feladatkörök szétválasztásának beállítása

[!include [banner](../../includes/banner.md)]

Beállíthat szabályokat a más felhasználók által elvégzendő feladatok elválasztásához. Ezt a fogalmat a feladatkörök szétválasztásának nevezzük. Például nem biztos, hogy ugyanannak a személynek kell az árut átvennie és a szállítói kifizetést is feldolgoznia. A feladatkörök szétválasztása segít a csalás kockázatának csökkentésében, illetve a hibák és a szabálytalanságok észlelésében. Használhatja a feladatkörök szétválasztását a belső ellenőrzési irányelvek végrehajtásához is. A szabály létrehozásához hajtsa végre a következő lépéseket. Csak egy rendszergazda hajthatja végre ezt a műveletet.

1. Ugrás a **Rendszerfelügyelet** > **Biztonság** > **Feladatkörök szétválasztása** > **Feladatkör-szétválasztási szabályok** elemre.
2. Kattintson az **Új** elemre.
3. A **Név** mezőben adja meg a szabályhoz tartozó értéket.
4. Az **Első feladat** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
5. Keresse meg és jelölje ki a kívánt rekordot a listán. Válassza ki azt az első feladatot, amelyet a szabály határoz meg.
6. A **Második feladat** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához. 
7. Keresse meg és jelölje ki a kívánt rekordot a listán. Válassza ki azt a második feladatot, amelyet a szabály határoz meg.
10. Válasszon egy lehetőséget a **Súlyosság** mezőben. Válassza ki azt a kockázatot, amely akkor lép fel, amikor ugyanaz a felhasználó vagy szerepkör hajtja végre mindkét feladatot.  
11. Írjon be egy értéket a **Biztonsági kockázat** mezőbe. Írja be a biztonsági kockázat leírását.  
12. Írjon be egy értéket a **Biztonsági kockázatcsökkentés** mezőbe. Írja le a műveleteket, amelyeket a biztonsági kockázat enyhítése érdekében vezet be. A kockázatot enyhítheti például úgy, hogy részletesebb áttekintés ad a folyamatnak, havi vezetői ellenőrzést vezet be, vagy más részlegekkel is megoszt erőforrásokat.     
13. Kattintson a **Mentés** gombra.

> [!IMPORTANT] 
> A szabályok létrehozása során a rendszer nem ellenőrzi a feladatkörök szétválasztására vonatkozó szabályoknak való megfelelést. Létrehozhat olyan szabályt, amely ütközik a meglévő szerepkörökkel. A felhasználói szerepkör meglévő hozzárendelései az új szabállyal is ütközhetnek. A szabályok létrehozása vagy módosítása után ellenőriznie kell a megfelelést. További információk: [Feladatkörök szétválasztásával kapcsolatos ütközések azonosítása és feloldása](identify-resolve-conflicts-segregation-duties.md)

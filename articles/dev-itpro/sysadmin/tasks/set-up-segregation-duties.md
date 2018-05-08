--- 
title: "Feladatkörök szétválasztásának beállítása"
description: "Beállíthat szabályokat a más felhasználók által elvégzendő feladatok elválasztásához."
author: maertenm
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 754f28cd2831d8a9a57c408518d240de460b732b
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-segregation-of-duties"></a>Feladatkörök szétválasztásának beállítása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Beállíthat szabályokat a más felhasználók által elvégzendő feladatok elválasztásához. Ezt a fogalmat a feladatkörök szétválasztásának nevezzük. Például nem biztos, hogy ugyanannak a személynek kell az árut átvennie és a szállítói kifizetést feldolgoznia. A feladatkörök szétválasztása segít a csalás kockázatának csökkentésében, illetve a hibák és a szabálytalanságok észlelésében. Használhatja a feladatkörök szétválasztását a belső ellenőrzési irányelvek végrehajtásához is. A szabály létrehozásához hajtsa végre a következő lépéseket. Csak egy rendszergazda hajthatja végre ezt a műveletet. Ez az eljárás a DAT bemutatócéggel jött létre. 

1. Ugrás a Rendszerfelügyelet > Biztonság > Feladatkörök szétválasztása > Feladatkör-szétválasztási szabályok elemre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Név mezőbe.
    * Adja meg a szabály nevét.  
4. Az első feladat mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
5. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válassza ki azt az első feladatot, amelyet a szabály határoz meg.  
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.
7. A második feladat mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
8. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válassza ki azt a második feladatot, amelyet a szabály határoz meg.  
9. A listában kattintson a kijelölt sorban lévő hivatkozásra.
10. Válasszon egy lehetőséget a Súlyosság mezőben.
    * Válassza ki azt a kockázatot, amely akkor lép fel, amikor ugyanaz a felhasználó vagy szerepkör hajtja végre mindkét feladatot.  
11. Írjon be egy értéket a Biztonsági kockázat mezőbe.
    * Írja be a biztonsági kockázat leírását.  
12. Írjon be egy értéket a Biztonsági kockázatcsökkentés mezőbe.
    * Írja le a műveleteket, amelyeket a biztonsági kockázat enyhítése érdekében vezet be. A kockázatot enyhítheti például úgy, hogy részletesebb áttekintés ad a folyamatnak, havi vezetői ellenőrzést vezet be, vagy más részlegekkel is megoszt erőforrásokat.  
13. Kattintson a Mentés gombra.



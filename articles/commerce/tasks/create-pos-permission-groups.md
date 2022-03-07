---
title: POS-engedélycsoportok létrehozása
description: Ez a témakör a pénztár engedélycsoport létrehozásának lépéseit mutatja be.
author: scott-tucker
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailPosPermissionGroup, HcmJob
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b2439d1912b3ca013f4a524f3354923d2a3f76ca
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5221281"
---
# <a name="create-pos-permission-groups"></a>POS-engedélycsoportok létrehozása

[!include [banner](../includes/banner.md)]

Ez a témakör a pénztár engedélycsoport létrehozásának lépéseit mutatja be. A feladat létrehozásához az USRT bemutató vállalatot használtuk példaként. Ez a feladat Kereskedelmi üzemeltetési vezető szerepkörhöz tartozik.

1. A navigációs ablakban nyissa meg a **Modulok > Kiskereskedelem és kereskedelem > Alkalmazottak > Engedélycsoportok** elemet.
2. Válassza az **Új** lehetőséget.
3. Írjon be egy értéket a **POS-engedélycsoport azonosítója** mezőbe.
4. Írjon egy értéket a **Leírás** mezőbe.
5. Válassza ki az **Igen** lehetőséget a **Blokkolóóra bejegyzéseinek megtekintése** mezőben. Most engedélyezheti vagy a letilthatja a POS-engedélycsoport különféle engedélyeit. Egyes engedélyekhez beállíthat egy értéket, amely meghatározza, hogy a pénztári felhasználó végrehajthatja-e az adott műveletet. Ez a feladat-útmutató beállít néhány, pénztárosoknak adható engedélyt.  
6. Válassza ki az **Igen** lehetőséget a **Rendelés létrehozásának engedélyezése** mezőben.
7. Válassza ki az **Igen** lehetőséget a **Rendelés szerkesztésének engedélyezése** mezőben.
8. Válassza ki az **Igen** lehetőséget a **Rendelés beolvasásának engedélyezése** mezőben.
9. Válassza ki az **Igen** lehetőséget a **Jelszómódosítás engedélyezése** mezőben.
10. Válassza ki az **Igen** lehetőséget a **Számlálás nélküli zárás engedélyezése** mezőben.
11. Válassza a **Mentés** lehetőséget. A módosítások mentése után futtatnia kell a Személyzetelosztási ütemezést, hogy leküldje a változtatásokat a kereskedelmi csatornákba. 
12. Ugorjon a Navigációs ablaktábla **Modulok > Emberi erőforrások > Állások > Állások** lehetőségre.
13. A következőkben hozzárendelünk egy POS-engedélycsoportot egy Feladathoz. Keresse meg és jelölje ki a kívánt rekordot a listán.
14. Válassza ki a **Szerkesztés** opciót.
15. Bontsa ki a **Munkaköri besorolás** szakaszt.
16. A POS-engedélycsoport mezőben adjon meg, vagy válasszon ki egy értéket. Minden, ehhez a Feladathoz rendelt Pozícióban lévő Dolgozó ennek a pénztár-engedélycsoportnak a beállításait fogja használni, kivéve, ha a dolgozók pénztár-engedélyeit a Pozíció szintjén felülbírálták.  
17. Válassza a **Mentés** lehetőséget. A módosítások mentése után futtatnia kell a Személyzetelosztási ütemezést, hogy leküldje a változtatásokat a csatornákba.  



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
---
title: Pénztári engedélycsoportok létrehozása
description: Ez a cikk bemutatja a POS-engedélycsoport létrehozásához szükséges szükséges engedélyeket.
author: josaw1
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.industry: Retail
ms.search.form: RetailPosPermissionGroup, HcmJob
ms.openlocfilehash: 0aa394e5dc6685954c31cdddae7cdc042b80af29
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277960"
---
# <a name="create-pos-permission-groups"></a>Pénztári engedélycsoportok létrehozása

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja a POS-engedélycsoport létrehozásához szükséges szükséges engedélyeket. A feladat létrehozásához az USRT bemutató vállalatot használtuk példaként. Ez a feladat Kereskedelmi üzemeltetési vezető szerepkörhöz tartozik.

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

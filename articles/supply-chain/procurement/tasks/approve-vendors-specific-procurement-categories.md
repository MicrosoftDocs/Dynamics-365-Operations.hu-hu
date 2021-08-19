---
title: Szállítók jóváhagyása konkrét beszerzési kategóriákra vonatkozóan
description: Ez a témakör azt mutatja be, hogyan lehet jóváhagyni a Dynamics 365 Supply Chain Management megoldásban szállítókat az egyes beszerzési kategóriákhoz.
author: kamaybac
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable, DirPartyEcoResCategory, EcoResCategorySingleLookup, ProcCategoryHierarchyManagement
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 65a42e10edda7b492e86029ca05655d7c0175c23589dc55573c7ac5976e820d3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6717214"
---
# <a name="approve-vendors-for-specific-procurement-categories"></a>Szállítók jóváhagyása konkrét beszerzési kategóriákra vonatkozóan

[!include [banner](../../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet jóváhagyni a Dynamics 365 Supply Chain Management megoldásban szállítókat az egyes beszerzési kategóriákhoz. Amikor egy beszerzési igénylést hoznak létre, lehet szükséges lesz egy engedélyezett vagy preferált szállító kiválasztása, attól függően, hogy a beszerzési irányelvek hogy vannak beállítva. Ez az eljárás bemutatja, hogyan adja meg, hogy a szállító jóváhagyott vagy preferált egy adott beszerzési kategóriához. Ezt a feladatot általában egy beszerzési szakember végzi el. Az USMF bemutatócég adataiban használhatja ezt az eljárást.

1. A Navigációs ablaktáblán válassza a **Modulok > Beszerzés és forrás > Szállítók > Összes beszállító** elemet.
2. Válassza ki a szállítót, amelyet be szeretne állítani a kategóriához jóváhagyott vagy preferált szállítóként.
3. A Művelet ablaktáblán válassza ki az **Általános** elemet.
4. Válassza a **Kategóriák** elemet.
5. Válassza a **Kategória hozzáadása** elemet.
6. A **Kategória** mezőben válassza ki az **OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES)** lehetőséget.
7. A **Szállítói kategória állapot** mezőben válassza ki az **Elsődleges** lehetőséget. Lehetőség van arra, hogy egy kategóriához több mint egy elsődleges szállítót határozzon meg.  
8. Válassza a **Mentés** lehetőséget.
9. A navigációs ablaktáblában menjen a **Modulok > Beszerzés és forrás > Beszerzési kategóriák** menübe.
10. A fán válassza a **CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES** pontot.
11. Bontsa ki a **Szállító** szakaszt. Ellenőrizze, hogy a kiválasztott szállító jelenik-e meg az Office és asztali kellékek kategória elsődleges szállítójaként. Ha feladat útmutatójaként használata ezt az eljárást, előfordulhat, hogy ki kell választania a **Feloldás** gombot, hogy letudja görgetni a szállítók listáját.  Ezen az oldalon lehetséges elsődleges és engedélyezett szállítók hozzáadása.  
12. A fában bontsa ki az **OFFICE AND DESK ACCESSORIES** elemet, és válassza az **ollót**.
13. Válassza a **Nem** lehetőséget a **Szállítók öröklése szülőkategóriától:** mezőben.
14. Válassza az **Igen** lehetőséget a **Szállítók öröklése szülőkategóriától:** mezőben.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
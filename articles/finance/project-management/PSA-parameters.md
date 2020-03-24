---
title: Project Service Automation – integrálási paraméterek
description: Ez a témakör bemutatja, hogyan kell konfigurálni azt, hogyan legyenek megadva az alapértelmezett adatok a Microsoft Dynamics 365 for Project Service Automation és a Microsoft Dynamics 365 Finance integrálása során.
author: KimANelson
manager: AnnBe
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: cd09dad15112fd71bfd386e0072a77a4121c96e0
ms.sourcegitcommit: 236672932ffd0a758012ebb7b2df9bc51249c126
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096251"
---
# <a name="project-service-automation-integration-parameters"></a>Project Service Automation integráció paraméterei

[!include[banner](../includes/banner.md)]

A **Project Service Automation integrációs paraméterei** lapon beállíthatja, hogyan legyenek megadva az alapértelmezett adatok a Dynamics 365 Project Service Automation és Dynamics 365 Finance integrációja során. A következő mezőket be kell állítani a projektekhez, hogy sikeresen szinkronizálni lehessen a Project Service Automation alkalmazásból a Finance alkalmazásba.

A **Project Service Automation integrációs paraméterei** lap megnyitásához válassz a **Projektmenedzsment és könyvelés** \> **Beállítások** \> **Dynamics 365 for Project Service Automation integrációs paraméterek** elemet. 

> [!NOTE]
> - Ha a 8.0-ás verzióját használja a projektfeladat integrációja, költségtranzakció-kategóriák, munkaóra-becslés, költségbecslések és a funkciók zárolása funkciókat használhatja.
> - Tényleges integráció a 8.0.1 vagy újabb verzióiban érhető el.


| Tab                    | Mező                | Leírás |
|------------------------|----------------------|-------------|
| Általános                | Alapértelmezett projekttípus | Válassza ki az alapértelmezett projekttípust. Válassza ki a Projekttípus alapértelmezett értékét, amely akkor használatos, ha a Project Service Automationből szinkronizál projekteket, és nem adott meg alapértelmezett értéket az integrációs sablonban. A szinkronizálás során a **Projekttípus** mező az újprojektekben van erre az értékre állítva. Azonban az érték lehet, hogy frissítve lesz amikor projektszerződés sorok szinkronizálva vannak a Project Service Automation alkalmazásból. |
|                        | Időkategória        | Az alapértelmezett időkategória kiválasztása. Órabecslések szinkronizálása a Project Service Automation alkalmazásból ezt az értéket használja. Az órabecslések és aktuális órák szinkronizálása során a Project Service Automation alkalmazásból ez lesz a **Kategória** mező értéke az új projektóra becslésekben a Finance alkalmazásban. |
|                        | Díj kategóriája         | Az alapértelmezett díjkategória kiválasztása. Az aktuális díjak szinkronizálása a Project Service Automation alkalmazásból ezt az értéket használja. Az aktuális díjak szinkronizálása során a Project Service Automation alkalmazásból a Finance alkalmazásban ez lesz a **Kategória** mező értéke, amikor az új díjtranzakciókat szinkronizálják. |
| Projektcsoport alapértelmezett beállításai | Projekt típusa         | Kattintson az **Új** elemre egy sor hozzáadásához, ahol kiválaszthatja a projekttípust, amelyhez beállítja az alapértelmezett projektcsoport. Egy adott projekttípus csak egy alkalommal választható ki a konfigurációban. |
|                        | Projektcsoport        | Válassza ki a megadott projektcsoportot a megadott projekttípushoz. Amikor új projekteket szinkronizál a Project Service Automation alkalmazásból, a **Projektcsoport** az alapértelmezett értékre lesz beállítva a projekttípushoz, ha nem adott meg alapértelmezett értéket az integrációs sablonban. |
| Számlázási típus alapértelmezései  | Számlázás típusa         | Kattintson az **Új** elemre egy sor hozzáadásához ahol kiválaszthatja a számlázás típusát, melyhez beállítja az alapértelmezett sortulajdonságot. Egy adott számlázási típus csak egy alkalommal választható ki a konfigurációban. |
|                        | Sortulajdonság        | Az alapértelmezett sortulajdonság kiválasztása a kiválasztott számlázástípushoz. Amikor új becsült órák, az új becsült kiadások vagy új tényleges adatok szinkronizálása történik a Project Service Automation alkalmazásból a **Sortulajdonság** az alapértelmezett értékhez lesz beállítva a számlázási típushoz. |
| Funkció zárolása  | Nem alkalmazható       | Válassza ki a letiltandó funkciót a Finance alkalmazásban a projektekhez és a szerződésekhez, amelyek a Project Service Automation alkalmazásból származnak. Például úgy kikapcsolhatja a szerződések és projektek szerkesztése, munkalebontási struktúrák létrehozása, és munkaidő-nyilvántartások megadásának lehetőségét a Finance rendszerben. Könyveléssel kapcsolatos mezők továbbra is engedélyezve lesznek még akkor is, ha azok elérhetetlenné vannak téve a paraméter beállításával. Alapértelmezés szerint az összes funkciót engedélyezve lesz. |

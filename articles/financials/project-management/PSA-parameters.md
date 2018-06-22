---
title: "Project Service Automation – integrálási paraméterek"
description: "Beállíthatja, hogy hogyan viselkedjenek az adatok a Project Service Automation és Dynamics 365 for Finance and Operations integrációja esetén."
author: KimANelson
manager: AnnBe
ms.date: 12/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 32f7f70c5b1071cef5a3360ccc09fa2d95fbf9a9
ms.contentlocale: hu-hu
ms.lasthandoff: 05/29/2018

---

# <a name="project-service-automation-integration-parameters"></a>Project Service Automation – integrálási paraméterek

A **Project Service Automation integrációs paraméterek** oldalon, hogyan viselkedjenek az adatok a Project Service Automation és Finance and Operations integrálása esetén. A következő be kell állítani a projektekhez, hogy sikeresen szinkronizálni lehessen a Project Service Automationből a Finance and Operationsbe.

> [!NOTE]
> Projektfeladatok integrációja, költségtranzakció-kategóriák, munkaóra-becslés, költségbecslések és a funkciók zárolása a Dynamics 365 for Finance and Operations 8.0-ás verziójában érhető el.




| **Lap**                      | **Mező**                          | **Leírás**                    |
|------------------------------|------------------------------------|--------------------------------|
| **Általános**                  | **Alapértelmezett projekttípus**               | Válassza ki a **Projekttípus** alapértelmezett értékét, amely akkor használatos, ha a Project Service Automationből szinkronizál projekteket, ha nem adott meg alapértelmezett értéket az integrációs sablonban. A szinkronizálás során új projektek **Projekttípusa** erre az értékre lesz állítva és esetleg frissíthető, ha szerződés projektsorokat szinkronizál a Project Service Automation alkalmazásból.               |
| **Általános**                  | **Időkategória**                      | Válassza ki az alapértelmezettértéket az **Időkategória** elemhez, mely akkor használatos, amikor a becsült órák szinkronizálása történik a Project Service Automation alkalmazásból. A szinkronizálás során új projekt óra-előrejelzéseihez Finance and Operations alkalmazásban ez lesz a **Kategória** értéke, amikor a becsült órákat és a valós órákat szinkronizálják a Project Service Automationből..   |
| **Általános**                  | **Díj kategóriája**                       | Válassza ki az alapértelmezett értéket az **Díjkategória** elemhez, mely akkor használatos, amikor a valós díjak szinkronizálása történik a Project Service Automation alkalmazásból. A szinkronizálás során új díjtranzakciókhoz Finance and Operations alkalmazásban ez lesz a **Kategória** értéke, amikor a valós díjakat szinkronizálják a Project Service Automationből.          |
| **Projektcsoport alapértelmezett beállításai**   | **Projekt típusa** | Kattintson az **Új** elemre egy sor hozzáadásához ahol kiválaszthatja a projekttípust, amelyhez beállítja az alapértelmezett projektcsoport. Egy adott projekttípus csak egyszer választható ki a konfigurációban.              
|                              | **Projektcsoport**          | A megadott projektcsoport kiválasztása a megadott projekttípushoz. Amikor új projekteket szinkronizál a Project Service Automation alkalmazásból, a **Projektcsoport** lesz az alapértelmezett a projekttípus alapján, ha nem adott meg alapértelmezett értéket az integrációs sablonban.  |
| **Számlázási típus alapértelmezései**    | **Számlázás típusa** | Kattintson az **Új** elemre egy sor hozzáadásához ahol kiválaszthatja a számlázás típusát, amelyhez beállítja az alapértelmezett sortulajdonságot. Egy adott számlázástípus csak egyszer választható ki a konfigurációban.          |
|                              | **Sortulajdonság**| Az alapértelmezett sortulajdonság kiválasztása a megadott számlázástípushoz. Amikor új becsült órák, az új becsült kiadások vagy új tényleges adatok szinkronizálása történik a Project Service Automation alkalmazásból a **Sortulajdonság** lesz az alapértelmezett a számlázási típus alapján.          |
| **Funkció zárolása**    |                   | Válassza ki a letiltandó funkciót a Finance and Operations alkalmazásban a projektekhez és a szerződésekhez, amelyek a Project Service Automation alkalmazásból származnak. Például úgy dönthet, hogy kikapcsolja a szerződések és projektek szerkesztése, munkalebontási struktúrák létrehozása, és munkaidő-nyilvántartások megadásának lehetőségét a Finance and Operations rendszerben. Könyveléssel kapcsolatos mezők továbbra is engedélyezve lesznek még akkor is, ha azok elérhetetlenné vannak téve a paraméter beállításával. Alapértelmezés szerint az összes funkciót engedélyezve van.           |


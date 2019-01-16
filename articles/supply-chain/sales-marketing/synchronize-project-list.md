---
title: "Projektlista szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service közötti projektszinkronizálásra használhatók."
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.translationtype: HT
ms.sourcegitcommit: 8c6cb481f1a3fe48d329c5936118d8df88a4175b
ms.openlocfilehash: adcb1c1b241ce2b073cd26cf2a8a8d64931c8b0f
ms.contentlocale: hu-hu
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a>Projektlista szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba

[!include[banner](../includes/banner.md)]

Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service közötti projektszinkronizálásra használhatók.

[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSProjectOW.png)](./media/FSProjectOW.png)

## <a name="templates-and-tasks"></a>Sablonok és feladatok
A következő sablon és a kapcsolódó feladatok a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service közötti projektszinkronizálás futtatására használhatók.

**A sablon neve az adatintegrációban:**
- Projektek (a Finance and Operations megoldásból a Field Service megoldásba)

**A feladatok nevei az adatintegrációs projektben:**
- Projektek

A következő szinkronizálási feladatok kötelezők, mielőtt a projektlisták szinkronizálása megtörténhetne:
- Fiókok (a Sales megoldásból a Finance and Operations megoldásba) 

## <a name="entity-set"></a>Entitás beállítása
Field Service   Finance and Operations

| Field Service           | Finance and Operations  |
|-------------------------|-------------------------|
|msdynce_externalprojects | Projektek                |

## <a name="entity-flow"></a>Entitás folyamata
A projektek létrehozása a Finance and Operations alkalmazásban történik. A projektek, amelyek esetében a **Projekttípus** Idő és anyag, a **Projektfokozat** pedig Folyamatban, a Field Service **Külső projekt** entitásába szinkronizálódnak, a következő információkat beleértve: projekt száma, projektnév, projektfokozat és vevői számla adatai. A **Külső projekt** listát a rendszer a Field Service munkarendelések és a Finance and Operations projektek párosítására használja.
A Külső projekt Field Service CRM megoldás új entitás, amely minden projekt lekérés az Operations megoldásból.
A Külső projekt mezőt hozzáadtuk a munkarendelés entitáshoz. Ez a mező egy keresés és vásárlás, felcímkézi a Munkarendelést egy projekttel, majd az értékesítési rendelés kapcsolódik egy projekthez az Operations megoldáson belül. Miután a rendszer állapota Nyitott – folyamatban (690,970,000) magasabb állapba kerül, a külső projekt mezőt a rendszer zárolja, és nem lehet felvenni, törölni vagy módosítani az értéket.

## <a name="prerequisites-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás
### <a name="in-finance-and-operations"></a>A Finance and Operations alkalmazásban
A változáskövetés engedélyezése az adatentitás projektekhez

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban


### <a name="projects-finance-and-operations-to-field-service-projects"></a>Projektek (a Finance and Operations megoldásból a Field Service megoldásba): Projektek

[![Sablonleképezés az adatintegrátorban](./media/FSProject1.png)](./media/FSProject1.png)


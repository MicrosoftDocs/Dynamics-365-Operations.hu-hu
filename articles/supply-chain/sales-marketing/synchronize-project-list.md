---
title: Projektlista szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Microsoft Dynamics 365 for Finance and Operations projektjeinek a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: ea5c188891bb97ba73d2d022e86bbff50897381b
ms.sourcegitcommit: a6d385db6636ef2b7fb6b24d37a2160c8d5a3c0f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "842604"
---
# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a>Projektlista szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba

[!include[banner](../includes/banner.md)]

Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Microsoft Dynamics 365 for Finance and Operations projektjeinek a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.

[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSProjectOW.png)](./media/FSProjectOW.png)

## <a name="templates-and-tasks"></a>Sablonok és feladatok
A következő sablonok és a mögöttes tevékenységek használatosak a projektek szinkronizálásához a Microsoft Dynamics 365 for Finance and Operations alkalmazásból a Microsoft Dynamics 365 for Field Service alkalmazásba.

**Sablon az adatintegrációban**
- Projektek (a Fin and Ops megoldásból a Field Service megoldásba)

**Feladat az adatintegrációs projektben**
- Projektek

A következő szinkronizálási feladatok kötelezők, mielőtt a projektlisták szinkronizálása megtörténhetne:
- Számlák (Sales – Fin and Ops) 

## <a name="entity-set"></a>Entitás beállítása
| Field Service           | Finance and Operations  |
|-------------------------|-------------------------|
|msdynce_externalprojects | Projektek                |

## <a name="entity-flow"></a>Entitás folyamata
A projektek létrehozása a Finance and Operations alkalmazásban történik. A projektek, amelyek esetében a **Projekttípus** **Idő és anyag**, a **Projektfokozat** pedig **Folyamatban**, a Field Service **Külső projekt** entitásába szinkronizálódnak, a következő információkat beleértve: projekt száma, projektnév, projektfokozat és vevői számla adatai. A **Külső projekt** listát a rendszer a Field Service munkarendelések és a Finance and Operations projektek párosítására használja.

## <a name="field-service-crm-solution"></a>Field Service CRM megoldás
A **Külső projekt** entitás lekér minden projektet a Finance and Operations rendszerből. A **Külső projekt** mezőt hozzáadtuk a **Munkarendelés** entitáshoz. Ez a mező egy keresőmező felcímkézi a munkarendelést egy projekttel, majd az értékesítési rendelés kapcsolódik egy projekthez a Finance and Operations megoldáson belül. Miután a **Rendszer állapota** **Nyitott – folyamatban (690,970,000)** állapotból magasabb állapba kerül, a **Külső projekt** mezőt a rendszer zárolja, és a továbbiakban nem lehet felvenni, törölni vagy módosítani az értéket.

## <a name="prerequisites-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás
### <a name="finance-and-operations"></a>Finance and Operations
A változáskövetés engedélyezése az Adatentitás projektekhez.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban


### <a name="projects-fin-and-ops-to-field-service-projects"></a>Projektek (a Fin and Ops megoldásból a Field Service megoldásba): Projektek

[![Sablonleképezés az adatintegrátorban](./media/FSProject1.png)](./media/FSProject1.png)

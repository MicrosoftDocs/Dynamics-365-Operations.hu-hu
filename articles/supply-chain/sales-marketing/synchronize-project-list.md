---
title: Projektlista szinkronizálása a Supply Chain Management alkalmazásból a Field Service alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Supply Chain Management projektjeinek a Dynamics 365 Field Service szolgáltatásba történő szinkronizálására használatosak.
author: Henrikan
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: b825e2fce61e96b963ba0d41f8db49ca9ba646f6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571593"
---
# <a name="synchronize-project-list-from-supply-chain-management-to-field-service"></a>Projektlista szinkronizálása a Supply Chain Management alkalmazásból a Field Service alkalmazásba

[!include[banner](../includes/banner.md)]

Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Supply Chain Management projektjeinek a Dynamics 365 Field Service szolgáltatásba történő szinkronizálására használatosak.

[![Üzleti folyamatok szinkronizálása a Supply Chain Management és a Field Service között.](./media/FSProjectOW.png)](./media/FSProjectOW.png)

## <a name="templates-and-tasks"></a>Sablonok és feladatok
A következő sablonokat és alapul szolgáló feladatokat használják a projektszinkronizálás futtatásához a Supply Chain Management és a Field Service között:

**Sablon az adatintegrációban**
- Projektek (Supply Chain Management és Field Service között)

**Feladat az adatintegrációs projektben**
- Projektek

A következő szinkronizálási feladatok kötelezők, mielőtt a projektlisták szinkronizálása megtörténhetne:
- Számlák (Sales és Supply Chain Management között) 

## <a name="entity-set"></a>Entitás beállítása
| Field Service           | Ellátásilánc-kezelés  |
|-------------------------|-------------------------|
|msdynce_externalprojects | Projektek                |

## <a name="entity-flow"></a>Entitás folyamata
A Projekteket a Supply Chain Management szolgáltatásban hozzák létre. A projektek, amelyek esetében a **Projekttípus** **Idő és anyag**, a **Projektfokozat** pedig **Folyamatban**, a Field Service **Külső projekt** entitásába szinkronizálódnak, a következő információkat beleértve: projekt száma, projektnév, projektfokozat és vevői számla adatai. A **Külső projekt** listát a rendszer a Field Service munkarendelések és a Supply Chain Management projektek párosítására használja.

## <a name="field-service-crm-solution"></a>Field Service CRM megoldás
A **Külső projekt** entitás lekér minden projektet a Supply Chain Management rendszerből. A **Külső projekt** mezőt hozzáadtuk a **Munkarendelés** entitáshoz. Ez a mező egy keresőmező felcímkézi a munkarendelést egy projekttel, majd az értékesítési rendelés kapcsolódik egy projekthez a Supply Chain Management megoldáson belül. Miután a **Rendszer állapota** **Nyitott – folyamatban (690,970,000)** állapotból magasabb állapba kerül, a **Külső projekt** mezőt a rendszer zárolja, és a továbbiakban nem lehet felvenni, törölni vagy módosítani az értéket.

## <a name="prerequisites-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás
### <a name="supply-chain-management"></a>Ellátásilánc-kezelés
A változáskövetés engedélyezése az Adatentitás projektekhez.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban


### <a name="projects-supply-chain-management-to-field-service-projects"></a>Projektek (Supply Chain Management és Field Service között): Projektek

[![Sablonleképezés az adatintegrátorban.](./media/FSProject1.png)](./media/FSProject1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
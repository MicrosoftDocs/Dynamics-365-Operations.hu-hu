---
title: "Készletszintű információk szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a készletszint-információk szinkronizálására használhatók a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service között."
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
ms.openlocfilehash: 3ccc4d406fa4f9800dcdf8697a91892408783196
ms.contentlocale: hu-hu
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-inventory-level-information-from-finance-and-operations-to-field-service"></a>Készletszintű információk szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba 

[!include[banner](../includes/banner.md)]

Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a készletszint-információk szinkronizálására használhatók a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service között.

[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)

## <a name="templates-and-tasks"></a>Sablonok és feladatok
A következő sablon és a kapcsolódó feladatok a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service közötti aktuális készletszintek szinkronizálás futtatására használhatók.

**A sablon neve az adatintegrációban:**
- Termékkészlet (a Finance and Operations megoldásból a Field Service megoldásba)
  
**A feladatok nevei az adatintegrációs projektben:**
- Termékkészlet

A következő szinkronizálási feladatok kötelezők, mielőtt a készletszintek szinkronizálása megtörténhetne:
- Raktárak (a Finance and Operations megoldásból a Field Service megoldásba) 
- Készletegységgel rendelkező Field Service termékek (a Finance and Operations alkalmazásból a Sales alkalmazásba) 

## <a name="entity-set"></a>Entitás beállítása

| Field Service                      | Finance and Operations                 |
|------------------------------------|----------------------------------------|
| msdynce_externalproductinventories | CDS aktuális készlet raktár szerint     |

## <a name="entity-flow"></a>Entitás folyamata
Készletszintadatok küldése a Finance and Operations alkalmazásból a Field Service alkalmazásba a kiválasztott termékekre. A készletszintadatok magukban foglalják a következőket: 
- A készletben található mennyiség (aktuális rögzített, ténylegesen a raktárban található mennyiség)
- A rendelési mennyiség (teljes rögzített mennyiség rendelésen – azaz értékesítési rendelések)
- Megrendelt mennyiség (teljes rögzített megrendelt mennyiség – azaz beszerzési rendelések)

Ezt az információt a rendszer kiadott termékenként rögzíti minden egyes raktárhoz, és a változások nyomon követés alapján szinkronizálja a készletszint megváltozásakor.

A Field Service megoldásban az integrációs megoldás készletnaplókat hoz létre a különbözethez, hogy a Field Service szintjei megfeleljenek a Finance and Operations szintjeinek.

A Finance and Operations a készletszintek alapjaként szolgál. Ezért fontos az integráció beállítása a munkarendelések, az átvitelek és a kiigazítások esetében a Field Service megoldásból a Finance and Operations megoldásba, ha a funkció használatban van a Field Service szolgáltatásban, a készletszintek szinkronizálásával együtt a Finance and Operations megoldásból.

Az olyan termékeket és raktárakat, ahol a készletszintek alapja a Finance and Operations, a speciális lekérdezés és szűrés (Power Query) segítségével lehet vezérelni.

Megjegyzés: Lehetőség van több raktár létrehozására a Field Service megoldásban (ahol a Külsőleg karbantartott = Nem), majd a leképezésükre egy raktárba a Finance and Operations megoldásban, a speciális lekérdezési és szűrési funkcióval. Ez olyan helyzetekben használt, amikor azt szeretnénk, hogy a Field Service kezelje a részletes készletszintet, és csak frissítéseket küldjön a Finance and Operations megoldásba. Ebben az esetben a Field Service nem kap készletszint-frissítéseket a Finance and Operations megoldásból. További információért lásd: Készletátvitelek és szinkronizálása a Field Service alkalmazásból a Finance and Operations alkalmazásba és A Field Service szolgáltatásokban lévő munkarendelések szinkronizálása a Finance and Operations értékesítési rendeléseivel.

## <a name="field-service-crm-solution"></a>Field Service CRM megoldás
A külső termékkészlet entitás új entitás, amely csak az integráció háttérrendszereként használatos. A Finance and Operations készletszint-értékeit kapja meg az integrációban, majd ezeket az értékeket alakítja át manuális készletnaplókká, amelyek ezután módosítják a készlettermékeket a raktárban. 

## <a name="prerequisites-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

### <a name="in-the-data-integration-project"></a>Az adatintegrációs projektben
Használja a speciális lekérdezés és szűrés szűrőit annak a vezérléséhez, hogy a kívánt termékek küldjenek raktárszintadatokat a Finance and Operations alkalmazásból a Field Service alkalmazásba.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

### <a name="product-inventory-finance-and-operations-to-field-service-product-inventory"></a>Termékkészlet (a Finance and Operations megoldásból a Field Service megoldásba): Termékkészlet

[![Sablonleképezés az adatintegrátorban](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)


---
title: Készletszintű információk szinkronizálása a Supply Chain Management alkalmazásból a Field Service alkalmazásba
description: Ez a cikk a készletszint-információk szinkronizálásához használt sablonokat és mögöttes feladatokat tárgyalja Dynamics 365 Supply Chain Management Dynamics 365 Field Service.
author: Henrikan
ms.date: 05/07/2019
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
ms.openlocfilehash: fc14fc63bc1a69a57b10f39b2cb9fb8014e6f70b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844793"
---
# <a name="synchronize-inventory-level-information-from-supply-chain-management-to-field-service"></a>Készletszintű információk szinkronizálása a Supply Chain Management alkalmazásból a Field Service alkalmazásba 

[!include[banner](../includes/banner.md)]



Ez a cikk a készletszint-információk szinkronizálásához használt sablonokat és mögöttes feladatokat tárgyalja Dynamics 365 Supply Chain Management Dynamics 365 Field Service.

[![Üzleti folyamatok szinkronizálása a Supply Chain Management és a Field Service között.](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)

## <a name="templates-and-tasks"></a>Sablonok és feladatok
A következő sablonokat és alapul szolgáló feladatokat használják a tényleges készletszint szinkronizálásához a Supply Chain Management és a Field Service között:

**Sablon az adatintegrációban**
- Termékkészlet (Supply Chain Management és Field Service között)
  
**Feladat az adatintegrációs projektben**
- Termékkészlet

A következő szinkronizálási feladatok kötelezők, mielőtt a készletszintek szinkronizálása megtörténhetne:
- Raktárak (Supply Chain Management és Field Service között) 
- Készletegységgel rendelkező Field Service-termékek (Supply Chain Management alkalmazásból a Sales alkalmazásba) 

## <a name="entity-set"></a>Entitás beállítása

| Field Service                      | Ellátásilánc-kezelés                |
|------------------------------------|----------------------------------------|
| msdynce_externalproductinventories | Dataverse aktuális készlet raktár szerint     |

## <a name="entity-flow"></a>Entitás folyamata
Készletszintadatok küldése a Finance and Operations alkalmazásból a Field Service alkalmazásba a kiválasztott termékekre. A készletszintadatok magukban foglalják a következőket: 
- A készletben található mennyiség (aktuális rögzített és ténylegesen a raktárban található mennyiség)
- A rendelési mennyiség (teljes rögzített mennyiség rendelésen, például értékesítési rendelések)
- Megrendelt mennyiség (teljes rögzített megrendelt mennyiség, például beszerzési rendelések)

Ezt az információt a rendszer kiadott termékenként rögzíti minden egyes raktárhoz, és a változások nyomon követés alapján szinkronizálja a készletszint megváltozásakor.

A Field Service megoldásban az integrációs megoldás készletnaplókat hoz létre a különbözethez, hogy a Field Service szintjei megfeleljenek a Supply Chain Management szintjeinek.

A Supply Chain Management a készletszintek alapjaként szolgál. Tehát, ezért fontos az integráció beállítása a munkarendelések, az átvitelek és a kiigazítások esetében a Field Service megoldásból a Supply Chain Management megoldásba, ha a funkció használatban van a Field Service szolgáltatásban, a készletszintek szinkronizálásával együtt a Supply Chain Management megoldásból.

Azok a termékek és raktárak, amelyekben az Ellátásilánc-kezelés alapszintje a készletszintek, a Speciális lekérdezés és szűrés (Advanced Query and Filtering) segítségével vezérelhetők Power Query.

> [!NOTE]
> Megjegyzés: Lehetőség van több raktár létrehozására a Field Services megoldásban (ahol a **Külsőleg karbantartott = Nem**), majd a leképezésükre egy raktárba a Supply Chain Management megoldásban, a speciális lekérdezési és szűrési funkcióval. Ez olyan helyzetekben használt, amikor azt szeretnénk, hogy a Field Service kezelje a részletes készletszintet, és csak frissítéseket küldjön a Supply Chain Management megoldásba. Ebben az esetben a Field Service nem kap készletszintű frissítéseket a Supply Chain Management megoldásból. További információért lásd: [Készletátvitelek és szinkronizálása a Field Service alkalmazásból a Supply Chain Management alkalmazásba](/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) és [A Field Service szolgáltatásokban lévő munkarendelések szinkronizálása a Supply Chain Management értékesítési rendeléseivel](/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

## <a name="field-service-crm-solution"></a>Field Service CRM megoldás
A **Külső termékkészlet** entitás új entitás, amely csak az integráció háttérrendszereként használatos. Ez az entitás Supply Chain Management készletszint-értékeit kapja meg az integrációban, majd ezeket az értékeket alakítja át manuális készletnaplókká, amelyek ezután módosítják a készlettermékeket a raktárban.

## <a name="prerequisites-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

### <a name="data-integration"></a>Adatintegrálás
A projekt működéséhez gondoskodni kell arról, hogy az integrációs kulcs frissüljön a msdynce_externalproductinventories entitáshoz.
1.  Nyissa meg az **Adatintegráció > Csatlakozókészletek** menüt.
2.  Válassza ki a használt Csatlakozási beállítást.
3.  Győződjön meg arról, hogy az **Integrációs kulcs lapon** a következő kulcsok hozzá vannak adva az msdynce_externalproductinventories entitáshoz:
      - msdynce_productnumber (Termékszám)
      - msdynce_warehouseid (Raktár azonosítója)
      
### <a name="data-integration-project"></a>Adatintegrációs projekt
Használhatja a speciális lekérdezés és szűrés szűrőit annak a vezérléséhez, hogy a kívánt termékek küldjenek raktárszintadatokat a Supply Chain Management alkalmazásból a Field Service alkalmazásba.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

### <a name="product-inventory-supply-chain-management-to-field-service-product-inventory"></a>Termékkészlet (Supply Chain Management alkalmazásból a Field Service alkalmazásba): Termékkészlet

[![Sablonleképezés az adatintegrátorban.](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
---
title: Field Service megállapodási számlák szinkronizálása Supply Chain Management szabadszöveges számlákká
description: Ez a témakör a Dynamics 365 mezőszolgáltatás szerződési számláit a szabadszöveges számlák szabadszöveges számláihoz használt sablonokról és a kapcsolódó feladatokról tárgyalja Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 04/10/2018
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
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: c4ef70af71ae223baaa2abb2b64428beab946e3d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900883"
---
# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-supply-chain-management"></a>Field Service megállapodási számlák szinkronizálása Supply Chain Management szabadszöveges számlákká

[!include[banner](../includes/banner.md)]



Ez a cikk be tárgyalja a sablonokat és a mögöttes Dynamics 365 Field Service feladatokat, amelyek segítségével szinkronizálni lehet a szerződési számlákat a szabadszöveges számlákkal a következőben:Dynamics 365 Supply Chain Management

## <a name="templates-and-tasks"></a>Sablonok és feladatok

A következő sablon és a mögöttes feladatok használatosak a Field Service-ben lévő szerződéses számlák és a Supply Chain Management alkalmazásban lévő szabadszöveges számlák szinkronizálásához.

**A sablon neve az adatintegrációban**

- Szerződéses számlák (Field Service-ből Supply Chain Management szolgáltatásba)

**A feladatok nevei az adatintegrációs projektben**

- Számlafejlécek
- Számlasorok

A következő szinkronizálás kötelezőe, mielőtt a szerződéses számlák szinkronizálása megtörténhetne:

- Ügyfelek (Sales – Supply Chain Management) – közvetlen

## <a name="entity-set"></a>Entitás beállítása

| Field Service  | Ellátásilánc-kezelés                 |
|----------------|----------------------------------------|
| számlák       | Dataverse vevői szabadszöveges számlafejlécek |
| invoicedetails | Dataverse vevői szabadszöveges számlasorok   |

## <a name="entity-flow"></a>Entitás folyamata

A szerződésből a Field Service-ben létrehozott számlák a Microsoft Dataverse (CDS) adatintegrációs projekten keresztül szinkronizálhatók a Supply Chain Management szolgáltatásba. E számlák frissítései a Supply Chain Management szabadszöveges számláira szinkronizálódnak, ha a szabadszöveges számlák könyvelési állapota **Folyamatban**. Miután a szabadszöveges számlák könyvelési állapota a Supply Chain Management szolgáltatásban történő feladása után **Kész** értékre frissül, többé már nem szinkronizálhatók frissítések a Field Service-ből.

## <a name="field-service-crm-solution"></a>Field Service CRM megoldás

A **Sorokat tartalmaz a szerződés eredetével** oszlop hozzá lett adva a **Számla** táblához. Ez az oszlop garantálja, hogy csak a szerződésből létrehozott számlák legyenek szinkronizálhatók. Az érték **igaz**, ha a számla tartalmaz legalább egy számlasort, amely szerződésből származik.

A **Szerződéses eredetet tartalmaz** oszlop hozzá lett adva a **Számlasor** táblához. Ez az oszlop garantálja, hogy csak a szerződésből létrehozott számlasorok legyenek szinkronizálhatók. Az érték **igaz**, ha a számlasor szerződésből származik.

A **Számla dátuma** kötelező mező a Supply Chain Management szolgáltatásban. Ebből következően az oszlopnak értékkel kell rendelkeznie a Field Service szolgáltatásban a szinkronizálás előtt. E követelmény teljesítéséhez a következő logika került hozzáadásra:

- Ha a **Számladátum** oszlop üres a **Számla** táblában (azaz nincs értéke), akkor szerződésből eredő számlasor hozzáadásánál az aktuális dátumra kerül beállításra.
- A felhasználó módosíthatja a **Számladátum** oszlopot. Ha azonban a felhasználó megpróbál egy szerződésből eredő számlát menteni, az üzleti folyamatra vonatkozó hibát kap, ha a **Számladátum** oszlop üres a számlán.

## <a name="prerequisites-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

### <a name="in-supply-chain-management"></a>A Supply Chain Management alkalmazásban

Az integrációhoz számlázási eredetet kell beállítani, hogy megkülönböztessük a szabadszöveges számlákat a Supply Chain Management szolgáltatásban, amelyek a Field Service szolgáltatásban lévő szerződéses számlák alapján jöttek létre. Ha egy számla számlaeredete a **Szerződéses számla integrációja** típusú, akkor a **Külső számlaszám** mező megjelenik az **Értékesítési számla** fejlécében.

Amellett, hogy a számla fejlécében megjelenik, a **Külső számlaszám** az információ felhasználható annak biztosítására, hogy a Field Service szolgáltatásban lévő, szerződéses számlákból létrehozott számlák szűrésre kerüljenek a Supply Chain Management és a Field Service közötti számlaszinkronizálás során.

1. Ugorjon a **Kinnlevőségek** \> **Beállítás** \> **Számla forráskódjai** pontra.
2. Válassza az **Új** elemet új számlaeredet létrehozásához.
3. A **Számla eredete** mezőbe írjon be egy nevet a számla eredetének, például **FS**.
4. A **Leírás** mezőben adjon meg egy leírást, például **Field Service szerződéses számla**.
5. Jelölje be az **Eredettípus hozzárendelése** négyzetet.
6. Állítsa a **Számla eredettípusa** mezőt **Szerződéses számla integrációja** értékre.
7. Válassza a **Mentés** lehetőséget.

### <a name="in-the-data-integration-project"></a>Az adatintegrációs projektben

Feladat: **Számlasorok**  

Győződjön meg arról, hogy Supply Chain Management **Fő számla megjelenítendő értéke** mezője frissül, hogy megfeleljen a kívánt értéknek.

Az alapértelmezett sablonérték **401100**.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-headers"></a>Szerződéses számlák (Field Service-ből Supply Chain Managementbe): Számlafejlécek

[![Sablonleképezés a számlafejlécek adatintegrációjában.](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-lines"></a>Szerződéses számlák (Field Service-ből Supply Chain Managementbe): Számlasorok

[![Sablonleképezés a számlasorok adatintegrációjában.](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
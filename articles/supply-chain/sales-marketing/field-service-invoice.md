---
title: "A Field Service-ben lévő szerződéses számlák és a Finance and Operations-ben lévő szabadszöveges számlák szinkronizálása"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a szerződéses számlák a Microsoft Dynamics 365 for Field Service és a Microsoft Dynamics 365 for Finance and Operations közötti szinkronizálására használhatók."
author: ChristianRytt
manager: AnnBe
ms.date: 04/10/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: ace66c037953f4b1b2e8b93a315faefdb090b1eb
ms.openlocfilehash: 6672e283a5e56b068e3494d53a0fd6dd08253ba9
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---

# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-finance-and-operations"></a>A Field Service-ben lévő szerződéses számlák és a Finance and Operations-ben lévő szabadszöveges számlák szinkronizálása

[!include[banner](../includes/banner.md)]

Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a szerződéses számlák a Microsoft Dynamics 365 for Field Service és a Microsoft Dynamics 365 for Finance and Operations közötti szinkronizálására használhatók.

## <a name="templates-and-tasks"></a>Sablonok és feladatok

A következő sablon és a mögöttes feladatok használatosak a Field Service-ben lévő szerződéses számlák és a Finance and Operations-ben lévő szabadszöveges számlák szinkronizálásához.

**A sablon neve az adatintegrációban:**

- Szerződés számlák (Field Service – Fin and Ops)

**A feladatok nevei az adatintegrációs projektben:**

- Számlafejlécek
- Számlasorok

A következő szinkronizálás kötelezőe, mielőtt a szerződéses számlák szinkronizálása megtörténhetne:

- Számlák (Sales – Fin and Ops) – Közvetlen

## <a name="entity-set"></a>Entitás beállítása

| Field Service  | Finance and Operations                 |
|----------------|----------------------------------------|
| számlák       | CDS vevői szabadszöveges számlafejlécek |
| invoicedetails | CDS vevői szabadszöveges számlasorok   |

## <a name="entity-flow"></a>Entitás folyamata

A szerződésből a Field Service-ben létrehozott számlák a Common Data Service (CDS) adatintegrációs projekten keresztül szinkronizálhatók a Finance and Operations szolgáltatásba. E számlák frissítései a Finance and Operations szabadszöveges számláira szinkronizálódnak, ha a szabadszöveges számlák könyvelési állapota  **Folyamatban**. Miután a szabadszöveges számlák könyvelési állapota a Finance and Operations szolgáltatásban történő feladása után **Kész** értékre frissül, többé már nem szinkronizálhatók frissítések a Field Service-ből.

## <a name="field-service-crm-solution"></a>Field Service CRM megoldás

A **Sorokat tartalmaz a szerződés eredetével** mező hozzá lett adva a **Számla** entitáshoz. Ez a mező garantálja, hogy csak a szerződésből létrehozott számlák legyenek szinkronizálhatók. Az érték **igaz**, ha a számla tartalmaz legalább egy számlasort, amely szerződésből származik.

A **Szerződéses eredetet tartalmaz** mező hozzá lett adva a **Számlasor** entitáshoz. Ez a mező garantálja, hogy csak a szerződésből létrehozott számlasorok legyenek szinkronizálhatók. Az érték **igaz**, ha a számlasor szerződésből származik.

A **Számla dátuma** kötelező mező a Finance and Operations szolgáltatásban. Ebből következően a mezőnek értékkel kell rendelkeznie a Field Service szolgáltatásban a szinkronizálás előtt. E követelmény teljesítéséhez a következő logika került hozzáadásra:

- Ha a **Számladátum** mező üres a **Számla** entitásban (azaz nincs értéke), akkor szerződésből eredő számlasor hozzáadásánál az aktuális dátumra kerül beállításra.
- A felhasználó módosíthatja a **Számladátum** mezőt. Ha azonban a felhasználó megpróbál egy szerződésből eredő számlát menteni, üzletifolyamat-hibát kap, ha a **Számladátum** mező üres a számlán.

## <a name="prerequisites-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

### <a name="in-finance-and-operations"></a>A Finance and Operations alkalmazásban

Az integrációhoz számlázási eredetet kell beállítani, hogy megkülönböztessük a szabadszöveges számlákat a Finance and Operations szolgáltatásban, amelyek a Field Service szolgáltatásban lévő szerződéses számlák alapján jöttek létre. Ha egy számla számlaeredete a **Szerződéses számla integrációja** típusú, akkor a **Külső számlaszám** mező megjelenik az **Értékesítési számla** fejlécében.

Amellett, hogy a számla fejlécében megjelenik, a **Külső számlaszám** az információ felhasználható annak biztosítására, hogy a Field Service szolgáltatásban lévő, szerződéses számlákból létrehozott számlák szűrésre kerüljenek a Finance and Operations és a Field Service közötti számlaszinkronizálás során.

1. Ugorjon a **Kinnlevőségek** \> **Beállítás** \> **Számla forráskódjai** pontra.
2. Válassza az **Új** elemet új számlaeredet létrehozásához.
3. A **Számla eredete** mezőbe írjon be egy nevet a számla eredetének, például **FS**.
4. A **Leírás** mezőben adjon meg egy leírást, például **Field Service szerződéses számla**.
5. Jelölje be az **Eredettípus hozzárendelése** négyzetet.
6. Állítsa a **Számla eredettípusa** mezőt **Szerződéses számla integrációja** értékre.
7. Válassza a **Mentés** lehetőséget.

### <a name="in-the-data-integration-project"></a>Az adatintegrációs projektben

Feladat: **Számlasorok**  

Győződjön meg arról, hogy Finance and Operations **Fő számla megjelenítendő értéke** mezője frissül, hogy megfeleljen a kívánt értéknek.

Az alapértelmezett sablonérték **401100**.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.

### <a name="agreement-invoices-field-service-to-fin-and-ops-invoice-headers"></a>Szerződéshez kapcsolódő számlák (Field Service - Finance and Operations): számlák fejlécei

[![Sablonleképezés az adatintegrátorban](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)

### <a name="agreement-invoices-field-service-to-fin-and-ops-invoice-lines"></a>Szerződéshez kapcsolódő számlák (Field Service - Finance and Operations): számlák sorai

[![Sablonleképezés az adatintegrátorban](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)


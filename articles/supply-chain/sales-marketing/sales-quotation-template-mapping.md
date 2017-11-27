---
title: "Értékesítésiajánlat-fejlécek és -sorok szinkronizálása a Sales szolgáltatásból a Finance and Operations szolgáltatásba"
description: "A témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti szinkronizálásra használhatók az értékesítési árajánlatok fejlécei és sorai esetében."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
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
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c8cfc484eed02423dbf0c7caaf8ac2337b6ac38d
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-quotation-headers-and-lines-from-sales-to-finance-and-operations"></a>Értékesítésiajánlat-fejlécek és -sorok szinkronizálása a Sales szolgáltatásból a Finance and Operations szolgáltatásba

[!include[banner](../includes/banner.md)]

> [!NOTE]
> A potenciális vevő készpénzfizetési Solution használata előtt meg kell ismernie: [Dynamics 365 adatintegráció](/common-data-service/entity-reference/dynamics-365-integration). 

A témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations) és a Microsoft Dynamics 365 for Sales (Sales) közötti szinkronizálásra használhatók az értékesítési árajánlatok fejlécei és sorai esetében. 

## <a name="template-and-tasks"></a>Sablon és feladatok

A következő sablonokat és alapul szolgáló feladatokat használják az értékesítési ajánlati fejlécek és sorok szinkronizálásához a Sales és a Finance and Operations között:

- **Sablon neve:** Értékesítési árajánlatok (Sales – Fin and Ops)
- **A projekt tevékenységeinek neve:**

    - QuoteHeader
    - QuoteLine

A következő szinkronizálási feladatok kötelezőek, mielőtt az értékesítési ajánlat fejlécének és sorainak szinkronizálása megtörténhetne:

- Termékek (Fin és Ops a Saleshez)
- Számlák (Sales a Fin and Opshoz) (ha van)
- Kapcsolattartók vevőkkel (Sales a Fin and Opshoz) (ha van)

## <a name="entity-set"></a>Entitás beállítása

| Értékesítés        | CDS           | Finance and Operations    |
|--------------|---------------|---------------------------|
| Idézetek       | Árajánlat     | Értékesítésiajánlat-fejlécek   |
| QuoteDetails | QuotationLine | CDS értékesítési ajánlat sorai |

## <a name="entity-flow"></a>Entitás folyamata

Az értékesítési ajánlatok létrehozása a Sales-ben történik, majd szinkronizálódnak a Finance and Operations programban.

A Sales értékesítési ajánlatai csak akkor szinkronizálódnak, ha teljesülnek az alábbi feltételek:

- Az értékesítésiajánlat-sorokban szereplő összes termék külsőleg van karbantartva.
- Az értékesítési ajánlat aktív vagy aktiválva van.

## <a name="prospect-to-cash-solution-for-sales"></a>Potenciális vevő értékesítési készpénzfizetési megoldáshoz

A **Csak külsőleg karbantartott termékei vannak** mező hozzáadódott az Ajánlat entitáshoz annak érdekében, hogy konzisztensen követni lehessen, hogy az értékesítési ajánlat teljes mértékben külsőleg karbantartott termékekből áll-e. Ha az értékesítési árfolyamok csak külsőleg fenntartott termékeket tartalmaznak, a termékeket a Finance and Operations kezeli. Ez a viselkedés garantálja, hogy nem próbálja szinkronizálni az értékesítési ajánlati sorokat olyan termékekkel, amelyek ismeretlenek a Finance and Operations számára.

Az ajánlat minden terméke és sora frissül a **Csak külsőleg karbantartott termékei vannak** információval az árajánlat fejlécéből. Ezek az információk megtalálhatók az **ajánlat már külsőleg karbantartása termékek csak** az ajánlatkérési sorhoz entitáson mezőt.

A **engedmény**, **költségek**, és **adó** mezők egy összetett-beállítást a pénzügyi és műveletek szabályozhatók. Ezzel a beállítással jelenleg nem támogatott integrációs megfeleltetés. Az aktuális modellben a **ár**, **engedmény**, **költség**, és **adó** mezők lezárt fájlrendszer és kezeli a pénzügyi és a műveletek.

Az értékesítési a megoldás teszi a következő mezők írásvédett, mivel az értékek nem szinkronizálja a késedelmi a műveletekhez pedig:

- **Csak olvasható mezőket az értékesítésiajánlat-fejléc:** kedvezmény %, engedmény, szállítási mennyiség
- **Csak olvasható mezők értékesítésiajánlat-sorokban:** Adó

## <a name="preconditions-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

Értékesítési rendelések szinkronizálása előtt fontos frissíteni a rendszert a következő beállítással:

### <a name="setup-in-sales"></a>Beállítás a Salesben

- Lépjen a **Beállítások** &gt; **Felügyelet** &gt; **Rendszerbeállítások** &gt; **Sales** elemre, és győződjön meg róla, hogy a **Engedményszámítási módszer** mező értéke **Egységenkénti**. Ez a beállítás segít garantálni, hogy az értékesítésből származó sor engedménye megegyezik a Finance and Operations beállításával. Ellenkező esetben az engedmény nem fog Pénzügy és a műveletek, a megfelelő, mert a pénzügyi és műveletek felirat jelenik meg az engedmény egységenkénti kedvezményt, még akkor is, ha az értékesítési sor engedmény volt.

### <a name="setup-in-finance-and-operations"></a>Beállítás a Finance and Operations alkalmazásban

- Ugorjon a **Kintlévőségek** &gt; **Beállítás** &gt; **Kinnlevőségek paraméterei** pontra. Az a **számsorozat** lapon válassza ki az értékesítési ajánlatok számsorozata, és kattintson a **részleteinek megtekintése**. Ezután a **főkönyvi beállítása**, állítsa be a **kézi** mezőt **Igen**.
- Ugorjon a **Kintlévőségek** &gt; **Beállítás** &gt; **Kinnlevőségek paraméterei** pontra. Ezt a **Szállítmányok** lapon a **szállításidátum-ellenőrzés** mezőt **nincs**. Ez a beállítás megakadályozza, hogy az értékesítési ajánlatok sikertelen szinkronizálás.

### <a name="setup-in-the-data-integration-project"></a>Beállítás az adatintegrációs projektben

#### <a name="quoteheader"></a>QuoteHeader

- A **kért szállítási dátum** mező szükséges-e a pénzügyi és a műveletek, és a szinkronizálás nem hajtható végre, ha a mező üresen marad. Erről a problémáról megakadályozza, ha a mező üres, az alapértelmezett dátum származik **forrás &gt;CD**. A dátum a preferált értékre módosuljon. Jelenleg nem adhat meg értéket például **Ma**, amely meghatározza a mai dátumig. A dátum megadása kötelező. A sablon alapértelmezett **Kért kézbesítési dátum** értéke **1/1/2020**.
- **A cím, ország, terület kódja** mező kötelező a Finance and Operations programban. Szinkronizációs hibák elkerülése érdekében, megadhatja az alapértelmezett érték, amely akkor használható, ha a mezőt üresen hagyja az értékesítésben. A alapértelmezés szerinti értéke is hasznos, mivel nem kell manuálisan adja meg egy értéket a a **ország, régió** helyi címeknél mezőt. A **DeliveryAddressCountryRegionISOCode** beállításnak nincs alapértelmezett értéke.
- Frissíti a hozzárendelést az **CD Szervezetazonosító** a **forrás &gt;CD**, hogy megfeleljen **CD szervezet** a szervezeti egységben:

    - A sablon alapértelmezett **Organization_OrganizationId** értéke **ORG001**.
    - A sablon alapértelmezett **Account_Organization_OrganizationId** értéke **ORG001**.
    - A sablon alapértelmezett **InvoiceAccount_OrganizationId** értéke **ORG001**.

#### <a name="quoteline"></a>QuoteLine

- Frissíti a hozzárendelést az **CD Szervezetazonosító** a **forrás &gt;CD**, hogy megfeleljen **CD szervezet** a szervezeti egységben:

    - A sablon alapértelmezett **Organization_OrganizationId** értéke **ORG001**.
    - A sablon alapértelmezésre **Product_Organization_Organization_OrganizationId** van **ORG001**.
    - A sablon alapértelmezésre **Quotation_Organization_Organization_OrganizationId** van **ORG001**.

- A **kért szállítási dátum** mező szükséges-e a pénzügyi és a műveletek, és a szinkronizálás nem hajtható végre, ha a mező üresen marad. Erről a problémáról megakadályozza, ha a mező üres, az alapértelmezett dátum származik **forrás &gt;CD**. A dátum a preferált értékre módosuljon. Jelenleg nem adhat meg értéket például **Ma**, amely meghatározza a mai dátumig. A dátum megadása kötelező. A sablon alapértelmezett **Kért kézbesítési dátum** értéke **1/1/2020**.
- Lehetőség van a következő hozzárendelésének eltávolítása **CD &gt;cél** biztosítása, hogy az ajánlati sorok importálják Pénzügy és a műveletek, ha nincs megadva alapértelmezett a vevő vagy a termék:

    - **SiteId** – hely a Pénzügy és műveletek árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges. Nincs alapértelmezett sablonérték a **SiteId** elemnél.
    - **WarehouseId** – hely a raktár és műveletek árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges. Nincs alapértelmezett sablonérték a **WarehouseId** elemnél.

- Győződjön meg róla, hogy a szükséges érték hozzárendelése az Eladási mértékegység (Mértékegységet) a pénzügyi és a műveletek a **CD &gt;cél** hozzárendelése **Quantity_UOM**, **SALESUNITSYMBOL**.

## <a name="template-mapping-in-data-integrator"></a>Sablonleképezés az adatintegrátorban

> [!NOTE]
> - A **engedmény**, **költségek**, és **adó** mezők egy összetett-beállítást a pénzügyi és műveletek szabályozhatók. Ezzel a beállítással jelenleg nem támogatott integrációs megfeleltetés. Az aktuális modellben a **ár**, **engedmény**, **költség**, és **adó** mezők lezárt fájlrendszer a Finance and Operations.
> - A **fizetési feltételek**, **feltételek áruszállítási**, **szállítási feltételek**, **szállítási mód**, és **szállítási mód** mezők nem találhatók meg a alapértelmezett-leképezései. Ezek a mezők megfeleltetéséhez be kell állítania egy adott szervezetek között szinkronizált entitás adatainak értékmegfeleltetések.

Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése.

### <a name="quoteheader"></a>QuoteHeader

![Sablonleképezés az adatintegrátorban](./media/sales-quotation-template-mapping-data-integrator-1.png)

![Sablonleképezés az adatintegrátorban](./media/sales-quotation-template-mapping-data-integrator-2.png)

### <a name="quoteline"></a>QuoteLine

![Sablonleképezés az adatintegrátorban](./media/sales-quotation-template-mapping-data-integrator-3.png)

![Sablonleképezés az adatintegrátorban](./media/sales-quotation-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a>Kapcsolódó témakörök

[A Finance and Operations-termékek szinkronizálása a Sales-termékekre](products-template-mapping.md)

[A Sales-számlák szinkronizálása a Finance and Operations-ügyfelekre](accounts-template-mapping.md)

[A Sales-kapcsolatok szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre](contacts-template-mapping.md)




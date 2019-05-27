---
title: A Finance and Operations-munkarendelések szinkronizálása a Field Service vevői rendelésekre
description: Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Finance and Operations-munkarendelések a Field Service vevői rendelésekre történő szinkronizálásához szükségesek.
author: ChristianRytt
manager: AnnBe
ms.date: 04/09/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 49cb5942532e4feab64aa271ebfecf5cb60b1c61
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562718"
---
# <a name="synchronize-work-orders-in-field-service-to-sales-orders-in-finance-and-operations"></a>A Finance and Operations-munkarendelések szinkronizálása a Field Service vevői rendelésekre

[!include[banner](../includes/banner.md)]

Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Microsoft Dynamics 365 for Field Service munkarendeléseinek a Microsoft Dynamics 365 for Finance and Operations szolgáltatásban található értékesítési rendelésekkel történő szinkronizálására használatosak.

[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/field-service-integration.png)](./media/field-service-integration.png)

Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Finance and Operations-munkarendelések a Field Service vevői rendelésekre történő szinkronizálásához szükségesek.

## <a name="templates-and-tasks"></a>Sablonok és feladatok

A következő sablonok és kapcsolódó feladatok mutatja be a Finance and Operations-munkarendelések a Field Service vevői rendelésekre történő szinkronizálásához használatosak.

### <a name="names-of-the-templates-in-data-integration"></a>A sablonok nevei az adatintegrációban

A **Munkarendelések – értékesítési rendelések (Field Service – Fin and Ops)** sablon használható a szinkronizálás futtatásához.

### <a name="names-of-the-tasks-in-the-data-integration-project"></a>A feladatok nevei az adatintegrációs projektben

- WorkOrderHeader
- WorkOrderServiceLineEstimate
- WorkOrderServiceLineUsed
- WorkOrderProductLineEstimate
- WorkOrderProductLineUsed

A következő szinkronizálási feladatok kötelezőek, mielőtt az értékesítési rendelés fejlécének és sorainak szinkronizálása megtörténhetne:

- Field Service termékek (Fin and Ops – Field Service)
- Számlák (Sales – Fin and Ops) – Közvetlen

## <a name="entity-set"></a>Entitás beállítása

| **Field Service** | **Finance and Operations** |
|-------------------------|-------------------------|
| msdyn_workorders        | CDS értékesítésirendelés-fejlécek |
| msdyn_workorderservices | CDS értékesítési rendelés sorai   |
| msdyn_workorderproducts | CDS értékesítési rendelés sorai   |

## <a name="entity-flow"></a>Entitás folyamata

A munkarendelések létrejönnek a Field Service szolgáltatásban. Ha a munkarendelések csak külsőleg karbantartott termékeket tartalmaznak, és ha a **Munkarendelés állapota** érték nem **Nyitott – nincs beütemezve** és **Lezárt – visszavonva**, úgy a munkarendelések a Finance and Operations szolgáltatásba szinkronizálhatók CDS adatintegrációs projekten keresztül. A munkarendelések frissítései értékesítési rendelésként szinkronizálódnak a Finance and Operations szolgáltatásba. Ezek a frissítések tartalmazzák a származási típusra és állapotra vonatkozó információkat.

## <a name="estimated-versus-used"></a>Becsült, illetve felhasznált

A Field Service szolgáltatásban a termékek és szolgáltatások a munkarendelésekben egyaránt rendelkeznek **Becsült** és **Felhasznált** értékekkel mennyiség és összeg szerint. Azonban a Finance and Operations szolgáltatásban az értékesítési rendeléseknél a **Becsült** és a **Felhasznált** értékek koncepciója nem létezik. A Finance and Operations vevői rendeléseinél meglévő várható mennyiségeket alkalmazó termékelosztás támogatása érdekében és a felhasználandó és számlázandó mennyiség fenntartása érdekében két feladatcsoport szinkronizálja a termékeket és szolgáltatásokat a munkarendelésre. A feladatok egy csoportja a **Becsült** értékekhez tartozik, a másik a **Felhasznált** értékekhez.

Ez a viselkedés lehetővé tesz olyan forgatókönyveket, ahol becsült értékeket használnak az elosztás vagy a foglalás során a Finance and Operations szolgáltatásban, míg a felhasználási értékeket használják a fogyasztásnál és a számlázásnál.

### <a name="estimated"></a>Becsült

Terméksorok szinkronizálásához a **Becsült** értékek használatosak, ha a **Sor állapota** értéke **Becsült**, a **Felosztott** lehetőség **Igen** értékre van állítva, és a **Rendszer állapota** értéke nem **Lezárva – feladva**.

Szolgáltatási sorok szinkronizálásához a **Becsült** értékek használatosak, ha a **Sor állapota** értéke **Becsült**, a **Rendszer állapota** értéke pedig nem **Lezárva – feladva**.

### <a name="used"></a>Felhasználva

A **Felhasznált** értékeket fogyasztásra és számlázásra használják. Ebben az esetben a **Felhasznált** értékek szinkronizálódnak.

Az alábbi táblázat áttekintést ad a terméksorok különböző kombinációiról.

| Rendszer állapota <br>(Field Service) | Sor állapota <br>(Field Service) | Felosztott <br>(Field Service) |Szinkronizált érték <br>(Finance and Operations) |
|--------------------|-------------|-----------|---------------------------------|
| Nyitott – beütemezve   | Becsült   | Igen       | Becsült                       |
| Nyitott – beütemezve   | Becsült   | Nincs        | Felhasználva                            |
| Nyitott – beütemezve   | Felhasználva        | Igen       | Felhasználva                            |
| Nyitott – beütemezve   | Felhasználva        | Nincs        | Felhasználva                            |
| Nyitott – folyamatban | Becsült   | Igen       | Becsült                       |
| Nyitott – folyamatban | Becsült   | Nincs        | Felhasználva                            |
| Nyitott – folyamatban | Felhasználva        | Igen       | Felhasználva                            |
| Nyitott – folyamatban | Felhasználva        | Nincs        | Felhasználva                            |
| Nyitott – befejezve   | Becsült   | Igen       | Becsült                       |
| Nyitott – befejezve   | Becsült   | Nincs        | Felhasználva                            |
| Nyitott – befejezve   | Felhasználva        | Igen       | Felhasználva                            |
| Nyitott – befejezve   | Felhasználva        | Nincs        | Felhasználva                            |
| Lezárva – feladva    | Becsült   | Igen       | Felhasználva                            |
| Lezárva – feladva    | Becsült   | Nincs        | Felhasználva                            |
| Lezárva – feladva    | Felhasználva        | Igen       | Felhasználva                            |
| Lezárva – feladva    | Felhasználva        | Nincs        | Felhasználva                            |

Az alábbi táblázat áttekintést ad a szolgáltatási sorok különböző kombinációiról.

| Rendszer állapota <br>(Field Service) | Sor állapota <br>(Field Service) | Szinkronizált érték <br>(Finance and Operations) |
|--------------------|-------------|-----------|
| Nyitott – beütemezve   | Becsült   | Becsült |
| Nyitott – beütemezve   | Felhasználva        | Felhasználva      |
| Nyitott – folyamatban | Becsült   | Becsült |
| Nyitott – folyamatban | Felhasználva        | Felhasználva      |
| Nyitott – befejezve   | Becsült   | Becsült |
| Nyitott – befejezve   | Felhasználva        | Felhasználva      |
| Lezárva – feladva    | Becsült   | Felhasználva      |
| Lezárva – feladva    | Felhasználva        | Felhasználva      |

A **Becsült** és a **Felhasznált** értékek szinkronizálását két különböző termék- és szolgáltatássorokkal kapcsolatos feladat kezeli. Előre definiált szűrők indítják a megfelelő feladatot, és a mögöttes leképezést segítségével garantálható, hogy **Várt** és **Felhasznált** helyes értékei szinkronizálódjanak.

### <a name="example"></a>Példa

1. Munkarendelés jön létre és kerül ütemezésre a Field Service szolgáltatásban.

    A **Rendszerállapot** értéke **Nyitott – beütemezve**.

    - **Terméksor:** becsült mennyiség = 5ea, felhasznált mennyiség = 0ea, a sor állapota = becsült, felosztott = nem
    - **Szolgáltatási sor:** becsült mennyiség = 2 óra, a felhasznált mennyiség = 0 óra, sor állapota = becsült

    Az ebben a példában a termékhez tartozó **Használt mennyiség** értéke **0** (nulla) és a szolgáltatás **Becsült mennyiségének** értéke **2 óra**, amelyek szinkronizálódnak a Finance and Operations szolgáltatásba.

2. A fermékek felosztása a Field Service szolgáltatásban történik.

    A **Rendszerállapot** értéke **Nyitott – beütemezve**.

    - **Terméksor:** becsült mennyiség = 5ea, felhasznált mennyiség = 0ea, a sor állapota = becsült, felosztott = igen
    - **Szolgáltatási sor:** becsült mennyiség = 2 óra, a felhasznált mennyiség = 0 óra, sor állapota = becsült

    Az ebben a példában a termékhez tartozó **Becsült mennyiség** értéke **5ea** és a szolgáltatás **Becsült mennyiségének** értéke **2 óra**, amelyek szinkronizálódnak a Finance and Operations szolgáltatásba.

3. A szerviztechnikus megkezdi a munkát, a munkarendelésen, és regisztrálja a 6 anyagfelhasználást.

    A **Rendszerállapot** értéke **Nyitott – folyamatban**.

    - **Terméksor:** becsült mennyiség = 5ea, felhasznált mennyiség = 6ea, a sor állapota = felhasznált, felosztott = igen
    - **Szolgáltatási sor:** becsült mennyiség = 2 óra, a felhasznált mennyiség = 0 óra, sor állapota = becsült

    Az ebben a példában a termékhez tartozó **Használt mennyiség** értéke **6** és a szolgáltatás **Becsült mennyiségének** értéke **2 óra**, amelyek szinkronizálódnak a Finance and Operations szolgáltatásba.

4. A szerviztechnikus kitölti a munkarendelést és regisztrál 1,5 felhasznált órát.

    A **Rendszerállapot** értéke **Nyitott – befejezve**.

    - **Terméksor:** becsült mennyiség = 5ea, felhasznált mennyiség = 6ea, a sor állapota = felhasznált, felosztott = igen
    - **Szolgáltatási sor:** becsült mennyiség = 1,5 óra, a felhasznált mennyiség = 0 óra, sor állapota = felhasznált

    Az ebben a példában a termékhez tartozó **Használt mennyiség** értéke **6** és a szolgáltatás **Felhasznált mennyiségének** értéke **1,5 óra**, amelyek szinkronizálódnak a Finance and Operations szolgáltatásba.

## <a name="sales-order-origin-and-status"></a>Értékesítési rendelés eredete és állapota

### <a name="sales-origin"></a>Értékesítési forrás

A munkarendelésekből származó értékesítési rendelések a Finance and Operations szolgáltatásban való nyomon követése érdekében értékesítési eredetet hozhat létre, ahol az **Eredettípus hozzárendelése** beállítás **Igen** és a **Értékesítési forrás típusa** mező beállítása **Munkarendelés-integráció**.

Alapértelmezés szerint a leképezés kiválasztja az értékesítési forrást a **Munkarendelés-integráció** értékesítési forrástípusnál az összes olyan értékesítési rendelés esetén, amelyek munkarendelésekből jöttek létre. Ez a viselkedés akkor lehet hasznos, ha a Finance and Operations szolgáltatásban műveletek értékesítési rendelésekkel dolgozik. Gondoskodnia kell arról, hogy a munkarendelésekből származó értékesítési rendelések ne szinkronizálódjanak vissza a Field Service szolgáltatásba mint munkarendelések.

A megfelelő értékesítésiforrás-beállítások a Finance and Operations szolgáltatásban való megadásához lásd a jelen témakör „Előfeltételek és hozzárendelési beállítás” részét.

### <a name="status"></a>Állapot

Ha az értékesítési rendelés egy munkarendelésből származik, ha a **Külső munkarendelés állapota** mező megjelenik a **Beállítás** lapon az értékesítési rendelés fejlécében. Ez a mező mutatja a rendszer állapotát a munkarendelésből a Field Service szolgáltatásban, ami segít nyomon követni a szinkronizált munkarendelési állapotát az értékesítési rendeléseknek a Finance and Operations szolgáltatásban. Ez a mező segíthet a Finance and Operations felhasználójának abban is, hogy meghatározza, hogy az értékesítési rendelést szállítani vagy számlázni kell-e.

A **Külső munkarendelés állapota** mező a következő értékeket veheti fel:

- Nyitott – beütemezve
- Nyitott – folyamatban
- Nyitott – befejezve
- Lezárva – feladva

## <a name="field-service-crm-solution"></a>Field Service CRM megoldás

A Field Service és a Finance and Operations közötti integrálás támogatásához további funkciók szükségesek a Field Service CRM megoldásból. A megoldás a következő változásokat tartalmazza.

### <a name="work-order-entity"></a>Munkarendelés entitás

A **Csak külsőleg karbantartott termékei vannak** mező hozzá lett adva a **Munkarendelés** entitáshoz, és megjelenik az oldalon. Használata következetesen nyomon követi, hogy egy munkarendelés kizárólag külsőleg karbantartott termékekből áll-e. A munkarendelés akkor tartalmaz csak külsőleg karbantartott termékeket, ha az összes kapcsolódó terméket a Finance and Operations kezeli. Ez a mező garantálja, hogy a felhasználók ne szinkronizálják az olyan termékekkel rendelkező munkarendeléseket, amelyek ismeretlenek a Finance and Operations számára.

### <a name="work-order-product-entity"></a>Munkarendelési termék entitás

- A **Rendelésnek csak külsőleg karbantartott termékei vannak** mező hozzá lett adva a **Munkarendelési termék** entitáshoz, és megjelenik az oldalon. Következetesen követi, hogy a munkarendelési termék karbantartása a Finance and Operations szolgáltatásban történik-e. Ez a mező garantálja, hogy a felhasználók ne szinkronizálják az olyan munkarendelési termékeket, amelyek ismeretlenek a Finance and Operations számára.
- A **Fejléc-rendszerállapot** mező hozzá lett adva a **Munkarendelési termék** entitáshoz, és megjelenik az oldalon. Használata következetesen nyomon követi a munkarendelés rendszerállapotát, és segít garantálni a helyes szűrést a munkarendelési termékek a Finance and Operations szolgáltatásba való szinkronizálásakor. Ha szűrő van beállítva az integrációs feladatokra, a **Fejléc-rendszerállapot** információ is felhasználásra kerül annak meghatározására is, hogy a becsült vagy használt értékeket szinkronizálni kell-e.
- Az **Egységenként számlázott összeg** mező a ténylegesen felhasznált egységekre számlázott összeget mutatja. Az érték kiszámítása a **Teljes összeg** érték a **Tényleges mennyiség** értékkel való elosztása adja. A mező olyan rendszerekbe való integrációnál használható, amelyek nem támogatják a használt mennyiség és a számlázott mennyiség különböző értékeit. Ez a mező nem jelenik meg a felhasználói felületen (UI). 
- A **Kedvezmény számlázott összege** mező számítása az **Engedményösszeg** érték plusz a **Számlázott összeg** értékéből eredő kerekítés összeadásából ered. Ez a mező integrációs célokat szolgál, és nem jelenik meg a felhasználói felületen.
- A **Tizedesmennyiség** mező a **Mennyiség** mező értékét tizedesszámként tárolja. Ez a mező integrációs célokat szolgál, és nem jelenik meg a felhasználói felületen. 
- A **Felhasznált** mező értéke visszaáll **0-ra** (nullára), ha a munkarendelési termék **Sorállapot** értéke **Felhasznált** értékről **Becsült** értékre módosul. Ez a módosítás segít megelőzni azokat a helyzeteket, amikor a tévesen bevitt mennyiség szinkronizálásra kerül, amikor a **Sorállapot** értéke **Becsült** és a **Felosztott** beállítás értéke **Nem**.

### <a name="work-order-service-entity"></a>Munkarendelési szolgáltatás entitás

- A **Rendelésnek csak külsőleg karbantartott termékei vannak** mező hozzá lett adva a **Munkarendelési szolgáltatás** entitáshoz, és megjelenik az oldalon. Következetesen követi, hogy a munkarendelési szolgáltatás karbantartása a Finance and Operations szolgáltatásban történik-e. Ez a mező garantálja, hogy a felhasználók ne szinkronizálják az olyan munkarendelési szolgáltatásokat, amelyek ismeretlenek a Finance and Operations számára.
- A **Fejléc-rendszerállapot** mező hozzá lett adva a **Munkarendelési szolgáltatás** entitáshoz, és megjelenik az oldalon. Használata következetesen nyomon követi a munkarendelés rendszerállapotát, és segít garantálni a helyes szűrést a munkarendelési szolgáltatások a Finance and Operations szolgáltatásba való szinkronizálásakor. Ha szűrő van beállítva az integrációs feladatokra, a **Fejléc-rendszerállapot** információ is felhasználásra kerül annak meghatározására is, hogy a becsült vagy használt értékeket szinkronizálni kell-e.
- Az **Időtartam órában** mező tárolja az **Időtartam** mező értékét az értéket percről órára konvertálva. Ez a mező integrációs célokat szolgál, és nem jelenik meg a felhasználói felületen.
- A **Becsült időtartam órában** mező tárolja a **Becsült időtartam** mező értékét az értéket percről órára konvertálva. Ez a mező integrációs célokat szolgál, és nem jelenik meg a felhasználói felületen.
- Az **Egységenként számlázott összeg** mező a ténylegesen felhasznált egységekre számlázott összeget tárolja. Az érték kiszámítása a **Teljes összeg** érték a **Tényleges mennyiség** értékkel való elosztása adja. Ez a mező olyan rendszerekbe való integrációnál használható, amelyek nem támogatják a használt mennyiség és a számlázott mennyiség különböző értékeit. A mező nem jelenik meg a felhasználói felületen.
- A **Kedvezmény számlázott összege** mező számítása az **Engedményösszeg** érték plusz a **Számlázott összeg** értékéből eredő kerekítés összeadásából ered. Ez a mező integrációs célokat szolgál, és nem jelenik meg a felhasználói felületen.
- A **Külső sor rendelés** mező számított negatív sorrendelési szám, amely olyan külső rendszerekben használható, ahol a munkarendelési termékeket és a szolgáltatási sorokat összevonja a program. Ez a mező lehetővé teszi, hogy a munkarendelési termékek pozitív sorszámokkal és munkarendelési szolgáltatások negatív sorszámokkal rendelkezzenek. A mező értékét a rendszer úgy számítja, hogy a **Rendelési sor** értékét szorozza -1-gyel. Ez a mező nem jelenik meg a felhasználói felületen.
- A **Felhasznált** mező értéke visszaáll **0-ra** (nullára), ha a munkarendelési szolgáltatás **Sorállapot** értéke valamilyen okból **Felhasznált** értékről **Becsült** értékre módosul. Ez a módosítás segít megelőzni azokat a helyzeteket, amikor a tévesen bevitt mennyiség szinkronizálásra kerül, amikor a **Sorállapot** értéke **Becsült** és a **Fejléc-rendszerállapot** értéke **Lezárva – feladva**.

## <a name="preconditions-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

Munkarendelések szinkronizálása előtt fontos frissíteni a rendszert a következő beállításokkal.

### <a name="setup-in-field-service"></a>Beállítás a Field Service szolgáltatásban

- Győződjön meg arról, hogy a Field Service szolgáltatásban a munkarendelésekhez használt számozás nem fedi a Finance and Operations szolgáltatásban az értékesítési rendelésekhez használt számozást. Ellenkező esetben előfordulhat, hogy a meglévő értékesítési rendelések helytelenül frissülnek a Field Service vagy a Finance and Operations szolgáltatásban.
- A **Munkarendelési számla létrehozása** mezőt **Soha** értékre kell állítani, mert a számlázás a Finance and Operations szolgáltatásban történik. Lépjen a **Field Service** \> **Beállítások** \> **Adminisztráció** \> **Field Service beállítások** elemre, és győződjön meg róla, hogy a **Munkarendelési számla létrehozása** mező értéke **Soha** legyen.

### <a name="setup-in-finance-and-operations"></a>Beállítás a Finance and Operations alkalmazásban

A munkarendelés integrációjához szükséges az értékesítés forrásának beállítása. Az értékesítés forrása használatos azon értékesítési rendelések megkülönböztetésére a Finance and Operations szolgáltatásban, amelyek a Field Service szolgáltatásban lévő munkarendelésekből jöttek létre. Ha egy értékesítési rendelés értékesítési eredetű a **Munkarendelés-integráció** típusból, a **Külső munkarendelés állapota** mező megjelenik az értékesítési rendelés fejlécében. Ezenkívül az értékesítés származásának segítségével garantálható, hogy munkarendelésekből a Field Service szolgáltatásban létrejött értékesítési rendelések kiszűrésre kerüljenek, amikor az értékesítési rendelések szinkronizálása zajlik a Finance and Operations szolgáltatásból a Field Service szolgáltatásba.

1. Válassza az **Értékesítés és marketing** \> **Beállítás** \> **Értékesítési rendelések** \> **Értékesítési forrás** lehetőséget.
2. Válassza az **Új** elemet új értékesítési forrás létrehozásához.
3. Az **Értékesítési forrás** mezőbe írjon be egy nevet az értékesítés eredetének, például **WorkOrder**.
4. A **Leírás** mezőben adjon meg egy leírást, például **Field Service munkarendelés**.
5. Jelölje be az **Eredettípus hozzárendelése** négyzetet.
6. Állítsa az **Értékesítési forrás típusa** mezőt **Munkarendelés-integráció** értékre.
7. Válassza a **Mentés** lehetőséget.


### <a name="setup-in-data-integration"></a>Adatintegráció beállítása

Ügyeljen arra, hogy legyen **integrációs kulcs** ehhez: **msdyn_workorders**
1. Lépjen az Adatintegrációra
2. Válassza ki a **Csatlakozás beállítása** fület
3. Válassza ki a munkarendelés szinkronizálásához használt csatlakozási beállítást.
4. Válassza ki az **Integrációs kulcs** fület
5. Keresse meg a msdyn_workorders elemet, és ügyeljen arra, hogy a **msdyn_name (munkarendelés száma)** legyen hozzáadva. Ha nem látható, kattintson a **Kulcs hozzáadása** elemre a hozzáadáshoz, majd kattintson a **Mentés** elemre a lap tetején.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.

### <a name="work-orders-to-sales-orders-field-service-to-fin-and-ops-workorderheader"></a>Munkarendelések - értékesítési rendelések (Field Service - Finance and Operations): WorkOrderHeader

Szűrő: (msdyn_systemstatus ne 690970005) and (msdyn_systemstatus ne 690970000) és (msdynce_hasexternallymaintainedproductsonly eq true)

[![Sablonleképezés az adatintegrátorban](./media/FSWorkOrder1.png )](./media/FSWorkOrder1.png)

### <a name="work-orders-to-sales-orders-field-service-to-fin-and-ops-workorderservicelineestimate"></a>Munkarendelések - értékesítési rendelések (Field Service - Finance and Operations): WorkOrderServiceLineEstimate

Szűrő: (msdynce_headersystemstatus ne 690970005) and (msdynce_headersystemstatus ne 690970000) és (msdynce_orderhasexternalmaintainedproductsonly eq true) és (msdyn_linestatus eq 690970000) és (msdynce_headersystemstatus ne 690970004)

[![Sablonleképezés az adatintegrátorban](./media/FSWorkOrder2.png )](./media/FSWorkOrder2.png)

### <a name="work-orders-to-sales-orders-field-service-to-fin-and-ops-workorderservicelineused"></a>Munkarendelések - értékesítési rendelések (Field Service - Finance and Operations): WorkOrderServiceLineUsed

Szűrő: (msdynce_headersystemstatus ne 690970005) és (msdynce_headersystemstatus ne 690970000) és (msdynce_orderhasexternalmaintainedproductsonly eq true) és ((msdyn_linestatus eq 690970001) vagy (msdynce_headersystemstatus eq 690970004))

[![Sablonleképezés az adatintegrátorban](./media/FSWorkOrder3.png )](./media/FSWorkOrder3.png)

### <a name="work-orders-to-sales-orders-field-service-to-fin-and-ops-workorderproductlineestimate"></a>Munkarendelések - értékesítési rendelések (Field Service - Finance and Operations): WorkOrderProductLineEstimate

Szűrő: (msdynce_headersystemstatus ne 690970005) és (msdynce_headersystemstatus ne 690970000) és (msdynce_orderhasexternalmaintainedproductsonly eq true) és (msdyn_linestatus eq 690970000) és (msdynce_headersystemstatus ne 690970004) és (msdyn_allocated eq true)

[![Sablonleképezés az adatintegrátorban](./media/FSWorkOrder4.png )](./media/FSWorkOrder4.png)

### <a name="work-orders-to-sales-orders-field-service-to-fin-and-ops-workorderproductlineused"></a>Munkarendelések - értékesítési rendelések (Field Service - Finance and Operations): WorkOrderProductLineUsed

Szűrő: (msdynce_headersystemstatus ne 690970005) és (msdynce_headersystemstatus ne 690970000) és (msdynce_orderhasexternalmaintainedproductsonly eq true) és ((msdyn_linestatus eq 690970001) vagy (msdynce_headersystemstatus eq 690970004) vagy (msdyn_allocated ne true))

[![Sablonleképezés az adatintegrátorban](./media/FSWorkOrder5.png )](./media/FSWorkOrder5.png)

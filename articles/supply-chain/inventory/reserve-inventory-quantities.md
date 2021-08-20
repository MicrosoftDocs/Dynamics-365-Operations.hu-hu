---
title: Tartalék készletmennyiségek
description: Ez a témakör leírja a készlet lefoglalásával kapcsolatos különböző lehetőségeket.
author: perlynne
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 207264
ms.assetid: 47537e4f-cdf6-4813-96fd-c945b2dfe9d4
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 43443f510f5b8a627b4fd2b391c0c63d7d2ed147f1dea8f9cdd78a07009c2449
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6764860"
---
# <a name="reserve-inventory-quantities"></a>Tartalék készletmennyiségek

[!include [banner](../includes/banner.md)]

Ez a témakör leírja a készlet lefoglalásával kapcsolatos különböző lehetőségeket.

Egy meghatározott értékesítési rendelés készletmennyiségei automatikusan lefoglalhatók. Ez azt jelenti, hogy a foglalt készletet nem lehet kivenni a raktárból más rendelésekhez a készletfoglalás (legalább részleges) visszavonásáig.

A készletfoglalásnak számos lehetséges oka lehet:
-   Aki először rendelt, azt szolgálják ki először, vagyis a vevők a rendelkezésre álló cikkeket abban a sorrendben kapják meg, ahogyan leadták a rendeléseiket.
-   Cikkhiány a hosszú szállítási idő vagy az ismeretlen szállítási időpont miatt. Előfordulhat, hogy garantálni szeretné, hogy bizonyos vevők kapják meg az elsőként rendelkezésre álló cikkeket.
-   Bizonyos vevők és bizonyos rendeléstípusok szállítási prioritást kapjanak.
-   Sorozat- vagy kötegszámokkal rendelkező cikkek. Meg lehet jelölni bizonyos cikkeket, amelyek egy meghatározott rendeléshez voltak vagy lesznek leszállítva.
-   Különlegesen rendelt cikkek, amelyek meghatározott rendelésekhez vannak lefoglalva.
-   Termelési rendelések. Meg lehet jelölni például azokat a cikkeket, amelyek meghatározott rendelésekhez készülnek.

Automatikusan végre lehet hajtani készletfoglalást új rendeléssor létrehozása esetén, vagy kézzel is be lehet állítani az egyes rendelések foglalásait. A termelési folyamat különböző szakaszaiban is lehet készletet foglalni. Csak raktározott termékeket lehet lefoglalni. Szolgáltatásokat nem lehet foglalni, mivel nincs aktuális készletük. A tényleges és a megrendelt, de még meg nem érkezett készletből is lehet foglalni. Ha nagyobb mennyiséget foglal, mint amennyi az aktuális készletben szerepel, akkor megjelenik egy üzenet, hogy ekkora mennyiséget nem lehet foglalni. Ezután választani lehet, hogy mégis megtörténjen-e a foglalás, vagy módosítja a rendelt mennyiséget. A mennyiség lefoglalható vagy módosítható. Ha több cikket foglal, mint amennyi rendelkezésre áll, akkor a hiányt a következő olyan alkalommal fogja fedezni a program, amikor rendelkezésre állnak a szállítandó cikkek.

## <a name="inventory-reservation-policies"></a>Készletfoglalási szabályok
A készletfoglalási szabályok a **Cikkmodellcsoportok** lapon, a **Készlet- és raktárkezelési paraméterek** lapon és a **Termelési paraméterek** lapon olvashatók.
### <a name="policies-on-the-item-model-groups-page"></a>A Cikkmodellcsoportok lap szabályai

A **Készletszabályok** szakasz tartalmazza a következő foglalási szabályokat.

| &nbsp;                  | &nbsp;                                                                                                                                     |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Foglalási irányelvek**  | **Leírás**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| FIFO dátumvezérelt    | Ha bejelöli a **FIFO dátumvezérelt** lehetőséget, a készletfoglalást a FIFO elv szerint rendezési dátum vezérli. A kötegek lefoglalása a cikkek bevételezésének legkorábbi dátuma alapján történik az először beérkező, először kimenő elvnek (FIFO) megfelelően.                                                                                                                                                                                                                                                                       |
| A szállítási dátumtól visszafelé | Ez a beállítás csak akkor áll rendelkezésre, ha bejelölte a **FIFO dátumvezérelt** lehetőséget. Ha bejelöli a **Szállítási dátumtól visszafelé** lehetőséget, a készlet foglalása az utolsó beérkező, első kimenő (LIFO) elv szerint a kívánt szállítási dátumtól számított fordított időrendben történik (LIFO). Ha nem áll rendelkezésre olyan bevételezés, amely a szállítási dátum előttre esik, akkor FIFO-foglalást alkalmaz a program.                                                                                                                                                                                                           |
| Cikk értékesítési foglalása  | Meghatározza, hogy a foglalás cikk kézi vagy automatikus legyen. Automatikus foglalás esetén a készletet a rendeléssorok létrehozása alkalmával foglalja le. Lehetséges foglalásokat végezni az anyagjegyzékek cikkszámszintjén (**Automatikus** beállítás), illetve az Anyagjegyzék egyes elemeire (**Alábontás** lehetőség). Az alapértelmezett érték a **Cikk értékesítési foglalása** esetén a **Kinnlevőségek paramétereiből** érkezhet. Azon az oldalon az értéket a következőképpen állíthatja be: Foglalás mező **Értékesítési alapértelmezett értékek** **szakasz** az **Általános** lapon. |
| Ugyanazon köteg kiválasztása    | Az ugyanazon kötegből való foglalás funkcióval egy értékesítési rendelést a készlet egyetlen adott kötegéből foglalhatja le. Ha szeretné használni ezt a lehetőséget, az **Összesített követelmény** lehetőségnél válassza az **Igen** elemet. További beállítások is vannak, amelyek a nyomon követési dimenzió csoport és a tárolási dimenzió csoport beállításához szükségesek. További tudnivalókért lásd az [Azonos köteg foglalása az értékesítési rendeléshez](../sales-marketing/reserve-same-batch-sales-order.md) pontot.                                                          |
| Szükséglet konszolidálása | Ez a beállítás hasonlít az **Azonos köteg kiválasztása** lehetőséghez, és egyetlen szükségletben összesíti a rendeléssorokra foglalt készleteket.                                                                                                                                                                                                                                                                                                                                                                                      |
| FEFO dátumvezérlésű    | Ezzel a beállítással a lejárati dátumhoz vagy a szavatossági dátumhoz közeli kötegeket foglalhatja le. Be kell állítania a **Kitárolási feltételek** mezőben a következők valamelyikét is: **Lejárati dátum** vagy **Szavatossági dátum**.                                                                                                                                                                                                                                                                                                                              |

#### <a name="example-for-fifo-date-controlled-and-backward-from-ship-date"></a>Példa a FIFO dátumvezérelt és a Szállítási dátumtól visszafelé lehetőségekre

Ebben a példában az „A” cikkszám aktuális készletszámához három különböző kötegszám tartozik.

| Cikkszám | Köteg száma | Mennyiség | Dátum             |
|-------------|--------------|----------|------------------|
| A:           | 1000         | 5        | 2016. február 2. |
| A:           | 1001         | 3        | 2016. január 1.  |
| A:           | 1002         | 7        | 2016. március 3.    |

Egy automatikus foglalást alkalmazó, 2016. április 4-i szállítási határidővel rendelkező értékesítési rendelés a következő kötegfoglalást tenné:
-   Ha sem a **FIFO dátumvezérelt**, sem a **szállítási dátumtól visszafelé** jelölőnégyzet nincs bejelölve, az 1000-es köteg van lefoglalva, mert az a legkisebb számú köteg.
-   Ha a **FIFO dátumvezérelt** jelölőnégyzet be van jelölve, és a **szállítási dátumtól visszafelé** jelölőnégyzet nincs bejelölve, az 1001-es köteg van lefoglalva, mert ez a bevételezés első napjának kötege (FIFO).
-   Ha sem a **FIFO dátumvezérelt**, sem a **szállítási dátumtól visszafelé** jelölőnégyzet nincs bejelölve, az 1002-es köteg van lefoglalva, mert az a köteg van legközelebb az értékesítési rendelés szállítási dátumához.

### <a name="policies-on-the-inventory-and-warehouse-management-parameter-page"></a>A készlet- és raktárkezelési modul paraméteroldal szabályai

A **Készlet- és raktárkezelési paraméterek** lapon levő foglalásokhoz két lehetőség kapcsolódik:
-   Az **Általános** lap **Megrendelési cikkek lefoglalása** pontjában lefoglalhatja azokat a cikkbevételeket, amelyek a Kinnlevőségek, a Projektvezetés és könyvelés, valamint a Termelésirányítás cikk-kiadásaira vannak megrendelve. Ha törli ezt a beállítást, csak a ténylegesen bevételezett cikkeket foglalhatja le. Ha egy adott cikknél be van állítva a negatív készlet engedélyezése, ez a mező nem releváns.
-   A **Cikkek automatikus lefoglalása** beállítás a **Szállítás** lapon meghatározza az alapértelmezett beállításban, hogy a program automatikusan lefoglalja-e az átmozgatási rendelésekhez a cikkeket. Az alapértelmezett beállítás az egyes átmozgatási rendeléseken felülbírálható.

### <a name="inventory-reservation-policies-on-the-production-parameters-page"></a>Készletfoglalási szabályok a Termelési paraméterek lapon

A **Termelési paraméterek** **Általános** lapján levő **Foglalás** mező értéke határozza meg azt az alapértelmezett pontot a termelési folyamatban, amelyen a készletet le kell lefoglalni. Például a készletet a munka ütemezése során vagy a munka megkezdése után lehet lefoglalni.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
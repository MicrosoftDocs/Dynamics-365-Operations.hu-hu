---
title: Potenciális vevők készpénzre váltási adatainak áttelepítése a Data Integrator szolgáltatásból kettős írásba
description: Ez a témakör bemutatja a Potenciális vevők készpénzre váltási adatainak áttelepítését a Data Integrator szolgáltatásból kettős írásba.
author: RamaKrishnamoorthy
ms.date: 01/04/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: d119a9e5874f73e024cedc4cdb581f947e5bf1a0
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/10/2021
ms.locfileid: "7782505"
---
# <a name="migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>Potenciális vevők készpénzre váltási adatainak áttelepítése a Data Integrator szolgáltatásból kettős írásba

[!include [banner](../../includes/banner.md)]

A Potenciális vevők készpénzre váltási adatainak a Data Integrator szolgáltatásból kettős írásba történő áttelepítéséhez kövesse az alábbi lépéseket.

1. Futtassa a Potenciális vevők készpénzre váltása Data Integrator feladatokat egy utolsó teljes szinkronizálás lefuttatása érdekében. Ezzel a módszerrel gondoskodik arról, hogy mindkét rendszer (Finance and Operations alkalmazások és az ügyfélkapcsolati alkalmazások) minden adatot tartalmazzanak.
2. A potenciális adatvesztés elkerülése érdekében exportálja a Potenciális vevők készpénzre váltása adatokat a Microsoft Dynamics 365 Sales szolgáltatásból egy Excel-fájlba vagy egy vesszővel tagolt (CSV-) fájlba. Exportálja a következő entitások adatait:

    - [Könyvelési számla](#account-table)
    - [Kapcsolat](#contact-table)
    - [Számla](#invoice-table)
    - Termékek számlázása
    - [Megrendelés](#order-table)
    - [Termékek rendelése](#order-products-table)
    - [Termékek](#products-table)
    - [Árajánlat](#quote-and-quote-product-tables)
    - [Termékekkel kapcsolatos árajánlatok](#quote-and-quote-product-tables)

3. Távolítsa el a Potenciális vevők készpénzre váltása megoldást a Sales-környezetből. Ez a lépés eltávolítja a Potenciális vevők készpénzre váltása megoldás által bevezetett oszlopokat és a hozzájuk tartozó adatokat.
4. Telepítse a kettős írású megoldást.
5. Hozzon létre kettős írású kapcsolatot a Finance and Operations alkalmazás és az ügyfélkapcsolati alkalmazás között egy vagy több jogi személy számára.
6. Engedélyezze a kettős írású táblaleképezéseket, és futtassa a szükséges hivatkozási adatok kezdeti szinkronizálását. (További információk: [Szempontok a kezdeti szinkronizáláshoz](initial-sync-guidance.md).) A szükséges adatok közé tartoznak például a vevőcsoportok, a fizetési feltételek és a fizetési ütemezések. Ne engedélyezze a kettős írású leképezéseket az inicializálást igénylő tábláknál, például a számla, az árajánlat, az ajánlati sor, a rendelés és a rendelésisor-táblák esetében.
7. Az ügyfélkapcsolati alkalmazásban lépjen a **Speciális beállítások \> Rendszerbeállítások \> Adatkezelés \> Észlelési szabályok duplikálása** pontra, és tiltsa le az összes szabályt.
8. Inicializálja a 2. lépésben felsorolt táblákat. Az útmutatás a témakör további részeiben található.
9. Nyissa meg a Finance and Operations alkalmazást és engedélyezze a táblaleképezéseket, például a számla-, árajánlat-, ajánlatsor-, rendelés- és rendelésisortábla-leképezéseket. Ezután futtassa a kezdeti szinkronizálást. (További információk: [Szempontok a kezdeti szinkronizáláshoz](initial-sync-guidance.md).) Ez a folyamat a Finance and Operations alkalmazásból származó további adatokat, például a feldolgozási állapotot, a szállítási és számlázási címeket, a helyeket és a raktárokat fogja szinkronizálni.

## <a name="account-table"></a>Számla tábla

1. A **Vállalat** oszlopban adja meg a vállalat nevét, például **USMF**.
2. A **Kapcsolat típusa** oszlopban a **Vevő** értéke statikus érték legyen. Előfordulhat, hogy az üzleti logikában nem szeretne minden számlarekordot vevőként osztályozni.
3. A **Vevőcsoport azonosítója** oszlopban adja meg a Finance and Operations alkalmazás vevőcsoportjának számát. A potenciális ügyfelek készpénzre váltása megoldás alapértelmezett értéke **10**.
4. Ha A potenciális ügyfelek készpénzre váltása megoldás megoldást a **Számlaszám** testreszabása nélkül használja, adjon meg egy **Számlaszám** értéket a **Fél száma** oszlopban. Ha testreszabott beállítások vannak, és nem tudja a fél számát, keresse meg ezt az információt a Finance and Operations alkalmazásban.

## <a name="contact-table"></a>Kapcsolattartó tábla

1. A **Vállalat** oszlopban adja meg a vállalat nevét, például **USMF**.
2. Állítsa be a következő oszlopokat a CSV-fájl **IsActiveCustomer** értéke alapján:

    - Ha a CSV-fájlban az **IsActiveCustomer** beállítása **Igen**, állítsa **Igen** beállításra az **Árusítható** oszlopot. A **Vevőcsoport azonosítója** oszlopban adja meg a Finance and Operations alkalmazás vevőcsoportjának számát. A potenciális ügyfelek készpénzre váltása megoldás alapértelmezett értéke **10**.
    - Ha a CSV-fájlban az **IsActiveCustomer** beállítás **Nem**, állítsa **Nem** beállításra az **Árusítható** oszlopot, és állítsa **Vevő** értékre a **Kapcsolattartó** oszlopot.

3. Ha A potenciális ügyfelek készpénzre váltása megoldást a **Kapcsolattartó számának** testreszabása nélkül használja, állítsa be a következő oszlopokat:

    - Telepítse át a kapcsolattartó számát a CSV-fájlból (**msdynce\_ contactnumber**) a **Kapcsolattartó** táblában található kapcsolattartói számba (**msdyn\_ contactnumber**).
    - Használja a **Fél száma** oszlopban található **Kapcsolattartó száma** tábla értékeit.
    - Használja a **Számlaszám/Kapcsolattartó személy azonosítója** oszlopban található **Fél száma** tábla értékeit.

## <a name="invoice-table"></a>Számlatábla

Mivel a **Számla** táblában szereplő adatok egy irányba való áramlásra vannak kialakítva, a Finance and Operations alkalmazásból az ügyfélkapcsolati alkalmazásba történő áramláshoz nincs szükség inicializálásra. Futtass a kezdeti szinkronizálást az összes szükséges adatnak a Finance and Operations alkalmazásból az ügyfélkapcsolati alkalmazásba való áttelepítéséhez. További tájékoztatás: [Szempontok a kezdeti szinkronizáláshoz](initial-sync-guidance.md).

## <a name="order-table"></a>Rendeléstábla

1. A **Vállalat** oszlopban adja meg a vállalat nevét, például **USMF**.
2. Másolja a CSV-fájl **Rendelésazonosító** oszlopában található értéket az **Értékesítési rendelés száma** oszlopba.
3. Másolja a CSV-fájl **Vevő** oszlopában található értéket a **Számla vevői száma** oszlopba.
4. Másolja a CSV-fájl **Szállítás országa/régiója** oszlopában található értéket a **Szállítás országa/régiója** oszlopba. Ilyen érték lehet például az **US** és az **Egyesült Államok**.
5. Állítsa be a **Kért átvételi dátum** oszlopot. Ha nem használ átvételi dátumot, használja a CSV-fájl **Kért szállítási dátum**, **Teljesítési dátum** és **Elküldés dátuma** oszlopait. Erre az értékre példa a **2020-03-27T00:00:00Z**.
6. Állítsa be a **Nyelv** oszlopot. Erre az értékre példa az **en-us**.
7. Állítsa be a **Rendeléstípus** oszlopot a **Cikkalapú** oszlop segítségével.

## <a name="order-products-table"></a>Termékek rendelése tábla

- A **Vállalat** oszlopban adja meg a vállalat nevét, például **USMF**.

## <a name="products-table"></a>Termékek tábla

Mivel a **Termékek** táblában szereplő adatok egy irányba való áramlásra vannak kialakítva, a Finance and Operations alkalmazásból az ügyfélkapcsolati alkalmazásba történő áramláshoz nincs szükség inicializálásra. Futtass a kezdeti szinkronizálást az összes szükséges adatnak a Finance and Operations alkalmazásból az ügyfélkapcsolati alkalmazásba való áttelepítéséhez. További tájékoztatás: [Szempontok a kezdeti szinkronizáláshoz](initial-sync-guidance.md).

## <a name="quote-and-quote-product-tables"></a>Árajánlat és az Ajánlat terméke táblák

Az **Árajánlat** táblában kövesse a témakör korábbi, [Rendeléstábla](#order-table) szakaszának utasításait. Az **Ajánlat terméke** táblában kövesse a témakör korábbi, [Termékek rendelése tábla](#order-products-table) szakaszának utasításait.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
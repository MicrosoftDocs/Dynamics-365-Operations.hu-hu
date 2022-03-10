---
title: Potenciális vevők készpénzre váltási adatainak áttelepítése a Data Integrator szolgáltatásból kettős írásba
description: Ez a témakör bemutatja a Potenciális vevők készpénzre váltási adatainak áttelepítését a Data Integrator szolgáltatásból kettős írásba.
author: RamaKrishnamoorthy
ms.date: 02/01/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-26
ms.openlocfilehash: 82bfb768b0ecac04184f4b806527346d39584d64
ms.sourcegitcommit: 7893ffb081c36838f110fadf29a183f9bdb72dd3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/02/2022
ms.locfileid: "8087268"
---
# <a name="migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>A Potenciális vevők készpénzre váltása megoldás adatainak áttelepítése az adatintegrátor megoldásból a kettős írás szolgáltatásba

[!include [banner](../../includes/banner.md)]

A Data Integrator számára elérhető Prospect to cash megoldás nem kompatibilis a kettős írással. Ennek oka az msdynce_AccountNumber index a számlatáblázatban, amely a Prospect to cash megoldás részeként érkezett. Ha ez az index létezik, akkor nem hozható létre ugyanaz az ügyfélszámla két különböző jogi személynél. Dönthet úgy, hogy újból kezdi a kettős írást úgy, hogy a potenciális ügyfeleket készpénzadatokra migrálja a Data Integratorból kettős írásra, vagy telepítheti a Prospect to cash megoldás utolsó „alvó” verzióját. Ez a téma mindkét megközelítést lefedi.

## <a name="install-the-last-dorman-version-of-the-data-integrator-prospect-to-cash-solution"></a>Telepítse a Data Integrator Prospect to cash megoldás utolsó „alvó” verzióját

**P2C verzió 15.0.0.2** az adatintegrátor Prospect to cash megoldás utolsó "alvó" verziójának tekinthető. Letöltheti innen [FastTrack for Dynamics 365](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/P2C).

Kézzel kell telepítenie. A telepítés után minden pontosan ugyanaz marad, kivéve az msdynce_AccountNumber indexet.

## <a name="steps-to-migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>A Prospect készpénzadatokra történő migrálásának lépései a Data Integratorból a kettős írásra

A Potenciális vevők készpénzre váltási adatainak a Data Integrator szolgáltatásból kettős írásba történő áttelepítéséhez kövesse az alábbi lépéseket.

1. Futtassa a Potenciális vevők készpénzre váltása Data Integrator feladatokat egy utolsó teljes szinkronizálás lefuttatása érdekében. Ily módon biztosítja, hogy mindkét rendszer (a Pénzügyi és Operatív alkalmazások és az Ügyfél-elköteleződési alkalmazások) rendelkezzen az összes adattal.
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
5. Hozzon létre kettős írási kapcsolatot a Finance and Operations alkalmazás és az ügyfél-elköteleződés alkalmazás között egy vagy több jogi személy számára.
6. Engedélyezze a kettős írású táblaleképezéseket, és futtassa a szükséges hivatkozási adatok kezdeti szinkronizálását. (További információk: [Szempontok a kezdeti szinkronizáláshoz](initial-sync-guidance.md).) A szükséges adatok közé tartoznak például a vevőcsoportok, a fizetési feltételek és a fizetési ütemezések. Ne engedélyezze a kettős írású leképezéseket az inicializálást igénylő tábláknál, például a számla, az árajánlat, az ajánlati sor, a rendelés és a rendelésisor-táblák esetében.
7. Az ügyfélkapcsolati alkalmazásban lépjen a **Speciális beállítások \> Rendszerbeállítások \> Adatkezelés \> Észlelési szabályok duplikálása** pontra, és tiltsa le az összes szabályt.
8. Inicializálja a 2. lépésben felsorolt táblákat. Az útmutatás a témakör további részeiben található.
9. Nyissa meg a Finance and Operations alkalmazást, és engedélyezze a táblázattérképeket, például a számla-, árajánlat-, árajánlatsor-, rendelés- és rendelési sor táblázattérképeket. Ezután futtassa a kezdeti szinkronizálást. (További információért lásd [A kezdeti szinkronizálás szempontjai](initial-sync-guidance.md) .) Ez a folyamat további információkat szinkronizál a Finance and Operations alkalmazásból, például a feldolgozás állapotát, a szállítási és számlázási címeket, a telephelyeket és a raktárakat.

## <a name="account-table"></a>Számla tábla

1. A **Vállalat** oszlopban adja meg a vállalat nevét, például **USMF**.
2. A **Kapcsolat típusa** oszlopban a **Vevő** értéke statikus érték legyen. Előfordulhat, hogy az üzleti logikában nem szeretne minden számlarekordot vevőként osztályozni.
3. Ban,-ben **Ügyfélcsoport azonosítója** oszlopban adja meg az ügyfélcsoport számát a Finance and Operations alkalmazásból. A potenciális ügyfelek készpénzre váltása megoldás alapértelmezett értéke **10**.
4. Ha A potenciális ügyfelek készpénzre váltása megoldás megoldást a **Számlaszám** testreszabása nélkül használja, adjon meg egy **Számlaszám** értéket a **Fél száma** oszlopban. Ha vannak testreszabások, és nem ismeri a párt számát, húzza ki ezt az információt a Finance and Operations alkalmazásból.

## <a name="contact-table"></a>Kapcsolattartó tábla

1. A **Vállalat** oszlopban adja meg a vállalat nevét, például **USMF**.
2. Állítsa be a következő oszlopokat a CSV-fájl **IsActiveCustomer** értéke alapján:

    - Ha a CSV-fájlban az **IsActiveCustomer** beállítása **Igen**, állítsa **Igen** beállításra az **Árusítható** oszlopot. Ban,-ben **Ügyfélcsoport azonosítója** oszlopban adja meg az ügyfélcsoport számát a Finance and Operations alkalmazásból. A potenciális ügyfelek készpénzre váltása megoldás alapértelmezett értéke **10**.
    - Ha a CSV-fájlban az **IsActiveCustomer** beállítás **Nem**, állítsa **Nem** beállításra az **Árusítható** oszlopot, és állítsa **Vevő** értékre a **Kapcsolattartó** oszlopot.

3. Ha A potenciális ügyfelek készpénzre váltása megoldást a **Kapcsolattartó számának** testreszabása nélkül használja, állítsa be a következő oszlopokat:

    - Telepítse át a kapcsolattartó számát a CSV-fájlból (**msdynce\_contactnumber**) a **Kapcsolattartó** táblában található kapcsolattartói számba (**msdyn\_contactnumber**).
    - Használja a **Fél száma** oszlopban található **Kapcsolattartó száma** tábla értékeit.
    - Használja a **Számlaszám/Kapcsolattartó személy azonosítója** oszlopban található **Fél száma** tábla értékeit.

## <a name="invoice-table"></a>Számlatábla

Mivel az adatok a **Számla** A táblázatot úgy tervezték, hogy egyirányú legyen, a Finance and Operations alkalmazástól az ügyfélelköteleződési alkalmazásig, nincs szükség inicializálásra. Futtassa a kezdeti szinkronizálást az összes szükséges adat migrálásához a Finance and Operations alkalmazásból az ügyfél-elköteleződés alkalmazásba. További tájékoztatás: [Szempontok a kezdeti szinkronizáláshoz](initial-sync-guidance.md).

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

Mivel az adatok a **Termékek** A táblázatot úgy tervezték, hogy egyirányú legyen, a Finance and Operations alkalmazástól az ügyfélelköteleződési alkalmazásig, nincs szükség inicializálásra. Futtassa a kezdeti szinkronizálást az összes szükséges adat migrálásához a Finance and Operations alkalmazásból az ügyfél-elköteleződés alkalmazásba. További tájékoztatás: [Szempontok a kezdeti szinkronizáláshoz](initial-sync-guidance.md).

## <a name="quote-and-quote-product-tables"></a>Árajánlat és az Ajánlat terméke táblák

Az **Árajánlat** táblában kövesse a témakör korábbi, [Rendeléstábla](#order-table) szakaszának utasításait. Az **Ajánlat terméke** táblában kövesse a témakör korábbi, [Termékek rendelése tábla](#order-products-table) szakaszának utasításait.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

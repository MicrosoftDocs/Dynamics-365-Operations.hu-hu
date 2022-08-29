---
title: A Potenciális vevők készpénzre váltása megoldás adatainak áttelepítése az adatintegrátor megoldásból a kettős írás szolgáltatásba
description: Ez a témakör azt ismerteti, hogyan lehet áttűnni a potenciális vevőt az Adat integrátorból a kettős írásba.
author: RamaKrishnamoorthy
ms.date: 02/01/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-26
ms.openlocfilehash: bbf5a7c2f409003816e2becf1a58ee7d7d5aafb2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289080"
---
# <a name="migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>A Potenciális vevők készpénzre váltása megoldás adatainak áttelepítése az adatintegrátor megoldásból a kettős írás szolgáltatásba

[!include [banner](../../includes/banner.md)]

Az Adat integrátorhoz elérhető potenciális vevő készpénzes megoldás nem kompatibilis kettős írással. Ez azért van, mert msdynce_AccountNumber a potenciális vevő készpénzes megoldás részeként létre jött számlatábla indexe. Ha létezik ez az index, nem hozhatja létre ugyanazt a vevőszámot két különböző jogi személynél. Választhat, hogy kettős írással kezdődjon a frissítés, ha a potenciális vevőt át kell telepítenie az Data Integrator rendszerből a kettős írású készpénzadatokra, vagy telepítheti a potenciális vevő utolsó "pénztári" verzióját a készpénzes megoldásba. Ez a cikk mindkét megközelítésre vonatkozik.

## <a name="install-the-last-dorman-version-of-the-data-integrator-prospect-to-cash-solution"></a>Az Adat integrátor potenciális vevő utolsó "pénztári" verziójának telepítése a készpénzes megoldásba

**A P2C15.0.0.2** verzió a Potenciális vevő készpénzes megoldásának utolsó "tanácsadó" verziójának számít. Innen töltheti le [FastTrack for Dynamics 365](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/P2C).

Manuálisan kell telepítenie. A telepítés után minden pontosan ugyanaz marad, kivéve az msdynce_AccountNumber index eltávolítása.

## <a name="steps-to-migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>A potenciális vevőnek az Adat integrátorból a kettős írásba való áttelepítéséhez szükséges lépések

A Potenciális vevők készpénzre váltási adatainak a Data Integrator szolgáltatásból kettős írásba történő áttelepítéséhez kövesse az alábbi lépéseket.

1. Futtassa a Potenciális vevők készpénzre váltása Data Integrator feladatokat egy utolsó teljes szinkronizálás lefuttatása érdekében. Így garantálhatja, hogy mind a rendszerek (a pénzügyi, mind a művelet-, mind az ügyfél-tevékenységi alkalmazások) minden adatot tartalmaznak.
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
5. Kettős írású kapcsolat létrehozása a pénzügyi és az üzemeltetési alkalmazás, valamint egy vagy több jogi személy vevői megállapodási alkalmazása között.
6. Engedélyezze a kettős írású táblaleképezéseket, és futtassa a szükséges hivatkozási adatok kezdeti szinkronizálását. (További információk: [Szempontok a kezdeti szinkronizáláshoz](initial-sync-guidance.md).) A szükséges adatok közé tartoznak például a vevőcsoportok, a fizetési feltételek és a fizetési ütemezések. Ne engedélyezze a kettős írású leképezéseket az inicializálást igénylő tábláknál, például a számla, az árajánlat, az ajánlati sor, a rendelés és a rendelésisor-táblák esetében.
7. Az ügyfélkapcsolati alkalmazásban lépjen a **Speciális beállítások \> Rendszerbeállítások \> Adatkezelés \> Észlelési szabályok duplikálása** pontra, és tiltsa le az összes szabályt.
8. Inicializálja a 2. lépésben felsorolt táblákat. Az útmutatás a cikk további részeiben olvasható.
9. A Pénzügy és műveletek alkalmazás megnyitása és a táblatérképek engedélyezése, például a számla, ajánlat, ajánlatsor, rendelés és rendeléssor tábla-leképezések. Ezután futtassa a kezdeti szinkronizálást. (További tájékoztatás: [A kezdeti szinkronizálással kapcsolatos szempontok](initial-sync-guidance.md).) Ez a folyamat a pénzügyi és műveleti alkalmazásból származó további adatokat, például a feldolgozás állapotát, a szállítási és számlázási címeket, a helyeket és a raktárokat fogja szinkronizálni.

## <a name="account-table"></a>Számla tábla

1. A **Vállalat** oszlopban adja meg a vállalat nevét, például **USMF**.
2. A **Kapcsolat típusa** oszlopban a **Vevő** értéke statikus érték legyen. Előfordulhat, hogy az üzleti logikában nem szeretne minden számlarekordot vevőként osztályozni.
3. A Vevőcsoport **azonosítója oszlopban** adja meg a vevőcsoport számát a Pénzügyi és műveletek alkalmazásból. A potenciális ügyfelek készpénzre váltása megoldás alapértelmezett értéke **10**.
4. Ha A potenciális ügyfelek készpénzre váltása megoldás megoldást a **Számlaszám** testreszabása nélkül használja, adjon meg egy **Számlaszám** értéket a **Fél száma** oszlopban. Ha testreszabott beállítások vannak, és nem tudja a fél számát, akkor ezt az információt a Pénzügy és műveletek alkalmazásból tudja le.

## <a name="contact-table"></a>Kapcsolattartó tábla

1. A **Vállalat** oszlopban adja meg a vállalat nevét, például **USMF**.
2. Állítsa be a következő oszlopokat a CSV-fájl **IsActiveCustomer** értéke alapján:

    - Ha a CSV-fájlban az **IsActiveCustomer** beállítása **Igen**, állítsa **Igen** beállításra az **Árusítható** oszlopot. A Vevőcsoport **azonosítója oszlopban** adja meg a vevőcsoport számát a Pénzügyi és műveletek alkalmazásból. A potenciális ügyfelek készpénzre váltása megoldás alapértelmezett értéke **10**.
    - Ha a CSV-fájlban az **IsActiveCustomer** beállítás **Nem**, állítsa **Nem** beállításra az **Árusítható** oszlopot, és állítsa **Vevő** értékre a **Kapcsolattartó** oszlopot.

3. Ha A potenciális ügyfelek készpénzre váltása megoldást a **Kapcsolattartó számának** testreszabása nélkül használja, állítsa be a következő oszlopokat:

    - Telepítse át a kapcsolattartó számát a CSV-fájlból (**msdynce\_contactnumber**) a **Kapcsolattartó** táblában található kapcsolattartói számba (**msdyn\_contactnumber**).
    - Használja a **Fél száma** oszlopban található **Kapcsolattartó száma** tábla értékeit.
    - Használja a **Számlaszám/Kapcsolattartó személy azonosítója** oszlopban található **Fél száma** tábla értékeit.

## <a name="invoice-table"></a>Számlatábla

Mivel a Számla **táblából** származó adatok egy módon való áramlásra vannak kialakítva, a pénzügyek és műveletek alkalmazásból a vevői együttműködés alkalmazásba nem szükséges inicializálni. Futtassa a kezdeti szinkronizálást, hogy minden szükséges adatot átvesz a pénzügyek és műveletek alkalmazásból az ügyfél-kapcsolati alkalmazásba. További tájékoztatás: [Szempontok a kezdeti szinkronizáláshoz](initial-sync-guidance.md).

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

Mivel a Termékek táblában **található** adatok egy módon való áramlásra vannak kialakítva, a pénzügyek és a műveletek alkalmazásból az ügyfél-együttműködés alkalmazásba való folyamatra nincs szükség inicializálásra. Futtassa a kezdeti szinkronizálást, hogy minden szükséges adatot átvesz a pénzügyek és műveletek alkalmazásból az ügyfél-kapcsolati alkalmazásba. További tájékoztatás: [Szempontok a kezdeti szinkronizáláshoz](initial-sync-guidance.md).

## <a name="quote-and-quote-product-tables"></a>Árajánlat és az Ajánlat terméke táblák

Az Árajánlatok **táblában** kövesse a [cikk korábbi, Rendelés tábla](#order-table) szakaszának utasításait. Az **Ajánlat terméke** táblában kövesse a témakör korábbi, [Termékek rendelése tábla](#order-products-table) szakaszának utasításait.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]


---
title: Több felvételi szállítási mód engedélyezése a vevői rendelésekhez
description: Ez a témakör a Microsoft Dynamics 365 Commerce azon funkcióit ismerteti, amelyek lehetővé teszik vevői rendelések létrehozását az üzletben való felvételhez.
author: hhainesms
manager: annbe
ms.date: 11/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: c0879343f100fa1fe6e0a4b4fbf085574225e898
ms.sourcegitcommit: bea695707d1e7b4e2713b62405ad0e7a7a893420
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/22/2021
ms.locfileid: "5053413"
---
# <a name="enable-multiple-pickup-delivery-modes-for-customer-orders"></a>Több felvételi szállítási mód engedélyezése a vevői rendelésekhez

[!include [banner](includes/banner.md)]


A Microsoft Dynamics 365 Commerce 10.0.16-os és újabb verziójában a szervezetek több szállítási módot is definiálhatnak, amelyek közül a vásárlók vagy az értékesítési munkatársak választhatnak, amikor olyan rendelést hoznak létre, amelyet egy üzletben vesznek fel. Ily módon a szervezetek több felvételi lehetőséget is biztosíthatnak a vásárlóknak. Például sok kiskereskedő kínálja a vásárlóknak a megrendeléseikhez a bolton belüli felvétel vagy az üzlet előtti felvétel választását. A Commerce támogatja a különböző felvételi típusú kézbesítési módok konfigurálását. A felhasználók ezután kihasználhatják őket, amikor vevői rendeléseket hoznak létre bármely támogatott kereskedelmi csatornán (e-kereskedelem, hívásközpont vagy áruház).

## <a name="enable-and-configure-pickup-delivery-modes"></a>Átvételi szállítási módok engedélyezése és konfigurálása

A funkció használatához kapcsolja be a **Több felvételi szállítási mód engedélyezése** funkciót a Commerce-központ **Funkciókezelési** munkaterületén. A funkció bekapcsolása után további konfigurációra van szükség.

A Commerce 10.0.15-ös és korábbi verziójában a szervezetek csak egy szállítási módot határozhatnak meg a kijelölt felvételi kézbesítési szállítási módként. Ez a definíció a **Kereskedelmi paraméterek** lapon történik. A 10.0.16-os és újabb verziókban, amikor bekapcsolja a **Több felvételi szállítási mód engedélyezése** funkciót, a **Kereskedelmi paraméterek** oldalon korábban a felvételi kézbesítési módként meghatározott kézbesítési mód automatikusan átkerül a felvételi kézbesítési módok új konfigurációjába.

![Átvételi szállítási módok a Kereskedelmi paraméterek oldalon](media/multiplepickupparameter.png)

Miután bekapcsolta a **Több felvételi szállítási mód engedélyezése** funkciót, a **Kereskedelmi paraméterek** lap **Vevői rendelések** lapjának **Szállítási módok** gyorslapján több felvételi szállítási módot is definiálhat az **Átvételi szállítási mód** rácsban.

A **Kiszállítási kézbesítési mód** és az **Elektronikus kézbesítési mód** mezők, valamint a **Csak szállítmányozói mód beállításainak megjelenítése kiszállítási rendelésekhez** beállítás átkerültek erre a gyorslapra.

További felvételi kézbesítési módok konfigurálása előtt meg kell határoznia a kézbesítési módokat. A Commerce központ **Szállítási módok** lapján adja hozzá azokat a szállítási módokat, amelyeket átvételi szállítási módoknak kell tekinteni. Győződjön meg arról, hogy minden konfiguráció befejeződött. Például győződjön meg arról, hogy a kézbesítés módja megfelelő csatornákhoz és cikkekhez van kapcsolva. Ha végzett, futtassa a **Kézbesítési módok feldolgozása** feladatot a kézbesítési mód, a csatornák és a cikkek közötti kapcsolatok létrehozásához. Miután a feladat futása befejeződött, nyissa meg a **Terjesztési ütemezés** lapot a Commerce központban, és futtassa az **1120**-as terjesztési feladatot, hogy a megfelelő Commerce-csatorna-adatbázisok frissüljenek az új szállítási mód konfigurációjával.

![Példa a bolt előtti felvétel szállítási konfigurációjának módjára](media/pickupmodes.png)

Miután definiálta a további felvételi kézbesítési módokat, adja hozzá őket az **Átvételi szállítási mód** rácshoz a **Kereskedelmi paraméterek** oldalon. Ezután futtassa a megfelelő terjesztési feladatokat a megfelelő Commerce-csatorna-adatbázisok frissítéséhez a konfiguráció módosításával.

> [!NOTE]
> Eltekintve a meglévő felvételi szállítási módtól, amelyet a rendszer átmásol az **Átvételi szállítási mód** rácsba a **Több felvételi szállítási mód engedélyezése** funkciónál, minden egyes további létrehozott átvételi szállítási mód konfigurációhoz konfigurálnia kell új kézbesítési módokat. Amikor szállítási módokat ad hozzá az **Átviteli szállítási mód** rácshoz, a Commerce ellenőrzi, hogy használják-e már ezeket aktív nyitott értékesítési sorok. Ha találhatók nyitott értékesítési sorok, hibaüzenet jelenik meg. A szállítási módok nem számítanak átvételi szállítási módnak, amíg az összes ezeket használó nyitott értékesítési sort le nem zárták (számlázták vagy törölték).

> [!IMPORTANT]
> Miután több felvételi kézbesítési módot is definiált a **Kereskedelmi paraméterek** oldalon, kötelezővé válik a **Több felvételi szállítási mód engedélyezése** funkció, és már nem kapcsolható ki. Ha ki kell kapcsolnia a funkciót, egy kivételével az összes felvételi kézbesítési módot el kell távolítania az **Átvételi szállítási mód** rácsból. Ha csak egy felvételi kézbesítési mód van megadva, a funkció már nem kötelezőnek számít, és kikapcsolható.

### <a name="e-commerce-site-configurations"></a>E-kereskedelmi webhelykonfigurációk

Ha a **Több felvételi szállítási mód engedélyezése** funkció be van kapcsolva, az e-kereskedelmi oldalakon a következő modulok mutatják az új átvételi kézbesítési módokat a konfigurált módon:

- Vásárlási modul
- Áruházválasztó
- Bevásárlókocsi
- Felvételi adatok
- Rendelés visszaigazolása
- Rendelés részletei

Az e-kereskedelmi oldalakon nincs szükség további lépésekre az átvételi kézbesítési módok elérhetővé tétele érdekében.

## <a name="work-with-multiple-pickup-delivery-modes"></a>Több átvételi szállítási mód használata

Ha egy csatornához több felvételi kézbesítési mód is rendelkezésre áll, az ügyfeleknek fokozott élményben lehet részük, amikor olyan termékeket vásárolnak, amelyeket át lehet venni. 

- Az e-kereskedelmi csatornákban a vásárlók bármilyen érvényes átvételi szállítási módot választhatnak, amely elérhető. Például egy kiskereskedő két felvételi szállítási módot határoz meg (bolton belüli felvétel és útszéli felvétel), mindkettő az **Átvételi szállítási mód** rácsban van konfigurálva, és mindkettő érvényes a rendelésteljesítési csatornára és a termékre, amelyet a vásárló jelenleg vásárol. Ebben az esetben a vásárló kiválaszthatja a kívánt felvételi szállítási módot. A kiválasztott felvételi szállítási mód ezután az értékesítési rendelési sorhoz kapcsolódó szállítási móddá válik, amikor a rendelést létrehozzák a Commerce központban.

    ![Felvételi lehetőség kiválasztása az e-kereskedelemben](media/pickupecommerce.png)

- Az áruházi csatornákban, ha a vevői rendelés felvételre jön létre a pénztári (POS) alkalmazáson keresztül, az értékesítési munkatársnak kell választania a rendelkezésre álló felvételi szállítási módok közül, ha van ilyen. Ha a csatornához és a cikkhez csak egy érvényes felvételi szállítási mód érhető el, az értékesítési munkatársnak nem kell kiválasztania azt. Ehelyett a rendelkezésre álló felvételi szállítási mód automatikusan alkalmazva lesz a rendelési sorokra.

    ![Felvételi lehetőség kiválasztása a pénztár alkalmazásban](media/pickuppos.png)

- A hívásközpont-csatornákban, amikor a felhasználók felvételi rendeléseket hoznak létre, manuálisan kiválaszthatják a hívásközpont csatornához kapcsolódó bármely meghatározott felvételi kézbesítési módot. A rendszer ezután ellenőrzi, hogy a kiválasztott felvételi szállítási mód használható-e, amikor a hozzá kapcsolt cikket megrendeli. Ha a hívásközpont-csatornákban be van jelölve egy felvételi kézbesítési mód, az értékesítésirendelés-sorokat egy érvényes üzletraktárhoz kell kapcsolni. Ha egy nem bolti raktár van megadva egy hívásközpont értékesítési soron, akkor az átvételi szállítási mód nem állítható be az adott értékesítési soron.
- Az értékesítési munkatársak a pénztár alkalmazásban a **Rendelés visszahívása** vagy a **Rendelés teljesítése** művelet segítségével lekérhetik az átvételre vonatkozó rendelések vagy rendeléssorok listáját. Ha egy értékesítési munkatárs egy előre definiált keresési szűrőt használ az aktuális üzletben felveendő összes rendelés megjelenítéséhez, a lekérdezések módosulnak annak érdekében, hogy a keresési eredmények tartalmazzák az összes olyan jogosult rendelést, amely bármely átvételi szállítási módot használja. A pénztár-felhasználók a meglévő szűrők segítségével is leszűkíthetik a rendelések listáját egy adott felvételi szállítási módra. Például megjeleníthetik csak a járdaszéli felvétellel rendelkező rendeléseket.

    ![A visszahívási rendelések listájára alkalmazott felvételi kézbesítési módok szűrése](media/pickuprecallorder.png)

## <a name="considerations-for-distributed-order-management"></a>A felosztott rendeléskezelés szempontjai

A Commerce [felosztott rendeléskezelési (DOM)](https://docs.microsoft.com/dynamics365/commerce/dom) funkciói figyelmen kívül hagyják az üzleti felvételre megjelölt értékesítési sorokat. Ezek a funkciók frissültek annak érdekében, hogy a konfigurált átvételi szállítási módokhoz kapcsolódó értékesítési sorok megkerüljék a DOM logikát, és ne kerüljenek át egy új teljesítési raktárba.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
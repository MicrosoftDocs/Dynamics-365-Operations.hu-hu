---
title: Szerializált cikkek használata a pénztárban
description: Ez a témakör azt mutatja be, hogyan kell kezelni a szerializált cikkeket a pénzár(POS) alkalmazásban.
author: boycezhu
manager: annbe
ms.date: 08/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 6ba01abc3d1a4496ec586a621aa03b4981f84d76
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412975"
---
# <a name="work-with-serialized-items-in-the-pos"></a>Szerializált cikkek használata a pénztárban

[!include [banner](includes/banner.md)]

Számos kiskereskedő olyan termékeket értékesít, amelyek sorozatszám-ellenőrzést igényelnek. Ezeket a termékeket *szerializált cikkeknek* nevezzük. Előfordulhat, hogy néhány kiskereskedő meg szeretné tartani a sorozatszámokat az áruházi vagy raktárkészletben nyomon követés céljából. Míg más kiskereskedők is szeretnék rögzíteni a sorozatszámot az értékesítési folyamat során, a szolgáltatási és a jótállási célokból. Ez a témakör azt mutatja be, hogyan lehet kezelni a szerializált cikkeket a Microsoft Dynamics 365 Commerce pénzár(POS) alkalmazásban.

## <a name="serial-number-configurations"></a>Sorozatszám-konfigurációk

Egy cikk akkor tekinthető szerializált cikknek, ha egy sorozatszámokat engedélyező nyomon követési dimenziócsoporthoz van hozzárendelve. A Commerce központban a **Nyomon követési dimenziócsoportok** lapon válassza az **Aktív** lehetőséget, ha engedélyezni szeretné a sorozatszámokat a készletfolyamathoz, vagy válassza az **Aktív az értékesítési folyamatban** lehetőséget, ha engedélyezni szeretné az értékesítési folyamat sorozatszámát.

Ha a **Nyomon követési dimenziók** gyorslapon kapcsolja be az **Üres bevételezés megengedett** paramétert, hogy a sorozatszám egy opcionális bemenet legyen a készletbevételezési-folyamat során. A paraméterek kikapcsolása kötelező bemenetként adja meg a sorozatszámot. Hasonlóképpen az **Üres kiadás megengedett** paraméter határozza meg, hogy a szállítási folyamat során a sorozatszám szükséges-e.

> [!NOTE]
> Ha egy szerializált elem regisztrálásához vagy ellenőrzéséhez a **Bejövő készlet** vagy **Kimenő készlet** pénztárműveletét kívánja használni a sorozatszámok validálásához egy szerializált cikkel szemben, akkor a cikket társítani kell egy olyan nyomon követési dimenziócsoporthoz, amely úgy van beállítva, hogy engedélyezze a sorozatszámokat az **Akítv** beállítással, nem az **Aktív az értékesítési folyamatban** beállítással.

## <a name="serial-number-management-page"></a>Sorozatszám-kezelés lap

A **Bejövő készlet** és a **Kimenő készlet** pénztári műveleteinél, ha a kiválasztott, fogadott vagy leszállított cikk szerializált tétel, a **Részletek** ablaktábla tartalmaz egy **Sorszám kezelése** lehetőséget, amely a **Sorozatszám kezelése** oldalra mutat, amelyen regisztrálhatók vagy ellenőrizhetők a cikk sorozatszámai. Azt is megteheti, hogy megnyitja a **Sorozatszámkezelés** lapot a rendelés részletei nézet alkalmazássávjának **Sorozatszám** művelete kiválasztásával vagy a bevételezési folyamat során megjelenő párbeszédpanelen a **Sorozatszám kezelése** lehetőséget választva. 

A **Sorozatszám-kezelés** lap felsorolja az összes olyan nyitott sorozatszámsort, amely regisztrációra vagy ellenőrzésre vár. Ez a lap két lapból állhat: egy az aktuális cikkhez, egy másik pedig a rendelés minden szerializált cikkéhez.

A **Sorozatszám-kezelés** lap **Állapot** mezője az aktuális állapotra vonatkozó adatokat tartalmaz, amelyekben az egyes sorozatszámok vannak:

- **Nincs regisztrálva** – A sorozatszám nem lett megadva, vagy az előregisztrált sorozatszám még nincs ellenőrizve ( a fogadási folyamatban).
- **Regisztrálás** – A sorozatszám regisztrálva lett, és helyben mentették az üzlet csatorna-adatbázisába, vagy az előregisztrált sorozatszám ellenőrizve lett. A bevételezés vagy teljesítés befejezését követően csak azok a sorozatszámok lesznek beküldve a Commerce Headquarters alkalmazásba, amelyek állapota **Regisztrálás**.

## <a name="receive-serialized-items"></a>Szerializált cikkek bevételezése

A **Bejövő készlet** pénztári művelet lehetővé teszi, hogy a felhasználók a következő feladatokat végezzék el szerializált cikkekhez:

- Sorozatszámok rögzítése szerializált cikkekhez, amikor a cikkeket az üzletben a beszerzési rendelésen keresztül bevételezik.
- Előre regisztrált sorozatszámok ellenőrzése a szerializált cikkekkel szemben, amikor a cikkeket az üzletben egy beszerzési rendeléssel bevételezik.

### <a name="register-serial-numbers-against-serialized-items"></a>Sorozatszámok rögzítése a szerializált elemekkel szemben

A beszerzési rendelésekhez egy párbeszédpanel jelenik meg, amely egy szerializált elem bevételezési folyamata során felkínálja a **Sorozatszám-kezelés** lehetőséget. Ezt a lehetőséget választva megnyithatja a **Sorozatszám-kezelés** lapot, és megkezdheti a sorozatszámok regisztrálását. Ezt a lépést ki is hagyhatja a bevételezési folyamat során, és később is megadhatja a bevételezés feladása előtt.

Alapértelmezés szerint az aktuális cikk lapja jelenik meg. Minden sorozatszám-sorhoz tartozik egy üres sorozatszámértéj és egy **Nem regisztrált** állapot. Beolvashatja a sorozatszám vonalkódjait, vagy kiválaszthatja a **Sorozatszám** lehetőséget az alkalmazássávon sorozatszámoknak a folyamatos beviteléhez. A megadott sorozatszámok megjelennek a listán, és az állapotuk a **Regisztrálás** értékre módosul. A listába regisztrálható sorozatszámok maximális száma egyenlő a bevételezési mennyiséggel. Ha hibázik, akkor a **Részletek** ablaktáblában a **Szerkesztés** vagy a **Törlés** lehetőséget választva módosíthatja a megadott sorozatszámokat.

A sorozatszámokat a **Sorozatszám-kezelés** lap **Minden szerializált cikk** lapján is regisztrálhat. A listában válassza ki azt a cikket, amellyel szemben sorozatszámokat szeretne regisztrálni.

### <a name="validate-serial-numbers-on-serialized-items"></a>Sorozatszámok ellenőrzése szerializált cikkeken

Egy átmozgatási rendelés esetében a kimenő oldalon előre kell regisztrálni sorozatszámokat a szerializált elemekhez a szállítási folyamat során. Egy beszerzési rendelés esetében az előzetes szállítási értesítésen (ASN) keresztül a szállító megadhat sorozatszám-információkat, és Ön előre regisztrálhatja a számokat a szállítandó cikkekhez. Mindkét esetben a sorozatszámok a bevételezés előtt ismertek. Éppen ezért a bejövő oldalon csak ellenőrizni kell, hogy azt kapta, amit kapnia kellett.

A sorozatszámok ellenőrzéséhez a **Sorozatszám-kezelés** lapot a bevételezési folyamat során vagy a nyugta feladása előtt bármikor meg lehet nyitni. Minden olyan szerializált elemhez, amely előzetesen regisztrált sorozatszámmal rendelkezik, az összes sorozatszám automatikusan a **Nem regisztrált** állapotra lesz állítva ezen a lapon. A sorozatszámok ellenőrzéséhez beolvashatja vagy beírhatja azokat. A sorozatszám megadásakor az alkalmazás ellenőrzi, hogy megfelel-e az előregisztrált sorozatszámoknak. Ha megfelelnek, akkor az állapot **Regisztrálás** értékre módosul. Máskülönben egy hibaüzenetet kap. Azt is megteheti, hogy közvetlenül kiválasztja a sorozatszámot, majd a **Részletek** ablaktáblában kiválasztja a **Sorozatszám érvényesítése** lehetőséget, hogy a sorozatszámot gyorsan érvényesítettnek megjelölje. A listában ellenőrizhető sorozatszámok maximális száma egyenlő a bevételezési mennyiséggel.

A sorozatszámokat a **Sorozatszám-kezelés** lap **Minden szerializált cikk** lapján is ellenőrizhet. A listában válassza ki azt a cikket, amellyel szemben sorozatszámokat szeretne ellenőrizni.

## <a name="ship-serialized-items"></a>Szerializált cikkek szállítása

A **Kimenő készlet** pénztári műveletével sorozatszámokat regisztrálhat a szerializált cikkekkel szemben, amikor az átmozgatási rendelésen keresztül szállítja őket az aktuális üzletből.

### <a name="register-serial-numbers-against-serialized-items"></a>Sorozatszámok rögzítése a szerializált elemekkel szemben

Az átmozgatási rendelésekhez egy párbeszédpanel jelenik meg, amely egy szerializált elem szállítási folyamata során felkínálja a **Sorozatszám-kezelés** lehetőséget. A lehetőséget választva megnyithatja a **Sorozatszám-kezelés** lapot, és megkezdheti a sorozatszámok regisztrálását. Ezt a lépést ki is hagyhatja a szállítási folyamat során, és később is megadhatja a szállítmány feladása előtt.

Alapértelmezés szerint az aktuális cikk lapja jelenik meg. Minden sorozatszám-sorhoz tartozik egy üres sorozatszámértéj és egy **Nem regisztrált** állapot. Beolvashatja a sorozatszám vonalkódjait, vagy kiválaszthatja a **Sorozatszám** lehetőséget az alkalmazássávon sorozatszámoknak a folyamatos beviteléhez. A megadott sorozatszámok megjelennek a listán, és az állapotuk a **Regisztrálás** értékre módosul. A listába regisztrálható sorozatszámok maximális száma egyenlő a szállítási mennyiséggel. Ha hibázik, akkor a **Részletek** ablaktáblában a **Szerkesztés** vagy a **Törlés** lehetőséget választva módosíthatja a megadott sorozatszámokat.

A sorozatszámokat a **Sorozatszám-kezelés** lap **Minden szerializált cikk** lapján is regisztrálhat. A listában válassza ki azt a cikket, amellyel szemben sorozatszámokat szeretne regisztrálni.

Lehetőség van arra is, hogy a sorozatszám-elérhetőség érvényesítését egy kimenő átmozgatási rendeléshez tartozó sorozatszám-regisztráció során engedélyezze. Ha ezzel az ellenőrzéssel olyan sorozatszámot próbál szállítani, amely nem érhető el a szállító üzlet készletében, hibaüzenetet kap, és egy másik számot kell megadni.

Ha engedélyezni szeretné az ilyen érvényesítést előfeltételként a következő feladatokat kell ütemeznie, hogy ismétlődően fussanak:

- Ugorjon a **Kiskereskedelem és kereskedelem** > **Kiskereskedelem és kereskedelem IT** > **Termékek és készlet** > **Termékelérhetőség nyomon követési dimenziókkal** lehetőségre
- **Kiskereskedelem és kereskedelem** > **Elosztási ütemezések** > **1130** (**Termék elérhetősége**)

## <a name="additional-resources"></a>További erőforrások

[Bejövő készletműveletek a pénztárban](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation)

[Kimenő készletműveletek a pénztárban](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation)

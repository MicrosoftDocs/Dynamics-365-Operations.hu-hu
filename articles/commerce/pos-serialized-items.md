---
title: Szerializált cikkek használata a pénztárban
description: Ez a témakör azt mutatja be, hogyan kell kezelni a szerializált cikkeket a pénzár(POS) alkalmazásban.
author: boycezhu
manager: annbe
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycezhu
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: eedb64ae04345cb94bdd8cc68de833cfcfd40119
ms.sourcegitcommit: 39981582778b0a62567324452485a6721ca18284
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/27/2020
ms.locfileid: "3407498"
---
# <a name="work-with-serialized-items-in-the-pos"></a>Szerializált cikkek használata a pénztárban

[!include [banner](includes/banner.md)]

Számos kiskereskedő olyan termékeket értékesít, amelyek sorozatszám-ellenőrzést igényelnek. Ezeket a cikkeket *szerializált cikkeknek* nevezzük. Előfordulhat, hogy néhány kiskereskedő meg szeretné tartani a sorozatszámokat nyomon követés céljából. Míg más kiskereskedők is szeretnék rögzíteni a sorozatszámot az értékesítési folyamat során, a szolgáltatási és a jótállási célokból. Ez a témakör azt mutatja be, hogyan lehet kezelni a szerializált cikkeket a Microsoft Dynamics 365 Commerce pénzár(POS) alkalmazásban.

## <a name="serial-number-configurations"></a>Sorozatszám-konfigurációk

Egy cikk akkor tekinthető szerializált cikknek, ha egy sorozatszámokat engedélyező nyomon követési dimenziócsoporthoz van hozzárendelve. A Commerce központban **Nyomon követési dimenziócsoportok** oldalon válassza ki az **Aktív** lehetőséget a sorozatszámok engedélyezéséhez a raktárfolyamatban. A sorozatszámok engedélyezéséhez az értékesítési folyamathoz válassza az **Értékesítési folyamatban aktív** beállítást.

Ha a **Nyomon követési dimenziók** gyorslapon be van kapcsolva az **Üres bevételezés megengedett** beállítás, akkor a sorozatszám egy opcionális bemenet a készletbevételezési-folyamat során. Ha ez a beállítás ki van kapcsolva, a sorozatszám megadása kötelező.

Ha a **Sorozatszám -ellenőrzés** beállítás be van kapcsolva, a **Sorozatszámok** gyorslapon a sorozatszámnak egyedinek kell lennie egységenként. Más szóval a duplikált sorozatszámok nem engedélyezettek.

## <a name="serialized-items-in-the-receiving-process"></a>Szerializált cikkek a bevételezési folyamatban

A pénztári alkalmazás **Bejövő készlet** művelete lehetővé teszi, hogy a felhasználók a következő feladatokat végezzék el szerializált cikkekhez:

- Sorozatszámok rögzítése szerializált cikkekhez, amikor a cikkeket az üzletben a beszerzési rendelésen keresztül bevételezik.
- Előre regisztrált sorozatszámok ellenőrzése a szerializált cikkekkel szemben, amikor a cikkeket az üzletben egy beszerzési rendeléssel bevételezik.

> [!NOTE]
> kHa egy szerializált elem regisztrálásához vagy ellenőrzéséhez a **Bejövő készlet** műveletét kívánja használni, akkor a cikket társítani kell egy olyan nyomon követési dimenziócsoporthoz, amely úgy van beállítva, hogy engedélyezze a sorozatszámokat az **Akítv** beállítással, nem az **Aktív az értékesítési folyamatban** beállítással.

A bevételezési folyamat megkezdéséhez a **Bejövő készlet** műveletben a kezdhet a **Bevételezés most** nézetben egy cikk vonalkódjának beolvasásával vagy egy cikkazonosító megadásával. Azt is megteheti, hogy a tételt manuálisan választja ki a **Teljes rendelési lista** nézetben.

Ha a kiválasztott vagy bevételezett cikk szerializált tétel, a tételhez tartozó **Részletek** ablaktábla tartalmaz egy **Sorozatszám kezelése** hivatkozást amely megnyitja a **Sorozatszám kezelése** lapot. Azt is megteheti, hogy megnyitja a **Sorozatszámkezelés** lapot a rendelés részletei nézet alkalmazássávjának **Sorozatszám** eleme kiválasztásával vagy a bevételezési folyamat során megjelenő párbeszédpanelen a **Sorozatszám kezelése** lehetőséget választva. A **Sorozatszám-kezelés** lap felsorolja az összes olyan nyitott sorozatszámsort, amely regisztrációra vagy ellenőrzésre vár. Ez a lap két lapból állhat: egy az aktuális cikkhez, egy pedig a rendelés minden szerializált cikkéhez.

A **Sorozatszám-kezelés** lap **Állapot** mezője az aktuális állapotra vonatkozó adatokat tartalmaz, amelyekben az egyes sorozatszámok vannak:

- **Nincs regisztrálva** – A sorozatszám nem lett megadva, vagy az előregisztrált sorozatszám még nincs ellenőrizve.
- **Regisztrálás** – A sorozatszám regisztrálva lett, és helyben mentették az üzlet csatorna-adatbázisába, vagy az előregisztrált sorozatszám ellenőrizve lett. A bevételezés befejezését követően csak azok a sorozatszámok lesznek beküldve a Commerce Headquarters alkalmazásba, amelyek állapota **Regisztrálás**.

### <a name="register-serial-numbers-against-serialized-items"></a>Sorozatszámok rögzítése a szerializált elemekkel szemben

A beszerzési rendelésekhez egy párbeszédpanel jelenik meg, amely egy szerializált elem bevételezési folyamata során felkínálja a **Sorozatszám-kezelés** lehetőséget. Ezt a lehetőséget választva megnyithatja a **Sorozatszám-kezelés** lapot, és megkezdheti a sorozatszámok regisztrálását. Ezt a lépést ki is hagyhatja a bevételezési folyamat során, és később is megadhatja a bevételezés feladása előtt.

Alapértelmezés szerint az aktuális cikk lapja jelenik meg. Minden sorozatszám-sorhoz tartozik egy üres sorozatszámértéj és egy **Nem regisztrált** állapot. Beolvashatja a sorozatszám vonalkódjait, vagy kiválaszthatja a **Sorozatszám** lehetőséget az alkalmazássávon sorozatszámoknak a párbeszédpanelen történő folyamatos beviteléhez. A megadott sorozatszámok megjelennek a listán, és a sorozatszám-sorok állapota a **Regisztrálás** értékre módosul. A listába regisztrálható sorozatszámok maximális száma megegyezik a bevételezési mennyiséggel. Ha hibázik, akkor a **Részletek** ablaktáblában a **Szerkesztés** vagy a **Törlés** lehetőséget választva módosíthatja a megadott sorozatszámokat.

A sorozatszámokat a **Sorozatszám-kezelés** lap **Minden szerializált cikk** lapján is regisztrálhat. A listában válassza ki azt a cikket, amellyel szemben sorozatszámokat szeretne regisztrálni.

Ezen a lapon a sorozatszám-regisztráció ezen az oldalon a duplikálások ellenőrzése történik. Ha egy olyan elemhez próbál meg ismétlődő sorozatszámot megadni, amelynél a sorozatszám-ellenőrzés be van kapcsolva, hibaüzenet jelenik meg, és egy másik számot kell megadnia.

### <a name="validate-serial-numbers-on-serialized-items"></a>Sorozatszámok ellenőrzése szerializált cikkeken

Egy átmozgatási rendelés esetében a kimenő oldalon előre kell regisztrálni sorozatszámokat a szerializált elemekhez a szállítási folyamat során. Egy beszerzési rendelés esetében az előzetes szállítási értesítésen (ASN) keresztül a szállító megadhat sorozatszám-információkat, és Ön előre regisztrálhatja a számokat a szállítandó cikkekhez. Mindkét esetben a sorozatszámok a bevételezés előtt ismertek. Éppen ezért a bejövő oldalon csak ellenőrizni kell, hogy azt kapta, amit kapnia kellett.

A sorozatszámok ellenőrzéséhez a **Sorozatszám-kezelés** lapot a bevételezési folyamat során vagy a nyugta feladása előtt bármikor meg lehet nyitni. Minden olyan szerializált elemhez, amely előzetesen regisztrált sorozatszámmal rendelkezik, az összes sorozatszám automatikusan a **Nem regisztrált** állapotra lesz állítva ezen a lapon. A sorozatszámok ellenőrzéséhez beolvashatja vagy beírhatja azokat. A sorozatszám megadásakor az alkalmazás ellenőrzi, hogy megfelel-e az előregisztrált sorozatszámoknak. Ha megfelelnek, akkor az állapot **Regisztrálás** értékre módosul. Máskülönben egy hibaüzenetet kap. A listában ellenőrizhető sorozatszámok maximális száma megegyezik a bevételezési mennyiséggel.

A sorozatszámokat a **Sorozatszám-kezelés** lap **Minden szerializált cikk** lapján is ellenőrizhet. A listában válassza ki azt a cikket, amellyel szemben sorozatszámokat szeretne ellenőrizni.

## <a name="additional-resources"></a>További erőforrások

[Bejövő készletműveletek a pénztárban](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation)

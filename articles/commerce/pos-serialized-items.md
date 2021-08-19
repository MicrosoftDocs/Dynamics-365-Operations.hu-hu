---
title: Szerializált cikkek használata a pénztárban
description: Ez a témakör azt mutatja be, hogyan kell kezelni a szerializált cikkeket a pénzár(POS) alkalmazásban.
author: boycezhu
ms.date: 01/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 5725943fd249e1b5d66b08b829c2eb58b6aad3ee24db9ca83bbde9be906bbf82
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6737578"
---
# <a name="work-with-serialized-items-in-the-pos"></a>Szerializált cikkek használata a pénztárban

[!include [banner](includes/banner.md)]

Számos kiskereskedő olyan termékeket értékesít, amelyek sorozatszám-ellenőrzést igényelnek. Ezeket a termékeket *szerializált cikkeknek* nevezzük. Előfordulhat, hogy néhány kiskereskedő meg szeretné tartani a sorozatszámokat az áruházi vagy raktárkészletben nyomon követés céljából. Míg más kiskereskedők is szeretnék rögzíteni a sorozatszámot az értékesítési folyamat során, a szolgáltatási és a jótállási célokból. Ez a témakör azt mutatja be, hogyan lehet kezelni a szerializált cikkeket a Microsoft Dynamics 365 Commerce pénztár (POS) alkalmazásban.

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

## <a name="sell-serialized-items-in-pos"></a>Szerializált cikkek használata értékesítése a pénztárban

Bár a pénztáralkalmazás mindig támogatta a szerializált cikkek eladását, a Commerce 10.0.17-es és újabb verzióiban a szervezetek olyan funkciókat engedélyezhetnek, amelyek javítják a sorozatszám-követésre beállított termékek értékesítése során kiváltott üzleti logikát.

Ha a **Továbbfejlesztett sorozatszám-ellenőrzés a pénztár rendelésrögzítésében és rendelésteljesítésében** funkció engedélyezve van, a rendszer a következő termékkonfigurációkat értékeli ki a szerializált termékek pénztári értékesítése során:

- A termék **Sorozattípus** beállítása (**aktív** vagy **értékesítési folyamatban aktív**).
- **Üres kiadás megengedett** beállításai a termékre vonatkozóan.
- A termékre és/vagy az értékesítési raktárra vonatkozó **Tényleges negatív készlet** beállításai.

### <a name="active-serial-configurations"></a>Aktív sorozatkonfigurációk

Ha a pénztárban olyan cikkeket értékesít, amelyek **Aktív** sorozatszám-követési dimenzióval vannak konfigurálva, a pénztár olyan ellenőrzési logikát kezdeményez, amely megakadályozza, hogy a felhasználók végrehajtsák egy olyan sorozatszámú szerializált cikk értékesítését, amely nem található az értékesítési raktár aktuális készletében. Az ellenőrzési szabály alól két kivétel van:

- Ha a cikk **Üres kiadás megengedett** beállítással is konfigurálva van, a felhasználók átugorhatják a sorozatszám beírását, és a sorozatszám nélkül értékesíthetik a cikket.
- Ha a cikk és/vagy az értékesítési raktár úgy van beállítva, hogy engedélyezve van a **Tényleges negatív készlet**, az alkalmazás elfogad és értékesít egy olyan sorozatszámot, amely esetében nem erősíthető meg, hogy a készletben van abban a raktárban, ahol az értékesítés történik. Ez a konfiguráció lehetővé teszi, hogy az adott cikk/sorozatszám készlettranzakciója negatív állapotba kerüljön, és így a rendszer lehetővé teszi az ismeretlen sorozatszámok értékesítését.

> [!IMPORTANT]
> Annak érdekében, hogy a pénztáralkalmazás megfelelően tudja ellenőrizni, hogy az **Aktív** sorozattípusú cikkekhez értékesített sorozatszámok az értékesítő raktár készletében vannak-e, a szervezetek gyakran a **Termékelérhetőség nyomonkövetési dimenziókkal** feladatot futtatják a Commerce központi felületén a kapcsolódó **1130** termékelérési elosztási feladattal. Amikor az új szerializált készletet a rendszer bevételezi az értékesítési raktárakba, ahhoz, hogy a pénztár ellenőrizze az értékesített sorozatszámok készletelérhetőségét, a készlet alapadatának gyakran frissítenie kell a csatorna-adatbázist a legfrissebb készlet-elérhetőségi adatokkal. A **Termékelérhetőség nyomonkövetési dimenziókkal** feladat aktuális pillanatképet készít az alapkészletről összes vállalati raktárra vonatkozóan, beleértve a sorozatszámokat is. A **1130** elosztási feladat a készlet pillanatfelvételét készíti el, és megosztja az összes konfigurált csatorna-adatbázissal.

### <a name="active-in-sales-process-serial-configurations"></a>Aktív az értékesítési folyamat sorozatkonfigurációiban

Az **Aktív az értékesítési folyamatban** tulajdonsággal konfigurált cikkek nem esnek át egyetlen készlete-llenőrzési logikán sem, mivel ez a konfiguráció azzal jár, hogy a készlet sorozatszámai nincsenek előre regisztrálva a készletbe, és a sorozatszámokat csak az értékesítéskor rögzítik.  

Ha az **Üres kiadás megengedett** beállítás konfigurálva van az **Aktív az értékesítési folyamatban** típusú konfigurált cikkeknél is, a sorozatszám beírását ki lehet hagyni. Ha az **Üres kiadás megengedett** nincs konfigurálva, az alkalmazás előírja a felhasználó számára egy sorozatszám beírásá annak ellenére, hogy a rendszer nem ellenőrzi a rendelkezésre álló készletet.

### <a name="apply-serial-numbers-during-creation-of-pos-transactions"></a>Sorozatszámok alkalmazása pénztártranzakciók létrehozásakor

A pénztáralkalmazás azonnal kéri a sorozatszám-rögzítését a felhasználóktól szerializált cikk értékesítése esetén, de az alkalmazás lehetővé teszi a felhasználóknak, hogy az értékesítési folyamat egy bizonyos pontjáig kihagyják a sorozatszámok bevitelét. Amikor a felhasználó megkezdi a fizetés rögzítését, az alkalmazás betartatja és megköveteli a sorozatszám bejegyzését minden olyan cikkhez, amely nincs úgy beállítva, hogy a jövőbeli szállítmányokkal vagy átvételekkel teljesíthető legyen. Minden, készpénzben fizetett, kiszállításra teljesített konfigurált szerializált cikk esetében a felhasználónak rögzítenie kell a sorozatszámot (vagy elfogadja, hogy üresen hagyja, ha a cikk konfigurációja ezt lehetővé teszi) az értékesítés befejezése előtt.

A jövőbeli átvételhez vagy szállítmányhoz értékesített szerializált cikkek esetében a pénztárfelhasználók kezdetben átugorhatják a sorozatszám beírását, és így is befejezhetik a vevői rendelés létrehozását.   

> [!NOTE]
> Ha a pénztáralkalmazáson keresztül szerializált termékeket értékesít vagy teljesít, az értékesítési tranzakcióban szerializált cikkeknél az 1 mennyiséget érvényesíti a rendszer. Ez annak az eredménye, hogy a sorozatszámra vonatkozó információkat hogyan követik nyomon az értékesítési sorban. Ha a pénztáron keresztül több szerializált cikk tranzakcióját értékesíti vagy teljesíti, minden értékesítési sort csak 1 mennyiséggel kell konfigurálni. 

### <a name="apply-serial-numbers-during-customer-order-fulfillment-or-pickup"></a>Sorozatszámok alkalmazása vevői rendelés teljesítése vagy átvétele során

Amikor a pénztár **Rendelési teljesítés** műveletével teljesíti a szerializált termékekre vonatkozó vevői rendelési sorokat, a pénztár kötelezően rögzíti a sorozatszámot a végleges teljesítés előtt. Ezért ha a kezdeti rendelés rögzítése során nem adott meg sorozatszámot, rögzíteni kell a pénztár kitárolási, csomagolási vagy szállítási folyamatai során. A rendszer minden lépést ellenőriz, és a felhasználótól a rendszer csak akkor kéri a sorozatszámadatokat, ha azok hiányoznak vagy már nem érvényesek. Ha például egy felhasználó kihagyja a kitárolási vagy csomagolási lépéseket és azonnal elindít egy szállítmányt, a sorhoz pedig nem regisztráltak sorozatszámot, a pénztár előírja a sorozatszám beírását a végső számlázási lépés befejezése előtt. A sorozatszám rögzítésének a pénztárban való rögzítésekor a korábban említett szabályok továbbra is érvényesek. Csak az **Aktív** típusúként konfigurált szerializált cikkek mennek át sorozatszám-készletellenőrzésen. Az **Értékesítési folyamatban aktív** típusúként konfigurált cikkek érvényesítése nem történik meg. Ha az **Aktív** termékek esetében engedélyezve van a **Tényleges negatív készlet**, a készlet rendelkezésre állásától függetlenül a rendszer bármilyen sorozatszámot elfogad. Ha az **Aktív** és **Értékesítési folyamatban aktív** típusú cikkek esetén az **Üres kiadás megengedett** beállítás konfigurálva van, a felhasználó üresen hagyhatja a sorozatszámokat a kitárolási, csomagolási és szállítási lépések során, ha szeretné.

A sorozatszámok ellenőrzése akkor is megtörténik, amikor a felhasználó végrehajtja a vevői rendeléseken pénztárban a felvételi műveleteket. A pénztáralkalmazás nem engedélyezi a felvétel véglegesítését a szerializált termékre, hacsak meg nem felel a korábban említett ellenőrzéseken. Az ellenőrzések mindig a termék nyomonkövetési dimenzióján és az értékesítési raktár konfigurációin alapulnak. 

## <a name="additional-resources"></a>További erőforrások

[Bejövő készletműveletek a pénztárban](./pos-inbound-inventory-operation.md)

[Kimenő készletműveletek a pénztárban](./pos-outbound-inventory-operation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
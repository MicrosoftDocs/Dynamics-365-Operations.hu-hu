---
title: A tényleges súllyal rendelkező termék feldolgozása a raktárkezelésben
description: A témakör azt ismerteti, hogy a munkasablonok és helyutasítások segítségével meghatározhatja, hogy hol és hogyan lehet munkavégzést végezni a raktárban.
author: perlynne
manager: tfehr
ms.date: 08/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCatchWeightTag, WHSCatchWeightItemHandlingPolicy, TMSLoadBuildWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-1-31
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 710446db7746ed3cd3fb9754caeaa15fd2f76641
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4429879"
---
# <a name="catch-weight-product-processing-with-warehouse-management"></a>A tényleges súllyal rendelkező termék feldolgozása a raktárkezelésben

[!include [banner](../includes/banner.md)]


## <a name="feature-exposure"></a>Funkció kitettsége

Hogy a tényleges súllyal rendelkező termékek feldolgozásához használja a raktárkezelési funkciókat, a funkció bekapcsolásához a licenc konfigurációs kulcsot kell használnia. Lépjen a **Rendszerfelügyelet \> Beállítás \> Licenckonfiguráció** elemre. Ezután a **Konfigurációs kulcsok** fülön bontsa ki a **Kereskedelem \> Raktár- és szállításkezelés** elemet, és jelölje be a jelölőnégyzetet a **Tényleges súly raktár esetén** lehetőséget.

> [!NOTE]
> Mind a **Raktár-és szállításkezelés** licenc konfigurációs kulcsot, mind a **Folyamatelosztás \> tényleges súly** licenc konfigurációs kulcsokat is be kell kapcsolni. A tényleges súlyra vonatkozó konfigurációs kulcsok beállításához be kell kapcsolnia a funkciót a **Funkciókezelés** munkaterületen. A fő funkció, amelyet be kell kapcsolni a **Termék tényleges súly szerinti feldolgozása raktárkezeléssel**. Két kapcsolódó, de nem kötelező funkció, amelyet esetleg bekapcsolhat: **Tényleges súllyal rendelkező termékek készletállapotának változása** és **Meglévő ténylegessúly-címkék használata, ha a termelési rendeléseket készként jelentik**.

Miután a licenc konfigurációs kulcs be van kapcsolva, a kiadott termék létrehozásakor kiválaszthatja a **Tényleges súlyt**. A kiadott termékhez tárolási dimenziócsoportot társíthat, amelyhez a **Raktárkezelési folyamatok használata** paraméter ki van választva.

Mielőtt a terméket a Raktárkezelésben használhatja, bizonyos alapvető termékspecifikus beállításokat kell elvégeznie a tényleges súlyra:

- Adja meg a tényleges súly átváltását a ténylegessúly-egység (doboz) és a készletegység (kilogramm \[kg\]) között a mértékegység-átváltás definíciója részeként.
- Adja meg az a legkisebb és legnagyobb tömeg tűréshatárait a tényleges súly egységének beállítása részeként.
- Állítson be egy egység szekvenciacsoportot, ahol a tényleges súly egysége a legkisebb raktározási egységként (SKU) van meghatározva.
- Állítson be egy tényleges súllyal rendelkező cikkek kezelésére vonatkozó irányelvet.

További tudnivalókért lásd: [Tényleges súly alapú cikkek beállítása és karbantartása](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-catch-weight-items).

## <a name="transaction-adjustments"></a>Tranzakció kiigazításai

Mivel a készlet súlya a raktárba kerüléskor eltérhet a súlytól, amivel a raktárból kiadják, a tényleges súllyal rendelkező termék feldolgozásakor a készlet korrekciója szükséges.

> [!NOTE]
> A mobileszköz-tevékenység csak akkor indítja el a tranzakciók kiigazítását, ha a cikk tényleges súllyal rendelkező cikkekre vonatkozó kezelési irányelvének Kimenő súlyeltérési módszere **Súlyeltérés engedélyezése**.

**1. példa**

A **Jelentés készként** termelési folyamat során az azonosítótábla beviteli súlya, amely nyolc doboz tényleges súllyal rendelkező terméket tartalmaz, 80,1 kg-ként lesz rögzítve. Az azonosítótáblát ezután a késztermékek területen tárolják el, és a raktározási időszak alatt a súly egy része elvész.

Később, egy értékesítési rendelés kitárolási folyamata részeként az azonos azonosítótábla súlya 79,8 kg-ként rögzített. Ezért a rendszerben most már rendelkezik fizikai dimenziókészlet részeként súlyeltéréssel.

Ebben az esetben a rendszer automatikusan kiigazítja a különbséget a hiányzó 0,3 kg-ra egy tranzakció feladásával.

**2. példa**

A meghatározás alapján egy termék be van állítva, hogy a **Doboz** ténylegessúly-egység esetén a minimális súly 8 kg-t és a maximális súlyt 12 kg-t toleráljon.

Tegyük fel, hogy a termékből két dobozunk van, és a regisztrált súlyuk 16 kg. Ha egy raktári dolgozó kitárolja és leméri az egyik dobozt, és a rögzített súly 9 kg lesz, a másik doboz súlya 7 kg lesz. Azonban mivel a 7 kg a minimális tömeg alatt van, a rendszer automatikusan kiigazítást tesz és az aktuális készlet súlyát 1 kg-val növeli.

A számlák beállításához, amelyekhez ezeket a kiigazításokat feladják, lépjen a **Költségkezelés \> Főkönyv-integrálási irányelvek beállítása \> Feladás** menüpontra. Ezután a **Készlet** fülön adja meg a következő számlákat:

- Tényleges súlyhoz kapcsolódó veszteségszámla
- Tényleges súlyhoz kapcsolódó nyereségszámla

## <a name="catch-weight-item-handling-policy"></a>Tényleges súllyal rendelkező cikkek kezelésére vonatkozó irányelv

A tényleges súllyal rendelkező cikkek kezelési házirendje a cikkek két raktárkezelési folyamatot határoz meg: mikor és hogyan kell a cikkek yúlát rögzíteni.

Be lehet állítani, hogy a súly rögzítése mikor történjen az értékesítési és átmozgatási rendelések feldolgozása során. A tömeg a következő folyamatok egyike során rögzíthető:

- **Kitárolás** – A súlyt a rendelési munka első kitárolási munkasora során rögzítik.
- **Csomagolás-** – A súly rögzítése a kézi csomagolás során történik. (El kell küldenie a cikkeket a csomagolási állomásra.)

Ha a tényleges súlyt a csomagolási állomáson a tároló csomagolási folyamatok során rögzítik, a raktári dolgozókat nem kéri a rendszer a tömeg rögzítésére a kitárolási munka során. Ehelyett a tényleges készlet átlagos súlya lesz a kitárolt készlet súlya, ami a csomagolási területre megy. Ez a fogalom a címkékkel nyomon követett tényleges súllyal rendelkező cikkekre is vonatkozik. A címkékkel nyomott követett cikkeknél ezek a paraméterek határozzák meg, hogy mikor történik a címke rögzítése. A címke rögzíthető a kitárolás időpontjában mobileszköz használatával vagy a manuális csomagolás során.

> [!NOTE]
> Mivel a **Csomagolás** beállítás azt eredményezi, hogy a készletet az átlagos kitárolt súllyal kell frissíteni, ez olyan eltérést idézhet elő, amely a ténylegessúly-nyereségi/-veszteségi kiigazítást és/vagy a tényleges készletsúly és a ténylegessúly-címke által megadott súly közti különbséget eredményezhet.

A belső raktárkezelési folyamatok esetén, pl. a leltár és a kiigazítási javítások, meg lehet határozni, hogy a súlyt kell-e rögzíteni, vagy sem. Ha nem rögzítik, a névleges tömeg lesz használva. A többi beállítással a súlyt ténylegessúly-egység és leltározási mennyiség alapján lehet rögzíteni.

Megadhatja, hogyan rögzítésék a súlyt. A két fő folyamat egyikében a ténylegessúly-címkéket követik nyomon, és a súly rögzítéséhez használják. A másik folyamatban a tényleges súly címkékez nem követik nyomon.

- **Igen** – A cikk használ ténylegessúly-címkéket. Minden címkeszám egy tényleges súly egységet (doboz) jelöl, és a súly és egyéb információkat amelyek a címkéhez kapcsolódnak. A kimenő folyamatoknál a súly használatos, amelyet a címkéhez társítottak.
- **Nem** – A cikk tényleges súllyal rendelkező címkéket nem használ. A beviteli és kiviteli súlymérő folyamatok az egyes folyamatok során rögzített tényleges súlyon alapulnak.

A ténylegessúly-címkék nyilvántartási folyamata a cikkeknél használható, ahol a súly nem módosul a raktározási időszak alatt. Csak a bejövő raktárfolyamat során rögzíti a rendszer a súlyt. A kimenő folyamat során a ténylegessúly-címkéket csak beolvassák, és a kimenő tranzakciós feldolgozása során a címkéhez társított súlyadatokat használják.

A ténylegessúly-címkék feldolgozásával kapcsolatos másik fontos paraméter a **Ténylegessúly-címke dimenziójának követési módja**. A címkéket lehet részlegesen vagy teljeskörűen nyomon követni. Ha egy címke részben nyomon követhető, akkor nyomon követi a termékdimenziókat, a nyomon követési dimenziókat és a készlet állapotát. Ha egy címke teljeskörűen nyomon követhető, akkor nyomon követi a termékdimenziókat, a nyomon követési dimenziókat és az **összes** tárolási dimenziót.

Ezen kívül, ha a cikket címke alapján nyomon követik, akkor létezik egy **Kimenő címkerögzítési módszer** paraméter. Ez a paraméter beállítható úgy, hogy a mobileszközön a rendszer mindig kérje a kimenő tranzakciókat tartalmazó címkét. A paraméter úgy is beállítható, hogy csak a rendszer csak szükség esetén kérje a címkéket. Például a készletben öt ténylegessúly-címke található egy adott azonosítótáblán, és Ön jelezte, hogy mind az öt címkét szeretné kitárolni az azonosítótábláról. Ebben az esetben ha a **Kimenő címkerögzítési módszer** paraméter beállítása **Címke kérése csak szükség esetén**, a rendszer automatikusan kitárolja az öt címkét. Nem kell minden címkét beolvasni. Ha a paraméter beállítása **Mindig kérje a címkét**, akkor minden egyes címkét be kell olvasni, akkor is, ha az összes címkét kitárolja.

> [!NOTE]
> Szabály szerint a címkéket a rendszer csak a mobileszköz menüelemeiből rögzíti és frissíti. Ennek ellenére van néhány olyan eset, amikor a címkéket máshol rögzítik (például a kézi csomagoló állomástól). Általában viszont a mobileszköz menüelemeit kell használni az összes raktári tevékenységhez, ha címkéket használnak.

### <a name="how-to-capture-catch-weight"></a>Hogyan kell a tényleges súlyt rögzíteni?

**Ténylegessúly-címke követése használata esetén** a címkét mindig létre kell hozni minden ténylegessúly-egységhez ami beérkezik, és minden címkét mindig súllyal kell társítani.

Például **Doboz** a tényleges súly egysége, és kap egy raklapot nyolc dobozzal. Ebben az esetben nyolc egyedi tényleges súly címkét létre kell hozni, és a súlyt minden címkéhez társítva kell lennie. A bejövő tényleges súly címkétől függően vagy összes nyolc doboz tömege rögzíthető, és az átlagos tömeg minden dobozra leosztható, vagy egyedi tömegek rögzíthetők az egyes dobozokra.
A **Meglévő ténylegessúly-címkék használata, ha a termelési rendeléseket készként jelentik** funkció használatakor a mobileszköz menüelemen keresztül engedélyezett folyamattal, a készletet a rendszer a meglévő ténylegessúly-címke adatai alapján frissíti. Ennek eredményeképpen a raktáralkalmazás nem kéri a ténylegessúly-címke adatainak rögzítését a termelési készként jelentés művelet részeként.

**Ha a tényleges súly címke nyomon követését nem alkalmazzák**, a súly rögzíthető az egyes dimenziókészletekre (például az egyes azonosítótáblákra és nyomon követési dimenzióra). Másik lehetőségként a súly rögzíthető az összesített szint alapján, például mint öt azonosítótábla (raklap).

A kimenő súly rögzítésének módszereinél a **Ténylegessúly-egységenként** beállítással beállíthatja, hogy a súlyt minden egyes ténylegessúly-egységnél végezzék (például dobozonként). A **Kitárolási egységenként** beállítással megadhatja, hogy a rendszer a súlyt a kitárolandó mennyiség alapján rögzítse (például három doboz). Vegye figyelembe, hogy a termelési sor kitárolási és belső átmozgatási folyamatához az átlagos súlyt használják, ha a **Nem rögzített** beállítás van használatban.

Több súlyrögzítési módszer van megadva a tényleges súllyal rendelkező cikkek kezelési irányelvében. Minden egyes súlyrögzítési módszert különböző tranzakciók használnak. A következő táblázat összefoglalja, hogy mely paraméterek használatosak mely tranzakcióknál.

| Módszer                                     | Tranzakció                                |
|--------------------------------------------|--------------------------------------------|
| Kimenő súly rögzítési módszere           | Értékesítés kitárolása, Átmozgatás kitárolása            |
| Termelési kitárolási súly rögzítési módszere | Termelés kitárolása, Termelési felhasználás |
| Mozgási súly rögzítési módszere           | Szállítás                                   |
| Súly helyesbítésének rögzítési időpontja       | Kiigazítások, Leltár                      |
| Számítási súly rögzítési módszere           | Számlálás                                   |
| Raktári átmozgatáshoz tartozó súlyrögzítési metódus | Raktári átmozgatás                         |

Ha szeretné a raktárkezelés kitárolási folyamatait megakadályozni, hogy olyan súlyokat rögzítsen, amelyek ténylegessúly-profit/-veszteség kiigazításokat eredményeznek, használhatja a Kimenő súly eltérési metódust. A Kimeneti súlyeltérési módszer a következő mobileszköz-folyamatokra vonatkozik: értékesítési kitárolás, átmozgatási kitárolás, termelési kitárolás, áthelyezések, leltár és raktárak közti átmozgatás. A **Súlyeltérés korlátozása** beállítást akkor használhatja, ha a tényleges súllyal rendelkező cikk súlya nem változik a raktári tárolás során, és ha nincs szükség ténylegessúly-nyereségi/-veszteségi kiigazításokra. A **Súlyeltérés engedélyezése** beállítást akkor használhatja, ha a súly változhat, és ha szükség van a súlyváltozás rögzítésekor ténylegessúly-nyereségi/-veszteségi kiigazításokra.

## <a name="unsupported-scenarios"></a>Nem támogatott esetek

Nem minden munkafolyamat támogatja a tényleges súllyal renelkező termékek feldolgozását a raktárkezeléssel. Jelenleg az alábbi korlátozások érvényesek. Ezek a tényleges súly szerinti cikkekre érvényesek, függetlenül attól, hogy azokat címkézték-e.

### <a name="configuring-catch-weight-products-for-warehouse-management-processes"></a>A tényleges súllyal rendelkező termékek konfigurálása a raktárkezelési folyamatokhoz

- Csak a receptúra feldolgozása támogatott a tényleges súllyal rendelkező termékek (nem anyagjegyzék) esetén.
- Tényleges súllyal rendelkező termékek nem társíthatók nyomon követési dimenziócsoporthoz tulajdonos dimenzió használatával.
- A tényleges súllyal rendelkező termékek nem használhatók a szolgáltatásként.
- Tényleges súllyal rendelkező termékek „raktározott termékként” csak egy cikkmodellcsoport részeként használható.
- Tényleges súllyal rendelkező termékek nem használhatók együtt az "Értékesítési folyamatban aktív" nyomonkövetési funkcióval.
- Tényleges súllyal rendelkező termékek nem használhatók együtt az sorozatszámok rögzítésée vonatkozó funkcióval. Ezért termékek nem helyezhetők át az "üres" helyről egy sorozatszámra a kitárolási és csomagolási folyamat részeként.
- Tényleges súllyal rendelkező termékek nem használhatók együtt a sorozatok felhasználás előtti rögzítésére vonatkozó funkcióval.
- A tényleges súllyal rendelkező termékek, amelyeknél a változatok engedélyezettek, nem használhatók együtt a mértékegység-változatok átalakítására vonatkozó funkcióval.
- Tényleges súllyal rendelkező termékek nem jelölhetők meg kereskedelmi „termékcsomagként”.
- Tényleges súllyal rendelkező termékek csak olyan egységszekvencia-csoporttal használhatók, amelynek az tényleges súly anyagkezelési egységei vannak és amelynek a tényleges súly egysége, a legkisebb sorozat.
- A tényleges súllyal rendelkező termékek esetén a készletegységek csak akkor konvertálhatók tényleges súly egységre, ha az átalakítás által létrehozott névleges mennyiség több mint 1.
- A tényleges súllyal rendelkező termékek vonalkódjainak beállítása nem támogatja a változó súly beállítását.

### <a name="order-processing"></a>Rendelés feldolgozása

- Előzetes kiszállítási értesítés (ASN/csomagolási szerkezetek) létrehozása nem támogatja a súlyadatokat.
- A rendelési mennyiséget a tényleges súly egysége alapján kell karbantartani.

### <a name="inbound-warehouse-processing"></a>Bejövő raktárkezelés

- Az azonosítótáblák bevételezéséhez szüksége, hogy a súlyokat a regisztráció során rendeljék hozzá, mert a tömegadatokat a rendszer nem támogatja az előzetes kiszállítási értesítés részeként. Ha a tényleges súly címke folyamatokat használnak, a címke számát manuálisan kell hozzárendelni egy tényleges súly egységenként megadva.
- A bejövő minőségi ellenőrzési munka nem támogatott a tényleges súllyal rendelkező termékeknél. Ha konfigurálva van, akkor a rendszer kihagyja a minőség-ellenőrzési munkát.

### <a name="inventory-and-warehouse-operations"></a>Készlet- és raktárműveletek

- Karanténutasítások manuális létrehozása a tényleges súllyal rendelkező termékek esetében nem támogatott.
- A készlet manuális mozgatása, amely nyitott munkához kapcsolódik, nem támogatot a tényleges súllyal rendelkező termékek esetén.
- Azonosítótábla rakodása, amely inicializálja a raktári készletet, tényleges súllyal rendelkező termékek esetében nem támogatott.
- Tételalapú kiigazítási folyamatok a tényleges súllyal rendelkező termékek esetében nem támogatottak.
- Negatív tényleges készlet kezelése tényleges súllyal rendelkező termékek esetében nem támogatott.
- Készletjelölés tényleges súllyal rendelkező termékek nem használható.

### <a name="outbound-warehouse-processing"></a>Kimenő raktárkezelés

- Tényleges súllyal rendelkező termékek esetén a fürtkitárolás funkció nem támogatott.
- Kitárolás és csomagolás raktári feldolgozása tényleges súllyal rendelkező termékek esetében nem támogatott.
- A tényleges súllyal rendelkező termékekre, a munkák, melyek a munkasablonokban vannak megadva, nem futtathatók automatikusan.
- Tényleges súllyal rendelkező termékek esetén a rendszer nem támogatja a kézi csomagolási állomás feldolgozását, ha csomagolt tároló kitárolására vonatkozó munka a tárolók bezárása után kerül létrehozásra.
- Tényleges súllyal rendelkező termékek esetén a darabonkénti beolvasás funkció nem támogatott.

### <a name="production-processing"></a>Termelés feldolgozása

- Tényleges súllyal rendelkező termékek esetén csak receptúra termékekre vonatkozó kötegrendelések használhatók.
- Tényleges súllyal rendelkező termékek esetén a kanban funkció nem támogatott.
- Tényleges súllyal rendelkező termékek esetén a sorozatszámok nem regisztrálhatók a felhasználás előtt.
- Tényleges súllyal rendelkező termékek esetén az azonosítótáblák termelésből sztornírozása funkció nem támogatott.
- Tényleges súllyal rendelkező termékek esetén a készként való jelentés nem regisztrálható sorozatszám szerint.

### <a name="transportation-management-processing"></a>Szállításkezelési folyamatok feldolgozása

- KRakomány-összeállítási munkaterület feldolgozása tényleges súllyal rendelkező termékek esetében nem támogatott.
- Szállításigénylési sorok tényleges súllyal rendelkező termékek esetében nem támogatottak.

### <a name="other-restrictions-and-behaviors-for-catch-weight-product-processing-with-warehouse-management"></a>Egyéb korlátozások és a viselkedések a tényleges súllyal megadott termékek feldolgozásához raktárkezelés használatával

- Kitárolási folyamatok során, amelyen a felhasználót a rendszer nem kéri nyomon követési dimenziók meghatározására, a súly hozzárendelését az átlagos tömeg alapján végzik. Ez a viselkedés akkor fordul elő, amikor például nyomon követési dimenziók egy kombinációját használják ugyanazon a helyen, és miután a felhasználó feldolgozza a kitárolást, csak egy nyomon követési dimenzióérték marad az adott helyen.
- Ha a készlet le van foglalva a tényleges súllyal rendelkező termék számára, amelyet a raktárkezelési folyamatokhoz konfiguráltak, a foglalás a meghatározott minimális súly alapján történik, akkor is, ha ez a mennyiség az aktuális utolsó kezelési mennyiség. Ez a viselkedés eltér az olyan cikkek viselkedésétől, amelyeket a raktárkezelési folyamatokhoz nem konfiguráltak. Erre a korlátozásra egyetlen kivétel vonatkozik. Termelési kitárolás esetén, amikor a tényleges súllyal rendelkező termék utolsó, sorozatszámmal szabályozott mennyiségét is kitárolják, a rendszer a tényleges súlyt használja.
- Azok a folyamatok, amelyek a súlyt kapacitásszámítás részeként használják (hullám küszöbértékei, munka maximális szünetek, tároló maximumok, hely terhelési kapacitásai stb.) nem használják a készlet tényleges súlyát. Ehelyett a folyamatok a termékhez meghatározott fizikai kezelési súlyon alapulnak.
- Általánosságban a tényleges súllyal rendelkező termékek esetén a kereskedelmi funkció nem támogatott.
- A tényleges súly szerinti termékek esetében a készlet állapota nem frissíthető a **Raktári állapot változása** alapján.

### <a name="catch-weight-tags"></a>Ténylegessúly-címkék

A ténylegessúly-címkét létrehozhatja raktáralkalmazási folyamattal, manuálisan a képernyőn vagy adatentitás-folyamat segítségével. Ha egy ténylegessúly-címkét társítanak egy bejövő forrásbizonylatsorral, például beszerzési rendelési sorral, a címke nyilvántartásba kerül. Ha a sor a kimenő feldolgozáshoz használatos, akkor a rendszer a címkét szállítottként frissíti.

A tényleges súllyal rendelkező termékekre jelenleg érvényes korlátozások mellegg a címkézett tényleges súllyal rendelkező termékekre aktuálisan más korlátozások is érvényesek.

- A készlet minden manuális frissítése (azaz a nem mobileszközön végzett frissítéseknek) tartalmazniuk kell a megfelelő manuális frissítéseket a társított ténylegessúly-címkéken is, mivel ezek a frissítések nem történnek meg automatikusan. Például a manuális kiigazítási naplók frissítik a készletet, de a társított tényleges súly címkéket nem.
- Manuálisan kell frissíteni a ténylegessúly-címkéket, hogy tükrözzék a feltöltési munka mozgatásait. Ennek az az oka, hogy a rendszer nem tudja rögzíteni a súlyokat a feltöltési munka feldolgozásakor, így helyette az átlagos súlyt rögzíti.
- Vegyes azonosítótábla bevételezése címkézett tényleges súllyal rendelkező cikkek esetében jelenleg nem támogatott.
- Az értékesítési visszárurendelés bevételezésének feldolgozásával rögzítheti a tényleges súly-címkéket. A folyamat azonban nem ellenőrzi, hogy a visszaküldött címke ugyanaz-e, mint a eredetileg egy értékesítési rendeléshez tartozó címke.
- A mobileszköz-menü, amelyben az **Anyagfelhasználás regisztrálása** tevékenységkód szerepel, jelenleg nem támogatja a ténylegessúly-címkék rögzítését.
- Bár a leltározási folyamatok a címkézett tényleges súlyú cikkek esetében is támogatottak, csak korlátozottak. Használhatja például a mobileszköz-beállításokat a címkézett tényleges súlyú cikkek leltározásához, és az átlagos súlyt használja a program. A tényleges súly-címkék azonban nem frissülnek automatikusan a leltározási tranzakcióval. A leltározási tranzakció befejezése után a tényleges súly címkéit manuálisan kell módosítani, hogy azok tükrözzék a készletet. Ha azok a cikkeket is az adott helyhez leltározzák, amelyek eredetileg nem voltak a helyen, a rendszer a névleges súlyt használja.
- Az azonosítótábla-konszolidáció jelenleg nem támogatja a címkézett tényleges súlyú cikkeket.
- A munka sztornózása funkció nem támogatott a ténylegessúly-cikkek esetén, amelyek címkeszámát nyomon követik.

> [!NOTE]
> Az előző információk a ténylegessúly-címkékről csak akkor érvényesek, ha a tényleges súllyal rendelkező termék olyan ténylegessúly-címke dimenziókövetési metódussal rendelkezik, amely teljes körűen nyomon követett (azaz ha a **Ténylegessúly-címke dimenziójának követési módja** paraméter a ténylegesssúly-cikk kezelési irányelvében a következő beállítású: **Termékdimenziók, a nyomon követési dimenziók és az összes tárolási dimenzió**). Ha a ténylegessúly-cikk csak részlegesen címke által nyomon követett (azaz ha a **Ténylegessúly-címke dimenziójának követési módja** paraméter a ténlyegessúly-cikk kezelési irányelvében **Termékdimenziók, nyomon követési dimenziók és készletállapot** beállítású), akkor további korlátozások érvényesek. Mivel a láthatóság elveszik ebben az esetben a címke és a készlet között, bizonyos további esetek nem támogatottak.

---
title: A tényleges súllyal rendelkező termék feldolgozása a raktárkezelésben
description: A témakör azt ismerteti, hogy a munkasablonok és helyutasítások segítségével meghatározhatja, hogy hol és hogyan lehet munkavégzést végezni a raktárban.
author: perlynne
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCatchWeightTag, WHSCatchWeightItemHandlingPolicy
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-1-31
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: ced22a144e57b624ceacb8bb5c3032218db3a0eb
ms.sourcegitcommit: bacec397ee48ac583596be156c87ead474ee07df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "777272"
---
# <a name="catch-weight-product-processing-with-warehouse-management"></a>A tényleges súllyal rendelkező termék feldolgozása a raktárkezelésben

[!include [banner](../includes/banner.md)]

## <a name="feature-exposure"></a>Funkció kitettsége

Hogy a tényleges súllyal rendelkező termékek feldolgozásához használja a raktárkezelési funkciókat, a funkció bekapcsolásához a licenc konfigurációs kulcsot kell használnia. (Lépjen a **Rendszerfelügyelet \> Beállítás \> Licenckonfiguráció** elemre. Ezután a **Konfigurációs kulcsok** fülön bontsa ki a **Kereskedelem \> Raktár- és szállításkezelés** elemet, és jelölje be a jelölőnégyzetet a **Tényleges súly raktár esetén** lehetőséget).

> [!NOTE]
> Mind a **Raktár-és szállításkezelés** licenc konfigurációs kulcsot, mind a **Folyamatelosztás \> tényleges súly** licenc konfigurációs kulcsokat is be kell kapcsolni.

Miután a licenc konfigurációs kulcs be van kapcsolva, a kiadott termék létrehozásakor kiválaszthatja a **Tényleges súlyt**. A kiadott termékhez tárolási dimenziócsoportot társíthat, amelyhez a **Raktárkezelési folyamatok használata** paraméter ki van választva.

Mielőtt a terméket a Raktárkezelésben használhatja, bizonyos alapvető termékspecifikus beállításokat kell elvégeznie a tényleges súlyra:

- Adja meg a tényleges súly átváltását a ténylegessúly-egység (doboz) és a készletegység (kilogramm \[kg\]) között a mértékegység-átváltás definíciója részeként.
- Adja meg az a legkisebb és legnagyobb tömeg tűréshatárait a tényleges súly egységének beállítása részeként.
- Állítson be egy egység szekvenciacsoportot, ahol a tényleges súly egysége a legkisebb raktározási egységként (SKU) van meghatározva.
- Állítson be egy tényleges súllyal rendelkező cikkek kezelésére vonatkozó irányelvet.

További tudnivalókért lásd: [Tényleges súly alapú cikkek beállítása és karbantartása](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-catch-weight-items).

## <a name="transaction-adjustments"></a>Tranzakció kiigazításai

Mivel a készlet súlya a raktárba kerüléskor eltérhet a súlytól, amivel a raktárból kiadják, a tényleges súllyal rendelkező termék feldolgozásakor a készlet korrekciója szükséges.

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

Ha a tényleges súlyt a csomagolási állomáson a tároló csomagolási folyamatok során rögzítik, a raktári dolgozókat nem kéri a rendszer a tömeg rögzítésére a kitárolási munka során. Ehelyett a tényleges készlet átlagos súlya lesz a kitárolt készlet súlya, ami a csomagolási területre megy.

A belső raktárkezelési folyamatok esetén, mint a leltár és a kiigazítási javítások, meg lehet határozni, hogy a súlyt kell-e rögzíteni, vagy sem. Ha nem rögzített, a névleges tömeg lesz használva.

Megadhatja, hogyan rögzítésék a súlyt. A két fő folyamat egyikében a ténylegessúly-címkéket követik nyomon, és a súly rögzítéséhez használják. A másik folyamatban a tényleges súly címkékez nem követik nyomon.

- **Igen** – A cikk használ ténylegessúly-címkéket. Minden címkeszám egy tényleges súly egységet (doboz) jelöl, és a súly és egyéb információkat amelyek a címkéhez kapcsolódnak. A kimenő folyamatoknál a súly használatos, amelyet a címkéhez társítottak.
- **Nem** – A cikk tényleges súllyal rendelkező címkéket nem használ. A beviteli és kiviteli súlymérő folyamatok az egyes folyamatok során rögzített tényleges súlyon alapulnak.

A ténylegessúly-címkék nyilvántartási folyamata a cikkeknél használható, ahol a súly nem módosul a raktározási időszak alatt. Csak a bejövő raktárfolyamat során rögzíti a rendszer a súlyt. A kimenő folyamat során a ténylegessúly-címkéket csak beolvassák, és a kimenő tranzakciós feldolgozása során a címkéhez társított súlyadatokat használják.

### <a name="how-to-capture-catch-weight"></a>Hogyan kell a tényleges súlyt rögzíteni?

Tényleges súly címke követése használata esetén a címkét mindig létre kell hozni minden ténylegessúly-egységhez ami beérkezik, és minden címkét mindig tömeggel társítva kell lennie.

Például **Doboz** a tényleges súly egysége, és kap egy raklapot nyolc dobozzal. Ebben az esetben nyolc egyedi tényleges súly címkét létre kell hozni, és a súlyt minden címkéhez társítva kell lennie. A bejövő tényleges súly címkétől függően vagy összes nyolc doboz tömege rögzíthető, és az átlagos tömeg minden dobozra leosztható, vagy egyedi tömegek rögzíthetők az egyes dobozokra.

Ha a tényleges súly címke nyomon követését nem alkalmazzák, a súly rögzíthető az egyes dimenziókészletekre (például az egyes azonosítótáblákra és nyomon követési dimenzióra). Másik lehetőségként a súly rögzíthető az összesített szint alapján, például mint öt azonosítótábla (raklap).

Kimenő tömeg rögzítés módszerei esetén megadhatja, hogy a mérés minden tényleges súly egységre megtörtént (például dobozonként), vagy a súly rögzítése a kitárolandó mennyiség alapján rögzített (például három doboz). Vegye figyelembe, hogy a termelési sor kitárolási folyamatához az átlagos súlyt használják, ha a **Nem rögzített** beállítás van használatban.

## <a name="supported-scenarios"></a>Támogatott esetek

Nem minden munkafolyamat támogatja a tényleges súllyal renelkező termékek feldolgozását a raktárkezeléssel. Jelenleg az alábbi korlátozások érvényesek.
 
### <a name="configuring-catch-weight-products-for-warehouse-management-processes"></a>A tényleges súllyal rendelkező termékek konfigurálása a raktárkezelési folyamatokhoz

- A tényleges súllyal rendelkező termékek esetén a cikkek tárolásidimenzió-csoportjai nem módosíthatók (hogy azokhoz raktárkezelési folyamatokat is lehessen használni).
- Csak a receptúra feldolgozása támogatott a tényleges súllyal rendelkező termékek (nem anyagjegyzék) esetén.
- Tényleges súllyal rendelkező termékek nem társíthatók nyomon követési dimenziócsoporthoz tulajdonos dimenzió használatával.
- A tényleges súllyal rendelkező termékek nem használhatók a szolgáltatásként.
- Tényleges súllyal rendelkező termékek „raktározott termékként” csak egy cikkmodellcsoport részeként használható.
- Tényleges súllyal rendelkező termékek nem használhatók együtt az "Értékesítési folyamatban aktív" nyomonkövetési funkcióval.
- Tényleges súllyal rendelkező termékek nem használhatók együtt az sorozatszámok rögzítésée vonatkozó funkcióval. Ezért termékek nem helyezhetők át az "üres" helyről egy sorozatszámra a kitárolási és csomagolási folyamat részeként.
- Tényleges súllyal rendelkező termékek nem használhatók együtt a sorozatok felhasználás előtti rögzítésére vonatkozó funkcióval.
- A tényleges súllyal rendelkező termékek, amelyeknél a változatok engedélyezettek, nem használhatók együtt a mértékegység-változatok átalakítására vonatkozó funkcióval.
- Tényleges súllyal rendelkező termékek nem jelölhetők meg „termékcsomagként”.
- Tényleges súllyal rendelkező termékek csak olyan egységszekvencia-csoporttal használhatók, amelynek az tényleges súly anyagkezelési egységei vannak és amelynek a tényleges súly egysége, a legkisebb sorozat.
- A tényleges súllyal rendelkező termékek esetén a készletegységek csak akkor konvertálhatók tényleges súly egységre, ha az átalakítás által létrehozott névleges mennyiség több mint 1.
- A tényleges súllyal rendelkező termékek vonalkódjainak beállítása nem támogatja a változó súly beállítását.
 
### <a name="order-processing"></a>Rendelés feldolgozása

- Vállalatközi rendelések feldolgozása nem támogatott.
- Előzetes kiszállítási értesítés (ASN/csomagolási szerkezetek) létrehozása nem támogatja a súlyadatokat.
- A rendelési mennyiséget a tényleges súly egysége alapján kell karbantartani.
 
### <a name="inbound-warehouse-processing"></a>Bejövő raktárkezelés

- Az azonosítótáblák bevételezéséhez szüksége, hogy a súlyokat a regisztráció során rendeljék hozzá, mert a tömegadatokat a rendszer nem támogatja az előzetes kiszállítási értesítés részeként. Ha a tényleges súly címke folyamatokat használnak, a címke számát manuálisan kell hozzárendelni egy tényleges súly egységenként megadva.
- Vegyes azonosítótáblák bevételezése tényleges súllyal rendelkező termékek esetében nem támogatott.
 
### <a name="inventory-and-warehouse-operations"></a>Készlet- és raktárműveletek

- Karanténutasítások manuális létrehozása a tényleges súllyal rendelkező termékek esetében nem támogatott.
- A készlet manuális mozgatása, amely munkához kapcsolódik, nem támogatot a tényleges súllyal rendelkező termékek esetén.
- Az azonosítótáblák konszolidációja tényleges súllyal rendelkező termékek esetében nem támogatott.
- A raktári készletállapot módosításai ismétlődő feladat részeként a tényleges súllyal rendelkező termékek esetében nem támogatottak.
- A készletállapot módosításai, amelyet lekérdezés határoz meg, a tényleges súllyal rendelkező termékek nem támogatottak. (A minőségi rendelés készletállapot módosításai sem támogatottak.)
- A tényleges súllyal rendelkező termékek esetén a készlet állapota nem módosítható az **Aktuális készlet hely szerint** oldalról.
- Tényleges súllyal rendelkező termékek esetén a készlet állapota nem módosítható a raktáralkalmazás áthelyezési munka részeként.
- Azonosítótábla rakodása, amely inicializálja a raktári készletet, tényleges súllyal rendelkező termékek esetében nem támogatott.
- Tételalapú kiigazítási folyamatok a tényleges súllyal rendelkező termékek esetében nem támogatottak.
- Negatív tényleges készlet kezelése tényleges súllyal rendelkező termékek esetében nem támogatott.
- Készletjelölés tényleges súllyal rendelkező termékek nem használható.
 
### <a name="outbound-warehouse-processing"></a>Kimenő raktárkezelés

- Tényleges súllyal rendelkező termékek esetén a fürtkitárolás funkció nem támogatott.
- Kitárolás és csomagolás raktári feldolgozása tényleges súllyal rendelkező termékek esetében nem támogatott.
- Tényleges súllyal rendelkező termékek esetén a munka nem fejezhető be a **Munka** oldalról.
- A tényleges súllyal rendelkező termékek esetén a munkasablonon megadott munka automatikusan futtatható.
- Tényleges súllyal rendelkező termékek esetén a munka sztornírozása funkció nem támogatott.
- Tényleges súllyal rendelkező termékekesetén a kézi csomagolási állomás feldolgozása nem támogatott, ha munka a tárolók bezárása után kerül létrehozásra.
- Tényleges súllyal rendelkező termékek esetén a darabonkénti beolvasás funkció nem támogatott.
 
### <a name="production-processing"></a>Termelés feldolgozása

- Tényleges súllyal rendelkező termékek esetén csak receptúra termékekre vonatkozó kötegrendelések használhatók.
- Tényleges súllyal rendelkező termékek esetén a kanban funkció nem támogatott.
- Tényleges súllyal rendelkező termékek esetén a sorozatszámok nem regisztrálhatók a felhasználás előtt.
- Tényleges súllyal rendelkező termékek esetén az azonosítótáblák sztornírozása funkció nem támogatott.
- Tényleges súllyal rendelkező termékek esetén a készként való jelentés regisztrálható sorozatszám szerint.

### <a name="transportation-management-processing"></a>Szállításkezelési folyamatok feldolgozása

- KRakomány-összeállítási munkaterület feldolgozása tényleges súllyal rendelkező termékek esetében nem támogatott.
- Szállításigénylési sorok tényleges súllyal rendelkező termékek esetében nem támogatottak.
 
### <a name="other-restrictions-and-behaviors-for-catch-weight-product-processing-with-warehouse-management"></a>Egyéb korlátozások és a viselkedések a tényleges súllyal megadott termékek feldolgozásához raktárkezelés használatával

- Ha a tényleges súly címkéket a raktári alkalmazás feldolgozása részeként vannak rögzítve, a felhasználó nem vonhatja vissza a munkaefolyamatot.
- Kitárolási folyamatok során, amelyen a felhasználót a rendszer nem kéri nyomon követési dimenziók meghatározására, a súly hozzárendelését az átlagos tömeg alapján végzik. Ez a viselkedés akkor fordul elő, amikor például nyomon követési dimenziók egy kombinációját használják ugyanazon a helyen, és miután a felhasználó feldolgozza a kitárolást, csak egy nyomon követési dimenzióérték marad az adott helyen.
- Ha a készlet le van foglalva a tényleges súllyal rendelkező termék számára, amelyet a raktárkezelési folyamatokhoz konfiguráltak, a foglalás a meghatározott minimális súly alapján történik, akkor is, ha ez a mennyiség az aktuális utolsó kezelési mennyiség. Ez a viselkedés eltér az olyan cikkek viselkedésétől, amelyeket a raktárkezelési folyamatokhoz nem konfiguráltak.
- Azok a folyamatok, amelyek a súlyt kapacitásszámítás részeként használják (hullám küszöbértékei, munka maximális szünetek, tároló maximumok, hely terhelési kapacitásai stb.) nem használják a készlet tényleges súlyát. Ehelyett a folyamatok a termékhez meghatározott fizikai kezelési súlyon alapulnak.
- Általánosságban a tényleges súllyal rendelkező termékek esetén a kiskereskedelmi funkció nem támogatott.
 
### <a name="catch-weight-tags"></a>Ténylegessúly-címkék

Jelenleg a tényleges súly címkék funkciója csak a következő helyzetekben támogatott:

- Beszerzési rendelés raktári alkalmazás bevételezésének feldolgozásakor.
- Rakománybevételezés raktári alkalmazás általi feldolgozásakor.
- Azonosítótábla bevételezése esetén, amely a beszerzési rendelés rakományához kapcsolódik, a súly hozzárendelést a rendszer az érkeztetési folyamat során kéri. Ezzel szemben az átmozgatási rendelések bevételezése esetén, az átmozgatási rendeléshez a szállítási adatokból származó súly használatos.
- Olyan átmozgatási rendelési cikk és sor bevételezése esetén, amely nem raktárkezelési folyamatot folytató raktárból érkezik.
- Értékesítési visszárurendelés bevételezésének feldolgozása rögzítheti a tényleges súly címkéket, de feldolgozás nem érvényesíthető, ha a címkék ugyanazok a címkék, amelyeket egy adott értékesítési rendelési sorra eredetileg leszállították.
- A készletállapot feldolgozásának változásakor a raktáralkalmazás segítségével.
- Amikor a raktári átmozgatás a raktáralkalmazás segítségével történik.
- Kiigazítás befelé és kifelé való feldolgozásakor a raktáralkalmazáson keresztül.
- Kitárolási munka feldolgozásakor értékesítési és átmozgatási rendelések esetén. (Felhívjuk figyelmét, hogy a tényleges súly címkék nem rögzíthetők termélési összetevő kitárolása esetén.)
- Ha a kitárolt mennyiségeket csökkentik a rakománysorokból, függetlenül attól, hogy milyen tárolók használatosak.
- Amikor a termékeket tárolókba csomagolják a csomagolási állomáson.
- Amikor tárolók újranyitása történik.
- Amikor receptúratermékeket készként jelentik a raktáralkalmazás segítségével.
- Amikor szállítási rakományokat dolgoznak fel a raktáralkalmazás segítségével.

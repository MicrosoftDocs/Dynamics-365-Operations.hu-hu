---
title: Elektronikus üzenetküldés
description: Ez a témakör a áttekintést és beállítással kapcsolatos információt nyújt az elektromos üzenetküldéssel kapcsolatban a Microsoft Dynamics 365 Finance szolgáltatásban.
author: ShylaThompson
ms.date: 11/16/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-10-28
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: dd49edeb92e6a23723b1b6b6ea7800b69a81bd0f
ms.sourcegitcommit: 7d0cfb359a4abc7392ddb3f0b3e9539c40b7204d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/14/2021
ms.locfileid: "5897600"
---
# <a name="electronic-messaging"></a>Elektronikus üzenetküldés

[!include [banner](../includes/banner.md)]

Ez a témakör a áttekintést és beállítással kapcsolatos információt nyújt az elektromos üzenetküldéssel kapcsolatban.

Nemrég a világ számos országának és régiójának kormányai és törvényhozó hatóságai alkalmazni kezdték az adott országokban vagy régiókban regisztrált vállalatokkal szembeni jelentéskészítési előírásokat. A követelmények célja az, hogy ezektől a vállalatoktól elektronikus úton lehessen adatokat gyűjteni, közvetlenül a feljegyzésre, tárolásra és kezelésre használt rendszerből.

A Finance Elektronikus üzenetküldés funkciója támogatja az elektronikus együttműködés számos folyamatát, amely a Finance és a kormányok és jogalkotási hatóságok által a hivatalos információk jelentésére, elküldésére és fogadására szolgáló rendszerek között zajlik.

Az Elektronikus üzenetek funkció integrálva van az **Elektronikus jelentéskészítés** (ER) modulban. Emiatt ER formátumot az elektronikus üzenetekhez be lehet állítani. További információ: [Elektronikus jelentéskészítés (ER)](/dynamics365/unified-operations/dev-itpro/analytics/general-electronic-reporting).

Elektronikus üzenetküldés a következő entitások alapján történik:

- **Elektronikus üzenet** – Jelentés vagy nyilatkoat, amelyet belsőleg kell jelenteni és/vagy továbbítani. Például egy jelentés, amely egy adóhivatalnak küldött.
- **Elektronikus üzenetcikkek** – Rekordok, amelyeket a jelentett üzenetbe kell szerepeltetni.
- **Elektronikus üzenetfeldolgozás** – Műveletek láncolata, amelyeket a szükséges adatok gyűjtésére, jelentések létrehozására, a Microsoft Azure blobtárhelyén az adatok tárolására, a jelentések rendszeren kívülre való továbbítása, a rendszeren kívülről származó válaszok fogadására, és a beérkezett információknak megfelelően az adatbázis frissítésére kell futtatni. A láncban található műveletek vagy kapcsolódnak vagy nem kapcsolódnak egymáshoz

Az alábbi ábra az elektronikus üzenetküldés adatainak útját mutatja be.

![Elektronikus üzenetküldés adatfolyama](media/electronic-messaging-data-flow.png)

Az elektronikus üzenetek funkció támogatja az alábbi eseteket:

- Üzenetek manuális létrehozása és jelentések generálása, amelyekk a különböző típusú társított exportálási ER-formátumokon alapulnak: Microsoft Excel, XML, JavaScript Object Notation (JSON), PDF, szöveg és Microsoft Word.
- Üzenetek automatikus létrehozása és feldolgozása, amik egy hatóságtól kért és beérkezett információkon alapul a társított importálási ER formátumon keresztül.
- Információk gyűjtése és feldolgozása adaforrásból üzenetelemként. Az adatforrás egy Finance tábla.
- További információk tárolása, és különböző értékek értékelése a specifikusan meghatározott osztályok lehívásával az üzenetekkel vagy üzenetelemekkel kapcsolatban.
- Információ aggregálása, amit az üzenetelemekben gyűjtött, az információ felosztása üzenet szerint, és jelentések létrehozása, amik a társított exportálási ER-formátumokban vannak.
- A létrehozott jelentések továbbítása egy webes szolgáltatónak az Azure Key Vault szolgáltatásban tárolt biztonsági információ segítségével.
- Válasz fogadása a webes szolgáltatótól, a válasz értelmezése, és szükség szerint az adatok frissítése a Finance szolgáltatásban.
- A létrehozott jelentések tárolása és áttekintése.
- A naplóadatok tárolása és áttekintése, amelyek egy üzenettel vagy üzenetelemhez kapcsolódóan futtatott műveletre vonatkoznak.
- A feldolgozás szabályozása különböző üzenetállapotok és üzenetelem-állapotok segítségével.

## <a name="set-up-electronic-messaging"></a>Elektronikus üzenetküldés beállítása

Elektronikus üzenetküldés segítségével különféle dokumentumtípusokhoz különböző elektronikus jelentéskészítési folyamatok karbantartása lehetséges. Egyes komplex esetekben az elektronikus üzenetküldést úgy állítják be, hogy üzenetállapotok, üzenetelem-állapotok, műveletek, további mezők és végrehajtható osztályok számos kombinációját lehetővé tegye. Az ilyen esetekhez adatentitás-csomagokat lehet importálni. Ezek az adatentitás-csomagok használata esetén importálni kell őket egy jogi személyhez az Adatkezelés eszköz segítségével. Az Adatkezelés eszköz használatával kapcsolatos további tudnivalókat lásd: [Adatkezelés](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).

Ha nem importál adatentitás-csomagot, akkor manuálisan is beállíthatja az Elektromos üzenetek funkciót. Ebben az esetben be kell állítania a következő elemeket:

- [Számsorozatok](#number-sequences)
- [Üzenetelem-típusok és -állapotok](#message-item-types-and-statuses)
- [Üzenetállapotok](#message-statuses)
- [További mezők](#additional-fields)
- [Végrehajtható osztály beállításai](#executable-class-settings)
- [Rekordok műveletek feltöltése](#populate-records-actions)
- [Webalkalmazások](#web-applications)
- [Webszolgáltatás-beállítások](#web-service-settings)
- [Üzenetfeldolgozási műveletek](#message-processing-actions)
- [Elektronikus üzenetek feldolgozása](#electronic-message-processing)

A következő részekben további információkat találhat minden egyes elemről.

### <a name="number-sequences"></a>Számsorozatok

Üzenetek és a üzenetelemek számsorozatainak beállítása. A számsorozatok segítségével a rendszer automatikusan számozza az üzeneteket és az üzenetelemeket. A hozzárendelt számok az üzenetek és üzenetelemek egyedi azonosítójaként szolgálnak majd a rendszerben. Az elektronikus üzenetküldéshez a számsorozatokat a **Főkönyvi paraméterek** oldalon (**Főkönyv** \> **Főkönyv beállítása** \> **Főkönyvi paraméterek**) menüpontban lehet beállítani.

### <a name="message-item-types-and-statuses"></a>Üzenetelem-típusok és -állapotok

Az üzenetelem-típusok azonosítják a rekordok típusait, amelyeket elektronikus üzenetekben használnak majd. Az üzenetelem-típusokat az **Üzenetelem-típusok** oldalon állíthat be (**Adó** \> **Beállítás** \> **Elektronikus üzenetek** \> **Üzenetelem-típusok**).

Az üzenetelem-állapotok azonosítják az állapotokat, amelyek az üzenetelemre vonatkoznak majd a feldolgozásban, amelyet beállít. Az üzenetelem-típusokat az **Üzenetelem-állapotok** oldalon állíthat be (**Adó** \> **Beállítás** \> **Elektronikus üzenetek** \> **Üzenetelem-állapotok**).

A **Törlés engedélyezése** paraméter egy üzenet elemállapotában határozza meg, hogy felhasználók törölhetik-e azokat az üzenetelemeket, amelyek ezzel az állapottal rendelkeznek az **Elektronikus üzenetek** vagy **Elektronikusüzenet-elemek** képernyőn.

### <a name="message-statuses"></a>Üzenetállapotok

Üzenetállapotok beállítása, amelyek rendelkezésre állnak az üzenetek feldolgozása során. Az üzenetállapotokat az **Üzenetállapotok** oldalon állíthat be (**Adó** \> **Beállítás** \> **Elektronikus üzenetek** \> **Üzenetállapotok**).

Az alábbi táblázat ismerteti az **Üzenetállapotok** oldalon elérhető mezőket.

| Mezőnév          | Leírás |
|---------------------|-------------|
| Üzenet állapota      | Adjon meg egy egyedi nevet az üzenetállapot számára. Az üzenetállapotok egy elektronikus üzenet az adott pillanatban érvényes állapotának jellemzésére használatosak. A beírt név jelenik meg az **Elektronikus üzenetek** lapon, és az elektronikus üzenetekhez kapcsolódó naplóban. |
| Leírás         | Adja meg az üzenetállapot leírását. |
| Választípus       | Válassza ki az üzenetállapothoz tartozó válasz típusát. Előfordulhat, hogy bizonyos műveletek a feldolgozás során egynél több választípust eredményeznek. Például a **Webszolgáltatás** típusú műveletek **Sikeresen végrehajtott** vagy **Technikai hiba** választípust is eredményezhetnek a végrehajtás eredményétől függően. Ebben az esetben mindkét választípus üzenetállapotát meg kell határozni. A művelettípusokkal és a hozzájuk kapcsolódó választípusokkal kapcsolatos további információkért lásd az [Üzenetfeldolgozási művelettípusok](#message-processing-action-types) részt. |
| Üzenetelem-állapot | Bizonyos esetekben előfordulhat, hogy egy elektronikus üzenet állapotának a kapcsolódó üzenetelemek állapotát is befolyásolnia kell. Válassza ki az üzenetelem állapotát ebben a mezőben, amelyet társítani szeretne az üzenet állapotával. |
| Törölhető        | Jelölje be ezt a jelölőnégyzetet, ha szeretné, hogy a felhasználók képesek legyenek az olyan elektronikus üzenetek törlésére, amely az **Elektronikus üzenetek** oldalon ezzel az állapottal rendelkeznek. |

### <a name="additional-fields"></a>További mezők

Az Elektronikus üzenetek funkció segítségével kitöltheti a rekordokat egy tranzakciós táblából. Ezzel a módszerrel a rekordokat előkészítheti a jelentéskészítésre, majd jelentheti őket. Azonban néha a tranzakciós táblák nem tartalmaznak elég információt ahhoz, hogy a rekordokat a jelentéskészítési követelményeknek megfelelő módon ki lehessen tölteni. Annak érdekében, hogy a rekordhoz tartozó jelentéshez szükséges összes adatot ki tudja tölteni, létrehozhat további mezőket. A további mezőket az üzenetekhez és üzenetelemekhez is társíthatja. További mezőket a **További mezők** oldalon állíthat be (**Adó** \> **Beállítás** \> **Elektronikus üzenetek** \> **További mezők**).

Az alábbi táblázat ismerteti a **További mezők** oldalon elérhető általános mezőket.

| Mező       | Leírás |
|-------------|-------------|
| Mezőnév  | Adja meg a folyamathoz kapcsolódó üzenetelemek további attribútumai nevét. Ez a név jelenik meg a felhasználói felületen (UI) a folyamat közben. A folyamathoz kapcsolódó ER-konfigurációban is használatos. |
| Leírás | Adja meg a további mező leírását. |
| Felhasználói szerkesztés   | Ezt a beállítást állítsa **Igen** értékre, ha szeretné, hogy a felhasználók képesek legyenek a további mező értékét a felhasználói felületről módosítani. |
| Számláló     | Állítsa ezt a beállítást **Igen** értékre, hogy a további mező tartalmazzon egy számsorozatot az elektronikus üzenetben. A kiegészítő mező értéklt a rendszer automatikusan kitölti az **Elektronikus jelentés exportálása** típusú művelet futtatása során. |
| Rejtett      | Ezt a beállítást állítsa **Igen** értékre, ha a további mezőt el szeretné rejteni a felhasználói felületen. |

Minden további mező eltérő értékeket tartalmazhat a feldolgozáshoz. Ezeket az értékeket **Értékek** gyorslapon adhatja meg: Az alábbi táblázatban részletes leírás található ezekről a mezőkről.

| Mező                | Leírás |
|----------------------|-------------|
| Mező értéke          | Adja meg a jelentés során az üzenethez vagy üzenetelemhez kapcsolódóan használandó mezőértéket. |
| Leírás          | Adja meg a mezőérték leírását. |
| Számla típusa         | Lehetséges, hogy bizonyos mezőértékek meghatározott számlatípusokra van korlátozva. Válassza ki a következő értékek egyikét: **Összes**, **Vevő**, vagy **Szállító**. |
| Számlakód         | Ha a **Számlatípus** mezőben **Vevő** vagy **Szállító** lehetőséget választott, a mezőérték használatát tovább korlátozhatja egy meghatározott csoportra vagy táblára. |
| Számla/csoport száma | Ha a **Számlatípus** mezőben **Vevő** vagy **Szállító** lehetőséget választott, és ha a **Számlakód** mezőben megadott egy csoportot vagy táblát, akkor ebben a mezőben megadhat egy meghatározott csoportot vagy ellenoldali felet. |
| Érvénybe lépés            | Adja meg a dátumot, amikortól az értéket figyelembe kell venni. |
| Lejárat           | Adja meg a dátumot, amikortól az értéket már nem kell figyelembe venni. |

Alapértelmezés szerint a **Számla/csoport száma**, **Számlakód**, **Hatályos** és **Lejárat** mezők által meghatározott feltételek kombinációi nem befolyásolják a további mezők értékeinek kiválasztását. Azonban ezek a kombinációk használhatók egy végrehajtható osztályban egy meghatározott logika megvalósításához, amely a további mezők értékeit kiszámítja.

### <a name="executable-class-settings"></a>Végrehajtható osztály beállításai

Egy végrehajtható osztály egy olyan X++ metódus vagy osztály, amelyet az elektronikus üzenetfeldolgozás le tud hívni egy művelettel kapcsolatban, ha a folyamathoz értékelés szükséges.

Manuálisan beállíthat egy végrehajtható osztályt a **Végrehajtható osztály beállításai** oldalon (**Adó** \> **Beállítás** \> **Elektronikus üzenetek** \> **Végrehajtható osztály beállításai**). Hozzon létre egy sort, és állítsa be a következő mezőket.

| Mező                 | Leírás |
|-----------------------|-------------|
| Végrehajtható osztály      | Adja meg a nevet, amelyet egy olyan üzenetfeldolgozási művelet során használni kíván, amellyel kapcsolatban az osztályt lehívják. |
| Leírás           | Adja meg a végrehajtandó osztály leírását. |
| Végrehajtható osztály neve | Jelöljön ki egy X ++ végrehajtható osztályt. |
| Végrehajtási szint       | Ez a mező automatikusan kerül beállításra, mert az értéket előre meg kell határozni a kiválasztott végrehajtható osztályhoz. A mező korlátozza a szintet, amelyen a kapcsolódó értékelés fut. |
| Osztály leírása     | Ez a mező automatikusan kerül beállításra, mert az értéket előre meg kell határozni a kiválasztott végrehajtható osztályhoz. |

Előfordulhat, hogy az egyes végrehajtható osztályok kötelező paramétereket tartalmaznak, amelyeket a végrehajtható osztály első lefuttatása előtt meg kell adni. A paraméterek meghatározásához válassza a Műveleti ablaktábla **Paraméterek** lehetőségét, állítsa be a mezőket a megjelenő párbeszédablakban, majd kattintson az **OK** lehetőségre. Fontos, hogy kiválassza az **OK** lehetőséget. Ellenkező esetben a paramétereket nem menti az adatbázisba, és a végrehajtható osztályt nem tudja megfelelően lehívni.

### <a name="populate-records-actions"></a>Rekordok műveletek feltöltése

A rekordfeltöltési műveletek használatával olyan műveleteket állíthat be, amelyek rekordokat adnak az Üzenetelemek táblához azért, hogy az elektronikus üzenethez lehessen adni őket. Például, ha az elektronikus üzenetnek vevői számlákat kell jelentenie, be kell állítania a Rekordok feltöltése műveletet, amely a Vevői számla naplója táblában található **Adatforrás** mezőre hivatkozik. Rekordfeltöltési műveleteket a **Rekordfeltöltési művelet** oldalon állíthat be (**Adó** \> **Beállítás** \> **Elektronikus üzenetek** \> **Rekordfeltöltési műveletek**). Hozzon létre egy új rekordot minden művelethez, amelynek rekordokat kell adnia a táblához, és állítsa be az alábbi mezőket.

| Mező       | Leírás |
|-------------|-------------|
| Név        | Adjon nevet a műveletnek, amely a folyamatban rekordokat tölt fel. |
| Leírás | Adja meg a Rekordok feltöltése művelet leírását. |

Az **Adatforrások beállítása** gyorslapon adjon hozzá egy sort minden olyan adatforráshoz, amelyet a folyamathoz használ, és állítsa be a következő mezőket.

| Mező                  | Leírás |
|------------------------|-------------|
| Név                   | Adja meg az adatforrás nevét. |
| Üzenetelem típusa      | Válassza ki az üzenetelem-típust, amely akkor használatos, amikor a rekordokat létrehozzák az adatforráshoz. |
| Számla típusa           | Válassza ki a számlatípust, amelyet az adatforrásból származó rekordokkal kell társítani. |
| Fő tábla neve      | Válassza ki azt a táblát, amely az adatforrás legyen. |
| Dokumentumszám mező  | Válassza ki a mezőt, amelyből a választott táblában a dokumentumszámot kell venni. |
| Dokumentumdátum mező    | Válassza ki a mezőt, amelyből a választott táblában a dokumentum dátumát kell venni. |
| Dokumentumszámla mező | Válassza ki a mezőt, amelyből a választott táblában a dokumentumszámlát kell venni. |
| Felhasználó lekérdezése             | Ha ez a jelölőnégyzet be van jelölve, akkor lekérdezést állíthat be, ha kiválasztja a rács felett a **Lekérdezés szerkesztése** lehetőséget. Ellenkező esetben az összes rekord a kiválasztott adatforrásból került feltöltésre. |

### <a name="web-applications"></a>Webalkalmazások

A webalkalmazás beállításai segítségével beállíthat egy olyan webalkalmazást, amely támogatja az Open Authorization (OAuth) 2.0 szolgáltatást. Az OAuth az a nyitott szabvány, amelynek segítségével a felhasználók saját nevükben „biztonságos delegált hozzáférést” biztosíthatnak az alkalmazásnak anélkül, hogy a hozzáféréshez használt hitelesítési adataikat meg kellene vele osztaniuk. Az engedélyezési folyamatot is elvégezheti, amelyhez kérhet egy ellenőrzőkódot és hozzáférési tokent. A webes alkalmazás beállításait a **Webes alkalmazások** oldalon (**Adó** \> **Beállítások** \> **Elektronikus üzenetek** \> **Webes alkalmazások**) állíthatja be.

Az alábbi táblázat ismerteti a **Webes alkalmazások** oldalon elérhető mezőket.

| Mező                        | Leírás |
|------------------------------|-------------|
| Alkalmazásnév             | Adja meg a webes alkalmazás nevét. |
| Leírás                  | Itt megadhatja a webes alkalmazás leírását. |
| Alap URL                     | Adja meg a webes alkalmazás alap internetcímét. |
| Engedélyezési URL-cím elérési útja       | Adja meg a hitelesítésre szolgáló URL-cím összeállításának elérési útját. |
| Jogkivonat URL-címe               | Adja meg a tokenhez tartozó URL-cím összeállításának elérési útját. |
| Átirányítási URL-cím                 | Adja meg az átirányítási URL-címet. |
| Ügyfél azonosítója                    | Adja meg a webalkalmazás ügyfél-azonosítóját. |
| Titkos ügyfélkód                | Adja meg a webalkalmazás titkos ügyfélkódját. |
| Kiszolgálói jogkivonat                 | Adja meg a webalkalmazás kiszolgálótokenjét. |
| Engedélyezési formátum megfeleltetése | Válassza ki a hitelesítésre vonatkozó kérelem létrehozásához használt ER formátumot. |
| Jogkivonat modell-leképezésének importálása   | Válasszon egy ER importáló modell-leképezést, amely a hozzáférési token tárolására szolgál. |
| Kiadott hatókör                | Az alkalmazáshoz a kérelmek esetére biztosított hatókör. Ez a mező automatikusan frissül. |
| A hozzáférési jogkivonat lejár ennyi idő múlva:  | A hozzáférési token lejáratáig fennmaradó idő. | 
| Elfogadás                       | Határozza meg a webes kérelem **Elfogadás** tulajdonságát. Például adja meg a következőt: **application/vnd.hmrc.1.0+json**. |
| Tartalomtípus                 | Határozza meg a tartalom típusát. Például adja meg a következőt: **application/json**. |

Ezenkívül a **Webalkalmazások** Műveleti ablaktábláján a következő gombok találhatók, amelyek támogatják a hitelesítési folyamatot:

- **Engedélyezési kód lekérése** – A webalkalmazás engedélyezését kezdeményezi.
- **Hozzáférési token lekérése** – A hozzáférési token lekérési folyamatát kezdeményezi.
- **Hozzáférési token frissítése** – Frissíti a hozzáférési tokent.

Amikor egy webalkalmazás hozzáférési tokenjét titkosított formátumban tárolja a rendszer adatbázisában, az használható webes szolgáltatással kapcsolatos kérelmekhez. A biztonsági okokból a hozzáférési tokenhez való hozzáférést korlátozni kell azon szerepkörökre, amelyekhez válaszolhatnak az adott kérelmekre. Ha a biztonsági csoporton kívüli felhasználók próbálnak válaszolni egy kérelemre, hibaüzenetet kapnak, amely tájékoztatja őket, hogy nincs engedélyük a kiválasztott webalkalmazáson keresztüli együttműködésre. Ha szeretné beállítani azokat a biztonsági szerepköröket, amelyeknek feltétlenül rendelkezniük kell hozzáféréssel a hozzáférési tokenhez, használja a **Webalkalmazások** oldal **Biztonsági szerepkörök** gyorslapját. Ha nincsenek megadva egy webalkalmazáshoz biztonsági szerepkörök, akkor csak egy rendszergazda tud együttműködni a webalkalmazás segítségével.

### <a name="web-service-settings"></a>Webszolgáltatás-beállítások

Webes szolgáltatás beállításainak segítségével beállíthatja a közvetlen adatátvitelt a webes szolgáltatáshoz. A webes szolgáltatás beállításait a **Webes szolgáltatás beállításai** oldalon (**Adó** \> **Beállítások** \> **Elektronikus üzenetek** \> **Webes szolgáltatás beállításai**) állíthatja be.

Az alábbi táblázat ismerteti a **Webes szolgáltatás beállításai** oldalon elérhető mezőket.

| Mező                          | Leírás |
|--------------------------------|-------------|
| Webes szolgáltatás                    | Adja meg a webes szolgáltatás nevét. |
| Leírás                    | Itt megadhatja a webes szolgáltatás leírását. |
| Internetcím               | Adja meg a webes szolgáltatás internetcímét. Ha egy webalkalmazás van megadva egy webes szolgáltatáshoz, és a webes szolgáltatás internetcímének meg kell egyeznie a kiválasztott webalkalmazáshoz meghatározott internetcímmel, kattintson az **Alap URL-cím másolása** gombra a webalkalmazás alap URL-címének másoláshoz ebbe a mezőbe. |
| Diploma                    | Válasszon ki egy korábban beállított Key Vault-tanúsítványt. |
| Webalkalmazás                | Válasszon ki egy korábban beállított Key Vault-tanúsítványt. |
| A válasz típusa – XML        | Állítsa ezt a beállítást **Igen** értékre, ha a választípus XML. |
| Kérelemmetódus                 | Adja meg a kérés metódusát. A HTTP meghatároz egy készlet kérésmetódust, amely jelzi a műveletet, amelyet az adott erőforráshoz el kell végezni. A kérelem metódusa lehet **GET**, **POST**, vagy más HTTP-metódus. |
| Kérelem fejléce                | Adja meg a kérés fejléceit. A kérés fejléce egy HTTP-fejlév, amelyet egy HTTP-kérésben lehet használni, és amely nem kapcsolódik az üzenet tartalmához. |
| Elfogadás                         | Határozza meg a webes kérelem **Elfogadás** tulajdonságát. |
| Kódolás elfogadása                | Adja me az **Accept-Encoding** értékét. Az Accept-Encoding kérés HTTP-fejléce a tartalom kódolását hirdeti, amelyet a kliens is megért. Ez a tartalomkódolás általában egy kompressziós algoritmus. |
| Tartalomtípus                   | Határozza meg a tartalom típusát. A Tartalomtípus entitás HTTP-fejléce jelzi az erőforrás médiatípusát. |
| Sikeres válasz kódja       | Adja meg a HTTP-állapototkódot, amely jelzi, hogy a kérelem sikeres volt. |
| Kérelem fejlécéhez tartozó formátum megfeleltetése | Válassza ki a webes kérelem fejlécének létrehozásához használt ER formátumot. |

### <a name="message-processing-actions"></a>Üzenetfeldolgozási műveletek

Az üzenetfeldolgozási műveletek segítségével műveleteket hozhat létre a folyamataihoz, és beállíthatja paramétereiket. Az üzenetfeldolgozási műveleteket az **Üzenetfeldolgozási műveletek** oldalon állíthat be (**Adó** \> **Beállítás** \> **Elektronikus üzenetek** \> **Üzenetfeldolgozási műveletek**).

Az alábbi táblázat ismerteti az **Üzenetfeldolgozási műveletek** oldalon elérhető mezőket.

#### <a name="general-fasttab"></a>Általános gyorslap

| Mező                       | Leírás |
|-----------------------------|-------------|
| Művelettípus                 | Válassza ki a művelet típusát. A rendelkezésre álló lehetőségekkel kapcsolatos további tudnivalókat lásd az [Üzenetfeldolgozási művelettípusok](#message-processing-action-types) szakaszban. |
| Formátum leképezése              | Válassza ki, hogy a művelethez milyen ER-formátumot kell lehívni. Ez a mező csak az **Elektronikus jelentéskészítés exportálása**, **Elektronikus jelentéskészítés importálása** és **Elektronikus jelentéskészítés exportálási üzenete** típusokhoz tartozó műveletekhez érhető el. |
| Formátum megfeleltetése az URL-cím elérési útvonalára vonatkozóan | Válassza ki, hogy a művelethez milyen ER-formátumot kell lehívni. Ez a mező csak a **Webszolgáltatás** típusú műveletekhez érhető el. Ennek segítségével lehet létrehozni az URL-cím elérési útvonalát, amelyet a kiválasztott webkiszolgálóhoz meghatározott alap internetes címhez adnak hozzá. |
| Üzenetelem típusa           | Válassza ki a rekordok típusát, amelyhez a műveletet értékelni kell. Ez a mező az **Üzenetelem végrehajtási szint**, **Elektronikus jelentéskészítés exportálása**, **Elektronikus jelentéskészítés importálása** és **Webszolgáltatás** típusokhoz tartozó műveletekhez érhető el, és még néhány másik típushoz. Ha üresen hagyja ezt a mezőt, minden olyan üzenetelem-típus értékelésre kerül, amely az üzenetfeldolgozáshoz meg van határozva. |
| Végrehajtható osztály            | Jelölje ki a korábban létrehozott végrehajthatóosztály-beállításokat. Ez a mező csak az **Üzenetelem-végrehajtási szint** és **Üzenetelem-végrehajtási szint** típusokhoz tartozó műveletekhez érhető el. |
| Rekordok művelet feltöltése     | Válasszon ki egy korábban már beállított rekordfeltöltési műveletet. Ez a mező csak a **Rekordfeltöltés** típusú műveletekhez érhető el. |
| Webes szolgáltatás                 | Válasszon ki egy korábban már beállított webszolgáltatást. Ez a mező csak a **Webszolgáltatás** típusú műveletekhez érhető el. |
| Fájlnév                   | Adja meg a fájl nevét, amely a művelet eredményeképp jön létre. Ez a fájl lehet a webkiszolgálótól érkező válasz vagy a létrehozott jelentés. Ez a mező csak a **Webszolgáltatás** és **Elektronikus jelentéskészítés üzenet exportálása** típusú műveletekhez érhető el. |
| Párbeszédpanel megjelenítése                 | Állítsa ezt a beállítást **Igen** értékre, ha a jelentés létrehozás előtt a felhasználónak jelenjen meg egy párbeszédablak. Ez a mező csak az **Elektronikus jelentéskészítés üzenet exportálása** típus műveletekhez érhető el. |

##### <a name="message-processing-action-types"></a>Üzenetfeldolgozási művelettípusok

A **Művelettípus** mezőben az alábbi lehetőségek éérhetők el:

- **Üzenet létrehozása** – Ennek a művelettípusnak a segítségével a felhasználók manuálisan hozhatnak létre üzeneteket az **Elektronikus üzenet** oldalon. Kiindulási állapotot nem lehet beállítani ilyen típusú művelethez.
- **Rekordok feltöltése** – A **Rekordok feltöltése** típusú műveletet előzőleg be kell állítani. Társítsa ezt a művelettípust a Rekordok feltöltése művelettel, hogy a művelet szerepeljen a feldolgozásban. Feltételezett, hogy ez a művelettípus vagy üzenetfeldolgozás első műveletéhez (ha nem volt előre létrehozva elektronikus üzenet) vagy olyan művelethez, amely üzenetelemeket ad üzenetekhez, amelyeket korábban az **Üzenet létrehozása** típusú művelettel hoztak létre. Ezért az ilyen típusú műveletek esetén csak az üzenetelemek eredményállapotát lehet beállítani. A kiindulási állapot csak üzenethez állítható be.
- **Üzenet-végrehajtási szint** – Ennek a művelettípusnak a használatával be lehet egy végrehajtható osztályt állítani, amelyet az üzenet szintjén kell értékelni.
- **Üzenetelem-végrehajtási szint** – Ennek a művelettípusnak a használatával be lehet egy végrehajtható osztályt állítani, amelyet az üzenetelem szintjén kell értékelni.
- **Elektronikus jelentéskészítés exportálása** – Ez a művelettípus használható az olyan műveletekhez, amelyeknek reportot kell létrehozniuk egy exportálási ER-konfiguráció alapján az üzenetelem szintjén.
- **Elektronikus jelentéskészítés exportüzenete** – Ez a művelettípus használható az olyan műveletekhez, amelyeknek reportot kell létrehozniuk egy exportálási ER-konfiguráció alapján az üzenet szintjén (például ha az üzenetnek nincsenek üzenetelemei).
- **Elektronikus jelentéskészítés importálása** – Ez a művelettípus használható az olyan műveletekhez, amelyeknek reportot kell létrehozniuk egy importálási ER-konfiguráció alapján.
- **Üzenetszint felhasználói feldolgozás** – Ez a művelettípus használható olyan műveletekhez, amelyek valamilyen manuális felhasználói műveletet feltételeznek az üzenet szintjén. Például a felhasználó frissítheti az üzenetek állapotát.
- **Felhasználói feldolgozás** – Ez a művelettípus használható olyan műveletekhez, amelyek valamilyen manuális felhasználói műveletet feltételeznek az üzenetelem szintjén. Például a felhasználó frissítheti az üzenetelemek állapotát.
- **Webes szolgáltatás** – Ez a művelettípus használható olyan műveletekhez, amelyeknek egy létrehozott jelentést egy webes szolgáltatáshoz kell továbbítaniuk. Ez a művelettípus nem használatos az Olasz beszerzés és az Értékesítési számlakommunikáció jelentéskészítéséhez. A **Webszolgáltatás** típusú műveletek esetén az **Üzenetfeldolgozási műveletek** oldalán található a **Vegyes részletek** gyorslap, ahol meghatározhatja a visszaigazolási szöveget. Ez a visszaigazolási szöveg lesz a megjelenítve a felhasználó számára, mielőtt a kiválasztott webszolgáltatás kérelmére reagálnak lenne.
- **Ellenőrzés kérése** – Ezzel a művelettípussal ellenőrzést lehet kérni a kiszolgálótól.

#### <a name="initial-statuses-fasttab"></a>Kiindulási állapotok gyorslap

> [!NOTE]
> A **Kiindulási állapotok** gyorslap nem érhető el olyan műveletekhez, amelyeknek kiindulási művelettípusa **Üzenet létrehozása**.

| Mező               | Leírás |
|---------------------|-------------|
| Üzenetelem-állapot | Válassza ki azt az üzenetelem-állapotot, amelyre vonatkozóan a kiválasztott üzenetfeldolgozási műveletet értékelni kell. |
| Leírás         | A kiválasztott üzenetelem-állapot leírása. |

#### <a name="result-statuses-fasttab"></a>Eredményállapotok gyorslap

| Mező               | Leírás |
|---------------------|-------------|
| Üzenet állapota      | Válassza ki azt az üzenetállapotokat, amelyekre vonatkozóan a kiválasztott üzenetfeldolgozási műveletet értékelni kell. Ez a mező csak az üzenet szintjén értékelt üzenetfeldolgozási műveletekhez elérhető. Például elérhető az **Elektronikus jelentéskészítés exportálása** és **Elektronikus jelentéskészítés importálása** típusú műveletekhez, de nem érhető el a **Felhasználói feldolgozás** és az **Üzenetelem végrehajtási szint** típusúakhoz. |
| Leírás         | A kiválasztott üzenetállapot leírása. |
| Választípus       | A kiválasztott üzenetállapot választípusa. |
| Üzenetelem-állapot | Válassza ki azokat az eredményállapotokat, amelyeknek elérhetőnek kell lenniük, miután a kiválasztott üzenetfeldolgozási műveletet a rendszer értékelte. Ez a mező csak az üzenetelem szintjén értékelt üzenetfeldolgozási műveletekhez elérhető. Például elérhető a **Felhasználói feldolgozás** és **Üzenetszint felhasználói feldolgozás** típusokhoz. Az üzenet szintjén értékelt üzenetfeldolgozási műveletek esetén ez a mező az üzenetelem-állapotot mutatja, amelyet a kiválasztot üzenetállapothoz beállítottak, |

Az alábbi táblázat bemutatja az eredményállapotokat, amelyeket a különböző művelettípusokhoz és választípusokhoz be kell állítani.

| Elektronikus üzenet művelettípusa/Választípus | Sikeresen végrehajtva | Üzleti hiba | Technikai hiba | Felhasználó által meghatározott | Érvénytelenít |
|----------------------------------------------|-----------------------|----------------|-----------------|--------------|--------|
| Üzenet létrehozása                               | X                     |                |                 |              |        |
| Elektronikus jelentéskészítés exportálása                  | X                     |                |                 |              |        |
| Elektronikus jelentéskészítés importálása                  |                       |                |                 |              |        |
| Webes szolgáltatás                                  | X                     |                | X               |              |        |
| Felhasználói feldolgozás                              |                       |                |                 |              |        |
| Üzenet végrehajtási szint                      |                       |                |                 |              |        |
| Rekordok felöltése                             |                       |                |                 |              |        |
| Üzenetcikk végrehajtási szint                 |                       |                |                 |              |        |
| Kérelem ellenőrzése                         | X                     | X              | X               |              |        |
| Elektronikus jelentéskészítés üzenet exportálása          | X                     |                |                 |              |        |
| Üzenetszint felhasználói feldolgozás                |                       |                |                 |              |        |

### <a name="electronic-message-processing"></a>Elektronikus üzenetek feldolgozása

Az elektronikus üzenetfeldolgozás az Elektronikus üzenetek funkció alapvető koncepciója. Összesíti azokat a műveleteket, amelyeket az elektronikus üzenet esetén értékelni kell. A műveletek összekapcsolása kiindulási állapoton és eredményállapoton keresztül történhet. Másik lehetőségként a **Felhasználó feldolgozás** típusú műveletek önállóan is elindíthatók. Az **Elektronikus üzenetek feldolgozása** lapon (**Adó** \> **Beállítás** \> **Elektronikus üzenetek** \> **Elektronikus üzenetek feldolgozása**) további mezőket választhat ki, amelyeket a rendszer támogatni fog feldolgozás közben vagy üzenetszinten vagy üzenetelemek szintjén.

A **Művelet** gyorslapon előre meghatározott műveleteket adhat a feldolgozáshoz. Megadhatja, hogy egy műveletet külön kell-e futtatni, vagy a feldolgozás során elindítható. Annak meghatározásához, hogy egy művelet a feldolgozás során csak egy felhasználó által elindítható, állítsa az adott művelet **Futtatás külön** mezőjének értékét **Igen** értékre. Ha egy művelet elindítható azon üzenetek vagy üzenetelemek feldolgozása által is, amelyeket a művelet kezdő állapotaként megadott állapotban szerepelnek, állítsa a **Futtatás külön** mezőt **Nem** értékre. A **Felhasználói művelet** típusű műveletet mindig csak külön szabad futtatni.

Bizonyos esetekben több műveletet kell összesíteni egy sorozatba annak ellenére, hogy az első művelet a beállításai alapján külön is képes futásra. Például ha a felhasználónak kell kezdeményeznie a jelentéskészítést, de a közvetlenül a jelentés létrehozása után el kell küldeni a webes szolgáltatásnak, és a webszolgáltatás válaszának tükröződnie kell a rendszerben. Ebben a helyzetben létrehozhatja a műveletek szétválaszthatatlan sorozatát, amelyeknek mindig együtt kell futniuk. A **Művelet** gyorslapon válassza az **El nem választható sorozat** lehetőséget a rács felett, és hozzon létre egy sorozatot. Ezután az együtt futtatandó minden egyes műveletnél válassza ki a sorozatot az **El nem választható sorozat** mezőben. Ebben az esetben a **Futtatás külön** mezőt az első művelethez **Igen** értékre állíthatja, de a többi műveletnél **Nem** értékre.

Az **Üzenetelem további mezői** gyorslapon hozzáadhat előre meghatározott további mezőket, amelyek az üzenetelemekhez kapcsolódnak. Minden egyes üzenettípushoz kell további mezőket hozzáadnia, amelyekhez a mezők kapcsolódnak.

Az **Üzenet további mezői** gyorslapon hozzáadhat előre meghatározott további mezőket, amelyek az üzenetekhez kapcsolódnak.

A **Biztonsági szerepkörök** gyorslap lehetővé teszi, hogy beállítson biztonsági szerepköröket, amelyek egy meghatározott feldolgozáshoz előre meghatározásra kerülnek a rendszerben. A specifikus szerepkörrel rendelkező felhasználók csak azokat a feldolgozásokat látják, amelyek az adott szerepkörhöz meg vannak határozva.

A **Köteg** gyorslap lehetővé teszi annak beállítását, hogy kötegrendszerben dolgozzon.

## <a name="work-with-the-electronic-messages-functionality"></a>Elektronikus üzenetek funkcióval való munkavégzés

Ha az üzenet szintjén dolgozik, az **Elektronikus üzenetek** oldal (**Adó** \> **Lekérdezések és jelentések** \> **Elektronikus üzenetek** \> **Elektronikus üzenetek**) hasznosabb. Ha az adatgyűjtés (üzenetelem) szintjén üzemel, az **Elektronikus üzenetelemek** oldal (**Adó** \> **Lekérdezések és jelentések** \> **Elektronikus üzenetek** \> **Elektronikus üzenetelemek**) hasznosabb.

### <a name="electronic-messages"></a>Elektronikus üzenetek

A **Elektronikus üzenetek** oldal bemutatja az Ön számára rendelkezésre álló feldolgozást, a szerepkörének megfelelően. A biztonsági szerepköröket a feldolgozás beállításakor társítják a feldolgozáshoz. Minden egyes rendelkezésre álló feldolgozásra vonatkozóan az oldal megjeleníti az elektronikus üzeneteket és a hozzájuk kapcsolódó információt.

Az **Üzenetek** gyorslap a kijelölt feldolgozáshoz jeleníti meg az elektronikus üzeneteket. A kiválasztott üzenet állapotától és az előre meghatározott feldolgozástól függően néhány műveletet a rács feletti gombokkal futtathat:

- **Új** – Ez a gomb az **Üzenet létrehozása** típusú műveletekhez van társítva.
- **Törlés** – Ez a gomb akkor érhető el, ha a **Törlés engedélyezése** jelölőnégyzet be van jelölve a kiválasztott üzenet aktuális állapotához.
- **Adatgyűjtés** – Ez a gomb a **Rekordok feltöltése** típusú műveletekhez van társítva.
- **Jelentés létrehozása** – Ez a gomb az **Elektronikus jelentéskészítési exportálási üzenet** típusú műveletekhez van társítva.
- **Jelentés küldése** – Ez a gomb a **Webes szolgáltatás** típusú műveletekhez van társítva.
- **Válasz importálása** – Ez a gomb az **Elektronikus jelentéskészítés importálása** típusú műveletekhez van társítva.
- **Állapot frissítése** – Ez a gomb az **Üzenetszint felhasználói feldolgozás** típusú műveletekhez van társítva.
- **Üzenetelemek** – Nyissa meg az **Elektronikus üzenetelemek** oldalt.

A **Műveleti napló** gyorslap a kiválasztott üzenethez kapcsolódóan futtatott összes műveletről megjelenít információkat. Ha a művelet hibát okozott, a hibával kapcsolatos információk hozzá lesznek fűzve a kapcsolódó sorhoz a rácsban. Ha szerené áttekinteni a hibával kapcsolatos információkat, válassza az adott sort a rácsban, majd válassza a **Melléklet** gombot (kapocs jel) az oldal jobb felső sarkában.

Az **Üzenet további mezők** gyorslapon az üzenetekhez a feldolgozás beállításában meghatározott összes további mező látható. Ez a további mezők értékeit is megjeleníti.

Az **Üzenetelemek** gyorslap a kiválasztott üzenethez kapcsolódó összes üzenetelemet megjeleníti. A kiválasztott üzenetelem állapotától függően néhány műveletet a rács feletti gombokkal futtathat:

- **Törlés** – Ez a gomb akkor érhető el, ha a **Törlés engedélyezése** jelölőnégyzet be van jelölve a kiválasztott üzenetelemhez.
- **Állapot frissítése** – Ez a gomb a **Felhasználói feldolgozás** típusú műveletekhez van társítva.
- **Eredeti dokumentum** – Megnyit egy oldalt, amely a kiválasztott üzenetelemhez tartozó eredeti dokumentumot jeleníti meg.

Az összes, az adott üzenethez létrehozott és fogadott jelentés csatolva van az üzenethez. Ha szerené áttekinteni egy üzenethez kapcsolódó mellékleteket, válassza az adott üzenetet, majd válassza a **Melléklet** gombot (kapocs jel) az oldal jobb felső sarkában.

![Csatolmány gomb](media/attachment-icon.png)

A **Csatolmányok** oldal jeleníti meg a kiválasztott üzenethez kapcsolódó összes csatolmányt. A fájl megtekintéséhez jelölje ki a bal oldali listán, majd válassza **Megnyitás** lehetőséget a Művelet panelen.

![Megnyitás gomb](media/open-button.png)

Ezenkívül áttekintheti az adott művelethez kapcsolódó mellékleteket, amelyet korábban egy üzenethez futtattak. Az **Elektronikus üzenetek** oldalon válassza ki az üzenetet az **Üzenetek** gyorslapon, válassza ki a műveletet a **Műveleti napló** gyorslapon, majd válassza ki a **Mellékletek** gombot az oldal jobb felső sarkában.

Lefuttathatja az egész feldolgozást vagy csak egy bizonyos műveletet, ha kiválasztja a **Feldolgozás futtatása** lehetőséget a Művelet panelen.

### <a name="electronic-message-items"></a>Elektronikusüzenet-elemek

Az **Elektronikus üzenetelemek** oldalon az összes üzenetelem és az egyes üzenetelemekhez futtatott műveletek naplója látható. Ezenfelül az üzenetelemekhez meghatározott további mezőket is megjeleníti, valamint a további mezők értékeit.

Az alábbi táblázat ismerteti az **Üzenetelemek** oldalon elérhető mezőket.

<table>
<thead>
<tr>
<th>Mező</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr>
<td>Feldolgozás</td>
<td>A feldolgozás neve, amelyet az üzenetelem létrehozásához használtak.</td>
</tr>
<tr>
<td>Üzenetelem</td>
<td>Az üzenetelem azonosítója. Az azonosító automatikusan kerül hozzárendelésre, az <strong>Üzenetelem</strong> számsorozata alapján, amelyet a <strong>Főkönyvi paraméterek</strong> oldalon határoztak meg.</td>
</tr>
<tr>
<td>Üzenetelem dátuma</td>
<td>Az üzenetelem létrehozásának dátuma.</td>
</tr>
<tr>
<td>Üzenetelem típusa</td>
<td>Az üzenetelem típusa. Számos típusú üzenetelemet be lehet állítani ugyanahhoz a feldolgozáshoz (például <strong>Bejövő számlákat</strong> és <strong>Kimenő számlákat</strong>). Ezt a mezőt csak akkor lehet automatikusan kitölteni, ha az Üzenetelemek táblához hozzáadnak egy számlát.</td>
</tr>
<tr>
<td>Üzenetelem-állapot</td>
<td>Az üzenetelem aktuális állapota. A lehetséges állapotok az üzenetelem típusától függően változnak. Íme néhány példa:
<ul>
<li><strong>Feltöltött</strong> – Egy rekordot hozzáadtak az Üzenetelemek táblához.</li>
<li><strong>Értékelve</strong> – Az üzenetelemhez további attribútumok kerültek kiszállításra.</li>
<li><strong>Jelentve</strong> – Az üzenetelemet sikeresen hozzáadták egy jelentéshez.</li>
<li><strong>Kizárt</strong> – Ez az állapot akkor lehet hasznos, ha bizonyos üzenetelemeket ki kell zárnia a jelentésből az exportálás előtt.</li>
</ul>
</td>
</tr>
<tr>
<td>Átvitel dátuma</td>
<td>Oylyan feldolgozás esetén, amely automatikusan elküldi a létrehozott jelentést a rendszeren kívülre, a dátum, amikor az üzenetelemet elküldték.</td>
</tr>
<tr>
<td>Dokumentum száma</td>
<td>A mező automatikusan kitöltésre kerül a Rekordfeltöltés művelet beállítása alapján. Ezt a mezőt csak akkor lehet automatikusan kitölteni, ha az Üzenetelemek táblához hozzáadnak egy számlát.</td>
</tr>
<tr>
<td>Számlaszám</td>
<td>A vevő vagy szállító számlaszáma (vagy másik mezőérték, a Rekordfeltöltés műveletben megadottaknak megfelelően). Ezt a mezőt csak akkor lehet automatikusan kitölteni, ha az Üzenetelemek táblához hozzáadnak egy számlát.</td>
</tr>
<tr>
<td>Üzenet</td>
<td>Az üzenet száma. A szám automatikusan kerül hozzárendelésre, az <strong>Üzenet</strong> számsorozata alapján, amelyet a <strong>Főkönyvi paraméterek</strong> oldalon határoztak meg.</td>
</tr>
<tr>
<td>Üzenet állapota</td>
<td>Az elektronikus üzenet aktuális állapota.</td>
</tr>
<tr>
<td>Következő művelet</td>
<td>A következő műveletek, amelyeket az üzenetelem aktuális állapotához lehet indítani.</td>
</tr>
</tbody>
</table>

A **További mezők** lap megjeleníti a kijelölt üzenetelemhez tartozó további mezőket, és ezek értékeit.

#### <a name="run-processing"></a>Feldolgozás futtatása

Válassza a **Feldolgozás** lehetőséget a Művelet panelen az üzenetelemekhez tartozó feldolgozás futtatásához. Ha specifikus műveletet akar futtatni, akkor a **Feldolgozás futtatása** párbeszédablakban állítsa a **Művelet választása** lehetőséget **Igen** értékre, majd válasszon ki egy műveletet. Ha a teljes feldolgozást le akarja futtatni, hagyja a **Művelet választása** beállítást **Nem** értéken.

#### <a name="generate-report"></a>Jelentés létrehozása

Válassza a **Jelentés létrehozása** lehetőséget a Művelet panelen a jelentés létrehozásához. Ez a gomb az **Elektronikus jelentéskészítési exportálás** típusú műveletekhez van társítva.

#### <a name="update-status"></a>Állapot frissítése

Válassza az **Állapot frissítése** lehetőséget a Művelet panelen, ha egy vagy több üzenetelem állapotát szeretné frissíteni. Az **Állapot frissítése** párbeszédpanelen használja a **Belefoglalandó rekordok** gyorslapot a frissítendő üzenetelemek kiválasztására. Ellenőrizze, hogy helyesen határozta-e meg a kiválasztási feltételt, mivel az üzenetelem-állapotok frissítése a feltételek, a kiválasztott művelet kiindulási állapota és az Ön által meghatározott **Új állapot** értéke alapján történik. Az állapotfrissítés befejezése után nehéz megállapítani, hogy mely elemek frissültek. Emiatt nehéz lenne az állapotfrissítés visszaállítása.

#### <a name="electronic-messages"></a>Elektronikus üzenetek

Válassza az **Elektronikus üzenetek** lehetőséget a Művelet panelen, ahol áttekintheti a kiválasztott üzenetelemhez kapcsolódó elektronikus üzenetet.

Ezenkívül megtekintheti az összes fájlt, amelyek kapcsolódnak egy megadott üzenetelemhez. Válassza ki az üzenetelemhez tartozó **Üzenet** mezőt, vagy válassza az **Elektronikus üzenetek** elemet a Művelet panelen. Majd az **Elektronikus üzenet** oldalon válassza ki az üzenetet, amelynek fájljait át szeretné tekinteni, majd válassza a **Melléklet** gombot (kapocs jel) az oldal jobb felső sarkában.

![Csatolmány gomb](media/attachment-icon.png)

A **Csatolmányok** oldal jeleníti meg az üzenethez kapcsolódó összes csatolmányt. A fájl megtekintéséhez jelölje ki a bal oldali listán, majd válassza **Megnyitás** lehetőséget a Művelet panelen.

![Megnyitás gomb](media/open-button.png)

#### <a name="original-document"></a>Eredeti dokumentum

Válassza az **Eredeti dokumentum** elemet a Művelet panelen a kiválasztott üzenetelemhez tartozó eredeti dokumentum megnyitásához.

## <a name="example-set-up-and-run-processing-to-call-a-simple-er-exporting-format-to-generate-an-excel-report"></a>Példa: Feldolgozás beállítása és futtatása egy egyszerű ER exportálási formátum lehívásához egy Excel-jelentés létrehozása érdekében

Miután létrehozta az ER-formátumát, az adatforrásokhoz társította és befejezte azt, lefuttathatja az **Elektronikus jelentéskészítés** munkaterület segítségével. A rendszer létrehoz egy jelentést, és ezt helyileg elmentheti.

Be kell állítania az elektronikus üzenetfeldolgozást, ha szeretné szabályozni a jelentéskészítési folyamat alábbi aspektusait:

- Naplóinformáció a jelentés létrehozójáról.
- Naplóinformáció a jelentés létrehozásának idejéről.
- A jelentések mentése, amelyet korábbi időszakokra hoztak létre.

Ez a szakasz bemutat egy példát arra, hogy hogyan lehet elektronikus üzenetet beállítani egy Excelhez tartozó exportálási ER-formátumon alapuló jelentés létrehozására. A példa követéséhez az ER Excel jelentéskészítési formátumot már létre kell hoznia, adatforrásokhoz kell társítania és be kell fejeznie. Ezenfelül, az elektronikus üzenetekhez már be kell állítani egy számsorozatot.

A feldolgozás készítési során hasznos, ha először meghatározza a feldolgozási műveleteket és az állapotokat, amiket be fog állítani. Az alábbi ábra azt mutatja, hogy a feldolgozás hogy néz ki ebben a példában.

![Feldolgozási séma](media/processing-scheme.png)

#### <a name="create-message-statuses"></a>Üzenetállapotok létrehozása

1. Lépjen az **Adó \> Beállítás \> Elektronikus üzenetek \> Üzenetállapotok** menüpontra.
2. Hozza létre a következő üzenetállapotokat:

    - Új
    - Előkészítve
    - Létrehozva

    ![Üzenetállapotok](media/message-statuses.png)

3. Az **Új** állapothoz tartozó sorban jelölje be a **Törlés engedélyezése** jelölőnégyzetet, hogy a felhasználók törölhessenek olyan üzeneteket, amelyek ezzel az állapottal rendelkeznek.

#### <a name="create-additional-fields"></a>További mezők létrehozása

1. Lépjen az **Adó \> Beállítás \> Elektronikus üzenetek \> További mezők** menüpontra.
2. Adjon hozzá egy további mezőt és ennek értékeit. Íme, egy példa.

    ![További mezők](media/additional-fields.png)

3. Állítsa a **Felhasználói szerkesztés** beállítást **Igen** értékre, hogy a felhasználók szerkeszthessék a mezőt.

#### <a name="create-message-processing-actions"></a>Üzenetfeldolgozási műveletek létrehozása

Ebben a példában az alábbi műveleteket fogja létrehozni:

- **Üzenet létrehozása**
- **Frissítés Előkészítve értékre**
- **Jelentés létrehozása**
- **Frissítés kiindulási állapotra** (nem kötelező)

1. Lépjen az **Adó \> Beállítás \> Elektronikus üzenetek \> Üzenetfeldolgozási műveletek** menüpontra.
2. Hozzon létre egy műveletet, amelynek a neve **Üzenet létrehozása**. Az **Általános** gyorslapon a **Művelettípus** mezőben válassza az **Üzenet létrehozása** lehetőséget.
3. Hozzon létre egy **Frissítés Előkészítve értékre**, majd állítsa be a következő mezőket:

    - Az **Általános** gyorslapon a **Művelettípus** mezőben válassza az **Üzenetszint felhasználói feldolgozás** lehetőséget.
    - A **Kiindulási állapotok** gyorslapon az **Üzenetállapot** mezőben válassza az **Új** lehetőséget.
    - Az **Eredményállapotok** gyorslapon az **Üzenetállapot** mezőben válassza az **Előkészítve** lehetőséget. A **Választípus** mezőben adja meg a **Sikeresen végrehajtva** lehetőséget.

4. Hozzon létre egy **Jelentés létrehozása**, majd állítsa be a következő mezőket:

    - Az **Általános** gyorslapon a **Művelettípus** mezőben válassza az **Elektronikus jelentéskészítés exportálása** lehetőséget. A **Formátumleképezés** mezőben válassza ki az exportálási ER-formátumot. A lehetőségek a következők: **Excel**, **XML**, **JSON**, **Szöveg** és **Egyéb**.
    - A **Kiindulási állapotok** gyorslapon az **Üzenetállapot** mezőben válassza az **Előkészítve** lehetőséget.
    - Az **Eredményállapotok** gyorslapon az **Üzenetállapot** mezőben válassza a **Létrehozva** lehetőséget. A **Választípus** mezőben adja meg a **Sikeresen végrehajtva** lehetőséget.

    ![Jelentés létrehozása művelet](media/generate-report-action.png)

5. Nem kötelező: Annak érdekében, hogy a felhasználók egy jelentést több alkalommal ismételten létrehozzák, létrehozhat egy **Frissítés kiindulási állapotra** műveletet, és beállíthatja az alábbi mezőket:

    - Az **Általános** gyorslapon a **Művelettípus** mezőben válassza az **Üzenetszint felhasználói feldolgozás** lehetőséget.
    - A **Kiindulási állapotok** gyorslapon az **Üzenetállapot** mezőben válassza a **Létrehozva** lehetőséget.
    - Az **Eredményállapotok** gyorslapon adjon hozzá külön sort mindkét üzenetállapothoz (**Előkészítve** és **Új**). Mindkét sorban állítsa a **Választípus** mezőt **Sikeresen végrehajtva** értékre.

#### <a name="electronic-message-processing"></a>Elektronikus üzenetek feldolgozása

Ebben a példában az össze műveletet úgy kell beállítani, hogy egymástól külön is tudjanak futni. Az a feltételezés, hogy minden műveletet a felhasználó kezdeményez majd.

1. Lépjen az **Adó \> Beállítás \> Elektronikus üzenetek \> Elektronikus üzenetfeldolgozás** menüpontra.
2. Adjon hozzá egy rekordot a feldolgozáshoz, és adja hozzá az összes korábban meghatározott műveletet és egy további mezőt.
3. Választható: A **Biztonsági szerepkörök** gyorslapon határozza meg a biztonsági szerepköröket a feldolgozáshoz, hogy azzal korlátozza a meghatározott jelentéskészítéshez való hozzáférést.
4. Lépjen az **Adó \> Lekérdezések és jelentések \> Elektronikus üzenetek \> Elektronikus üzenetek** menüpontjára.
5. Válassza az **Új** lehetőséget egy üzenet létrehozásához. Ezen a ponton adhat hozzá dátumokat és leírást. Ekkor szükség szerint a további mező értékét is frissítheti.

    ![Elektronikus üzenet létrehozása](media/create-electronic-message.png)

A **Műveletnapló** gyorslapon a rács automatikusan kitöltésre kerül az adott üzeneten elvégzett összes művelet naplója.

Most törölheti vagy frissítheti az üzenet állapotát. Ha frissíteni szeretné egy üzenet állapotát, válassza az **Üzenetállapot** lehetőséget. Az **Új állapot** mezőben válassza az **Előkészítve** lehetőséget, majd az **OK** gombot.

![Az üzenet állapotának frissítése](media/update-status.png)

Az üzenet állapota **Előkészítve** állapotra frissül, és most létrehozhatja a jelentést a **Jelentés létrehozása** kiválasztásával. A jelentés létrejött, az üzenet állapota és a műveletnapló pedig frissült. A létrehozott jelentés megtekintéséhez válassza a **Melléklet** gombot (kapocs jel) az oldal jobb felső sarkában.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
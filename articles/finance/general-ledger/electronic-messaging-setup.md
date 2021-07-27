---
title: Elektronikus üzenetek beállítása
description: Ez a témakör az Elektronikus üzenetek (EM) funkció beállításának lépéseiről tartalmaz információt.
author: liza-golub
ms.date: 07/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2021-06-23
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 947170d1db132ca5a6b7caed0e47ee814b9148cc
ms.sourcegitcommit: 73d320d2103f2b0c6ecbb2b9df746469bc544ea2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/07/2021
ms.locfileid: "6433788"
---
# <a name="set-up-electronic-messages"></a>Elektronikus üzenetek beállítása

[!include [banner](../includes/banner.md)]

Az **Elektronikus üzenetek** (EM) funkció segítségével a különféle dokumentumtípusokhoz különböző elektronikus jelentéskészítési folyamatokat tarthat karban. Egyes olyan komplex esetekben, melyek támogatják az [országspecifikus jelentéskészítési funkciókat](electronic-messaging.md#country-specific-regulatory-features-supported-by-the-em-functionality), az EM funkciót úgy állítják be, hogy üzenetállapotok, üzenetelem-állapotok, műveletek, további mezők és végrehajtható osztályok számos kombinációjával rendelkezzen. Az ilyen esetekhez adatentitás-csomagokat lehet importálni. Ezen adatentitás-csomagok használata esetén importálni kell őket egy jogi személybe az Adatkezelés eszköz segítségével. Az Adatkezelés eszköz használatával kapcsolatos további tudnivalókat lásd: [Adatkezelés](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).

Ha nem importál adatentitás-csomagot, akkor manuálisan is beállíthatja az EM funkciót. Ebben az esetben be kell állítania a következő elemeket:

- [Számsorozatok](#sequences)
- [Üzenetelem-típusok](#types)
- [Üzenetelem-állapotok](#item)
- [Üzenetállapotok](#statuses)
- [További mezők](#additional)
- [Végrehajtható osztály beállításai](#executable)
- [Rekordok műveletek feltöltése](#populate)
- [Webalkalmazások](#applications)
- [Webszolgáltatás-beállítások](#settings)
- [Üzenetfeldolgozási műveletek](#actions)
- [Elektronikus üzenetek feldolgozása](#processing)

A következő részekben további információkat találhat minden egyes elemről.

## <a name="number-sequences"></a><a id="sequences"></a>Számsorozatok

Üzenetek és a üzenetelemek számsorozatainak beállítása. A számsorozatok segítségével ezután a rendszer automatikusan számozza az üzeneteket és az üzenetelemeket. A hozzárendelt számok az üzenetek és üzenetelemek egyedi azonosítójaként szolgálnak a rendszerben. Az elektronikus üzenetküldéshez a számsorozatokat a Főkönyvi paraméterek oldalon (**Főkönyv** \> **Főkönyv beállítása** \> **Főkönyvi paraméterek**) menüpontban lehet beállítani.

## <a name="message-item-types"></a><a id="types"></a>Üzenetelem-típusok

Az üzenetelem-típusok azonosítják a rekordok típusait, amelyeket elektronikus üzenetekben használnak. Az üzenetelem-típusokat az **Adó** \> **Beállítás** \> **Elektronikus üzenetek** \> **Üzenetelem-típusok** oldalon állíthatja be.

## <a name="message-item-statuses"></a><a id="item"></a>Üzenetelem-állapotok

Az üzenetelem-állapotok azonosítják azokat az állapotokat, amelyek az üzenetelemre vonatkoznak majd a feldolgozásban, amelyet beállít. Az üzenetelem-állapotokat az **Adó** \> **Beállítás** \> **Elektronikus üzenetek** \> **Üzenetelem-állapotok** oldalon állíthatja be.

A **Törlés engedélyezése** paraméter egy üzenet elemállapotában azt határozza meg, hogy felhasználók törölhetik-e azokat az üzenetelemeket, amelyek ezzel az állapottal rendelkeznek az **Elektronikus üzenetek** vagy **Elektronikusüzenet-elemek** oldalon.

## <a name="message-statuses"></a><a id="statuses"></a>Üzenetállapotok

Üzenetállapotok beállítása, amelyek rendelkezésre állnak az üzenetek feldolgozása során. Az üzenetállapotokat az **Adó** \> **Beállítás** \> **Elektronikus üzenetek** \> **Üzenetállapotok** oldalon állíthatja be.

Az alábbi táblázat ismerteti az **Üzenetállapotok** oldalon elérhető mezőket.

| Mezőnév          | Leírás |
|---------------------|-------------|
| Üzenet állapota      | Adjon meg egy egyedi nevet az üzenetállapot számára. Az üzenetállapotok egy elektronikus üzenet az adott pillanatban érvényes állapotának jellemzésére használatosak. A beírt név jelenik meg az **Elektronikus üzenetek** lapon, és az elektronikus üzenetekhez kapcsolódó naplóban. |
| Leírás         | Adja meg az üzenetállapot leírását. |
| Választípus       | Válassza ki az üzenetállapothoz tartozó választípust. Előfordulhat, hogy bizonyos műveletek a feldolgozás során egynél több választípust eredményeznek. Például a **Webszolgáltatás** típusú műveletek **Sikeresen végrehajtott** vagy **Technikai hiba** választípust is eredményezhetnek a végrehajtás eredményétől függően. Ebben az esetben mindkét választípus üzenetállapotát meg kell határozni. A művelettípusokkal és a hozzájuk kapcsolódó választípusokkal kapcsolatos további információkért lásd az alábbi, [Üzenetfeldolgozási művelettípusok](#action-types) részt. |
| Üzenetelem-állapot | Bizonyos esetekben előfordulhat, hogy egy elektronikus üzenet állapotának a kapcsolódó üzenetelemek állapotát is befolyásolnia kell. Válassza ki az üzenetelem állapotát ebben a mezőben, amelyet társítani szeretne az üzenet állapotával. |
| Törölhető        | Jelölje be ezt a jelölőnégyzetet, ha szeretné, hogy a felhasználók képesek legyenek az olyan elektronikus üzenetek törlésére, amelyek az **Elektronikus üzenetek** oldalon ezzel az állapottal rendelkeznek. |

## <a name="additional-fields"></a><a id="additional"></a>További mezők

Az EM funkcióval rekordokat lehet gyűjteni üzenetelemként a Microsoft Dynamics 365 Finance tranzakciós tábláiból. Ezzel a módszerrel a rekordokat előkészítheti a jelentéskészítésre, majd jelentheti őket. Azonban néha a tranzakciós táblák nem tartalmaznak elég információt ahhoz, hogy a rekordokat a jelentéskészítési követelményeknek megfelelő módon ki lehessen tölteni. Annak érdekében, hogy a rekordhoz tartozó jelentéshez szükséges összes adatot ki tudja tölteni, létrehozhat további mezőket. A további mezőket üzenetekhez és üzenetelemekhez társíthatja. További mezőket az **Adó** \> **Beállítás** \> **Elektronikus üzenetek** \> **További mezők** oldalon állíthat be.

Az alábbi táblázat ismerteti a **További mezők** oldalon elérhető általános mezőket.

| Mező       | Leírás |
|-------------|-------------|
| Mezőnév  | Adja meg a folyamathoz kapcsolódó elektronikus üzenetek vagy üzenetelemek további mezőjének nevét. Ez a név jelenik meg a felhasználói felületen (UI) a folyamat közben. A név a folyamathoz kapcsolódó Elektronikus jelentéskészítési ER-konfigurációban is használható. |
| Leírás | Adja meg a további mező leírását. |
| Felhasználói szerkesztés   | Ezt a beállítást állítsa **Igen** értékre, ha szeretné, hogy a felhasználók képesek legyenek a további mező értékét a felhasználói felületen módosítani. |
| Számláló     | Állítsa ezt a beállítást **Igen** értékre, hogy a további mező tartalmazzon egy számsorozatot az elektronikus üzenetben. A kiegészítő mező értékét a rendszer automatikusan kitölti az **Elektronikus jelentés exportálása** típusú művelet futtatása során. |
| Rejtett      | Állítsa **Igen** beállításra, ha a további mezőt el kell rejteni a felhasználói felületen az **Elektronikus üzenetek** lapon vagy az **Elektronikus üzenetelemek** lapon. |

Az **Értékek** gyorslapon előre meg lehet adni azokat az értékeket, amelyekkel egy további mező rendelkezhet. Ezeket az értékeket választhatják majd ki a felhasználók. Így a feldolgozás során nem kell manuálisan kitölteni őket. Az alábbi táblázatban részletes leírás található ezekről a mezőkről.

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

## <a name="executable-class-settings"></a><a id="executable"></a>Végrehajtható osztály beállításai

Egy végrehajtható osztály egy olyan X++ metódus vagy osztály, amelyet az elektronikus üzenetfeldolgozás le tud hívni egy művelettel kapcsolatban, ha a folyamathoz értékelés szükséges.

Manuálisan is be lehet állítani egy olyan végrehajtható osztályt, amelyet a feldolgozás során meg kell hívni. Ehhez lépjen az **Adó** \> **Beállítás** \> **Elektronikus üzenetek** \> **Végrehajtható osztály beállításai** menüpontba. Hozzon létre egy sort a **Végrehajtható osztály beállításai** oldalon, és állítsa be a következő mezőket.

| Mező                 | Leírás |
|-----------------------|-------------|
| Végrehajtható osztály      | Adja meg a nevet, amelyet egy olyan üzenetfeldolgozási művelet során használni kíván, amellyel kapcsolatban az osztályt lehívják. |
| Leírás           | Adja meg a végrehajtandó osztály leírását. |
| Végrehajtható osztály neve | Jelöljön ki egy X ++ végrehajtható osztályt. |
| Végrehajtási szint       | Ez a mező automatikusan kerül beállításra, mert az értéke előre meg van határozva a kiválasztott végrehajtható osztályhoz. A mező korlátozza a szintet, amelyen a kapcsolódó értékelés fut. |
| Osztály leírása     | Ez a mező automatikusan kerül beállításra, mert az értéke előre meg van határozva a kiválasztott végrehajtható osztályhoz. |
| Művelettípus           | Ez a mező akkor érhető el, ha az **\[EM\] Végrehajtható osztály művelettípusa** funkció be van kapcsolva a **Szolgáltatáskezelés** munkaterületen. Ebben a mezőben lehet megadni a végrehajtható osztály művelettípusát. Ez a mező pontosabb ellenőrzést biztosít az **Elektronikus üzenetek** lapon az elektronikus üzenethez elérhető következő műveletek felett. |

Előfordulhat, hogy az egyes végrehajtható osztályok kötelező paramétereket tartalmaznak, amelyeket a végrehajtható osztály első lefuttatása előtt meg kell adni. Ezeknek a paramétereknek a beállításához a Művelet panelen válassza a **Paraméterek** lehetőséget. A megjelenő párbeszédpanelen adja meg a mezőket, majd kattintson az **OK** gombra. Fontos, hogy kiválassza az **OK** lehetőséget. Ellenkező esetben a paramétereket nem menti az adatbázisba, és a végrehajtható osztályt nem tudja megfelelően lehívni.

## <a name="populate-records-actions"></a><a id="populate"></a>Rekordok műveletek feltöltése

A rekordfeltöltési műveletek használatával olyan műveleteket állíthat be, amelyek rekordokat adnak az Üzenetelemek táblához azért, hogy az elektronikus üzenetekhez lehessen adni őket. Például, ha az elektronikus üzenetnek vevői számlákat kell jelentenie, be kell állítania a Rekordok feltöltése műveletet, amely a Vevői számla naplója táblában található **Adatforrás** mezőre hivatkozik.

Rekordfeltöltési műveleteket az **Adó** \> **Beállítás** \> **Elektronikus üzenetek** \> **Rekordfeltöltési műveletek** oldalon állíthat be. Hozzon létre egy új rekordot minden művelethez, amelynek rekordokat kell adnia a táblához, és állítsa be az alábbi mezőket.

| Mező       | Leírás |
|-------------|-------------|
| Név        | Adjon nevet a műveletnek, amely a folyamatban rekordokat tölt fel. |
| Leírás | Adja meg a Rekordok feltöltése művelet leírását. |

Az **Adatforrások beállítása** gyorslapon adjon hozzá egy sort minden olyan adatforráshoz, amelyet a folyamathoz használ, és állítsa be a következő mezőket.

| Mező                  | Leírás |
|------------------------|-------------|
| Név                   | Adja meg az adatforrás nevét. |
| Üzenetelem típusa      | Válassza ki azt az üzenetelem-típust, amely akkor használatos, amikor a rekordok létrejönnek az adatforráshoz. |
| Számla típusa           | Válassza ki az a fióktípust, amelyet az adatforrásból származó rekordokhoz szeretne társítani. |
| Fő tábla neve      | Válassza ki az adatforrásként használni kívánt táblát. |
| Dokumentumszám mező  | Válassza ki azt a mezőt, amelyből a rendszer a kiválasztott fő táblában a dokumentumszámot kinyeri. E mező értékét használja a rendszer az üzenetelem **Dokumentumszám** mezőjének értékeként. |
| Dokumentumdátum mező    | Válassza ki azt a mezőt, amelyből a rendszer a kiválasztott fő táblában a dokumentum dátumát kinyeri. E mező értékét használja a rendszer az üzenetelem **Üzenetelem dátuma** mezőjének értékeként. |
| Dokumentumszámla mező | Válassza ki azt a mezőt, amelyből a rendszer a kiválasztott fő táblában a dokumentumfiókot kinyeri. E mező értékét használja a rendszer az üzenetelem **Fiókszám** mezőjének értékeként. |
| Cég                | Ez a mező akkor érhető el, ha a **Szolgáltatáskezelés** munkaterületen be van kapcsolva a **Rekordok feltöltése funkció több vállalatot átfedő lekérdezései** beállítás. Ezzel a funkcióval vállalatközi adatforrásokat állíthat be a rekordfeltöltési műveletekhez. Az adatokat több vállalattól is le lehet kérni. |
| Felhasználó lekérdezése             | <p>Ha a rács fölötti **Lekérdezés szerkesztése** lehetőség kiválasztásával beállít egy lekérdezést, és megadja azokat a feltételeket, amelyeket arra a kijelölt fő táblára kell alkalmazni, amelyekből az adatokat betölti a rendszer, akkor ez a jelölőnégyzet automatikusan be van jelölve. Ellenkező esetben az összes rekordot a kiválasztott fő táblából tölti fel a rendszer.</p><p>Ha a **Rekordok feltöltése funkció több vállalatot átfedő lekérdezései** funkció be van kapcsolva a **Funkciókezelés** munkaterületen, és a rekordokat több vállalattól kell összegyűjteni, akkor minden további jogi személyhez adjon hozzá egy olyan sort, amely részt fog venni a jelentésen. Minden új sornál válassza a **Lekérdezés szerkesztése** lehetőséget, és adjon meg egy olyan kapcsolódó feltételt, amely a sor **Vállalat** mezőjében megadott jogi személyre vonatkozik. Ha végzett, az **Adatforrások beállítása** rács minden olyan jogi személy sorait tartalmazni fogja, amelyeknek szerepelniük kell a jelentésen.</p> |

## <a name="web-applications"></a><a id="applications"></a>Webalkalmazások

A webalkalmazás beállításai segítségével beállíthat egy olyan webalkalmazást, amely támogatja az Open Authorization (OAuth) 2.0 szabványt. Az OAuth az a nyitott szabvány, amelynek segítségével a felhasználók saját nevükben „biztonságos delegált hozzáférést” biztosíthatnak az alkalmazásnak anélkül, hogy a hozzáféréshez használt hitelesítési adataikat meg kellene vele osztaniuk. Az engedélyezési folyamatot is elvégezheti, amelyhez kérhet egy ellenőrzőkódot és hozzáférési tokent. A webalkalmazás beállításait az **Adó** \> **Beállítások** \> **Elektronikus üzenetek** \> **Webalkalmazások** oldalon állíthatja be.

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
| A hozzáférési jogkivonat lejár ennyi idő múlva:  | A hozzáférési token lejáratáig fennmaradó idő. Ez a mező automatikusan frissül. | 
| Elfogadás                       | Határozza meg a webes kérelem **Elfogadás** tulajdonságát. Például adja meg a következőt: **application/vnd.hmrc.1.0+json**. |
| Tartalomtípus                 | Határozza meg a tartalom típusát. Például adja meg a következőt: **application/json**. |

Ezenkívül a **Webalkalmazások** Műveleti ablaktábláján a következő gombok találhatók, amelyek támogatják a hitelesítési folyamatot:

- **Engedélyezési kód lekérése** – A webalkalmazás engedélyezését kezdeményezi. Ez a funkció az **Engedélyezési formátum megfeleltetése** mezőben megadott ER-formátumot használja az engedélyezési kérés generálásához.
- **Hozzáférési token lekérése** – A hozzáférési token lekérési folyamatát kezdeményezi.
- **Hozzáférési token frissítése** – Frissíti a hozzáférési tokent. Ez a funkció a **Jogkivonat modell-leképezésének importálása** mezőben megadott ER-funkciót használja a kapott hozzáférési jogkivonattal kapcsolatos információk importálásához.

Amikor egy webalkalmazás hozzáférési tokenjét titkosított formátumban tárolja a rendszer adatbázisában, az használható webes szolgáltatással kapcsolatos kérelmekhez. Biztonsági okokból a hozzáférési jogkivonathoz való hozzáférést azon biztonsági szerepkörökre kell korlátozni, amelyek válaszolhatnak az adott kérelmekre. Ha a biztonsági csoporton kívüli felhasználók próbálnak válaszolni egy kérelemre, hibaüzenetet kapnak, amely tájékoztatja őket, hogy nincs engedélyük a kiválasztott webalkalmazáson keresztüli együttműködésre. Ha szeretné beállítani azokat a biztonsági szerepköröket, amelyeknek rendelkezniük kell hozzáféréssel a hozzáférési jogkivonathoz, használja a **Webalkalmazások** oldal **Biztonsági szerepkörök** gyorslapját. Ha nincsenek megadva egy webalkalmazáshoz biztonsági szerepkörök, akkor csak egy rendszergazda tud együttműködni a webalkalmazás használatával.

A **Műveletnapló** gyorslap minden, a kiválasztott webalkalmazással kapcsolatos művelethez menti a felhasználó adatait, valamint a dátumot és az időpontot.

Egyes webszolgáltatásoknál előfordulhat, hogy különböző fejléceket kell szerepeltetni a kérésben. A rendszergazda beállíthat további fejléceket és azok értékeit a **Kiegészítő fejlécek** gyorslapon, majd a kérések létrehozása során felhasználhatja őket.

## <a name="web-service-settings"></a><a id="settings"></a>Webszolgáltatás-beállítások

A webszolgáltatások beállításainak segítségével beállíthatja a közvetlen adatátvitelt a webszolgáltatáshoz. A webszolgáltatás beállításait az **Adó** \> **Beállítások** \> **Elektronikus üzenetek** \> **Webszolgáltatás-beállítások** oldalon állíthatja be.

Az alábbi táblázat ismerteti a **Webes szolgáltatás beállításai** oldalon elérhető mezőket.

| Mező                          | Leírás |
|--------------------------------|-------------|
| Webes szolgáltatás                    | Adja meg a webes szolgáltatás nevét. |
| Leírás                    | Itt megadhatja a webes szolgáltatás leírását. |
| Internetcím               | <p>Adja meg a webes szolgáltatás internetcímét. Ha egy webalkalmazás van megadva egy webszolgáltatáshoz, és a webszolgáltatás internetcímének meg kell egyeznie a kiválasztott webalkalmazáshoz meghatározott internetcímmel, kattintson az **Alap URL-cím másolása** gombra. A rendszer ezután átmásolja a webalkalmazás alap URL-címét ebbe a mezőbe.</p><p>**Figyelmeztetés:** A harmadik fél által nyújtott szolgáltatások és az itt beállított egyéb szolgáltatások nem követelnek meg tanúsítványt, és előfordulhat, hogy nem felelnek meg a Microsoft adatvédelmi követelményeinek. Át kell tekintenie az egyes szolgáltatások adatvédelmi dokumentációját, valamint együtt kell működnie az egyes szolgáltatókkal, hogy megtudja, milyen szintű megfelelőséget biztosít a szolgáltatás. Ön felelős azért, hogy ezek a szolgáltatások teljesítsék a biztonsági, adatvédelmi és jogi előírásokat. A szolgáltatások használatával járó kockázatot Ön viseli. A Microsoft nem nyújt semmiféle kifejezett jótállást, garanciát vagy feltételt. Erősen ajánljuk, hogy csak olyan szolgáltatásokat használjon, amelyek biztonságos és engedélyezett kapcsolatokat, például HTTPS-t biztosítanak.</p> |
| Diploma                    | Válasszon ki egy korábban beállított Azure Key Vault-tanúsítványt. |
| Webalkalmazás                | Válasszon ki egy korábban beállított webalkalmazást. |
| A válasz típusa – XML        | Állítsa ezt a beállítást **Igen** értékre, ha a választípus XML. |
| Kérelemmetódus                 | Adja meg a kérés metódusát. A HTTP meghatároz egy készlet kérésmetódust, amely jelzi a műveletet, amelyet az adott erőforráshoz el kell végezni. A kérelem metódusa lehet **GET**, **POST**, vagy más HTTP-metódus. |
| Kérelem fejléce                | Adja meg a kérés fejléceit. A kérésfejléc egy olyan HTTP-fejléc, amely HTTP-kérésekben használható. Nem kapcsolódik az üzenet tartalmához. |
| Elfogadás                         | Határozza meg a webes kérelem elfogadási tulajdonságát. |
| Kódolás elfogadása                | Adja me az accept-encoding értékét. Az Accept-Encoding kérés HTTP-fejléce a tartalom kódolását hirdeti, amelyet a kliens is megért. Ez a tartalomkódolás általában egy kompressziós algoritmus. |
| Tartalomtípus                   | Határozza meg a tartalom típusát. A Tartalomtípus entitás HTTP-fejléce jelzi az erőforrás médiatípusát. |
| Sikeres válasz kódja       | Adja meg a HTTP-állapototkódot, amely jelzi, hogy a kérelem sikeres volt. |
| Kérelem fejlécéhez tartozó formátum megfeleltetése | Válassza ki a webes kérelem fejlécének létrehozásához használt ER formátumot. |

## <a name="message-processing-actions"></a><a id="actions"></a>Üzenetfeldolgozási műveletek

Az üzenetfeldolgozási műveletek segítségével műveleteket hozhat létre a folyamataihoz, és beállíthatja paramétereiket. Üzenetfeldolgozási műveleteket az **Adó** \> **Beállítás** \> **Elektronikus üzenetek** \> **Üzenetfeldolgozási műveletek** oldalon állíthat be.

Az alábbi táblázat ismerteti az **Üzenetfeldolgozási műveletek** oldalon elérhető mezőket.

### <a name="general-fasttab"></a>Általános gyorslap

| Mező                                     | Leírás |
|-------------------------------------------|-------------|
| Művelettípus                               | Válassza ki a művelet típusát. A rendelkezésre álló lehetőségekkel kapcsolatos további tudnivalókat lásd az [Üzenetfeldolgozási művelettípusok](#action-types) szakaszban alább. |
| Formátum leképezése                            | Válassza ki, hogy a művelethez milyen ER-formátumot kell lehívni. Ez a mező csak az **Elektronikus jelentéskészítés exportálása**, **Elektronikus jelentéskészítés importálása** és **Elektronikus jelentéskészítés exportálási üzenete** típusokhoz tartozó műveletekhez érhető el. |
| Formátum megfeleltetése az URL-cím elérési útvonalára vonatkozóan               | Válassza ki, hogy a művelethez milyen ER-formátumot kell lehívni. Ennek a formátumnak a segítségével lehet létrehozni az URL-cím elérési útvonalát, amelyet a kiválasztott webkiszolgálóhoz meghatározott alap internetes címhez adnak hozzá. Ez a mező csak a **Webszolgáltatás** típusú műveletekhez érhető el. |
| Üzenetelem típusa                         | Válassza ki a rekordok típusát, amelyhez a műveletet értékelni kell. Ez a mező az **Üzenetelem végrehajtási szint**, **Elektronikus jelentéskészítés exportálása**, **Elektronikus jelentéskészítés importálása** és **Webszolgáltatás** típusokhoz tartozó műveletekhez érhető el, illetve néhány másik típushoz. Ha üresen hagyja ezt a mezőt, minden olyan üzenetelem-típus értékelésre kerül, amely az üzenetfeldolgozáshoz meg van határozva. |
| Végrehajtható osztály                          | Válasszon ki egy meglévő végrehajtható osztálybeállítást. Ez a mező csak az **Üzenetelem-végrehajtási szint** és **Üzenetelem-végrehajtási szint** típusokhoz tartozó műveletekhez érhető el. |
| Rekordok művelet feltöltése                   | Válasszon ki egy meglévő rekordfeltöltési műveletet. Ez a mező csak a **Rekordfeltöltés** típusú műveletekhez érhető el. |
| Webes szolgáltatás                               | Válasszon ki egy meglévő webszolgáltatást. Ez a mező csak a **Webszolgáltatás** típusú műveletekhez érhető el. |
| Fájlnév                                 | Adja meg a fájl nevét, amely a művelet eredményeképp jön létre. Ez a fájl lehet a webkiszolgálótól érkező válasz vagy a létrehozott jelentés. Ez a mező csak a **Webszolgáltatás** és **Elektronikus jelentéskészítés üzenet exportálása** típusú műveletekhez érhető el. |
| Fájlok csatolása a forrásbizonylatokhoz          | Jelölje be ezt a jelölőnégyzetet, ha a generált fájlokat az EM-elemek hivatkozott fő táblájában található rekordokhoz szeretné csatolni. Ez a mező csak az **Elektronikus jelentéskészítés exportálása** és a **Webszolgáltatás** típusú műveletekhez érhető el. |
| Fájlok csatolása elemekhez a kimeneti archívumból | Jelölje be ezt a jelölőnégyzetet, ha a kimeneti archív fájlból különálló XML-fájlokat szeretne kinyerni, és csatolni szeretné őket a megfelelő elektronikusüzenet-elemekhez. Ez a mező csak az **Elektronikus jelentéskészítés exportálása** típusú műveletekhez érhető el. |
| Üzenetelemek száma exportálásonként        | Adja meg, hogy legfeljebb hány üzenetelemet kell egyetlen fájlba (üzenetbe) foglalni. Ez a mező csak az **Elektronikus jelentéskészítés exportálása** típusú műveletekhez érhető el. |
| ER-forrás használata                             | Jelölje be ezt a jelölőnégyzetet, ha ER-forrásparamétereket szeretne használni az importáláshoz. Ellenkező esetben az elektronikus üzenet mellékletét használja a rendszer. Ez a mező csak az **Elektronikus jelentéskészítés importálása** típusú műveletekhez érhető el. |
| Párbeszédpanel megjelenítése                               | Állítsa ezt a beállítást **Igen** értékre, ha a jelentés létrehozása előtt a felhasználónak meg szeretne jeleníteni egy párbeszédablakot. Ez a mező csak az **Elektronikus jelentéskészítés üzenet exportálása** típus műveletekhez érhető el. |

#### <a name="message-processing-action-types"></a><a id="action-types"></a>Üzenetfeldolgozási művelettípusok

A **Művelettípus** mezőben az alábbi lehetőségek éérhetők el:

- **Üzenet létrehozása** – Ennek a művelettípusnak a segítségével a felhasználók manuálisan hozhatnak létre üzeneteket az **Elektronikus üzenet** oldalon. Kiindulási állapotot nem lehet beállítani ilyen típusú művelethez.
- **Rekordok feltöltése** – ezt a művelettípust már be kellett állítani. Társítsa ezt egy rekordfeltöltési művelettel, hogy engedélyezze a művelet feldolgozásban való szerepeltetését. A rendszer feltételezi, hogy ez a művelettípus az üzenetfeldolgozás első műveletéhez (ha nem volt előre létrehozva elektronikus üzenet) vagy olyan művelethez használatos, amely üzenetelemeket ad az olyan üzenetekhez, amelyeket korábban az **Üzenet létrehozása** művelettípussal hoztak létre. Ezért az ilyen típusú műveletek esetén csak az üzenetelemek eredményállapotát lehet beállítani. A kiindulási állapot csak üzenethez állítható be.
- **Üzenet-végrehajtási szint** – Ennek a művelettípusnak a használatával be lehet egy végrehajtható osztályt állítani, amelyet az üzenet szintjén kell értékelni.
- **Üzenetelem-végrehajtási szint** – Ennek a művelettípusnak a használatával be lehet egy végrehajtható osztályt állítani, amelyet az üzenetelem szintjén kell értékelni.
- **Elektronikus jelentéskészítés exportálása** – Ez a művelettípus használható az olyan műveletekhez, amelyeknek jelentést kell létrehozniuk egy exportálási ER-konfiguráció alapján az üzenetelem szintjén.
- **Elektronikus jelentéskészítés exportüzenete** – Ez a művelettípus használható az olyan műveletekhez, amelyeknek jelentést kell létrehozniuk egy exportálási ER-konfiguráció alapján az üzenet szintjén (például ha az üzenetnek nincsenek üzenetelemei).
- **Elektronikus jelentéskészítés importálása** – Ez a művelettípus használható az olyan műveletekhez, amelyeknek jelentést kell létrehozniuk egy importálási ER-konfiguráció alapján.
- **Üzenetszint felhasználói feldolgozás** – Ez a művelettípus használható olyan műveletekhez, amelyek valamilyen manuális felhasználói műveletet feltételeznek az üzenet szintjén. Például a felhasználó frissítheti az üzenetek állapotát.
- **Felhasználói feldolgozás** – Ez a művelettípus használható olyan műveletekhez, amelyek valamilyen manuális felhasználói műveletet feltételeznek az üzenetelem szintjén. Például a felhasználó frissítheti az üzenetelemek állapotát.
- **Webes szolgáltatás** – Ez a művelettípus használható olyan műveletekhez, amelyeknek egy létrehozott jelentést egy webes szolgáltatáshoz kell továbbítaniuk. Ez a művelettípus nem használatos az Olasz beszerzés és az Értékesítési számlakommunikáció jelentéskészítéséhez. Ennél a művelettípusnál az **Üzenetfeldolgozási műveletek** oldalán található a **Vegyes részletek** gyorslap, ahol meghatározhatja a visszaigazolási szöveget. Ez a visszaigazolási szöveg lesz a megjelenítve a felhasználó számára, mielőtt a kéréseket a kiválasztott webszolgáltatásnak küldené a rendszer.
- **Ellenőrzés kérése** – Ezzel a művelettípussal ellenőrzést lehet kérni a kiszolgálótól.

### <a name="initial-statuses-fasttab"></a>Kiindulási állapotok gyorslap

> [!NOTE]
> A **Kiindulási állapotok** gyorslap nem érhető el olyan műveletekhez, amelyeknek kiindulási művelettípusa **Üzenet létrehozása**.

| Mező               | Leírás |
|---------------------|-------------|
| Üzenetelem-állapot | Válassza ki azt az üzenetelem-állapotot, amelyre vonatkozóan a kiválasztott üzenetfeldolgozási műveletet értékelni kell. |
| Leírás         | A kiválasztott üzenetelem-állapot leírása. |

### <a name="result-statuses-fasttab"></a>Eredményállapotok gyorslap

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

## <a name="electronic-message-processing"></a><a id="processing"></a>Elektronikus üzenetek feldolgozása

Az elektronikus üzenetfeldolgozás az EM funkció alapvető koncepciója. Összesíti azokat a műveleteket, amelyeket az elektronikus üzenet esetén értékelni kell. A műveletek összekapcsolása kiindulási állapot és eredményállapot használatával történhet. Másik lehetőségként a **Felhasználó feldolgozás** típusú műveletek önállóan is elindíthatók. Az elektronikus üzenetek feldolgozásának beállításához lépjen az **Adó** \> **Beállítás** \> **Elektronikus üzenetek** \> **Elektronikus üzenetek feldolgozása** oldalra.

A **Művelet** gyorslapon előre meghatározott műveleteket adhat a feldolgozáshoz. Megadhatja, hogy egy műveletet külön kell-e futtatni, vagy a feldolgozás során elindítható. Annak meghatározásához, hogy egy művelet a feldolgozás során csak egy felhasználó által elindítható, állítsa az adott művelet **Futtatás külön** mezőjének értékét **Igen** értékre. Ha egy művelet elindítható azon üzenetek vagy üzenetelemek feldolgozása által is, amelyeket a művelet kezdő állapotaként megadott állapotban szerepelnek, állítsa a **Futtatás külön** mezőt **Nem** értékre. A **Felhasználói művelet** típusű műveletet mindig csak külön szabad futtatni.

Bizonyos esetekben több műveletet kell összesíteni egy sorozatba annak ellenére, hogy az első művelet külön történő futásra van beállítva. Például egy felhasználónak inicializálnia kell a jelentés-előállítást. Azonban a közvetlenül a jelentés létrehozása után el kell küldeni a webszolgáltatásnak, és a webszolgáltatás válaszának tükröződnie kell a rendszerben. Ebben az esetben létrehozhatja a műveletek szétválaszthatatlan sorozatát, amelyeknek mindig együtt kell futniuk. A **Művelet** gyorslapon válassza az **El nem választható sorozat** lehetőséget a rács felett, és hozzon létre egy sorozatot. Ezután az egy sorozatban együtt futtatandó minden egyes műveletnél válassza ki a sorozatot az **El nem választható sorozat** mezőben. Ebben a példában a **Futtatás külön** mezőt az első művelethez **Igen** értékre állíthatja, de a többi műveletnél **Nem** értékre.

Az **Elektronikus jelentéskészítés exportálása** és az **Elektronikus jelentéskészítés üzenet exportálása** típus egy bemeneti paraméterekkel megadott ER-formátumot futtat. Ha az elektronikus üzenetek feldolgozása e két típusba tartozó műveletet tartalmaz, a jelentés létrehozása előtt meg kell adnia a bemeneti paraméterek értékeit. Így a rendszer kötegelten is előállíthatja a jelentést. A rács fölötti **Paraméterek** területen beállíthatja a kiválasztott művelettípus (**Elektronikus jelentéskészítés exportálása** vagy **Elektronikus jelentéskészítés üzenet exportálása**) paramétereit. Jelölje be a **Paraméterek használata** jelölőnégyzetet annál a műveletnél, amelyet a megadott paraméterekkel kötegelten kell futtatni.

Az **Üzenetelem további mezői** gyorslapon adjon hozzá olyan előre meghatározott további mezőket, amelyek az üzenetelemekhez kapcsolódnak. Minden egyes üzenettípushoz kell további mezőket hozzáadnia, amelyekhez a mezők kapcsolódnak. Megadhat egy alapértelmezett értéket, amely a feldolgozás során a további mezőhöz lesz rendelve.

Az **Üzenet további mezői** gyorslapon adjon hozzá olyan előre meghatározott további mezőket, amelyek az üzenetekhez kapcsolódnak. Megadhat egy alapértelmezett értéket, amely a feldolgozás során a további mezőhöz lesz rendelve.

A **Biztonsági szerepkörök** gyorslapon állítson be olyan biztonsági szerepköröket, amelyek meghatározott feldolgozáshoz előre meg vannak határozva a rendszerben. A specifikus szerepkörrel rendelkező felhasználók csak azokat a feldolgozásokat látják, amelyek az adott szerepkörhöz meg vannak határozva.

A **Köteg** gyorslapon állítsa be, hogy a feldolgozás kötegelten történjen. Azt ajánljuk, hogy közvetlenül az **Elektronikus üzenetek** vagy az **Elektronikus üzenetelemek** lapon állítsa be a kötegelt feldolgozást, amikor a Művelet panelen kiválasztja a **Feldolgozás futtatása** lehetőséget.

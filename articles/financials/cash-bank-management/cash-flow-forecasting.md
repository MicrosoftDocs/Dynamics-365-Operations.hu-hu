---
title: "Pénzforgalmi előrejelzés"
description: "Ez a témakör a pénzforgalmi előrejelzések folyamatáról nyújt áttekintést. Azt is elmagyarázza, hogy miként integrálódnak a pénzforgalm előrejelzések a rendszer más moduljaival."
author: saraschi
manager: AnnBe
ms.date: 05/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sarasch
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 75b47611f1c73a3fb771e63dc1dd12cadf8c4b32
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="cash-flow-forecasting"></a>Pénzforgalmi előrejelzés

[!include[banner](../includes/banner.md)]

A készpénzforgalom-előrejelzési eszközökkel elemezheti a közelgő pénzforgalmi és devizakövetelményeket, és így megbecsülheti a vállalat jövőbeli készpénzigényét. A készpénzforgalom előrejelzésének lekéréséhez a következő feladatokat kell végrehajtania:

- Az összes likviditási függő számla azonosítása és listázása. A likviditási számlák a vállalat készpénzes vagy készpénzzel egyenértékű számlái.
- Konfigurálni kell a viselkedést azon tranazakciók előrejelzéseinél, amelyek befolyásolják a vállalat likviditási számláit.

Miután végrehajtotta ezeket a feladatokat, kiszámíthatja és elemezheti a készpénzforgalmat és a hamarosan érkező pénznemkövetelményeket.

## <a name="cash-flow-forecasting-integration"></a>Pénzforgalmi előrejelzés integrációja

A pénzforgalmi jelentések integrálhatók a főkönyvvel, a kötelezettségekkel, a kintlevőségekkel, a költségvetéssel és a készletkezeléssel. Az előrejelzési folyamat a rendszerbe bevitt tranzakciós információkat használja, és a számítási folyamat előrejelzi az egyes tranzakciók várható pénzforgalmi hatását. A következő tranzakciótípusokat veszi figyelembe a rendszer a készpénzforgalom kiszámítása során:

- **Értékesítési rendelések** – A még nem számlázott értékesítési rendelések, valamint a fizikai vagy pénzügyi teljesítésű értékesítések.
- **Beszerzési rendelések** – A még nem számlázott beszerzési rendelések, valamint a fizikai vagy pénzügyi teljesítésű beszerzések.
- **Kinnlevőségek** – Nyitott vevői tranzakciók (eddig kifizetetlen számlák).
- **Kötelezettségek** – Nyitott szállítói tranzakciók (eddig kifizetetlen számlák).
- **Főkönyvi tranzakciók** – Olyan tranzakciók, ahol meg van határozva valamilyen jövőbeni feladás.
- **Költségvetési tételjegyzék-bejegyzések** – Olyan költségvetési tételjegyzék-bejegyzések, amelyek ki lettek választva a pénzforgalmi előrejelzésekhez.
- **Igény-előrejelzések** – A készlet-előrejelzési modell azon sorai, amelyek ki lettek választva a készpénzforgalmi előrejelzésekhez.
- **Ellátási előrejelzések** – A készlet-előrejelzési modell azon sorai, amelyek ki lettek választva a készpénzforgalmi előrejelzésekhez.

Bár nincs közvetlen integráció a projektmenedzseléssel és a könyveléssel, a projekttranzakciók többféleképpen is szerepelhetnek a pénzforgalmi előrejelzésben. A feladott projektszámlákat az előrejelzés tartalmazza a nyitott vevői tranzakciók részeként. A projekt által kezdeményezett értékesítési rendelések és beszerzési rendelések az előrejelzésben nyitott rendelésként szerepelnek a rendszerbe való beírásuk után. Projektelőrejelzéseket át is lehet vinni egy főkönyvi költségvetésmodellbe. Ez a főkönyvi költségvetési modell a költségvetési nyilvántartási bejegyzések részeként szerepel a pénzforgalmi előrejelzésben.

## <a name="configuration"></a>Konfiguráció

A pénzforgalmi előrejelzési folyamat konfigurálásához használja a **Pénzforgalmi előrejelzés beállítása** oldalt. Ezen az oldalon megadhatja az egyes területeken követendő likviditási számlákat és az alapértelmezett előrejelzési viselkedéseket.

### <a name="general-ledger"></a>Főkönyv

Először meg kell adnia, hogy mely likviditási számlákat kell követnie a pénzforgalmi előrejelzésen keresztül. Ezek a likviditási számlák jellemzően olyan fő számlák, amelyek társulnak azokhoz a bankszámlákhoz, amelyek készpénzt fogadnak és osztanak szét. A **Pénzforgalmi előrejelzés beállítása** oldalon, a **Főkönyv** lapon, válassza ki azokat a fő számlákat, melyeket szerepeltetni kíván az előrejelzésben. Ha társul egy bankszámla a fő számlával a **Bankszámla** oldalon, akkor az a **Bankszámla** mezőben jelenik meg.

Beállíthat függő pénzforgalmi előrejelzést egy olyan fő számlához, amelyik egy másik fő számla tranzakcióival közvetlenül összefüggő tranzakciókat tartalmaz. A **Függő számlák** szakasz minden egyes hozzáadott sora létrehoz egy pénzforgalmi előrejelzési mennyiséget egy függő fő számlánál. Ez az összeg a kiválasztott elsődleges fő fiókhoz tartozó pénzforgalom összegének százalékos arányát jelenti.

Először állítsa be a **Fő számla** mezőt arra az elsődleges fő számlára, ahol a tranzakciók várhatóan a kezdetben előfordulnak. Állítsa a **Függő fő számla** mezőt arra a számlára, amelyiket érint a kezdeti tranzakció az elsődleges fő számlánál. Állítson be megfelelő értékeket a sor további mezőiben. A **Százalék** mező értékének módosításával jelezheti az elsődleges fő számlának a függő fő számlára gyakorolt hatását. Az értékesítési vagy beszerzési előrejelzésekhez válasszon olyan értéket a **Fizetési feltételek** mezőben, amely a legtöbb vevőre, illetve szállítóra jellemző. Állítsa a **Feladási típus** mezőt a várható feladási típusra, amely kapcsolódik a pénzforgalmi előrejelzéshez.

### <a name="accounts-payable"></a>Kötelezettségek

A beszerzési előrejelzést a **Pénzforgalmi előrejelzés beállítása** oldal **Kötelezettségek** beállításaival számíthatja ki. Mielőtt konfigurálná a pénzforgalmi előrejelzést a Kötelezettségek számára, be kell állítania a fizetési feltételeket, a szállítói csoportokat és a szállítói feladási profilokat.

A **Beszerzési előrejelzés alapértelmezései** szakaszban kiválaszthatja az alapértelmezett beszerzési viselkedéseket a pénzforgalmi előrejelzésekhez. Három mező határozza meg a pénzbeli hatás időtartamát: **A kézbesítési dátum és a számladátum közötti idő**, a **Fizetési feltételek** és **A számla esedékességének dátuma és a fizetési dátum közötti idő**. Az előrejelzés csak akkor fogja használni a **Fizetési feltételek** mező alapértelmezett értékét, ha nincs megadva egy érték a tranzakciónál. Használjon olyan fizetési feltételt, amely legjobban megfelel a folyamat egyes részére jellemző napok számának.

A **Likviditási számlák befizetésekhez** mező azt a likviditási számlát határozza meg, amelyiket leggyakrabban használnak fizetésekhez. **A pénzforgalmi előrejelzésbe felosztandó összeg százalékos aránya** mező segítségével adható meg, hogy az összegek egy százalékát kell-e használni az előrejelzések során. Hagyja ezt a mezőt üresen, ha a teljes tranzakciós összegeket szerepeltetni szeretné az előrejelzésekben.

Felülírhatja **A számla esedékességének dátuma és a fizetési dátum közötti idő** mező alapértelmezett alapértelmezett beállítását adott szállítói csoportokra vonatkozóan. Az előrejelzés az alapértelmezett értéket fogja használni a **Beszerzési előrejelzés alapértelmezései** szakaszból, hacsak nincs eltérő érték megadva annál a szállítói csoportnál, amely kapcsolódik a tranzakció szállítójához. Az alapértelmezett érték felülírásához válasszon ki egy szállítói csoportot, majd állítsa be az új értéket a **Beszerzési idő** mezőre vonatkozóan.

Felülírhatja a **Likviditási számla** mező értékét az adott szállítói feladási profilokhoz. Az előrejelzés az alapértelmezett értéket fogja használni a **Beszerzési előrejelzés alapértelmezései** szakaszból, hacsak nincs eltérő likviditási számla megadva annál a feladási profilnál, amely kapcsolódik a tranzakció szállítójához. Az alapértelmezett érték felülírásához válasszon ki egy feladási profilt, majd adja meg azt a likviditási számlát, amely várhatóan érintett lesz.

### <a name="accounts-receivable"></a>Kinnlevőségek

Az értékesítési előrejelzést a **Pénzforgalmi előrejelzés beállítása** oldal **Kinnlevőségek** beállításaival számíthatja ki. Mielőtt konfigurálná a pénzforgalmi előrejelzést a Kinnlevőségek számára, be kell állítania a fizetési feltételeket, a vevői csoportokat és a vevői feladási profilokat.

Az **Értékesítési előrejelzés alapértelmezései** szakaszban kiválaszthatja az alapértelmezett értékesítési viselkedéseket a pénzforgalmi előrejelzésekhez. Három mező határozza meg a pénzbeli hatás időtartamát: **A szállítási dátum és a számladátum közötti idő**, a **Fizetési feltételek** és **A számla esedékességének dátuma és a fizetési dátum közötti idő**. Az előrejelzés csak akkor fogja használni a **Fizetési feltételek** mező alapértelmezett értékét, ha nincs megadva egy érték a tranzakciónál. Használjon olyan fizetési feltételt, amely legjobban megfelel a folyamat egyes részére jellemző napok számának. 

A **Likviditási számlák befizetésekhez** mező azt a likviditási számlát határozza meg, amelyiket leggyakrabban használnak fizetésekhez. **A pénzforgalmi előrejelzésbe felosztandó összeg százalékos aránya** mező segítségével adható meg, hogy az összegek egy százalékát kell-e használni az előrejelzések során. Hagyja ezt a mezőt üresen, ha a teljes tranzakciós összegeket szerepeltetni szeretné az előrejelzésekben.

Felülírhatja **A számla esedékességének dátuma és a fizetési dátum közötti idő** mező alapértelmezett alapértelmezett beállítását adott vevőcsoportokra vonatkozóan. Az előrejelzés az alapértelmezett értéket fogja használni az **Értékesítési előrejelzés alapértelmezései** szakaszból, hacsak nincs eltérő érték megadva annál a vevőcsoportnál, amely kapcsolódik a tranzakció vevőjéhez. Az alapértelmezett érték felülírásához válasszon ki egy vevőcsoportot, majd állítsa be az új értéket az **Értékesítési idő** mezőre vonatkozóan.

Felülírhatja a **Likviditási számla** mező értékét az adott vevői feladási profilokhoz. Az előrejelzés az alapértelmezett értéket fogja használni az **Értékesítési előrejelzés alapértelmezései** szakaszból, hacsak nincs eltérő likviditási számla megadva annál a feladási profilnál, amely kapcsolódik a tranzakció vevőjéhez. Az alapértelmezett érték felülírásához válasszon ki egy feladási profilt, majd állítsa be azt a likviditási számlát, amely várhatóan érintett lesz.

### <a name="budgeting"></a>Költségvetés készítése

A pénzforgalmi előrejelzésekben költségvetési modellekből készített költségvetéseket is szerepeltethet. A **Pénzforgalmi előrejelzés beállítása** oldalon, a **Főkönyv** lapon, válassza ki azokat a fő számlákat, melyeket szerepeltetni kíván az előrejelzésben. Alapértelmezés szerint az új költségkeret-bejegyzések szerepelnek az előrejelzésekben, miután a költségvetési modellt bekapcsolta a pénzforgalmi előrejelzéseknél. A pénzforgalmi előrejelzésbe való bekerülés felülírható az egyes költségvetési tételjegyzék-bejegyzéseken.

### <a name="inventory-management"></a>Készletgazdálkodás

A készletkínálati és -keresleti előrejelzések szerepeltethetők a pénzforgalmi előrejelzésekben. A **Pénzforgalmi előrejelzés beállítása** oldalon, a **Készletgazdálkodás** lapon, válassza ki azt az előrejelzési modellt, amelyet szerepeltetni kíván a pénzforgalmi előrejelzésben. A pénzforgalmi előrejelzésbe való bekerülés felülírható az egyes kínálati és keresleti előrejelzési soroknál.

### <a name="calculation"></a>Számítás

Ahhoz, hogy megtekinthesse a készpénzforgalom előrejelzésének elemzését, le kell futtatnia a készpénzforgalom kiszámítási folyamatát. A számítási folyamat előrejelzi a bevitt tranzakciók jövőbeni pénzforgalmi hatásait.

A pénzforgalmi előrejelzés a **Pénzforgalmi előrejelzések kiszámítása** oldalon számítható ki. Kiszámíthatja a teljes pénzforgalmi előrejelzést vagy egy növekményes pénzforgalmi előrejelzést. 

- Az összes pénzforgalmi előrejelzés tranzakcióinak törléséhez és újrakalkulálásához állítsa a **Pénzforgalmi előrejelzés kiszámítási módszere** mezőt **Összesen** értékre. Ezt a megközelítést akkor érdemes használni, ha már régóta nem voltak frissítve a pénzforgalmi előrejelzések. 
- A csak az új tranzakciókra vonatkozó meglévő pénzforgalmi adatok frissítéséhez állítsa a **Pénzforgalmi előrejelzés kiszámítási módszere** mezőt **Új** értékre. Az oldal megjeleníti a dátumot, amikor utoljára futott a pénzforgalmi számítás.

A pénzforgalmi előrejelzéshez kötegelt feldolgozást is használhat. Annak érdekében, hogy garantálja az előrejelzési elemzés rendszeres frissítését, hozzon létre egy ismétlődő kötegelt eljárást a pénzforgalmi előrejelzés kiszámításához.

### <a name="reporting"></a>Jelentés

A pénzforgalmi előrejelzés kiszámítása után frissítenie kell a kapcsolódó entitások adatait az analitikus jelentésekhez. Az **Entitástár** oldalon válassza ki a **LedgerCovLiquidityMeasurement összesített** mértéket, majd kattintson a **Frissítés** elemre.

Két olyan munkaterület található, amelyek tartalmazzák a pénzforgalmi előrejelzési adatokat. Az egyik munkaterület adatai az összes vállalatra vonatkoznak, a másik munkaterület pedig csak az aktuális vállalathoz tartozó adatokat tartalmazza.

A munkaterülethez való hozzáférés minden vállalat számára a **Pénzforgalom összes vállalati munkaterülete – megtekintés** feladaton keresztül történik. A **Készpénzáttekintés – minden vállalat** munkaterület alapértelmezés szerint a következő szerepkörökhöz érhető el:

- Vezérigazgató
- Pénzügyi igazgató
- Pénzügyi ellenőr

A munkaterülethez való hozzáférés a jelenlegi vállalat számára a **Pénzforgalom jelenlegi vállalati munkaterülete – megtekintés** feladaton keresztül történik. A **Készpénzáttekintés – jelenlegi vállalat** munkaterület alapértelmezés szerint a következő szerepkörökhöz érhető el:

- Könyvelő
- Főkönyvelő
- Számviteli felügyelő
- Kötelezettségkezelő vezető
- Kinnlevőség-kezelő

Megtekintheti a pénzforgalmi előrejelzések elemzéseit a rendszer pénznemében a **Készpénzáttekintés – minden vállalat** munkaterületen. A rendszer pénzneme és az elemzéseknél használt rendszerárfolyam-típus a **Rendszerparaméterek** oldalon kerül meghatározásra. Ez a munkaterület áttekintést nyújt a pénzforgalmi előrejelzésről és a bankszámla-egyenlegekről minden vállalat vonatkozásában. A készpénzbeáramlás és -kiáramlás áttekintése áttekintést nyújt a jövőbeli pénzmozgásokról és egyenlegekről a rendszer pénznemében, valamint részletes információkat tartalmaz az előrejelzett tranzakciókra vonatkozóan. Az előrejelzett pénznem egyenlegeit is megjelenítheti.

Megtekintheti a pénzforgalmi előrejelzések elemzéseit a vállalat által meghatározott pénznemben a **Készpénzáttekintés – jelenlegi vállalat** munkaterületen. Az elemzésekhez használt könyvelési pénznem meghatározása a **Főkönyv** oldalon történik. Ez a munkaterület áttekintést nyújt a pénzforgalmi előrejelzésről és a bankszámla-egyenlegekről a jelenlegi vállalat vonatkozásában. A készpénzbeáramlás és -kiáramlás áttekintése áttekintést nyújt a jövőbeli pénzmozgásokról és egyenlegekről a könyvelés pénznemében, valamint részletes információkat tartalmaz az előrejelzett tranzakciókra vonatkozóan. Az előrejelzett pénznem egyenlegeit is megjelenítheti.

Ha további információt szeretne a pénzforgalmi előrejelzések elemzéséről, tekintse meg a Készpénzáttekintés Power BI-tartalmat.

Ezenkívül a következő oldalakon megtekintheti a pénzforgalmi előrejelzési adatokat az adott fiókokhoz, rendelésekhez és cikkekhez:

- **Főkönyvi kivonat**: A **Pénzforgalmi előrejelzések** lehetőségre kattintva megtekintheti a kiválasztott fő számla jövőbeni pénzforgalmait.
- **Minden értékesítési rendelés**: A **Számla** lapon válassza ki a **Pénzforgalmi előrejelzések** lehetőséget, hogy megtekinthesse a kiválasztott értékesítési rendelés pénzforgalomra gyakorolt hatását.
- **Minden beszerzési rendelés**: A **Számla** lapon válassza ki a **Pénzforgalmi előrejelzések** lehetőséget, hogy megtekinthesse a kiválasztott beszerzési rendelés pénzforgalomra gyakorolt hatását.
- **Ellátási előrejelzés**: A **Pénzforgalmi előrejelzések** lehetőségre kattintva megtekintheti a kiválasztott cikk ellátási előrejelzéséhez társított jövőbeni pénzforgalmait.
- **Igény-előrejelzés**: A **Pénzforgalmi előrejelzések** lehetőségre kattintva megtekintheti a kiválasztott cikk igény-előrejelzéséhez társított jövőbeni pénzforgalmait.



---
title: "Dimenzióhierarchia"
description: "Ez a témakör tájékoztatást tartalmaz a dimenzióhierarchiákkal kapcsolatban. Dimenziókészlet-hierarchia segítségével határozza meg a jelentés szerkezetét, a költségirányelveket és a biztonsági beállításokat a költségkönyvelésben."
author: YuyuScheller
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMDimensionHierarchy,
audience: Application User
ms.reviewer: yuyus
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: YuyuScheller
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: dcbab70d2057a2eb252538a51343fa8bae16873d
ms.contentlocale: hu-hu
ms.lasthandoff: 06/20/2017

---

# <a name="dimension-hierarchy"></a>Dimenzióhierarchia

[!include[banner](../includes/banner.md)]

Ez a témakör tájékoztatást tartalmaz a dimenzióhierarchiákkal kapcsolatban. Dimenziókészlet-hierarchia segítségével határozza meg a jelentés szerkezetét, a költségirányelveket és a biztonsági beállításokat a költségkönyvelésben.  

## <a name="overview"></a>Áttekintés

A dimenzióhierarchiákat a Költségkönyvelés különböző helyein használhatja. A dimenzióhierarchia révén megadhatja a következő adatokat:

-  A jelentési struktúra, amely megfelel a vállalat szükségleteinek
-  Költségirányelvek
-  A biztonság beállítása

Íme, egy példa a dimenzióhierarchiára.

![A dimenzióhierarchia egy példája](./media/dimension-hierarchy.png)

A dimenzióhierarchia a következő dimenziótípusokhoz hozható létre:

-  Költségösszetevő-dimenziók
-  Költségobjektum-dimenziók
-  Statisztikai dimenziók

> [!NOTE]
> - Több dimenzióhierarchiát is létrehozhat ugyanarra a dimenzióra, ha más perspektívákra van szükség.
> - A dimenzióhierarchiához csak egy dimenzió társítható.
> - A dimenzióhierarchiáknak korlátlan szintje lehet a struktúrájában. Minden szint elérhető a **Költségkontroll** munkaterületen. Ha jelentéseket készít a Microsoft Excel vagy a Microsoft Power BI segítségével, csak a dimenzióhierarchiák első 15 szintje exportálható. Ez a korlátozás azért létezik, mert mind az Excel, mind a Power BI egy fix sémát igényel.
> - A dimenzióhierarchiák nem dátumfüggők. Ezért a dimenzióhierarchia minden változása azonnal mentésre kerül a rekordban, és nem tudja összehasonlítani a dátum előtti és a dátum utáni állapotot.

## <a name="dimension-hierarchy-type"></a>Dimenzióhierarchia típusa

Új dimenzióhierarchia létrehozásakor meg kell adnia a hierarchia típusát is. Lépjen a **Költségkönyvelés** > **Dimenziók** > **Dimenzióhierarchiák** ponthoz. Kattintson az **Új** lehetőségre, és válasszon Dimenzióhierarchia-típust. A **Dimenzió-kategorizáláshierarchia** vagy a **Dimenzió-osztályozáshierarchia** lehetőséget választhatja.

### <a name="dimension-categorization-hierarchy"></a>Dimenzió-kategorizáláshierarchia

A **Dimenziókategorizálás-hierarchia** típus a jelentésekhez szükséges. Csak a költségösszetevő-dimenziókat támogatja. Ha ezt a típust választja, az alábbi szabályok lesznek érvényesek:

-  Egy dimenziótagot egynél többször lehet társítani a hierarchiaszerkezetben.
-  A költségelem dimenziótagot különböző csomópontokban helyezheti el, ha költségviselkedést rendel hozzá a levélcsomóponthoz.

### <a name="dimension-classification-hierarchy"></a>Dimenzió-osztályozáshierarchia

A **Dimenzióosztályozás-hierarchia** típus a szabályokhoz és a jelentésekhez szükséges. Támogatja az összes dimenziót, például költségobjektumokat, költségelemeket és statisztikai dimenziókat. Ha ezt a típust választja ki, egy dimenziótagot egyszer lehet társítani a hierarchiaszerkezetben.

## <a name="create-and-maintain-a-dimension-hierarchy"></a>Dimenzióhierarchia létrehozása és karbantartása

A dimenzióhierarchiát olyan fastruktúrának hozzák létre, amely csomópont- és levélcsomópont-kapcsolatokat tartalmaz.

-  A csomópontnak 1:_n_ alcsomópontja lehet.
-  A csomóponthoz nem lehet hozzárendelni mind alcsomópontot, mind levélcsomópontot.
-  A levélcsomópont csak a hierarchia legalacsonyabb szintjén rendelhető hozzá.

### <a name="example"></a>Példa

Egy kis cég a következő szervezeti struktúrával rendelkezik, ahol a Pénzügy és a Humán erőforrások az Adminisztráció alatt állnak, a Szerelés és a Csomagolás pedig a Termelés részlegei.

![Példa szervezeti felépítésre](./media/dimension-hierarchy-org.png)

A költségobjektum dimenziója a szervezet összes költségközpontját jelenti.

- Költségobjektum dimenziója
    - Költséghelyek

Itt állítható be a költségobjektum dimenziója, amely a szervezet összes költségközpontjára jellemző.

| Költséghelyek | Leírás |
|--------------|-------------|
| CC001        | HR          |
| CC002        | Pénzügy     |
| CC003        | Adó         |
| CC007        | AR/AP       |
| CC005        | Szerelvény    |
| CC006        | Csomagolás   |

A költségelem dimenziója a szervezet összes költségelemét jelenti.

- Költségösszetevő-dimenzió
    - Költségösszetevők

Itt állítható be a költségösszetevő dimenziója, amely a szervezet összes költségösszetevőjére jellemző.

| Költségösszetevők | Leírás |
|---------------|-------------|
| 10001         | Villamos energia |
| 10010         | Takarítás    |
| 10011         | Fűtés     |
| 40001         | ELÁBÉ        |

A szervezeti jelentési követelményeket teljesítő dimenziók hierarchiája az alábbiak szerint állítható be.

**Dimenzióhierarchia részletei**

| Dimenzióhierarchia neve | Dimenzió    | Dimenzióhierarchia típus neve      | Hozzáférési lista hierarchia |
|--------------------------|--------------|------------------------------------|-----------------------|
| Szervezet             | Költséghelyek | Dimenzió-osztályozáshierarchia | Nincs                    |

A jelentések dimenzióhierarchiája az alábbiak szerint állítható be.

|                   | Dimenziótag tartományok   |                         |
|-------------------|---------------------------|-------------------------|
| **Csomópontok**         | **Forrásdimenzió-tag** | **Céldimenziótag** |
| Szervezet      |                           |                         |
| &nbsp;&nbsp;Rendszergazda         |                           |                         |
|&nbsp;&nbsp;&nbsp;&nbsp;Pénzügy   | CC002                     | CC003                   |
|                   | CC007                     | CC007                   |
| &nbsp;&nbsp;&nbsp;&nbsp;HR        | CC001                     | CC001                   |
| &nbsp;&nbsp;Termelés    |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Csomagolás | CC005                     | CC005                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Szerelvény  | CC006                     | CC006                   |

A szervezeti jelentési követelményeket teljesítő dimenziók hierarchiája az alábbiak szerint állítható be.

**Dimenzióhierarchia részletei**

| Dimenzióhierarchia neve | Dimenzió     | Dimenzióhierarchia típus neve      |
|--------------------------|---------------|------------------------------------|
| Költség működése            | Költségösszetevők | Dimenzió-osztályozáshierarchia |

Az irányelv dimenzióhierarchiája az alábbiak szerint állítható be.

|                   | Dimenziótag tartományok   |                         |
|-------------------|---------------------------|-------------------------|
| **Csomópontok**         | **Forrásdimenzió-tag** | **Céldimenziótag** |
| Költség működése     |                           |                         |
| &nbsp;&nbsp;Fix költség    | 10001                     | 10011                   |
|&nbsp;&nbsp;Változó költség | 40001                     | 40010                   |

> [!NOTE]
> A **Dimenziótag-tartományok** alatt egy csomópont 1:_n_ dimenziótagtartományt tartalmazhat. Dimenziótag-azonosítókat illeszthet be, amelyek még nem léteznek dimenziótagokként. Ezzel a módszerrel a hierarchia rugalmas lesz a jövőben.  

### <a name="copy-a-hierarchy"></a>Hierarchia másolása

Új dimenzióhierarchia kiindulási pontjaként bemásolhatja az aktuális dimenzióhierarchiát. Ez a megközelítés akkor lehet hasznos, ha össze szeretné hasonlítani,az új dimenzióhierarchiát a korábbi dimenzióhierarchiával.

### <a name="rearrange-nodes-in-a-hierarchy"></a>A csomópontok átrendezése egy hierarchiában

A csomópontot felfelé és lefelé mozgathatja az aktuális szinten a struktúrában. Ily módon átrendezheti a csomópontok sorrendjét a **Költségkontroll** munkaterület jelentéseihez.

A csomópontot a hierarchiában lévő új helyre mozgatja a célcsomópont kiválasztásával. Kétféle módon lehet mozgatni egy csomópontot:

- **Áthelyezés alá** – a kiválasztott csomópont áthelyezése a hierarchia aktuális helyéről, és szúrja be a kijelölt célcsomópont **alá**.
- **Áthelyezés mögé** – a kiválasztott csomópont áthelyezése a hierarchia aktuális helyéről, és szúrja be a kijelölt célcsomópont **mögé** a saját hierarchiaszintjén.

> [!NOTE] 
> A csomópontok sorrendjét nem tartja fenn, amikor adatokat exportál Excelbe vagy Power BI-be, mert ezek az eszközök alapértelmezés szerint alfanumerikus rendezést használnak. A sorrendet manuálisan rendezheti.

## <a name="define-dimension-hierarchies-for-reporting"></a>A jelentések dimenzióhierarchiája az alábbiak szerint állítható be.

A dimenzióhierarchiák a jelentéseknél fontosak. Lehetővé teszik, hogy meghatározza az egyedi szervezetnek megfelelő struktúrát. A dimenziók hierarchiájának csomópontján végrehajtott összesítések lehetővé teszik, hogy a szervezet bármely szintjén az érdekelt felek bármely szinten láthassák az adatokat.

A dimenzióhierarchiák a következő jelentéskészítő eszközöknél érhetők el. Ez a megközelítés segíti a jelentéstételi struktúra következetességét.

- **Költségkontroll** munkaterület (a kliensben):

    - A konfiguráció szabályozza.

- **Költségkontroll** munkaterület (a mobilalkalmazásban):

    - A konfiguráció szabályozza.

- Excel

    - Lehetőséget kínál arra, hogy exportdefiníció szerint kiválassza a konkrét dimenziók hierarchiáját:

        - Egy költségösszetevő-dimenzióhierarchia (kötelező)
        - Egy költségobjektum-dimenzióhierarchia (opcionális)
        - Egy statisztikai dimenzióhierarchia (opcionális)

- Power BI:

    - Minden dimenzióhierarchia rendelkezésre áll.
    
Ha jelentéseket készít az Excel vagy a Power BI segítségével, csak a dimenzióhierarchiák első 15 szintje exportálható. Ez a korlátozás azért létezik, az Excel és a Power BI egy fix sémát igényel. Ha egy hierarchia több mint 15 szinten van, akkor a további szinteket nem exportálja a rendszer. A normalizált táblázat tartalmaz egy rekordot a hierarchiában lévő minden egyes dimenziótag számára. Ezért automatizált összesítés történik. Ez a viselkedés garantálja, hogy a hierarchiában szereplő 15 rendelkezésre álló szint bármelyik egyenlege még mindig helyes.

A következő példában bemutatjuk, hogyan nézhet ki egy dimenzióhierarchia a jelentések szerkezetében.

| Költségobjektum-dimenzióhierarchia - 1. szint | Költségobjektum-dimenzióhierarchia - 2. szint | Költségobjektum-dimenzióhierarchia - 3. szint | Költségobjektum-dimenzióhierarchia - 4. szint | Költségobjektum-dimenzióhierarchia - 15. szint |
|-------------------------------------------|-------------------------------------------|-------------------------------------------|-------------------------------------------|--------------------------------------------|
| Szervezet                              | Rendszergazda                                     | Pénzügy                                   | CC002                                     |                                            |
| Szervezet                              | Rendszergazda                                     | Pénzügy                                   | CC003                                     |                                            |
| Szervezet                              | Rendszergazda                                     | Pénzügy                                   | CC007                                     |                                            |
| Szervezet                              | Rendszergazda                                     | HR                                        | CC001                                     |                                            |
| Szervezet                              | Termelés                                | Csomagolás                                 | CC005                                     |                                            |
| Szervezet                              | Termelés                                | Szerelvény                                  | CC006                                     |                                            |

### <a name="update-the-dimension-hierarchies-that-are-used-for-reporting"></a>Frissítse a jelentéskészítéshez használt dimenzióhierarchiákat 

Idővel az előzőekben említett jelentési eszközökben használt dimenzióhierarchiákat frissíteni kell. Az ügyfél frissítésével frissítheti a dimenziók hierarchiáját.

- **Költségkontroll** munkaterület (a kliensben)
- **Költségkontroll** munkaterület (a mobilalkalmazásban)

A dimenziók hierarchiáinak frissítései 24 óránként előre gyorsítótárazott munkával kerülnek felvételre. Az exportált adatok frissítése után a frissített dimenzióhierarchiák a következő jelentéskészítő eszközöknél érhetők el:

- Excel
- Power BI

> [!NOTE] 
> A dimenzióhierarchia gyorsítótárának manuális frissítéséhez hozzon létre egy új Excel-exportot az olyan dimenzióhierarchiájához vagy -hierarchiáihoz, amelyeket frissíteni kell.

## <a name="define-dimension-hierarchies-for-cost-policies"></a>Dimenzióhierarchiák beállítása költségirányelvekhez

A költségszámítás több olyan irányelvet tartalmaz, ahol részletes szabályok vannak meghatározva. A következő irányelvekhez egy vagy több dimenzióhierarchiát kell megadnia:

- Költség működése
- Költségfelosztás
- Költségfelosztás
- Költségösszesítés

A dimenzió-hierarchiák egyszerűvé teszik a szabályok létrehozását. Annak elkerülése érdekében, hogy szabályokat kelljen létrehoznia minden egyes dimenziótag számára, használhatja a dimenziótagok összesítését, amelyeket a dimenzióhierarchia szintjei nyújtanak. Ha átfedő szabályok vannak, akkor meg kell határoznia azokat a speciális szabályokat, amelyeket a rendszer figyelembe fog venni, amikor az általános költségek számítását végzi.

### <a name="example-define-a-cost-behavior-policy"></a>Példa: Költségműködési irányelv meghatározása

Új költégviselkedési irányelv jön létre, és megfelelő dimenzióhierarchiák kerülnek hozzárendelésre a házirendhez, ahogy az itt látható.

**Költségműködési irányelv**

| Irányelv neve   | Költségösszetevő dimenzióhierarchia | Költségobjektum dimenzióhierarchia | Könyvelési pénznem |
|---------------|----------------------------------|---------------------------------|---------------------|
| Költség működése | Költség működése                    | Szervezet                    | dollár                 |

**Szabályok**

| Költségösszetevő dimenzióhierarchia-csomópont | Költségobjektum dimenzióhierarchia-csomópont | Rögzített százalék | Rögzített összeg | Érvényesség kezdete | Érvényesség vége |
|---------------------------------------|--------------------------------------|------------------|--------------|------------|----------|
| Fix költség                            | Szervezet                         | 100,00           | 0,00         | 2017/1/1   | Soha    |
| 10001                                 | Szervezet                         | 0,00             | 150,00       | 2017/1/1   | Soha    |
| 10001 (\*)                             | Pénzügy                              |                  | 50,00        | 2017/1/1   | Soha    |
| Költségviselkedés + változó költség (\*\*)   | Szervezet                         | 0,00             | 0,00         | 2017/1/1   | Soha    |

\*A változó költségcsomópont nem kötelező. Ha egy költség nem minősül állandó költségnek, akkor annak változó költségnek kell lennie.

\*\* A 10001 költségelem-tag és az összes költségobjektum-tag kombinációjának részletes szabálya a Pénzügy hierarchiája szintjén található (CC002, CC003, CC007).

Az előző szabályok azt a rugalmasságot mutatják, amelyet a dimenzióhierarchiák biztosítanak. A magas szintű szabályok meghatározásával csökkentheti a karbantartást. Ezután részletes szabályokat határozhat meg, amelyek egy adott üzleti célhoz illeszkednek.

Ha a szabályokban használt dimenzióhierarchiák frissülnek, akkor a rendszer automatikusan továbbítja a frissítéseket.

Ha a szabályok részletességi szintje már nem szükséges, akkor a szabály lejártnak nyilvánítható.

Például a Pénzügy költségobjektum-dimenzióhierarchia csomópontra vonatkozó speciális költségviselkedési szabály már nem szükséges. Ebben az esetben kattintson a **Szabály lejáratának beállítása** lehetőségre a szabály lejáratának beállításához.

| Költségösszetevő dimenzióhierarchia-csomópont | Költségobjektum dimenzióhierarchia-csomópont | Rögzített százalék | Rögzített összeg | Érvényesség kezdete | Érvényesség vége  |
|---------------------------------------|--------------------------------------|------------------|--------------|------------|-----------|
| Fix költség                            | Szervezet                         | 100,00           | 0,00         | 2017/1/1   | Soha     |
| 10001                                 | Szervezet                         | 0,00             | 150,00       | 2017/1/1   | Soha     |
| 10001                                 | Pénzügy                              |                  | 50,00        | 2017/1/1   | 2017/1/20 |
| Költségviselkedés + változó költség        | Szervezet                         | 0,00             | 0,00         | 2017/1/1   | Soha     |

A 2017. január 20-a után kezdődő általános költségekre vonatkozó számítás már nem veszi figyelembe ezt a szabályt.

> [!NOTE] 
> Az **Érvényesség kezdete** és **Érvényesség vége** mezők dátum- és időfüggők. Lejártnak nyilváníthatja a szabályt, és futtathat egy új költségfelmérést ugyanazon a napon.

## <a name="define-dimension-hierarchies-for-security-setup"></a>Dimenzióhierarchiák megadása a biztonsági beállításhoz

A költségelszámolási adatokat minden olyan vezetőnek elérhetővé kell tennie, aki felelős a jelentéstevő egységért. A költségszámítási terminológiában a jelentéskészítő egység költségobjektumként vagy költségobjektumok készleteként jelenik meg.

Lehetséges, hogy minden vezető képes lesz elérni a rendkívül érzékeny üzleti adatokat, például bevételeket és árréseket. Ezért fontos beállítani a biztonságot, hogy a vezetők csak azokat az adatokat lássák, amelyek rájuk vonatkoznak. Az adatbiztonság ellenőrzéséhez határozza meg a dimenziók hierarchiáját.

- A dimenziók hierarchiái csak akkor alkalmazhatók, ha a dimenzióhierarchia referenciáján kiválasztott dimenzióérték költségobjektum-dimenzió.
- A hozzáférésilista-hierarchiában csak egy dimenziós hierarchia engedélyezhető költségobjektum-dimenzió szerint.

**Dimenzióhierarchia részletei**

| Dimenzióhierarchia neve | Dimenzió    | Dimenzióhierarchia típus neve      | Hozzáférési lista hierarchia |
|--------------------------|--------------|------------------------------------|-----------------------|
| Szervezet             | Költséghelyek | Dimenzió-osztályozáshierarchia | **Igen**               |

Egy új **Felhasználók** gyorslap áll rendelkezésre a hierarchiatervezőben. Itt beilleszthet egy vagy több felhasználói azonosítót a hierarchiában lévő minden egyes csomóponthoz.

|                 | Felhasználók            | Dimenziótag tartományok   |                         |
|-----------------|------------------|---------------------------|-------------------------|
| **Csomópontok**       | **Felhasználói azonosító**      | **Forrásdimenzió-tag** | **Céldimenziótag** |
| Szervezet    | Benjamin, Claire |                           |                         |
| &nbsp;&nbsp;Rendszergazda         | Április            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Pénzügy   | Alicia           | CC002                     | CC003                   |
|                 |                  | CC007                     | CC007                   |
| &nbsp;&nbsp;&nbsp;&nbsp;HR        | Anna            | CC001                     | CC001                   |
| &nbsp;&nbsp;Termelés    | Dávid            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Csomagolás | Verebélyi            | CC005                     | CC005                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Szerelvény  | Chris            | CC006                     | CC006                   |

> [!NOTE] 
> A költségkönyvelőket a hierarchia felső szintjéhez kell rendelni, hogy láthassák az összes költségkönyvelési tételt.

A hozzáférési lista hierarchiájának és biztonsági beállításainak engedélyezéséhez lépjen ide: **Költségkönyvelés** > **Beállítás** > **Paraméterek** > **Általános**. Válassza ki a **Költségobjektumdimenzió-tagok megtekintési hozzáférésének engedélyezése** paramétert.

A Hozzáférési lista hierarchiájának beállításait használja a rendszer azoknak az adatoknak az irányítására, amelyek a következő területeken jelennek meg:

- **Költségkontroll** munkaterület (a kliensben):

    - Adatok azokról az űrlapokról, amelyeket a forgatókönyvek részletezésénél használ a rendszer

- **Költségkontroll** munkaterület (a mobilalkalmazásban):

    - Egyenlegek a kártyákon

- Power BI:

    - Adatok, amelyek megjelennek a Power BI ábrázolásaiban
    - Az adatok azon Power BI megjelenítései, amelyek be vannak építve a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition kliensébe.

> [!NOTE] 
> - Ahhoz, hogy a hozzáférési lista hierarchia befolyásolhassa a Power BI adatait, párosítani kell a Hozzáférési lista hierarchiát és a sorszintű biztonságot a Power BI-ben. További információ: [Biztonság beállítása a Költségkönyvelés tartalmi csomagban](/dynamics365/unified-operations/dev-itpro/analytics/setup-security-cost-accounting-content-pack)
> - A hozzáférési lista hierarchiája nem segít az adatok biztonságos Excel-exportjában. Ezért a jelentési eszközt csak olyan költségkönyvelők és vezetők használhatják, akiknek teljes hozzáférésük van az adatok megtekintéséhez.


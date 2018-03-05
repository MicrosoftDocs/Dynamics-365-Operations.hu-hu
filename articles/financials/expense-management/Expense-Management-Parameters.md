---
title: "Költséggazdálkodási paraméterek"
description: "A következő paraméterek határozzák meg a Költséggazdálkodás modul működését."
author: KimANelson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 8ca9e80d6d2b87fcdd10ebb9d32bd0a2b2d15614
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="expense-management-parameters"></a>Költséggazdálkodási paraméterek

[!include[banner](../includes/banner.md)]

-----------------------------

A következő paraméterek a Költséggazdálkodás modul általános működését határozzák meg.

### <a name="general"></a>Általános

| **Mező**                                                | **Leírás**                                                 |
|----------------------------------------------------------|---------------------------------------------------------------------|
| **Az útiköltség szokásos tarifája**                             | Az útiköltséggek kapcsolatos költségek visszatérítési tarifájának megadása. A tarifát a rendszer megsorozza költségeknél megadott kilométerfutással, és kiszámítja az utazási költségnél visszatérítendő összeget.                       |
|**A személyes költségek kifizetése:**                             | Válassza ki, hogy ki felel a hitelkártya-tranzakciók személyesként kategorizált összegeinek megfizetéséért.                                                                                                     |
|**Teljes költségjelentés megjelenítése visszakövetés esetén**               | Jelölje be ezt a lehetőséget, ha a költségjelentést összes költségét meg szeretné jeleníteni olyankor, amikor az eredeti dokumentum részleteit nézi egy olyan utalványnál, amelyet a költségjelentés feladásakor hoztak létre.              |
|**Utazás előzetes engedélyezése kötelező**                 | Válassza ezt az opciót, ha megköveteli, hogy az utazási igényeket benyújtsák és jóváhagyják, mielőtt a munkavállaló költségjelentést küldhetne.                                                                    |
|**Felosztások feladás előtti szerkesztésének engedélyezése**            | Válassza ki, hogy a költségjelentés felosztásai szerkeszthetők legyenek-e a feladás előtt.                                                                                                                 |
|**Költséggazdálkodási alapszabályok kiértékelése**                     | Válassza ki, ha a költségeket kiértékelik annak megállapítására, hogy megsértették-e a költségirányelvek valamelyikét. A költségeket szabályosságát ellenőrizni lehet olyankor, amikor a kiadási tétel be van jegyezve és mentésre kerül, vagy ha a költséget benyújtják jóváhagyásra. A szükséges bevételekre vonatkozó irányelvszabályokat ellenőrizni fogják, amikor a költségsor mentésre kerül.                   |
|**Vállalatközi költségsorok engedélyezése**                         | Válassza ki, hogy engedélyezi-e a költségeket más jogi személyek számára a költségjelentésben.                                                                                                          |
|**A hitelkártyás költségekre vonatkozó árfolyam szerkesztésének engedélyezése** | Jelölje be ezt a lehetőséget, ha engedélyezni szeretné a felhasználónak az átváltási arány szerkesztését az importált hitelkártyaköltségeknél.                                                                        |
|**Megjelenítendő többszintű hierarchiamezők**                  | Válassza ki, hogy melyik jóváhagyói mezők jelenjenek meg olyankor, amikor a költségjelentés munkafolyamat-hozzárendelési típusának beállítása hierarchia, és a hierarchia kiválasztása a költségkeret többszintű jóváhagyási hierarchiájának használatára van beállítva. Ha többszintű jóváhagyási hierarchiát használ a munkafolyamatoknál, akkor a kijelölt mezők megjelennek és szerkeszthetőek a költségjelentésben. |
|**Adja meg az alkalmazott hitelkártyaszámát (2017. júliusi frissítés)**     | Válassza ki, hogy meg lehet-e adni és menteni lehet-e egy 15 vagy 16 karakterből álló számot a **Kártyaazonosító** mezőben, az adott alkalmazott **Hitelkártyák** oldalán.                                                                          |

### <a name="financial"></a>Pénzügyi

| **Mező**                                                            | **Leírás**     |
|----------------------------------------------------------------------|------------------------------------|
|**Főkönyvi napi napló neve**                                         | Válassza ki, hogy milyen nevű főkönyvi naplóba kell feladni a jóváhagyott költségjelentéseket.            |
|**Költségadó-visszaigénylés engedélyezése**                                  | Ezt a beállítást akkor válassza, ha engedélyezni szeretné a költségadó-visszaigénylést az arra jogosult költségeknél. Ez a beállítás nem engedélyezhető, ha az Egyesült Államok áfa- és importadó-szabályainak használata engedélyezve van.      |
|**Készpénzes előlegek azonnali feladása**                                     | Akkor válassza ezt a beállítást, ha fel szeretne adni egy jóváhagyott készpénzes előleget akkor, amikor befejeződik a kifizetés és átvezetés folyamat. Ha ez a lehetőség nincs bejelölve, akkor a kifizetés és átvezetés folyamata fel nem adott főkönyvi naplót hoz létre. |
|**Helyes könyvelési dátum feladás közben**                             | Ezt a beállítást akkor válassza, ha frissíteni szeretné a könyvelési dátumot olyankor, amikor az aktuális időszak költségei várakoztatott vagy lezárt állapotúak. A könyvelés dátuma átáll a következő nyitott időszakra.   |
|**Tranzakciók fizetési módban meghatározott ellenszámla alapján történő csoportosításának engedélyezése.**      | Jelölje be ezt a lehetőséget, ha összesíteni szeretné a költségtranzakciókat egy költségjelentéshez, a költségeknél meghatározott ellenszámla fizetési módja alapján.   
|**Adóval együtt**                                                   | Válassza ezt a lehetőséget, ha azt szeretné, hogy az áfát a költség összege alapértelmezés szerint tartalmazza.             |
|**Kötelezettségvállalások felszabadítása utazásigénylések lezárásakor**            | Jelölje be ezt az opciót, ha a jóváhagyott utazási igény lezárásakor szeretné felszabadítani a kötelezettségvállalásokat.                                                                                   |
|**Utazásigénylés benyújtásának engedélyezése a költségvetés túllépésekor a költségvetésjegyzék és a projektköltségvetés számára** | Ezt a lehetőséget választva engedélyezheti, hogy az alkalmazottak az olyan utazási igényeket beadják jóváhagyásra, amelyek meghaladják a költségvetési nyilvántartásban vagy a projekt megengedett költségvetésében meghatározott összeget.            |
|**Költségjelentés benyújtásának engedélyezése a költségvetés túllépésekor a költségvetésjegyzék és a projektköltségvetés számára**    | Ezt a lehetőséget választva engedélyezheti, hogy az alkalmazottak az olyan költségjelentéseket beadják jóváhagyásra, amelyek meghaladják a költségvetési nyilvántartásban vagy a projekt megengedett költségvetésében meghatározott összeget.                |
|**Költségjelentés jóváhagyásának engedélyezése a költségvetés túllépésekor kizárólag a költségvetésjegyzék számára**                | Jelölje be ezt az opciót, hogy engedélyezhesse a jóváhagyók számára, hogy jóváhagyják a költségregiszterben beállított költségkeretet meghaladó költségjelentéseket.                                                                       |

### <a name="per-diem"></a>Napidíj

| **Mező**                             | **Leírás**             |
|---------------------------------------|--------------------------------------------------------------------------------------|
|**Napidíj minimális órakövetelménye**           | Adja meg azt az alapértelmezett minimális óraszámot, amelyet egy munkavállalónak egy nap alatt kell dolgoznia ahhoz, hogy napidíjat kaphasson az utazáshoz kapcsolódó költségekért.  Ez az érték csak a napidíjszint minimális óraszám mezőjében használtos alapértelmezett értékként.                                                                                      |
|**Étkezés százaléka**                          | Adja meg a napidíj alapértelmezett százalékát az étkezéshez, amelyet az utazással kapcsolatos költségek első és utolsó napján használnak, ha az **Étkezési levonás számításának alapja:** mező beállítása **Étkezéstípus nap szerint** vagy **Étkezések száma naponta**. Az első és utolsó munkanap rövidebb lehet, mint a normál napi munkaidő. Ezért a napidíj összege eltérhet a standard összegtől. Ha a százalékos érték 0, akkor az első és utolsó napi levonás összege 0,00 lesz. |
|**Szálloda százaléka**                        | Írja be a napidíj alapértelmezett százalékát a szállásköltségeknek az utazás első és utolsó napján felhasznált összegeire vonatkozóan. Az első és utolsó munkanap rövidebb lehet, mint a normál napi munkaidő. Ezért a napidíj összege eltérhet a standard összegtől. Ha a százalékos érték 0, akkor az első és utolsó napi levonás összege 0,00 lesz.                                              |
|**Egyéb százalék**                        | Írja be a napidíj alapértelmezett százalékát a járulékos költségeknek az utazás első és utolsó napján felhasznált összegeire vonatkozóan. Az első és utolsó munkanap rövidebb lehet, mint a normál napi munkaidő. Ezért a napidíj összege eltérhet a standard összegtől. Ha a százalékos érték 0, akkor az első és utolsó napi levonás összege 0,00 lesz.                                                                                                     |
|**A reggeli miatti levonás százalékban** | Adja meg azt az összeget, amellyel a napidíj csökken a reggeli miatt. Ha például az alkalmazott díjmentesen kap reggelit, dönthet úgy, hogy tíz százalékkal csökkenti a napidíj összegét.                               |
|**Az ebéd miatti levonás százalékban**    | Adja meg azt az összeget, amellyel a napidíj csökken az ebéd miatt. Ha például az alkalmazott díjmentesen kap ebédet, dönthet úgy, hogy tíz százalékkal csökkenti a napidíj összegét.                                       |
|**A vacsora miatti levonás százalékban**   | Adja meg azt az összeget, amellyel a napidíj csökken a vacsora miatt. Ha például az alkalmazott díjmentesen kap vacsorát, dönthet úgy, hogy tíz százalékkal csökkenti a napidíj összegét.                                     |
|**Étkezési levonás számításának alapja:**         | Válassza ki, hogyan kell a rendszernek kiszámítania a napi étkezés csökkentését, ha kiválasztja, hogy a csökkentés az étkezés típusán alapul-e az utazásnál vagy naponta, illetve ha a csökkentés a napi megengedett étkezések számán alapul.|
|**Napidíj kerekítése**                  | Válassza ki a napidíjak költségeinél használt kerekítés típusát. Ha a normál kerekítést választja, minden 0,50-ig terjedő napidíjat 1,00-ra kerekít a rendszer, és minden olyan napidíjat, amelynek összege 0,50-nél kisebb, 0,00-re kerekít.                                                                                              |
|**Napi kalkuláció alapja**         | Válassza ki, hogy a napidíj összege naptári napon vagy 24 órás időtartamon alapul-e.       |

### <a name="fax-cover-pages"></a>Faxfedőlapok

| **Mező**                      | **Leírás**            |
|--------------------------------|-----------------------------------------------------------------------------|
| **Útmutatás**                   | Adja meg az utasításokat amelyeket az alkalmazottaknak követniük kell a fax fedőlap létrehozásához amelyben elküldik költségjelentéshez kapcsolódó nyugtákat. Kattintson a **Fordítások** gombra olyan nyelvfüggő szöveg beírásához, amely a felhasználó nyelve alapján jelenik meg. |
|**Felhasználóazonosító (Vonalkód adatai)** | Jelölje be ezt a beállítást az alkalmazott egyedi azonosítójának vonalkódban történő tárolásához, amelyet a fax fedőlapjaként használhat.                 |
|**Vonalkód**                      | Válassza ki a vonalkódot, amely a fax fedőlapján is szerepel. A Költséggazdálkodásnál a 39-es és 128-as vonalkódok támogatottak.               |

### <a name="anti-corruption"></a>Korrupcióellenes

| **Mező**                             | **Leírás**      |
|---------------------------------------|------------------------------------------------------------------------|
|**Korrupcióellenes nyilatkozat megjelenítése**   | Jelölje be ezt az opciót a korrupcióellenes szöveg megjelenítéséhez új költségjelentés létrehozásakor. Ezután meg lehet adni bizonyos költségkategóriákat, amelyek megkövetelik, hogy korrupcióellenes igazolást válasszanak ki a költségjelentésben. Például egy kormányzati tisztviselő költségéhez kapcsolódó ajándékkategória megkövetelheti a munkavállalótól, hogy erősítse meg, hogy a költség megfelel a kormányzati tisztviselőkkel kapcsolatos vállalati irányelveknek. |
|**Korrupcióellenes üzenet a benyújtónak** | Adja meg az új költségjelentés létrehozásakor a munkavállaló számára megjelenő szöveget. Kattintson a **Fordítások** gombra olyan nyelvfüggő szöveg beírásához, amely a felhasználó nyelve alapján jelenik meg.         |
|**Korrupcióellenes üzenet a jóváhagyónak**  | Adja meg az új költségjelentés létrehozásakor a jóváhagyó számára megjelenő szöveget. Kattintson a **Fordítások** gombra olyan nyelvfüggő szöveg beírásához, amely a felhasználó nyelve alapján jelenik meg.        |


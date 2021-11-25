---
title: Elektronikus számlázás konfigurálása a Regulatory Configuration Services (RCS) megoldásban
description: Ez a témakör bemutatja, hogy hogyan konfigurálhatja az Elektronikus számlázást a Dynamics 365 Regulatory Configuration Services (RCS) szolgáltatásban.
author: gionoder
ms.date: 11/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 640244612a2a553ec09661635787cb7f8694283b
ms.sourcegitcommit: f4823a97c856e9a9b4ae14116a43c87f9482dd90
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/09/2021
ms.locfileid: "7779670"
---
# <a name="configure-electronic-invoicing-in-regulatory-configuration-services-rcs"></a>Elektronikus számlázás konfigurálása a Regulatory Configuration Services (RCS) megoldásban

[!include [banner](../includes/banner.md)]

Ez a témakör a Dynamics 365 Regulatory Configuration Services (RCS) Elektronikus számlázásnak konfigurációs lehetőségeiről nyújt tájékoztatást.

Az Elektronikus számlázás konfigurációs lehetőségei révén segíti az elektronikus számlákra vonatkozó üzleti és jogi követelményeknek programozás nélkül való megfelelését. És olyan helyzetekben, amikor egy webszolgáltatásnak elektronikusan jóvá kell hagynia az elektronikus számlákat, a konfigurációs képességek segítséget nyújtanak a webszolgáltatással történő üzenetcserével kapcsolatos, kód nélküli követelményeknek is.

## <a name="electronic-reporting"></a>Elektronikus jelentés

Az Elektronikus jelentéskészítés (ER) támogatja az Elektronikus számlázást.

Az adatmodell-hozzárendelések és -formátumok olyan, konfigurálható összetevők, amelyeket az ER modulon keresztül hoztak létre és tartanak karban, és az Elektronikus számlázásban használatosak. Az ER formátumtervező a fájlformátumok létrehozásához és karbantartásához használható eszköz. Az elektronikus számlázási funkciók konfigurálására használatos.

További információkért lásd: [Elektronikus jelentés (ER) – áttekintés](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

## <a name="electronic-invoicing-features"></a>Elektronikus számlázási funkciók

Az elektronikus számlázási funkciók felelősek az elektronikus számlák az Elektronikus számlázáson keresztüli létrehozásáért. Beágyazzák a konfigurációs szabályokat, és felhasználják azokat a Microsoft Dynamics 365 Finance és a Dynamics 365 Supply Chain Management által az Elektronikus számlázásnak és az elektronikus számláknak küldött adatok feldolgozására.

Ez a funkció olyan eseteket is támogat, ahol meg kell adni a fájlformátum-specifikációknak való megfelelést, és a kimenet egy önálló elektronikus fájl. A legtöbb esetben az adóhatóság közzéteszi a fájlformátum-specifikációkat.

Végül a funkciók támogatják az olyan külső webes szolgáltatásokkal történő üzenetváltást, amelyek az adóhatóság vagy valamilyen elismert fél által biztosított szolgáltatásokat, valamint engedélyezési kéréseket vagy jóváhagyási pecsétet tartalmaznak az elektronikus számlán.

## <a name="availability-of-electronic-invoicing-features"></a>Az elektronikus számlázási funkciók elérhetősége

Az elektronikus számlázási funkciók elérhetősége az országtól vagy területtől függ. Bár egyes szolgáltatások általában elérhetők, mások előnézetben érhetők el.

### <a name="generally-available-features"></a>Általánosan elérhető funkciók

Az alábbi táblázat bemutatja az általánosan elérhető elektronikus számlázási funkciókat.

| Ország/régió | Funkció neve                         | Üzleti dokumentum |
|----------------|--------------------------------------|-------------------|
| Ausztria        | Osztrák elektronikus számlák (AT)    | Értékesítési és projektszámlák |
| Belgium        | Belga elektronikus számla (BE)      | Értékesítési és projektszámlák |
| Brazília         | Brazil NF-e (BR)                  | 55-ös modellű pénzügyi bizonylat, helyesbítő levelek, érvénytelenítések és elvetések |
| Brazília         | Brazil NFS-e ABRASF Curitiba (BR) | Szolgáltatási pénzügyi bizonylatok |
| Brazília         | Brazíliai NF-e import e-mailből (BR) | 55. modell típusú pénzügyi bizonylat |
| Dánia        | Dán elektronikus számla (DK)       | Értékesítési és projektszámlák |
| Egyiptom          | Egyiptomi elektronikus számla (EG)     | Értékesítési és projektszámlák |
| Észtország        | Észt elektronikus számla (EE)     | Értékesítési és projektszámlák |
| Finnország        | Finn elektronikus számla (FI)      | Értékesítési és projektszámlák |
| Franciaország         | Francia elektronikus számla (FR)       | Értékesítési és projektszámlák |
| Németország        | Német elektronikus számla (DE)       | Értékesítési és projektszámlák |
| Olaszország          | FatturaPA (IT)                       | Értékesítési és projektszámlák |
| Hollandia    | Holland elektronikus számla (NL)        | Értékesítési és projektszámlák |
| Norvégia         | Norvég elektronikus számla (NO)    | Értékesítési és projektszámlák |
| Spanyolország          | Spanyol elektronikus számla (ES)      | Értékesítési és projektszámlák |
| Európa         | PEPPOL elektronikus számla            | PEPPOL értékesítési és projektszámlák |
| Európa         | PEPPOL szállítói számla                | PEPPOL import szállítói számlák |
| Szaúd-Arábia   | Szaúd-arábiai elektronikus számla (SA)| Értékesítési és projektszámlák |

### <a name="preview-features"></a>Előnézeti funkciók

Az alábbi táblázat bemutatja az előnézetben jelenleg elérhető elektronikus számlázási funkciókat.

| Ország/régió | Funkció neve                         | Üzleti dokumentum |
|----------------|--------------------------------------|-------------------|
| Mexikó         | Mexican CFDI (MX)                    | Értékesítési számlák, szállítólevelek, készletátvitelek, fizetéskiegészítések és érvénytelenítések |

### <a name="configurable-components-of-electronic-invoicing-features"></a>Az elektronikus számlázási funkciók konfigurálható összetevői

Az elektronikus számlázás funkciói a konfigurálható összetevők következő csoportjaiból állnak:

- **Formátumok**: A formátumok segítségével konfigurálhatja, hogy mit kell az Elektronikus számlázásnak generálnia, amikor egy elektronikus dokumentum elektronikus számlává válik. A formátumok közé tartozik az elektronikus számla formátumkonfigurációja, valamint a kérések és a válaszok küldésére használt fájlok és üzenetek formátuma, amikor egy külső webszolgáltatással való kommunikációra van szükség.
- **Műveletek**: A Műveletek segítségével beállíthatja, hogy hogyan generálja az Elektronikus számlázás a Finance and Supply Chain Management szolgáltatás által küldött elektronikus dokumentum átalakítását elektronikus számlává.
- **Alkalmazhatósági szabályok**: Az alkalmazhatósági szabályok segítségével konfigurálhatja azt a kontextust, amelyet az Elektronikus számlázásnak figyelembe kell vennie az elektronikus számlázási funkció feldolgozásához.
- **Változók**: A változók segítségével konfigurálhatja a konfigurációs logika felépítését. A változók egy adott művelet végrehajtásához értékbemenetkén is működhetnek. Arra is lehetőség van, hogy értékcsereként működjenek a Finance and Supply Chain Management és az Elektronikus számlázás között.
- **Elektronikusdokumentum-modell leképezése**: Az elektronikus dokumentummodellek leképezése lehetővé teszi az ER modell-leképezés konfigurálását. A modell-leképezés meghatározza annak az absztrakt számlának az adatleképezését, amely elektronikus dokumentumok beküldése esetén integrálva van az Elektronikus számlázásba.
- **Számla kontextusmodellje**: A számla kontextusmodellje segítségével konfigurálhatja az ER számla kontextusmodelljét, és megadhatja az elektronikus számlázási funkció kontextusát.
- **Választípusok**: A választípusok segítségével beállíthatja, hogy az Elektronikus számlázásnak mit kell frissítenie a Finance and Supply Chain Management modulban az elektronikus számlafeldolgozás eredményeként.

### <a name="formats"></a>Formátumok

A következő listák megjeleníti az elektronikus számlázási funkciókhoz elérhető ER-formátumkonfigurációkat.

#### <a name="austrian-at-electronic-invoices-sales-and-project-invoices-for-austria"></a>Osztrák (AT) elektronikus számlák: értékesítési és projektszámlák Ausztria számára

- OIOUBL Értékesítési számla
- OIOUBL Projektszámla
- OIOUBL Értékesítési jóváírás
- OIOUBL Projektjóváírás

#### <a name="belgian-be-electronic-invoice-sales-and-project-invoices-for-belgium"></a>Belga (BET) elektronikus számla: értékesítési és projektszámlák Belgium számára

- UBL Értékesítési számla BE
- UBL Projektszámla BE
- UBL Projektjóváírás BE
- UBL Értékesítési jóváírás BE

#### <a name="brazilian-br-nf-e-nf-e-federal-brazil"></a>Brazil (BR) NF-e: NF-e Federal (Brazília)

- NF-e beküldésének exportálási formátuma (BR)
- NF-e helyesbítő levél exportálási formátuma (BR)
- NF-e exportálási formátum érvénytelenítése (BR)
- NF-e exportálási formátum elvetése (BR)

#### <a name="brazilian-nfs-e-br-nfs-e-abrasf-curitiba-city"></a>Brazil NFS-e (BR): NFS-e ABRASF Curitiba város

- NFS-e ABRASF Curitiba (BR)
- NFS-e ABRASF Lekérdezés Curitiba (BR)

#### <a name="danish-dk-electronic-invoice-sales-and-project-invoices-for-denmark"></a>Dán (DK) elektronikus számla: értékesítési és projektszámlák Dánia számára

- OIOUBL Értékesítési számla
- OIOUBL Projektszámla
- OIOUBL Értékesítési jóváírás
- OIOUBL Projektjóváírás

#### <a name="dutch-nl-electronic-invoice-sales-and-project-invoices-for-netherlands"></a>Holland (NL) elektronikus számla: értékesítési és projektszámlák Hollandia számára

- UBL Értékesítési számla NL
- UBL Projektszámla NL
- UBL Projektjóváírás NL
- UBL Értékesítési jóváírás NL

#### <a name="egyptian-eg-electronic-invoice-sales-and-project-invoices-for-egypt"></a>Egyiptomi (EG) elektronikus számla: értékesítési és projektszámlák Egyiptom számára

- Értékesítési számla (EG) (számlázás)
- Projektszámla (EG) (számlázás)

#### <a name="estonian-ee-electronic-invoice-sales-and-project-invoices-for-estonia"></a>Észt (EE) elektronikus számla: értékesítési és projektszámlák Észtország számára

- Értékesítési számla (EE)
- Projektszámla (EE)

#### <a name="finnish-fi-electronic-invoice-sales-and-project-invoices-for-finland"></a>Finn (FI) elektronikus számla: értékesítési és projektszámlák Finnország számára

- Értékesítési számla (FI)
- Projektszámla (FI)

#### <a name="french-fr-electronic-invoice-sales-and-project-invoices-for-france"></a>Francia (FR) elektronikus számla: értékesítési és projektszámlák Franciaország számára

- UBL Értékesítési számla (FR)
- UBL Projektszámla FR
- UBL Projektjóváírás FR
- UBL Értékesítési jóváírás FR

#### <a name="german-de-electronic-invoice-sales-and-project-invoices-for-germany"></a>Német (DE) elektronikus számla: értékesítési és projektszámlák Németország számára

- Értékesítési számla (DE)
- Projektszámla (DE)

#### <a name="italian-it-electronic-invoice-sales-and-project-invoices-for-italy"></a>Olasz (IT) elektronikus számla: értékesítési és projektszámlák Olaszország számára

- Értékesítési számla (IT)
- Projektszámla (IT)

#### <a name="mexican-mx-cfdi-cfdi-for-mexico"></a>Mexikói (MX) CFDI: CFDI Mexikó számára

- CFDI számlaformátum (MX)
- CFDI szállítólevél (MX)
- CFDI készletátvitel (MX)
- CFDI kifizetés formátuma (MX)
- CFDI-számlaérvénytelenítési formátum (MX)

#### <a name="norwegian-no-electronic-invoice-sales-and-project-invoices-for-norway"></a>Norvég (NO) elektronikus számla: értékesítési és projektszámlák Norvégia számára

- OIOUBL Értékesítési számla
- OIOUBL Projektszámla
- OIOUBL Értékesítési jóváírás
- OIOUBL Projektjóváírás

#### <a name="peppol-electronic-invoice-peppol-sales-and-project-invoices"></a>PEPPOL elektronikus számla: PEPPOL értékesítési és projektszámlák

- PEPPOL Értékesítési számla
- PEPPOL Projektszámla
- PEPPOL Értékesítési jóváírás
- PEPPOL Projektjóváírás

#### <a name="spanish-es-electronic-invoice-sales-and-project-invoices-for-spain"></a>Spanyol (ES) elektronikus számla: értékesítési és projektszámlák Spanyolország számára

- Értékesítési számla (ES)
- Projektszámla (ES)

#### <a name="saudi-arabian-sa-electronic-invoice-sales-and-project-invoices-for-saudi-arabia"></a>Szaúd-arábiai elektronikus számla : Szaúd-Arábia értékesítési és projektszámlái

- Értékesítés - e-számla (SA)
- Projekt - e-számla (SA)

Az elektronikus számlázási szolgáltatással azonnal használatba vehető elektronikus jelentéskészítési formátumkonfigurációk mellett saját elektronikus jelentéskészítési formátumkonfigurációkat is létrehozhat. Az elektronikus számlázási funkciókhoz létrehozott formátumkonfigurációk azonban nem támogatják a Finance és a Supply Chain Management tábláira történő közvetlen hivatkozást, illetve a megfelelő metaadatokat. Csak az elektronikus jelentéskészítési modellleképezésre mutató hivatkozások támogatottak.

### <a name="actions"></a>Műveletek

A következő táblázat felsorolja a rendelkezésre álló műveleteket, valamint azt, hogy jelenleg elérhetők-e vagy még az előzetes verzióban vannak.

| Művelet                                        | Leírás                                                                  | Elérhetőség         |
|-----------------------------------------------|------------------------------------------------------------------------------|----------------------|
| Dokumentum átalakítása                            | Az Elektronikus jelentés formátum futtatása a dokumentum átalakításához.                   | Általánosan elérhető  |
| XML-dokumentum aláírása                             | XML-dokumentumok aláírása digitális aláírással.                                   | Általánosan elérhető  |
| JSON-dokumentum aláírása az egyiptomi adóhatóság számára | JSON-dokumentumok aláírása digitális aláírással az egyiptomi adóhatóság számára.       | Általánosan elérhető  |
| Integráció az Egyiptomi ETA-szolgáltatással           | Kommunikáció az egyiptomi adóhatósággal.                                     | Általánosan elérhető  |
| Brazil SEFAZ-szolgáltatás hívása                  | Integráció a Brazil SEFAZ-szolgáltatással a pénzügyi bizonylatok benyújtásához.       | Általánosan elérhető  |
| Mexikói PAC-szolgáltatás hívása                      | Integráció a mexikói PAC-szolgáltatással CFDI beküldéséhez.                      | Előnézetben           |
| Folyamatválasz                              | A webszolgáltatás hívása alapján kapott válasz elemzése.                     | Általánosan elérhető  |
| MS Power Automate használata                         | Integrálható a beépített Microsoft Power Automate-folyamatokkal.                       | Előnézetben           |

### <a name="applicability-rules"></a>Alkalmazhatósági szabályok

Az alkalmazhatósági szabályok az Elektronikus számlázás funkció szintjén meghatározott konfigurálható záradékok. A szabályok úgy konfigurálják, hogy kontextust adjanak az elektronikus számlázás készségnek az Elektronikus számlázásra beállított funkción keresztül.

Ha egy üzleti dokumentumot a Finance vagy a Supply Chain Management elektronikus számlázásra küldenek be, akkor az üzleti dokumentumhoz nem tartozik egyértelmű hivatkozás, amely lehetővé teszi, hogy az Elektronikus számlázási funkciók egy bizonyos elektronikus számlázási funkciót hívjanak meg a beküldés feldolgozásához.

Azonban a megfelelő konfigurálás esetén az üzleti dokumentum tartalmazza azokat a szükséges elemeket, amelyek lehetővé teszik az elektronikus számlázást annak megoldásához, hogy melyik elektronikus számlázási funkciót kell kiválasztani, majd létre kell hozni az elektronikus számlát.

Az alkalmazhatósági szabályok lehetővé teszik, hogy az Elektronikus számlázás lehetővé tegye a pontos elektronikus számlázási funkciók megkeresését, amelyek a benyújtás feldolgozásához használatosak. Ehhez a beküldött üzleti dokumentum tartalmát egyeztetni kell az alkalmazhatósági szabályokban szereplő záradékokkal.

Például az elektronikus számlázáshoz kapcsolódó Alkalmazhatósági szabályokkal rendelkező két elektronikus számlázási funkció az Elektronikus számlázás készségkészletbe kerül.

| Elektronikus számlázási funkció | Alkalmazhatósági szabályok        |
|------------------------------|--------------------------- |
| A                            | <p>Ország = BR</p><p>és</p><p>Jogi személy = BRMF</p>  |
| milliárd                            | <p>Ország = MX</p><p>és</p><p>Jogi személy = MXMF</p>  |

Ha a Finance vagy a Supply Chain Management valamelyik üzleti dokumentumát az Elektronikus számlázás képességkészlethez beküldik, akkor az üzleti dokumentum a következő attribútumokat tartalmazza:

- Ország = BR
- Jogi személy = BRMF

Az Elektronikus számlázás képességkészlet az **A** elektronikus számlázási funkciót választja az elküldés feldolgozásához és az elektronikus számla létrehozásához.

Ugyanez érvényes akkor is, ha az üzleti dokumentum a következő elemeket tartalmazza:

- Ország = MX
- Jogi személy = MXMF

Az elektronikus számla létrehozásához a **B** elektronikus számlázási funkció van kiválasztva.

Az Alkalmazhatósági szabályok konfigurációja nem lehet kétértelmű. Ez azt jelenti, hogy két vagy több elektronikus számlázási funkció nem tartalmazhatja ugyanazt az záradékot, ellenkező esetben nem lesz végrehajtva a kiválasztás. Ha az elektronikus számlázási funkciók ismétlődnek, a kétértelműség elkerülése érdekében használjon további záradékokat, amelyek lehetővé teszik, hogy az elektronikus számlázással meg lehessen különböztetni a két elektronikus számlázási funkciót.

Vegyük például az elektronikus számlázás **C** funkcióját. Ez a funkció az **A** elektronikus számlázási funkció másolata.

| Elektronikus számlázási funkció | Alkalmazhatósági szabályok        |
|------------------------------|--------------------------- |
| A                            | <p>Ország = BR</p><p>és</p><p>Jogi személy = BRMF</p>  |
| K                            | <p>Ország = BR</p><p>és</p><p>Jogi személy = BRMF</p>  |

Ebben a példában a **C** funkció a következőket tartalmazó üzleti dokumentumok benyújtása előtt áll:

- Ország = BR
- Jogi személy = BRMF

Az Elektronikus számlázás képesség nem tudja megkülönböztetni, hogy melyik elektronikus számlázási funkciót kell használni a beküldés feldolgozásához, mivel a beküldött adatok pontosan ugyanazt az záradékot tartalmazzák.

Ahhoz, hogy az Alkalmazhatósági szabályok segítségével meg lehessen különböztetni a két funkciót, egy új záradékot kell hozzáadni az egyik funkcióhoz, hogy az Elektronikus számlázási képességkészlet a megfelelő elektronikus számlázási funkciót válassza ki.

| Elektronikus számlázási funkció | Alkalmazhatósági szabályok        |
|------------------------------|--------------------------- |
| A                            | <p>Ország = BR</p><p>és</p><p>Jogi személy = BRMF</p>  |
| K                            | <p>Ország = BR</p><p>és</p><p>Jogi személy = BRMF</p><p>és</p><p>Modell=55</p>  |

Az összetettebb záradékok létrehozásának támogatása érdekében a következő erőforrások állnak rendelkezésre:

Logikai operátorok:
- És
- Vagy

Kezelőtípusok:
- Equal
- Not equal
- Greater than
- Less than
- Nagyobb vagy egyenlő
- Kisebb vagy egyenlő
- Contains
- Kezdete

Adattípusok:
- Sztring
- Szám
- Logikai
- Dátum
- UUID

A záradékok csoportosításra és a csoportok szétválasztására való képesség.
A példa a következőképpen néz ki.

| Elektronikus számlázási funkció | Alkalmazhatósági szabályok        |
|------------------------------|--------------------------- |
| K                            | <p>Ország = BR</p><p>és</p><p>( Jogi személy = BRMF</p><p>vagy</p><p>Modell=55)</p>  |


## <a name="configuration-providers"></a>Konfigurációszolgáltatók

A konfigurációs szolgáltatók biztosítják az elektronikus számlázási funkciókat és az ER-összetevőiket, például a modell-leképezést, a formátumkonfigurációt és a kontextusmodellt. Közzéteszik a társított Globális adattár elektronikus számlázási funkcióit és ER-összetevőit. Innen más szervezetek is letölthetik őket.

Mielőtt konfigurálja az elektronikus számlázási funkciókat az RCS szolgáltatáson keresztül, konfigurálnia kell saját szervezetét konfigurációszolgáltatóként az **Elektronikus jelentéskészítés** modulban. A konigurációszolgáltatók **Aktív** értékre állításával kapcsolatban tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md) elemet.

## <a name="viewing-electronic-invoicing-features-in-the-global-repository"></a>A Globális adattár elektronikus számlázási funkcióinak megtekintése

Ha tallózással szeretne böngészni egy adott konfigurációszolgáltató Globális adattárában elérhető elektronikus számlázási funkciók között, szinkronizálja a szervezet RCS-példányát. A szinkronizálás befejeződése után a program frissíti az elérhető elektronikus számlázási funkciók listáját.

## <a name="importing-electronic-invoicing-features"></a>Elektronikus számlázási funkciók importálása

Az elektronikus számlázási funkciók használata vagy konfigurálása előtt ezeket importálnia kell a szervezet RCS-példányába. Az importálási művelet létrehozza a funkciók egy helyi példányát, és a rendszer átmásolja a funkciók által használt összes ER-műterméket (például a formátumkonfigurációkat és a modellkonfigurációkat) a szervezet RCS-példányába.

Az elektronikus számlázási funkciók bármelyik konfigurációszolgáltatóból importálhatók.

## <a name="creating-electronic-invoicing-features"></a>Elektronikus számlázási funkciók létrehozása

Létrehozhatja az elektronikus számlázási funkciót az alapoktól, vagy származtathatja egy másik elektronikus számlázási funkcióból.

Ha nulláról kezdve hoz létre elektronikus számlázási funkciót, manuálisan kell hozzáadnia az ER-összetevőket (például a funkcióverzió konfigurációit és más konfigurációkat, például a funkcióverzió beállításait és az alkalmazás beállítását). Amikor egy funkciót egy másik funkcióból származtat, az új funkció az összes konfigurációt az eredetitől örökli. 

## <a name="electronic-invoicing-feature-version"></a>Elektronikus számlázási funkcióverzió

Az elektronikus számlázási funkciók verziószámozva vannak. Új verzió létrehozásakor a verziószám automatikusan nő. Az új verzióhoz meg lehet határozni egy tényleges kezdési dátumot.

Az elektronikus számlázás funkcióverziói egy legfeljebb három állapotú életciklust követnek:

- **Piszkozat** – ha egy funkcióverzió ebben az állapotban van, szerkesztheti annak konfigurációs attribútumait és bármelyik műtermékét (például fájlformátum-konfigurációkat).
- **Befejezés** – ha egy funkcióverzió ilyen állapotban van, azt már közzétették a szervezetéhez társított Globális adattárban. Ezután már nem szerkesztheti a funkcióverziót és egyik ER-összetevőt sem.
- **Közzétéve** – ha egy funkcióverzió ilyen állapotban van, akkor azt közzétették az Elektronikus számlázásban. Ezután már nem szerkesztheti a funkcióverziót és egyik ER-összetevőt sem.

### <a name="feature-configurations"></a>Funkciókonfigurációk

A funkciókonfigurációk az elektronikus számlázási funkciók által használt összes ER-formátumkonfigurációt tartalmazzák. Az elektronikus számlázási funkció által a feldolgozás során használt összes elektronikus fájl a funkció funkciókonfigurációihoz hozzáadott formátumkonfigurációkból jön létre.

A funkciókonfigurációkból elérhető az ER-formátumtervező, amely a formátumkonfigurációk létrehozására használt ER-eszköz.

### <a name="feature-setup"></a>Funkcióbeállítás

A funkcióbeállításokat a funkciókonfigurációkkal együttesen lehet használni. Minden egyes funkcióbeállítás olyan műveleteket, alkalmazhatósági szabályokat és variánsokat ágyaz be, amelyek a várt működést biztosítják, hogy az elektronikus számlázási funkció teljesíteni tudja az elektronikus számlára vonatkozó egyedi követelményt.

### <a name="application-setup"></a>Alkalmazástelepítés

Az alkalmazás beállítását egy korábban létrehozott, csatlakoztatott alkalmazáshoz kell társítani.

Az alkalmazás beállítása révén beállíthatja az elektronikus számlázási funkció azon részét, amit a Finance and Supply Chain Management modulban kell elvégeznie. Az elektronikus számlázás funkciótól függetlenül legalább három konfigurálható összetevő kötelező:

- **Tábla neve** – a Finance and Supply Chain Management modulban szereplő entitás, amely a feladott számlákat tartalmazza, és amelyen az elektronikus számlázási funkció alapul.
- **Kontextus**– az ER-en keresztül konfigurált számla-kontextusmodell neve.
- **Üzleti dokumentum leképezése**– az ER-en keresztül konfigurált számlaleképezési modell neve.

> [!IMPORTANT]
> Az alkalmazás beállításában megadott konfiguráció a Finance and Supply Chain Management eszközben tekinthető meg. Lépjen a **Szervezeti adminisztráció \> Beállítás \> Elektronikus dokumentumparaméter** lehetőségre. Az **Elektronikus dokumentum** lapon a **Telepítés** lehetőséget, majd válassza a **Csatlakoztatott alkalmazás** lehetőséget.

### <a name="deploying-feature-versions"></a>Funkcióverziók telepítése

Az RCS esetében a **Telepítés** parancs használatával tehet közzé elektronikus számlázási funkcióverziót. Válassza a **Telepítés** lehetőséget, majd válasszon a következő beállítások közül a telepítés célhelyének meghatározásához: 

- **Szolgáltatási környezet** – ha a telepítés célja a szolgáltatási környezet, a rendszer közzéteszi az elektronikus számlázási funkcióverziót a szolgáltatási környezetben. Az Elektronikus számlázás ezután készen áll a Finance and Supply Chain Management eszköz által küldött elektronikus dokumentumok fogadására és feldolgozására.
- **Csatlakoztatott alkalmazás** – ha a telepítés célja a csatlakoztatott alkalmazás, akkor az alkalmazás beállítása által megadott konfiguráció a korábban társított Finance and Supply Chain Management-példányba lesz írva.

Csak a **Befejezve** állapotú elektronikus számlázási funkcióverziókat lehet szolgáltatási környezetbe vagy csatlakoztatott alkalmazásba telepíteni.

### <a name="removing-feature-versions"></a>Funkcióverziók eltávolítása

Az RCS-ben az **Eltávolítás** paranccsal távolíthat el egy adott elektronikus számlázási funkcióverziót a szolgáltatási környezetből az Elektronikus számlázásban.

> [!IMPORTANT]
> Az **Eltávolítás** parancs csak szolgáltatási környezetekben működik. Nem távolítja el az elektronikus számlázás funkcióverzióit a kapcsolódó alkalmazásokból.

### <a name="rebasing-electronic-invoicing-features"></a>Elektronikus számlázási funkciók új alapjának megadása

Ha az egyik elektronikus számlázási funkció egy másikból származik, akkor az **Új alap megadása** parancs az eredeti funkcióban bevezetett módosításoknak megfelelő származtatott funkciót frissíti.

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus számlák kibocstása a Finance és Supply Chain Management szolgáltatásokban](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

---
title: Az Elektronikus számlázási bővítmény konfigurálása a Regulatory Configuration Services (RCS) szolgáltatásban
description: Ez a témakör bemutatja, hogy hogyan konfigurálhatja az Elektronikus számlázási bővítményt a Dynamics 365 Regulatory Configuration Services (RCS) szolgáltatásban.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 99fac9a42dc2b180c220612c66fe753d43e5bd7f
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592622"
---
# <a name="configure-the-electronic-invoicing-add-on-in-regulatory-configuration-services-rcs"></a>Az Elektronikus számlázási bővítmény konfigurálása a Regulatory Configuration Services (RCS) szolgáltatásban

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/banner.md)]

Ez a témakör a Dynamics 365 Regulatory Configuration Services (RCS) Elektronikus számlázási bővítményének konfigurációs lehetőségeiről nyújt tájékoztatást.

Az Elektronikus számlázási bővítmény konfigurációs lehetőségei révén segíti az elektronikus számlákra vonatkozó üzleti és jogi követelményeknek programozás nélkül való megfelelését. Az olyan helyzetekben pedig, amikor az elektronikus számlákat elektronikusan egy webes szolgáltatásnak jóvá kell hagynia, a konfigurációs képességek segítséget nyújtanak a webes szolgáltatásokkal történő üzenetváltásban, mindezt programozás nélkül.

## <a name="electronic-reporting"></a>Elektronikus jelentés

Az Elektronikus jelentéskészítés (ER) támogatja az Elektronikus számlázási bővítményt.

Az adatmodell-hozzárendelések és -formátumok olyan, konfigurálható összetevők, amelyeket az ER modulon keresztül hoztak létre és tartanak karban, és az Elektronikus számlázási bővítményben használatosak. Az ER formátumtervező a fájlformátumok létrehozásához és karbantartásához használható eszköz. Az elektronikus számlázási funkciók konfigurálására használatos.

További információkért lásd: [Elektronikus jelentés (ER) – áttekintés](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

## <a name="electronic-invoicing-features"></a>Elektronikus számlázási funkciók

Az elektronikus számlázási funkciók felelősek az elektronikus számlák Elektronikus számlázási bővítményen keresztüli létrehozásáért. Beágyazzák a konfigurációs szabályokat, és felhasználják azokat a Microsoft Dynamics 365 Finance és a Dynamics 365 Supply Chain Management által az Elektronikus számlázási bővítménynek és az elektronikus számláknak küldött adatok feldolgozására.

Ez a funkció olyan eseteket is támogat, ahol meg kell adni a fájlformátum-specifikációknak való megfelelést, és a kimenet egy önálló elektronikus fájl. A legtöbb esetben az adóhatóság közzéteszi a fájlformátum-specifikációkat.

Végül a funkciók támogatják az olyan külső webes szolgáltatásokkal történő üzenetváltást, amelyek az adóhatóság vagy valamilyen elismert fél által biztosított szolgáltatásokat, valamint engedélyezési kéréseket vagy jóváhagyási pecsétet tartalmaznak az elektronikus számlán.

### <a name="availability-of-electronic-invoicing-features"></a>Az elektronikus számlázási funkciók elérhetősége

Az elektronikus számlázási funkciók elérhetősége az országtól vagy területtől függ. Bár egyes szolgáltatások általában elérhetők, mások előnézetben érhetők el.

#### <a name="preview-features"></a>Előnézeti funkciók

Az alábbi táblázat bemutatja az előnézetben jelenleg elérhető elektronikus számlázási funkciókat.

| Ország/régió | Funkció neve                         | Üzleti dokumentum |
|----------------|--------------------------------------|-------------------|
| Ausztria        | Osztrák elektronikus számlák (AT)    | Értékesítési és projektszámlák |
| Belgium        | Belga elektronikus számla (BE)      | Értékesítési és projektszámlák |
| Brazília         | Brazil NF-e (BR)                  | 55-ös modellű pénzügyi bizonylat, helyesbítő levelek, érvénytelenítések és elvetések |
| Brazília         | Brazil NFS-e ABRASF Curitiba (BR) | Szolgáltatási pénzügyi bizonylatok |
| Dánia        | Dán elektronikus számla (DK)       | Értékesítési és projektszámlák |
| Egyiptom          | Egyiptomi elektronikus számla (EG) | Értékesítési és projektszámlák |
| Észtország        | Észt elektronikus számla (EE)     | Értékesítési és projektszámlák |
| Finnország        | Finn elektronikus számla (FI)      | Értékesítési és projektszámlák |
| Franciaország         | Francia elektronikus számla (FR)       | Értékesítési és projektszámlák |
| Németország        | Német elektronikus számla (DE)       | Értékesítési és projektszámlák |
| Olaszország          | FatturaPA (IT)                       | Értékesítési és projektszámlák |
| Mexikó         | Mexican CFDI (MX)                    | Értékesítési számlák, szállítólevelek, készletátvitelek, fizetéskiegészítések és érvénytelenítések |
| Hollandia    | Holland elektronikus számla (NL)        | Értékesítési és projektszámlák |
| Norvégia         | Norvég elektronikus számla (NO)    | Értékesítési és projektszámlák |
| Spanyolország          | Spanyol elektronikus számla (ES)      | Értékesítési és projektszámlák |
| Európa         | PEPPOL elektronikus számla            | PEPPOL értékesítési és projektszámlák |

### <a name="configurable-components-of-electronic-invoicing-features"></a>Az elektronikus számlázási funkciók konfigurálható összetevői

Az elektronikus számlázás funkciói a konfigurálható összetevők következő csoportjaiból állnak:

- **Formátumok** – A formátumok segítségével konfigurálhatja, hogy mit kell az Elektronikus számlázási bővítménynek generálnia, amikor egy elektronikus dokumentum elektronikus számlává válik. A formátumok közé tartozik az elektronikus számla formátumkonfigurációja, valamint a kérések és a válaszok küldésére használt fájlok és üzenetek formátuma, amikor egy külső webszolgáltatással való kommunikációra van szükség.
- **Műveletek** – a Műveletek segítségével beállíthatja, hogy hogyan generálja az Elektronikus számlázási bővítmény a Finance and Supply Chain Management szolgáltatás által küldött elektronikus dokumentum átalakítását elektronikus számlává.
- **Alkalmazhatósági szabályok** – az alkalmazhatósági szabályok segítségével konfigurálhatja azt a kontextust, amelyet az Elektronikus számlázási bővítménynek figyelembe kell vennie az elektronikus számlázási funkciók feldolgozásához.
- **Változók** – a változók segítségével konfigurálhatja a konfigurációs logika felépítését. A változók egy adott művelet végrehajtásához értékbemenetkén is működhetnek. Arra is lehetőség van, hogy értékcsereként működjenek a Finance and Supply Chain Management és az Elektronikus számlázási bővítmény között.
- **Elektronikusdokumentum-modell leképezése** – az elektronikus dokumentummodellek leképezése lehetővé teszi az ER modell-leképezés konfigurálását. A modell-leképezés meghatározza annak az absztrakt számlának az adatleképezését, amely elektronikus dokumentumok beküldése esetén integrálva van az Elektronikus számlázási bővítménybe.
- **Számla kontextusmodellje** – a számla kontextusmodellje segítségével konfigurálhatja az ER számla kontextusmodelljét, és megadhatja az elektronikus számlázási funkciók kontextusát.
- **Választípusok** – a választípusok segítségével beállíthatja, hogy az Elektronikus számlázási bővítménynek mit kell frissítenie a Finance and Supply Chain Management modulban az elektronikus számlafeldolgozás eredményeként.

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

### <a name="actions"></a>Műveletek

A következő táblázat felsorolja a rendelkezésre álló műveleteket, valamint azt, hogy jelenleg elérhetők-e vagy még az előzetes verzióban vannak.

| Művelet                                        | Leírás                                                                  | Elérhetőség         |
|-----------------------------------------------|------------------------------------------------------------------------------|----------------------|
| Dokumentum átalakítása                            | Az Elektronikus jelentés formátum futtatása a dokumentum átalakításához.                   | Általánosan elérhető  |
| XML-dokumentum aláírása                             | XML-dokumentumok aláírása digitális aláírással.                                   | Előnézetben           |
| JSON-dokumentum aláírása az egyiptomi adóhatóság számára | JSON-dokumentumok aláírása digitális aláírással az egyiptomi adóhatóság számára.       | Általánosan elérhető  |
| Integráció az Egyiptomi ETA-szolgáltatással           | Kommunikáció az egyiptomi adóhatósággal.                                     | Általánosan elérhető  |
| Brazil SEFAZ-szolgáltatás hívása                  | Integráció a Brazil SEFAZ-szolgáltatással a pénzügyi bizonylatok benyújtásához.       | Előnézetben           |
| Mexikói PAC-szolgáltatás hívása                      | Integráció a mexikói PAC-szolgáltatással CFDI beküldéséhez.                      | Előnézetben           |
| Folyamatválasz                              | A webszolgáltatás hívása alapján kapott válasz elemzése.                     | Általánosan elérhető  |
| MS Power Automate használata                         | Integrálható a beépített Microsoft Power Automate-folyamatokkal.                       | Előnézetben           |

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
- **Közzétéve** – ha egy funkcióverzió ilyen állapotban van, akkor azt közzétették az Elektronikus számlázási bővítményben. Ezután már nem szerkesztheti a funkcióverziót és egyik ER-összetevőt sem.

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

- **Szolgáltatási környezet** – ha a telepítés célja a szolgáltatási környezet, a rendszer közzéteszi az elektronikus számlázási funkcióverziót a szolgáltatási környezetben. Az Elektronikus számlázási bővítmény ezután készen áll a Finance and Supply Chain Management eszköz által küldött elektronikus dokumentumok fogadására és feldolgozására.
- **Csatlakoztatott alkalmazás** – ha a telepítés célja a csatlakoztatott alkalmazás, akkor az alkalmazás beállítása által megadott konfiguráció a korábban társított Finance and Supply Chain Management-példányba lesz írva.

Csak a **Befejezve** állapotú elektronikus számlázási funkcióverziókat lehet szolgáltatási környezetbe vagy csatlakoztatott alkalmazásba telepíteni.

### <a name="removing-feature-versions"></a>Funkcióverziók eltávolítása

Az RCS-ben az **Eltávolítás** paranccsal távolíthat el egy adott elektronikus számlázási funkcióverziót a szolgáltatási környezetből az Elektronikus számlázási bővítményben.

> [!IMPORTANT]
> Az **Eltávolítás** parancs csak szolgáltatási környezetekben működik. Nem távolítja el az elektronikus számlázás funkcióverzióit a kapcsolódó alkalmazásokból.

### <a name="rebasing-electronic-invoicing-features"></a>Elektronikus számlázási funkciók új alapjának megadása

Ha az egyik elektronikus számlázási funkció egy másikból származik, akkor az **Új alap megadása** parancs az eredeti funkcióban bevezetett módosításoknak megfelelő származtatott funkciót frissíti.

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus számlák kibocstása a Finance és Supply Chain Management szolgáltatásokban](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

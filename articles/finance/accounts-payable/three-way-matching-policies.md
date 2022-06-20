---
title: Háromirányú egyeztetési irányelvek
description: Ez a cikk a háromirányú egyeztetésről nyújt tájékoztatást.
author: abruer
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendInvoicePostingHistory
audience: Application User
ms.reviewer: twheeloc
ms.custom: 2761
ms.assetid: 70f3cb1a-18b7-4474-95ec-28b2410dd8f8
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2d6d98164766e81625bd9eeb9e504e5f0683151e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904930"
---
# <a name="three-way-matching-policies"></a>Háromirányú egyeztetési irányelvek

[!include [banner](../includes/banner.md)]

Ez a cikk a háromirányú egyeztetésről nyújt tájékoztatást.

## <a name="example-three-way-matching-for-items"></a>Példa: Háromirányú egyeztetés, eszközök esetében

**Összegzés:** Ken a Fabrikam nevű jogi személy testületi vezetőségének az irányítója. Ken úgy dönt, hogy minden beszerzési rendelésen alapuló szállítói számlát egyeztetni kell a beszerzési rendelés sorokkal (kétirányú egyeztetés). A tárgyi eszközbeszerzések során, a számlákat egyeztetni kell mind a beszerzési rendeléssel, mind pedig a termék bevételezéssel (háromirányú egyeztetés).

A Fabrikam világszerte számos jogi személlyel és alkalmazottal működik együtt. Ahogy nő a tranzakciók volumene, úgy nőnek az eltérések a számlák és a nyugták között is. Ez az eszközök elszámolását eredményezi. A szállítók számlái kifizetésre kerülnek, azonban a folyamat nem tartalmazza az eltérések megállapítását olyankor, mikor kevesebb eszközt kapunk a rendeltnél vagy mikor egyáltalán nem kapjuk meg a rendelést. A költségeket továbbá az is növeli, hogy az alkalmazottaknak továbbra is szükségük van eszközökre és anyagokra a munkájuk elvégzéséhez. Ken megakar győződni arról, hogy a rendelt termékek leszállításra kerülnek és a Fabrikam dolgozói megkapják eszközeiket. Így hát, Ken kétirányú és háromirányú egyeztetést rendel el a vállalat minden jogi személyéért. A számlaegyeztetés biztosítja, hogy a meg nem kapott vagy eltűnt eszközök problémái lekövetetőek és megoldatóak legyenek. 

Az ebben a példában szereplő számlaegyeztetési irányelvek segítik a következő szerepeknek ezen célok elérését:

-   Ken a Fabrikam vállalat vezetője. Ken segíthet szervezete dolgozóinak felismerni és korrigálni a rendeléssel, átvétellel és az eszközök és szolgáltatások kifizetésével kapcsolatos problémákat.
-   Phyllis és April könyvelők a Fabrikam Egyesült Államokbeli részlegénél a Kötelezettségek osztályon. Ők tartatják be a vállalat irányelveit és biztosítják, hogy a kifizetések csak azután történjenek meg, hogy egyeztetve lettek a beszerzési rendelésekkel, valamint az eszközök és a szolgáltatások nyugtáival.
-   Tony a termelési felügyelő a Fabrikam Egyesült Államokbeli részlegén. Tony és a gyártó személyzet többi tagja teszik lehetővé az eszközrendelések zavartalan lefolyását és ők a felelősek azért is, hogy a személyzet mindent megkapjon ami a munkájukhoz szükséges.

### <a name="prerequisites"></a>Előfeltételek

-   A "Egyeztetési **irányelv"** a jogi személy szintjén háromszintű **egyeztetést állít be**.
-   A "Ve" beállítás **a fejlécegyeztetés automatikus frissítése állapotát** Igen beállításra állítja **a jogi személynél**.
-   A "Kedvezmény" beállítás **·** **a** jogi személy Teljes árak egyeztetése mezőjét Százalék értékre állítja, és 15%-**ot ad meg tűrésszázalékként.**
-   Az egyeztetési házirendet a 1500-as cikk (CNC Milicron Machine **) cikk szintjén a háromrészes egyeztetésre állítja be**. Ez egy eszköz melyen gyártáshoz használnak a Fabrikamnál. Az ehhez a cikkhez tartozó számlák beszerzési rendeléssorokkal vannak egyeztetve az áraknál és termék bevételezésekkel a mennyiségeknél.
-   Tony öt CNC Milicron Gépezetre nyújt be igényt. Alicia (aki beszerzési rendelésekkel dolgozik a Fabrikamnál) beszerzési rendelést ad ki egy Contoso nevű jogi személynek, hogy beszerezze az eszközöket.

    | Cikkszám                 | Mennyiség | Egységár | Nettó összeg | Költségkód        | Költségek értéke |
    |-----------------------------|----------|------------|------------|---------------------|---------------|
    | 1500 – CNC Milicron Gépezet. | 5        | 8,000.00   | 40,000.00  | Szállítás és kezelés | 3,000.00      |

-   Arnie (aki kinnlevőség-adminisztrátor a Contosonál), ellenőrzi az eheti szállítmányokat. Arnie a szállítmányok tranzakcióit választja, hogy kiszámlázhassa a Fabricannak a CNC Milicron Gépezetek kiszállítását. Arnie beszámítja a kezelésért és a szállításért járó költségeket is. A Fabrikam megfogja fontolni, hogy a plusz költség az eszköz alapköltségének része legyen.

### <a name="scenario"></a>Eset

1.  Sammy, a Fabrikam bevételezési osztályának dolgozója, kapja meg az összes gépet amit a Contosotól leszállítottak. Sammy termék bevételezésen szereplő mennyiséghez 5-öt ír. mivel a beszerzési rendelés teljesen megérkezett, a beszerzési rendelés változásai állapotot Teljesítettre állítja.
2.  April, a Fabrikam kötelezettségek koordinátora, belép és érvényesíti a Contoso által kiállított számlát. A következő információkat ellenőrzi:
    -   A háromirányú egyeztetést igénylő eszközök esetén a számlasoron található mennyiséget a kapott mennyiséggel egyezteti. A kapott mennyiség a termék bevételezésen van feltüntetve és egyeztetve van a számlával.
    -   A két vagy Microsoft Dynamics három irányos egyeztetést igénylő cikkek esetén a számlasor árai a Pénzügy 365-ben meghatározott tűréshatáron belül vannak. Ezek a következő típusú áregyeztetéseket jelentik:
        -   Nettó egységár-egyeztetés – A számlasorban szereplő nettó egységár megegyezik a beszerzési rendelésen feltüntetett egységárral. Ebben a példában a nettó ára tolerancia szintje +8%.
        -   Összár egyeztetés – A számlasorban szereplő nettó ár megegyezik a beszerzési rendelésen feltüntetett nettó árral. A tolerancia szint lehet mérték, százalék vagy mérték és százalék. Ebben a példában az összárak tolerancia szintje + 15%.

A Contosotól kapott papíralapú számla a következő információkat tartalmazza.

| Cikk                        | Mennyiség | Egységár | Nettó összeg |
|-----------------------------|----------|------------|------------|
| 1500 – CNC Milicron Gépezet. | 5        | 8,100.00   | 40,500.00  |
| Szállítás és kezelés       |          |            | 4,000.00   |
| Adó                         |          |            | 0,00       |
| Összesen                       |          |            | 44,500.00  |

A számlasor a következő információkat tartalmazza.

| Cikkszám                 | Mennyiség | Egységár | Sor nettó összege | Egyeztetési irányelv    | Termékbevételezések mennyiségének egyeztetése | Áregyeztetés | Teljes ár egyeztetése |
|-----------------------------|----------|------------|-----------------|--------------------|--------------------------------|-------------|-------------------|
| 1500 – CNC Milicron Gépezet. | 5        | 8,100.00   | 40,500.00       | Háromirányú egyeztetés | Megfelelt                         | Megfelelt      | Megfelelt            |

Ez a sor közzé tehető, mivel túl van a számla egyeztetési folyamaton.

## <a name="example-three-way-matching-for-item-and-vendor-combinations"></a>Példa: Háromirányú egyeztetés cikk és szállító kombinációk esetén
Összegzés: Ken a Fabrikam nevű jogi személy testületi vezetőségének az irányítója. Ken úgy dönt, hogy minden beszerzési rendelésen alapuló szállítói számlát egyeztetni kell a beszerzési rendelés sorokkal (kétirányú egyeztetés). Cassie a Fabrikam Malajziai kirendeltségének könyvelője. Ő határozza megy, hogy a bizonyos a kereskedőktől rendelt eszközöknek egyeznie kell mind a beszerzési rendeléssorokkal, mind pedig a termék bevételezési sorokkal (háromirányú egyeztetés). Emellett, megemelheti az egyeztetési irányelvet magasabb egyeztetési szintre a különleges beszerzési rendelések esetében. 

A mennyiség és az összegek alacsonyak és néhány malajziai árus szállítmányaival problémák is voltak. Ezért Cassie bizonyos Malajziai beszerzésű cikkek és azok beszállítóinak ellenőrzési szintjét háromirányú egyeztetésre emelte. 

Az ebben a példában szereplő számlaegyeztetési irányelvek segítik a következő szerepeknek ezen célok elérését:
-   Ken a Fabrikam vállalat vezetője. Ken segíthet szervezete dolgozóinak felismerni és korrigálni a rendeléssel, átvétellel és az eszközök és szolgáltatások kifizetésével kapcsolatos problémákat.
-   Cassie a Fabrikam Malajziai kirendeltségének könyvelője. Ő tartatja be a vállalati irányelveket és biztosítja, hogy a számlák csak azután kerüljenek kifizetésre, hogy egyeztetve lettek a beszerzési rendeléssorokkal és az eszközök és a szolgáltatások termék bevételezéseivel. Növelheti továbbá a háromirányú egyeztetések ellenőrzését egyes cikkek esetén, így biztosítva a műveletek büdzséjének a kézben tartását.

### <a name="prerequisites"></a>Előfeltételek

-   A "Egyeztetési **irányelv"** a jogi személy szintjén a **"Kétes egyeztetés" beállítású**.
-   A "Kedvezmény" beállítás **·** **a** jogi személy Teljes árak egyeztetése mezőjét a Százalék értékre állítja, **a tűrésszázalékot pedig 10%-** **ban adja meg.**
-   Ken az egységnyi ár toleranciát minden eszköznél 2 %-ra állítja be.
-   Az Egyeztetési **irányelv a** PH2500 **cikkre és szállítóra vonatkozó egyeztetési házirendet a cikk-/szállítókombináció szintjén állítja be háromszintű egyeztetésre a Contoso számítógép és szállító számára**.
-   Alicia, a Fabrikam Malajziai részlegének beszerzési rendelési adminisztrátora, három cikkre ad le beszerzési rendelést a Contosonál. Ezt mutatja a következő táblázat. Amikor létrehozza a beszerzési rendelést, felülbírálja azt az egyeztetési házirendet, **amely** szerint az egér háromes sorrendű lesz a kétes mód egyeztetése helyett.

    | Cikkszám           | Mennyiség | Egységár | Nettó összeg | Egyeztetési irányelv (alapértelmezett bejegyzés) | Egyeztetési irányelv (a beszerzési rendelési soron) |
    |-----------------------|----------|------------|------------|---------------------------------|----------------------------------------------|
    | PH2500 – Számítógép     | 2        | 2,500.00   | 5,000.00   | Háromirányú egyeztetés              | Háromirányú egyeztetés                           |
    | MM01 – Vezeték nélküli egér | 2        | 40.00      | 80.00      | Kétirányú egyeztetés                | Háromirányú egyeztetés                           |
    | USB Meghajtó             | 200      | 10,00      | 2,000.00   | Kétirányú egyeztetés                | Kétirányú egyeztetés                             |

### <a name="scenario"></a>Eset

1.  A cikkek érkezése. Sammy, a Fabrikam Malajziai bevételezési osztályának dolgozója, munkáját félbeszakítják és ezért nem adja fel a termék bevételezést azonnal.
2.  April, a Fabrikam kötelezettségek koordinátora, belép és érvényesíti a Contoso által kiállított számlát. A következő információkat ellenőrzi:
    -   A háromirányú egyeztetést igénylő eszközök esetén a számlasoron található mennyiséget a kapott mennyiséggel egyezteti. A kapott mennyiség a termék bevételezésen van feltüntetve és egyeztetve van a számlával.
    -   Azon eszközök esetében, melyek két- vagy háromirányú egyeztetést igényelnek, a számlasoron feltüntetett áraknak az alkalmazás által meghatározott toleranciaszinten belül kell lenniük. Ezek a következő típusú áregyeztetéseket jelentik:
        -   Nettó egységár-egyeztetés – A számlasorban szereplő nettó egységár megegyezik a beszerzési rendelésen feltüntetett egységárral. Ebben a példában a nettó egységár tolerancia szintje +2%.
        -   Összár egyeztetés – A számlasorban szereplő nettó ár megegyezik a beszerzési rendelésen feltüntetett nettó árral. A tolerancia szint lehet mérték, százalék vagy mérték és százalék. Ebben a példában az összárak tolerancia szintje +10%.

A Contosotól kapott papíralapú számla a következő információkat tartalmazza.

| Cikk                  | Mennyiség | Egységár | Nettó összeg |
|-----------------------|----------|------------|------------|
| PH2500 – Számítógép     | 2        | 2,500.00   | 5,000.00   |
| MM01 – Vezeték nélküli egér | 2        | 41.00      | 82.00      |
| USB Meghajtó             | 200      | 10.05      | 2,010.00   |
| Számla teljes összege         |          |            | 7,092.00   |

A számlasor a következő információkat tartalmazza.

| Cikkszám           | Mennyiség | Egységár | Sor nettó összege | Egyeztetési irányelv    | Termékbevételezések mennyiségének egyeztetése | Áregyeztetés | Teljes ár egyeztetése |
|-----------------------|----------|------------|-----------------|--------------------|--------------------------------|-------------|-------------------|
| PH2500 – Számítógép     | 2        | 2,500.00   | 5,000.00        | Háromirányú egyeztetés | Sikertelen                         | Megfelelt      | Megfelelt            |
| MM01 – Vezeték nélküli egér | 2        | 41.00      | 82.00           | Háromirányú egyeztetés | Sikertelen                         | Sikertelen      | Megfelelt            |
| USB Meghajtó             | 200      | 10.05      | 2010.00         | Kétirányú egyeztetés   |                                | Megfelelt      | Megfelelt            |

Vegye figyelembe az alábbiakat:
-   A PH2500 – Számítógép sorában a termék bevételezés mennyiség egyezése oszlopban megjelent egy figyelmeztető ikon, mivel a számlasor nincs egyeztetve a termék bevételezéssel.
-   Az MM01 – Számítógép sorában a termék bevételezés mennyiség egyezése oszlopban megjelent egy figyelmeztető ikon, mivel a számlasor nincs egyeztetve a termék bevételezéssel. Az Egységár egyezés oszlopban megjelent egy figyelmeztető ikon, mert a 2%-os nettó egységár határ túl lett lépve.
-   Az USB meghajtó sorban a termék bevételezés mennyiség egyezése oszlop üres, mivel a kétirányú egyeztetés nem felel meg a számlasor és a termék bevételezés mennységeinek.

Ha a számlaegyeztetési eltérésekkel feladott számlákhoz jóváhagyás szükséges, **·** **ki** kell választani az egyeztetési eltérésekkel való feladás jóváhagyását, mielőtt a számlát fel lehet adni áregyeztetési hibákkal és mennyiségegyeztetési hibákkal. Amennyiben nincs szükség jóváhagyásra és nem jelenik meg hibaüzenet, a számlázási folyamat folytatható.


További tudnivalókért lásd: [Kötelezettségek számlaegyeztete – áttekintés](accounts-payable-invoice-matching.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]

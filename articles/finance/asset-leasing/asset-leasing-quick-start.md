---
title: Eszközlízing – első lépések
description: Ez a témakör az eszközlízing-képességet ismerteti, valamint bemutatja az eszközlízing létrehozásának, valamint a lízingekkel kapcsolatos információk megtekintésének lépéseit.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseLeasingWorkspace
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "4464"
- intro-internal
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-09-24
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 40e2bb78e6a4db51f61f4197a9cd444226e7f71b012468274b85306bb8f185d1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6726134"
---
# <a name="asset-leasing-get-started"></a>Eszközlízing – első lépések

[!include [banner](../includes/banner.md)]

Ez a témakör az eszközlízing-képességet ismerteti, valamint bemutatja az eszközlízing létrehozásának, valamint a lízingekkel kapcsolatos információk megtekintésének lépéseit. A témakör a felhasználói felületen és a dokumentációban használt terminológiát is meghatározza. Az eszközlízing egy speciális modul, amely lehetővé teszi a lízingelt eszközökre vonatkozó pénzügyi tranzakciók kezelését, nyomon követését és automatizálását a Microsoft Dynamics 365 Finance alkalmazásban. Az eszközlízing megfelel a nemzetközi könyvelési szabványoknak (IFRS 16) és az Egyesült Államokban GAAP szabványainak (ASC 842). Az eszközlízing modul rögzíti és dolgozza fel a lízinggel kapcsolatos adatokat, és segítséget nyújt a naplóbejegyzések létrehozásában a lízing életciklusa alatt – a kezdő elszámolástól és a havi naplóbejegyzésektől egészen a lízing értékvesztéséig és lezárásáig. Az eszközlízing modul zökkenőmentesen épül be a Dynamics 365 Finance egyéb összetevőibe, így például a tárgyi eszközökbe, a kötelezettségekbe és a főkönyvbe is.

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a **Funkciókezelés** munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A **Funkciókezelés** munkaterületen keresse meg és válassza ki az **Eszközlízing** funkciót, majd kattintson az **Engedélyezés most** gombra.

A könyvelési szabványokkal kapcsolatos további tudnivalókat lásd az IFRS 16 és az USA GAAP ASC 842 szabványok dokumentációjában.

## <a name="asset-leasing-elements"></a>Tárgyieszköz-lízing elemei
A következő ábra a lízingek üzleti folyamatának fő elemeit mutatja be.

[![Tárgyieszköz-lízing elemei.](./media/overview-01.png)](./media/overview-01.png)

Egy adott lízingelt eszköz a következő fő összetevőket tartalmazza:

- **Lízingszerződés** – A lízingbeadó birtokolja a tárgyi eszközt, és megállapodik a lízingbevevővel abban, hogy egy tárgyi eszközt meghatározott időszakra bérbe ad az időszakra meghatározott lízingdíj megfizetése ellenében. A lízingbeadó és a lízingbevevő között létrejött szerződésen kívül a lízingszerződés olyan ügyviteli döntéseket rögzít, mint például a megújítás gyakorlásának és a tulajdonjog átruházásának a valószínűsége.

- **Lízingszámítás és számviteli standard szerinti minősítés** – A lízingszámítás és -minősítés határozza meg a kezdeti és az azt követő mérés során alkalmazott könyvelési szabványt, valamint a minősítési tesztet, amely meghatározza, hogy milyen típusú a lízing. A lízing lehet pénzügyi lízing, operatív lízing, rövid távú lízing vagy egy alacsony értékű lízing. A rendszer az értékelés és a minősítés céljából kiszámítja a jövőbeli minimális lízingdíjak jelenlegi nettó értékét is.

- **Lízingtranzakciók** – Az eszközlízing támogatja a használatijog-eszköznek kezdeti megjelenítését a mérlegben, valamint a mérlegen szereplő lízingek vagy mérlegen kívüli lízingek későbbi mérését. A kezdeti megjelenítés tranzakció a jövőbeli minimális lízingdíjak jelenlegi nettó értékét méri meg. Ezekkel az adatokkal lehet meghatározni a használatijog-eszköz és a lízingkötelezettség kezdeti értékét, amelyek hatással vannak a szervezet mérlegére. A havi lízingtranzakciók ezt követő mérése a lízingkötelezettséggel kapcsolatos kamat felhalmozódását foglalja magában, amely növeli a lízingkötelezettségét. Ezenkívül a lízingkötelezettséget csökkentő lízingdíjfizetés elszámolását is méri, amelyet ezt követően a lízingbeadónak fizetnek ki. A mérés továbbá magában foglalja a használatijog-eszköz amortizációját is.

  A mérlegen kívüli lízingek esetén a rendszer lineáris lízingköltséget számít arra, amelyik a következők közül kisebb: az eszköz gazdasági élettartama vagy a lízingfutamidő. A lízingkorrekciók az olyan szerződésmódosításokat mérik, mint amilyen a lízing meghosszabbítása vagy kibővítése, illetve az értékvesztési tranzakció, amely a vissza nem igényelhető költségekre vonatkozó használatijog-eszközt veszi alapul.

  Az eszközlízing modul a főkönyvbe épülve gondoskodik arról, hogy minden feladott lízingtranzakcióval frissüljön a számlatükör. Az eszközlízing modul a kötelezettségekbe épül, ezzel lehetőség van a lízingbeadó számláinak a kötelezettségeken belüli nyomon követésére, valamint onnan jövőbeli kifizetéseket végrehajtani. A tárgyi eszközök modulba épülésnek köszönhetően a tárgyi eszközök nyilvántartásában nyomon követheti a lízingeket, valamint olyan használatijog-eszköz tranzakciókat adhat fel a tárgyi eszközök modulból, mint például az eszköz kezdeti megjelenítése, értékcsökkenése és értékvesztése.   

## <a name="asset-leasing-components"></a>Az eszközlízing modul összetevői 
Az eszközlízing modul feltérképezi a lízingadatokat, fizetési ütemezéseket, kezdő és záró dátumokat, valamint a fizetési gyakoriságot. A modul ezenkívül automatizálja a jelenlegi nettó értékkel, a havi lízingdíjfizetésekkel, a kamattal és a lízing amortizációjával kapcsolatos számításokat. A rendszer a konfigurációtól függően lízingminősítési teszteket hajt végre. A rendszer létrehozza és feladja a megfelelő lízingtranzakciókat, amelyek az Ön által követett könyvelési szabvány által meghatározott keretrendszeren alapulnak.

A következő ábra a lízingkönyvet, a lízinget, a számított fizetés ütemtervet, a lízingek és a lízingkönyvek minősítésére használt teszteket, valamint a megfelelő számviteli tranzakciókat mutatja be.

[![Lízing, lízingkönyv és fizetési ütemterv.](./media/overview-02.png)](./media/overview-02.png)

- **Lízingkönyv** – A lízingkönyv tartalmazza a lízingszerződés összes adatát, például a lízingfeltételeket, a valós értéket és a lízingdíjfizetéseket. A modul az Ön által követett könyvelési szabványt, illetve a lízingminősítési teszten figyelembe veendő lízingtípust és annak küszöbértékeit is tartalmazza. A lízingkönyv tartalmazza továbbá a főkönyvben feladott lízingtranzakciókat is. 
  
- **Lízing** – A lízing magában foglalja az eszközlízing alapjául szolgáló eszközlízingadatokat, a lízingadatok forrása pedig a lízingszerződés és az ügyviteli döntés, melyek mind a Dynamics 365 Finance-en kívüli tényezők. Az eszköz valós értéke az az ár, amelyet az értékelés időpontjában végrehajtott tranzakció során az eszközért fizetnének. Ez az érték függhet az eszköz típusától, a piaci feltételektől, valamint az értékelés során figyelembe veendő egyéb feltételektől. Az eszköz valós értékét a program figyelembe veszi a minősítési teszt egyenletében.

- **Eszköz hasznos élettartama** – Ez az eszköznek a lízing kezdő dátumától számolt hasznos élettartamából hátralévő időszakokat jelzi. Az eszköz hasznos élettartamát a program figyelembe veszi a minősítési teszt egyenletében. Ez nem egyezik a tárgyi eszközök modulban meghatározott hasznos élettartammal.

- **Járulékos kamatláb** – Ezt a kamatlábat használja a program a jelenlegi nettó érték kiszámításához. A rendszer a lízingdíjfizetések nettó jelenértékének kiszámításához az implicit kamatlábat fogja használni, ha ezt a lízingadatokban meghatározták. Ha az implicit kamatlábat nem határozták meg, akkor a rendszer a járulékos kamatlábat fogja használni.

- **Annuitás típusa** – Ez a fizetési időszak elején vagy végén esedékes lízingdíjfizetést jelenti. Ez lehet előlegfizetés, illetve esedékes annuitás (a lízingdíjfizetés időszakának kezdetén) vagy rendes annuitás (a lízingdíjfizetés időszakának végén).

  Az első hónap az előlegfizetés tekintetében nulladik időszaknak, míg az első hónap a hátralékok tekintetében első időszaknak minősül.

- **Kamatos kamat intervalluma** – Ez azon időszakok számát jelzi, amelyekben évente kamatos kamat keletkezik. Ez lehet havi (12 időszak évente), negyedéves (4 időszak évente), féléves (2 időszak évente), vagy éves (1 időszak évente). Az időszakok számát a program figyelembe veszi a nettó jelenérték számításánál.

- **Kezdőnap** – Ez az a dátum, amikor a lízingbeadó a lízingbevevő számára használatra elérhetővé teszi a tárgyi eszközt. Az összes lízingszámítás és tranzakció a kezdőnapon fog alapulni. A kezdőnapnak egy időszak kezdetén kell lennie (a hónap első napján) a későbbi számítások pontossága érdekében. A **szerződés aláírásának dátuma** mező segítségével megadhatja a szerződés aláírásának tényleges dátumát.

- **Lízingfutamidő** – A lízingfutamidő hossza hónapokban.

> [!NOTE] 
> A lízingfutamidő meghatározása a fizetési ütemterv soraiban megadott időszakok vagy intervallum alapján történik. A megadott számú intervallumot a program hónapokra váltja át.

- **Fizetési ütemterv sora** – Ez a lízingdíjfizetéseket rögzíti időszakokra bontva. Ez a sor meghatározza azt is, hogy megújítási időszak érvényesítése történik-e, illetve belekerül-e a használatijog-eszköz és a lízingkötelezettség kezdeti értékelésébe. Megadhatja a lízingdíjfizetések kezdő dátumát, valamint a lízing hosszát tükröző intervallumokat, amelyek lehetnek napok, hónapok vagy évek.

- **Fizetési gyakoriság** – Ez azt jelzi, hogy a kifizetés havi, negyedéves, féléves vagy éves ütemezéssel történik-e. A záró dátumot program automatikusan számítja ki a kezdő dátum és a megadott időszakok száma alapján.

- **Fizetési ütemterv** – Ez a lízingdíjfizetések időtartama, a díjfizetések összege, a kamatos kamattal érintett időszakok és az annuitás típusa alapján számított nettó jelenérték.

- **Időszakok** – Ezek azok a lízingidőszakok, amelyek a kamatos kamattal érintett időszakot és az annuitás típusát tükrözik. A kamatos kamat intervalluma határozza meg, hogy az időszakok hogyan kerülnek felosztásra. A következő kamatos kamattal érintett intervallumok állíthatók be:

  - Havi, 12 időszak évente
  - Negyedéves, 4 időszak évente
  - Féléves, 2 időszak évente
  - Éves, 1 időszak évente

Az első időszak a nulladik időszakkal kezdődik, ha az annuitás típusa az esedékes annuitás. Ellenkező esetben az első időszak egyel kezdődik, ha az annuitás típusa a hátralékos kifizetés.

- **Hónapok** – Ez a lízing hosszán túli naptári hónapok számát jelzi. A kifizetés összege a fizetési gyakoriságban meghatározott esedékes összeg. A számított nettó jelenérték az időszakonkénti nettó jelenértéken alapuló lízingdíjfizetés, a kamatos kamattal érintett intervallumok és a járulékos kamatláb.

> [!NOTE] 
> A nettó jelenértéket a program a diszkontált pénzforgalmi egyenlet alapján számítja ki.

- **Könyvek** – Ez egy, az egyes lízingekhez társított előre konfigurált beállítás. A könyv határozza meg a minősítési tesztek alapjául szolgáló alkalmazott könyvelési szabványokat, lízingtípusokat és küszöbértéket. A minősítési tesztek a lízingtípus automatikus meghatározására szolgálnak.

- **Számviteli keretrendszer** – Ez a kiválasztott könyvelési szabványt jeleníti meg, mely lehet akár az IFRS 16, akár az ASC 842. A könyvelési szabvány a lízinghez társított könyvben van megjelölve. A könyvelési szabvány határozza meg a feladási profilban megadott főkönyvi számlákat.

- **Lízingtípusok** – Ez azt jelzi, hogy a két lízingtípus – vagyis a pénzügyi lízing vagy operatív lízing – közül melyiket használja. Pénzügyi lízing esetén a lízingbe adott eszközzel összefüggő kockázatok és hasznok a lízingbevevőre hárulnak át. Operatív lízing esetén a lízingbe adott eszközzel összefüggő kockázatok és hasznok a lízingbeadónál maradnak. A harmadik lehetőség a lízing típusának (pénzügyi vagy operatív) automatizált azonosítása a könyvben meghatározott küszöbértékek alapján. Ezt az automatikus azonosítást a lízing-újraminősítési teszt során hajtja végre a rendszer.

- **Küszöbértékek** – Ezeket a lízingminősítési tesztek során a program annak megállapítására használja, hogy az eszköz a következő kategóriák melyikébe kerüljön:

  - **Lízingfutamidő** – Ez a hasznos élettartam százalékos értéke, amelyet aztán a program a minősítési teszt során alkalmaz. A rendszer akkor minősíti a lízinget pénzügyinek, ha a lízingtípust automatikusra állították, és ha a lízingfutamidő az eszköz hasznos élettartamán túl nagyobb vagy egyenlő az itt meghatározott százalékkal.

  - **Nettó jelenérték** – Ez az eszköz valós értékének százalékos értéke, amelyet aztán a program a minősítési teszt során alkalmaz. A rendszer akkor minősíti a lízinget pénzügyinek, ha a lízingtípust automatikusra állították, és ha a jövőbeli lízingdíjfizetések nettó jelenértéke az eszköz valós értékén túl nagyobb vagy egyenlő az itt meghatározott százalékkal.

  - **Rövid lejáratú lízing** – Ha a lízingfutamidő kisebb vagy egyenlő, mint a megadott érték, a lízinget rövid lejáratúnak minősíti a rendszer.

  - **Alacsony értékű lízing** – Ha az eszköz valós értéke kisebb vagy egyenlő, mint a megadott érték, a lízinget alacsony értékűnek minősíti a rendszer.

  - **Lízingminősítés és -tranzakciók** A lízingminősítés egy olyan automatizált folyamat, amely a lízingeket a könyvekben meghatározott küszöbértékek, valamint egyéb minősítésiteszt-kritériumok alapján beazonosítja, hogy a lízing egy pénzügyi lízingnek, operatív lízingnek, rövid lejáratú lízingnek vagy alacsony értékű lízingnek minősül-e. Ez a művelet annak meghatározására is szolgál, hogy a halasztott bérleti díj folyamata követendő-e.

A minősítési tesztek kiterjednek a tulajdonjog átruházására, a vételi opcióra, a lízingfutamidőre, a Nettó jelenértékre és az egyedi eszközre is. A következő ábra a lízingminősítési teszteket mutatja be.

[![Lízingminősítési tesztek.](./media/overview-03.png)](./media/overview-03.png)

Minden lízingtípus a különböző lízingtranzakciók esetében eltérően kezeli a könyvelést. A tranzakciók magukban foglalják a kezdeti megjelenítést, a kamatráfordítást, az esedékes lízingdíjfizetést és a lízing értékcsökkenését, továbbá a következő könyvelési szabványokon alapulnak (IFRS 16 vagy ASC 842). A főkönyvi számlák meghatározása a lízing feladási profilja alatt történik minden tranzakciótípus és számviteli keretrendszer esetében.

## <a name="asset-leasing-transactions"></a>Eszközlízing-tranzakciók

#### <a name="initial-recognition"></a>Kezdeti elszámolás 
A lízingbe adott eszköz kezdeti megjelenítése a számított nettó jelenérték alapján történik, így az megjeleníthető a mérlegben. A program automatikusan létrehoz egy ehhez tartozó könyvelési tételt. Ez a tranzakció a használatijog-eszköz számlájának terhelését, és az operatívlízing-kötelezettség számlájának jóváírását a következők szerint hajtja végre. Ha egy tárgyi eszközt társítottak a lízinghez, akkor a kezdeti megjelenítés könyvelési tétele tárgyieszköz-beszerzésként fog szerepelni. Ebben a helyzetben meg kell határoznia egy tárgyieszköz-feladási profilt, amelyet a megfelelő használatijogeszköz-számlára kell feladni. 

> [!NOTE]
> Az operatív lízingeket csak az USA GAAP ASC 842 támogatja.

|     Típus                                          |     Tartozik                     |     Követel                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Operatív lízing az USA GAAP szerint            |     Használatijog-eszköz        |     Operatívlízing-kötelezettség     |
|     Pénzügyi lízing az IFRS és az USA GAAP alapján      |     Használatijog-eszköz        |     Pénzügyi lízingkötelezettség       |

#### <a name="lease-liability-amortization-interest-expense"></a>Lízingkötelezettség amortizációja (kamatráfordítás) 
A lízingre vonatkozó kamatot a lízing kezdő egyenlegére, a lízingdíjfizetés időszakára, járulékos kamatlábra, valamint az évenkénti kamatos kamattal érintett intervallumokra való kamatszámítással jeleníti meg a rendszer. A kamatösszeg jóváírással növeli az opartívlízing-kötelezettség számláját, amelyet a szervezet mérlege fog tükrözni. A tranzakció egy, a kamatráfordítási számlán megjelenő terhelési tételt tartalmaz, amelyet a pénzügyi lízingek esetén az eredménykimutatás, az operatív lízingek esetén pedig a lízingköltségszámla tükröz.

|     Típus                                          |     Tartozik                     |     Követel                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Operatívlízing-kötelezettségi tétel az USA GAAP ASC 842 alapján.    |     Lízingköltség         |     Operatívlízing-kötelezettség         |
|     Pénzügyilízing-kötelezettségi tétel az IFRS és az USA GAAP alapján      |     Kamatköltség          |     Pénzügyi lízingkötelezettség           |

#### <a name="accrued-lease-payment"></a>Elhatárolt lízingdíjfizetés
Az elhatárolt lízingdíjfizetés olyan jövőbeli lízingdíjfizetésként jelenik meg, amelyet bankszámláról vagy készpénzszámláról végrehajtott fizetési tranzakcióként kell feldolgozni. Az esedékes lízingdíjfizetés a lízingkötelezettséget a lízingkötelezettség számlájának szállítói analitikus naplóval szembeni terhelésével csökkenti, ha a lízingbeadó szállítónak minősül, illetve egy váltókötelezettségek főkönyvi számlán a jóváírás oldal feladásával csökkenti, melyet követően a kifizetés a szállítóval vagy váltókötelezettségekkel szemben teljesül.

|     Típus                                          |     Tartozik                     |     Követel                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Operatív lízing az USA GAAP szerint              |  Operatívlízing-kötelezettség    |   Szállítói kötelezettség (analitikus számla)/Váltókötelezettségek  |
|     Pénzügyi lízing az IFRS és az USA GAAP alapján        |  Pénzügyi lízingkötelezettség      |   Szállítói kötelezettség (analitikus számla)/Váltókötelezettségek  |

#### <a name="asset-depreciation"></a>Eszköz értékcsökkenése
A használatijog-eszköz értékcsökkenése a következők közül a kisebbel valósul meg: az eszköz hasznos élettartama vagy a lízingfutamidő. Az US GAAP operatív lízing(ASC 842) szerinti értékcsökkenés számításának módszere a lineáris lízingköltség és a költségráfordítás közötti különbségen alapul. A pénzügyi lízingek avultatását a szabványos lineáris módszer alapján számítja ki a program. A lízing értékcsökkenése hatással van az eredménykimutatásra, mivel a kamatráfordtást terheli. A mérleget annyiban érinti, hogy a pénzügyi lízingek esetén jóváírás történik a felhalmozott használatijogeszköz-számlán. Ha a lízinget egy tárgyi eszközhöz társították, akkor az értékcsökkenési tranzakciók csak a tárgyi eszközök modulból hajthatók végre. 

|     Típus                                          |     Tartozik                     |     Követel                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Operatív lízing az USA GAAP szerint              |  Lízingköltség                |   Használatijog-eszköz felhalmozott értékcsökkenése     |
|     Pénzügyi lízing az IFRS és az USA GAAP alapján        |   Használatijog-eszköz költségének értékcsökkenése   |   Használatijog-eszköz felhalmozott értékcsökkenése    |

#### <a name="short-term-lease"></a>Rövidtávú bérlet
A rövid lejáratú lízing költségként jelenik meg, amely hatással van a szervezet bevételkimutatására. A létrehozott esedékes lízingdíjfizetés a lízingköltség számláját terheli, és a váltókötelezettségek vagy szállítói analitikus számlán okoz jóváírást.

|     Típus                                          |     Tartozik                     |     Követel                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Rövid lejáratú lízingkötelezettségi tétel az IFRS és az USA GAAP alapján     |  Lízingköltség                |   Szállítói kötelezettség (analitikus számla)/Váltókötelezettségek  |

#### <a name="low-value-lease"></a>Alacsony értékű lízing
Az alacsony értékű lízing költségként jelenik meg, amely hatással van a szervezet bevételkimutatására. A létrehozott esedékes lízingdíjfizetés a lízingköltséget terheli, és a váltókötelezettségek vagy szállítói analitikus számlán okoz jóváírást.

|     Típus                                          |     Tartozik                     |     Követel                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Alacsony értékű lízingkötelezettségi tétel az IFRS és az USA GAAP alapján      |  Lízingköltség                |   Szállítói kötelezettség (analitikus számla)/Váltókötelezettségek  |


#### <a name="index-revaluation"></a>Referenciaindex újraértékelése
Ez egy, referencia-kamatláb alapján számított változó lízingdíjfizetésre szóló eszközlízingszámla. A referencia-kamatlábban jelentkező ingadozások okozta változások a lízingdíjfizetésben az IFRS 16 alapján lízingkorrekciónak minősülnek. A lízingkötelezettség és a használatijog-eszközök korrekciója történik az új kifizetések könyvelése érdekében. 

|     Típus                                          |     Tartozik                             |     Követel                    |
|-----------------------------------------------    |-------------------------------------  |----------------------------   |
|   IFRS szerinti index-átértékelési tétel növekedés esetén  |  Használatijog-eszköz       |   Operatívlízing-kötelezettség |
|   IFRS szerinti referencia-átértékelési tétel csökkenés esetén  |  Operatívlízing-kötelezettség  |   Használatijog-eszköz      |

Amikor a díjkifizetések a referencia-kamatláb változása miatt módosulnak, akkor csak a változó díjkifizetések változnak mindaddig, amíg a készpénzforgalmat érintő további változások nem következnek be, így például az US GAAP ASC 842 szerinti kamatlábakkal összefüggő változások a lízingfutamidőben.

#### <a name="lease-adjustment"></a>Lízingkorrekció
Az eszközlízing modul lehetővé teszi a lízingek korrekcióját, ha a lízingfutamidők módosulnak, a lízinget meghosszabbítják vagy egyéb, olyan körülmények merülnek fel, amelyek miatt a lízing korrekcióra szorul. A lízingkorrekciók feladásával nő vagy csökken a használatijog-eszköz és a lízingkötelezettség. A korrekció folyamat során a kötelezettségamortizációhoz és eszközmérleghez tartozó, maradvánnyal zárt mérlegek a korrekció dátumával módosulnak. Amikor egy lízinget tárgyi eszközhöz társítottak, a használatijog-eszköz korrekciójának feladására a tárgyi eszközökhöz rendelt azonosítóval kerül sor. 

|     Típus                                          |     Tartozik                             |     Követel                    |
|-----------------------------------------------    |-------------------------------------  |----------------------------   |
|   Lízingkorrekciós tétel az IFRS és US GAAP alapján növekedés esetén     |  Használatijog-eszköz       |   Operatívlízing-kötelezettség |
|   Lízingkorrekciós tétel az IFRS és US GAAP alapján csökkenés esetén     |  Operatívlízing-kötelezettség  |   Használatijog-eszköz      |


#### <a name="lease-impairment"></a>Lízing értékvesztése
Ez a használatijog-eszköz átvitt egyenlegének csökkentését jelenti. Az értékvesztés összegének, a tranzakció dátumának és a hátralévő időszakok meghatározása. A megmaradó használatijog-eszköz amortizálása lineáris módszerrel történik. A lízing értékvesztési logikája figyelembe veszi az eszköz értékcsökkenési ütemezésében lévő eszköz-maradványértéket.  

|     Típus                                          |     Tartozik                             |     Követel                    |
|-----------------------------------------------    |-------------------------------------  |----------------------------   |
|   Értékvesztési tétel az IFRS és az USA GAAP alapján           |  Értékvesztési költség                   |    Használatijog-eszköz     |

>[!NOTE]
> Ha a lízinget egy tárgyi eszközhöz kapcsolják, akkor a lízing értékvesztését a tárgyi eszközökből kell feladni, mivel az eszköz értékvesztése a tárgyi eszközök modulból megy végbe.

**A kétdevizás** lízingtranzakciók a számviteli és beszámolási pénznemtől eltérő valutában adhatók fel. A pénznem árfolyamát a főkönyvben a kezdőnappal kell meghatározni. Az árfolyamok akkor módosíthatók, ha a **Rögzített árfolyam** mezőt **Igen** értékre állítja a lízing létrehozásakor. Amikor lízingtranzakciókat ad meg, a kezdeti megjelenítés és a későbbi értékcsökkenés tranzakciói a kezdőnap szerinti árfolyamot alkalmazzák majd. A következő fizetési és kamattranzakciók az aktuális aktív árfolyamot fogják alkalmazni. 

## <a name="create-an-asset-lease"></a>Eszközlízing létrehozása
Új lízinget a következő lépésekkel hozhat létre. 

1. Az **Eszközlízing** használatához engedélyeznie kell ezt a funkciót a **Funkciókezelési** munkaterület használatával. A **Funkciókezelési** munkaterületen válassza az **Összes** lehetőséget, hogy az összes funkciót tartalmazó lista megjelenjen az oldalon. Válassza ki az **Eszközlízing** funkciót, majd pedig az **Engedélyezés most** lehetőséget.
2. Lépjen az **Eszközlízing > Általános > Lízingösszesítő** felületre. Az **Általános** gyorsfülön töltse ki a következő mezőket: 
   - **Lízing részletei**
   - **Eszköz hasznos élettartama (hónap)**
   - **Lízingcsoport**
   - **Járulékos kamatláb (%)**
   - **Összetételi intervallum**
   - **Annuitás típusa**
   - **Pénznem**
   - **Kezdési dátum**

3. Lépjen tovább a **Fizetési ütemterv sorai** gyorsfülre, és adjon meg egy kifizetési sort, majd válassza az **Ütemtervek létrehozása** elemet.

4. Válassza ki a **Könyvek** lehetőséget. 

5. Váltson át az **Általános** gyorsfülre. A program kiszámítja a **Kezdeti használatijog-eszközt** és a **lízingkötelezettséget**. 

6. Lépjen a **Lízingminősítési teszt** gyorsfülre a **Lízingtípus** mező értékének ellenőrzéséhez. 

   Az automatikus **Lízingtípus** minősítése a **Könyvek** oldalon meghatározott feltételek alapján történik.

7.  Lépjen a **Fizetési ütemterv** oldalra a **Funkció** részben.  

   A **Fizetési ütemterv** oldal az adott lízingazonosítóhoz tartozó jövőbeli fizetési ütemterveket listázza. Válassza az **Ütemterv megerősítése** lehetőséget a **Kezdeti megjelenítési** tranzakciók feladásához. 

[![Kezdeti megjelenítési funkció.](./media/overview-13.png)](./media/overview-13.png)

8. Válassza ki a **Kezdeti megjelenítést** a kezdeti megjelenítési napló létrehozásához. 

9. Válassza ki az **Eszközlízing-naplók** lehetőséget a kezdeti megjelenítési tranzakció feladásához. 

   A fizetési ütemtervből egy részletes oldalt nyithat meg, amely a használatijog-eszközzel kapcsolatos tranzakciókat listázza. 
 
   A **Lízingkötelezettség amortizációjának ütemezése** az egyes időszakokra kiszámított kamat összegét jeleníti meg.
   
10. Hozza létre a naplót, majd kattintson az **Eszközlízing naplókra**. A **Lízingkötelezettség amortizációjának ütemezése** a kamattranzakciókban is látható.

   Az **Eszköz értékcsökkenésének ütemezése** oldal a kiválasztott lízingazonosítóhoz tartozó értékcsökkenési tranzakciókat jeleníti meg. 

   [![ROU-eszközhöz tartozó tranzakciók oldal.](./media/overview-20.png)](./media/overview-20.png)

   A **ROU-eszköztranzakciók** oldal a kezdeti megjelenítést, a halmozott értékcsökkenést és az eszközegyenleget listázza. 

   A **lízingkötelezettség-tranzakciók** oldal a kezdeti megjelenítést, a lízingkamatot, a lízingdíjfizetést és a lízingkötelezettség egyenlegét jeleníti meg. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]

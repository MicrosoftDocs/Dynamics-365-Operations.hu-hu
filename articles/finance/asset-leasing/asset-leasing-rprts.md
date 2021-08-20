---
title: Eszközlízing-jelentések
description: Ez a témakör az eszközlízing számára elérhető jelentéseket listázza és röviden ismerteti.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-27
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7044378a66ed9ff952f4579d375d59576fe09294fc158c000ab28a93f4173421
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6739407"
---
# <a name="asset-leasing-reports"></a>Eszközlízing-jelentések

[!include [banner](../includes/banner.md)]

Ez a témakör az eszközlízing számára elérhető jelentéseket listázza és röviden ismerteti. A legtöbb jelentést úgy jelenítheti meg, hogy a következő vagy a következőkhöz nagyon hasonló lépéseket végrehajtja. 

- A legtöbb eszközlízing-jelentés megtekintéséhez válassza az **Eszközlízing > Lekérdezések és jelentések > Lízingjelentések** lehetőséget, majd válassza ki a megtekinteni kívánt jelentést. Az eltérő kijelölési útvonalat igénylő jelentések esetében a jelentés megnyitásának lépéseit a jelentés leírása tartalmazza. 
- Amikor kiválaszt egy nyomtatandó jelentést, megnyílik egy paraméteroldal, amely lehetővé teszi a jelentésben szereplő információk szűrését. Írja be a szűrési feltételeket, majd a jelentés létrehozásához kattintson az **OK** gombra. A létrehozott jelentés olyan információkat jelenít meg, amelyek a megadott szűrőkbe tartoznak.

## <a name="asset-movement"></a>Eszközmozgás
Az Eszközmozgás jelentés a használati jog eszközegyenlegeinek minden egyes lízinghez a használatijog-eszköz egyenlegéhez használható. Ez a jelentés lehetővé teszi a lízing eszköztranzakcióinak megtekintését egy adott időszakban. A jelentés a következő mezőket tartalmazza. 

|     Jelentésmezők                  |     Leírás                                                                |
|------------------------------------|--------------------------------------------------------------------------------|
|     Kezdési dátum              |     A lízing legkorábbi verziójának kezdő dátuma.                     |   
|     Lízingfutamidő                     |     A lízing legkorábbi verziójának bérleti ideje.                            |
|     Rövidtávú lízing               |     Ha a lízing rövidtávú lízingként van besorolva, akkor az **Igen** érték jelenik meg.         |
|     Alacsony értékű lízing                |     Ha a lízing alacsony értékű lízingként van besorolva, akkor az **Igen** érték jelenik meg.          |
|     Kezdeti használatijog-eszköz     |     A használatijog-eszköz eredeti értéke a kezdeti kivezetés naplóbejegyzésből.      |
|     Nyitó egyenleg              |     A használatijog-eszköz nettó könyv szerinti értéke a **Kezdő dátumtól** kezdődően.                         |
|     Időszak értékcsökkenési költsége    |     A jelentéshez meghatározott dátumtartományon belül felvett értékcsökkenési költség összege.        |
|     Halmozott értékcsökkenés       |     A halmozott értékcsökkenés összege a **Kezdő dátumtól** kezdve.                               |
|     Értékvesztés                     |     A jelentéshez meghatározott dátumtartományon belül értékcsökkentett eszköz összege.               |
|     Módosítások                  |     A használatijog-eszköz használati jogának a dátumparaméterek közötti módosítási összege.                            |
|     Nettó könyv szerinti érték                 |     A használati jog záró nettó könyv szerinti értéke, amely a **Záró dátumtól** kezdődő halmozott értékcsökkenés nettó értéke.    |

## <a name="differences-report"></a>Különbségek jelentése
A Különbségek jelentés a lízing importálási keretrendszerébe betöltött adatok és a rendszerben jelenleg lévő információk közötti különbségeket mutatja. Ez lehetővé teszi, hogy összehasonlítsa, mi volt módosítva, frissítve vagy hozzáadva a Lízing importálási keretrendszeren keresztül.  

A jelentésben lévő értékek a kiválasztott lízingtől függően változnak. A jelentés csak azokat a mezőket jeleníti meg, amelyek eltérnek a rendszer jelenlegi rendszerétől és az átmeneti táblákban lévőktől. A régi érték az, ami jelenleg a rendszerben van, vagy ami korábban a rendszerben volt, attól függően, hogy az importálási folyamat futott-e. Az új érték az átmeneti táblában lévő értéket jeleníti meg, amely felülírja a régi értéket.

## <a name="five-years-undiscounted-payment-forecast"></a>Öt éves nem diszkontált fizetési előrejelzés
Az ötéves nem diszkontált fizetési előrejelzési jelentés a jelentés paraméterein meghatározott dátumtól számított következő öt évben kifizetendő, nem diszkontált lízingkifizetéseket mutatja. A jelentés a következő mezőket tartalmazza. 

|     Jelentésmezők         |     Leírás                                                                                       |
|-------------------------- |---------------------------------------------------------------------------------------------------    |
|     Lízing leírása     |     A lízing leírása a lízing fejlécéből.                                                      |
|     Lízingazonosító              |     Az egyedi lízingazonosító.                                                                              |
|     Foglalás                  |     A könyvazonosítóhoz társított lízingkönyv.                                                         |
|     Osztályozás        |     A lízing besorolása.                                                                  |
|     Feladási réteg         |     Az a réteg, amelyre ez a lízing felad.                                                         |
|     Pénznem              |     A lízing pénzneme.                                                                        |
|     Aktuális               |     A beszámolási időponttól számított 12 hónapon belül fizetendő összes lízingdíjfizetés összege.          |
|     13–24 hónap          |     A beszámolási időponttól számított 13–24 hónapon belül fizetendő összes lízingdíjfizetés összege.           |
|     25–36 hónap          |     A beszámolási időponttól számított 25–36 hónapon belül fizetendő összes lízingdíjfizetés összege.           |
|     37–48 hónap          |     A beszámolási időponttól számított 37–48 hónapon belül fizetendő összes lízingdíjfizetés összege.           |
|     49–60 hónap          |     A beszámolási időponttól számított 49–60 hónapon belül fizetendő összes lízingdíjfizetés összege.           |
|     Ezután            |     A beszámolási időponttól számított 61. hónapon belül vagy azon túl fizetendő összes lízingdíjfizetés összege.              |

## <a name="gaap-cash-flows-report"></a>GAAP pénzforgalmi jelentés
A GAAP közzétételi jelentése megfelel az Amerikai Egyesült Államok GAAP-842-20-50-4 (g) (1) bekezdésében meghatározott közzétételi követelményének. A jelentés megtekintéséhez nyissa meg az **Eszközlízing > Lekérdezések és jelentések > Közzétételek > GAAP – pénzforgalom** menüpontban. 

|     Jelentésmezők                                 |     Leírás                                                                                                                                               |
|------------------------------------------------   |-----------------------------------------------------------------------------  |
|     Kezdő dátum <br> Záró dátum                        |     A jelentésben szereplő információk korlátozására használt dátumtartományt határozza meg.      |
|     Jogi személy                                  |     A lízingekhez kötött jogi személy.                                      |
|     Lízingtípus                                    |     A lízing pénzügyi vagy működési besorolása.           |
|     Lízingazonosító                                      |     Az egyedi lízingazonosító.                                                      |
|     Lízing leírása                             |     A lízing leírása a lízing fejlécéből.                              |
|     Lízingkönyv                                    |     A lízingkönyv, amelyre a sor utal.                        |
|     Feladási réteg                                 |     A tárgyi eszközhöz csatolt valamennyi könyv egy meghatározott feladási réteghez tartozik, amelynek saját átfogó értékcsökkenési célkitűzése van.                          |
|     Lízingcsoport                                   |     Az a csoport, amelyhez a lízing kötődik.                                     |
|     Pénznem                                      |     A használt tranzakciós pénznem rövidítése. Minden jelentés átváltja a tranzakciópénznemet a jelentés pénznemére.                      |
|     Pénzügyi lízingek – Működési pénzforgalmak         |     Az összes könyvelt változó kifizetés és az amortizációs ütemezésből a dátumparaméterek között feladott összes kamatkifizetés összege.        |
|     Pénzügyi lízingek – Pénzügyi pénzforgalmak           |     Az amortizációs ütemezésből származó összes tőkekifizetés összege a dátumparaméterek között.       |
|     Működési lízingek – Működési pénzforgalmak       |     Az összes könyvelt lízingkifizetés és feladott változó kifizetés összege a dátumparaméterek között.            |

## <a name="lease-balances-forecast"></a>Lízingegyenlegek előrejelzése
A Lízingegyenlegek előrejelzés a közvetlenül a kötelezettségamortizációs ütemezésből és az eszköz értékcsökkenési ütemezéséből származó információkat sorolja fel. A jelentés a tervezett lízingkötelezettség és használati jog szerinti eszközök előre jelzett összegeit jeleníti meg egy adott időszakban, beleértve a jelen lízingek összes tervezett kiadását is. A jelentés a következő mezőket tartalmazza.

|     Jelentésmezők                 |     Leírás                                                                                                                                                                               |
|---------------------------------  |--------------------------------------------------------------------------------------------------------------------   |
|     Nyitó egyenleg             |     A lízing amortizációs ütemezésének kezdő egyenlege a jelentés kezdő dátumát tartalmazó időszakra vonatkozóan.            |
|     Kezdeti elszámolás           |     Ha a lízing kezdő dátuma a jelentéshez megadott dátumtartományba esik, ebben az oszlopban a kezdeti kivonási naplóbejegyzés forrásszámlaértéke látható.      |
|     Kifizetések                      |     A lízing által a jelentéshez meghatározott dátumtartományba tartozó kifizetések összege.                               |
|     Érdeklődési terület                      |     A lízing által a jelentéshez meghatározott dátumtartományba tartozó kamatráfordítások összege.                    |
|     Záró egyenleg                |     A lízing forrásegyenlege a **Záró dátumtól** kezdődően.                                                             |
|     Rövidtávú kötelezettség          |     A rövidtávú kötelezettség összege a lízing amortizációs ütemezésében a **Záró dátumtól** kezdődően.                           |
|     Hosszú lejáratú kötelezettség           |     A hosszú távú kötelezettség összege a lízing amortizációs ütemezésében a **Záró dátumtól** kezdődően.                            |
|     Kezdő nettó könyv szerinti érték      |     A lízing értékcsökkenési ütemezésének „Kezdő nettó könyvértékre” a jelentés kezdő dátumát tartalmazó időszakra vonatkozóan      |
|     Kezdeti elszámolás           |     Ha a lízing kezdő dátuma a jelentéshez megadott dátumparaméterek közé esik, ebben az oszlopban a kezdeti kivonási naplóbejegyzés eszközszámla értéke látható.            |
|     Értékcsökkenés költsége          |     A lízing által a jelentéshez meghatározott dátumtartományba tartozó értékcsökkenés összege.                  |
|     Záró egyenleg                |     A lízing eszközegyenlege a **Záró dátumtól** kezdődően.                                                              |
|     Saját tőke helyesbítése             |     A kezdő egyenleg mínusz a kezdő nettó könyv szerinti érték.                                                             |

## <a name="lease-commencements-report"></a>Lízing kezdeti jelentés
A Lízing kezdeti jelentés az összes olyan lízinget mutatja, amely egy meghatározott dátumtartományon belül kezdődött, beleértve a kezdeti kötelezettséget és a használatijog-eszköz egyenlegét. A jelentés a következő mezőket tartalmazza. 

|     Jelentésmezők                 |     Leírás                                                                                       |
|---------------------------------  |---------------------------------------------------------------------------------------------------    |
|     Kezdési dátum             |     Az adott lízing verzióhoz feladott kezdeti elszámolási naplóbejegyzés dátuma.         |
|     Kezdeti kötelezettség összege      |     A kezdeti elszámolásnapló-bejegyzésből származó kötelezettségösszeg.                                  |
|     Eszköz kiindulási összege          |     A kezdeti elszámolásnapló-bejegyzésből származó eszközösszeg.                                      |

## <a name="lease-modification-report"></a>Lízingmódosítási jelentés
A Lízing módosítása jelentés az összes olyan lízinget megjeleníti, amelyet egy megadott dátumtartományon belül módosítottak. A jelentésben látható az a felhasználó is, aki módosította a lízinget, és a kötelezettség teljes összege kiigazítva. A jelentés a következő mezőket tartalmazza. 

|     Jelentésmezők                 |     Leírás           |
|---------------------------------  |-------------------------  |
|     Helyesbítette:                   |     A lízinget módosító személy felhasználóneve.                                |
|     Kiigazítás oka               |     Az a dátum, amelyen a naplóbejegyzés kiigazítása fel lett adva.                        |
|     Helyesbítések                   |     A lízing kötelezettségszámlájára a dátumparaméterek között feladott bármely helyesbítő naplóbejegyzés összege. A jóváírások pozitívan, míg a terhelések negatívak lesznek.       |
|     Nyereség (veszteség) összege            |     A lízing nyereség-/veszteségszámlájára a dátumparaméterek között feladott bármely helyesbítő naplóbejegyzés összege. A jóváírások pozitívan, míg a terhelések negatívak lesznek.       |
|     Mérleg szerinti eredmény             |     A lízing fenntartott bevételek számlájára a dátumparaméterek között feladott bármely helyesbítő naplóbejegyzés összege.      |
|     Záró kötelezettségegyenleg      |     Az eredményül kapott lízing forrásegyenlege a kiigazítás dátumtól kezdődően.           |

## <a name="lease-movement-report"></a>Lízing mozgási jelentése
A Lízingmozgás jelentés a használati jog eszközegyenlegeinek minden egyes lízinghez a lízingkötelezettség egyenlegekhez használható. Ez a jelentés lehetővé teszi a felhasználónak lízingtranzakcióinak megtekintését egy adott időszakban.

|     Jelentésmezők             |     Leírás                                               |
|----------------------------   |-------------------------------------------------------------- |
|     Kezdési dátum         |     A lízing legkorábbi verziójának kezdő dátuma.    |
|     Lízingfutamidő                |     A lízing legkorábbi verziójának bérleti ideje.           |
|     Fennmaradó fizetések        |     A lízingre még fel nem adott kifizetések száma.                       |
|     Nyitó egyenleg         |     A lízingkötelezettséget befolyásoló összes tranzakció összege, amely a jelentés kezdő dátuma előtt történt.             |
|     Kezdeti elszámolás       |     A lízinghez tartozó, a jelentéshez meghatározott dátumtartományon belül feladott kezdeti megjelenítési tranzakciók összege.     |
|     Kifizetések                  |     A lízing által a jelentéshez feladott dátumtartományba tartozó kifizetéstranzakciók. Az ebben az oszlopban szereplő értékek negatív összegekként jelennek meg, mivel a kifizetések csökkentik a lízing kötelezettségegyenlegét.  |
|     Érdeklődési terület                  |     A lízinggel szemben a jelentéshez feladott dátumtartományba tartozó kamatkönyvelések.            |
|     Helyesbítések               |     A lízing által a jelentéshez feladott dátumtartományba tartozó kiigazítási tranzakciók összege.                               |
|     Záró egyenleg            |     A lízing összes olyan kötelezettségtranzakciójának egyenlege, amelyet a jelentés **Záró dátuma** óta könyveltek.                  |

## <a name="lease-transactions-report"></a>Lízingtranzakciók jelentése
A Lízingtranzakciók lekérdezése az Eszközlízing által létrehozott összes naplóbejegyzést megjeleníti. Minden naplóbejegyzés ahhoz a könyvazonosítóhoz kapcsolódik, amelyből származik. Ez lehetővé teszi, hogy a naplóbejegyzést könnyen társítsa a megfelelő lízinghez. A Lízingtranzakciók lekérdezése a Főkönyv **Bizonylattranzakciói** laphoz hasonló módon működik.

## <a name="weighted-average-discount-rate-report"></a>Súlyozott átlagos kedvezményes árjelentés
A súlyozott átlagos kedvezményes árjelentés megfelel az ASC 842-20-50-4 (g) (4) bekezdésében meghatározott, súlyozott átlagos kedvezményes árra vonatkozó amerikai GAAP-közzétételi követelménynek. A jelentés megtekintéséhez nyissa meg az **Eszközlízing > Lekérdezések és jelentések > Közzétételek > Súlyozott átlagos kedvezményes ár** menüpontban. A jelentés a következő mezőket tartalmazza. 

|     Jelentésmezők                     |     Leírás                                                           |
|------------------------------------   |------------------------------------------------------------------------   |
|     Adott dátumtól                        |     Ez a jelentés tartalmazza az összes olyan lízinget, amely a **kezdő** dátum paraméterrel vagy azt megelőzően kezdődött. Ezt a jelentést a közzétévő időszak utolsó napjától kell futtatni.      |
|     Jogi személy                      |     A lízinghez kötött jogi személy.                           |
|     Lízingazonosító                          |     Az egyedi lízingazonosító.                                                  |
|     Lízing leírása                 |     A lízing leírása a lízing fejlécéből.                          |
|     Foglalás                              |     A megjelenített bérlet konkrét könyvtípusa.                                                                                                                                            |
|     Feladási réteg                     |     A tárgyi eszközhöz csatolt valamennyi könyv egy meghatározott feladási réteghez tartozik, amelynek saját átfogó értékcsökkenési célkitűzése van.      |
|     Lízingcsoport                       |     Az a csoport, amelyhez a lízing tartozik.                                 |
|     Engedményszázalék                     |     A kedvezményes lízingfizetésekhez használt százalék.                             |
|     Pénznem                          |     A használt tranzakciós pénznem rövidítése. Minden jelentés átváltja a tranzakciópénznemet a jelentés pénznemére.  |
|     Fennmaradó lízingdíjfizetések          |     A kifizetési ütemezésből származó kifizetetlen lízingfizetések teljes összege, amelyek a **Kezdő** dátumtól maradtak.            |
|     Fennmaradó súlyozott kifizetések       |     A fennmaradó lízingdíjfizetések és a felhasznált kedvezményes ár szorzata.   |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

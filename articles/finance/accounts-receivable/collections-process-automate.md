---
title: Beszedési folyamat automatizálása
description: Ez a témakör azt mutatja be, hogyan lehet beállítani azokat a beszedési folyamat-stratégiákat, amelyekkel automatikusan azonosíthatja a vevői számlákat, amelyekhez egy e-mail emlékeztető, a beszedési tevékenység vagy a vevőnek küldendő fizetési felszólítás szükséges.
author: panolte
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-26
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: ce83b8e66abece2c40ca0a7ca3bf67894b97c287
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827626"
---
# <a name="collections-process-automation"></a>Beszedési folyamat automatizálása

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet beállítani azokat a beszedési folyamat-stratégiákat, amelyekkel automatikusan azonosíthatja a vevői számlákat, amelyekhez egy e-mail emlékeztető, a beszedési tevékenység (például a telefonhívás) vagy a vevőnek küldendő fizetési felszólítás szükséges. 

A vállalatok jelentős időt töltenek az éves egyenlegjelentések, a vevői számlák és a nyitott számlák kutatására, hogy megtudják, hogy mely vevőkkel kell felvenni a kapcsolatot nyitott számlákkal vagy számlával kapcsolatos egyenleggel kapcsolatban. Ez a kutatás időt vesz igénybe a beszedési ügynököktől, hogy kommunikáljanak a vevőkkel, beszedjék a lejárt tartozásokat, vagy megoldják a számlákkal kapcsolatos vitákat. A beszedési folyamatok automatizálásával stratégián alapuló megközelítést állíthat be a beszedési folyamathoz. Ily módon a beszedési tevékenységeket következetesen alkalmazhatja a személyre szabott e-mailes emlékeztetőkkel, illetve a fizetési felszólítások küldésének programozott folyamatával. 

## <a name="collections-process-setup"></a>Beszedési folyamat beállítása
A **Beszedési folyamat beállítása** lap (**Követelések és beszedések > Beállítás > Beszedési folyamat beállítása**) segítségével létrehozható egy automatizált beszedési folyamat, amely a tevékenységeket, e-mailek küldését, valamint a vevői fizetési felszólítások létrehozását és feladását végzi. A folyamat lépései a kezdő vagy legrégebbi nyitott számlán alapulnak. Minden lépés ezt a számlát használja annak meghatározására, hogy milyen kommunikációt vagy tevékenységet kell végezni egy adott vevővel.  

A beszedési csoportok általában korai értesítést küldenek minden egyes függőben lévő számláról, így a vevő értesítést kap, amikor a számla esedékessé válik. Az **Előzetes fizetési felszólítás** lehetőséggel be lehet állítani, hogy minden folyamathierarchiában egy lépés legyen érvényes minden számlára, amikor a számla időzítése eléri az adott lépést.

### <a name="process-hierarchy"></a>Folyamathierarchia
A vevőgyűjtőket csak egy munkafolyamat-hierarchiához lehet hozzárendelni. Ennek a lépésnek a hierarchiaszintje határozza meg, hogy melyik folyamat fog elsőbbséget élvezni, ha a vevő egynél több olyan gyűjtőben szerepel, amelyhez van hozzárendelve munkafolyamat-hierarchia. A gyűjtő azonosítója határozza meg, hogy a folyamathoz melyik vevők lesznek hozzárendelve. 

A csendes napok segítségével biztosítható, hogy a vevővel ne legyen túl gyakran felvéve a kapcsolat az automatizált eljárással.  Ha például a csendes napok kettő értékre vannak állítva, akkor az automatizált folyamat veszi fel a kapcsolatot a vevővel legalább két napig, még sem, ha az eredeti vezető számlát teljes egészében kiegyenlítették. 

Ha ki szeretne zárni vevőket a folyamatból abban az esetben, ha a partner egyenlege vagy a számla egyenlege kisebb, mint a meghatározott érték, állítsa a **Kizárás a folyamatból** mezőt **Igen** értékre, és adja meg az összeg értékét.

## <a name="process-details"></a>Folyamat részletei
**Leírás** – a hierarchiában szereplő lépés céljának vagy nevének a meghatározására szolgál.

**Művelettípus** – azt határozza meg, hogy a lépés egy tevékenységet hozzon létre, e-mailt küldjön vagy fizetési felszólítást hozzon létre.

**Üzleti dokumentum** – a művelettípus létrehozásához használt sablont határozza meg.  Ez lehet egy tevékenységsablon, egy e-mail-sablon vagy egy vevői fizetési felszólítás. 

A Művelettípus a számla esedékességi dátuma előtt vagy után is létrehozható a **Napok a számla esedékességi dátumához képest** oszlopban megjelenített beállítás alapján.

Amikor kiválaszt egy e-mail műveleti típust, a címzett határozza meg, hogy a vevő, értékesítési csoport vagy a beszedési ügynök kapcsolattartója-e. Az **Üzleti célú kapcsolattartó** határozza meg, hogy a vevő fiókjából melyik kapcsolattartó fogja kapni a kommunikációt.

## <a name="business-document-details"></a>Üzleti dokumentum részletei
Az üzleti dokumentum részletei a folyamat részleteinél kiválasztott művelettípus alapján változik.  Ha a művelettípus egy tevékenység, akkor a program a műveletsablon adatait jeleníti meg.  Ezek a részletek a műveletsablon nevét, a létrehozandó tevékenység típusát, a tevékenység célját, a tevékenység befejezéséhez ütemezett napok számát, valamint a tevékenység részleteit tartalmazzák.  Ez a tevékenység ezt követően a vezető számlára hivatkozik, amely megadja a tevékenység teljesítéséhez szükséges művelet címzettjét.

Ha a művelettípus egy e-mailt a folyamat részletes adataiban, akkor ez a szakasz két gyorslapot fog tartalmazni.  Az első a sablon azonosítójának, az e-mail leírásának, az alapértelmezett nyelvnek, az automatikusan elküldött e-mailekhez rendelt felhasználóneveknek, valamint a társított feladók e-mail címének a meghatározására szolgál. A második lehetővé teszi az e-mailek szövegtörzsének létrehozását, miután a **Nyelvi** és a **Tárgy** mezők értékeit a **Szerkesztés** gombra kattintva menti.  Ekkor megnyílik egy ablak, amely lehetővé teszi a HTML-tartalom feltöltését. Az ablak bal alsó sarkában, a manuálisan létrehozott üzenetet is megadhat.  

> [!Note]
> Az Outlook-e-mail a kommunikáció kívánt szövegtörzsével menthető HTML formátumban. Ezt követően feltölthető a sablon végrehajtásához. <br> <br> Ha a fizetési felszólítás típusú művelet van kiválasztva, akkor a beállítási képernyő nem tartalmaz üzleti dokumentum részletei szakaszt.


## <a name="fasttab-reference"></a>Gyorslap-hivatkozás
A következő táblázatokban azoknak a lapoknak és mezőknek a listája látható, amelyekről a megadott Gyorslapok elérhetők, valamint a lap adatainak leírása. 

### <a name="process-hierarchy"></a>Folyamathierarchia

|     Oldal                                                  |     Mező                         |     Leírás                           |
| --------------------------------------------------------  |-------------------------------    |---------------------------------------    |
|     Beszedési folyamat beállítása <br> Folyamatok automatizálása       |                                   |     A beszedési folyamatok létrehozása és kezelése a vevőgyűjtők hozzárendelései alapján.                                                                                                                             |
|     Beszedési folyamat beállítása <br> Folyamatok automatizálása       |     Hierarchia                     |     Meghatározza a folyamatok automatizálásának prioritását, amely egy vevőt rendel hozzá, ha több gyűjtőbe tartoznak.                                                                                                   |
|     Beszedési folyamat beállítása <br> Folyamatok automatizálása       |     Csoportazonosító                       |     Lekérdezések, amelyek a vevői rekordok egy csoportját határozzák meg.                                                                                                                                                        |
|     Beszedési folyamat beállítása <br> Folyamatok automatizálása       |     Csendes napok                    |     A feldolgozási lépés gyakoriságának korlátozása. Ha például két csendes nap van beállítva, a következő folyamatlépés nem fog bekövetkezni legalább két napig, ha a vezető számla megváltozik.     |
|     Beszedési folyamat beállítása <br> Folyamatok automatizálása       |     Kihagyás a folyamatból        |     A **Vevő korosítási egyenlege kisebb, mint** vagy a **Számla összege kisebb, mint** kiválasztásával program kizárja a vevőt a folyamat-automatizálásból, ha az érték feltételei nem teljesülnek.                                   |

### <a name="process-details"></a>Folyamat részletei
|     Oldal                                                  |     Mező                                         |      Leírás                  |
|--------------------------------------------------------   |-----------------------------------------------    |----------------------------   |
|     Beszedési folyamat beállítása <br> Folyamatok automatizálása       |                                                   |     A vezető számla alapján tett lépések meghatározása.                                                                                                |
|                                                           |     Leírás                                   |     A lépés nevének és/vagy leírásának megadására használt szabadszöveges mező.                                                                           |
|                                                           |     Művelettípus                                   |     Az a tevékenység, e-mail vagy fizetési felszólítás, amelyet a folyamatlépés létrehoz.                                                                     |
|                                                           |     Üzleti dokumentum                           |     A folyamat lépéseiben használt tevékenység vagy e-mail sablon meghatározása.                                                                        |
|                                                           |     Mikor                                          |     Azt határozza meg, hogy a folyamatlépés a kezdő számla esedékességi dátuma előtt vagy után történik fel a **Napok a számla esedékességi dátumához képest** mezővel.        |
|                                                           |     A számla esedékességi dátumával kapcsolatos napok        |     A **Ha** mezővel együttesen azonosítja a folyamatlépés időzítését.                                                                          |
|                                                           |     Előzetes felszólítás                                   |     Ez a kiválasztás lehetővé teszi, hogy a folyamathierarchiánként egy lépést állítson be és futtasson minden számlával, amikor az eléri az időzítési feltételeket.                                                |
|                                                           |     Átvevő                                     |     Azt határozza meg, hogy e-mailt küldenek-e a vevőnek, értékesítési csoportnak vagy a beszedési ügynök kapcsolattartójának.                                                   |
|                                                           |     Üzleti célú kapcsolattartó                    |     Azt határozza meg, hogy a címzett melyik e-mail címe használatos az e-mail kommunikációhoz.                                                                                 |

### <a name="business-process-activity-template-details"></a>Üzleti folyamat tevékenységsablonjának részletei 
|     Oldal                                                  |     Mező                     |      Leírás                  |
|--------------------------------------------------------   |----------------------------   |-------------------------  |
|     Beszedési folyamat beállítása <br> Folyamatok automatizálása       |                               |     A beállítási folyamat szakasza, amely azonosítja a tevékenységsablon részleteit.                                                                      |
|     Beszedési folyamat beállítása <br> Folyamatok automatizálása       |     Tevékenységsablon       |     Azonosítja a típust, a célt, a befejezéshez szükséges napok számát, valamint a tevékenység folyamatlépése során létrejövő tevékenység részleteit.       |

### <a name="business-document-email-template-details"></a>Üzleti dokumentum e-mail sablonjának részletei 
|     Oldal                                                  |     Mező     |      Leírás                  |
|--------------------------------------------------------   |-------------- |-----------------------------  |
|     Beszedési folyamat beállítása <br> Folyamatok automatizálása       |               |     Az e-mailek leírásának, az alapértelmezett nyelvnek, a feladók nevének és e-mail címének azonosítására szolgál, amelyet az e-mail-folyamat lépései során hoz létre a rendszer.        |


### <a name="collections-history"></a>Beszedési előzmények 
|     Oldal                              |     Mező     |      Leírás                                                          |
|------------------------------------   |-------------- |---------------------------------------------------------------------  |
|     Beszedési folyamat beállítása       |               |     A kiválasztott feldolgozási hierarchia legutóbbi előzményeinek megtekintése.       |

### <a name="collection-process-assignment"></a>Beszedési folyamat hozzárendelése
|     Oldal                              |     Mező     |      Leírás                                                  |
|------------------------------------   |-------------- |-----------------------------------------------------------    |
|     Beszedési folyamat beállítása       |               |     A beszedési folyamathoz rendelt vevők megtekintése.  
|     Manuális hozzárendelés               |               |     Egy folyamathoz kézzel hozzárendelt vevők megtekintése, illetve a folyamathoz hozzárendelendő vevők kiválasztása. |
|     Folyamat-hozzárendelés előzetes verziója      |               |     Azoknak a vevőknek az előnézete, akik a futtatásakor stratégiához hozzá lesznek rendelve.   |
|     Vevőhozzárendelés előzetes verziója     |               |     Az adott vevőhöz hozzárendelt stratégia megtekintése.    |
 
 ### <a name="process-simulation"></a>Szimuláció feldolgozása
|     Oldal                              |     Mező     |      Leírás                                                  |
|------------------------------------   |-------------- |-----------------------------------------------------------    |
|    Szimuláció feldolgozása                 |               |     Azon műveletek előzetes verziója, amelyek akkor jönnek létre, ha a kiválasztott folyamatautomatizálás fut. |

### <a name="parameters"></a>Paraméterek
|     Oldal                                                                  |     Mező                                             |      Leírás                              |
|-------------------------------------------------------------------------- |------------------------------------------------------ |-------------------------------------  |
|     Kinnlevőségek paraméterei > Beszedési folyamatok automatizálása     |     Ügyfelek százaléka kötegelt feladatonként          |     Beállítással meghatározhatja az automatizálási folyamatok kötegelt feladatainak számát.                                          |
|     Kinnlevőségek paraméterei > Beszedési folyamatok automatizálása     |     Fizetési felszólítások automatikus közzététele           |     A fizetési felszólítás műveletitípusai feladják a levelet az automatizálás során.                                      |
|     Kinnlevőségek paraméterei > Beszedési folyamatok automatizálása     |     Tevékenységek létrehozása automatizáláshoz                |     Tevékenységek létrehozása és bezárása a nem tevékenység típusú művelettípusokhoz a számlán végrehajtott összes automatizált lépés megtekintéséhez.        |
|     Kinnlevőségek paraméterei > Beszedési folyamatok automatizálása     |     A beszedési folyamatok automatizálása megtartása ennyi napig     |     Azt határozza meg, hogy hány napig tárolják a beszedések előzményeit.                                                       |
|     Kinnlevőségek paraméterei > Beszedési folyamatok automatizálása     |     Számla kizárása az utolsó folyamatlépés aktiválása után    |     A jövőbeli folyamatautomatizálási művelettípusok létrehozására nem használható olyan számla, amely eléri a beszedési folyamat utolsó lépését. A következő legrégebbi számla fogja meghatározni a következő folyamatautomatizálási lépést, hogy a beszedési folyamat automatizálási művelete folytatódjon.                                                        |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

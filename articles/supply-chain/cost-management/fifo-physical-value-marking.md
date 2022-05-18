---
title: FIFO tényleges értékkel és jelöléssel
description: A FIFO-elv (First in, First out) egy készletmodell, amelyben az elsőként bevételezett cikkek kerülnek először kiadásra. A készletből történő pénzügyi kiadások a készlettranzakciók pénzügyi dátuma alapján az első pénzügyi készletbevételezésekkel vannak kiegyenlítve.
author: JennySong-SH
ms.date: 02/02/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 54682
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 663dce9f871e96fec7017616732428c49b1224a0
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8676243"
---
# <a name="fifo-with-physical-value-and-marking"></a>FIFO tényleges értékkel és jelöléssel

[!include [banner](../includes/banner.md)]


A FIFO(First in, first out) egy készletkezelés és értékelési módszer, amelyben az elsőként termelt vagy beszerzett készletet először értékesítik, használják vagy adják el. A Microsoft Dynamics 365 Supply Chain Management készletzárási folyamata során a rendszer kiegyenlítéseket hoz létre, amelyekben az első bevételezést az első kiadás stb.

A kiegyenlítések és az egyeztetési elv a készlettranzakciók pénzügyi dátumán alapul. A kiegyenlítések és helyesbítések előzetes értékelése a készlet-újraszámítási folyamat futtatásával végezhető el.

A FIFO-elv felülbírálható a készlettranzakciók megjelölésével, így egy adott cikkbevételezést egy adott kiadással szemben lehet kiegyenlíteni. Időszakos készletzárásra van szükség, ha a FIFO készletmodell segítségével kiegyenlítéseket lehet létrehozni, és a FIFO elv szerint módosítani lehet a problémák értékét. Amíg nem futtatja a készletzárási folyamatot, a kiadási tranzakciók értékének a tényleges és pénzügyi frissítések esetén a mozgóátlagon történik a program. Ha nem használ jelölést, akkor a rendszer a fizikai vagy pénzügyi frissítéskor kiszámítja a mozgóátlagot. Az alábbi példák bemutatják a FIFO-elv alkalmazásának hatását három különböző konfiguráción:

- FIFO a **Tényleges értékkel együtt** beállítás nélkül
- FIFO a **Tényleges értékkel együtt** beállítással
- FIFO jelöléssel

## <a name="fifo-without-the-include-physical-value-option"></a>FIFO a Tényleges értékkel együtt beállítás nélkül

Ebben a példában **a kiadott** termék cikkmodellcsoportjában törlődik a Tényleges értékkel kapcsolatos értékkel kapcsolatos jelölőnégyzet jelölése. A következő ábrán ezek a tranzakciók láthatók:

- 1a. Fizikai bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
- 1b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
- 2a. Fizikai bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
- 2b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 22,00 USD áron.
- 3a. Fizikai kiadás készletről, 1 mennyiséggel, USD 16.00 önköltségi áron (a pénzügyileg feladott tranzakciók mozgóátlaga).
- 3b. Pénzügyi kiadás készletről, 1 mennyiséggel, USD 16.00 önköltségi áron (a pénzügyileg feladott tranzakciók mozgóátlaga).
- 4a. Fizikai bevételezés készletre, 1 mennyiséggel, 25,00 USD áron.
- 5a. Fizikai bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 5b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 6a. Fizikai kiadás készletről, 1 mennyiséggel, USD 23.00 önköltségi áron (a pénzügyileg feladott tranzakciók mozgóátlaga)
- 7\. Készletzárást hajtanak végre. A FIFO-módszer alapján az első pénzügyi kiadást az első pénzügyi bevételezés stb. egyenlíti ki. Ebben a példában egy kiegyenlítés jön létre 1b és 3b között. 3b-re 6,00 USD-s korrekciót fognak végezni, és a végső költséget USD 10.00.

Az önköltség új mozgóátlaga a pénzügyi tranzakciók átlagát tükrözi. A következő ábra bemutatja, milyen hatása van a FIFO készletmodellnek, ha a **Tényleges értékkel együtt** beállítást nincs beállítva.

![FIFO a Tényleges értékkel be nem foglalva beállítás nélkül.](./media/fifo-without-include-physical-value.png)

**Jelmagyarázat**

- A készlettranzakciókat függőleges nyilak jelölik.
- A fizikai tranzakciókat rövidebb világosszürke nyilak ábrázolják.
- A pénzügyi tranzakciókat hosszabb fekete nyilak jelzik.
- A készletre való bevételezéseket az idősor fölötti függőleges nyilak jelölik.
- A készletről való kiadásokat az idősor alatti függőleges nyilak jelölik.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A diagram minden dátumát egy vékony fekete függőleges vonal választja el egymástól. A dátum a diagram alján látható.
- A készletzárásokat egy piros színű, szaggatott függőleges vonal ábrázolja.
- A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

## <a name="fifo-with-the-include-physical-value-option"></a>FIFO a Tényleges értékkel együtt beállítással

Ha a **Cikkmodellcsoport** **lapon** található cikkhez be van jelölve a Tényleges értékkel együtt jelölőnégyzet, a rendszer fizikai és pénzügyi bevételezési tranzakciókat egyaránt használ a mozgóátlagon keresztüli önköltségi ár kiszámításához. Ahol lehetséges, a rendszer a fizikailag frissített kiadási tranzakciót is korrigálja. A FIFO készletmodellt használó készletzárás csak a pénzügyileg frissített tranzakciókkal kapcsolatos kiegyenlítéseket teszi lehetővé. A következő ábrán ezek a tranzakciók láthatók:

- 1a. Fizikai bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
- 1b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
- 2a. Fizikai bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
- 2b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 22,00 USD áron.
- 3a. Fizikai kiadás készletről, 1 mennyiséggel, USD 16.00 önköltségi áron (a ténylegesen és pénzügyileg feladott tranzakciók mozgóátlaga).
- 3b. Pénzügyi kiadás készletről, 1 mennyiséggel, USD 16.00 önköltségi áron (a ténylegesen és pénzügyileg feladott tranzakciók mozgóátlaga).
- 4a. Fizikai bevételezés készletre, 1 mennyiséggel, 25,00 USD áron.
- 5a. Fizikai bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 5b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 6a. Fizikai kiadás készletről, 1 mennyiséggel, USD 23.67 önköltségi áron (a ténylegesen és pénzügyileg feladott tranzakciók mozgóátlaga).
- 7\. Készletzárást hajtanak végre. A FIFO-módszer alapján az első pénzügyi kiadást az első pénzügyi bevételezés stb. egyenlíti ki. Ebben a példában egy kiegyenlítés jön létre 1b és 3b között. 3b-re 6,00 USD-s korrekciót fognak végezni, és a végső költséget USD 10.00. Ezenkívül a 6a. tranzakciót a 2b bevételezési tranzakció költségére is módosítja a a tranzakció. A rendszer nem egyenlíti ki ezeket a tranzakciókat, mivel a bevételezés csak fizikailag történt meg, pénzügyileg azonban nem. Ehelyett csak egy -1,67 USD-s korrekció feladása történik a fizikai kiadási tranzakcióhoz, és az így kapott helyesb USD 22.00.

![FIFO a Tényleges értékkel együtt beállítással.](./media/fifo-with-include-physical-value.png)

A készletzárási folyamat futtatásának eredménye ugyanaz, függetlenül attól, **·** **hogy a Cikkmodellcsoport lapon a Tényleges értékkel való betétele lehetőséget választja-e.** A **Tényleges értékkel való berakodva** beállítás csak a mozgóátlagot érinti.

**Jelmagyarázat**

- A készlettranzakciókat függőleges nyilak jelölik.
- A fizikai tranzakciókat rövidebb világosszürke nyilak ábrázolják.
- A pénzügyi tranzakciókat hosszabb fekete nyilak jelzik.
- A készletre való bevételezéseket az idősor fölötti függőleges nyilak jelölik.
- A készletről való kiadásokat az idősor alatti függőleges nyilak jelölik.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A diagram minden dátumát egy vékony fekete függőleges vonal választja el egymástól. A dátum a diagram alján látható.
- A készletzárásokat egy piros színű, szaggatott függőleges vonal ábrázolja.
- A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

## <a name="fifo-with-marking"></a>FIFO jelöléssel

A jelölés egy olyan folyamat, amellyel összekapcsolható egy kiadási tranzakció egy bevételezési tranzakcióval. A jelölés történhet a tranzakciók feladása előtt és után is. A jelölés használható a készlet pontos költségének megállapítására a tranzakció feladásakor vagy a készletzárás végrehajtásakor.

Tegyük fel például, hogy az ügyfélszolgálati osztály elfogadott egy sürgős megrendelést egy fontos vevőtől. Mivel ez a rendelés sürgős rendelés, többe kell fizetnie azért, hogy teljesíteni tudja az ügyfél kérését. Meg kell győződnie arról, hogy a készletcikk költsége megjelenik az értékesítési rendelés számlájának árrésében vagy eladott áruk költségében (ELÁBÉ). A beszerzési rendelés feladásakor a készlet bevételezése 120,00 USD értéken történik. Ha még a csomagjegyzék vagy a számla feladása előtt meg van jelölve az értékesítési rendelési dokumentum a beszerzési rendelésen, akkor a rendszer feladja USD 120.00 ELÁBÉ-t, nem pedig a cikk jelenlegi mozgóátlagát. Ha még a jelölés előtt feladják a csomagjegyzéket vagy a számlát, a feladott ELÁBÉ megfelel a beszerzési ár mozgóátlagának. A két tranzakció még a készletzárás végrehajtása előtt is összekapcsolható egymással.

Ha egy bevételezési tranzakció egy kiadási tranzakcióhoz van megjelölve, a rendszer figyelmen kívül hagyja a cikkmodellcsoportban meghatározott értékelési módot, és ezeket a tranzakciókat egymással egyenlíti ki. A tranzakciókat kézzel is megjelölheti egy értékesítésirendelés-sorhoz **·** **\>** **az** Értékesítési rendelés részletei lapon, ha az Értékesítésirendelés-sorok gyorslapon a Készletjelölés adatokat választja. A nyitott bevételezési tranzakciókat megtekintheti **Jelölés** oldalon. Egy kiadási tranzakciót egy feladott készletkorrekció-naplóból származó készlettranzakciót egy nyitott bevételezési tranzakcióval is megfeleltethet vagy megjelölhet. A következő ábrán ezek a tranzakciók láthatók:

- 1a. Fizikai bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
- 1b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
- 2a. Fizikai bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
- 2b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 22,00 USD áron.
- 3a. Fizikai kiadás készletről, 1 mennyiséggel, USD 16.00 önköltségi áron (a pénzügyileg feladott tranzakciók mozgóátlaga).
- 3b. Pénzügyi kiadás készletről, 1 mennyiséggel, USD 16.00 önköltségi áron (a pénzügyileg feladott tranzakciók mozgóátlaga).
- 3c. A 3b pénzügyi készletről való kiadás a 2b pénzügyi készlet kiadására van bejelölve.
- 4a. Fizikai bevételezés készletre, 1 mennyiséggel, 25,00 USD áron.
- 5a. Fizikai bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 5b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 6a. Fizikai kiadás készletről, 1 mennyiséggel, USD 23.00 önköltségi áron (a pénzügyileg feladott tranzakciók mozgóátlaga)
- 7\. Készletzárást hajtanak végre. A FIFO módszert használó jelölési elv alapján a megjelölt tranzakciókat egymással szemben egyenlítik ki. Ebben a példában a 3b értékét 2b-t egyenlít ki, és a USD 6.00 feladása 3b-re, hogy az érték 3b értékre USD 22.00. Ebben a példában nincs további kiegyenlítés, mivel a lezárás csak a pénzügyileg frissített tranzakciókhoz hoz létre kiegyenlítéseket.

A következő diagram a FIFO-elvű készletmodell hatását ábrázolja olyan tranzakciósorozatra, ahol kiadások és bevételezések vannak egymáshoz rendelve.

![FIFO jelöléssel.](./media/fifo-with-marking.png)

**Jelmagyarázat**

- A készlettranzakciókat függőleges nyilak jelölik.
- A fizikai tranzakciókat rövidebb világosszürke nyilak ábrázolják.
- A pénzügyi tranzakciókat hosszabb fekete nyilak jelzik.
- A készletre való bevételezéseket az idősor fölötti függőleges nyilak jelölik.
- A készletről való kiadásokat az idősor alatti függőleges nyilak jelölik.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A diagram minden dátumát egy vékony fekete függőleges vonal választja el egymástól. A dátum a diagram alján látható.
- A készletzárásokat egy piros színű, szaggatott függőleges vonal ábrázolja.
- A készletzárás által végrehajtott elszámolásokat és jelöléseket piros átlós, szaggatott nyilak jelzik, amelyek bevételezésről kiadásra váltnak.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

---
title: LIFO tényleges értékkel és jelöléssel
description: A LIFO (Last in, first out) egy olyan készletmodell, amelynél a legutóbb bevételezett (legújabb) cikkeket adják ki elsőként. A program a készletbe a készlettranzakció dátuma alapján legutoljára bevételezett cikkekből egyenlíti ki a kiadásokat.
author: JennySong-SH
ms.date: 02/02/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 55021
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c1acc103291c5d648ac7e179a598348cd9cc2a93
ms.sourcegitcommit: 6b209919de39c15e0ebe4abc9cbcd30618f2af0b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/11/2022
ms.locfileid: "9135569"
---
# <a name="lifo-with-physical-value-and-marking"></a>LIFO tényleges értékkel és jelöléssel

[!include [banner](../includes/banner.md)]

A LIFO (Last in, first out) egy készletkezelés és értékelési módszer, amelyben a legutóbb termelt vagy beszerzett készletet elsőként értékesítik, használják vagy adják el. A Microsoft Dynamics 365 Supply Chain Management készletzárási folyamata során a rendszer kiegyenlítéseket hoz létre, ahol az utolsó bevételezést az első kiadáshoz stb. A kiegyenlítések és az egyeztetési elv a készlettranzakciók pénzügyi dátumán alapul. A kiegyenlítések és helyesbítések előzetes értékelése a készlet-újraszámítási folyamat futtatásával végezhető el.

A LIFO elv felülbírálható a készlettranzakciók megjelölésével, így egy adott cikkbevételezést egy adott kiadással szemben lehet kiegyenlíteni. Időszakos készletzárásra van szükség, ha a LIFO készletmodell segítségével kiegyenlítéseket lehet létrehozni, és a LIFO elv szerint módosítani lehet a problémák értékét. Amíg nem futtatja a készletzárási folyamatot, a kiadási tranzakciók értékének a tényleges és pénzügyi frissítések esetén a mozgóátlagon történik a program. Ha nem használ jelölést, akkor a rendszer a fizikai vagy pénzügyi frissítéskor kiszámítja a mozgóátlagot.

Az alábbi példák bemutatják a LIFO-elv alkalmazásának hatását három különböző konfiguráción:

- LIFO a **Tényleges értékkel együtt** beállítás nélkül
- LIFO a **Tényleges értékkel együtt** beállítással
- LIFO jelöléssel

## <a name="lifo-without-the-include-physical-value-option"></a>LIFO a Tényleges értékkel együtt beállítás nélkül

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
- 7\. Készletzárást hajtanak végre. A LIFO módszer alapján az első pénzügyi kiadást a legutóbb pénzügyileg frissített bevételezés stb. egyenlíti ki. Ebben a példában egy kiegyenlítés jön létre 5b és 3b között. A program USD 14.00 korrekciót a 3b értékre, az így kapott végső költséget pedig USD 30.00.

A következő illusztráció bemutatja, milyen hatása van a FIFO készletmodellnek erre a tranzakció sorozatra, ha a **Tényleges értékkel együtt** beállítás nincs beállítva.

![LIFO a Tényleges értékkel való be nem foglalva beállítás nélkül.](./media/lifo-without-including-physical-value.png)

**Jelmagyarázat**

- A készlettranzakciókat függőleges nyilak jelölik.
- A fizikai tranzakciókat rövidebb világosszürke nyilak ábrázolják.
- A pénzügyi tranzakciókat hosszabb fekete nyilak jelzik.
- A készletre való bevételezéseket a tengely fölötti függőleges nyilak jelzik.
- A készletről való problémákat a tengely alatti függőleges nyilak jelzik.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A diagram minden dátumát egy vékony fekete függőleges vonal választja el egymástól. A dátum a diagram alján látható.
- A készletzárásokat egy piros színű, szaggatott függőleges vonal ábrázolja.
- A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

## <a name="lifo-with-the-include-physical-value-option"></a>LIFO a Tényleges értékkel együtt beállítással

Ha a **Cikkmodellcsoportok** **lapon** be van jelölve a Tényleges értékkel együtt jelölőnégyzet, a rendszer fizikai és pénzügyi bevételezési tranzakciókat egyaránt használ a mozgóátlagon áteső önköltségi ár kiszámításához. Ahol lehetséges, a rendszer a fizikailag frissített kiadási tranzakciót is korrigálja. Ha a **Tényleges értékkel be** van véve jelölőnégyzet törölve, akkor a LIFO készletmodellt használó készletzárás csak a pénzügyileg frissített tranzakciókkal teszi a kiegyenlítést.

A következő ábrán ezek a tranzakciók láthatók:

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
- 7\. Készletzárást hajtanak végre. A LIFO módszer alapján az első pénzügyi kiadást a legutóbb pénzügyileg frissített bevételezés stb. egyenlíti ki. Ebben a példában egy kiegyenlítés jön létre 3b és 5b között. A program USD 14.00 korrekciót a 3b értékre, az így kapott végső költséget pedig USD 30.00. Ezenkívül a 6a. tranzakciót a 4a. bevételezési tranzakció költségére is módosítja a a tranzakció. A rendszer nem egyenlíti ki ezeket a tranzakciókat, mivel a bevételezés csak fizikailag történt meg, pénzügyileg azonban nem. Ehelyett a tényleges kiadási USD 1.33 csak az összeg korrekciója lesz feladva, és az így kapott helyesb USD 25.00.

A következő ábra bemutatja, milyen hatása van a LIFO készletmodellnek, ha a **Tényleges értékkel együtt** beállítás be van kapcsolva.

![LIFO a Tényleges értékkel együtt beállítással.](./media/lifo-with-included-physical-value.png)

**Jelmagyarázat**

- A készlettranzakciókat függőleges nyilak jelölik.
- A fizikai tranzakciókat rövidebb világosszürke nyilak ábrázolják.
- A pénzügyi tranzakciókat hosszabb fekete nyilak jelzik.
- A készletre való bevételezéseket a tengely fölötti függőleges nyilak jelzik.
- A készletről való problémákat a tengely alatti függőleges nyilak jelzik.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A diagram minden dátumát egy vékony fekete függőleges vonal választja el egymástól. A dátum a diagram alján látható.
- A készletzárásokat egy piros színű, szaggatott függőleges vonal ábrázolja.
- A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

## <a name="lifo-with-marking"></a>LIFO jelöléssel

A jelölés egy olyan folyamat, amellyel összekapcsolható egy kiadási tranzakció egy bevételezési tranzakcióval. A jelölés történhet a tranzakciók feladása előtt és után is. A jelölés használható a készlet pontos költségének megállapítására a tranzakció feladásakor vagy a készletzárás végrehajtásakor. Tegyük fel például, hogy az ügyfélszolgálati osztály elfogadott egy sürgős megrendelést egy fontos vevőtől. Mivel ez a rendelés sürgős rendelés, többe kell fizetnie a cikkért, hogy teljesíteni tudja az ügyfél kérését.

Meg kell győződnie arról, hogy a készletcikk költsége megjelenik az értékesítési rendelés számlájának árrésében vagy eladott áruk költségében (ELÁBÉ). A beszerzési rendelés feladásakor a készlet bevételezése 120,00 USD értéken történik. Ha ezt az értékesítési rendelési dokumentumot jelöléssel összekapcsolják a beszerzési rendeléssel még a csomagjegyzék vagy a számla feladása előtt, az ELÁBÉ nem a cikk jelenlegi mozgóátlaga lesz, hanem 120,00 USD. Ha még a jelölés előtt feladják a csomagjegyzéket vagy a számlát, a feladott ELÁBÉ megfelel a beszerzési ár mozgóátlagának.

A két tranzakció még a készletzárás végrehajtása előtt is összekapcsolható egymással.

Kiadási tranzakciót a tranzakció feladása előtt jelölhet hozzá egy nyugtához. Ezt a **jelölést** **\>** **az** Értékesítési rendelés részletei lap egyik értékesítésirendelés-sorában használhatja, ha az Értékesítésirendelés-sorok gyorslapon a Készletjelölés adatokat választja. A nyitott bevételezési tranzakciókat megtekintheti **Jelölés** oldalon.

Kiadási tranzakciót a tranzakció feladása után jelölhet hozzá egy nyugtához. Egyeztethet vagy megjelölhet egy kiadási tranzakciót egy nyílt nyugtájú tranzakcióhoz egy leltárazott cikk esetén, feladott készlethelyesbítési naplósorból.

A következő ábrán ezek a tranzakciók láthatók:

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
- 7\. Készletzárást hajtanak végre. A LIFO módszert használó jelölési elv alapján a megjelölt tranzakciókat egymással szemben egyenlítik ki. Ebben a példában a 3b értékét 2b-t egyenlít ki, és a USD 6.00 feladása 3b-re, hogy az érték 3b értékre USD 22.00. Ebben a példában nincs további kiegyenlítés, mivel a lezárás csak a pénzügyileg frissített tranzakciókhoz hoz létre kiegyenlítéseket.

Az új, mozgóátlagon alapuló önköltségi ár a pénzügyileg és fizikailag frissített tranzakciók átlagának, azaz 17,50 USD összegnek felel meg.

A következő diagram a LIFO-elvű készletmodell hatását ábrázolja olyan tranzakciósorozatra, ahol kiadások és bevételezések vannak egymáshoz rendelve.

![LIFO jelöléssel.](./media/lifo-with-marking.png)

**Jelmagyarázat**

- A készlettranzakciókat függőleges nyilak jelölik.
- A fizikai tranzakciókat rövidebb világosszürke nyilak ábrázolják.
- A pénzügyi tranzakciókat hosszabb fekete nyilak jelzik.
- A készletre való bevételezéseket a tengely fölötti függőleges nyilak jelzik.
- A készletről való problémákat a tengely alatti függőleges nyilak jelzik.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A diagram minden dátumát egy vékony fekete függőleges vonal választja el egymástól. A dátum a diagram alján látható.
- A készletzárásokat egy piros színű, szaggatott függőleges vonal ábrázolja.
- A készletzárás által végrehajtott elszámolásokat és jelöléseket piros átlós, szaggatott nyilak jelzik, amelyek bevételezésről kiadásra váltnak.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

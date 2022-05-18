---
title: LIFO dátum tényleges értékkel és jelöléssel
description: Az utolsóként be, elsőként ki (DÁTUM LIFO) egy készletmodell, amely a LIFO-elven alapul. A program a készletbe a készlettranzakció dátuma alapján legutoljára bevételezett cikkekből egyenlíti ki a kiadásokat. A LIFO dátum használatával, ha a kiadás előtt nincs bevételezés, a kiadás bármely a kiadás dátuma utáni bevételezés alapján lesz kiegyenlítve. Ha ugyanazzal a dátummal több kiadás van, akkor az az utolsó kiadás, utolsó bevételezés sorrendben egyenlíthető ki.
author: JennySong-SH
ms.date: 02/21/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 51592
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8ca344e6ca81814e787046f6ece97625d035346d
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671450"
---
# <a name="lifo-date-with-physical-value-and-marking"></a>LIFO dátum tényleges értékkel és jelöléssel

[!include [banner](../includes/banner.md)]

Az utolsóként be, elsőként ki (LIFO dátum) egy készletkezelés és értékelési módszer, amelyben az utoljára termelt vagy beszerzett készletet elsőként értékesítik, használják vagy adják el. A Microsoft Dynamics 365 Supply Chain Management készletzárási folyamata során a rendszer kiegyenlítéseket hoz létre, ahol a legutóbbi bevételezést minden egyes megadott dátum első kiadásával, a legrégebbi dátummal kezdve stb. Az utolsóként be, elsőként ki (DÁTUM LIFO) készletmodell használata esetén, ha a kiadás előtt nincs bevételezés, akkor a kiadást bármely a kiadás dátuma utáni bevételezés alapján egyenlíti ki a rendszer. A kiegyenlítések és az egyeztetési elv a készlettranzakciók pénzügyi dátumán alapul. Ha több kiadás van ugyanazon a dátumon, akkor az utolsó kiadás, utolsó bevételezés sorrendben egyenlítik ki őket. A kiegyenlítések és helyesbítések előzetes értékelése a készlet-újraszámítási folyamat futtatásával végezhető el.

A LIFO dátumszabály felülbírálható a készlettranzakciók megjelölésével, így egy adott cikkbevételezést egy adott kiadással szemben lehet kiegyenlíteni. Időszakos készletzárásra van szükség, ha a LIFO dátum készletmodellel kiegyenlítéseket lehet létrehozni, és a LIFO elv szerint módosítani lehet a problémák értékét. Amíg nem futtatja a készletzárási folyamatot, a kiadási tranzakciók értékének a tényleges és pénzügyi frissítések esetén a mozgóátlagon történik a program. Ha nem használ jelölést, akkor a rendszer a fizikai vagy pénzügyi frissítéskor kiszámítja a mozgóátlagot.

A DÁTUM LIFO készletmodell használata esetében javasoljuk, hogy időszaki készletzárást követően.

Az alábbi példák bemutatják a DÁTUM LIFO-dátum használatának hatását három konfigurációban:

- LIFO dátum a Tényleges értékkel **való be nem foglalva beállítás** nélkül
- LIFO dátum a Tényleges értékkel **együtt beállítással**
- LIFO dátum jelöléssel

## <a name="lifo-date-without-the-include-physical-value-option"></a>LIFO dátum a Tényleges értékkel való be nem foglalva beállítás nélkül

Ebben a példában a cikkmodellcsoport nem tartalmazza a tényleges értéket. A következő ábrán ezek a tranzakciók láthatók:

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
- 7\. Készletzárást hajtanak végre. A LIFO dátum módszer alapján az első pénzügyi kiadást az első dátumtól kezdődően utoljára frissített bevételezésekkel kell kiegyenlíteni, stb. Ebben a példában egy kiegyenlítés jön létre 3b és 2b között. A program USD 6.00 korrekciót a 3b értékre, az így kapott végső költséget pedig USD 22.00.

A következő ábra a dátum LIFO készletmodell hatását mutatja be, **ha a Tényleges értékkel** együtt beállítás nincs használva.

![LIFO dátum a Tényleges értékkel való be nem foglalva beállítás nélkül.](media/lifo-date-without-include-physical-value.png)

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

## <a name="lifo-date-with-the-include-physical-value-option"></a>LIFO dátum a Tényleges értékkel együtt beállítással

Ha a **Cikkmodellcsoportok** **lapon** be van jelölve a Tényleges értékkel együtt jelölőnégyzet, a rendszer fizikai és pénzügyi bevételezési tranzakciókat egyaránt használ a mozgóátlagon áteső önköltségi ár kiszámításához. Ahol lehetséges, a rendszer a fizikailag frissített kiadási tranzakciót is korrigálja. Ha a **Tényleges értékkel be** van véve jelölőnégyzet törölve, akkor a LIFO dátum készletmodellt használó készletzárás csak a pénzügyileg frissített tranzakciókkal teszi a kiegyenlítést.

Ebben a példában a cikkmodellcsoport tartalmazza a tényleges értéket. 

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
- 7\. Készletzárást hajtanak végre. A LIFO dátum módszer alapján az első pénzügyi kiadást az első napon kezdődő minden egyes dátumon a legutóbb pénzügyileg frissített bevételezésekkel stb. egyenlíti ki a program. Ebben a példában egy kiegyenlítés jön létre 2b és 3b között. A program USD 6.00 korrekciót a 3b értékre, az így kapott végső költséget pedig USD 22.00. Ezenkívül a 6a. tranzakciót az 5b bevételezési tranzakció költségére módosítja a a tranzakció. A rendszer nem egyenlíti ki ezeket a tranzakciókat, mert a bevételezés fizikailag frissítve van, de pénzügyileg nem. Ehelyett a tényleges kiadási USD 6.33 csak a tényleges kiadási tranzakcióhoz ad fel korrekciót, és az így kapott helyesb USD 30.00.

A következő ábra bemutatja, milyen hatása van a LIFO dátum készletmodellnek, ha a **Tényleges értékkel együtt** beállítás be van kapcsolva.

![LIFO dátum a Tényleges értékkel együtt beállítással.](media/lifo-date-with-include-physical-value.png)

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

## <a name="lifo-date-with-marking"></a>LIFO dátum jelöléssel

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
- 3c. A 3b pénzügyi készlet kiadását egy 1b pénzügyi készlet kiadására jelölték.
- 4a. Fizikai bevételezés készletre, 1 mennyiséggel, 25,00 USD áron.
- 5a. Fizikai bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 5b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 6a. Fizikai kiadás készletről, 1 mennyiséggel, USD 23.00 önköltségi áron (a pénzügyileg feladott tranzakciók mozgóátlaga)
- 7\. Készletzárást hajtanak végre. A LIFO dátum módszert használó jelölési elv alapján a megjelölt tranzakciókat egymással szemben egyenlítik ki. Ebben a példában a 3b értékét 1b-el egyenlítik ki, és egy -6,00 USD értékű korrekciót ad fel a 3b részére, hogy az értéket USD 10.00. Ebben a példában nincs további kiegyenlítés, mivel a lezárás csak a pénzügyileg frissített tranzakciókhoz hoz létre kiegyenlítéseket.

Az alábbi ábra a dátum LIFO készletmodell hatását mutatja be a bevételek és a bevételek közötti jelölés használata során. 

![LIFO dátum jelöléssel.](media/lifo-date-with-marking.png)

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

---
title: LIFO tényleges értékkel és jelöléssel
description: A LIFO (Last in, first out) egy olyan készletmodell, amelynél a legutóbb bevételezett (legújabb) cikkeket adják ki elsőként. A program a készletbe a készlettranzakció dátuma alapján legutoljára bevételezett cikkekből egyenlíti ki a kiadásokat.
author: AndersGirke
ms.date: 02/02/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 55021
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fd57d58aa91aa87b1c2feff52a568296fc18ed9b
ms.sourcegitcommit: fefe93f3f44d8aa0b7e6d54cc4a3e5eca6e64feb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2022
ms.locfileid: "8092164"
---
# <a name="lifo-with-physical-value-and-marking"></a>LIFO tényleges értékkel és jelöléssel

[!include [banner](../includes/banner.md)]

Utolsó be, első ki (LIFO) egy készletkezelési és értékelési módszer, amelynek során az utoljára előállított vagy beszerzett készletet először értékesítik, használják fel vagy dobják ki. A Microsoft leltárbezárási folyamata alatt Dynamics 365 Supply Chain Management, a rendszer olyan elszámolásokat hoz létre, ahol az utolsó bevételt az első kiadással párosítja, és így tovább. Az elszámolások és az egyeztetési elv a készlettranzakciók pénzügyi dátumán alapul. Az elszámolások, kiigazítások előzetes felmérése a készlet-újraszámítási folyamat lefuttatásával végezhető el.

A LIFO-elvet felülírhatja a készlettranzakciók megjelölésével, így egy adott cikkbeérkezés egy adott probléma ellenében kerül kiegyenlítésre. Rendszeres leltárbezárásra van szükség, ha a LIFO leltári modellt használja az elszámolások létrehozásához és a kibocsátások értékének a LIFO elv szerinti beállításához. Amíg le nem futja a készletbezárási folyamatot, a kiadási tranzakciók értéke a fizikai és pénzügyi frissítések bekövetkezésekor futó átlagon történik. Hacsak nem használ jelölést, a futó átlagot a rendszer a fizikai vagy pénzügyi frissítés végrehajtásakor számítja ki.

Az alábbi példák bemutatják a LIFO-elv alkalmazásának hatását három különböző konfiguráción:

- LIFO a **Tényleges értékkel együtt** beállítás nélkül
- LIFO a **Tényleges értékkel együtt** beállítással
- LIFO jelöléssel

## <a name="lifo-without-the-include-physical-value-option"></a>LIFO a Tényleges értékkel együtt beállítás nélkül

Ebben a példában a **Tartalmazza a fizikai értéket** A kiadott termék cikkmodellcsoportjában a jelölőnégyzet törlődik. A következő ábrán ezek a tranzakciók láthatók:

- 1a. Fizikai bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
- 1b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
- 2a. Fizikai bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
- 2b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 22,00 USD áron.
- 3a. Készlet fizikai kiadása 1 darab mennyiséghez USD 16.00 (a pénzügyileg könyvelt tranzakciók futó átlaga) költségáron.
- 3b. Pénzügyi készletkiadás 1 darabos mennyiséghez, USD 16.00 önköltségi áron (a pénzügyileg könyvelt tranzakciók futó átlaga).
- 4a. Fizikai bevételezés készletre, 1 mennyiséggel, 25,00 USD áron.
- 5a. Fizikai bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 5b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 6a. Készlet fizikai probléma 1 darabos mennyiségnél USD 23.00 önköltségi áron (a pénzügyileg könyvelt tranzakciók futó átlaga)
- 7\. Készletzárást hajtanak végre. A LIFO módszer alapján az első pénzügyileg frissített kiadás az utolsó pénzügyileg frissített bizonylattal kerül kiegyenlítésre, és így tovább. Ebben a példában egy település jön létre 5b és 3b között. A USD 14.00 módosítása 3b lesz, és a végső költség USD 30.00 lesz.

A következő illusztráció bemutatja, milyen hatása van a FIFO készletmodellnek erre a tranzakció sorozatra, ha a **Tényleges értékkel együtt** beállítás nincs beállítva.

![LIFO a Fizikai érték megadása opció nélkül.](./media/lifo-without-including-physical-value.png)

**Jelmagyarázat**

- A készlettranzakciókat függőleges nyilak jelölik.
- A fizikai tranzakciókat rövidebb világosszürke nyilak jelölik.
- A pénzügyi tranzakciókat hosszabb fekete nyilak jelölik.
- A készletbe vett bevételeket a tengely felett függőleges nyilak jelzik.
- A készleten kívüli problémákat a tengely alatti függőleges nyilak jelzik.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A diagramon minden dátumot vékony fekete függőleges vonal választ el. A dátum a diagram alján van feltüntetve.
- A készletzárásokat egy piros függőleges szaggatott vonal jelöli.
- A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

## <a name="lifo-with-the-include-physical-value-option"></a>LIFO a Tényleges értékkel együtt beállítással

Ha a **Tartalmazza a fizikai értéket** jelölőnégyzet be van jelölve egy elemhez a **Tételmodell csoportok** oldalon a rendszer fizikai és pénzügyi nyugtatranzakciókat is felhasznál a folyó átlagos önköltségi ár kiszámításához. Adott esetben a rendszer a fizikailag frissített kiadási tranzakciót is módosítja. Amikor az **Tartalmazza a fizikai értéket** A jelölőnégyzet törlődik, a LIFO leltármodellt használó készletlezárás csak a pénzügyileg frissített tranzakciókra hajtja végre az elszámolásokat.

A következő ábrán ezek a tranzakciók láthatók:

- 1a. Fizikai bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
- 1b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
- 2a. Fizikai bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
- 2b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 22,00 USD áron.
- 3a. Készlet fizikai kiadása 1 darab mennyiséghez USD 16.00 önköltségi áron (a fizikailag és pénzügyileg könyvelt tranzakciók futó átlaga).
- 3b. Pénzügyi készletkiadás 1 darabos mennyiséghez, USD 16.00 önköltségi áron (a fizikailag és pénzügyileg könyvelt tranzakciók futó átlaga).
- 4a. Fizikai bevételezés készletre, 1 mennyiséggel, 25,00 USD áron.
- 5a. Fizikai bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 5b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 6a. Készlet fizikai kiadása 1 darab mennyiséghez USD 23.67 önköltségi áron (a fizikailag és pénzügyileg könyvelt tranzakciók futó átlaga).
- 7\. Készletzárást hajtanak végre. A LIFO módszer alapján az első pénzügyileg frissített kiadás az utolsó pénzügyileg frissített bizonylattal kerül kiegyenlítésre, és így tovább. Ebben a példában egy település jön létre 3b és 5b között. A USD 14.00 módosítása 3b lesz, és a végső költség USD 30.00 lesz. Ezenkívül a 6a tranzakció a 4a átvételi tranzakciós költséghez lesz igazítva. A rendszer nem egyenlíti ki ezeket a tranzakciókat, mivel a bevételezés csak fizikailag történt meg, pénzügyileg azonban nem. Ehelyett csak a USD 1.33 korrekció kerül feladásra a fizikai kiadási tranzakcióban, és az ebből eredő korrigált költség USD 25.00 lesz.

A következő ábra bemutatja, milyen hatása van a LIFO készletmodellnek, ha a **Tényleges értékkel együtt** beállítás be van kapcsolva.

![LIFO a Fizikai érték megadása opcióval.](./media/lifo-with-included-physical-value.png)

**Jelmagyarázat**

- A készlettranzakciókat függőleges nyilak jelölik.
- A fizikai tranzakciókat rövidebb világosszürke nyilak jelölik.
- A pénzügyi tranzakciókat hosszabb fekete nyilak jelölik.
- A készletbe vett bevételeket a tengely felett függőleges nyilak jelzik.
- A készleten kívüli problémákat a tengely alatti függőleges nyilak jelzik.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A diagramon minden dátumot vékony fekete függőleges vonal választ el. A dátum a diagram alján van feltüntetve.
- A készletzárásokat egy piros függőleges szaggatott vonal jelöli.
- A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

## <a name="lifo-with-marking"></a>LIFO jelöléssel

A jelölés egy olyan folyamat, amellyel összekapcsolható egy kiadási tranzakció egy bevételezési tranzakcióval. A jelölés történhet a tranzakciók feladása előtt és után is. A jelölés használható a készlet pontos költségének megállapítására a tranzakció feladásakor vagy a készletzárás végrehajtásakor. Tegyük fel például, hogy az ügyfélszolgálati osztály elfogadott egy sürgős megrendelést egy fontos vevőtől. Mivel ez a rendelés egy gyorsrendelés, többet kell fizetnie a tételért, hogy teljesítse az ügyfél kérését.

Győződjön meg arról, hogy a készletcikk költsége megjelenik az értékesítési rendelési számlán az árrésben vagy az eladott áruk költségében (COGS). A beszerzési rendelés feladásakor a készlet bevételezése 120,00 USD értéken történik. Ha ezt az értékesítési rendelési dokumentumot jelöléssel összekapcsolják a beszerzési rendeléssel még a csomagjegyzék vagy a számla feladása előtt, az ELÁBÉ nem a cikk jelenlegi mozgóátlaga lesz, hanem 120,00 USD. Ha még a jelölés előtt feladják a csomagjegyzéket vagy a számlát, a feladott ELÁBÉ megfelel a beszerzési ár mozgóátlagának.

A két tranzakció még a készletzárás végrehajtása előtt is összekapcsolható egymással.

Kiadási tranzakciót a tranzakció feladása előtt jelölhet hozzá egy nyugtához. Ezt a jelölést az értékesítési rendelés sorából teheti meg a **Az értékesítési rendelés részletei** oldal kiválasztásával **Leltár \> Jelzés** a **Értékesítési rendelési sorok** FastTab. A nyitott bevételezési tranzakciókat megtekintheti **Jelölés** oldalon.

Kiadási tranzakciót a tranzakció feladása után jelölhet hozzá egy nyugtához. Egyeztethet vagy megjelölhet egy kiadási tranzakciót egy nyílt nyugtájú tranzakcióhoz egy leltárazott cikk esetén, feladott készlethelyesbítési naplósorból.

A következő ábrán ezek a tranzakciók láthatók:

- 1a. Fizikai bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
- 1b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
- 2a. Fizikai bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
- 2b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 22,00 USD áron.
- 3a. Készlet fizikai kiadása 1 darab mennyiséghez USD 16.00 (a pénzügyileg könyvelt tranzakciók futó átlaga) költségáron.
- 3b. Pénzügyi készletkiadás 1 darabos mennyiséghez, USD 16.00 önköltségi áron (a pénzügyileg könyvelt tranzakciók futó átlaga).
- 3c. A 3b készlet pénzügyi kibocsátása a 2b készlet pénzügyi kiadásaként van megjelölve.
- 4a. Fizikai bevételezés készletre, 1 mennyiséggel, 25,00 USD áron.
- 5a. Fizikai bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 5b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 6a. Készlet fizikai probléma 1 darabos mennyiségnél USD 23.00 önköltségi áron (a pénzügyileg könyvelt tranzakciók futó átlaga)
- 7\. Készletzárást hajtanak végre. A LIFO módszert alkalmazó jelölési elv alapján a megjelölt tranzakciók elszámolásra kerülnek egymással szemben. Ebben a példában a 3b kiegyenlítésre kerül a 2b-vel szemben, és a USD 6.00 korrekciója elküldésre kerül a 3b-re, hogy az érték a USD 22.00 értékre kerüljön. Ebben a példában nem történik további elszámolás, mert a zárás csak a pénzügyileg frissített tranzakciókra hoz létre elszámolásokat.

Az új, mozgóátlagon alapuló önköltségi ár a pénzügyileg és fizikailag frissített tranzakciók átlagának, azaz 27,50 USD összegnek felel meg.

A következő diagram a LIFO-elvű készletmodell hatását ábrázolja olyan tranzakciósorozatra, ahol kiadások és bevételezések vannak egymáshoz rendelve.

![LIFO jelöléssel.](./media/lifo-with-marking.png)

**Jelmagyarázat**

- A készlettranzakciókat függőleges nyilak jelölik.
- A fizikai tranzakciókat rövidebb világosszürke nyilak jelölik.
- A pénzügyi tranzakciókat hosszabb fekete nyilak jelölik.
- A készletbe vett bevételeket a tengely felett függőleges nyilak jelzik.
- A készleten kívüli problémákat a tengely alatti függőleges nyilak jelzik.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A diagramon minden dátumot vékony fekete függőleges vonal választ el. A dátum a diagram alján van feltüntetve.
- A készletzárásokat egy piros függőleges szaggatott vonal jelöli.
- A leltárzárással végrehajtott elszámolásokat és jelöléseket piros, átlósan szaggatott nyilak jelzik, amelyek a nyugtától a kiadásig terjednek.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

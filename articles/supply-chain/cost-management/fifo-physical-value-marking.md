---
title: FIFO tényleges értékkel és jelöléssel
description: A FIFO-elv (First in, First out) egy készletmodell, amelyben az elsőként bevételezett cikkek kerülnek először kiadásra. A készletből történő pénzügyi kiadások a készlettranzakciók pénzügyi dátuma alapján az első pénzügyi készletbevételezésekkel vannak kiegyenlítve.
author: AndersGirke
ms.date: 02/02/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 54682
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5280498a23df26873dda1f380f686796f5e1055f
ms.sourcegitcommit: fefe93f3f44d8aa0b7e6d54cc4a3e5eca6e64feb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2022
ms.locfileid: "8092140"
---
# <a name="fifo-with-physical-value-and-marking"></a>FIFO tényleges értékkel és jelöléssel

[!include [banner](../includes/banner.md)]


A FIFO egy készletkezelési és -értékelési módszer, ahol az elsőként előállított vagy beszerzett készletet először értékesítik, használják fel vagy dobják ki. A Microsoft leltárbezárási folyamata alatt Dynamics 365 Supply Chain Management, a rendszer olyan elszámolásokat hoz létre, ahol az első bevételt az első kiadással egyezteti, és így tovább.

Az elszámolások és az egyeztetési elv a készlettranzakciók pénzügyi dátumán alapul. Az elszámolások, kiigazítások előzetes felmérése a készlet-újraszámítási folyamat lefuttatásával végezhető el.

A FIFO-elvet felülírhatja a készlettranzakciók megjelölésével, így egy adott cikkbeérkezés egy adott probléma ellenében kerül kiegyenlítésre. Rendszeres leltárzárásra van szükség, ha a FIFO leltári modellt használja az elszámolások létrehozásához és a kibocsátások értékének FIFO elv szerinti beállításához. Amíg le nem futja a készletbezárási folyamatot, a kiadási tranzakciók értéke a fizikai és pénzügyi frissítések bekövetkezésekor futó átlagon történik. Hacsak nem használ jelölést, a futó átlagot a rendszer a fizikai vagy pénzügyi frissítés végrehajtásakor számítja ki. Az alábbi példák bemutatják a FIFO-elv alkalmazásának hatását három különböző konfiguráción:

- FIFO a **Tényleges értékkel együtt** beállítás nélkül
- FIFO a **Tényleges értékkel együtt** beállítással
- FIFO jelöléssel

## <a name="fifo-without-the-include-physical-value-option"></a>FIFO a Tényleges értékkel együtt beállítás nélkül

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
- 7\. Készletzárást hajtanak végre. A FIFO módszer alapján az első pénzügyileg frissített kiadás az első pénzügyileg frissített bizonylat ellenében kerül kiegyenlítésre, és így tovább. Ebben a példában egy település jön létre 1b és 3b között. –6,00 USD korrekciót hajtanak végre a 3b-nél, és az ebből eredő végső költség USD 10.00 lesz.

Az önköltség új mozgóátlaga a pénzügyi tranzakciók átlagát tükrözi. A következő ábra bemutatja, milyen hatása van a FIFO készletmodellnek, ha a **Tényleges értékkel együtt** beállítást nincs beállítva.

![FIFO a Fizikai érték megadása opció nélkül.](./media/fifo-without-include-physical-value.png)

**Jelmagyarázat**

- A készlettranzakciókat függőleges nyilak jelölik.
- A fizikai tranzakciókat rövidebb világosszürke nyilak jelölik.
- A pénzügyi tranzakciókat hosszabb fekete nyilak jelölik.
- A készletre való bevételezéseket az idősor fölötti függőleges nyilak jelölik.
- A készletről való kiadásokat az idősor alatti függőleges nyilak jelölik.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A diagramon minden dátumot vékony fekete függőleges vonal választ el. A dátum a diagram alján van feltüntetve.
- A készletzárásokat egy piros függőleges szaggatott vonal jelöli.
- A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

## <a name="fifo-with-the-include-physical-value-option"></a>FIFO a Tényleges értékkel együtt beállítással

Ha a **Tartalmazza a fizikai értéket** jelölőnégyzet be van jelölve egy elemhez a **Tételmodell csoport** oldalon a rendszer fizikai és pénzügyi nyugtatranzakciókat is felhasznál a folyó átlagos önköltségi ár kiszámításához. Adott esetben a rendszer a fizikailag frissített kiadási tranzakciót is módosítja. A FIFO leltármodellt használó készletzárás csak a pénzügyileg frissített tranzakciókra hajtja végre az elszámolásokat. A következő ábrán ezek a tranzakciók láthatók:

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
- 7\. Készletzárást hajtanak végre. A FIFO módszer alapján az első pénzügyileg frissített kiadás az első pénzügyileg frissített bizonylat ellenében kerül kiegyenlítésre, és így tovább. Ebben a példában egy település jön létre 1b és 3b között. –6,00 USD korrekciót hajtanak végre a 3b-nél, és az ebből eredő végső költség USD 10.00 lesz. Ezenkívül a 6a tranzakció a 2b átvételi tranzakciós költséghez lesz igazítva. A rendszer nem egyenlíti ki ezeket a tranzakciókat, mivel a bevételezés csak fizikailag történt meg, pénzügyileg azonban nem. Ehelyett csak -1,67 USD értékű korrekció jelenik meg a fizikai kibocsátási tranzakcióban, és az ebből eredő korrigált költség USD 22.00 lesz.

![FIFO a Fizikai érték megadása opcióval.](./media/fifo-with-include-physical-value.png)

Figyelje meg, hogy a készletbezárási folyamat futtatásának eredménye ugyanaz, függetlenül attól, hogy kiválasztja-e a **Tartalmazza a fizikai értéket** opció a **Tételmodell csoport** oldalon. A **Tartalmazza a fizikai értéket** opció csak a futóátlagot érinti.

**Jelmagyarázat**

- A készlettranzakciókat függőleges nyilak jelölik.
- A fizikai tranzakciókat rövidebb világosszürke nyilak jelölik.
- A pénzügyi tranzakciókat hosszabb fekete nyilak jelölik.
- A készletre való bevételezéseket az idősor fölötti függőleges nyilak jelölik.
- A készletről való kiadásokat az idősor alatti függőleges nyilak jelölik.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A diagramon minden dátumot vékony fekete függőleges vonal választ el. A dátum a diagram alján van feltüntetve.
- A készletzárásokat egy piros függőleges szaggatott vonal jelöli.
- A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

## <a name="fifo-with-marking"></a>FIFO jelöléssel

A jelölés egy olyan folyamat, amellyel összekapcsolható egy kiadási tranzakció egy bevételezési tranzakcióval. A jelölés történhet a tranzakciók feladása előtt és után is. A jelölés használható a készlet pontos költségének megállapítására a tranzakció feladásakor vagy a készletzárás végrehajtásakor.

Tegyük fel például, hogy az ügyfélszolgálati osztály elfogadott egy sürgős megrendelést egy fontos vevőtől. Mivel ez a rendelés egy sürgősségi megrendelés, többet kell fizetnie ezért a tételért, hogy teljesítse az ügyfél kérését. Győződjön meg arról, hogy a készletcikk költsége megjelenik az értékesítési rendelési számlán az árrésben vagy az eladott áruk költségében (COGS). A beszerzési rendelés feladásakor a készlet bevételezése 120,00 USD értéken történik. Ha az értékesítési rendelés bizonylatát a szállítólevél vagy számla feladása előtt megjelölik a beszerzési rendelésen, akkor az ELÁBÉ USD 120.00 lesz, nem pedig a cikk aktuális folyó átlagköltsége. Ha még a jelölés előtt feladják a csomagjegyzéket vagy a számlát, a feladott ELÁBÉ megfelel a beszerzési ár mozgóátlagának. A két tranzakció még a készletzárás végrehajtása előtt is összekapcsolható egymással.

Ha egy nyugta-tranzakciót kibocsátási tranzakciónak jelölünk, akkor a cikkmodell-csoportban meghatározott értékelési módszer figyelmen kívül marad, és a rendszer ezeket a tranzakciókat egymásnak számolja el. Manuálisan megjelölhet egy tranzakciót az értékesítési rendelés sorához a következő oldalon **Az értékesítési rendelés részletei** oldal kiválasztásával **Leltár \> Jelzés** a **Értékesítési rendelési sorok** FastTab. A nyitott bevételezési tranzakciókat megtekintheti **Jelölés** oldalon. Kibocsátási tranzakciót egyeztethet vagy megjelölhet egy nyitott nyugtatranzakcióval egy leltározott cikkhez egy feladott készletkorrekciós naplóból. A következő ábrán ezek a tranzakciók láthatók:

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
- 7\. Készletzárást hajtanak végre. A FIFO módszert alkalmazó jelölési elv alapján a megjelölt tranzakciók egymással szemben kerülnek elszámolásra. Ebben a példában a 3b kiegyenlítésre kerül a 2b-vel szemben, és a USD 6.00 korrekciója elküldésre kerül a 3b-re, hogy az érték a USD 22.00 értékre kerüljön. Ebben a példában nem történik további elszámolás, mert a zárás csak a pénzügyileg frissített tranzakciókra hoz létre elszámolásokat.

A következő diagram a FIFO-elvű készletmodell hatását ábrázolja olyan tranzakciósorozatra, ahol kiadások és bevételezések vannak egymáshoz rendelve.

![FIFO jelöléssel.](./media/fifo-with-marking.png)

**Jelmagyarázat**

- A készlettranzakciókat függőleges nyilak jelölik.
- A fizikai tranzakciókat rövidebb világosszürke nyilak jelölik.
- A pénzügyi tranzakciókat hosszabb fekete nyilak jelölik.
- A készletre való bevételezéseket az idősor fölötti függőleges nyilak jelölik.
- A készletről való kiadásokat az idősor alatti függőleges nyilak jelölik.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A diagramon minden dátumot vékony fekete függőleges vonal választ el. A dátum a diagram alján van feltüntetve.
- A készletzárásokat egy piros függőleges szaggatott vonal jelöli.
- A leltárzárással végrehajtott elszámolásokat és jelöléseket piros, átlósan szaggatott nyilak jelzik, amelyek a nyugtától a kiadásig terjednek.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

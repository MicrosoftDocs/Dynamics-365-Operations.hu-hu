---
title: Készlettranzakció részletei
description: Ez a témakör áttekintést nyújt a Tranzakciók részletei lapról, amely a kiválasztott készlettranzakció részleteit mutatja be.
author: rachel-profitt
ms.date: 04/25/2022
ms.topic: article
ms.search.form: InventTrans, InventTransDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-04-25
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: fd1416f21ce15dc832dd41ea4110c93bf5bb41a2
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735877"
---
# <a name="inventory-transaction-details"></a>Készlettranzakció részletei

A Tranzakciók **részletei lapon** megtekintheti a kiválasztott készlettranzakciók részleteit.

## <a name="open-the-transaction-details-page"></a>A Tranzakció részletei lap megnyitása

A Tranzakciók részletei **lap megnyitásához** kövesse ezeket a lépéseket.

1. Ugrás a Készletkezelés **– \> Lekérdezések és jelentések tranzakcióihoz \>**.
1. Válassza ki a vizsgálni kívánt tranzakciót.
1. A munkaablakban válassza ki a tranzakció **részleteit**.

## <a name="fasttabs-overview"></a>FastTabs – áttekintés

A **Tranzakciók részletei** lap több FastTabs gyorslapra van osztva. A következő táblázat ismerteti az egyes gyors gyorstáblák célját.

| Gyorslap | Leírás |
|---|---|
| Általános | Ez a gyorsáb a kiválasztott készlettranzakcióval kapcsolatos alapvető információkat jeleníti meg. A Készlettranzakciók **lapon** megjelenő mezők mellett további, a témakörben később ismertetett mezőket is tartalmaz. |
| Frissítések | Ez a gyorsáb a kiválasztott készlettranzakció fizikai, pénzügyi és kiegyenlítési aspektusával kapcsolatos adatokat jeleníti meg. A tranzakció aktuális állapotától függően egyes mezők üresen maradnak. Ezeket a mezőket azonban automatikusan beállítja a rendszer a tranzakciók feladása során. A Gyorslap **a** Készlettranzakciók lapon megjelenő mezők mellett további, a témakörben később ismertetett mezőket is tartalmaz. |
| Főkönyvi feladások | Ez a gyorsjelentés mutatja a feladás típusát és a főkönyvi számlát, amely a kiválasztott készlettranzakcióval kapcsolatos tényleges frissítéshez, pénzügyi frissítéshez, tényleges bevételhez, fizikai költségekhez, pénzügyi bevételhez és pénzügyi költségekhez használatos. |
| Hivatkozások | Ez a gyorsáb további adatokat mutat a kijelölt készlettranzakciót létrehozó forrástranzakcióról. Ezek az adatok például a beszerzési vagy értékesítési rendelés adatait is tartalmazhatják. |
| Kapcsolódó információ | Ez a gyorsáb további adatokat tartalmaz a kijelölt készlettranzakcióról. Előfordulhat, hogy ezek a mezők nincsenek beállítva, ha nem használ bizonyos funkciókat, például beszerzési kategóriákat vagy projekteket. |
| Pénzügyi dimenziók - tényleges | Ez a gyorsáb a tényleges frissítés feladása során használt pénzügyi dimenzióértékeket jeleníti meg. Ha a tényleges frissítés még nincs feladva, a mezők üresen maradnak. |
| Pénzügyi dimenziók - pénzügyi | Ez a gyorsáb a pénzügyi frissítés feladása során használt pénzügyi dimenzióértékeket jeleníti meg. Ha a pénzügyi frissítés még nincs feladva, a mezők üresen maradnak. |
| Készletdimenziók | Ez a gyorsáb a kiválasztott készlettranzakcióhoz rendelt készletdimenzió-értékeket jeleníti meg. Ilyen érték például a telephely, a raktár, a méret, a szín, a konfiguráció, a hely, a kötegszám, a sorozatszám, a készletállapot, az azonosítótábla és a tulajdonos. |

## <a name="fields-on-the-general-fasttab"></a>Mezők az Általános gyorsábon

A következő táblázat olyan **mezőket** ír le az általános gyorslapon, amelyek nem jelennek meg a **Készlettranzakciók lapon**.

| Mező | Leírás |
|---|---|
| Fél | A kiválasztott készlettranzakcióhoz kapcsolódó fél neve. Például a beszerzési rendelés tranzakciója a beszerzési rendelésen a szállító nevét, az értékesítési rendelés tranzakciója pedig a vevő nevét mutatja. Ez a mező nem érhető el minden készlettranzakció-típus esetében. |
| Készlethivatkozás | Ha a kiválasztott készlettranzakcióhoz másik készlettranzakció kapcsolódik, a másik tranzakció típusa. Ha például egy beszerzési rendelés egy értékesítési rendeléssel szemben van megjelölve, **a** beszerzési rendelés tranzakció készlethivatkozás mezőjének beállítása Értékesítési *rendelés* lesz. A közvetlen kiszállításos rendelések és a vállalatközi rendelések esetén a jelölés automatikusan történik. Ha az *elszámolóárastól* *és* a mozgó átlagtól különböző költségszámítási módszerrel alkalmaz jelölést, a rendszer a megjelölt pontos tranzakciókra vonatkozó kiegyenlítéseket és helyesbítéseket hoz létre. Ily módon el lehet érni a "tényleges" költségszámítást, amely felülbírálja az első be, az első ki (FIFO) logikáját. utolsóként be, elsőként ki (LIFO); vagy súlyozott átlag. |
| Készletszám | A kiválasztott készlettranzakcióhoz kapcsolódó konkrét tranzakció. Ha például egy beszerzési rendelés egy értékesítési rendeléssel szemben van megjelölve, **a** beszerzési rendelés tranzakció készletszám mezőjének beállítása az értékesítési rendelés száma lesz. |
| Projektazonosító | Ha a kiválasztott készlettranzakció egy projekthez kapcsolódik, ez a mező a projektszámra van beállítva. |
| Adagazonosító | A kijelölt készlettranzakcióhoz a rendszer által hozzárendelt egyedi tételazonosító. |
| Hivatkozási adag | Ha a kiválasztott készlettranzakcióhoz másik készlettranzakció kapcsolódik, a másik tranzakció tételazonosítója. Ha például egy beszerzési rendelés egy értékesítési rendeléssel szemben van megjelölve, **·** **a** beszerzési rendelés tranzakciójának Hivatkozási tétel mezője az értékesítési rendelési sor készlettranzakciójának készletazonosító értéke lesz. |
| Dimenziószám | Egyedi azonosító, amely a kiválasztott készlettranzakcióhoz rendelt összes készletdimenzió-érték kombinációját jelöli. |
| Nyitott érték | Ez az érték jelzi, hogy a kiválasztott készlettranzakció ki van-e egyenlítve a készletzárási folyamat során. Ha a mező igenre van *állítva*, akkor a tranzakció nincs kiegyenlítve. |
| Várható dátum | Bevételezési tranzakciók esetében az a dátum, amikorra a készletbevételezés várható. Ez a mező például egy készletzárolási rendelés várható kézhezvételi dátumát vagy a beszerzésirendelés-sorok szállítási dátumát mutatja. |
| Készlet dátuma | Ez a mező akkor van beállítva, amikor a tényleges bevételezés feladása előtt megtörtént egy regisztrációs tranzakció a bevételezési rendelésen. |
| Nem pénzügyi jellegű átvitel | Ez az érték jelzi, hogy a kiválasztott készlettranzakció nem pénzügyi jellegű átvitel-e. Nem pénzügyi jellegű átvitelre akkor kerül sor, ha a **készletdimenziók egy módosítása nincs pénzügyileg nyomon követhető a Cikkmodellcsoport lapon**. |
| Átmozgatási adag azonosítója | Ha a kiválasztott készlettranzakció nem pénzügyi jellegű átvitel, ez a mező annak a másik készlettranzakciónak az azonosítóértékére van beállítva, **amely** a kijelölt tranzakciót kiegyenlíti. |

## <a name="fields-on-the-updates-fasttab"></a>A Frissítések gyorsattab mezői

Az alábbi táblázat olyan mezőket **ír** le a Frissítések gyorslapon, amelyek nem jelennek meg a **Készlettranzakciók lapon**.

| Mező | Leírás |
|---|---|
| Tényleges bizonylat | Az a főkönyvi bizonylatszám, amelyből a kiválasztott készlettranzakció tényleges feladása létre lett hozva. |
| Útvonal | A kiválasztott készlettranzakcióhoz kapcsolódó útvonal. Ez a mező csak olyan termelési kitárolásilista-tranzakciók esetében van beállítva, amelyekben az anyagjegyzék vagy receptúrasor egy adott cikkhez kapcsolódik. |
| Szállítólevél | A beszerzési rendelés termékbevételezési tranzakcióhoz megadott szállítólevélszáma. |
| Tényleges önköltségi érték | A tényleges frissítéshez a főkönyvbe feladott összeg. Elszámolóáras termékekhez ez az összeg jelenti az elszámolóárat. Egyéb költségszámítási módszereknél ez a termék súlyozott átlagát jelenti a feladáskor. |
| Tényleges bevétel | A főkönyvbe a tényleges frissítésre feladott halasztott bevétel összege. |
| Rakományazonosító | Ha az aktuális tranzakció a Szállításkezelés egy rakományával áll kapcsolatban, ez a mező a cikket is magában vevő rakomány egyedi számát mutatja. |
| Ténylegesen feladott | Ez az érték jelzi, hogy a kiválasztott készlettranzakció ténylegesen fel lett-e adva. Ha az aktuális tranzakciót feladja a főkönyvbe, akkor tényleges bizonylat is lesz. |
| Pénzügyileg feladott | Ez az érték jelzi, hogy a kiválasztott készlettranzakció pénzügyileg fel lett-e adva. Ha az aktuális tranzakciót feladja a főkönyvbe, akkor egy pénzügyi bizonylat is lesz. |
| Feladott tényleges költség | Ez az érték jelzi, hogy a kiválasztott készlettranzakcióhoz kapcsolódó tényleges költségek fel vannak-e adva. |
| Feladott pénzügyi költség | Ez az érték jelzi, hogy a kiválasztott készlettranzakcióhoz kapcsolódó pénzügyi költségek fel vannak-e adva. |
| Pénzügyi bizonylat | Az a bizonylatszám a főkönyvben, ahol a pénzügyi feladás történt. |
| Számla | A számlaszám, amely például egy beszerzési rendeléshez vagy egy értékesítési rendeléshez lett létrehozva. |
| Korrekció | A kiválasztott készlettranzakción a készletzárás és a helyesbítési folyamat során korrigált összeg. |
| Eredmény, feladott összeg | A kiválasztott készlettranzakciónak az eredményki kimutatásba feladott összege. |
| Fel nem adott számla | Annak a kapcsolódó beszerzési rendelésnek a számlaszáma, amely megjelenik **a Függőben lévő szállítói számla oldalon**. |
| Pénzügyileg lezárva | A tranzakció teljes kiegyenlített voltának dátuma. |
| Vonatkozó tényleges súly szerinti mennyiség | A kiegyenlítés által fedezett tényleges súly mennyisége. |
| Rendezett mennyiség | A kiválasztott készlettranzakcióval kiegyenlített mennyiség. |
| Kiegyenlített összeg | A kiválasztott készlettranzakcióval kiegyenlített érték. |

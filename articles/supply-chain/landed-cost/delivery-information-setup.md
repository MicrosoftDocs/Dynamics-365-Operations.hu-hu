---
title: Szállítási adatok beállítása
description: Ez a témakör azt ismerteti, hogyan lehet kézbesítési adatokat beállítani a Partraszállítási költség modulhoz.
author: sherry-zheng
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMPortTable, ITMLeadTimeTable, ITMLegTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 57f17d481f9660d67b96ac2c8e68558407b1bcf9
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7577600"
---
# <a name="delivery-information-setup"></a>Szállítási adatok beállítása

[!include [banner](../../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet kézbesítési adatokat beállítani a **Partraszállítási költség** modulhoz.

## <a name="shipping-ports"></a>Szállítási kikötők

A szállítási kikötők meghatározzák, hogy honnan és hová szállítják az árukat. Minden egyes hajóútnál meg van adva egy „cél-” és egy „forrás-” kikötő, a hajóúton használt hajóhoz kiválasztott utazás alapján. A szállítási kikötők segítségével hozzák létre az utazás szakaszait és az utazás tevékenységeit. Ezek meghatározása általában a város és az ország/régió nevének használatával történik, ahol a tényleges szállítási kikötő található.

A kikötők használatához lépjen a **Partraszállítási költség \> Szállítási adatok beállítása \> Szállítási kikötők** részre. Itt megtekintheti, hozzáadhatja és eltávolíthatja a szállítási kikötők rekordjait. Az alábbi táblázat bemutatja az egyes rekordokhoz rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Szállítási kikötő | Adja meg a szállítási kikötő egyedi azonosító nevét/számát. |
| Leírás | Adja meg a szállítási kikötő leírását. |

## <a name="tracking-control-center"></a><a name="tracking-control-center"></a>Követés ellenőrzési központja

A Követési vezérlőközpont használatával beállíthatja az átfutási időt, az állapotfrissítéseket és az információk folyamatát, amelyek a hajóúthoz kötődnek, ahogy a szállítótárolók az egyik szakaszból a következőre haladnak. Követésvezérlési rekord létrehozásakor a rendszer társítja egy hajóút utazásának egyik megadott szakaszához. Amikor egy hajóút frissít egy szakaszt, a kapcsolódó rekord frissül, és a meghatározottak szerint kitölti a rendszer. Az egyes hajóútakkal kapcsolatos követési információkat az **Összes hajóút** oldalon frissítheti.

A Követési vezérlőközpont megnyitésához lépjen a **Partraszállási költség \> Szállítási információk beállítása \> Követési vezérlőközpont** pontra.

A Követési vezérlőközpont három oldalnézet közül az egyiket jeleníti meg a **Létrehozási típus** mezőben kiválasztott érték alapján a listapanelen: *Üres*, *Átfutási idő* vagy *Állapotfrissítés*. Minden létrehozási típus egy másik információhalmazt frissíti, amely egy hajóút haladásával van kapcsolatban a kiindulási ponttól a végső célig.

### <a name="common-rule-settings"></a>Gyakori szabálybeállítások

Az alábbi táblázat bemutatja azokat a mezőket, amelyek mindhárom létrehozási típushoz rendelkezésre állnak a Követési vezérlőközpontban.

| Mező | Leírás |
|---|---|
| Forrástábla, Forrásmező | Ezek a mezők azonosítják az adatbázis egyik forrástábláját és mezőjét. A szabály betölti a mezőben megadott értéket, majd a szabály egyéb beállításaiban megadott módon használja azt. |
| Céltábla, Célmező | Ezek a mezők azonosítják az adatbázis egyik céltábláját és mezőjét. A szabály betölti a mezőben megadott értéket, majd a szabály egyéb beállításaiban megadott módon használja azt (vagy felülírja). |
| Tevékenység | Ez a mező azonosítja annak a tevékenységnek a típusát, amelyet alkalmazni kell egy olyan szállítási tárolóra, amelynek egy szabály megfelel. |
| Egyezési feltételek | Ez a mező határozza meg, hogy hogyan azonosítja a rendszer egy szabály egyezését. A rendszer mindegyik példányban áttekinti a forrás- és céltáblák adatait, és meghatározza, hogy kell-e frissíteni egy mezőt a céltáblában, és ha igen, mikor.<p>Például a forrástábla *Hajóutak*, a céltábla pedig *Beszerzési fejléc* vagy *Beszerzési sorok*. A *Hajóút* tábla **Forráskikötő** értéke *Hongkong*, a *Beszerzési fejléc* tábla **Forráskikötő** értéke *Sanghaj*. Ekkor létrejön egy olyan szabály, amelynél *Hongkong* a forráskikötő. Ebben az esetben az **Egyeztetési feltételek** mező értékei a következő módon működnek:</p><ul><li>**Mindkettő** – a célmező nem frissül, mert a két kikötő valamelyike nem egyezik.</li><li>**Forrás** – a célmező frissül, mert a forrástábla forráskikötője *Hongkong*.</li><li>**Cél** – a célmező nem frissül, mert a céltábla forráskikötője *Sanghaj* és nem *Hongkong*.</li></ul> |
| Művelet másolása | A lehetséges értékek a *Másolás* és az *Alapértelmezett* érték. Válassza a *Másolás* lehetőséget, ha a forrásmezőben megadott értéket a célmezőbe kell másolni. Az *Alapértelmezett* érték kiválasztásával statikus értéket állíthat be a célmezőhöz. |
| Alapértelmezett | Ha a **Másolás művelet** mező értéke *Alapértelmezett*, az **Alapértelmezett** mező határozza meg a célmező alapértelmezett értékét. Ha például a művelet egy kikötőfrissítéshez kapcsolódik, és a **Másolás művelet** mező az *Alapértelmezett* beállításra van állítva, az **Alapértelmezett** mező egy kikötőt azonosít. |
| Szakasz | Ez a mező azonosítja az utazásnak azon szakaszát, amelynél a megadott művelet történik, például rakodás vagy vámkezelés. |
| Szolgáltató | Ha az utazás aktuális állapotfrissítéséhez/szakaszához egy megadott szolgáltatót használnak, ez a mező azonosítja a szolgáltatót. A szolgáltatók a szállítói számlán vannak megadva. |

### <a name="lead-time-rules"></a>Átfutási idő szabályai

Az átfutási idő az a becsült idő, amely alatt az utazásnak végre kell hajtania egy utazás megadott szakaszát egy hajóútnál. Az utazás egyes szakaszának átfutási ideje a hajóút becsült szállítási dátumának kiszámítására használható. Ezt a dátumot kell beírni az út összes beszerzési sorának **Visszaigazolt szállítási dátum** mezőjébe.

Az átfutási idő szabályaival kezelheti a dátumfrissítéseket. A tevékenységek automatikusan létrejönnek, amikor egy hajóúthoz utazássablont használnak.

Ha átfutásiidő-szabályt szeretne hozzáadni a Követési vezérlőközponthoz, kövesse ezeket a lépéseket.

1. Tegye a következők egyikét:

    - Lépjen ide: **Partraszállítási költség \> Többszakaszos út beállítása \> Szakaszok**. Válassza ki azt a szakaszt, amelynél be szeretné állítani az átfutási időket, majd a Műveleti ablaktáblán válassza a **Követési vezérlőközpontot**. A Követési vezérlőközpont előre ki van töltve a kiválasztott szakasz adataival.
    - Lépjen a **Partraszállási költség \> Szállítási információk beállítása \> Követési vezérlőközpont** pontra. Ezután manuálisan ki kell választania egy szakaszt az eljárás 4. lépésében.

1. A listaablakban állítsa a **Létrehozási típus** mezőt *Átfutási idő* értékre.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Ha a követési vezérlőközpontból indult el az 1. lépésben, állítsa a **Szakasz** mezőt arra a szakaszra, amelynél átfutási idő szabályt szeretne létrehozni. Ha a **szakasz** lapról indult el, akkor a **Szakasz** mezőt a Követési vezérlőközpont megnyitása előtt kiválasztott szakaszhoz kell előre beállítani.

    A **szakasz** mező értéke alapján a program automatikusan több mezőt is beállít, az itt látható módon:

    - **Forrástábla:** *Tárolótevékenységek*
    - **Forrásmező:** *Kezdő dátum*
    - **Céltábla:** *Tárolótevékenységek*
    - **Célmező:** *Becsült záró dátum*

1. A **Tevékenység** mezőben válassza ki azt a tevékenységet, amelyre az aktuális szabály vonatkozik.
1. Az **Átfutási idő** mezőben adja meg azt az átfutási időt (napokban), amelyet az aktuális szabály aktiválásakor kell alkalmazni.

### <a name="status-update-rules"></a>Állapotfrissítési szabályok

Az olyan rekordoknál, ahol a **Létrehozási típus** mező értéke *Állapotfrissítés*, frissíteni fogja a beszerzésirendelés-sorok állapotát, vagy az állapotot a hajóút, szállítótároló vagy levél szintjén. Az állapotok önállóan is beállíthatók. Használatával tájékoztatni lehet a felhasználót vagy a részleget az hajóút fokozatáról (például a kapott dokumentumokról vagy az úton lévő árukról).

Ha a **Létrehozási típus** mező értéke *Állapotfrissítés*, a Követési vezérlőközpontban szerepel egy **Sorok** gyorslap, ahol megadhatja a hajóút költségterületét és a frissített állapotát. Például van egy olyan sor, ahol a **Költségterület** mező értéke *Tároló*, a **Hajó állapota** mező beállított értéke pedig *Úton lévő áruk*. Ebben az esetben, amikor egy rendelés befejezi a megadott szakaszt, a szállítási tároló **Hajóút állapota** mezője át fog frissülni az *Úton lévő áruk* állapotra.

Az állapotfrissítések egy hajóút állapotát adják meg az adott hajóúthoz társított hajóútsorokon és beszerzésirendelés-sorokon keresztül. Ahogy a hajóút végighalad az utazáson a kikötőből, hajózáson és vámkezelésen a célraktárba, a hajóútrekord **Hajóút állapota** mezője gyors betekintést biztosít az áruk aktuális fázisába.

Ha állapotfrissítési szabált szeretne hozzáadni a Követési vezérlőközponthoz, kövesse ezeket a lépéseket.

1. Tegye a következők egyikét:

    - Lépjen ide: **Partraszállítási költség \> Többszakaszos út beállítása \> Szakaszok**. Válassza ki azt a szakaszt, amelynél be szeretné állítani az állapotfrissítést, majd a Műveleti ablaktáblán válassza a **Követési vezérlőközpontot**. A Követési vezérlőközpont előre ki van töltve a kiválasztott szakasz adataival.
    - Lépjen a **Partraszállási költség \> Szállítási információk beállítása \> Követési vezérlőközpont** pontra. Ezután manuálisan ki kell választania egy szakaszt az eljárás 4. lépésében.

1. A listaablakban állítsa a **Létrehozási típus** mezőt *Állapotfrissítés* értékre.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Ha a követési vezérlőközpontból indult el az 1. lépésben, állítsa a **Szakasz** mezőt arra a szakaszra, amelynél állapotfrissítési szabályt szeretne létrehozni. Ha a **szakasz** lapról indult el, akkor a **Szakasz** mezőt a Követési vezérlőközpont megnyitása előtt kiválasztott szakaszhoz kell előre beállítani.

    A **szakasz** mező értéke alapján a program automatikusan több mezőt is beállít, az itt látható módon:

    - **Forrástábla:** *Tárolótevékenységek*
    - **Forrásmező:** *Tényleges záró dátum*
    - **Céltábla:** Ez a mező üresen marad.
    - **Célmező:** Ez a mező üresen marad.

1. A **Tevékenység** mezőben válassza ki azt a tevékenységet, amelyre a szabálya vonatkozik.
1. Adja meg az egyes költségterületek állapotfrissítéseit a **Sorok** gyorsjelentésben.

### <a name="blank-type-rules"></a>Üres típusszabályok

*Üres* értékű **Létrehozási típus** beállítással rendelkező rekordok segítségével felülbírálhatja vagy megadhatja egy mező értékét egy másik mező adatai alapján. A Partraszállási költség modulból származó mező felülírja a Microsoft Dynamics 365 Supply Chain Management más területein található adatokat a Követési vezérlőközpontban beállított szabályok alapján.

1. Lépjen a **Partraszállási költség \> Szállítási információk beállítása \> Követési vezérlőközpont** pontra.
1. A listaablakban állítsa a **Létrehozási típus** mezőt *Üres* értékre.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Határozza meg forrás- és célértékek, egyeztetési feltételek, másolási művelet és más fontos paraméterek értékét a szabályhoz szükséges szerint.

### <a name="required-tracking-control-setup"></a>Kötelező követési vezérlő beállítása

Minden utazássablonhoz két rekordot kell beállítani a Követési vezérlőközpontban. Mindkét rekord *Üres* **Létrehozási típussal** rendelkezik, és minden Partraszállási költség-megvalósításban használatos. Gondoskodnak arról, hogy a beszerzés visszaigazolt dátuma és az úton lévő áruk várható dátumai a hajóúton és a kapcsolódó beszerzésirendelés-sorokban a várt módon frissüljenek.

Az első rekord a beszerzési sorok frissítéséhez szükséges. A következő beállításokat kell megadni:

- **Forrástábla:** *Tárolótevékenységek*
- **Forrásmező:** *Becsült záró dátum*
- **Céltábla:** *Beszerzési sorok*
- **Célmező:** *Visszaigazolt vagy szállítási dátum*

A második rekord az úton lévő árukkal kapcsolatos tranzakciók frissítéséhez szükséges. A következő beállításokat kell megadni:

- **Forrástábla:** *Tárolótevékenységek*
- **Forrásmező:** *Becsült záró dátum*
- **Céltábla:** *Úton lévő áruk rendelése*
- **Célmező:** *Várt dátum*

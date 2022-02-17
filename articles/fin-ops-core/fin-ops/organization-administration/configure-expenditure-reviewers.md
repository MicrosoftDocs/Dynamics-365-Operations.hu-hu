---
title: Kiadásellenőrök konfigurálása
description: Ez a témakör azt írja le, hogyan lehet a kiadásellenőrök használatával dinamikusan kiválasztani azt a felhasználót, akihez egy munkafolyamat-feladat, jóváhagyás vagy manuális döntés van hozzárendelve.
author: rachel-profitt
ms.date: 06/25/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2021-06-24
ms.openlocfilehash: ad980889247e0239ad743078cb013c1c5839f676
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070146"
---
# <a name="configure-expenditure-reviewers"></a>Kiadásellenőrök konfigurálása
[!include[banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Beállíthat dinamikus kiadásellenőröket a kiadások ellenőrzésre küldéséhez vagy azon felhasználó alapján, aki hozzá van rendelve egy projektszerepkörhöz, vagy azon pénzügyi dimenzió alapján, ahol a kiadás megjelenik. A munkafolyamat a megadott projektszerepkör vagy pénzügyi dimenzió tulajdonosa alapján határozza meg, hogy kinek kell elküldeni a kiadást.

Definiálhat egy vagy több kiadásellenőri konfigurációt, majd a munkafolyamat létrehozásakor választhat egy konfigurációt. A kiadásellenőri értékeket beállíthatja a szervezetben található minden jogi személyhez. A kiadásellenőri konfigurációk definiálása után hozzárendelhet a konfigurációt. A kiadásellenőröket hozzá lehet rendelni munkafolyamat-feladatokhoz, jóváhagyásokhoz és manuális döntésekhez.

> [!NOTE]
> Bár a kiadásellenőrök nem kötelezőek, egyszerűbbé tehetik a munkafolyamat konfigurálását. Például nem szükséges egyetlen feltételes döntés létrehozni az egyes költséghely-dimenziók ellenőrzéséhez, majd egy másik elemet létrehozni a jóváhagyás vagy feladat meghatározott felhasználóhoz vagy felhasználócsoportokhoz való hozzárendelése céljából. Ehelyett beállíthatja a költséghely-dimenzió tulajdonosát, és egy kiadásellenőr használatával dinamikusan kiválaszthatja a megfelelő felhasználót. Ily módon, amikor megváltozik a költséghelyek tulajdonjoga vagy hozzárendelése, akkor csak a pénzügyi dimenzió **Tulajdonos** mezőjét kell frissíteni.

## <a name="types-of-expenditure-reviewers"></a>A kiadásellenőrök típusai

Nem minden munkafolyamat támogatja a kiadásellenőrök koncepcióját. Alapértelmezés szerint a beszerzési igénylések, a beszerzési rendelések, a szállítói számlák és a költségjelentések számára állíthat be kiadásellenőröket. E munkafolyamat-típusok mindegyike azt igényli, hogy egy külön, a funkcióra és a modulra jellemző oldalon állítsa be a kiadásellenőröket. A kiadásellenőrök minden támogatott dokumentum esetén használhatók fejlécszintű munkafolyamatokkal vagy sorszintű munkafolyamatokkal is.

A következő táblázat azt mutatja be, hogy hol kell konfigurálnia a kiadásellenőrt az egyes támogatott dokumentumokhoz.

| Dokumentum | Navigációs útvonal |
|----------|-----------------|
| Költségjelentések | Költséggazdálkodás \> Beállítás \> Irányelvek \> Kiadásellenőrök |
| Beszerzési rendelések | Beszerzés és forrás \> Beállítás \> Irányelvek \> Beszerzési rendelések kiadásellenőrei |
| Beszerzési igénylések | Beszerzés és forrás \> Beállítás \> Irányelvek \> Beszerzési igénylés kiadásellenőrei |
| Szállítói számlák | Kötelezettségek \> Irányelv-beállítás \> Szállítói számlák kiadásellenőrei |

## <a name="expenditure-reviewer-assignments"></a>Kiadásellenőrök hozzárendelései

Minden kiadásellenőrhöz kétféle hozzárendelés érhető el: *projektkiosztások* és *szervezeti kiosztások*. A projektkiosztások esetén a projektirányítók és a pénzügyi dimenziók közül választhat. Szervezeti kiosztások esetén pénzügyi dimenziókat választhat.

A projektirányítók közé tartozik a projektvezető, a projektfelügyelő és a projekt értékesítési vezetője. Ezeket a hatóságok közvetlenül a projektben határozhatja meg úgy, hogy kiválaszt egy dolgozót a megfelelő mezőkben.

A pénzügyi dimenziókat az egyes jogi személyek fiókstruktúrái vezérlik. Minden jogi személyhez meg lehet választani, hogy mely pénzügyi dimenziókat fogja használni a kiadásellenőrrel. A dimenziók vagy a projektből (ebben az esetben a **Projektkiosztások** lapon kell kiválasztani a dimenziókat) vagy a dokumentumból (ebben az esetben a **Szervezeti kiosztások** lapon kell kiválasztani a dimenziókat) származhatnak. A **Pénzügyi dimenziók értékei** lap **Tulajdonos** mezőjében kiválaszthatja a dolgozót az egyes pénzügyi dimenziókhoz.

## <a name="example-1-expenditure-reviewers-based-on-organization-distributions"></a>1. példa: Költségellenőrök a szervezeti kiosztások alapján

Ön a Contoso Appliances vállalatnál dolgozik, és szervezetének hat osztálya és 10 költséghelye van. Új beszerzési igénylés beküldése esetén először a részlegvezető, majd a költséghelyvezető jóváhagyását kell megszerezni.

Ebben a példában két *beszerzési igénylési kiadásellenőrt* konfigurál:

- Az első ellenőrnél elnevezi a részleget, majd kiválasztja a **Részleg** pénzügyi dimenziót a **Szervezeti kiosztások** lapon. 
- A második ellenőrnél elnevezi a költséghelyet, majd kiválasztja a **Költséghely** pénzügyi dimenziót a **Szervezeti kiosztások** lapon.

A munkafolyamat konfigurálása során két jóváhagyásai lépést hoz létre. Az elsőt a részleg, a másodikat a költséghely számára. Minden jóváhagyási elemnél kiválasztja a **Résztvevő** lehetőséget a **Szerepköralapú** lap **Hozzárendelés típusa** mezőjében, kiválasztja a **Kiadások résztvevői** lehetőséget a **Résztvevő típusa** mezőben, majd kiválasztja a megfelelő résztvevőt a **Résztvevő** mezőben.

A beszerzési igénylés létrehozásakor a részleg és a költséghely pénzügyi dimenzióit a rendszer hozzárendeli a beszerzési igénylés soraihoz. A munkafolyamat elküldése után a rendszer először kiértékeli a beszerzési igénylés részlegét, és a jóváhagyási elemet hozzárendeli a részleghez kiválasztott dolgozóhoz kapcsolódó felhasználóhoz. Az első jóváhagyási lépés befejeződése után a rendszer kiértékeli a második jóváhagyási lépést, és hozzárendeli a második jóváhagyási elemet a költséghelyhez kiválasztott dolgozóhoz kapcsolódó felhasználóhoz.

## <a name="example-2-expenditure-reviewers-based-on-project-distributions"></a>2. példa: Költségellenőrök a projektkiosztások alapján

Ön a Contoso Appliances szolgáltatási részlegénél dolgozik. A szervezet előírja, hogy minden beszerzési rendelés projektvezetőjének jóvá kell hagyni a költséget. Ezenkívül a projekt költséghely-kezelőjének is jóvá kell hagynia. A jóváhagyásokat egyszerre is el lehet végezni. A munkafolyamat folytatása előtt minden esetben mindkét felhasználónak jóvá kell hagynia a beszerzési rendelést.

Ebben a példában létrehoz egy *beszerzési rendelési kiadásellenőrt*, amelynek a **PM és költséghely** nevet adja. Bejelöli a **Projektvezető** jelölőnégyzetet, és a **Költséghely dimenzió** számára beállítja az **Igen** értéket a **Beszerzési rendelési kiadásellenőr** oldal **Projektkiosztások** lapján. A konfiguráció részeként gondoskodni kell arról, hogy a **Projektvezető** mező minden projektnél be legyen állítva, és hogy a **Pénzügyi dimenzióértékek** oldalon az összes költséghelyhez meg legyen adva tulajdonos.

A munkafolyamat konfigurálása során egy jóváhagyásai elemre van szükség. A **Hozzárendelés típusa** mezőben a **Résztvevő** lehetőséget választja. Ezután a **Szerepköralapú** lapon a **Résztvevő típusa** mezőben a **Kiadások résztvevői** lehetőséget választja, majd a **Résztvevő** mezőben kiválasztja a projektvezetőt és a költséghelyet. Annak érdekében, hogy a munkafolyamat ne folytatódjon mindaddig, amíg a projektvezető és a költséghely tulajdonosa jóvá nem hagyja a munkafolyamatot, a **Befejezési irányelv** mezőben a **Minden jóváhagyó** értéket adja meg.

A beszerzési rendelés létrehozásakor meg kell adni a **Projekt** mezőt. Ha nincs szükség projektre az összes beszerzési rendeléshez, a jóváhagyási lépés futtatása előtt hozzá kell adnia egy feltételes, a projekt ellenőrzésére szolgáló döntést a munkafolyamathoz. A rendszer ezután kiértékeli a beszerzési rendeléshez megadott projektet, és hozzárendeli a jóváhagyási elemet a **Projektvezető** mezőben szereplő dolgozóhoz kapcsolódó felhasználóhoz. Ezenkívül a rendszer létrehoz egy feladatot, és hozzárendeli a projekt költséghelyének **Tulajdonos** mezőjében kiválasztott dolgozóhoz kapcsolódó felhasználóhoz. Ne feledje, hogy ez a példa a projekt költséghelyét használja, nem pedig a beszerzési rendelés költséghelyét.

## <a name="set-up-expenditure-reviewers"></a>Kiadásellenőrök beállítása

Ebben a példában azt láthatja, hogyan konfigurálhat beszerzési igénylési kiadásellenőrt. Egyéb típusú kiadásellenőrök konfigurálásához cserélje le az 1. lépésben szereplő navigációs útvonalat a jelen témakörben feljebb található, [Kiadásellenőrök típusai](configure-expenditure-reviewers.md#types-of-expenditure-reviewers) című szakasz táblázatából származó megfelelő útvonalra.

1. Lépjen a **Beszerzés és forrás \> Beállítás \> Irányelvek \> Beszerzési igénylés kiadásellenőrei** oldalra.
2. A **Beszerzési igénylés kiadásellenőrei** oldalon válassza az **Új** lehetőséget.
3. A **Név** mezőben adja meg a kiadásellenőr konfigurációjának nevét, amely lehet például a **költséghely**.
4. Válassza ki a konfigurálni kívánt jogi személyt a **Kiadásellenőrök jogi személy szerint** gyorslapon.
5. A projektkiosztáshoz jelölje be az egyes projektirányítók jelölőnégyzetét, majd válassza az **Igen** lehetőséget minden engedélyezni kívánt pénzügyi dimenziónál. 
6. Szervezeti kiosztáshoz a **Szervezeti kiosztások** lapon válassza az **Igen** lehetőséget minden olyan pénzügyi dimenzióhoz, amelyet engedélyezni szeretne.
7. Ismételje meg a 4–6. lépést minden egyes jogi személyhez.

## <a name="assign-owners-to-financial-dimensions"></a>Tulajdonosok hozzárendelése a pénzügyi dimenziókhoz

Ha hozzá szeretne rendelni egy tulajdonost egy pénzügyi dimenzióhoz, kövesse ezeket a lépéseket.

1. Lépjen a **Főkönyv \> Számlatükör \> Dimenziók \> Pénzügyi dimenziók** oldalra.
2. A listából válassza ki azt a pénzügyi dimenziót, amelyhez tulajdonosokat szeretne hozzárendelni.
3. Válassza ki a **Dimenzióértékeket**.
4. Ha módosítani szeretné a dimenzióértékeket, válassza a **Szerkesztés** lehetőséget.
5. A listából válassza ki azt a dimenzióértéket, amelyhez tulajdonost szeretne hozzárendelni.
6. A **Tulajdonos** mezőben válassza ki, hogy melyik dolgozóhoz szeretné hozzárendelni a dimenzióértéket.

## <a name="configure-project-distributions"></a>Projektkiosztások konfigurálása

Ha projektirányítókat szeretne hozzárendelni egy projekthez, kövesse az alábbi lépéseket.

1. Ugorjon a **Projektvezetés és könyvelés \> Projektek \> Minden projekt** pontra.
2. Válassza ki azt a projektet, amelyhez hozzá szeretné rendelni az irányítókat.
3. Ha módosítani szeretné a projektet, válassza a **Szerkesztés** lehetőséget.
4. Az **Általános** gyorslap **Felelős** szakaszában válasszon egy dolgozót az **Értékesítési vezető**, a **Projektvezető** és a **Projektfelügyelő** mezőhöz igény szerint.
5. A **Pénzügyi dimenziók** gyorslapon válassza ki a projekthez szükséges pénzügyi dimenziókat.

## <a name="assign-expenditure-reviewers-to-a-workflow-task"></a>Kiadásellenőrök hozzárendelése egy munkafolyamat-feladathoz

Ez a példa az mutatja be, hogyan kell konfigurálni egy beszerzési igénylési munkafolyamatot úgy, hogy az a beszerzési igénylés kiadásellenőrét használja. Ha más típusú munkafolyamatokat is konfigurálni kell, akkor az 1. lépésben megnyitandó munkafolyamatlap a **Beszerzés és forrás** modul helyett a **Költséggazdálkodás** vagy a **Kötelezettségek** modulban is lehet.

Beszerzési igénylési kiadásellenőrök munkafolyamat-feladathoz való hozzárendeléséhez kövesse az alábbi lépéseket.

1. Nyissa meg a **Beszerzés és forrás \> Beállítás \> Beszerzés és forráskezelés munkafolyamatai** pontot.
2. Koppintson (vagy kattintson) duplán egy meglévő munkafolyamatra, vagy hozzon létre egy új munkafolyamatot.
3. A munkafolyamat-szerkesztő **Munkafolyamat** panelén válassza ki azt a feladatot, amelyhez hozzárendeli a kiadásellenőr konfigurációját. Ezután a **Művelet panel** **Megjelenítés** csoportjában válassza a **Tulajdonságok** lehetőséget.
4. A **Tulajdonságok** lap bal oldali panelén válassza a **Hozzárendelés** lehetőséget.
5. A **Hozzárendelés típusa** lapon válassza a **Résztvevő** lehetőséget.
6. A **Szerepköralapú** lap **Résztvevő típusa** mezőjében válassza a **Kiadások résztvevői** lehetőséget. Ezután a **Résztvevő** mezőben válassza ki a munkafolyamat-feladathoz használni kívánt kiadásellenőri konfigurációt.

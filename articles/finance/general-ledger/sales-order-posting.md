---
title: Értékesítési rendelés feladása
description: Ez a témakör a készletfeladási profil lap Értékesítési rendelés lapján található tájékoztatást tartalmaz.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: 5d84723b51d6977867fa162c4a47befa61bd9ef6
ms.sourcegitcommit: dc3053625dfe24aef64399dd1d002214e7f7619f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755928"
---
# <a name="sales-order-posting"></a>Értékesítési rendelés feladása

A **Készletfeladási profilok lap** **Értékesítési rendelés** lapja az értékesítési rendelések főkönyvbe való feladásának szabályozására használható. Az értékesítési rendelések főkönyvbe való feladása két fő tevékenységből áll: 

- Szállítólevél
- Számla

Ahhoz, hogy egy értékesítési rendelés tényleges tranzakciója (csomagjegyzéke) feladható legyen a főkönyvbe, teljesülnie kell a következő feltételeknek:

- A Készlet- **és raktárkezelési paraméterek** lapon **be** kell lennie jelölve a Szállítólevél feladása a főkönyvbe jelölőnégyzet.
- Az értékesítésirendelés-sorban **·** **kiválasztott** cikk cikkmodellcsoport-lapján be kell lennie jelölve a Tényleges készlet feladása a főkönyvben jelölőnégyzetnek.
- A Készletfeladási **profil** lapon a fő számlákat a következő feladási típusokhoz kell megadni:
  - Kiszállított egységek költsége
  - Eladott, kiszállított áruk beszerzési értéke

Ahhoz, hogy egy értékesítési rendelés pénzügyi tranzakciója (számlája) feladható legyen a főkönyvbe, teljesülnie kell a következő feltételeknek:

- Az értékesítésirendelés-sorban **·** **kiválasztott** cikk cikkmodellcsoport-lapján be kell lennie jelölve a Pénzügyi készlet feladása a főkönyvbe jelölőnégyzetnek.
- A fő számlákat a következő feladási **típusokhoz** kell megadni a Készletfeladási profil oldalon:
  - Számlázott egységek költsége
  - Eladott áruk számlázott beszerzési értéke
  - Bevétel
  - Kedvezmény\*

> [!NOTE]
> Az engedményszámla megadása nem kötelező. Sok könyvelési előírás, például a GALLAP és az IFRS, megköveteli, hogy az engedmények csökkentik az értékesítési bevételt, ezért ezek a számlák nem sok esetben használatosak. Ha a helyi szabályozás lehetővé teszi, egy külön fő számlával engedményes eladási ár részével használhatja fel a számlát.

Ha az értékesítési rendelés csomagjegyzékének generálása esetén a halasztott (becsült) bevételértéket fel kell rendelni a főkönyvbe, teljesülnie kell a következő feltételeknek:

- Az értékesítésirendelés-sorban **·** **kiválasztott** cikk cikkmodellcsoport-lapján be kell lennie jelölve a Tényleges készlet feladása a főkönyvben jelölőnégyzetnek.
- A Cikkmodellcsoport **lapon** be **kell lennie jelölve a Post toferred revenue account on Sales Delivery** jelölőnégyzetnek.
- A Készlet- **és raktárkezelési paraméterek** oldalon be **kell** lennie jelölve a Szállítólevél feladása a főkönyvbe jelölőnégyzet.
- A Készlet- **és raktárkezelési paraméterek** lapon **be** kell lennie jelölve a Tényleges áfa feladása jelölőnégyzet.
- A Kinnlevőségek **paraméterei** lapon be **kell** lennie jelölve a Szállítólevél feladása a főkönyvbe jelölőnégyzet.
- A Készletfeladási **profil** lapon a fő számlákat a következő feladási típusokhoz kell megadni:
  - Szállításkori halasztott bevétel
  - Szállításkori halasztott bevételi ellenszámla
  - Szállításkori halasztott áfa

> [!NOTE]
> Általában javasolt engedélyezni **a** **Tényleges készlet feladása és a Csomagjegyzék főkönyvi feladása lehetőséget.** A beállítások engedélyezése felgyorsíthatja a hónap végi zárási eljárásokat, mivel halasztásokat nem kell manuálisan kiszámítani és feladva. Ezenkívül a pénzügyi kimutatások a halasztott összegeket is tükrözik automatikusan, kézi beavatkozás nélkül.

> [!IMPORTANT]
> Az Értékesítés **szállításának Halasztott** bevételi számlájára történő feladás beállítás nem használható bevétel-elszámolással. A Bevétel-elismertségről a Bevétel-kimutatások áttekintésében [olvashat bővebben.](/accounts-receivable/revenue-recognition-overview.md)

## <a name="sample-posting-profile-configuration"></a>Minta feladási profil konfigurációja 

Az alábbi táblázat példákat mutat be az alapértelmezett feladási típusokra a minta fő számlákkal és leírásokkal:
 
- Az **Elszámolószámla** oszlop azt jelzi, hogy a feladás elszámolószámla típusú. Egy későbbi tranzakció feladása során a program automatikusan sztornírozi az erre a számlára feladott összeget. 
- A **P/F** oszlop mutatja **, hogy tényleges feladásra P**, **pénzügyi feladásra pedig F**. 
- A **Követés** oszlop jelzi, hogy egy adott feladási típus fő számlája általában megegyezik-e egy másik feladási típussal. Az oszlopban lévő érték jelzi a feladás jellemzően használt típusát.

> [!NOTE]
> Ezek a fő számlák és fő számlák neve csak javaslatok. Javasoljuk, hogy a könyvelővel együtt határozza meg, hogy az üzleti igényeknek megfelelő konfigurációt szeretné-e meghatározni.


| Feladás típusa | Példa a fő számlára | Példa a fő számlanévre | Számla típusa | Tartozik/követel? | Elszámolási számla | K/F | Kövesse | Leírás |
|------------|------------------------|-------------------------|--------------|---------|-------------------|------------|------|-------------------------|
| Kiszállított egységek költsége | 140100</br>140101 | Anyagkészlet</br>Nem számlázott leszállított anyagok | Eszközök | Jóváírás | Igen | P | Számlázott egységek költsége | Értékesítési rendelés csomagjegyzékének feladásakor használatos. A számla ellentétele az eladott áruk költsége, leszállított áruk. Az értékesítési rendelés számlájának feladott összege ebben a számlán sztornírozva lesz. Előfordulhat, hogy a leszállított, nem számlázott anyagok számláját szeretné a tényleges készletnek megfelelő összegként használni, és le szeretné foglalni az Anyag készletszámlát a pénzügyi frissítéshez. |
| Eladott, kiszállított áruk beszerzési értéke | 500150 | Elhalasztott ELÁBÉ | Költség | Terhelés | Igen | P  | Értékesítési rendelés csomagjegyzékének feladásakor használatos. A számla ellenszámlája a szállított egységek költsége. Az értékesítési rendelés számlájának feladott összege ebben a számlán sztornírozva lesz. |
| Számlázott egységek költsége | 140100 | Anyagkészlet | Eszközök | Jóváírás | Nem | P | Kiszállított egységek költsége | Értékesítési rendelés számlájának feladott dátumakor használatos. A számla ellenszámlája a számlázott eladott áruk költsége. Ez a számla jelenti a készletet a mérlegben. |
| Eladott áruk számlázott beszerzési értéke | 500100 | ELÁBÉ-anyagok | Költség | Terhelés | Nem | P  | Értékesítési rendelés számlájának feladott dátumakor használatos. A számla ellenszámlája a számlázott egységek költsége. Ez a számla képviseli az ELÁBÉ-t az ön PL-kivonatán&amp;. |
| Bevétel (értékesítési rendelés bevétele*) | 400100 | Bevételi anyagok | Bevétel | Jóváírás | Nem | P   | Értékesítési rendelés számlájának feladott dátumakor használatos. Ennek a számlának az ellenszámlája a **Kinnlevőségek feladási profil** összesített számlája (vevői egyenleg*). |
| Jutalék (értékesítés, jutalék*) | 602150 | Jutalék költsége | Költség | Terhelés | Nem | P  | Akkor használatos, amikor a jutalék engedélyezve van és ki van számítva egy értékesítéshez, és fel van adva az értékesítési rendelés számlázási folyamata során. Ennek a számlának az ellenszámlája a Kötelezettség Jutalék. |
| Jutalék-ellenszámla (értékesítés, jutalék-ellenszámla*) | 201110 | Fizetendő jutalékok | Kötelezettség | Jóváírás | Igen | P | Akkor használatos, amikor a jutalék engedélyezve van és ki van számítva egy értékesítéshez, és fel van adva az értékesítési rendelés számlázási folyamata során. Ennek a számlának az ellenszámlája a Jutalék költsége. |
| Szállítás utáni halasztott bevétel (értékesítés - szállítólevél - bevétel*) | 401400 | Elhatárolt értékesítés | Bevétel | Jóváírás | Igen | P  | Akkor használatos, ha engedélyezve van a Szállítás halasztott bevétel, és akkor kerül feladásra, amikor feldolgoz egy értékesítési rendelés csomagjegyzékét. A számla ellenszámlája a Halasztott bevétel ellenszámlája. Az értékesítési rendelés számlájának feladott összegei automatikusan sztornírozódnak a számlán. |
| Szállítás halasztott bevételének ellenszámlája (értékesítés - szállítólevél - bevétel ellenszámlája)* | 130400 | Kinnlevőségek - nem számlázott | Eszközök | Terhelés | Igen | P  | Akkor használja a rendszer, ha engedélyezve van a Szállítás halasztott bevétel, és akkor ad fel, amikor értékesítési rendelés csomagjegyzékét feldolgozja. Ennek a számlának az ellenszámlája a Szállítás halasztott bevétele. Az értékesítési rendelés számlájának feladott összegei automatikusan sztornírozódnak a számlán. |
| Szállításkor halasztott áfa (értékesítés, szállítólevél - adó*) | 250500 | Halasztott áfa | Kötelezettség | Jóváírás | Igen | P  | Akkor használatos, ha a Szállítás halasztott bevétel engedélyezve van, és engedélyezve van a Tényleges áfa feladása beállítás. Az adóösszeg feladása az értékesítési rendelés csomagjegyzékének feldolgozásakor történik. |

\* Az ebben a táblában zárójelben **látható értékek a Bizonylattranzakciók lapPosting típus** **mezőjében használt értéket képviselik**. A feladás típusát az **Általános** lap Bizonylattranzakciók **lapján** lehet **megtekinteni**.

## <a name="sales-category-posting"></a>Értékesítési kategória feladása

A készletfeladás beállítása helyett beállíthatja az összes cikkre, cikkcsoportra vagy egyetlen cikkre vonatkozó kategóriákat, és értékesítési kategóriák szerint szabályozhatja a főkönyvi feladást. A kategóriahierarchiák beállításával és a [kategóriák termékekhez való hozzárendelésével kapcsolatos további tudnivalókért használja a Termékosztályozás hierarchia](/supply-chain/pim/tasks/create-hierarchy-product-classification.md)[létrehozása és a termék kategóriába sorolása kategóriahierarchiák használatával való csoportosítását](/supply-chain/pim/tasks/classify-product-category-hierarchies.md).

A kategóriahierarchia létrehozása után a hierarchiát hozzá kell rendelni egy vagy több típushoz. Ha az értékesítési rendeléseken kategóriahierarchiát szeretne használni, hozzá kell rendelnie a kategóriát az értékesítési kategóriahierarchia típushoz. További tájékoztatás a kategóriahierarchiákról [nyújt tájékoztatást](/dynamicsax-2012/appuser-itpro/about-category-hierarchies.md).

## <a name="create-revenue-posting-by-sales-category"></a>Bevételfeladás létrehozása értékesítési kategória szerint

Ha értékesítési kategória alapján szeretne főkönyvi feladásokat hozzárendelni egy értékesítési rendeléshez, kövesse a következő lépéseket:

1. Nyissa meg a **Készletkezelés** > **Beállítás** > **Feladás** > **Feladás** menüt.
2. Válassza az **Értékesítés lapot**.
3. Jelölje ki a beállítva kívánt feladási típus választógombját (például **Bevétel**).
4. Válassza az **Új** lehetőséget.
5. A Cikk-kód **mezőben** válassza ki a **Kategóriát**.
6. A Kategóriakapcsolat **mezővel** kiválaszthatja a feladási profil kategóriáját.
7. A Számlakód mezőben válasszon egy **táblára**, **csoportra vagy** mindre vonatkozó **beállítást**.**·** Ha például a feladási profilt az összes vevőre alkalmazni, válassza az Összes **lehetőséget**.
   - Ha a **6**. lépésben a Táblát választotta, **·** **a Számlakapcsolat mezőben válassza ki a feladási profilhoz a szállító számát**.
   - Ha a **6**. lépésben a Csoport lehetőséget választotta, **·** **akkor a Számlakapcsolat mezőben válassza ki a feladási profil szállítócsoportját**.
   - Ha a **6**. lépésben a Mind beállítást választotta, **a** Számlakapcsolat mező üresen marad.

8. Ha egy olyan áfacsoportot kell társítani, amelybe a feladási típus van bejelölve, akkor válasszon egy **áfacsoportot**. Ha ez a mező nincs kitöltve, akkor a feladási típus az összes meglévő adócsoportra vonatkozik. Az adócsoportokhoz megadott feladás csak az értékesítésre és a beszerzésre vonatkozó tranzakciókra vonatkozik.

9. A Fő **számla mezőben** adja meg annak a számlaszámnak a számát, amelybe a számlatípust fel kell adni. Válassza ki a számlatükörben az egyik létező számlaszámot.

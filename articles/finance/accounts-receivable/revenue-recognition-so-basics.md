---
title: Értékesítési rendelések bevételelszámolása
description: Ez a témakör az értékesítési rendelések és számlák bevételének elkönyveléséhez szükséges alapvető funkciókat ismerteti. A bevételkönyvelés az értékesítési rendelés és az értékesítési rendelésből létrehozott megfelelő számla esetében érhető el.
author: kweekley
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 6212ecbf1883405d7ca8cb1dba752b778e4d901c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995542"
---
# <a name="revenue-recognition-on-sales-orders"></a>Értékesítési rendelések bevételelszámolása

[!include [banner](../includes/banner.md)]

> [!NOTE]
> A bevételelszámolási funkció nem kapcsolható be a Funkciókezelés lehetőségen keresztül. Jelenleg konfigurációs kulcsok használatával kapcsolhatja be.

Ez a témakör az értékesítési rendelések és számlák bevételének elkönyveléséhez szükséges alapvető funkciókat ismerteti. A bevételkönyvelés az adott értékesítési rendelés és az értékesítési rendelésből létrehozott megfelelő számla esetében érhető el. Az értékesítési rendelés idő- és anyagelszámolású projekttel is létrehozható.

> [!NOTE]
> Az ebben a témakörben található ábrákon hozzáadunk vagy eltávolítunk oszlopokat a táblázatokból, hogy jobban megjelenjenek a fogalmak. Ennek megfelelően előfordulhat, hogy az ábrán látható oldalak és adatok eltérnek a termékben láthatótól.

## <a name="enter-a-sales-order"></a>Értékesítési rendelés megadása

A programban a következő értékesítési rendelés megadására kerül sor, amely három olyan cikket tartalmaz, amelyeket bevételkönyveléshez állítottak be.

[![Értékesítési rendelés megadása](./media/revenue-recognition-so-basic-sales-order-header.png)](./media/revenue-recognition-so-basic-sales-order-header.png)

A bevétel-könyveléshez két fogalom tartozik:

- **Határozza meg a bevételi árat.** A bevételi árat a kiadott termékek beállításai alapján számítja ki a program. A bevételi ár sosem jelenik meg a vevőnél, az csak az értékesítési rendelés számlájának könyveléséhez használatos. Az értékesítési rendelés soraiban és az értékesítés részeként kinyomtatott dokumentumokban továbbra is a egység-/listaár jelenik meg.
- **Határozza meg, hogy mikor történjen a bevétel elszámolása.** A bevétel ütemezése határozza meg, hogy mikor kell elkönyvelni a bevételt.

    Ebben a példában az S0001 első cikk egy **1O** (egyszeri előfordulás) bevételi ütemezéshez van hozzárendelve. Ez a sor mérföldkő típusú esetet mutat be, amelynél a bevételt a rendszer a jövőben teljesített telepítés után fogja elkönyvelni. Ezért a bevétel könyvelését a program mindaddig elhalasztja, amíg a telepítés be nem fejeződik.

    Az S0008 második cikk egy olyan szolgáltatási tétel, amely szerződéskötés utáni támogatási (PCS-) tételként jelenik meg. A folyamatos mérnöki szolgáltatásokat tizenkét hónapos időszakra biztosítják a vevőnek. Ennek megfelelően alapértelmezés szerint egy **12M** bevételi ütemezést rendelnek hozzá a termékhez. Mivel ez a cikk PCS-termék, meg kell határozni a szerződés kezdő és záró dátumát. Alapértelmezés szerint a szerződés kezdő és záró dátuma a Cikk részletes adatai – Beállítás lapon található. A bevétel ütemezése esetén a **12M**-hez tartozó beállítást úgy kell definiálni, hogy a szerződési feltételeket automatikusan kitöltse a rendszer a következő ábra szerint.

    [![Bevételek ütemezései](./media/revenue-recognition-so-basic-revenue-schedules.png)](./media/revenue-recognition-so-basic-revenue-schedules.png)

    Az S0012 harmadik cikk hardver, és a rendszer nem rendel hozzá alapértelmezés szerint bevételi ütemezést. A program a hardver utáni bevételt akkor könyveli el, amikor a cikk ki van számlázva.

## <a name="confirm-the-sales-order"></a>Értékesítési rendelés megerősítése

A bevételi ár és a bevételi ütemezés további részleteinek megtekintéséhez használja az értékesítési rendelés műveleti ablaktábláján található **Kezelés** lap **Bevételkönyvelés** csoportjának gombjait. Mivel a(z) értékesítési rendelés ezen a ponton nem lett visszaigazolva, a bevételkönyveléshez használt gombok nem érhetők el. Ezek a gombok az értékesítési rendelés teljesítési szakaszainak előrehaladtával elérhetővé vagy inaktívvá válnak.

[![Értékesítési rendelés fejléce](./media/revenue-recognition-so-basic-sales-order-header-02.png)](./media/revenue-recognition-so-basic-sales-order-header-02.png)

Az első három gomb a bevételkönyvelés értékesítési rendelési beállításaiban szereplő cikkek bevételi árának részletes adatait tartalmazza.

- **Bevételi ár felosztása** – Ez a gomb az értékesítési rendelés visszaigazolása vagy a számla feladásának megtörténte után válik elérhetővé. Az értékesítési rendelés visszaigazolása és a számla feladása során a program kiszámítja a bevételt, hogy elkönyvelje a könyvelési tételnél könyvelendő vagy elhalasztandó árat. Beállítástól függően a kiszámított bevételi ár eltérhet a vevő számára megjelenített egységártól.
- **Az ár újrafelosztása új rendelési sorokba** – Ez a gomb az értékesítési rendelés visszaigazolása vagy a számla feladásának megtörténte után válik elérhetővé. Az újrafelosztási folyamat a bevétel újraszámítására szolgál, amelyet akkor kell elkönyvelni, ha új sort adnak hozzá az aktuális értékesítési rendeléshez – miután kiszámlázták –, vagy egy új értékesítési rendeléshez. Mindkét esetben előfordulhat, hogy egy új cikk hozzáadásával módosul a szerződés. Ennélfogva a bevételi árat újra fel kell osztani.
- **Bevételi ár felosztásának frissítése** – Ez a gomb az értékesítési rendelés visszaigazolása után válik elérhetővé, de az értékesítési rendelés kiszámlázása után már nem lesz elérhető. A frissítés a bevételi ár felosztásának újrafuttatására szolgál anélkül, hogy az értékesítési rendelést meg kellene erősítenie. Az értékesítési rendelés kiszámlázása után a bevételi ár nem számítható ki újra.

Az utolsó két gomb az értékesítési rendelésen szereplő cikkek bevételi ütemezésével kapcsolatban nyújt tájékoztatást.

- **Várható bevételkönyvelési ütemezés** – Ez a gomb az értékesítési rendelés visszaigazolása után válik elérhetővé, de az értékesítési rendelés kiszámlázása után már nem lesz elérhető. Egy olyan lapot nyit meg, amelyen a várható bevételütemezés látható. Előfordulhat, hogy a végleges ütemezés változik, mivel a várt ütemezés a kért szállítási dátumot használja, míg a végleges ütemezésben a tényleges szállítási dátumot tüntetik fel.
- **Bevételkönyvelési ütemezés** – Ez a gomb az értékesítési rendelés számlázása után válik elérhetővé. A végleges bevételkönyvelési ütemezés nem jön létre visszaigazoláskor vagy a szállítólevél létrehozásakor. Csak akkor jön létre, ha az értékesítési rendelés ki van számlázva.

A következő példa azt szemlélteti, hogy sor került a bevételi ár felosztására, amikor az értékesítési rendelést visszaigazolták. Vegye figyelembe, hogy annak ellenére, hogy a bevételi árak eltérően vannak felosztva, a **Könyvelendő bevétel** mezőben szereplő teljes összegnek meg kell egyeznie a vevőnek számlázott értékesítésirendelés-sorok összegével. Például az értékesítésirendelés-sorok összege (adó nélkül) 1499 USA-dollár. Ennek megfelelően a **Könyvelendő bevétel** mezőben szereplő értékek összegének is 1499 USA-dollárnak kell lennie.

[![Bevételi ár felosztása](./media/revenue-recognition-so-basic-revenue-price-allocation.png)](./media/revenue-recognition-so-basic-revenue-price-allocation.png)

A program a várható bevételkönyvelési ütemezést is létrehozza. A bevétel ütemezése a **Könyvelendő bevétel** értékét elhalasztandó összegként használja fel. Az S0001 cikk 321,21 USA-dollár helyett 300-at halaszt el, míg az S0008 cikk 160,61 USA-dollárt a 100 helyett. Az S0012 cikk nem jelenik meg a várt ütemezésben, mert a bevételt nem halasztották el. Feladás esetén az S0012 cikk 1017,18 USA-dollárt ad fel közvetlenül a bevételi főkönyvi számlára.

[![Elvárt bevételkönyvelési ütemezés](./media/revenue-recognition-so-basic-expected-rev-rec-schedule.png)](./media/revenue-recognition-so-basic-expected-rev-rec-schedule.png)

## <a name="create-the-packing-slip"></a>Szállítólevél létrehozása

Következő lépésként létrehozható a szállítólevél az értékesítési rendeléshez. A szállítólevél feladásakor nem történik bevételkönyvelés. Ha az értékesítési rendelés nem lett visszaigazolva, akkor a szállítólevél feladása nem indítja el a bevételi ár kiszámítását. Továbbá nem idézi elő a várható vagy végleges bevételkönyvelés ütemezésének létrehozását. Ha a cikkmodellcsoport úgy van beállítva, hogy elhalasztja a bevételt a szállítólevélen, akkor a program továbbra is az aktuális feladási profilú főkönyvi számlák használatával adja fel a szállítólevelet, nem pedig a számla feladásakor használt új elhalasztott bevételi számlákat.

## <a name="create-the-invoice"></a>Számla létrehozása

Az utolsó lépés az értékesítési rendelés kiszámlázása. Ha megtekinti a számla bizonylatát, akkor látni fogja, hogy az S0001 és az S0008 cikkek bevételét elhalasztották (321,21 + 160,61 USA-dollár = 481,82 USA-dollár), és az S0012 cikk fennmaradó összegét feladták a bevételhez (1017,18). Ezek az értékek összesen 1499 USA-dollárt tesznek ki, amely megegyezik az értékesítési rendelés sorainak összegével.

[![Bizonylattranzakciók](./media/revenue-recognition-so-voucher-transactions.png)](./media/revenue-recognition-so-voucher-transactions.png)

A számla létrehozása után a **Bevételi ár felosztása**, **Az ár újrafelosztása új rendelési sorokba** és a **Bevételkönyvelési ütemezés** gombok a bevételkönyvelés esetében elérhetővé válnak, azonban a **Bevételi ár felosztásának frissítése** és az **Elvárt bevételkönyvelési ütemezés** gombok inaktívak maradnak.

[![Elérhető bevételkönyvelés gombjának elérhetősége](./media/revenue-recognition-so-basic-after-invoice-buttons.png)](./media/revenue-recognition-so-basic-after-invoice-buttons.png)

A **Bevételi ár felosztása** gomb továbbra is elérhető, így megtekintheti a bevételi ár kiszámított értékét. Ha nem módosult az értékesítési rendelés a megerősítést követően, a számla feladása nem fogja módosítani a **Könyvelendő bevétel** mezőben lévő kiszámított összeget.

A program eltávolítja a várható bevételkönyvelési ütemezést és a végleges bevételkönyvelési ütemezésre cseréli. A program minden értékesítésirendelés-sor esetében karbantartja a bevételi ütemezés adatait, és a szerződéses kötelezettségek teljesítése során közzéteszi az elhalasztott bevételt a tényleges bevételhez képest.

[![Végleges bevételkönyvelési ütemezés](./media/revenue-recognition-so-revenue-recognition-schedule.png)](./media/revenue-recognition-so-revenue-recognition-schedule.png)

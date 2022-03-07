---
title: Visszáru önköltségi ára és visszáru adagazonosítója
description: Hasznos, ha a visszáruk költsége megegyezik a termékeknek az akkori költségével, amikor a termékeket az ügyfélnek eladta. Ehhez használhatja a **Visszáru adagazonosítóját**.
author: kamaybac
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReturnTableListPage, ReturnInventTransIdLookup, ReturnItemNumLookup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c8c5ad2f7e46ecefd490936b950d2b579faed60b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580336"
---
# <a name="return-cost-price-and-return-lot-id"></a>Visszáru önköltségi ára és visszáru adagazonosítója        

[!include [banner](../includes/banner.md)]



A készletbe visszavett termékek költsége a termék jelenlegi költségeinek segítségével számítható ki. Hasznos lehet azonban, ha a visszáruk költsége megegyezik a termékeknek az akkori költségével, amikor a termékeket az ügyfélnek eladta. Ehhez a következőt használhatja: **Értékesítési rendelés** képernyő, **Sor részletei** gyorslap, **Visszáru adagazonosítója** mező.

Vegyük például a következő forgatókönyvet: Ön kiállít egy számlát a vevőnek. Ezt követően a vevő visszaküldi Önnek a leszállított termékeket. Ön visszateszi a termékeket a készletbe. Ebben az esetben, amikor jóváírja a vevőnek a visszaküldött termékeket, az ilyen termékek költséginek kiszámítása a termék jelenlegi költségeinek használatával történik. Ha azonban használja a **Visszáru adagazonosítója** mezőt, a visszaküldött termékek költségének kiszámítása a vevőnek történő eredeti értékesítéshez kapcsolódó számlán feltüntetett költség alapján történik.

Ha nem akarja a vevő által visszaküldött termékek jelenlegi költségeit használni a költségszámításhoz, használja a következő módszerek egyikét.

## <a name="method-1-manually-enter-the-return-cost-price"></a>1. módszer: Manuálisan adja meg a visszáru önköltségi árát

Alapértelmezés szerint, amikor cikkeket ad hozzá egy visszárurendeléshez, a cikkek visszakerülnek készletbe, az aktuális önköltségi áron. Ahhoz, hogy másik önköltségi árat adjon meg a visszáruhoz, kövesse az alábbi lépéseket.

1.  Kattintson a következőkre: **Értékesítés és marketing** \> **Közös** \> **Visszárurendelések** \> **MInden visszárurendelés**.

2.  A **Műveleti ablaktáblán** az **Új** csoportban kattintson a **Visszárurendelés** lehetőségre.

3.  A **Visszárurendelés létrehozása** képernyőn válasszon ki egy vevőkódot, majd kattintson az **OK** gombra.

4.  A **Visszárurendelések - RMA szám: %1, %2** képernyőn válasszon ki egy cikket, majd adja meg a negatív mennyiséget a **Mennyiség** mezőben.

5.  Kattintson a **Soradatok** gyorslapra.

6.  Adjon meg egy értéket az **Általános** lap **Visszáru önköltségi ára** mezőjében. A rendszer ezt az értéket használja, amikor az áruk visszakerülnek a készletbe. Ha nem ad meg értéket, akkor a rendszer az aktuális önköltségi árat használja, amikor az áruk visszakerülnek a készletbe.

## <a name="method-2-automatically-generate-the-cost-price-based-on-the-customer-invoice-line"></a>2. módszer: az önköltségi ár automatikus létrehozása a vevőiszámla-sor alapján

Ez az elsődlegesen ajánlott módszer a visszárusorok létrehozásához. Ahhoz, hogy a terméknek az akkori költségét használja, amikor a termékeket az ügyfélnek eladta, hozzon létre egy visszárurendelést, és adjon meg egy értékesítési sort a visszáruhoz.

1.  Kattintson a következőkre: **Értékesítés és marketing** \> **Közös** \> **Visszárurendelések** \> **MInden visszárurendelés**.

2.  A **Műveleti ablaktáblán** az **Új** csoportban kattintson a **Visszárurendelés** lehetőségre.

3.  A **Visszárurendelés létrehozása** képernyőn válasszon ki egy vevőkódot, majd kattintson az **OK** gombra.

4.  A **Visszárurendelések - RMA-szám: %1, %2** képernyőn, a **Műveleti panelen** kattintson az **Értékesítési rendelés megkeresése** lehetőségre.

5.  Az **Értékesítési rendelés megkeresése** képernyőn válassza ki a számlasort a visszáruhoz, és kattintson az **OK** gombra.
    
    A **Sor adatai** gyorslapon, az **Általános** lapon, a **Visszáruadag-azonosító** mezőben látható az eredeti értékesítési sorban szereplő érték. Ezenkívül a **Visszáru önköltségi ára** mezőben látható az eredeti értékesítési sorból származó költségérték.

## <a name="cost-calculation-example"></a>Költségszámítási példa

Amikor egy visszárurendelési sor **Visszáruadag-azonosító** mezőjét használja a visszáru önköltségi árának meghatározásához, a rendszer a visszárurendelés sorában szereplő költséget alkalmazza. A készletzárási vagy újraszámítási funkció használata esetén a költség az eredeti értékesítési soron módosul. A visszárurendelés sorában szereplő költség automatikusan úgy módosul, hogy megegyezzen a darabonkénti költség.

1.  Hozzon létre, és adjon ki egy teméket, amelynek az elnevezése Teszt. A **Kiadott termék részletei** képernyőn adja meg a következő információkat.
    
    1.  A **Költségek kezelése** gyorslapon, a **Cikkcsoport** mezőben válassza ki a **Részek** csoportot.
    
    2.  Az **Általános** gyorslap **Cikkmodellcsoport** mezőjében válassza ki a **DEF** lehetőséget.
    
    3.  A **Beszerzés** gyorslap **Ár** mezőjében a cikk önköltségi árához írja be: 10.00.
    
    4.  A **Műveleti panelen** kattintson a **Dimenziócsoportok** elemre. A **Tárolásidimenzió-csoport** mezőben válassza a **Csak hely és raktár** lehetőséget. A **Nyomonkövetésidimenzió-csoport** mezőben válassza a **Nincsenek aktív nyomon követési dimenziók** elemet.

2.  Hozzon létre egy beszerzési rendelést a Tesztcikk 10 darabjára, 6,00/darab áron, majd adjon fel egy számlát a beszerzési rendeléshez.
    
    Hozzon létre egy második beszerzési rendelést a Tesztcikk 10 darabjára, 8,00/darab áron, majd adjon fel egy számlát a beszerzési rendeléshez.

3.  Adjon fel egy számlát az értékesítési rendeléshez azzal a céllal, hogy eladjon öt darab Tesztcikket.
    
    Ebben az esetben az értékesítésirendelés-soron 35,00 összegű költség szerepel (5 darab \* 7,00/darab átlagos költséggel számolva).

4.  Hozzon létre visszárurendelést a vevő számára. Az **Értékesítési rendelés megkeresése** képernyőn válassza ki a számlasort, és kattintson az **OK** gombra.

5.  A **Visszárurendelések - RMA szám: %1, %2** képernyőn győződjön meg róla, hogy létrejön a visszáru-rendelés a Tesztcikk visszaküldéséhez. A visszáru-rendelés mennyisége 5,00-re van beállítva.
    
    A **Visszáruadag-azonosító** mezőben megjelenik az adagazonosító. Ez az adagazonosító annak a cikknek az eredeti értékesítési rendeléséből jön, amelyet értékesítettek a vevőnek. A **Visszáru önköltségi ára** mezőben látható az eredeti értékesítési sorból származó önköltségi ár.

6.  Rögzítse a visszaadott cikkek bevételezését.

7.  Adjon fel egy szállítólevelet a visszaküldött cikkekhez.

8.  Számla feladása egy visszárurendeléshez. A **Minden értékesítési rendelés** listaoldalon jelöljön ki egy értékesítési rendelést, amelynél a rendelés típusa **Visszaküldött rendelés**.

9.  Nyissa meg a **Készlettranzakciók** képernyőjét. Győződjön meg róla, hogy a visszáru költsége 7,00/darabonkénti áron van elszámolva a **Visszáru önköltségi ára** mezőben lévő értéket használva, és a **Költségösszeg** mezőben összesen 35,00 szerepel. A **Készlettranzakciók** képernyőt a **Visszárurendelések - RMA szám: %1, %2** képernyőn nyithatja meg. A **Sorok** rácsban kattintson a **Készlet** \> **Tranzakciók** lehetőségre.

10. A készlet- és raktárkezelő modulban használja a **Zárás és módosítás** képernyőt a **3. Bezárás** eljárás lefuttatásához.
    
    Ez a művelet módosítja a költséget az eredeti értékesítési sorban, amelynek -35.00 volt a költségszámítása (5 darab \*7,00) és-30.00 (5 darab \*6,00). Ennek oka az, hogy a készletmodell-csoport az Elsőként be, elsőként ki (FIFO) módszert használja, és darabonként 6,00 a FIFO-költség az első beszerzési rendelésből. Ezenkívül a művelet módosítja a költséget a visszárusoron úgy, hogy az megfeleljen az eredeti értékesítési soron lévő darabonként költségnek. Emiatt a visszárusor költsége 35,00-ről 30,00-ra módosul.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
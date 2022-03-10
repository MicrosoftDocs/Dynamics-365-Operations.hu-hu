---
title: Funkcióbeállítások használata
description: Ez a témakör bemutatja az Elektronikus számlázás funkció beállítását.
author: dkalyuzh
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 41ffc9c7009291a55392e50c5e490d3288d122bc
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371882"
---
# <a name="work-with-feature-setups"></a>Funkcióbeállítások használata

[!include [banner](../includes/banner.md)]

Az elektronikus fájlok generálása és más feldolgozási lépések beállítása (például fájlok digitális aláírása, fájlküldés a kormányzati webszolgáltatásnak, válasz fogadása, illetve tárolása), az elektronikus számlázási funkciók feldolgozási folyamatának, alkalmazhatósági szabályainak és változóinak beállítása.

A beállítási információk a funkcióbeállítási *koncepcióba* kerülnek, létrehozásra, törlésre és módosítására is lehetőség van. Az Elektronikus számlázás funkció teljes verzióiban az adatok is megtekinthetők.

Annyi funkcióbeállítási elemet hozhat létre, amennyit az elektronikus fájlok generálásának, feldolgozásának és fogadásának különböző helyzetéhez szükséges. Bár ezek a funkcióbeállítási elemek független feldolgozási műveletekkel és feltételekkel rendelkezik a végrehajtáshoz, egyetlen elektronikus számlázási funkció részeként jön létre, és öröklik életciklusát és telepítési folyamatát.

## <a name="add-a-feature-setup"></a>Funkcióbeállítások hozzáadása

1. Jelentkezzen be a saját RCS-fiókjába.
2. A **Globalizációs funkció** munkaterületen a **Funkciók** szakaszban válassza ki az **Elektronikus számlázás** csempét.
3. Az Elektronikus **számlázás funkció** lapon válasszon ki egy Vázlat állapotú elektronikus számlázási **funkcióverziót**.
4. A Beállítások **lapon válassza a Hozzáadás lehetőséget** **.**
5. Válasszon a **következő lehetőségek közül** **a** Funkcióbeállítás létrehozása legördülő párbeszédpanel Új mezőcsoport területén:
 
    - **Egyéni beállítás** – új funkcióbeállítás létrehozása, amely üres csatornákat, üres feldolgozási prognózist, az alkalmazhatósági szabályok üres szakaszát és a beállítás típusától függően alapértelmezett változókészletet tartalmaz.
    - **Funkcióbeállításból** – másolat létrehozása az aktuális elektronikus számlázási funkció hatókörében lévő másik funkcióbeállításról.

6. Ha az utolsó **lépésben** az Egyéni beállítás lehetőséget választotta, adja meg a funkcióbeállítási elem nevét és leírását, **majd a Beállítástípus** mezőcsoportban válasszon a következő lehetőségek közül:

    - **Feldolgozási prognózis** – ezzel a beállítással kimenő elektronikus dokumentumokat generálhat és feldolgozhat. Ilyen beállítási típus esetén a rendszer létrehoz egy üres feldolgozási prognózislistát, egy üres szakaszt az alkalmazhatósági szabályok számára, valamint egy alapértelmezett változókészletet. A bejövő elektronikus dokumentumok csatornáin nem fog tudni dolgozni.
    - **Adatcsatorna** – ezzel a beállítással beállíthatja a bejövő elektronikus dokumentumok fogadásának folyamatát az egyik megadott csatornából, és közvetlenül a Microsoftnak Dynamics 365 Finance való átadása, Dynamics 365 Supply Chain Management illetve további műveletek nélkül. Ehhez a beállítási típushoz a rendszer létrehoz egy előre definiált paraméterlistát az adatcsatornákhoz, egy üres szakaszt az alkalmazhatósági szabályok számára, valamint alapértelmezett változókat. Nem adhat hozzá műveleteket a feldolgozási folyamathoz.
    - **Adatcsatorna és feldolgozási prognózis** – ez a beállítástípus hasonlít az adatcsatorna **beállítási** típusához. A bejövő elektronikus dokumentumok pénzügyi vagy ellátásilánc-kezeléshez történő feldolgozása előtt azonban további műveleteket is be lehet állítani a feldolgozási folyamatban.

7. Ha az utolsó **lépésben** **az** Adatcsatornát vagy Az adatcsatornát és a feldolgozási folyamatot választotta, **az** Adatcsatorna kiválasztása mezőben ki kell választania az integrációhoz szükséges csatornát.
8. Válassza a **Létrehozása** lehetőséget.

Miután létrehozott egy funkcióbeállítást, **a beállításához a Szerkesztés** gombra is választhat.

## <a name="edit-a-feature-setup"></a>Funkcióbeállítások szerkesztése

A funkcióbeállítás típusától függően konfigurálhatja a kimenő elektronikus fájlok generálásának, a külső csatornáknak való küldésüknek, illetve a bejövő dokumentumok fogadásának, és a pénzügyi és ellátásilánc-kezelési alkalmazásnak való továbbküldését.

### <a name="data-channel"></a>Adatcsatorna

Az *adatcsatorna az* elektronikus fájlt veszi, és vagy feldolgozza, vagy közvetlenül továbbítja a Pénzügy vagy az Ellátásilánc-kezelés számára. Ez a beállítás nem érhető el a Feldolgozási folyamat típusú **funkcióbeállításoknál**.

Az adatcsatorna beállításhoz írja be a csatorna nevét. Ezután határozza meg a paramétereket a kiválasztott csatornatípus alapján. Az adatcsatorna azonosítójának arra a változóra kell hivatkozni, amely kifejezetten az adatcsatorna azonosítására jött létre. Ezt a rendszer hivatkozásként fogja használni a Pénzügy és az Ellátásilánc-kezelésben.

A Mellékletek **szűrő** lapon meg kell határoznia egy szűrőkészletet, hogy az adott fájlokat ki tudja szűrni a csatornából. Több sort is létrehozhat, ha arra számít, hogy a fájlok fájlnévkiterjesztései eltérőek, vagy a fájlnévtől függően másképpen kell feldolgozni a fájlokat. Itt vannak a fő paraméterek:

- **Név** – adja meg annak a fájlnak a nevét, amelyre a rendszer a feldolgozás során hivatkozik. A Pénzügy és az Ellátásilánc-kezelés alkalmazásokban láthatja a fájlokat a beküldési naplóban.
- **Szűrő** – a fájlok kiválasztására szűrő definiálása.
- **Nem kötelező** – ha törli a jelölést a jelölőnégyzetből, szükség van a fájlra. Ebben az esetben a rendszer hibaüzenetet küld, ha a csatornák nem tartalmaznak a szűrőnek megfelelő fájlokat. Ez a paraméter az e-mailekre vonatkozik.

Ha a csatorna egy postaláda, és a bejövő e-mail cím több mellékletet is tartalmaz, konfigurálhat olyan szabályokat, amelyek meghatározzák, hogyan kezelje a szolgáltatás a mellékleteket. A szolgáltatás az egyes mellékleteket külön elektronikus számlának, illetve egy mellékletet fő számlaként, a többi mellékletet pedig kiegészítésként kezelhet.

### <a name="processing-pipeline"></a>Feldolgozási folyamat

A *feldolgozási prognózis* műveletek *sorozata*, amely a sikeres befejeződésig folyamatosan fut. A feldolgozási prognózis segítségével beállíthatja az elektronikus fájlok generálásának folyamatát, valamint más lépéseket is végrehajthat (például a fájlok digitális aláírását, a külső webes szolgáltatásokba való küldést, a válasz elemezését, valamint a bejövő dokumentumok fogadását és feldolgozását).

A műveletek listája előre definiált. Az Új **és** **a** Törlés gombbal meghatározhatja a műveletek kombinációját, amely logikailag meghatározza a dokumentumok küldési és fogadási folyamatát.

A műveletek sorrendje fontos. A sorrendet a Fel és a Le gombbal **módosíthatja** **·**.

Minden művelethez paraméterek halmaza van, amelyek konfigurálhatók és módosíthatók. A paraméterek adott halmaza a művelet típusától függ.

- **Művelet** – a művelet típusának kiválasztása.
- **Művelet neve** – adja meg a művelet nevét. Ez a név megjelenik a beküldési naplókban és a Pénzügy és az Ellátásilánc-kezelés alkalmazások üzenetei között.
- **Leírás** – további részletekkel szolgál arról, hogy mi a művelet célja a folyamatban.
- **Újrapróbálkozás** engedélyezése – ha bejelöni ezt a jelölőnégyzetet, **kijelölhet egy műveletet az Újrapróbálkozási** **művelet mezőben, és további paramétereket konfigurálhat az Újrapróbálkozási paraméterek** lapon.

    Az újrapróbálkozási funkcióval konfigurálható a szolgáltatás viselkedése, ha egy adott műveletet nem lehet futtatni. Ha például az a külső webszolgáltatás, amelyhez kapcsolódni próbál, nem válaszol, megadhatja, hogy a rendszer hányszor adja meg újra a kapcsolatot, milyen időközönként, és milyen műveletből kell a feldolgozási folyamatban lennie.

- **Eredmények exportálása** – a *feldolgozási* folyamatban egy művelethez bejelérheti ezt a jelölőnégyzetet. Ezután a művelet által a Pénzügy vagy az Ellátásilánc-kezelés alkalmazásban előállított elektronikus fájl exportálható az Elektronikus dokumentumok **benyújtása naplóoldalról**.

### <a name="applicability-rules"></a>Alkalmazhatósági szabályok

*Az alkalmazhatósági szabályok* konfigurálható záradékok, amelyek az elektronikus számlázás funkciónak az elektronikus számlázás funkciókészleten keresztüli futtatására vonatkozó környezetet biztosítanak.
A Pénzügy vagy az Ellátásilánc-kezelés modulból az elektronikus számlázásba elküldött üzleti dokumentumok nem tartalmaznak egyértelmű hivatkozást, amely lehetővé teszi, hogy az elektronikus számlázás lehetővé tévődje az elektronikus számlázás funkció adott verziójának és egy funkcióbeállítási elemének hívását a benyújtás feldolgozásához. Amikor viszont egy üzleti dokumentum helyesen van konfigurálva, akkor tartalmazza azokat az elemeket, amelyek alapján az elektronikus számlázás meghatározza, hogy melyik elektronikus számlázási funkcióverziót és feldolgozási folyamatot kell kiválasztani és futtatni.

Az alkalmazhatósági szabályok segítségével az elektronikus számlázási szolgáltatás megkeresi a pontos elektronikus számlázási funkciókat, amelyek a benyújtás feldolgozásához szükségesek. A megfelelő funkciók megkereshetősége érdekében **az** elküldött üzleti dokumentum Környezet mezői egyeztetésre állnak az alkalmazhatósági szabályokban szereplő záradékokkal.

Az alkalmazhatósági szabályok a következőképpen használhatók:

- Válassza az **Új** lehetőséget, ha új záradékot szeretne hozzáadni az alkalmazhatósági szabályok egy készletéhez.
- Ha törölni **szeretne** egy záradékot, válassza a Törlés lehetőséget.
- Több rekord kiválasztása, **·** **és a Cikkek és logikai utasítások kombinációjának létrehozásához használja a Csoport vagy az Ungroup** gombot. Például válassza ki a csoportosítni kívánt sorokat, majd válassza a **Csoport záradékot**. Ha a feltételek csoportosítva vannak, akkor új oszlop lesz hozzáadva a rácshoz. Ez az oszlop megadja a csoportosított záradék logikai operátorát. A következő típusú operátorok támogatottak:

    - Equal
    - Not equal
    - Nagyobb, mint/Kisebb, mint
    - Nagyobb, mint vagy egyenlő/Kisebb, mint vagy egyenlő
    - Contains
    - Kezdete:

    > [!NOTE]
    > Feltételek szétválasztásakor mindig a legbelső csoportosítási szinttől induljon el.

### <a name="variables"></a>Változók

*A változók* nagyobb rugalmasságot adnak a feldolgozási folyamat és a műveletek közötti folyamat beállítása során. Egyes műveletparaméterek egy változóra hivatkozva ideiglenesen tárolhat adatokat vagy elektronikus fájlokat. Egyes változók az adatok pénzügyi és ellátásilánc-kezelési alkalmazások és az elektronikus számlázási szolgáltatás közötti adatátvitelre használhatók.

A rendszer alapértelmezés szerint néhány változót hoz létre. A BusinessDocumentDataModel **változó például egy JavaScript objektum-notation (JSON) szerkezetben található üzleti adatokat tartalmaz,** amelyek a kapcsolódó alkalmazásból a beküldési folyamat során érkezik a hívásban.

A következő változótípusok érhetők el:

- **Konstans** – tároló a csővezeték-műveletek feldolgozásához használt ideiglenes adatok tárolására.
- **Ügyfélből** – a változó tartalma a Dynamics 365 ügyfélből szerezhető be a beküldési folyamat futtatásakor.
- **Ügyfélre** – a változó tartalma elérhetővé válik a Dynamics 365 ügyfél számára a beküldési folyamat futtatásakor.
- **Adattípus** – válassza ki a változóban tárolt információ adattípusát.

### <a name="parameters"></a>Paraméterek

Az **üzleti adatcsökkentés** letiltása lehetőség az üzleti adatok terhelésének optimalizálására használható, amely a Pénzügyi vagy Ellátásilánc-kezelés alkalmazásból származik az elektronikus dokumentumok benyújtása során. Az optimalizálás segít csökkenteni az elektronikus számlázási szolgáltatásba kerül adatokat a szükséges elektronikus fájlba történő további átalakítás érdekében. Az alapértelmezett érték a **Nem**.

- **Igen** – a Pénzügy és az Ellátásilánc-kezelés az Elektronikus jelentési modulban megadott számlamodell vagy pénzügyi modell (Brazília) **szerkezetének megfelelő JSON-fájlt** **·** **küld.** A modell minden eleme az alkalmazás oldalán található üzleti adatokkal van feltöltve, függetlenül a végleges elektronikus fájlstruktúrától. A modellek általában több üzleti adatot tartalmaznak, mint amennyit a cél fájlstruktúra igényel, és több idő is szükséges az adatok generálása az alkalmazásban. A beállításhoz **Igen** érték szükséges abban a ritka esetben, amikor különböző kimeneti fájlokat szeretne létrehozni egyetlen elektronikus számlázási funkcióban és funkcióbeállításban. Az Igen érték **jól** használható a helyzetekkel, az elektronikus fájlok szerkezetével és az üzleti adatok teljességével kapcsolatos hibaelhárításhoz.
- **Nem** – a pénzügyi vagy ellátásilánc-kezelés üzleti adatok nélkül teszi meg a szolgáltatás első hívását. A hívás célja, hogy információt nyújtson az elektronikus jelentéskészítő (ER) konfigurációról, amely a feldolgozási folyamatban található elektronikus fájlátalakításhoz lesz használva. Ezt az információt a program visszaküldi az alkalmazásnak, amely annak meghatározására használja, hogy az üzleti adatoknak melyik részkészletét kell szerepeletni a Brazília számlamodell vagy pénzügyi modell szerkezetének JSON-fájljában **·** **·**. Az ehhez **a** beállításhoz megadott Nem értékkel csökkenthető az alkalmazás által a szolgáltatásba beküldő üzleti adatok mennyisége, mivel az alkalmazás csak az elektronikus fájl sikeres létrehozásához szükséges üzleti adatokat küldheti el.

### <a name="validate-a-feature-setup"></a>Funkcióbeállítások ellenőrzése

Az ellenőrzés futtatásával ellenőrizheti a teljes konfiguráció egységességét. Ha például egy kötelező paramétert üresen hagytak, az ellenőrzés észleli ezt az inkonzisztenciát, és megjelenik egy figyelmeztető üzenet.

- A Funkcióverzió **beállítása lapon**, a munkaablakban válassza az Ellenőrzés **lehetőséget**.

## <a name="delete-a-feature-setup"></a>Funkcióbeállítások törlése

1. Az Elektronikus **számlázás funkció** lapon válasszon ki egy Vázlat állapotú elektronikus számlázási **funkcióverziót**.
2. A Beállítások **lapon** válassza a Törlés **lehetőséget**.
3. A megjelenő üzenetmezőben kattintson az Igen **gombra, és győződjön meg arról,** hogy törölni szeretné a funkcióbeállítást.

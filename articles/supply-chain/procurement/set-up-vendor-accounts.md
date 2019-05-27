---
title: Szállítókódok beállítása
description: Ez a témakör ismerteti azokat az információkat, amelyeket egy új szállítói számla létrehozása esetén meg kell adnia.
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: smmContactPerson, VendBankAccounts, VendTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 191053
ms.assetid: 06168199-7c54-40e9-a038-4eb274ca958d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7653b01a8d5b80d3026a04d9979906d9ddae5d27
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547675"
---
# <a name="set-up-vendor-accounts"></a>Szállítókódok beállítása

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti azokat az információkat, amelyeket egy új szállítói számla létrehozása esetén meg kell adnia.

Szállítói fiók létrehozásakor meg kell adnia a szállítóra vonatkozó információkat. Ez az információ arra szolgál, hogy az adatokat automatikusan beírja a dokumentumokba és nyomonköveti az olyan tevékenységeket, amelyek érintik a szállítót. Például a szállító következő információit konfigurálhatja:

-   Szállítócsoport hozzárendelése. Minden szállítót hozzá kell rendelni egy szállítócsoporthoz. A szállítóknak a szállítói csoportban vannak olyan paramétereik, amelyek közösek. Lehetnek például ugyanolyan fizetési feltételeik.
-   Konfigurálja a szállítót katalógus importálásához. Szállítók megadhatnak egy fájlt, amely tartalmazza a cikkjeik és a szolgáltatásaik katalógusát. Ezt a fájlt fel lehet tölteni, így a munkatársai rendelhetnek a szállítótól.
-   A szállító hozzárendelése beszerzési kategóriákhoz.
-   Engedélyezheti egy meglévő szállítónak, hogy a szervezeten belül más jogi személlyel is üzleti kapcsolatban legyen.
-   Szállítók várakoztatása bizonyos típusú tranzakciók esetén.
-   A szállító banki adatainak beírása, melyek segítségével a kifizetések elektronikus úton is intézhetők.
-   A szállító adózási, szállítási, számlázási és fizetési adatainak bevitele. Alapértelmezés szerint ezek az adatok automatikusan betöltődnek a szállítóra vonatkozóan létrehozott dokumentumokba.
-   Megadhatja az alapértelmezett pénzügyi dimenziókat, melyek segítségével a szállítóval kapcsolatos tranzakciók automatikusan feladhatók a pénzügyi számlákra.

A szállítói fiókok létrehozásának a folyamatát felgyorsíthatja sablonok létrehozásával. A sablon létrehozásához kattintson a **Szállító** lapon a Műveleti ablakban **Lehetőségek** &gt; **Rögzítési információ** lehetőségre. Ezután kattintson a **Vállalati számlák sablonazonosítója** pontra. A vállalatifiók-sablonok meg vannak osztva más felhasználókkal.  

Felhasználói sablont saját használatra is létrehozhat. Egyéb rekordokhoz, például kapcsolattartókhoz és termékekhez társított szállító nem törölhető.

## <a name="vendor-account-numbers"></a>Szállító fiókszáma.
A fiókszám a szállító egyedi azonosítója. Beállíthatja a fiókszámokat úgy, hogy a rendszer azokat automatikusan létrehozza egy szállító létrehozásakor. A számsorozat konfigurálható a fiókszámok manuális beírásával is. Például előfordulhat, hogy a szállító telefonszámát akarja használni azonosítójaként.

## <a name="vendor-organizations-and-individual-vendors"></a>Szállítói szervezetek és az egyes szállítók
Új szállítói számla létrehozásakor ki kell választania, hogy a szállító egy szervezet vagy személy-e. Választása befolyásolja azt, hogy milyen adatokat kell kitölteni a szállítóról. Személyek esetében ez az információ a keresztnevet, a vezetéknevet és a címet tartalmazza. Egy szervezet esetén ez az információ tartalmazza a szervezeti számot és az alkalmazottak számát.

## <a name="addresses"></a>Címek
Minden egyes szállítóhoz több címet is be lehet állítani, amelyek mindegyike más célt szolgál. Például létrehozhat egy címet, amelynek a célja a **számlázás**. Abban az esetben, ha a szállítóknak csekken teljesíti a kifizetést, beállíthat egy címet, aminek a célja az **átutalás**. Ha meg kell adnia egy címet külföldi bankoknak szóló átutalásokhoz, akkor a cél a **SWIFT** lesz.

## <a name="vendor-contacts"></a>Szállítói kapcsolattartás
Tárolhatja egy szállító kapcsolattartási adatait. Ezek a kapcsolattartási adatok felhasználhatók olyan dokumentumokon, mint például a beszerzési rendelések, vagy az ajánlatkérések (RFQ-k).  

Kapcsolattartási adatok hozzáadásához a szállítóhoz kattintson a **Minden szállító** oldalon, a **Szállítók** lapon, a **Beállítás** csoportban, a **Kapcsolattartók** &gt; **Kapcsolattartók felvitele** lehetőségre.  

Szállítói kapcsolattartókat előröl kezdve is létrehozhat. Másik lehetőségként kimásolhat részleteket egy másik, már a Microsoft Dynamics 365 for Finance and Operations rendszerben regisztrált személytől, és szükség szerint szerkesztheti az adatokat.  

**Megjegyzés:** kapcsolattartók hozzáadása a szállító nem ugyanaz, mint a szóban forgó szállító kapcsolattartási információk hozzáadása. Annak ellenére, hogy a szállító általános kapcsolattartói adatait adhatja meg, akkor is lehet több meghatározott személy, akik az adott vállalatnál kapcsolattartók, és akiknek mind megvannak a saját kapcsolattartási adataik.  

Kapcsolattartás rögzítése nem törölhető, ha egy dokumentumra hivatkozik a kapcsolattartási adat. Ehelyett inaktiválhatja a kapcsolattartót.  

A szállítói kapcsolattartókat hozzáadhatja a Microsoft Office 365 személyes kapcsolattartókhoz. Azonban először be kell állítania a Finance and Operations és Office 365 közötti szinkronizálást mind Microsoft Exchange Server szinkronizálásban, mind a Microsoft Outlook beállítási varázslóban.

## <a name="vendors-in-different-legal-entities"></a>Szállítók különböző jogi személyekként
Ha a szállító csak egy jogi személyként van regisztrálva szervezetében, és más jogi személyeket kell regisztrálni ugyanahhoz a szállítóhoz, használhatja a **Szállító hozzáadása egy másik jogi személyhez** lapot, hogy konfigurálja a szállítót, hogy áll egy másik jogi személlyel üzletelhessen. Válasszon egy szállítói csoportot, egy pénznemet, és a szállító várakoztatási állapotát a kijelölt jogi személyhez.  

Ha a szervezeten belül több jogi személy ugyanazzal a szállítóval köt üzleteket, és az adott szállítóhoz mindegyik jogi személy külön szállítói számlát tart fenn, akkor egyesíteni lehet a szállítói számlák partnerazonosítóit. Ezzel a módszerrel az információk, például a cím és az alkalmazottak száma is megosztható, úgy, hogy csak egy helyen kelljen frissíteni.  

Partnerazonosítók egyesítéséhez kövesse az alábbi lépéseket.

1.  A **Globális címjegyzék** lapon válassza azokat a címjegyzék-rekordokat, amelyek valamennyi jogi személynél azoknak a szállítónak felelnek meg, akiknek szerepelnie kell a hozzárendelésben.
2.  A műveleti panelen kattintson **Rekordok egyesítése** elemre.

## <a name="agreements"></a>Megállapodások
Szállítói számla beállításakor érdemes regisztrálnia is a szerződéseket, amelyeket a szállítóval kötött. Ár- és engedménymegállapodásokat beállíthatja a szállítórekord műveletek használatával. Szintén beállítható egy beszerzési szerződés a **Beszerzési szerződések** oldalon.

## <a name="putting-a-vendor-on-hold"></a>A szállító várakoztatásra helyezése
A szállítót különböző tranzakciótípusokhoz lehet varakozásra helyezni. Az alábbi lehetőségek közül választhat:

-   **Nem** – nem lett várakoztatásra helyezve a szállító.
-   **Számla** – nem adható fel számla a szállító részére.
-   **Minden** – a szállító minden tranzakciótípus esetén várakozásra van helyezve. Ezek a tranzakció típusok a következők lehetnek: beszerzési igénylések, számlák és kifizetések.
-   **Fizetés** – nem hozható létre fizetés a szállító számára.
-   **Igénylés**– csak beszerzési igénylés hozható létre. Nem lehet más tranzakciót létrehozni.
-   **Soha** – a szállító soha nem lesz várakoztatott inaktivitás miatt.

Ha a szállítót várakoztatja, akkor megadhatja az okot és a várakoztatott állapot végét jelölő dátumot is. Ha nem ad meg egy záró dátumot, a szállító várakoztatott állapota határozatlan ideig tart.

Tömegesen **Mind** értékre frissítheti a várakoztatott állapotot a szállítóknál a **Szállító inaktiválása** oldal kiválasztott feltételei alapján, majd hozzárendel egy okot arra vonatkozóan, hogy miért van a szállító várakoztatott állapotban.

A következő kritériumok olyan szállítók bevonására használhatók, akik egy adott időszakban inaktívak voltak, illetve olyan szállítók bevonására vagy kizárására, akik alkalmazottak, továbbá az olyan szállítók kizárására, akik türelmi idő alatt vannak a következő várakoztatás előtt.

- Attól függően, hogy hány napot állít be az **Inaktivitási időszak** mezőben, a **Szállító inaktiválása** oldalon, az alkalmazás kiszámítja a legfrissebb dátumot, amikor a szállító bármilyen tevékenysége inaktívnak tekinthető. Ez azt jelenti, hogy az aktuális dátumból le kell vonni az Ön által megadott napoknak a számát. Ha egy vagy több olyan számla található a szállítónál, ahol a dátum a legkésőbbi kiszámított dátumnál később van, akkor a szállító kizárásra kerül az inaktiválásból. Ezt akkor is ellenőrzi a rendszer, ha a szállítónak befizetései vannak az adott dátum után, illetve nyitott beszerzési rendelésekkel, ajánlatkérésekkel vagy válaszokkal rendelkezik.
- A **Türelmi idő a következő felfüggesztés előtt** mezőben található napok száma segítségével számítja ki a rendszer a legújabb türelmi idő dátumát. Ez azt jelenti, hogy az aktuális dátumból le kell vonni az Ön által megadott napok számát. Ez csak a korábban inaktivált szállítókra vonatkozik. Előző inaktiválás esetén az alkalmazás ellenőrzi az inaktiválás egyéb előfordulásainak előzményeit a szállítónál, és ellenőrzi, hogy a legutóbbi inaktiválás a legutóbbi türelmi dátum előtt történt-e. Ebben az esetben a szállítót belevonja a rendszer az inaktiválási folyamatba.
- Az **Alkalmazottak megjelenítése** paraméter azokra a szállítókra vonatkozik, amelyek egy alkalmazotthoz kapcsolódnak. Beállíthatja, hogy szerepeltetni kívánja-e ezeket az alkalmazottakat.

Ez a folyamat mindig kizárja azokat a szállítókat, amelyeknél a **Szállító várakoztatása** mező értéke **Soha**.

Az ellenőrzéseket teljesítő szállítók várakoztatott állapotba kerülnek, ami a **Szállító várakoztatása** mezőt **Mind** értékre, az **Ok** mezőt pedig a kijelölt értékre állítja. A várakoztatott előzményekhez egy rekord kerül létrehozásra a szállítónál.

## <a name="vendor-invoice-account"></a>Szállító számlaszáma
Ha egynél több szállító van ugyanazon a számlázási címen, vagy ha egy szállító egy harmadik félen keresztül kapja a számláját, megadhatja a számlázási fiókot a szállító rekordján. A számlafogadó az a számla, amelyen követel tételként jelenik meg a számlaösszeg olyankor, amikor szállítói számlát hoz létre egy beszerzési rendelésből. Ha nem ad meg számlafogadót a szállítói rekordon, akkor a szállítói számla lesz a számlafogadó.

## <a name="vendor-bank-accounts"></a>Szállítói bankszámlák
Ha kifizetést kell végrehajtania a szállítói bankszámlára, akkor szállító bankjára és bankszámlákra vonatkozó információkat vihet fel a **Szállítói bankszámlák** oldalra. A kiválasztott bankszámla érvényesítésével és fizetéseivel kapcsolatos adatokat is megadhat. Például hozzáadhat ellenőrző tranzakciókat a szállítói bankszámlához. Ezek az ellenőrző tranzakciók arra használhatók, hogy meggyőződjenek a számlaadatok pontosságáról, például a banki regisztrációs azonosítók és számlaszámok helyességéről. Meg kell adnia egy alapértelmezett számlát a szállítói kifizetésekhez. Azonban amikor tényleges kifizetést hajt végre akkor kicserélheti ezt a számlát a szállító egy egyéb számlájára.

## <a name="ledger-accounts"></a>Főkönyvi számlák
Megadhatja a szállítói számlanaplón automatikusan megjelenő alapértelmezett számlákat a megadott szállítóhoz. Ez a lehetőséget akkor lehet hasznos, ha általában azonos típusú elemeket, vagy szolgáltatásokat szokott fizetni, ugyanazoktól a szállítóktól. Ha megad egy alapértelmezett számlát, gyorsan és hatékonyan írhat be naplóbejegyzéseket a számlanaplóba. A megadott alapértelmezett számlák nincsenek használatban a beszerzési rendelésekhez, vagy azokhoz a szállítói számlákhoz, amelyek a **Szállítói számla** oldalon vannak rögzítve.  

Alapértelmezett számlákat választhat az **Alapértelmezett számla beállítása** lapon, amely megnyitható a **Számla** lapon szállítórekordon. Naplóbejegyzések amiket itt kiválaszt megjelennek a szállítói számlák szűrt listáján, amikor beír egy naplóbejegyzést. A számlák közül megadhat egy alapértelmezett számlát.




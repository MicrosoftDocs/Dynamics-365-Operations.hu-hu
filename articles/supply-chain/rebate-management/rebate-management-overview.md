---
title: Visszatérítés-kezelő modul áttekintése
description: Ez a témakör a Microsoft Dynamics 365 Supply Chain Management Visszatérítés-kezelési moduljáról ad áttekintést.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 7afad911454916c49cda47253736defdd7e9b16b
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020459"
---
# <a name="rebate-management-module-overview"></a>Visszatérítés-kezelő modul áttekintése

[!include [banner](../includes/banner.md)]

A **Visszatérítés-kezelő modul** segítségével szerződéseket, ajánlatokat vagy megállapodásokat hozhat létre vállalkozása és vevői vagy szállítói között, így kiszámíthatja a visszatérítéseket, levonásokat és jogdíjakat. A visszatérítés-kezelés nyomon követi és fenntartja a visszatérítési és levonási tranzakciókat egy központi helyen, ahol a felhasználók hatékonyan létrehozhatják, felülvizsgálhat és feldolgozhatják azokat.

A visszatérítés-kezelés támogatja a *visszatérítések* létrehozását, karbantartását és feldolgozását. A visszatérítés a vételár egy részének az eladó vagy a vevő általi visszaadása. A visszatérítések jellemzően egy adott árumennyiség vagy -érték meghatározott időszakban történő megvásárlásán alapulnak. Az engedményekkel ellentétben a visszatérítések a beszerzési összeg teljes számlázása után történnek.

A visszatérítés-kezelés a *levonásokat* is támogatja. A levonás olyan kompenzáció, ellenérték vagy díj, amelyet vagy licencért vagy szellemi tulajdon, például márka, szerzői jog vagy szabadalom használatára vonatkozó kiváltságért fizetnek, vagy a természeti erőforrások halászatra, vadászatra vagy bányászatra való felhasználásának kiváltsága. A levonásokat általában a realizált felhasználásból származó bevétel vagy nyereség százalékában számítják ki. Minél többet használják a szellemi tulajdont vagy a természeti erőforrást, annál nagyobb a levonás, amely megvalósul.

Ezenkívül a Visszatérítés-kezelés támogatja az ügyfél *jogdíjait* is. A jogdíjak olyan kifizetések, amelyeket az egyik fél a licenc jogosultjának vagy a franchise felhasználójának az eszköz használatának jogáért fizet.

A visszatérítés-kezelés lehetővé teszi a fedezetek, visszatérítések és leírások feladási profiljainak meghatározását. Ezenkívül a feladások egy adott vevőhöz vagy szállítóhoz is meghatározhatóak. Ily módon azok az ajánlatok, amelyek nem vonatkoznak az összes vevői vagy szállítói forgatókönyvre, feladásokkal nyomon követhetőek.

A visszatérítési tranzakciók automatikusan jönnek létre a kötegelt feladatokban kiválasztott és ütemezett számítási módszer alapján. Ezenkívül munkafolyamatokat is beállíthat a megállapodások kezelésére, felülvizsgálatára és jóváhagyására.

## <a name="basis-calculation"></a>Számítás alapja

A vevői visszatérítések, a vevői jogdíjak és a szállítói visszatérítések az üzleti igényektől függően különböző alapokat használhatnak:

- A vevői visszatérítések alapulhatnak értékesítési rendeléseken, szállítóleveleken vagy számlákon.
- A vevői jogdíjak alapulhatnak értékesítési rendeléseken, szállítóleveleken vagy kifizetett számlákon.
- A szállítói visszatérítések beszerzési rendeléseken vagy értékesítési rendeléseken alapulhatnak. Ezek a visszatérítési szállítótól vásárolt és a vevőknek értékesítési számlákon keresztül értékesített termékek alapján számíthatók ki.

## <a name="flexible-calculations"></a>Rugalmas számítások

A visszatérítés számítási időszakai mind a vevői, mind a szállítói ajánlatokhoz rendelkezésre állnak. A számítási időszak határozza meg az ajánlat hosszát, a számítási gyakoriságot és a számítási időszakot. A visszatérítések a visszatérítési időszak alatt a minősített termékek értékesítési rendelési mennyiségei vagy összegei alapján kerülnek elhatárolásra.

Minden egyes megállapodásszámításhoz a következő időszakok bármelyike állítható be:

- Számla
- Nap
- Hét
- Hónap
- Negyedév
- Év
- Egyéni időszak
- A korábban felsorolt időszakok bármelyikének többszöröse

A számítás alkalmazható az egyes vevőkre és termékekre, vevők és termékek csoportjaira, illetve az összes vevőre és termékre. A több részletsorból álló visszatérítések különböző jogosultsági dátumtartományokkal is rendelkezhetnek. A fedezeti és igénylési időszakok eltérőek lehetnek. A fedezeteket például minden nap fel lehet dolgozni, míg az igénylések feldolgozása havonta egyszer történik.

A visszatérítések számos különböző paraméter alapján konfigurálhatók. Konfigurálhatók például százalékként, díjként vagy rögzített összegként. Négy fő számítási módszer van:

- Lépcsőzetes
- Halmozott
- Gördülő
- Összérték

A visszatérítési számítás eredményei más visszatérítésekkel is csökkenthetők, attól függően, hogy a visszatérítést a nettó összeg alapján kell-e kiszámítani.

A szállítói oldalon a visszatérítések kiszámíthatják az árat az először be, először ki (FIFO) szabály, a legutóbbi vételár, az átlagos vételár vagy az eladási ár alapján.

## <a name="rebate-target-transactions"></a>Visszatérítési céltranzakciók

A visszatérítési ajánlat vagy megállapodás által generált kimenetek lehetnek pénzügyi tételek vagy cikkek.

A pénzügyi kimeneteket a feladási profilból a megállapodáshoz rendelt fizetési típus határozza meg. Ezek a kimenetek tartalmazhatnak vevői levonási naplókat, szabadszöveges számlákat és szállítói számlákat. Auditálási célokból a pénzügyi visszatérítési céltranzakciók az eredeti visszatérítési megállapodásra való hivatkozást tartalmaznak.

A cikk-kimenetek ingyenes cikkértékesítési rendelést hoznak létre a vevői visszatérítések és beszerzési rendelést a szállítói visszatérítések számára. A cikk-visszatérítési céltranzakciók olyan beállításokat tartalmaznak, amelyek meghatározzák, hogy melyik visszatérítési hivatkozást kell megadni az ingyenes cikkértékesítési rendelésen vagy beszerzési rendelésen.

## <a name="accurate-rebate-calculations"></a>Pontos visszatérítési számítások

A társított ügyletek kombinációja, a számítások gyakorisága, a számítási alap és a kiválasztott számítási módszer határozza meg a visszatérítési számítások pontosságát és precizitását. A visszatérítési fedezetek felhasználhatók a feladott és igényelt értékek elhatárolására.

A céltartalékok naponta vagy havonta kezelhetők. A funkció azonban bármely meghatározott gyakorisággal lefoglalhatja vagy kifizetheti a visszatérítést, vagy bevételezheti a kifizetést. A felhasználók a kifizetés során bármikor könnyedén módosíthatnak egy csomagot vagy kifizetési összeget.

A felhasználóknak már nem kell két lépésben kezelniük az ajánlatokat vagy fedezeteket. A fedezetek és leírások közvetlenül a főkönyvbe vannak feladva. Ezenkívül a jóváírások automatikusan létrehozhatók. Ezért teljes mértékben integrálható a kötelezettségekkel és a követelésekkel. A feldolgozás során a számítások figyelembe veszik a kiegyenlítési engedményeket, a kifizetett számlákat, a fizetési engedményeket és a meglévő jóváírásokat, hogy biztosítsák az összegek és értékek pontos kiszámítását.

A visszatérítések kiszámításakor a folyamat olyan tranzakciókat hoz létre, amelyek a feladás előtt felülvizsgálhatók. Ezután létre lehet hozni egy napló-, jóváírás- vagy tartozik tranzakciót. Egy külön folyamattal adhatók fel visszatérítési és levonási tranzakciók. A megfelelőség, a hatékonyság és az átláthatóság biztosítása érdekében jelentési kimutatások és tranzakciólisták kérhetők le.

## <a name="guaranteed-royalty-payments"></a>Garantált jogdíjfizetések

A visszatérítés-kezelésben az automatikus fizetésgenerálás lehetővé teszi a jogdíjak gyors és könnyű kezelését, még akkor is, ha garantált minimumok érvényesek. 

## <a name="maximizing-spend-versus-rebates"></a>A kiadások maximalizálása a visszatérítésekkel szemben

A szállítók és a termékek terület szerint csoportosíthatóak, és a tranzakció országától vagy régiójától függően különböző ajánlatok is biztosíthatók. Amikor a felhasználók kiválasztják a termékeket, meghatározhatják a benne lévő cikkeket és a visszatérítési kiegyenlítésben használni használt cikkek számát.

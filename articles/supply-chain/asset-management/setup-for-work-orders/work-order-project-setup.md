---
title: Munkarendelési projekt beállítása
description: Ez a témakör a munkarendelés projektbeállítását mutatja be az Eszközkezelésben.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderProjectSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 031e61549474745360ac00f9a66bef7a9dbaaf96
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021554"
---
# <a name="work-order-project-setup"></a>Munkarendelési projekt beállítása

[!include [banner](../../includes/banner.md)]

 

Az **Eszközkezelés** modulban minden munkarendelési feladathoz szükséges egy projektkapcsolat. A munkarendelési feladathoz társított projekt segítségével nyomon követheti a különböző projektek Eszközkezeléshez kapcsolódó költségeit, például belső karbantartási projektek, szolgáltatáskezelési projektek és befektetési projektek esetén. 

## <a name="project-setup-for-a-work-order-job"></a>Egy munkarendelési feladat projektbeállítása

Ha munkarendelési feladatot hoz létre munkarendelésen, akkor a **Projektvezetés és könyvelés** modulban történt projektbeállítás és az **Eszközkezelés** modulban történt munkarendelési projektbeállítás határozza meg, hogy a projekteket hogyan lehet egy olyan eszközön költségkontrollhoz használni, amelyet az adott munkarendelési feladaton kiválasztottak. Ez a szakasz a projekt beállításainak következő részeit írja le, amelyek a munkarendeléshez használatosak: a fölérendelt projekt (projektazonosító), projekttípus, projekttevékenységek és pénzügyi dimenziók:

- Ha munkarendelési feladatot hoz létre egy munkarendelésen, a rendszer automatikusan létrehoz egy egyedi projektazonosítót és egy kapcsolódó projekttevékenységet. Ha azonban egy munkarendelésen számos munkarendelési feladatban szerepel ugyanaz az eszköz, akkor a rendszer ugyanazt a projektazonosítót használja hozzájuk. Más szóval egy projektazonosító jön létre egy munkarendelésen minden eszközhöz.

    - A munkarendelési feladathoz tartozó fölérendelt projekt (projektazonosító) a fölérendelt projekt beállításaiban található. (A fölérendelt projekt beállításával kapcsolatos további tudnivalókat lásd a következő szakaszban.) Ha például egy vevőt vagy egy munkavégzési helyszínt rendel egy adott fölérendelt projekthez, akkor a rendszer minden alkalommal a fölérendelt projektet használja, amikor munkarendeléseket hoz létre az adott vevőhöz vagy munkavégzési helyszínhez. Ha például egy munkavégzési helyszínhez nem kapcsol egy meghatározott projektazonosítót, akkor a munkarendelés projektbeállításban található következő releváns fölérendelt projektet használja a rendszer.
    - Minden egyes projektazonosítóhoz szükséges egy projekttípus. A projekttípus a projektcsoport-beállítás beállításai között található. (A projektcsoport beállításával kapcsolatos további tudnivalókat lásd a következő szakaszban.) Ha a projektcsoport beállításai között nem található egyezés, akkor a rendszer a fölérendelt projekt projektcsoport-beállításait használja.
    - A projekttevékenységek előrejelzésekben és naplókban való szükségességének beállítását a rendszer a fölérendelt projektből másolja a munkarendelési projektbe. Ha az **Óra**, **Költség** és **Cikk** beállítások értéke **Igen** a fölérendelt projektként használt rojektnél, akkor a projekttevékenység kötelező az előrejelzéseken és naplókban. (Ezeket a beállításokat úgy érheti el, ha a **Projektvezetés és könyvelés** \> **Projektek** \> **Összes projekt** elemet választja, majd kiválasztja a fölérendelt projektként használt projektet. A beállítások a **Beállítás** gyorslap **Tevékenység megkövetelése naplókban** szakaszában találhatók.)

- A program átmásolja az eszközből a pénzügyi dimenziókat, és egyesíti azokat a fölérendelt projekttel.

A következő szakasz bemutatja, hogyan lehet beállítani a fölérendelt projekteket és a projektcsoportokat. A munkarendelések ellenőrzésére a fölérendelt projekt és a fölérendelt csoportok használhatók. A munkarendelésekkel kapcsolatos jelentéskészítésre is használhatók.

## <a name="set-up-work-order-projects"></a>Munkarendelési projektek beállítása

A munkarendelések létrehozása előtt be kell állítania a munkarendelési projekteket. A **Munkarendelési projekt beállítása** lap (**Eszközkezelés** \> **Beállítás** \> **Munkarendelések** \> **Projektbeállítás**) két lapot tartalmaz: A **Fölérendelt projekt** és a **Projektcsoport** lapot.

A **Fölérendelt projekt** lapont beállíthatja a projektkapcsolatokat, amelyek akkor használhatók, ha azon az eszközön nincs projekt kiválasztva, amelyet a munkarendelési feladathoz kiválasztottak. Nem kötelező beállítani fölérendelt projektet, ha a vállalat eszközprojekteket használ. Csak akkor releváns, ha eszközprojektek helyett munkarendelési projekteket szeretne használni. Ebben az esetben legalább egy fölérendelt projektet be kell állítani.

A **Projektcsoport** lapon beállíthatja azokat a projektcsoportokat, amelyek a Munkarendelés-típusokhoz, az eszköztípusokhoz és az eszközökhöz társíthatók.

A projektcsoportok a költség-ellenőrzéshez használt kategóriák (csoportok) létrehozásához használhatók. Ha például egy adott eszköztípushoz vagy munkarendelés-típushoz hoz létre projektcsoportokat, akkor típus szerint részletesen nyomon követheti a karbantartási költségeket.

A projektcsoportok nem kötelezőek. Ha nem állított be projektcsoportoket, akkor a rendszer a fölérendelt projekt segítségével határozza meg a projektcsoportot, és létrehoz egy alárendelt projektet a fölérendelt projekt projektcsoportjából.

A beállítás lehetővé teszi a teljes integrációt a **Projektvezetés és könyvelés** modullal. Ennek megfelelően nyomon követheti a kapcsolódó projektek munkarendeléseivel kapcsolatos költségeket. A következő eljárás a munkarendelés-projektek beállítását írja le.

1. Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Munkarendelések** \> **Projektbeállítás** elemet.
2. A **Fölérendelt projekt** lapon válassza a **Hozzáadás** lehetőséget.
3. A **Munkarendelés-típus**, **Munkavégzési helyszín**, **Eszköztípus** és **Eszköz** mezőkben válassza ki a szükséges értékeket. Minden hozzáadott sorhoz kiválaszthat csak egy mezőt és több mezőt is. A beállított mezők száma határozza meg a kombinációt, amely az Eszközkezelésben a projektazonosító kiválasztásakor használatos. 

    Ha kiválaszt egy munkavégzési helyszínt, akkor a rendszer automatikusan szerepelteti a kapcsolódó alárendelt helyszíneket. Ha kiválaszt egy eszközt, akkor ugyanahhoz az eszközhöz több munkarendelési projektbeállítási sort is létrehozhat, de különböző projekteket is kiválaszthat az adott eszközhöz.

4. A **Projektazonosító** mezőben válassza ki a projektet, amelyiknek a 3. lépésben létrehozott beállításhoz kell kapcsolódnia.
5. Ha a projektbeállítás csak korlátozott időtartamra érvényes, válasszon egy befejezési dátumot a **Befejezési dátum** mezőben. Ellenkező esetben válassza a **Nincs** lehetőséget.

    Alapértelmezés szerint a kezdési dátum az a dátum, amikor a munkarendelési projektet hozzáadja az oldalhoz. A rendszer az **Érvényesség kezdete** mezővel vezérli, amely alapértelmezés szerint rejtett. Az **Érvényesség kezdete** mező megjelenítéséhez válassza a **Megtekintés** \> **Összes** elemet. Ezt követően az **Érvényesség kezdete** mezőt a **Befejezési dátum** mezővel együtt használhatja a munkarendelési projekt korlátozott időtartamú érvényességének beállításához.

    ![Munkarendelési projekt beállítási oldala](media/17-setup-for-work-orders.png)

6. A **Projektcsoport** lapon válassza a **Hozzáadás** lehetőséget.
7. A **Munkarendelés típusa** mezőben válasszon ki egy munkarendelés-típust.
8. Ha szeretné, hogy a projektcsoport társítása pontosabb legyen, válasszon egy eszköztípust az **Eszköztípus** mezőben, vagy egy eszközt az **Eszköz** mezőben.
9. A **Projektcsoport** mezőben válassza ki azt a projektcsoportot, amelynek a Munkarendelés-típushoz kell kapcsolódnia. Például egy **Megelőző karbantartás** nevű munkarendelés-típust valószínűleg a **Megel. karb.** vagy **Belső** nevű projektcsoporthoz társítják. Alternatív megoldásként az olyan munkarendelésekhez használt **Befektetés** munkarendelés-típus, amelyek befektetésekhez és tárgyi eszközökhöz kapcsolódnak, társítható egy **Befektet** vagy **Befektetés** projektcsoporthoz.
10. Válassza a **Mentés** lehetőséget.

![Munkarendelések projekt beállítási lapja, Munkarendelés hozzáadása](media/18-setup-for-work-orders.png)

> [!NOTE]
> Minden alkalommal, amikor munkarendelési sort hoz létre, az Eszközkezelés megkeresi azt a projektcsoportot, amely kapcsolódik a munkarendelési feladat projektjéhez. A Keresés az ebben a témakörben ismertetett beállításon alapul. Minden projektcsoport tartalmaz egy kapcsolódó projekttípust. Az **Idő- és anyageszámolás** vagy **Rögzített ár** projekttípussal rendelkező projektcsoportok csak olyan eszközök esetén érvényesek, amelyek kapcsolódnak a vevői számlához.
>
> A fölérendelt projektek és projektcsoportok esetén, amikor a rendszer kiválasztja az elérhető munkarendelési projektet vagy projektcsoportot, a kiválasztás az előző eljárás használatával létrehozott rekordok alapján történik. Az Eszközkezelés végigfut a munkarendelési projekthez kapcsolódó rekordokon, lehetséges egyezést keresve. Mindig a leginkább meghatározott kombinációt ellenőrzi először. Más szóval a munkarendelés fölérendelt projektjéhez az Eszközkezelés modul először az **Eszköz** mezővel való lehetséges egyezést ellenőrzi. Ha nem talál egyezést, akkor az **Eszköztípus** mezővel való egyezést ellenőrzi. Ha nem talál egyezést, akkor a **Munkavégzési helyszín** mezővel való egyezést ellenőrzi, és így tovább. Ahogy az a **Munkarendelési projektbeállítás** oldal elrendezésében is látható, ez a viselkedésmód azt jelenti, hogy a legspecifikusabb kombináció megkereséséhez az Eszközkezelés minden egyes rekordot jobbról balra ellenőriz egyezést keresve. Ha nem talál egyezést, akkor az alapértelmezett rekord, amelyben csak a projekt azonosítója van kiválasztva, lesz használva A kapcsolódó projektcsoport megkeresésének folyamata hasonló. Az Eszközkezelés először az **Eszköz** mezővel való lehetséges egyezést ellenőrzi, majd az **Eszköztípus** mezővel, majd a **Munkarendelés-típus** mezővel. Ha nem talál egyezést, akkor az alapértelmezett rekord, amelyben csak a projektcsoport van kiválasztva, lesz használva.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
---
title: Szállítók kategóriakérései
description: Ez a témakör azt ismerteti, hogyan kérhetnek a szállítók beszerzési kategóriákat a számlájukhoz. Ismerteti a beszerzési ügynökök által végrehajtott jóváhagyási folyamatot is.
author: GalynaFedorova
ms.date: 04/19/2021
ms.topic: article
ms.search.form: VendRequestNewCategory
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-04-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 9874151a5d82cc3441741489065877b78bab7bf5
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671197"
---
# <a name="category-requests-from-vendors"></a>Szállítók kategóriakérései

[!include [banner](../includes/banner.md)]

A szállítók a kategóriakérési folyamat során új beszerzési kategóriákat kérnek a számlájukhoz társítva. Ezek a beszerzési kategóriák ezután felhasználhatók a kapcsolódó beszerzési és forráskezelési folyamatokban. (A további tudnivalókat lásd: [Beszerzési katalógusok áttekintése](procurement-catalogs.md).)

A kategóriakéréseket a szállítók kezdeményezik a **Szállítói adatok** munkaterületén. Ezután elküldik őket ellenőrzésre és jóváhagyásra az ügynökségnek. A jóváhagyott kategóriákat a rendszer hozzáadja a szállító számlájához tartozó beszerzési kategóriák listájához.

## <a name="turn-the-category-requests-from-vendors-feature-on-or-off"></a>A kategóriakérések be- és kikapcsolása a szállítóktól

Az Ellátásilánc-kezelés 10.0.25-ös verziója szerint ez a funkció alapértelmezés szerint be van kapcsolva. A rendszergazdák úgy *kapcsolhatnak*[be](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) és kapcsolhatnak ki, hogy a Szolgáltatáskezelési munkaterület szállítói együttműködési funkciójával keresi meg, hogy a szállítók alkalmazhatják-e a beszerzési kategóriákat.

Ha ez a funkció be van kapcsolva, akkor is manuálisan hozzá lehet adni beszerzési kategóriákat a szállítói számlákhoz. További információk: [Szállítók jóváhagyása konkrét beszerzési kategóriákra vonatkozóan](tasks/approve-vendors-specific-procurement-categories.md).

## <a name="vendor-collaboration-requirements"></a>Szállítói együttműködés követelményei

A szállító csak akkor kommunikálhat kategóriakérésekkel, ha be van állítva a szállítói együttműködéshez.

A szállítónak legalább egy szállítói együttműködési felhasználóval kell rendelkeznie. Kategóriakéréseket csak a *Szállító rendszergazdai (külső)* biztonsági szerepkörrel rendelkező szállító felhasználók hozhatnak létre és küldhetnek be.

További információkért lásd: [Szállítói együttműködés beállítása és fenntartása](set-up-maintain-vendor-collaboration.md).

## <a name="set-up-the-vendor-category-request-workflow"></a>Szállítói kategóriakérésre vonatkozó munkafolyamat beállítása

A *Szállítói kategóriakérés* munkafolyamatát be kell állítani a beszerzési és forráskezelési munkafolyamatokban. A szállítók új kategóriakéréseket fognak benyújtani, ezeket ön áttekintheti és jóváhagyhatja. A kért beszerzési kategóriák a kategóriakérés jóváhagyása után hozzáadásra kerülnek a szállítói számlához.

A következő példa bemutatja, hogyan lehet egy egyszerű *Szállítói kategóriakérés* munkafolyamatot beállítani, amely egyetlen jóváhagyóval rendelkezik. A belső folyamatok áttekintése után meg kell határoznia a megfelelő munkafolyamat-beállításokat az ügynökség számára.

1. Nyissa meg a **Beszerzés és forrás \> Beállítás \> Beszerzés és forráskezelés munkafolyamatai** pontot.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A párbeszédpanelen válassza ki a **Szállítói kategóriakérés munkafolyamatot** a munkafolyamat-szerkesztő megnyitásához.
1. Jelentkezzen be a munkafolyamat-szerkesztőbe.
1. A műveleti panelen válassza a **Tulajdonságok** elemet.
1. Adja meg az utasítás szövegét a munkafolyamat **Tulajdonságok** oldalán, a **Beküldési utasítások** mezőben. Az útmutatások a kategóriakérések elküldésekor láthatóvá válnak a szállítók számára.
1. Zárja be a **Tulajdonságok** képernyőt.
1. Húzza az **Új kategóriakérés jóváhagyása** munkafolyamat-elemet a vászonra.
1. Húzza át az **Indítás** munkafolyamat-elem egyik hivatkozását az **Új kategóriakérés jóváhagyása** munkafolyamat-elemre.
1. Húzza át az **Új kategóriakérés jóváhagyása** munkafolyamat-elem egyik hivatkozását a **Befejezés** munkafolyamat-elemre.
1. Koppintson duplán (vagy kattintson duplán) az **Új kategóriakérés jóváhagyása** munkafolyamat-elemre.
1. Válassza ki és tartsa lenyomva (vagy kattintson a jobb gombbal) az **1. lépés** munkafolyamat-elemére, majd válassza a **Tulajdonságok** lehetőséget.
1. Adja meg a tárgy szövegét a munkafolyamat-elem **Tulajdonságok** oldalán, a **Munkaelem tárgya** mezőben. Ez a szöveg a megjelenik a **Tárgy** mező értékeként a **Hozzám rendelt munkaelemek** oldalon.
1. Írja be az utasítások szövegét a **Munkatétel utasításai** mezőbe. Az utasítások a jóváhagyók számára láthatóvá válnak, amikor kiválasztják a **Munkafolyamat** elemet egy kategóriakérés műveleti ablaktábláján.
1. A bal oldali panelen válassza a **Hozzárendelés** gombot.
1. A **Hozzárendelés típusa** lapon állítsa be a **Felhasználók hozzárendelése ehhez a munkafolyamat-elemhez** beállítást *Felhasználó* értékre.
1. A **Felhasználó** lap **Elérhető felhasználók** listájáról válasszon ki egy jóváhagyót. Jelöljön ki például egy felhasználót a beszerzési osztályon.
1. Válassza a jobbra nyíl gombot (**\>**) a jóváhagyó **Kiválasztott felhasználók** listára történő átmozgatásához.
1. Zárja be a **Tulajdonságok** képernyőt.
1. Válassza a **Mentés és bezárás** lehetőséget.
1. A **Verzió megjegyzései** mezőbe írja be a munkafolyamattal kapcsolatos megjegyzéseket.
1. A munkafolyamat mentéséhez kattintson az **Ok** lehetőségre.
1. Ha készen áll a munkafolyamat tesztelésére, válassza az **Új verzió aktiválása** lehetőséget. Ellenkező esetben válassza a **Ne aktiválja az új verziót** lehetőséget.
1. A munkafolyamat beállításának befejezéséhez válassza az **Ok** lehetőséget.

> [!TIP]
> Ha az ügynökség számára nem szükséges a kategóriakérések jóváhagyása, akkor érdemes beállítania a munkafolyamatot automatikus jóváhagyásra.

További tájékoztatás a munkafolyamatok beállításáról: [A munkafolyamat-rendszer áttekintése](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md).

## <a name="create-and-submit-a-category-request"></a>Kategóriakérés létrehozása és elküldése

Ez a szakasz bemutatja, hogy a szállítók hogyan használhatják a **Szállítói információk** munkaterületet a kategóriakérések létrehozására, szerkesztésére, megtekintésére és elküldésére.

### <a name="start-a-new-request"></a>Új kérelem indítása

A következő lépések követésével indítja el az új kategóriakérést.

1. A **Szállítói információk** munkaterületén jelölje ki a **Kategóriakérések** csempét.
1. A **Kategóriakérések** oldalon a műveleti ablaktáblán válassza az **Új kategóriakérés** lehetőséget.
1. Az **Új kategóriakérés** párbeszédpanelen keresse meg azt a kategóriát, amelyikre alkalmazni szeretné a fában való navigációval és/vagy a lista tetejét található szűrővel. Jelölje be az egyes megfelelő kategóriák jelölőnégyzetét.

    Vegye figyelembe az alábbiakat:

    - A szállítói számlán jelenleg aktív kategóriák kijelöltként jelennek meg, ezért nem távolíthatók el.
    - Egyetlen kategóriakérésben több beszerzési kategória is kérelmezhető.

1. Válassza az **OK** lehetőséget a kérés piszkozatának létrehozásához.

    Az új kéréspiszkozat megjelenik a **Kategóriakérések** lapon.

1. Nyissa meg az új kéréspiszkozatot, hogy megtekintse és szükség szerint szerkessze.

    - A kérésben jelenleg szereplő kategóriák listájának megtekintéséhez, válassza a **Kért kategóriák** gyorslapon.
    - Az aktív kategóriák megtekintéséhez nyissa meg az oldal jobb oldalán található **Aktív kategóriák** gyorslapot.
    - Kategória hozzáadásához a kéréshez válassza a **Hozzáadás** lehetőséget az eszköztáron a **Kért kategóriák** gyorslapon.
    - Ha el szeretne távolítani egy kategóriát a kérésből, jelölje ki a kategóriát a **Kért kategóriák** gyorslapon, majd válassza az **Eltávolítás** lehetőséget az eszköztáron.
    - Egy dokumentum kérelemhez való csatoláshoz válassza a **Mellékletek** elemet a műveleti ablaktáblán. A csatolt dokumentumok elérhetővé válnak a jóváhagyók számára, amikor megtekintik a kategóriakérést.
    - Egy csatolt dokumentum kérelemből való eltávolításához válassza a **Mellékletek** elemet a műveleti ablaktáblán. Jelölje ki az eltávolítani kívánt dokumentumot, majd válassza a Művelet ablaktáblán a **Törlés** lehetőséget.

1. Ha készen áll a kérés elküldére, válassza a **Küldés** elemet a műveletpanelen. Ellenkező esetben csak zárja be a lapot, és hagyja ki az eljárás további lépéseit. Ezután később visszatérhet a kéréshez.
1. Olvassa el a megjelenő küldési utasításokat, majd válassza a **Küldés** lehetőséget.
1. A **Megjegyzés** mezőben adja meg a szükséges további adatokat. Majd a kérés befejezéséhez válassza a **Küldés** lehetőséget.

### <a name="edit-a-draft-or-recalled-request"></a>Piszkozat állapotú vagy visszahívott kérelem szerkesztése

A piszkozatok és a visszahívott kategóriakérések szerkesztéséhez hajtsa végre a következő lépéseket.

1. A **Szállítói információk** munkaterületén jelölje ki a **Kategóriakérések** csempét.
1. Válassza ki a megnyitni kívánt piszkozatot vagy visszahívott kérést.
1. Szükség szerint módosítsa a kérést, majd zárja be, vagy küldje el az előző eljárásban leírtaknak megfelelően.

### <a name="submit-a-draft-or-recalled-request"></a>Piszkozat állapotú vagy visszahívott kérelem elküldése

A piszkozatok és a visszahívott kategóriakérések elküldéséhez hajtsa végre a következő lépéseket.

1. A **Szállítói információk** munkaterületén jelölje ki a **Kategóriakérések** csempét.
1. Válassza ki az elküldeni kívánt vázlatot vagy visszahívott kérelmet.
1. A műveleti ablaktáblán válassza a **Küldés** lehetőséget.
1. Olvassa el a megjelenő küldési utasításokat, majd válassza a **Küldés** lehetőséget.
1. A **Megjegyzés** mezőben adja meg a szükséges további adatokat. Majd a kérés befejezéséhez válassza a **Küldés** lehetőséget.

    A kategóriakérés állapota a következő értékek egyikére módosul:

    - _Felülvizsgálatra vár_ – a kérelem a munkafolyamatban van.
    - _Jóváhagyásra vár_ – jóváhagyás szükséges.

### <a name="recall-a-submitted-request-that-hasnt-yet-been-approved"></a>Még nem jóváhagyott elküldött kérelem visszahívása

Az elküldött, de még jóvá nem hagyott kategóriakérelem visszahívásához kövesse ezeket a lépéseket.

1. A **Szállítói információk** munkaterületén jelölje ki a **Kategóriakérések** csempét.
1. Válassza ki a visszahívni kívánt függőben lévő kérést.
1. A Műveleti ablaktáblán kattintson a **Visszahívás** elemre.
1. A **Megjegyzés megadása** mezőben adja meg a szükséges további adatokat. Majd a kérés befejezéséhez válassza a **Küldés** lehetőséget.

    A kategóriakérés állapota _Visszavonva_ értékre módosul. A kérelem addig ebben az állapotában marad, amíg Ön nem törli vagy újra el nem küldi.

### <a name="delete-a-draft-or-recalled-request"></a>Piszkozat állapotú vagy visszahívott kérelem törlése

A piszkozatok és a visszahívott kategóriakérések törléséhez hajtsa végre a következő lépéseket.

1. A **Szállítói információk** munkaterületén jelölje ki a **Kategóriakérések** csempét.
1. Válassza ki a törölni kívánt vázlatot vagy visszahívott kérelmet.
1. A Műveletpanelen válassza ezután a **Törlés** elemet.
1. A törlés jóváhagyásához válassza az **Igen** lehetőséget.

### <a name="view-completed-requests"></a>Befejezett kérelmek megtekintése

A befejezett kérések megtekintéséhez nyissa meg a **Szállítói adatok** munkaterületet, és válassza a **Kategóriakérések** csempét. A már befejezett kategóriakérések a következő állapotokat fogják követni:

- _Jóváhagyva_ – A kérést jóváhagyták. Az újonnan hozzáadott kategóriák megtekintéséhez menjen vissza a **Szállítói információk** munkaterületre, nyissa meg a bal oldali ablakban a **További részletek** legördülő listát, majd válassza a **Kategóriák** elemet.
- _Elutasítva_ – A kérést elutasították. Szükség esetén új kategóriakérést hozhat létre.

## <a name="review-category-requests"></a>Kategóriakérések áttekintése

Ez a szakasz bemutatja a szállítók által benyújtott kategóriakérések jóváhagyását, elutasítását és delegálását, valamint a befejezett kérések megtekintését. Ezek a munkafolyamat-műveletek a teljes kategóriakérésre vonatkoznak.

### <a name="view-category-requests"></a>Kategóriakérések megtekintése

A következő lépések követésével tekintheti meg a kategóriakéréseket.

1. Lépjen a **Beszerzés és forráskezelés \> Szállítók \> Szállítói együttműködési kérések \> Kategóriakérések** elemhez.

    Megjelenik a **Kategóriakérések** lap. Az alapértelmezett oldalnézet a *Függő művelet* állapotú kategóriaigényléseket jeleníti meg.

1. Az összes kérelem megtekintéséhez jelölje be az *Összes* lehetőséget a **Kérelmek megjelenítése** mezőben.
1. Nyissa meg a kérést, hogy megtekintse és szükség szerint szerkessze.

    - A kérésben jelenleg szereplő kategóriák listájának megtekintéséhez, válassza a **Kért kategóriák** gyorslapon.
    - Az aktív kategóriák megtekintéséhez nyissa meg az oldal jobb oldalán található **Aktív kategóriák** gyorslapot.
    - Ha dokumentumokat nyújtott be, a műveleti ablaktábla **Mellékletek** (gemkapocs) gombja mutatja a csatolt dokumentumok számát. A csatolt dokumentumok megtekintéséhez kattintson a **Mellékletek** gombra. Ezután válassza ki a megtekinteni kívánt dokumentumot, és a megtekintéséhez kattintson a **Megnyitás** gombra.
    - Egy dokumentum kérelemhez való csatoláshoz válassza a **Mellékletek** elemet a műveleti ablaktáblán. A csatolt dokumentumok elérhetővé válnak a jóváhagyók számára, amikor megtekintik a kategóriakérést.
    - Egy csatolt dokumentum kérelemből való eltávolításához válassza a **Mellékletek** elemet a műveleti ablaktáblán. Jelölje ki az eltávolítani kívánt dokumentumot, majd válassza a Művelet ablaktáblán a **Törlés** lehetőséget.
    - Az munkafolyamat-előzmények megtekintéséhez válassza ki az **Munkafolyamat** elemet a Művelet ablaktáblán. A munkafolyamat-beállítások között válassza a **Továbbiak**, majd a **Munkafolyamat-előzmények** gombot. Megjelenik a **Munkafolyamat-előzmények** lap.

### <a name="approve-a-pending-category-request"></a>Függő kategóriakérelem jóváhagyása

A függő kategóriakérések jóváhagyásához hajtsa végre a következő lépéseket.

1. Lépjen a **Beszerzés és forráskezelés \> Szállítók \> Szállítói együttműködési kérések \> Kategóriakérések** elemhez.
1. Válassza ki a jóváhagyni kívánt függőben lévő kérést.
1. Tekintse át a kategóriakérést.
1. Nem kötelező: Az **Általános** gyorslap **Okkód** mezőjében válasszon ki egy okkódot. Ezután az **Okra vonatkozó megjegyzés** mezőbe írja be az okkóddal kapcsolatos megjegyzést.
1. A Műveleti ablaktáblán kattintson a **Munkafolyamat** elemre.
1. A munkafolyamat-beállítások között válassza a **Jóváhagyás** lehetőséget.
1. A **Megjegyzés** mezőben adja meg a szükséges további adatokat. Majd a kérés befejezéséhez válassza a **Jóváhagyás** lehetőséget.

    A kategóriakérés állapota _Jóváhagyva_ állapotúra változik, és a beszerzési kategóriákat hozzáadja a rendszer a szállítói számlához.

### <a name="reject-a-pending-category-request"></a>Függő kategóriakérelem elutasítása

A függő kategóriakérések elutasításához hajtsa végre a következő lépéseket.

1. Lépjen a **Beszerzés és forráskezelés \> Szállítók \> Szállítói együttműködési kérések \> Kategóriakérések** elemhez.
1. Válassza ki az elutasítani kívánt függőben lévő kérést.
1. Tekintse át a kategóriakérést.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. Az **Általános** gyorslap **Okkód** mezőjében válasszon ki egy okkódot. Ezután az **Okra vonatkozó megjegyzés** mezőbe írja be az okkóddal kapcsolatos megjegyzést.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A Műveleti ablaktáblán kattintson a **Munkafolyamat** elemre.
1. A munkafolyamat-beállítások között válassza a **Továbbiak**, majd az **Elutasítás** gombot.
1. A **Megjegyzés** mezőben adja meg a szükséges további adatokat. Majd a kérés befejezéséhez válassza az **Elutasítás** lehetőséget.

    A kategóriakérés állapota _Elutasítva_ értékre módosul. Ezen a ponton a szállító szükség esetén új kategóriakérést hozhat létre.

### <a name="delegate-a-pending-category-request"></a>Függő kategóriakérelem delegálása

Ha egy függő kategóriakérést át szeretne delegálni egy másik felhasználónak, kövesse ezeket a lépéseket.

1. Lépjen a **Beszerzés és forráskezelés \> Szállítók \> Szállítói együttműködési kérések \> Kategóriakérések** elemhez.
1. Válassza ki a jóváhagyni kívánt függőben lévő kérést.
1. A Műveleti ablaktáblán kattintson a **Munkafolyamat** elemre.
1. A munkafolyamat-beállítások között válassza a **Továbbiak**, majd a **Delegálás** gombot.
1. A **Felhasználó** mezőben válassza ki azt a felhasználót, akihez hozzárendeli az ellenőrzésre váró kategóriakérést.
1. A **Megjegyzés** mezőben adja meg a szükséges további adatokat.
1. A delegálás befejezéséhez válassza a **Delegálás** lehetőséget. A kiválasztott felhasználó most áttekintheti a kategóriakérést.

### <a name="view-procurement-categories-for-a-vendor"></a>Szállító beszerzési kategóriáinak megtekintése

Kövesse az alábbi lépéseket az adott szállító beszerzési kategóriáinak megtekintéséhez a kategóriakérés jóváhagyása után.

1. Ugrás a **Beszerzés és forrás \> Beszállítók \> Minden szállító** pontra.
1. Az **Összes szállító** oldalon válassza ki azt a szállítót, akinél meg szeretné tekinteni a beszerzési kategóriákat.
1. A Művelet panelen nyissa meg az **Általános** lapot, és a **Beállítások** csoportban válassza a **Kategóriák** elemet.

    Megjelenik a **Kategóriák** oldal. A **Beszerzés** gyorslap megjeleníti a kategóriakérésen keresztül hozzáadott beszerzési kategóriákat.

1. Szükség esetén a módosításokhoz a **Beszerzés** gyorslapot használhatja. Beállíthatja például a **Szállítói kategória állapota** mezőt _Előnyben részesített_ értékre.

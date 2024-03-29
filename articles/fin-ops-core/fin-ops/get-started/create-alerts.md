---
title: Figyelmeztetési szabályok létrehozása
description: Ez a cikk a figyelmeztetésekkel kapcsolatban tartalmaz tájékoztatást, és bemutatja a figyelmeztetési szabályok létrehozásához szükséges tudnivalókat.
author: RichdiMSFT
ms.date: 10/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: richdi
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: a420c5b2a036ac63a1a179f93462d152c3941fda
ms.sourcegitcommit: 873d66c03a51ecb7082e269f30f5f980ccd9307f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2022
ms.locfileid: "9124224"
---
# <a name="create-alert-rules"></a>Figyelmeztetési szabályok létrehozása

[!include [banner](../includes/banner.md)]

## <a name="getting-started"></a>Első lépések

Mielőtt figyelmeztetési szabályokat állítana be, döntse el, mikor vagy milyen helyzetben szeretne figyelmeztetést kapni. Ha tudja, mely eseményről szeretne értesítést kapni, keresse meg azt az oldalt, amelyen az eseményt előidéző adat megtalálható. Az esemény lehet egy elérkező dátum vagy egy bizonyos módosítás. Ezért meg kell találni a lapot, ahol a dátum meg van adva, vagy ahol megjelenik a módosuló mező vagy a létrehozott új rekord. Amint birtokában van ennek az adatnak, létrehozhatja az értesítési szabályt.

Egy figyelmeztetési szabály létrehozása esetén meg kell adni a feltételeket, amelyek teljesülése esetén figyelmeztetés jelenik meg. A feltételek tulajdonképpen nem mások, mint meghatározott körülmények között mindig bekövetkező események. Ha egy esemény bekövetkezik, a rendszer a megadott feltételek szerint megkezdi az ellenőrzést.

## <a name="ensure-the-alert-batch-jobs-are-running"></a>A figyelmeztetési kötegelt feladatok futásának biztosítása

Az adatmódosítási és a határidővel kapcsolatos figyelmeztetéseket tartalmazó kötegelt feladatok futtatása szükséges a figyelmeztetési feltételek feldolgozásához, valamint az értesítések küldéséhez. A kötegelt feladatok futtatásához nyissa meg a **Rendszeradminisztráció** > **Ismétlődő feladatok** > **Figyelmeztetések** pontot, és adjon hozzá egy új kötegelt feladatot a **Módosításon alapuló figyelmeztetésekhez** és/vagy a **Határidős figyelmeztetésekhez**. Ha hosszú és gyakran futtatott kötegelt feladatra van szükség, válassza az **Ismétlődést**, és állítsa **Nincs befejezési dátum** értékre, az **Ismétlődési minta** értéke legyen **Percek**, a **Szám** pedig **1**.

## <a name="events"></a>Események

A figyelmeztetési szabályt kiváltó esemény lehet egy elérkező dátum vagy egy bizonyos módosítás. Az események kiváltói meghatározhatók a **Figyelmeztetés feltétele** gyorslapján a **Figyelmeztetési szabály létrehozása** párbeszédpanelnek. Az adott mezőhöz rendelkezésre álló események a kiválasztott kiváltótól függően változnak.

Ha például egy figyelmeztetési szabályt állít be a **Kezdő dátum** mezőhöz, a határidős események megfelelőek. Emiatt az `is due in` eseménytípus elérhető a mező esetében. Azonban a **Költséghely** és hasonló mezőkhöz a határidős események nem megfelelők. Emiatt az `is due in` eseménytípus nem érhető el. Ehelyett a `has changed` eseménytípus érhető el.

## <a name="event-types"></a>Eseménytípusok

Három típusú esemény fordulhat elő:

- **Létrehozás típusú és törlés típusú események** – ezeket az események figyelmeztetést váltanak ki, ha a rekord létrehozása vagy törlése történik.
- **Frissítés típusú események** – Ezek az események figyelmeztetést generálnak, ha egy adott mezőben lévő adat megváltozik.
- **Határidő típusú események** – Ezek az események riasztást indítanak, amikor dátum érkezik.
    
A bekövetkező változásokat a felhasználó kezdeményezheti. Például egy felhasználó módosítja a beszerzési rendelés szállítási dátumát. Alternatívaként a változások folyamatok részeként is előfordulhatnak. Például az **Állapot** mező egy oldalon a rendszerben folyó különféle műveletek életciklusát tükrözi.

## <a name="conditions"></a>Feltételek

A **Figyelmeztetés időszaka** gyorslapján a **Riasztási szabály létrehozása** párbeszédpanelnek használhat feltételeket, amelyek megszabják, mikor kap riasztást az eseményekről.

Megadhatja például, hogy a rendszer figyelmeztesse, amikor a beszerzési rendelések állapota megváltozik, de csak akkor, ha az állapot megfelel bizonyos feltételeknek. Különösen az a fontos, hogy figyelmeztetést szeretne kapni, ha egy beszerzési rendelés állapota átvált **Bevételezett** állapotra. Ez az állapotmódosítás a figyelmeztetést kiváltó esemény.

Ezután el kell döntenie, mely beszerzési rendelésekről szeretne figyelmeztetést kapni. Például a következő lehetőségek egyikét választhatja: Ezek a beállítások adják meg a figyelmeztetési szabályhoz tartozó feltételeket.

- **Aktuális kiválasztott rekord** – megjelenik egy figyelmeztetés, ha egy adott beszerzési rendelés állapota átvált **Beérkezett** értékre.
- **Összes rekord** – Figyelmeztetés érkezik, amikor a beszerzési rendelés állapota az aktív oldalnézet egy elemére módosul. Használhatja a speciális szűrést, amely elérhető az oldalon, meghatározott rekordkészletre vonatkozó szabályok létrehozásához. Például létre tud hozni egy figyelmeztetést, amelyet egy adott vevőcsoportba tartozó vevők minden beszerzési rendelése kivált.
    
## <a name="expiry-of-rule"></a>Szabály lejárata

A **Figyelmeztetés vége** gyorslapján a **Riasztási szabály létrehozása** párbeszédpanelnek megadhatja, hogy meddig legyen aktív a figyelmeztetési szabály.

## <a name="alert-contents"></a>Figyelmeztetés tartalma

A **Figyelmeztetés módja** gyorslapján a **Figyelmeztetési szabály létrehozása** párbeszédpanelnek megadhatja a figyelmeztető üzenetek által használandó tárgy szövegét és üzenet szövegét.

## <a name="user-id"></a>Felhasználói azonosító

A **Figyelmeztetés módja** gyorslapján a **Figyelmeztetési szabály** létrehozása párbeszédpanelnek megadhatja, hogy melyik felhasználó kapja meg a figyelmeztető üzeneteket. A felhasználói azonosító alapértelmezés szerint be van jelölve. A figyelmeztetést kapó felhasználó módosításának lehetősége korlátozott a szervezeti rendszergazdákra.

## <a name="alerts-as-business-events"></a>Figyelmeztetések üzleti eseményekként

A figyelmeztetéseket az üzleti események keretrendszerén kívül is el lehet küldeni. Figyelmeztetés létrehozásakor állítsa az **Egész szervezet** beállítást **Nem** értékre, és a **Küldés külsőleg** beállítást **Igen** értékre. Miután aktiválta az üzleti eseményt kiváltó figyelmeztetést, Power Automate **elindíthat egy beépített folyamatot az Üzleti esemény bekövetkeztének bekövetkeztét követően a** pénzügyre és az műveleti csatlakoztatóra, **vagy explicit módon elküldheti az eseményt az üzleti események végpontjának az üzleti események katalógusán keresztül**.

## <a name="create-an-alert-rule"></a>Figyelmeztetési szabály létrehozása

0. A figyelmeztetési kötegelt feladatok futásának biztosítása (lásd fent).
1. Nyissa meg a figyelni szándékozott adatot tartalmazó oldalt.
2. A műveleti ablakban a **Beállítások** lapon a **Megosztás** csoportban válassza az **Figyelmeztetési szabály létrehozása** lehetőséget.
3. A **Figyelmeztetési szabály létrehozása** párbeszédablak **Mező** mezőjében válassza ki a megfigyelni kívánt mezőt.
4. Az **Esemény** mezőben jelölje ki az esemény típusát.
5. A **Figyelmeztetés időszaka** gyorslapon válassz a kívánt beállítást. Ha üzleti eseményként szeretné elküldeni a figyelmeztetést, állítsa az **Egész szervezet** beállítás értékét **Nem** értékre.
6. Ha azt szeretné, hogy egy figyelmeztetési szabály egy megadott dátumon érvényét veszítse, válasszon ki egy befejezési dátumot a **Figyelmeztetés vége** gyorslapon.
7. A **Figyelmeztetés módja** gyorslapon a **Tárgy** mezőben fogadja el az e-mail üzenet alapértelmezett tárgyát, vagy adjon meg egy új tárgyat. A szöveg a figyelmeztetés kezdeményezése esetén küldött e-mail üzenet tárgya lesz. Ha üzleti eseményként szeretné elküldeni a figyelmeztetést, akkor a **Külső küldést** az **igen** értékre állítja.
8. Az **Üzenet** mezőbe beírható egy üzenet, ez azonban nem kötelező. A szöveg a figyelmeztetés kezdeményezésekor kapott üzenet lesz
9. Kattintson az **OK** gombra a beállítások mentéséhez és a figyelmeztetési szabály létrehozásához.

## <a name="limitations-and-workarounds"></a>Korlátozások és megkerülő megoldások

### <a name="workaround-for-creating-alerts-for-the-secondary-data-sources-of-a-form"></a>Megkerülő megoldás az űrlap másodlagos adatforrásaihoz tartozó figyelmeztetések létrehozásához
Nem hozhatók létre figyelmeztetések az űrlapok egyes másodlagos adatforrásaihoz. Ha például figyelmeztetéseket hoz létre a vevői vagy a szállítói feladási profilok űrlapon, akkor csak a fejléc (CustLedger vagy VendLedger) mezői érhetők el, a dimenziószámlák pedig nem. Ehhez a korlátozáshoz a megkerülő megoldás az, ha a **SysTableBrowser** segítségével a táblát elsődleges adatforrásként nyitja meg. 
1. Nyissa meg a táblát a **SysTableBrowser** űrlapon.
    ```
        https://<EnvironmentURL>/?cmp=USMF&mi=SysTableBrowser&TableName=<TableName>
    ```
2. Hozzon létre figyelmeztetést a SysTableBrowser űrlapról.

### <a name="change-based-alerts-do-not-work-for-batch-status-changes"></a>A Módosításalapú figyelmeztetések funkció nem működik kötegelt állapotváltozások esetén
A Módosításalapú figyelmeztetések funkció nem működik kötegelt állapotváltozások esetén, mert a teljesítmény miatt ki van kapcsolva. Ehelyett be kell állítania a **Kötegelt figyelmeztetések** funkciót. A további tudnivalókat lásd a [Figyelmeztetések beállítása továbbfejlesztett kötegelt képernyők számára](../../dev-itpro/sysadmin/alerts.md#set-up-alerts-for-batch-enhanced-forms) pontban.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

---
title: Késztermékek ténylegesen elérhetővé tétele a naplókba való feladás előtt
description: Amikor egy legyártott cikket készként jelent, a rendszer további fizikai feldolgozásra elérhetőként regisztrálja, és egy vagy több naplót felad. Ez a témakör azt ismerteti, hogyan lehet elhalasztva a naplófeladásokat, lehetővé téve, hogy egy üzenet-várólistán lévő kötegelt feladat feldolgozta őket.
author: johanhoffmann
ms.date: 08/02/2022
ms.topic: article
ms.search.form: ProdParameters, JmgProdParameters, InventLocation, JmgMES3PMessageProcessorMessage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-08-02
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: ee767a5d7c3dca2681861802ae42d7a07217c54d
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689340"
---
# <a name="make-finished-goods-physically-available-before-posting-to-journals"></a>Késztermékek ténylegesen elérhetővé tétele a naplókba való feladás előtt

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Amikor egy dolgozó készként jelenti a legyártott cikket, a rendszer azt további fizikai feldolgozásra (például szállításra vagy beszállításra) regisztrálja. A folyamat során egy vagy több naplót is felad a rendszer (például a készként jelentés naplóját, a kitárolási lista naplóját és az útvonalkártya-naplót). Ha az összes feladás feldolgozása előtt a cikkeket fizikailag elérhetővé szeretné tenni, be lehet állítani, hogy a rendszer halasztja a naplófeladásokat. A halasztott feladásokat ezután egy kötegelt feladat kezeli, amely a feladásokat a rendszererőforrások által megengedettként fogja feldolgozni.

A következő ábra bemutatja, hogy hogyan hívja meg a rendszer a feladási naplók folyamatait halasztott feladásokkal és azok nélkül.

![A készként jelentési folyamat halasztott naplófeladással és anélkül.](media/deferred-posting-flowchart.png "A készként jelentési folyamat halasztott naplófeladással és anélkül")

## <a name="turn-on-deferred-journal-posting-for-your-system"></a>Halasztott naplófeladás bekapcsolva a rendszerben

A halasztott naplófeladás csak akkor használható, ha be van kapcsolva a rendszerben. A rendszergazdák a Szolgáltatáskezelés [munkaterületen](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) ellenőrizhetik és bekapcsolják a funkció állapotát. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Gyártásvezérlés*
- **Funkció neve:** *(Előnézet) A késztermékek fizikai elérhetővé teése a naplókba történő feladás előtt*

## <a name="set-up-journal-posting-options-for-reporting-as-finished"></a>Adja meg a naplófeladási beállításokat a készként történő jelentéshez.

A dolgozók a következő ügyfelek bármelyikével készként jelenthetik a cikkeket:

- Webes ügyfél
- Raktárkezelés mobilalkalmazás
- Termelési emelet végrehajtási felülete

A webes ügyfél ugyanazt a feladási módszert használja, mint a Raktárkezelés mobilalkalmazás. A termelési emelet végrehajtási felületének feladási módját azonban külön kell konfigurálni.

### <a name="set-journal-posting-options-for-the-web-client-and-the-warehouse-management-mobile-app"></a>Adja meg a webalkalmazás és a Raktárkezelés mobilalkalmazás naplófeladási beállításait.

A mobilalkalmazásban a dolgozók készként jelentik a cikkeket úgy, hogy megnyitnak egy mobileszköz menüpontot, ahol **a** *·* *munka-létrehozási folyamat értéke Jelentés készként vagy Készként jelentve és berakodva.* A webalkalmazásban a **dolgozók** készként jelentik a cikkeket a Minden termelési rendelés listaoldalról **vagy a Termelési rendelés (részletek) lapról**. Az alapértelmezett módszert az egész vállalatra kiterjedően konfigurálhatja, és szükség esetén raktárspecifikus felülbírálásokat is be lehet állítani.

A következő eljárás szerint konfigurálhatja az egész vállalatra kiterjedő alapértelmezett feladási módszert a cikkek webes ügyfélből vagy a Raktárkezelés mobilalkalmazásból történő készként jelentéséhez.

1. Ugrás a Gyártásvezérlés **beállítása \> a \> gyártásvezérlés paramétereihez**
1. A Naplók **lap Készként jelentve** **·** **napló szakaszának Feladási mód mezőjét a következő értékek egyikére állíthatja:**

    - *Azonnali* – amikor a cikk készként van jelentve, a rendszer teljesen feldolgoz minden kapcsolódó naplófeladást, mielőtt a készterméket fizikailag elérhetőként megjelöli.
    - *Elhalasztva* – a cikk készként jelentésekkor a rendszer az elkészült cikket fizikailag elérhetőként megjelöli, és a naplófeladásokat hozzáadja az üzenet-várólistához. A rendszer nem várakozik addig, amíg a feladások teljesen fel vannak feldolgozva, mielőtt a készterméket fizikailag elérhetőként megjelöli.

A következő eljárás szerint konfigurálhatja a raktárspecifikus **felülbírálásokat a Gyártásvezérlési paraméterek lapon beállított alapértelmezett feladási módszerhez**.

1. Ugrás a Raktárkezelés **beállítása \> – \> Készletlebontás – \> Raktárak beállításához**
1. Válassza ki a beállítani kívánt raktárt.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. A Termelési **rendelések** szakasz Raktár gyorstára **a** **Következő** értékek egyikére állítsa a Feladási mód mezőt:

    - *Öröklés* – a kiválasztott raktár a Gyártásvezérlési **paraméterek lapon található beállítást örökli**.
    - *Azonnali* – amikor a cikk készként van jelentve, a rendszer teljesen feldolgoz minden kapcsolódó naplófeladást, mielőtt a készterméket fizikailag elérhetőként megjelöli.
    - *Elhalasztva* – a cikk készként jelentésekkor a rendszer az elkészült cikket fizikailag elérhetőként megjelöli, és a naplófeladásokat hozzáadja az üzenet-várólistához. A rendszer nem várakozik addig, amíg a feladások teljesen fel vannak feldolgozva, mielőtt a készterméket fizikailag elérhetőként megjelöli.

### <a name="set-journal-posting-options-for-the-production-floor-execution-interface"></a>Adja meg a termelési emelet végrehajtási felületének naplófeladási beállításait.

A következő eljárás szerint konfigurálhatja azt a feladási módszert, amely akkor használatos, amikor a cikkeket készként jelentik a termelési emelet végrehajtási felületéről.

1. Ugrás a Gyártásvezérlés **beállítása \> Gyártásvégrehajtás \> termelési \> rendelés alapértelmezéseihez**
1. A Készként **jelentve** lap **Készként** **jelentés** naplószakaszában állítsa a Feladási mód mezőt a következő értékek egyikére:

    - *Azonnali* – amikor a cikk készként van jelentve, a rendszer teljesen feldolgoz minden kapcsolódó naplófeladást, mielőtt a készterméket fizikailag elérhetőként megjelöli.
    - *Elhalasztva* – a cikk készként jelentésekkor a rendszer az elkészült cikket fizikailag elérhetőként megjelöli, és a naplófeladásokat hozzáadja az üzenet-várólistához. A rendszer nem várakozik addig, amíg a feladások teljesen fel vannak feldolgozva, mielőtt a készterméket fizikailag elérhetőként megjelöli.

## <a name="schedule-the-message-processor-batch-job-to-process-deferred-postings"></a>Ütemezi az üzenetfeldolgozó kötegelt feladatot a halasztott feladások feldolgozására

Az üzenetfeldolgozó kötegelt feladata felelős a naplófeladások feldolgozásáért, miután azok várólistára került. A naplófeladások feldolgozásának biztosítása érdekében be kell állítania ezt a feladatot, hogy rendszeres időközönként fusson. A következő eljárás szerint állíthatja be a szükséges kötegelt feladatot.

1. Ugrás a Rendszerfelügyelet **üzenetfeldolgozó \> üzenetfeldolgozóhoz \>**
1. A Paraméterek **gyors** területen állítsa **az Üzenetsor** mezőt Termelés *beállításra*.
1. A háttérben **futó gyorslapon** állítsa **a Kötegelt feldolgozás** beállítást Igen *beállításra*. Ezután állítson be ismétlődő ütemezést, és szükség szerint konfigurálja az egyéb beállításokat. A beállítások pont úgy működnek, mint a [Microsoft egyéb háttér-feladattípusokkal](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md)Dynamics 365 Supply Chain Management.

## <a name="track-the-progress-of-your-deferred-postings"></a>A halasztott feladások folyamatának követése

A halasztott *naplófeladások* *várólistára kerülnek üzenetfeldolgozó üzenetként, amely megvárja, amíg az üzenet feldolgozója feldolgozja őket*. Az üzenetfeldolgozót úgy kell beállítani, hogy ütemezett kötegelt feladatként fusson. Az üzenetfeldolgozó által **feldolgozott vagy feldolgozott halasztott feladási üzenetek megtekintéséhez kattintson a Termelésvezérlés \> termelési rendelések \> halasztott termelési rendelésének feladására**.

### <a name="message-grid-columns-and-filters"></a>Üzenetrács oszlopai és szűrői

A Halasztott termelési rendelés **feladása** lap tetején lévő mezők segítségével lehet megtalálni a keresett üzeneteket.

Az alábbi szűrők állnak rendelkezésre:

- **Üzenettípus** – a rácsban megjelenő üzenetek típusának meghatározása.
- **Üzenet állapota** – a rácsban megjelenő üzenetek állapotának meghatározása. A következő államok léteznek:

    - *Feldolgozási sorban* – az üzenetfeldolgozó készen áll az üzenet feldolgozására.
    - *Feldolgozva* – az üzenetfeldolgozó sikeresen elvégezte az üzenet feldolgozását.
    - *Megszakítva* – az üzenet feldolgozása nem sikerült a végső kísérlet során, ezt követően a felhasználó megszakította.
    - *Sikertelen* – az üzenet feldolgozása nem sikerült a legutóbbi kísérlet során. A rendszer háromszor próbálja meg újra a sikertelen üzeneteket. Ezt követően feladja, és az üzenetet Sikertelen állapotban *hagyja*. Ne feledje, hogy a három próbálkozás utánig nem szakíthat meg és nem szerkeszthet üzenetet manuálisan.

- **Üzenet tartalma** – Ezzel a szűrővel az üzenet tartalmának teljes szöveges keresését lehet végrehajtani. (Az üzenet tartalma nem jelenik meg a rácsban.) A szűrő a leg speciális szimbólumokat (például kötőjeleket) kezeli szóköz karakterként, és az összes szóköz karaktert logikai VAGY operátorként kezeli. Ha például egy USMF-123456-os`journalid` értékkel megegyező értéket keres, a rendszer minden olyan üzenetet megtalál, *amely* az "USMF" vagy az "123456" értéket tartalmazza. Ebben az esetben valószínűleg túl hosszú lesz az eredmények listája. Ezért jobb, ha *csak* a megadott 123456, mert így konkrétabb eredmények is fognak kapni.

A listát úgy is rendezheti és szűrheti, hogy kijelöli valamelyik oszlopfejlécet, és feltételeket ad meg a legördülő párbeszédpanelen.

### <a name="view-the-message-log-message-content-and-details"></a>Az üzenetnaplónak, az üzenet tartalmának és részleteinek megtekintése

Az üzenetek részletes adatait úgy találhatja meg, hogy kijelöli azt **a** **rácson**, majd az üzenetrácsOn belül a Napló vagy nyers tartalom lapot, ahol minden feldolgozási esemény megjelenik.

A **Napló** lap eszköztára a következő gombokat tartalmazza:

- **Napló** – ezzel a gombbal megmutatja a feldolgozási eredményeket. Ez a gomb különösen akkor hasznos, ha **az** üzenetek feldolgozási eredményének *értéke* Sikertelen, és szeretné tudni a feldolgozási hiba okát.
- **Csomag** – Több üzenetfeldolgozási művelet futhat ugyanazon kötegfolyamat részeként. A részletes adatok megtekintéséhez kattintson erre a gombra. Például láthatja, hogy vannak-e függőségek, amelyek bizonyos üzenetekhez meghatározott feldolgozási rendelést igényelnek.

### <a name="manually-process-or-cancel-a-message"></a>Üzenet manuális feldolgozása vagy visszavonása

Az üzenetek az aktuális állapottól függően saját kezűleg feldolgozhatók és visszavonhatóak. Jelölje ki az üzenetet a rácsban, majd válassza a **Feldolgozás** vagy **a Mégse** lehetőséget a munkaablakban.

### <a name="set-up-business-events-to-deliver-alerts-for-failed-processing-results"></a>Állítsa be az üzleti eseményeket, hogy sikertelen feldolgozási eredmények esetén riasztásokat küldjenek

Be lehet állítani olyan [üzleti eseményeket](../../fin-ops-core/dev-itpro/business-events/home-page.md), amelyek figyelmeztetik a feldolgozás sikertelen eredményeire. Menjen a Rendszerfelügyelet **beállítása \>\> üzleti események üzleti \>** eseménykatalógusához, és aktiválja azt az üzleti eseményt, amely az *Üzenetfeldolgozó üzenet feldolgozva* nevű.

Az aktiválási folyamat részeként a program megkérdezi, hogy az esemény egy jogi személyre vonatkozik-e, vagy minden jogi személyre vonatkozik. A program arra is kéri, hogy adjon meg egy végponti **névértéket**. Először ezt az értéket kell meghatározni.

> [!NOTE]
> Ha egy **üzleti** *Microsoft Power Automate* *esemény bekövetkeztének esetére a rendszer a HTTPS* helyett be van állítva, **akkor** a végpont nevének értéke automatikusan létrejön az Ellátásilánc-kezelésben a *Microsoft Power Automate* beállítás alapján.

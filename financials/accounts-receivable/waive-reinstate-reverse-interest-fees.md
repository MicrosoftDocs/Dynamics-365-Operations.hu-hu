---
title: "Kamatok, díjak elengedése, visszaállítása vagy sztornírozása"
description: "Ennek a cikknek a célja, hogy elmagyarázza a kamatok és díjak elengedésének, visszaállításának és fordított áfázásának folyamatát."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 59461
ms.assetid: 25ec29f3-e3ea-4abb-bf6b-f6240873b315
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: e25a7657c2b859ffd57313ed7eb8da6583e7130d
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="waive-reinstate-or-reverse-interest-fees"></a>Kamatok, díjak elengedése, visszaállítása vagy sztornírozása

[!include[banner](../includes/banner.md)]


Ennek a cikknek a célja, hogy elmagyarázza a kamatok és díjak elengedésének, visszaállításának és fordított áfázásának folyamatát.

Az **Összes vevő** listalap **Gyűjtés** lapján levő gombok használhatók a díjak elengedésére, sztornírozására vagy visszaállítására:

-   Az elengedett díjak alól mentesíti a másik felet. Akkor engedhet el például egy díjat, ha a vevő vitatja a díjat, és Ön meg szeretné tartani a jó üzleti kapcsolatot a vevővel.
-   A visszaállított díjak ismét esedékessé válnak. Korábban elengedett díjakat állíthat vissza. Lehetséges, hogy szükséges az elengedett költségek felszámítása, ha úgy dönt, hogy nem engedi el azokat.
-   A sztornírozott díjak el lesznek távolítva a vevő számlájáról és többé nem esedékesek. Például akkor sztornírozhat díjakat, ha nem megfelelő kamatláb alapján számította ki a vevő tartozásának összegét. Külön folyamatot használhat a kamat újraszámítására és az új díjakat tartalmazó kamatlevél létrehozására a vevő számára.

Ezek a műveletek megváltoztatják a kamatlevelet. A kamatlevél egy üzleti dokumentum, amely tájékoztatja a vevőket, ha kamatot vagy díjakat számítottak fel a számlájukra. Ha elenged vagy sztorníroz kamatot vagy díjakat, a rendszer automatikusan létrehoz egy jóváírást vagy módosító számlát a költségek kiegyenlítéséhez. Ha visszaállít korábban elengedett díjakat, a rendszer automatikusan létrehoz egy számlát egy tartozik összeggel a vevő tartozásának visszaállításához. Az alábbi táblázat ismerteti az egyes műveletek eredményeit.

| Művelet                                                                                                                                                                                                            | Eredmény az ügyfél szemszögéből                                                                                             | Feldolgozás                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Elengedhet teljes kamatleveleket a rajtuk szereplő összes kamattal és díjakkal együtt. –vagy– Kijelölhet és elengedhet kamatlevelek részét képező díjakat vagy kamattranzakciókat.                                        | A költségek már nem esedékesek.                                                                                           | A program létrehoz egy jóváírást vagy módosító számlát a vevő részére. A jóváírás felhasználásával automatikusan nem egyenlíti ki a kiválasztott kamatlevelet, kamattranzakciót vagy díjakat. A kiegyenlített összeg megegyezik a díjak teljes összegével, mínusz a vevő által korábban teljesített kifizetések, és mínusz a korábban elengedett vagy sztornírozott összegek. Ha a jóváírás összege meghaladja a vevő tartozását, a jóváírás szállítói számlává konvertálható. Ezután visszatérítést adhat majd a vevőnek.                                                       |
| Visszaállíthat teljes kamatleveleket a rajtuk szereplő összes kamattal és díjakkal együtt. –vagy– Kijelölhet és visszaállíthat kamatlevelek részét képező díjakat vagy kamattranzakciókat.                                | Az elengedett összeg újra esedékes.                                                                                     | A rendszer létrehoz egy számlát egy tartozik összeggel, és automatikusan kiegyenlíti ezzel az összeggel a korábban elengedett díjakat. A tényleges kamatlevelek nem lesznek visszaállítva. Ehelyett a program létrehoz egy számlát, amelyen a vevőtől esedékes összeg látható. Az elengedett kamatlevelek kiegyenlítéséhez létrehozott jóváírások vagy módosító számlák továbbra is létezhetnek, ha nem használták fel azokat a kamatlevelek kiegyenlítésére. Ilyen esetben a program visszavonja a kiegyenlítetlen jóváírásokat. A kiegyenlítetlen jóváírások elszámolása általában automatikusan megtörténik a kamatlevelek elengedésekor. Azonban létezhet kiegyenlítetlen jóváírás, ha egy vevő kifizetett egy kamatlevelet annak ellenére, hogy vitatta a költségeket. |
| Teljes kamatlevelek sztornírozása. –vagy– Sztornírozhat a kamatlevelek részét képező kijelölt kamattranzakciókat. **Megjegyzés:** Nem vonhat vissza díjat. Ugyanakkor visszavonhatja a teljes kamatlevelet, amelyik tartalmazza a díjat. | A díjak már nem esedékesek a vevőtől. A díjak azonban újból esedékessé válnak, ha újraszámítja a kamatot. | A folyamat ugyanaz, mint a kamatlevelek vagy kijelölt kamattranzakciók elengedésének folyamata. A program létrehoz egy jóváírást vagy módosító számlát a vevő részére. Ennek a jóváírásnak a felhasználásával automatikusan kiegyenlíti a kamatlevelet. Külön folyamatot használhat a kamat újraszámítására és új kamatlevél létrehozására.                                                                                                                                                                                                                                                                                                                                                                                              |

> [!NOTE] 
> Külön folyamatokat is használhat behajthatatlan adósságok leírására. Ez a folyamat megjelöli az összes kiegyenlítésre szánt vevői tranzakciót, ahelyett, hogy csak a kamatlevelekben szereplő díjakat engedné el.

## <a name="adjust-interest-for-invoices"></a>Kamat beállítása számlákhoz
A kamatlevelek kiigazítása mellett az alábbi eljárások használatával eltávolíthatja a számlákon szereplő kamatköltségeket is. Mindkét eljárás kiigazítást is végrehajt a kapcsolódó kamatleveleken.

### <a name="correct-an-invoice-that-has-associated-interest"></a>Számla javítása a kapcsolódó kamattal együtt

Kijavíthat egy feladott számlát, amely egy kamatlevélen szerepel. Ez az eljárás átmásolja az adatokat a létező számláról egy új számlára, hogy elvégezhesse csak a kívánt javításokat. A program visszavonja a számlát, és létrehoz egy új számlát. A tranzakciót terhelő kamat is sztornírozva lesz a kamatlevélen, ha feladták a kamatlevet. 

Elvégezheti a korrekciót a **Számla javítása** gombbal a szabadszöveges számla Műveleti ablakában. Ez a gomb csak akkor használható, ha be van állítva a **Szabadszöveges számla javítása** konfigurációs kulcs.

### <a name="reverse-a-customer-transaction-that-has-associated-interest"></a>Vevői tranzakció sztornírozása a kapcsolódó kamattal együtt

Sztornírozhat egy vevői tranzakciót egy számlán, ha a számla helytelenül lett létrehozva. Ha a sztornírozott vevői tranzakcióhoz kamat tartozik egy kamatlevélen, és a kamatlevelet feladták, a tranzakcióhoz tartozó kamat is sztornírozva lesz a kamatlevélen. Ha kamatlevél vissza lesz vonva, ha még nem adták fel. 

Visszavonhat vevő tranzakciókat a **Visszavonás**gombbal a **Vevői tranzakciók** oldalon.

## <a name="waive-or-reinstate-interest-notes"></a>Kamatlevelek elengedése vagy visszaállítása
Elengedheti vagy visszaállíthatja a kijelölt kamatleveleken szereplő összes költséget. Költségek elengedésekor az elengedni kívánt teljes összeg nem haladhatja meg a beállított összeghatárokat. Csak olyan kamatlevél állítható vissza, amelyet korábban elengedtek. 

Elengedheti vagy visszaállíthatja a kamatleveleket a **Kamatlevél** gomb segítségével a **Vevő** oldal **Begyűjtés** lapján.

## <a name="waive-or-reinstate-interest-transactions"></a>Kamattranzakciók elengedése vagy visszaállítása
Elengedhet vagy visszaállíthat egy kamatlevélen szereplő adott kamattranzakciókat, ahelyett, hogy a kamatlevélen szereplő összes díjat módosítaná. Költségek elengedésekor az elengedni kívánt teljes összeg nem haladhatja meg a beállított összeghatárokat. Csak olyan kamattranzakció állítható vissza, amelyet korábban elengedtek. 

Elengedheti vagy visszaállíthatja a kamatleveleket a **Tranzakciókamat** gomb segítségével a **Vevő** oldal **Begyűjtés** lapján.

## <a name="waive-or-reinstate-fees"></a>Díjak elengedése vagy visszaállítása
Elengedhet vagy visszaállíthat egy kamatlevélen szereplő adott díjakat, ahelyett, hogy a kamatlevélen szereplő összes díjat módosítaná. Költségek elengedésekor az elengedni kívánt teljes összeg nem haladhatja meg a beállított összeghatárokat. Csak olyan díj állítható vissza, amelyet korábban elengedtek. 

Elengedheti vagy visszaállíthatja a kamatleveleket a **Díj** gomb segítségével a **Vevő** oldal **Begyűjtés** lapján.

## <a name="reverse-interest-notes"></a>Kamatlevelek sztornírozása
Sztornírozhatja a kijelölt kamatleveleken szereplő összes költséget. A sztornírozott díjak el lesznek távolítva a vevő számlájáról és többé nem esedékesek. Egy kamatlevél sztornírozása után újraszámíthatja a kamatot, és létrehozhat egy új kamatlevelet. 

Sztornírozhat a kamatleveleket a **Kamatlevél**gomb segítségével a **Vevő** oldal **Begyűjtés** lapján.

## <a name="reverse-interest-transactions"></a>Kamattranzakciók sztornírozása
Sztornírozhatja az összes kiválasztott kamattranzakciót. A sztornírozott díjak el lesznek távolítva a vevő számlájáról és többé nem esedékesek. A tranzakciók sztornírozása után újraszámíthatja a kamatot, és létrehozhat egy új kamatlevelet.

Sztornírozhat kamattranzakciókat a **Kamattranzakció** gomb segítségével a **Vevő** oldal **Begyűjtés** lapján.

## <a name="view-the-history-of-adjustments-for-charges-that-were-waived-reinstated-or-reversed"></a>Elengedett, visszaállított vagy sztornírozott költségek módosítási előzményeinek megtekintése
Megtekintheti a kamatleveleken végzett módosítások részletes előzményeit, például a módosítást megadó felhasználó nevét, a módosítás típusát, az összeget, valamint a módosítás megadásának dátumát. Például célszerű lehet megtekinteni egy kamatlevélhez korábban megadott módosításokat, mielőtt új kamatlevelet hoz létre. 

Sztornírozhat kamattranzakciókat az **Előzmények**gomb segítségével a **Vevő** oldal **Begyűjtés** lapján.





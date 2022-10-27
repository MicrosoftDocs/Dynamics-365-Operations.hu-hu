---
title: Utalványok
description: Ez a cikk az utalványokkal kapcsolatos funkciókról nyújt áttekintést a következő témakörben:Microsoft Dynamics 365 Commerce
author: boycez
ms.date: 09/06/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-06-30
ms.openlocfilehash: 20427a04a552ddec013daa6576ec64ab7046e95f
ms.sourcegitcommit: 87e75aa6af2c3280316d7d73eafa14a52353a5e4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/21/2022
ms.locfileid: "9709759"
---
# <a name="coupons"></a>Utalványok

[!include [banner](../includes/banner.md)]

Ez a cikk az utalványokkal kapcsolatos funkciókról nyújt áttekintést a következő témakörben:Microsoft Dynamics 365 Commerce

Az utalványok olyan kódok és vonalkódok, amelyek segítségével engedményeket adnak hozzá a tranzakciókhoz. A kiskereskedők utalványokat osztnak fel a potenciális vagy meglévő vevők részére, hogy javíthatják a márka felismerését, javíthatják a konverziót, megtarthatják a vevőbázisukat, növelhetik az értékesítést, és végső soron növelhetik a bevételt. Az utalványok az egyik legnépszerűbb marketingeszközsé váltak, és új normaként váltnak az e-commerce értékesítésben.

A Dynamics 365 Commerce, az utalványok engedményekhez kapcsolódnak, és az engedmények felül további ellenőrzésnek számítanak. Minden utalvány egy engedményhez kapcsolódik, és a kapcsolódó engedmény meghatározza az utalvány érvényes termékhalmazát.

Az engedményhez társított árcsoportok meghatározzák azokat a feltételeket, amelyekre az utalványok felhasználhatók. Ilyen feltételek például a vevőcsoportok és az értékesítési csatornák. Az utalványok a használati **korlátozást** **és** a Vevő által megkövetelt tulajdonságokat is biztosítják, amelyek tetszőleges használati korlátozások beállítására használhatók.

Minden utalványnak több utalványkódja és vonalkódja is lehet, és mindegyik kódnak saját dátumtartománya és állapota lehet. Ha egy kód állapota **Inaktív**, akkor a kód nem használható egyetlen csatornában sem.

## <a name="set-up-a-coupon"></a>Utalvány beállítása

Utalvány beállítása előtt be kell állítania az utalvány vonalkódját és két utalványszám-sorozatot.

Az alábbi lépésekkel állíthat be utalványokat a Commerce Headquarters számára.

1. Ugrás a **Kiskereskedelmi és commerce készletkezelés \> vonalkód \>- és címkemaszk-karakterekhez \>**
1. Válassza **a Hozzáadás** lehetőséget az Utalványkódtípus maszk **karakterének létrehozásához**. A Karakter **mezőben** bármilyen nem használt karaktert kiválaszthat.
1. Ugrás a **Kiskereskedelmi és commerce készletkezelés \> vonalkódok \> és \> címkék vonalkódmaszk-beállításához**.
1. Az **Új beállítással** létrehozhatja az Utalvány típusú **vonalkódmaszkot**.
1. Ugrás a **Kiskereskedelmi és commerce készletkezelés \> vonalkódok \> és címkék \> vonalkód-beállításához**.
1. Az **Új** beállítás kiválasztásával olyan vonalkódot hozhat létre, amely a létrehozott vonalkódmaszkot használja.
1. Ugrás a Szervezet felügyelete **számsorozatok \> számára**.
1. Hozzon létre két számsorozatot:

    1. Egy sorozat az utalványszám-hivatkozáshoz **·** Ez a sorozat határozza meg az utalvány egyedi azonosítóját.
    1. Egy sorozat az utalványkód-azonosító **hivatkozásához** Ez a sorrend határozza meg az utalványkódok egyedi azonosítóját.

    Mindkét számsorozat esetén a **Hatókör** mező **Vállalat** értékre kell állítani. A legtöbb esetben mindkét sorszámot automatikusan kell generálni.

1. Ugrás a **Commerce rendszer ár- \> és engedményparamétereihez \>**
1. Állítsa az **Utalvány vonalkódmaszk mezőjét** a korábban létrehozott vonalkódra.
1. Ugrás a **Commerce rendszer számsorozataihoz \>**
1. Az utalványszám- és utalványkód-azonosító **hivatkozásokhoz** korábban létrehozott számsorozatok **kiválasztása**.

Az utalványok beállításához az engedményt és az utalványt külön kell létrehozni, **majd** az engedményt az utalvány-konfiguráció Engedmény mezőjében ki kell választani. Miután egy utalványt csatoltak egy engedményhez, **a** csatolt engedmény Állapot, **·** **Érvényességi** dátum és Lejárati dátum mezői írásra válnak, mivel az értékeket az utalvány állapota és érvényességi időszaka határozza meg. Ha egy utalvány állapota **Aktív**, **a csatolt engedmény állapota automatikusan Engedélyezve állapotúra módosul**. Hasonlóképpen, ha **egy** utalvány állapota Inaktívra van állítva, **a csatolt engedmény állapota automatikusan Letiltott állapotra frissül**.

## <a name="use-a-coupon"></a>Utalvány használata

Utalványnak a Commerce Point of Sale (POS) értékesítési tranzakcióhoz való hozzáadásához utalványkódot vagy utalvány vonalkódját használhatja. Utalványkód alkalmazásához válassza az **Utalványkód** hozzáadása műveletet, majd adja meg a kódot. Utalvány vonalkódja csak akkor használható, ha beolvasással beolvassa a vonalkódot egy **beolvasási eszközzel, vagy beírhatja azt a Tranzakció képernyőn látható numerikus billentyűzet** segítségével.

A kiskereskedők időnként azt szeretnék, ha a pénztárosok fix összegű engedményeket adhatnak a vevőknek, ha ezt meg szeretné tenni, annak érdekében, hogy a vásárlást megszatassa, vagy termékhibák miatt, de nem szeretnék kinyomtatni az utalványkódokat, és elosztani azokat a pénztárosok között. Ebben az esetben az **utalvány** utalványkód nélkül beállítását Igen beállításra **állíthatja**. A POS pénztárosok **ezután** **a** kód manuális megadása nélkül használhatja az Utalvány alkalmazása funkciót az Elérhető engedmények megtekintése műveletben egy utalvány hozzáadásához a tranzakcióhoz. Ha egy utalványhoz több utalványkód is van, a rendszer automatikusan kiválasztja az első aktív kódot, és azt alkalmazza a tranzakcióra.

Ha egy hívásközponti értékesítési rendeléshez szeretne utalványt hozzáadni, akkor **egy** **hívásközponti** felhasználónak ki kell választania az Utalványok lehetőséget az értékesítési rendelés munkaablakának Kezelése lapján.

Ha e-kereskedelmi rendeléshez szeretne hozzáadni egy utalványt, **a** vásárló a bevásárlókocsi promóciós kód mezőjében adhatja meg az utalványkódot.

Miután az utalványt hozzáadta egy értékesítési rendeléshez, az árképzési motor azonnal újraszámítást indít a teljes rendelésre, függetlenül attól, hogy engedélyezve van-e a késleltetett számítás.

> [!NOTE]
> A Commerce rendszer 10.0.30-as és korábbi verzióiban, miután a hívásközponti felhasználók hozzáadtak egy utalványt egy hívásközponti értékesítési rendeléshez, **·** **·** **az** utalványhoz társított engedmény alkalmazásához be kell választaniuk az Újraszámítás lehetőséget a munkaablak Értékesítési lapjának Számítás csoportjában.

## <a name="coupon-usage-limit"></a>Utalványhasználat korlátja

Az utalványok korlátozottan használhatók. A használati korlát vevőnként, csatornánként vagy globálisan határozható meg. A használati korlátot utalványkódonként érvényesíti a rendszer egy utalványon. Egy egyszer használatos utalványt például, amely két utalványkóddal rendelkezik, kétszer használható minden egyes utalványkódhoz.

Az utalványok az értékesítési csatornákon keresztül is használhatók. Hívásközponti célokra azonban csak **akkor** lehet korlátozottan használható utalványokat alkalmazni, ha engedélyezve van a hívásközponti csatorna Rendelésteljesítés engedélyezése beállítása. Ha a **Rendelés befejezésének** engedélyezése beállítás nincs engedélyezve, csak nem korlátozottan használható utalványok alkalmazhatók.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

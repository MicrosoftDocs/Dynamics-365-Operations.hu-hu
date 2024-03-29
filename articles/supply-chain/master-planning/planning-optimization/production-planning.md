---
title: Termeléstervezés
description: Ez a cikk a termelés tervezését írja le, és bemutatja, hogyan lehet módosítani a tervezett termelési rendeléseket a Tervezés optimalizálása segítségével.
author: t-benebo
ms.date: 08/09/2022
ms.topic: article
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 43da249637c44b3f56e8b5e210a0e44d9ac6cb9d
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740549"
---
# <a name="production-planning"></a>Termeléstervezés

[!include [banner](../../includes/banner.md)]

Az alábbi videofelvétel rövid bevezetőt nyújt a cikk néhány alapfogalma bevezetőjében: [Dynamics 365 Supply Chain Management A tervezés optimalizálási fejlesztések](https://youtu.be/u1pcmZuZBTw).

## <a name="turn-this-feature-on-or-off-for-your-system"></a>A funkció be- és kikapcsolása a rendszeren

A funkció használatához be kell kapcsolva lennie a rendszeren. Az Ellátásilánc-kezelés 10.0.29-es verziója szerint a funkció kötelező, és nem lehet kikapcsolni. Ha 10.0.29-esnél régebbi verziót futtat, *·*[akkor](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) a rendszergazdák a Funkciókezelés munkaterület tervezett termelési rendelései alapján kapcsolhatják be és kapcsolhat ki a funkciót.

## <a name="planned-production-orders"></a>Terv. term. rendelések

Amikor az alaptervezés tervezett rendeléseket hoz létre a követelmények kielégítése érdekében, a rendelés típusát a **Tervezett rendeléstípus** mező értéke határozza meg. Ha a **Tervezett rendelés típusa** mező beállítása *Termelés*, akkor létrejönnek a tervezett termelési rendelések. Ezek a tervezett termelési rendelések az aktív anyagjegyzékről (BOM) és a kapcsolódó termelési beállításból származó útvonal-azonosítóról tartalmaznak információkat.

## <a name="requirements-from-boms"></a>Követelmények az anyagjegyzékekből

Az anyagjegyzék-adatokat figyelembe veszik az alaptervezés során. A terv kimenete tartalmazza az anyagellátást, amely fedezi a kapcsolódó termelési anyagigényt.

Az alaptervezés során az aktuális, aktív anyagjegyzék használatos a termeléshez szükséges anyagok meghatározására. Ez a lépés az anyagjegyzék-szerkezetnek a szükséges termelési rendeléshez kapcsolódó összes szintjén történik. Az anyagszükséglet kielégítése az elérhető aktuális készletből, a meglévő rendelési készletekből és a jóváhagyott tervezett rendelésekből történik. Ha bárhol további anyag szükséges, egy tervezett rendelés jön létre az igény fedezése érdekében.

## <a name="scheduling-during-firming"></a>Ütemezés megerősítés során

A tervezett termelési rendelések tartalmazzák a termelés ütemezéséhez szükséges útvonal-azonosítót. A tervezett rendelések tervezett futtatása során azonban függőben van az ütemezés támogatása. Az útvonal-azonosító a tervezett termelési rendelések ütemezésére használható a megerősítés során. Ennek megfelelően a tervezett termelési rendelések átfutási ideje eltérhet a kapcsolódó ütemezett, megerősített termelési rendelések átfutási idejétől, a következők szerint:

- **Tervezett termelési rendelés** – Az átfutási idő a kiadott termékből származó statikus átfutási időn alapul.
- **Visszaszorítású termelési rendelés** – Az átfutási idő az útvonal-információkat és a kapcsolódó erőforrásmegszorításokat használó ütemezésen alapul.

## <a name="delays"></a>Késések

Ha a szükséges anyag átfutási ideje hosszabb a mai dátum és az anyagszükséglet dátuma közötti időszaknál, akkor a szükséges anyag és a kapcsolódó termelési rendelés tervezett rendelése késik. Tervezett rendelések esetén a késleltetés (napokban) számítása a kiadott termék átfutási ideje alapján történik. A késleltetési adatok ezután az anyagjegyzék-szerkezet összes szintjén keresztül továbbterjednek. Így végigkövetheti a késleltetett nyersanyag kihatását a vevői értékesítési rendelésre.

## <a name="modifying-planned-orders"></a>Tervezett rendelések módosítása

Ha módosítja egy tervezett rendelés adatait, a következő üzenet jelenik meg: „Ne feledje, hogy a következő alaptervezés futtatásáig a terv többi részében nem fog tükröződni a manuális módosítások hatása a tervezett rendelésekre.”

Ha módosítani szeretné a tervezett rendelés adatait, és látni szeretné a kapcsolódó anyagkövetelmények hatását, kövesse ezeket a lépéseket.

1. Frissítse a tervezett rendelést.
2. Hagyja jóvá a tervezett rendelést.
3. Futtassa az alaptervezést.

Az alaptervezés futtatásakor nem szabad szűrőket használni, ha szerepel benne tervezett termelési rendelés. A további tudnivalókat lásd [a](#filters) Cikk Szűrők szakaszában.

> [!NOTE]
> Ha a tervezett rendelés szállítási dátumát későbbi dátumra módosították, akkor előfordulhat, hogy az igény egy új tervezett rendeléshez lesz hozzárendelve. Ez a viselkedés akkor fordul elő, amikor az új ellátási dátum késést okoz a követett igényhez, de az átfutási idő beállításai szerint a késleltetés elkerülhető.

## <a name="explosion-page"></a>Alábontás lap

Az **Alábontás** lap használatával elemezni lehet egy adott termelési rendelés vagy tervezett termelési rendelés igényét, a kapcsolódó fedezetet és az igénykövetési adatokat. Az **Alábontás** lapon az alaptervezés során frissülnek az adatok. Az információk nem frissíthetőek közvetlenül az **Alábontás** lapon.

## <a name="filters"></a><a name="filters"></a>Szűrők

Annak érdekében, hogy az alaptervezés a helyes eredmény kiszámításához szükséges információkat tartalmazza, minden olyan terméket bele kell foglalnia a tervezett rendelés teljes anyagjegyzék-struktúrájába, amely kapcsolatban áll a termékekkel. A termelést is magukban foglaló tervezési eseteknél ezért azt javasoljuk, hogy kerülje el a szűrt alaptervezési futtatásokat.

Bár az elavult alaptervezési motor használata esetén a rendszer automatikusan észleli a függő gyermek cikkeket, és bekerül az alaptervezésbe, jelenleg nem végzi el ezt a műveletet a tervezési optimalizálás.

Ha például az A termék anyagjegyzék-szerkezetében egy csavar a B termék előállítására is használatos, akkor a szűrőben szerepelnie kell az A és a B termék anyagjegyzék-szerkezetében található összes terméknek. Mivel bonyolult lehet annak biztosítása, hogy minden termék a szűrő része legyen, javasoljuk, hogy ne használjon szűrőt alaptervezési futtatásoknál termelési rendelések esetén. Ellenkező esetben az alaptervezés nem kívánt eredményeket adhat.

### <a name="reasons-to-avoid-filtered-master-planning-runs"></a>Okok az alaptervezés szűrt futtatásainak elkerülésére

Amikor szűrt alaptervezést futtat egy termékhez, a tervezési optimalizálás (az elavult alaptervezési motorral szemben) nem észleli az adott termék anyagjegyzék-szerkezetében az összes altermelést és nyersanyagot, ezért nem foglalja bele azokat az alaptervezés futtatásába. Bár a Tervezési optimalizálás azonosítja a termék anyagjegyzékszerkezetének első szintjét, nem tölt be termékbeállításokat (például az alapértelmezett rendeléstípust vagy cikkfedezetet) az adatbázisból.

A Tervezés optimalizálásában a futtatás adatai előzőleg betöltődnek, és alkalmazza a szűrőket. Ez azt jelenti, hogy ha egy meghatározott termék alterméke vagy nyersanyaga nem része a szűrőnek, akkor az ezzel kapcsolatos adatokat nem rögzíti a rendszer a futtatás során. Ezenkívül ha az altermék vagy a nyersanyag szerepel egy másik termékben is, akkor egy olyan szűrt futtatás, amely csak az eredeti terméket és összetevőit tartalmazza, eltávolítja a másik termékhez létrehozott meglévő tervezett igényt.

Ez a logika azt okozhatja, hogy a szűrt alaptervezési futtatások nem várt eredményt hoznak. A következő szakaszok példákat mutatnak be az esetleges a váratlan eredményekre.

### <a name="example-1"></a>1. példa

A késztermék *FG* a következő összetevőkből áll:

- Nyersanyag *R*
- Az *S1* altermék amely az *S2* altermékből áll

Van aktuális készlet az *R* nyersanyaghoz, míg az *S1* altermék nincs jelen a készletben.

Ha az *FG* késztermékek fő tervezését szűrten futtatja, akkor a késztermék *FG* számára tervezett termelési rendelést, az *R* nyersanyaghoz tervezett beszerzési rendelést, valamint az *S1* altermékhez tervezett beszerzési rendelést fog kapni. Ez azért nem kívánt eredmény, mert a Tervezési optimalizálás figyelmen kívül hagyta az *R* nyersanyag meglévő készletét, és azt, hogy az *S1* alterméket a közvetlenül rendelés helyett az *S2* használatával kell előállítani. Ez azért történt, mert a tervezési optimalizálás csak a befejezett késztermékek *FG* összetevőinek listáját tartalmazza, kapcsolódó információk, például az összetevők meglévő készlete vagy az alapértelmezett rendelési beállítások nélkül.

### <a name="example-2"></a>2. példa

Az előző példára építve egy további késztermék, az *FG2* is az *S1* alterméket használja. A befejezett *FG2* késztermékre tervezett rendelés létezik, és a tervezett igény az összes összetevőre, köztük az *S1*-re is létezik.

Úgy dönt, hogy szűrt alaptervezés nem szükséges eredményeit az előző példából úgy küszöböli ki, hogy hozzáadja az összes alterméket és nyersanyagot az *FG* késztermék anyagjegyzék-struktúrájából a szűrőbe, majd teljes újragenerálást futtat.

A teljes újragenerálás futtatásakor a rendszer törli az összes benne szereplő termék összes meglévő eredményét, majd az új számítások alapján újra létrehozza az eredményeket. Ez azt jelenti, hogy az *S1* termékhez már meglévő tervezett igényt törli a rendszer, és csak az *FG* késztermékek követelményeit veszi figyelembe, az *FG2* késztermékek követelményeit azonban figyelmen kívül hagyja. Ez azért fordul elő, mert a tervezési optimalizálás futtatásakor a tervezési optimalizálás nem foglalja magában a többi tervezett termelési rendelés tervezett igényét &mdash; csak a futtatás során generált tervezett igényt használja fel a rendszer.

> [!NOTE]
> Ha az *FG2* késztermék meglévő tervezett rendelése *Jóváhagyott* állapotú, a jóváhagyott tervezett igény akkor is szerepelni fog, ha a szülő termék nincs hozzáadva a szűrőhöz.

Ezért hacsak nem ad hozzá minden összetevőt az *FG* késztermékhez, az *FG2* késztermék és minden más termék esetében, amelynek ezek az összetevők részei (az összetevőkkel együtt), a szűrt alaptervezés futtatása nem várt eredményt hoz.

Mivel bonyolult lehet annak biztosítása, hogy minden termék a szűrő része legyen, javasoljuk, hogy ne használjon szűrőt alaptervezési futtatásoknál termelési rendelések esetén.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

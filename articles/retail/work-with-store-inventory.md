---
title: Üzleti árukészlet kezelése
description: A témakör ismerteti, hogy mely dokumentumtípusokat használhat a készlet kezeléséhez.
author: rubencdelgado
manager: AnnBe
ms.date: 04/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: efc729c83b81bd8afb806c403d52fd85b36efc9d
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1523761"
---
# <a name="store-inventory-management"></a>Üzleti árukészlet kezelése

[!include [banner](includes/banner.md)]

Készletek kezelésekor Dynamics 365 for Retail alkalmazásban és a POS alkalmazás használatakor, fontos megjegyezni, hogy POS korlátozott támogatást nyújt készletdimenziókhoz és az egyes készletcikk típusokhoz.  

A POS-megoldás nem támogatja a következő cikk-konfigurációkat:
- Anyagjegyzék-cikkek (kivéve a csomagtermékeket, amelyek használják az anyagjegyzék-keretrendszer bizonyos összetevőit)
- Tényleges súllyal rendelkező cikkek
- Kötegvezérelt cikkek

A POS alkalmazás jelenleg nem támogatja a következő nyomon követési dimenziókat a POS-ben:
- Kötegkövetési-dimenzió
- Tulajdonosi dimenzió

A POS-megoldás a következő dimenziókhoz korlátozott támogatást nyújt. Korlátozott támogatás azt jelzi, hogy a POS esetleg ezen dimenziók némelyikét a automatikusan készlettranzakciókká alakítja a raktár/üzlet a telepítési konfigurációja alapján. POS nem teljes mértékben támogatja a dimenziók, olyan módin, mintha az értékesítési tranzakció manuálisan lenne megadva az ERP-ben. 

- **Raktár helye** – A felhasználók nem lesznek képesek kezelni a fogadó raktár helyét az üzlet raktárába beérkezett cikkekre, amikor az üzlet nincs beállítva a raktárkezelési folyamat használatára.  Ezekhez a cikkekhez az üzlet raktárában megadott alapértelmezett bevételezési hely lesz használatban.  Ha a raktárkezelési folyamat engedélyezve van az üzlethez, akkor korlátozott támogatás jelenik meg a felhasználó számára, válasszon egy fogadó helyszínt a teljes nyugtához.  Az üzletből eladott cikkek mindig az üzlet alapértelmezett raktárából kerülnek eladásra az üzlet raktárbeállításai szerint.   A visszáru-készlet kezelésének helye az üzlet raktárának alapértelmezett visszárurendelés-definícióján keresztül vagy visszaküldés helyére vonatkozó szabályzatban megadott visszaküldési kódok alapján történik.
- **Azonosítótábla** – Azonosítótábla csak akkor van használva, ha a **Raktárkezelési folyamatok alkalmazása** engedélyezve van a cikkhez és az áruházi raktárban.  A pénztárnál abban az esetben, ha a készletet olyan üzletraktárba fogadják, amelyben a raktárkezelési folyamat engedélyezve van, és a tétel beérkezéséhez kiválasztott helyprofil megköveteli az azonosítótábla ellenőrzését, a POS-alkalmazás szisztematikusan azonosítótáblát rendel a fogadó sorhoz.  A POS-felhasználók nem tudják módosítani vagy kezelni ezt az azonosítótábla-adatot.   Ha szükséges az azonosítótáblák teljes körű kezelése, akkor javasolt, hogy az üzlet a WMS Mobile alkalmazást vagy a back office ERP-ügyfelet használja a cikkek fogadásának kezelésére.
- **Sorozatszám** – A POS-alkalmazás korlátozottan támogatja egy sorozatszám regisztrálását tranzakciós értékesítési sorhoz, olyan rendelésekhez, amelyek a pénztárban sorszámozott cikkekkel lettek létrehozva.  Ez a sorozatszám nincs ellenőrizve a már készleten lévő regisztrált sorozatszámokkal szemben.  Ha egy értékesítési rendelést a hívásközpont-csatornában hoztak létre, vagy az ERP-n keresztül van teljesítve, és több sorozatszám lesz regisztrálva egy értékesítési sorhoz az ERP teljesítési folyamata során, akkor ezek a sorozatszámok nem lesznek alkalmazhatók vagy ellenőrizhetők, ha visszárut dolgoznak fel a pénztárban ezekhez a rendelésekhez.
- **Készlet állapota** – A raktárkezelési folyamatot használó cikkek esetében, amelyekhez készletállapot szükséges, ez a mező nem állítható be vagy módosítható a pénztáralkalmazáson keresztül.  A bolt raktárkonfigurátorában megadott készletállapot lesz használva, amikor a cikkek megérkeznek a készletbe.  

> [!NOTE]
> Az összes szervezetnek tesztelnie kell a cikk-konfigurációkat a fejlesztés alatt álló POS-en tesztelési környezeten keresztül a termelésbe helyezés előtt. Teszteljék a cikkeket a megszokott készpénzes tranzakciók és ügyfélrendelések létrehozásával (ha van) az elemek a POS-en keresztül a cikkeivel. A tesztelésnek tartalmaznia kell teljes nyilatkozatközzétételi folyamatokat a tesztkörnyezetben, és ellenőrizni kell, hogy ne legyenek problémák.
> Cikkek konfigurálása oly módon, amelyet POS alkalmazás nem támogat megfelelő tesztelés nélkül, a kimutatás feladási folyamat hibáját okozhatja a termelés során, anélkül, hogy könnyen javítani lehetne a problémákat. Az alkalmazás partneri vagy ügyfél-testreszabásai esetleg megfontolhatók, hogy lehetséges legyen ezen feladási folyamatok sikeres elvégzése. Ha nincs szükség testreszabásokra, a szervezetnek biztosítania kell, hogy megtörtént a termékek a termékkonfigurációja oly módon, hogy azt a szokások POS alkalmazás/rendelés létrehozása/kimutatásfeladási folyamat támogassa.

## <a name="purchase-orders"></a>Beszerzési rendelések

A beszerzési rendeléseket a központi irodában készítik. Ha kiskereskedelmi raktár szerepel a beszerzési rendelés fejlécében, akkor a rendelés fogadása az áruháznál történhet a Modern POS (MPOS) vagy a felhőalapú POS segítségével a Microsoft Dynamics 365 for Retail szolgáltatásban a **Kitárolás/bevételezés** művelettel. Miután az üzletben bevételezett mennyiségek beírásra kerülnek a **Fogadás most** mezőbe a pénztárban a beszerzési rendelés dokumentumba, lehetséges azok helyi mentése vagy véglegesítése. Ezeknek az adatoknak a helyi mentése nem befolyásolja a készleten lévő készletet. A mentés csak akkor hajtható végre, ha a felhasználó nem áll készen bizonylat elküldésére a központba, és szüksége van egy megoldásra a korábban megadott **Most fogadva** adat tárolására.  Ez a most fogadva adatokat menti helyben a felhasználó csatorna-adatbázisába. Miután a dokumentumot feldogozta a **Véglegesítés** lehetőséggel a **Fogadás most** adatokat a program elküldi a központnak és a beszerzési rendelés bizonylata fel lesz adva. 

## <a name="transfer-orders"></a>Átmozgatási rendelések

Az átmozgatási rendelés megadhatja, hogy egy adott üzlet az a hely, ahonnan a cikkeket szállítani lehet, vagy az a hely, ahol fogadják azokat. Ha a pénztár felhasználója egy átmozgatási rendelés szállítási raktára, akkor a pénztárból meg tudja adni a **Szállítás most** mennyiségeket.  A szállító üzlet által megadott adatok helyileg vagy véglegesítve menthetők.  Helyi mentéskor nem történik frissítés a központ átmozgatási rendelési dokumentumában. A mentés csak akkor hajtható végre, ha a felhasználó nem áll készen szállítmány elküldésére a központba, és szüksége van egy megoldásra a korábban megadott **Most szállítva** adat tárolására. Miután az üzlet készen áll a szállítmány jóváhagyására a **Véglegesítés** lehetőséget kell választani. Ez feladja az átmozgatási rendelés kiszállítását a központba, amelyet a fogadó raktár immár képes fogadni. 

Ha a pénztár felhasználója egy átmozgatási rendelés fogadó raktára, akkor a pénztárból meg tudja adni a **Fogadás most** mennyiségeket.  A fogadó üzlet által megadott adatok helyileg vagy véglegesítve menthetők. A mentés csak akkor hajtható végre, ha a felhasználó nem áll készen bizonylat elküldésére a központba, és csak szüksége van egy megoldásra a korábban megadott **Most fogadva** adat tárolására. Ez a most fogadva adatokat menti helyben a felhasználó csatorna-adatbázisába. Miután a dokumentumot feldogozta a **Véglegesítés** lehetőséggel a **Fogadás most** adatokat a program elküldi a központnak és az átmozgatási rendelés bizonylata fel lesz adva. Fontos megjegyezni, hogy a fogadó üzletet csak a szállított mennyiséggel megegyező vagy annál kisebb szállított mennyiségeket képes bevételezni. A korábban nem leszállított átmozgatási rendelések a mennyiségeinek fogadására tett kísérlet hibákat okoz, és a bizonylat nem lesz megerősítve a központban.

## <a name="stock-counts"></a>Leltárok

A leltárok lehetnek ütemezettek és nem tervezettek is. A tervezett leltárokat a központi irodában kezdeményezik, ami meghatározza, hogy melyik cikkeket kell leltározni. A központi iroda létrehoz egy leltárbizonylatot, amelyet fogadni tudnak az üzletnél, ahol a tényleges készletmennyiségeket rögzítik az MPOS vagy a Cloud POS rendszerben. A nem ütemezett leltárakat az üzlet kezdeményezi, és a frissített tényleges készletmennyiségeket vagy az MPOS, vagy a Cloud POS rendszerben rögzítik. Az ütemezett leltárakkal ellentétben a nem ütemezett leltárak nem rendelkeznek a cikkek előre meghatározott listájával. Amikor bármely típusú leltár befejeződik vállalásra kerül és a központi irodába küldik. A központi irodában a leltárt ellenőrzik és feladják egy külön lépésben.

## <a name="inventory-lookup"></a>Keresés a készletben

A több üzlet és raktár számára elérhető aktuális készleten levő termékmennyiséget a **Keresés a készletben** lapon tekintheti meg. Az aktuális készleten levő mennyiségen túl az ígérethez rendelkezésre álló (ATP) mennyiségek az egyes üzletek esetében tekinthetők meg. Ehhez válassza ki azt az üzletet, amelyre vonatkozóan meg akarja jeleníteni az ígérethez rendelkezésre álló mennyiséget, és kattintson az **Üzlet elérhetőségének megjelenítése** lehetőségre.

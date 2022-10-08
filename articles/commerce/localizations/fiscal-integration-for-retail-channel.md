---
title: Commerce-csatornák pénzügyi integrációja – áttekintés
description: Ez a cikk áttekintést nyújt a pénzügyi integrációs lehetőségekről, amelyek elérhetők a témakörben Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 10/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 1812405db3c1e58eaf7cd1df3896f786e7bf026f
ms.sourcegitcommit: 2bc6680dc6b12d20532d383a0edb84d180885b62
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/06/2022
ms.locfileid: "9631240"
---
# <a name="fiscal-integration-overview-for-commerce-channels"></a>Commerce-csatornák pénzügyi integrációja – áttekintés

[!include [banner](../includes/banner.md)]

Ez a témakör áttekintést nyújt a pénzügyi integrációs lehetőségekről Dynamics 365 Commerce. 

A pénzügyi integráció tartalmazza a különböző pénzügyi eszközök és szolgáltatások integrációját, amelyek lehetővé teszik az értékesítések pénzügyi regisztrációját a helyi pénzügyi jogszabályokkal összhangban, amelyek célja az adócsalás megakadályozása a kiskereskedelmi iparágban. Alább láthatók olyan tipikus esetek, amelyek pénzügyi integrációval megoldhatók:

- Ertékesítés regisztrálása olyan pénzügyi eszközön, amely a pénztárhoz (POS) csatlakozik, például pénzügyi nyomtató, majd a pénzügyi nyugta nyomtatása a vevő számára.
- A Retail POS szolgáltatásban végrehajtott értékesítéshez és visszárukhoz kapcsolódó információk biztonságos elküldése külső webes szolgáltatásnak, amelyet az ahatóság üzemeltet.
- Az értékesítési tranzakciós adatok digitális aláírással való el nem használhatóságának biztosítása.

A pénzügyi integrációs funkció egy keretrendszer, amely közös megoldást kínál a Retail POS és a pénzügyi eszközök és szolgáltatások közti integráció továbbfejlesztésére és testreszabására. A funkció pénzügyi integráció mintákat is tartalmaz, amelyek támogatják az alapvető eseteket az adott országban vagy régiókban, és amelyek specifikus pénzügyi eszközökkel vagy szolgáltatásokkal működnek. Pénzügyi integráció minta a Commerce-összetevők számos kiterjesztését is tartalmazza, és szerepel a szoftverfejlesztő készletben (SDK). A fiskális integrációs mintákról további információkat a [Commerce SDK fiskális integrációs mintái](#fiscal-integration-samples-in-the-commerce-sdk) című fejezetben talál. A Commerce SDK telepítéséről és használatáról a [kiskereskedelmi szoftverfejlesztő készlet (SDK) architektúrája](../dev-itpro/retail-sdk/retail-sdk-overview.md)című fejezetben talál információkat.

Az olyan helyzetek támogatásához, amelyeket nem támogat a pénzügyi integrációs minta, a Retail POS egyéb pénzügyi eszközökkel vagy szolgáltatásokkal való integrálásához, vagy a más országokban vagy régiókban levő követelmények lefedéséhez vagy ki kell terjesztenie a létező pénzügyi integrációs mintát, vagy új mintát kell létrehoznia egy meglévő minta példaként való használatával.

## <a name="fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services"></a>Pénzügyi nyilvántartási folyamat és pénzügyi integrációs mintái pénzügyi eszközök és szolgáltatások esetében

A pénzügyi regisztrációs folyamat a Retail POS felületén egy vagy több lépésből állhat. Minden egyes lépés magában foglalja az adott tranzakciók vagy események pénzügyi regisztrációját egy pénzügyi eszközben vagy szolgáltatásban. A következő megoldásösszetevők vesznek részt a pénzügyi regisztrációban egy pénzügyi eszközön vagy szolgáltatásban:

- **Pénzügyi bizonylat** szolgáltatója – ez az összetevő a pénzügyi eszközzel vagy szolgáltatással való együttműködésre is használt formátumban szerializálja a tranzakció-/eseményadatokat, elemezi a pénzügyi eszköz vagy szolgáltatás válaszait, és tárolja a válaszokat a csatorna-adatbázisban. A kiterjesztés a regisztrálandó meghatározott tranzakciókat és eseményeket is meghatározza.
- **Pénzügyi** csatlakoztató – ez az összetevő inicializálja a kommunikációt a pénzügyi eszközzel vagy szolgáltatással, kéréseket vagy közvetlen parancsokat küld a pénzügyi eszköznek vagy szolgáltatásnak a pénzügyi bizonylatból kinyert tranzakció-/eseményadatok alapján, és válaszokat fogad a pénzügyi eszköztől vagy szolgáltatástól.

A pénzügyi integrációs minta egy pénzügyi bizonylatszolgáltató és egy pénzügyi csatlakoztató Commerce runtime (CRT), hardverállomás és POS-bővítményét tartalmazhatja. A következő összetevő-konfigurációkat is tartalmazza:

- **Pénzügyi dokumentumszolgáltató konfigurációja** – Ez a beállítás meghatározza a pénzügyi dokumentumokhoz tartozó kimeneti módszert, valamint a formátumot. Az adók és fizetési módok adatleképezését is tartalmazza, hogy a Retail POS rendszerből származó adatokat kompatibilis legyen a pénzügyi eszközön vagy szolgáltatásban előre meghatározott értékekkel.
- **Pénzügyi csatlakoztató konfigurációja** – ez a konfiguráció határozza meg a tényleges kommunikációt az adott pénzügyi eszközzel vagy szolgáltatással.

Egy adott POS-pénztárgép pénzügyi regisztrációs folyamatát a pénztár funkcióprofiljának megfelelő beállítása határozza meg. A pénzügyi nyilvántartási folyamat konfiguráljával, a pénzügyi bizonylat szolgáltatójának és a pénzügyi csatlakoztató konfigurációjának feltöltésével, [valamint a konfigurációs paraméterek beállításának a beállítási folyamattal kapcsolatban további tudnivalókat olvashat](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

> [!NOTE]
> Ha nem pénzügyi műveletekhez eszközökre (például termékkatalógus-kereséshez, vevőkereséshez vagy tranzakció-vázlatok létrehozásához) van szükség, ezeket a pénzügyi folyamatra vonatkozó korlátozásokkal pénztárgépként választhatja ki. A további tudnivalókat lásd [a Pénztárgép beállítása pénzügyi nyilvántartási korlátozásokkal](setting-up-fiscal-integration-for-retail-channel.md#set-up-registers-with-fiscal-registration-restrictions).

A következő jellemző pénzügyi regisztrációs folyamat a POS egy eseményével kezdődik (például egy értékesítési tranzakció véglegesítésével), és egy előre meghatározott lépéssorozatot valósít meg, amely a Commerce rendszer más összetevőit (CRT például a hardverállomást) érinti.

1. A POS pénzügyi bizonylatot kér a pénzügyi integrációs keretrendszertől (FIF).
1. Az FIF határozza meg, hogy az aktuális eseményhez pénzügyi regisztráció szükséges-e.
1. A pénzügyi regisztrációs folyamat beállításai alapján a FIF azonosítja a pénzügyi csatlakoztatóját és a megfelelő pénzügyi dokumentumszolgáltatót, amely a pénzügyi regisztráció során használható.
1. A FIF futtatja a tranzakciót vagy eseményt képviselő pénzügyi bizonylatot (például XML-dokumentumot) generáló pénzügyi dokumentum szolgáltatóját.
1. Az FIF a létrehozott pénzügyi bizonylatot visszaadja a POS-nak.
1. A POS kéri, hogy a FIF küldje el a pénzügyi bizonylatot a pénzügyi eszköznek vagy szolgáltatásnak.
1. A FIF futtatja a pénzügyi bizonylatot feldolgozó pénzügyi csatlakoztatóját, és elküldi a pénzügyi eszköznek vagy szolgáltatásnak.
1. A FIF a pénzügyi választ (azaz a pénzügyi eszköz vagy szolgáltatás válaszát) adja vissza a PÉNZTÁRnak.
1. A POS a pénzügyi választ elemzi, és meghatározza, hogy sikeres volt-e a pénzügyi regisztráció. A POS a szükséges módon kéri, hogy a FIF kezelje a hibákat. 
1. A POS kéri a FIF feldolgozását és a pénzügyi válasz mentését.
1. A pénzügyi bizonylat szolgáltatója dolgozza fel a pénzügyi választ. A feldolgozás részeként a pénzügyi bizonylat szolgáltatója elemezi a választ, és további adatokat bont ki belőle.
1. A FIF rendszer menti a választ és a kiterjesztett adatokat a csatorna-adatbázisba.
1. A POS szükség esetén kinyomtat egy nyugtát egy normál nyugtanyomtatón keresztül, amely a hardverállomáshoz csatlakozik. A nyugta tartalmazhat a pénzügyi válaszból szükséges adatokat.
 
A következő példák bemutatják a pénzügyi regisztrációk végrehajtásának folyamatait a tipikus pénzügyi eszközökre és szolgáltatásokra.
 
### <a name="fiscal-registration-is-done-via-a-device-connected-to-the-hardware-station"></a>A pénzügyi regisztráció a hardverállomáshoz csatlakoztatott eszközön történik.

Ez a konfiguráció akkor használatos, amikor egy fizikai pénzügyi eszköz, például egy pénzügyi nyomtató kapcsolódik a hardverállomáshoz. Akkor is alkalmazható, ha a hardverállomásra telepített szoftveren keresztül történik a pénzügyi eszközzel vagy szolgáltatással való kommunikáció. Ebben az esetben a pénzügyi bizonylat szolgáltatója CRT a, a pénzügyi csatlakoztató pedig a Hardverállomáson található.

![A hardverállomáshoz csatlakoztatott eszközön végzett pénzügyi regisztráció.](media/FIF-CRT-HWS.png)

### <a name="fiscal-registration-is-done-via-an-external-service"></a>A pénzügyi regisztráció külső szolgáltatáson keresztül történik

Ez a konfiguráció akkor használatos, amikor a pénzügyi nyilvántartás külső szolgáltatáson keresztül történik, például egy olyan webszolgáltatással, amelyet az adóhatóság működtet. Ebben az esetben mind a pénzügyi bizonylat szolgáltatója, mind a pénzügyi csatlakoztató a helyen található CRT.

![Külső szolgáltatáson keresztül végzett pénzügyi regisztráció.](media/FIF-CRT-CRT.png)
 
### <a name="fiscal-registration-is-done-internally-in-the-crt"></a>A pénzügyi regisztráció belsőleg történik a következőben: CRT

Ez a konfiguráció akkor használatos, ha nincs szükség külső pénzügyi eszközre vagy szolgáltatásra a pénzügyi regisztrációhoz. Például akkor használatos, amikor a pénzügyi regisztráció az értékesítési tranzakciók digitális aláírásával történik. Ebben az esetben mind a pénzügyi bizonylat szolgáltatója, mind a pénzügyi csatlakoztató a helyen található CRT.

![A pénzügyi regisztráció belsőleg történik a CRT.](media/FIF-CRT-CRT-SGN.png)

### <a name="fiscal-registration-is-done-via-a-device-or-service-in-the-local-network"></a>A pénzügyi regisztráció a helyi hálózaton található eszközön vagy szolgáltatáson keresztül történik.

Ez a konfiguráció akkor használatos, amikor egy fizikai pénzügyi eszköz vagy pénzügyi szolgáltatás elérhető az üzlet helyi hálózatában, és HTTPS alkalmazásprogramozási felületet (API) biztosít. Ebben az esetben a pénzügyi bizonylat szolgáltatója CRT az, és a pénzügyi csatlakoztató a POS terminálon található.

![A pénzügyi regisztráció a helyi hálózaton található eszközön vagy szolgáltatáson keresztül történik.](media/FIF-CRT-POS.png)

## <a name="error-handling"></a>Hibakezelés

A pénzügyi integrációs keretrendszer a hibák kezelésére a pénzügyi regisztráció során a következő lehetőségeket nyújtja:

- **Újrapróbálkozás** – a kezelő akkor használhatja ezt a lehetőséget, ha a hiba gyorsan kijavítható, és a pénzügyi regisztráció újrafuttatható. Például ezt a lehetőséget használhatja, amikor a pénzügyi eszköz nincs csatlakoztatva, a pénzügyi nyomtatóból kifogyott a papír, vagy papírelakadás van a pénzügyi nyomtatóban.
- **Mégse** – ez a beállítás lehetővé teszi, hogy a kezelő sikertelen eset esetén halasztsa az aktuális tranzakció vagy esemény pénzügyi regisztrációját. A regisztráció halasztás után az operátor továbbra is dolgozhat a POS-terminálon, és bármilyen műveletet befejezhet, amihez nincs szükség a pénzügyi regisztrációra. Ha olyan esemény történik a pénztárban, amelyhez a pénzügyi regisztráció szükséges (például egy új tranzakciót nyitnak), a hibakezelési párbeszédpanel automatikusan megjelenik és értesíti az operátort, hogy a korábbi tranzakciót nem megfelelően regisztrálták, és hibakezelési lehetőségeket nyújt.
- **Kihagyás** – a kezelő akkor használhatja ezt a lehetőséget, ha nem lehet végrehajtani az aktuális tranzakció vagy esemény pénzügyi regisztrációját, például ha a pénzügyi nyomtató nincs megadva, **és** a pénzügyi regisztrációt ki lehet hagyni bizonyos körülmények között. Ez a beállítás például használható, amikor egy értékesítési tranzakciót, amelynek a pénzügyi regisztrációja nem sikerült, a különleges papírnaplóban lehet regisztrálni. A pénzügyi regisztráció kihagyása után a normál műveleteket folytatni lehet a POS-terminálon. 
- **Megjelölés regisztráltként** – a kezelő akkor használhatja ezt a lehetőséget, ha az aktuális tranzakció vagy esemény ténylegesen regisztrálva van a pénzügyi eszközön, például kinyomtatott egy pénzügyi nyugtát, de hiba történik a pénzügyi válasznak a csatorna-adatbázisba való mentésekor. Az aktuális tranzakció vagy esemény regisztráltként való megjelölése után a normál műveleteket folytatni lehet a POS-terminálon.
- **Halasztás** – a kezelő akkor **használhatja** ezt a lehetőséget, ha nincs regisztrálva a tranzakció, mert a regisztrációs eszköz vagy szolgáltatás nem érhető el, és a következők valamelyike érvényes:
    - Van egy biztonsági másolatként készítt pénzügyi regisztráció, és folytatható az aktuális tranzakció pénzügyi regisztrációs folyamata. Például egy helyi [pénzügyi](./latam-bra-cf-e-sat.md#scenario-4-make-a-cash-and-carry-sale-of-goods-by-using-sat-as-contingency-mode) eszköz lehet az online pénzügyi regisztrációs szolgáltatás biztonsági másolata, ha a szolgáltatás nem áll rendelkezésre.
    - A pénzügyi regisztráció később a pénzügyi integrációs keretrendszeren kívül más módon is tehet. Például az elhalasztott [tranzakciók később külön funkcióval regisztrálhatóak egy kötegben](./latam-bra-nfce.md#scenario-3-make-a-cash-and-carry-sale-of-goods-in-offline-contingency-mode).
    
    Az aktuális tranzakció vagy esemény elhalasztása után a normál műveleteket folytatni lehet a POS-terminálon.

> [!WARNING]
> A **Skip**, **a Megjelölés regisztráltként és** **a Halasztás** lehetőséget rendkívüli lehetőségnek kell tekinteni, és csak kivételes esetekben szabad alkalmazni. A hibakezelési beállításokat a jogi vagy adózási részletekben is tárgyalni kell, és mielőtt engedélyezték volna őket, jó tanácsokat kell alkalmazniuk. A beállításokat használat előtt aktiválni kell a pénzügyi nyilvántartási folyamatban. Annak érdekében, hogy a kezelők ne használják rendszeresen, meg kell adni a megfelelő engedélyeket az operátorok számára.

Pénzügyi tranzakció akkor [jön létre, ha a](#storing-fiscal-response-in-fiscal-transaction) Kihagyás **,** Megjelölés **regisztráltként** **vagy Halasztás beállítás van megjelölve, de a pénzügyi tranzakció nem tartalmaz pénzügyi** választ. Ennek segítségével rögzítheti a pénzügyi regisztráció sikertelenségének eseményét. Ezekkel a beállításokkal infókódok is rögzíthetik a hibákkal kapcsolatos bizonyos információkat, például a hiba okát, vagy a pénzügyi regisztráció kihagyásának vagy a tranzakció regisztráltként való megjelölésének indoklását. Hibakezelési paraméterek beállításával kapcsolatos további tudnivalókat lásd: [Hibakezelési beállítások beállítása](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="optional-fiscal-registration"></a>Opcionális pénzügyi regisztráció

Pénzügyi regisztráció kötelező lehet az egyes műveletekhez, míg másoknál opcionális. Például előfordulhat, hogy a pénzügyi regisztráció normál értékesítések és visszáru esetében kötelező, de lehet, hogy a vevői letétekhez kapcsolódó műveletek pénzügyi regisztrációja nem kötelező. Ebben az esetben az eladás pénzügyi regisztrálásának elmulasztása blokkolja a további értékesítést, de a vevői letétet pénzügyi regisztrációjának elmulasztása nem akadályozza meg a további értékesítést. A kötelező és választható műveletek megkülönböztetéséhez ajánlott a különböző dokumentum szolgáltatókon keresztül kezelni azokat, és hogy külön lépéseket állítson be a pénzügyi regisztrációs folyamatban ezekhez a szolgáltatókhoz. A **Hiba esetén folytatás** paramétert engedélyezni kell minden lépéshez, amely kapcsolódik az opcionális pénzügyi regisztrációhoz. Hibakezelési paraméterek beállításával kapcsolatos további tudnivalókat lásd: [Hibakezelési beállítások beállítása](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="manually-rerun-fiscal-registration"></a>Pénzügyi regisztráció manuális újrafutata

Ha egy tranzakció vagy esemény pénzügyi regisztrációja hiba után halasztva lett (**például** ha a művelet a Hibakezelési párbeszédpanelEn a Mégse gombra volt jelölve), akkor a pénzügyi regisztrációt kézzel újrafuttathatja a megfelelő műveletre való hivatkozással. A további tudnivalókat lásd [a Halasztott pénzügyi regisztrációk kézi végrehajtásának engedélyezése.](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-deferred-fiscal-registration)

### <a name="fiscal-registration-health-check"></a>Pénzügyi regisztráció állapotának ellenőrzése

A pénzügyi regisztrációkhoz tartozó állapotellenőrzési eljárás ellenőrzi az elérhetőségét egy pénzügyi eszköznek vagy szolgáltatásnak bizonyos események bekövetkezésekor. Ha a pénzügyi regisztráció jelenleg nem hajtható végre, a kezelő előre értesítést kap.

A pénztár lefuttatja az állapotellenőrzést a következő események bekövetkezése esetén:

- Új tranzakció megnyitása.
- Egy felfüggesztett tranzakció visszahívása.
- Egy értékesítési vagy visszáru-tranzakció lezárása.

Ha az állapotellenőrzés sikertelen, a POS megjeleníti az állapotellenőrzés párbeszédpanelt. Ez a párbeszédpanel a következő gombokat teszi elérhetővé:

- **OK** – Ez a gomb lehetővé teszi, hogy a kezelő az állapotellenőrzési hibát figyelmen kívül hagyja, és folytassa a műveletet. Kezelők csak akkor választhatják ki ezt a gombot, ha az **Állapotellenőrzési hiba kihagyásának ellenőrzése** jogosultság engedélyezve van hozzájuk.
- **Mégse** – Ha a kezelő ezt a gombot választja , a POS érvényteleníti az utolsó művelet (például egy cikk nem adódik hozzá egy új tranzakcióhoz).

> [!NOTE]
> Az állapotellenőrzés csak akkor fut le, ha az aktuális művelethez pénzügyi regisztráció szükséges, **és** ha a hiba esetén a Folytatás paraméter nincs engedélyezve a pénzügyi nyilvántartási folyamat aktuális lépésében. További részletekért lásd: [Hibakezelés beállításainak megadása](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

## <a name="storing-fiscal-response-in-fiscal-transaction"></a>Pénzügyi válasz tárolása pénzügyi tranzakcióban

Ha egy tranzakció vagy esemény pénzügyi regisztrációja sikeres, a pénzügyi tranzakció létrejön a csatorna-adatbázisban, és az eredeti tranzakcióhoz vagy eseményhez kapcsolódik. Hasonlóképpen, ha **sikertelen pénzügyi regisztrációnál be van jelölve a Skip**, **a Megjelölés** **regisztráltként** vagy az Elhalasztás beállítás, akkor ezek az adatok egy pénzügyi tranzakcióban tárolódnak. A pénzügyi tranzakció tárolja a pénzügyi eszköz vagy szolgáltatás pénzügyi válaszát. Ha a pénzügyi regisztrációs folyamat több lépésből áll, a sikeres vagy sikertelen regisztrációt eredményező folyamat minden egyes lépéséhez létrejön egy pénzügyi tranzakció.

A pénzügyi tranzakciókat a rendszer a Headquarters szolgáltatásba továbbítja a *P-feladat* segítségével, a tranzakciókkal együtt. A **Pénzügyi tranzakciók** gyorslapon az **Üzleti tranzakciók** oldalon belül megtekintheti azokat a pénzügyi tranzakciókat, amelyekhez tranzakciók kapcsolódnak.

A pénzügyi tranzakció tárolja a következő adatokat:

- Pénzügyi regisztrációs folyamat részletei (folyamat, csatlakozócsoport, csatlakozó stb). Szintén tárolja a pénzügyi eszköz sorozatszámát a **Pénztárgép száma** mezőben, ha ez az információ szerepel a pénzügyi válaszban.
- A pénzügyi regisztráció állapota: **Befejeződött** a sikeres regisztrációhoz. A rendszer kihagyja, **·** **ha** az operátor a Sikertelen regisztrációk Kihagyása lehetőséget választotta, ha az operátor regisztráltként jelöli meg, vagy Ha az operátor az Elhalasztás lehetőséget választotta, **·** **·** **·** **akkor** ez a beállítás van megjelölve.
- A kijelölt pénzügyi tranzakcióhoz kapcsolódó összes infókód-tranzakció. Az infókód-tranzakciók megtekintéséhez a Pénzügyi tranzakciók gyorsjelentés lapon válasszon ki egy Kihagyva, Regisztráltként **·** **megjelölve** vagy Halasztva állapotú pénzügyi tranzakciót, **majd válassza ki az infókód-tranzakciókat.** **·** **·**

A **Bővített adatok** kiválasztásával megtekintheti az adótranzakció egyes tulajdonságait is. A megtekinthető tulajdonságok listája az adóügyi tranzakciót generáló adóügyi nyilvántartási funkcióra jellemző. Például megtekintheti a digitális aláírást, a sorszámot, a tanúsítvány ujjlenyomatát, a kivonatoló algoritmus azonosítását és más adózási tranzakciótulajdonságokat a franciaországi digitális aláírási funkcióhoz.

## <a name="fiscal-texts-for-discounts"></a>Pénzügyi szövegek engedményekhez

Egyes országokban vagy régiókban különleges követelmények vannak érvényben a további szövegekkel kapcsolatban, amelyeket a pénzügyi nyugtára kell nyomtatni, amikor különböző engedményeket alkalmaznak. A pénzügyi integráció funkció segítségével beállíthat egy speciális szöveget az engedményhez, amelyet az engedmény sora után a pénzügyi nyugtára nyomtat. Manuális engedmények esetén, konfigurálhatja az infókódhoz megadott pénzügyi szöveget, amelyhez az infókód a **Termék engedménye** infókódként van megadva a pénztár funkcióprofilján. A pénzügyi szövegek engedményekhez való beállításával kapcsolatos további tudnivalókat lásd: [Pénzügyi szövegek beállítása engedményekhez](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-texts-for-discounts).

## <a name="printing-fiscal-x-and-fiscal-z-reports"></a>Pénzügyi X- és pénzügyi Z-jelentések nyomtatása

A pénzügyi integráció funkció támogatja az integrált pénzügyi eszköz vagy szolgáltatásra vonatkozóan egyedi napzáró kimutatások generálását:

- A megfelelő műveletek futtatására használatos új gombokat a pénztár képernyő-elrendezésén kell hozzáadni. További részletekért lásd: [Pénzügyi X/Z jelentések beállítása a pénztárból](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
- A pénzügyi integrációs mintában ezeket a műveleteket meg kell feleltetni a pénzügyi eszköz megfelelő műveleteivel.

## <a name="fiscal-integration-samples-in-the-commerce-sdk"></a>Adóügyi integrációs minták a Commerce SDK-ban

A Commerce SDK-ban jelenleg a következő adóügyi integrációs minták állnak rendelkezésre:

- [Adóügyi nyomtató integrációját bemutató minta Olaszországra vonatkozóan](./emea-ita-fpi-sample.md)
- [Adóügyi nyomtató integrációját bemutató minta Lengyelországra vonatkozóan](./emea-pol-fpi-sample.md)
- [Adóügyi regisztrációs szolgáltatás integrációját bemutató minta Ausztriára vonatkozóan](./emea-aut-fi-sample.md)
- [Adóügyi regisztrációs szolgáltatás integrációját bemutató minta Csehországra vonatkozóan](./emea-cze-fi-sample.md)
- [Ellenőrzőegység integrációs mintája Svédország esetén](./emea-swe-fi-sample.md)
- [Adóügyi regisztrációs szolgáltatás integrációját bemutató minta Németországra vonatkozóan](./emea-deu-fi-sample.md)
- [Adóügyi nyomtató integrációját bemutató minta Oroszországra vonatkozóan](./rus-fpi-sample.md)

A következő adóügyi integrációs funkciókat szintén a költségvetési integrációs keretrendszer használatával valósítjuk meg, de ezek a funkciók a dobozból elérhetőek, és nem szerepelnek a Commerce SDK-ban:

- [Adóügyi nyilvántartásba vétel Brazíliában](./latam-bra-commerce-localization.md#fiscal-registration-for-brazil)
- [Digitális aláírás Franciaország esetén](./emea-fra-cash-registers.md)

A következő adóügyi integrációs funkciók szintén elérhetők a Commerce SDK-ban, de jelenleg nem használják ki az adóügyi integrációs keretrendszert. Ennek a funkciónak az áttelepítése a pénzügyi integrációs keretrendszerbe a későbbi frissítésekben tervezett.

- [Digitális aláírás Norvégia esetén](./emea-nor-cash-registers.md)

A következő, a Commerce SDK-ban elérhető, régebbi adóügyi integrációs funkciók nem használják a költségvetési integrációs keretrendszert, és a későbbi frissítések során elavulttá válnak:

- [Ellenőrzőegység integrációs mintája Svédország esetén (örökölt)](./retail-sdk-control-unit-sample.md)
- [Digitális aláírás Franciaország esetében (örökölt)](./emea-fra-deployment.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

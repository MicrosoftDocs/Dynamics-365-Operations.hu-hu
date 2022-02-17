---
title: A Commerce-csatornák pénzügyi integrálásának áttekintése
description: Ez a témakör a Dynamics 365 Commerce szolgáltatásban rendelkezésre álló pénzügyi integrációs lehetőségekről ad áttekintést.
author: EvgenyPopovMBS
ms.date: 01/31/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 82913eaca1d56a5b0609480d8825717278eca132
ms.sourcegitcommit: 5cefe7d2a71c6f220190afc3293e33e2b9119685
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2022
ms.locfileid: "8077192"
---
# <a name="overview-of-fiscal-integration-for-commerce-channels"></a>A Commerce-csatornák pénzügyi integrálásának áttekintése

[!include [banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

Ez a témakör a Dynamics 365 Commerce szolgáltatásban rendelkezésre álló pénzügyi integrációs lehetőségek áttekintése. 

A pénzügyi integráció tartalmazza a különböző pénzügyi eszközök és szolgáltatások integrációját, amelyek lehetővé teszik az értékesítések pénzügyi regisztrációját a helyi pénzügyi jogszabályokkal összhangban, amelyek célja az adócsalás megakadályozása a kiskereskedelmi iparágban. Alább láthatók olyan tipikus esetek, amelyek pénzügyi integrációval megoldhatók:

- Ertékesítés regisztrálása olyan pénzügyi eszközön, amely a pénztárhoz (POS) csatlakozik, például pénzügyi nyomtató, majd a pénzügyi nyugta nyomtatása a vevő számára.
- A Retail POS szolgáltatásban végrehajtott értékesítéshez és visszárukhoz kapcsolódó információk biztonságos elküldése külső webes szolgáltatásnak, amelyet az ahatóság üzemeltet.
- Segít az értékesítési tranzakcióadatok megmásíthatatlanságát digitális aláírások segítségével.

A pénzügyi integrációs funkció egy keretrendszer, amely közös megoldást kínál a Retail POS és a pénzügyi eszközök és szolgáltatások közti integráció továbbfejlesztésére és testreszabására. A funkció pénzügyi integráció mintákat is tartalmaz, amelyek támogatják az alapvető eseteket az adott országban vagy régiókban, és amelyek specifikus pénzügyi eszközökkel vagy szolgáltatásokkal működnek. Pénzügyi integráció minta a Commerce-összetevők számos kiterjesztését is tartalmazza, és szerepel a szoftverfejlesztő készletben (SDK). A fiskális integrációs mintákról további információkat a [Commerce SDK fiskális integrációs mintái](#fiscal-integration-samples-in-the-commerce-sdk) című fejezetben talál. A Commerce SDK telepítéséről és használatáról a [kiskereskedelmi szoftverfejlesztő készlet (SDK) architektúrája](../dev-itpro/retail-sdk/retail-sdk-overview.md)című fejezetben talál információkat.

Az olyan helyzetek támogatásához, amelyeket nem támogat a pénzügyi integrációs minta, a Retail POS egyéb pénzügyi eszközökkel vagy szolgáltatásokkal való integrálásához, vagy a más országokban vagy régiókban levő követelmények lefedéséhez vagy ki kell terjesztenie a létező pénzügyi integrációs mintát, vagy új mintát kell létrehoznia egy meglévő minta példaként való használatával.

## <a name="fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services"></a>Fiskális regisztrációs folyamat és fiskális integrációs minták a fiskális eszközökhöz és szolgáltatásokhoz

A pénzügyi regisztrációs folyamat a Retail POS felületén egy vagy több lépésből állhat. Minden egyes lépés magában foglalja az adott tranzakciók vagy események pénzügyi regisztrációját egy pénzügyi eszközben vagy szolgáltatásban. A következő megoldás-összetevők vesznek részt az adózási eszköz vagy szolgáltatás adóregisztrációjában:

- **Adóügyi dokumentum-szolgáltató** – Ez az összetevő sorosítja a tranzakciós/eseményadatokat az adóeszközzel vagy szolgáltatással való interakcióhoz is használt formátumban, elemzi a pénzügyi eszközről vagy szolgáltatásról érkező válaszokat, és a válaszokat a csatornaadatbázisban tárolja. A kiterjesztés a regisztrálandó meghatározott tranzakciókat és eseményeket is meghatározza.
- **Pénzügyi csatlakozó** – Ez az összetevő inicializálja a kommunikációt az adóeszközzel vagy szolgáltatással, kéréseket vagy közvetlen parancsokat küld a pénzügyi eszköznek vagy szolgáltatásnak az adóbizonylatból kinyert tranzakció/eseményadatok alapján, és válaszokat fogad a pénzügyi eszköztől vagy szolgáltatástól.

Egy fiskális integrációs minta tartalmazhatja a Commerce futási környezetet (CRT), Hardverállomás és POS-bővítmények egy adódokumentum-szolgáltatóhoz és egy fiskális csatlakozóhoz. A következő összetevő-konfigurációkat is tartalmazza:

- **Pénzügyi dokumentumszolgáltató konfigurációja** – Ez a beállítás meghatározza a pénzügyi dokumentumokhoz tartozó kimeneti módszert, valamint a formátumot. Tartalmaz továbbá egy adatleképezést az adókra és a fizetési módokra vonatkozóan, hogy a Retail POS adatai kompatibilisek legyenek az adózási eszközben vagy szolgáltatás firmware-ében előre meghatározott értékekkel.
- **Fiskális csatlakozó konfigurációja** – Ez a konfiguráció határozza meg a fizikai kommunikációt az adott adóeszközzel vagy szolgáltatással.

Egy adott POS-pénztárgép pénzügyi regisztrációs folyamatát a pénztár funkcióprofiljának megfelelő beállítása határozza meg. Az adóregisztrációs folyamat konfigurálásával, az adódokumentum-szolgáltató és a fiskális csatlakozási konfigurációk feltöltésével, valamint a konfigurációs paraméterek módosításával kapcsolatos további részletekért lásd: [Állítsa be az adózási regisztrációs folyamatot](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

A következő tipikus fiskális regisztrációs folyamat egy eseménnyel kezdődik a POS-ban (például egy értékesítési tranzakció véglegesítése), és egy előre meghatározott lépéssorozatot hajt végre, amely más kereskedelmi összetevőket (például CRT és Hardver állomás).

1. A POS fiskális dokumentumot kér a fiskális integrációs keretrendszertől (FIF).
1. A FIF határozza meg, hogy az aktuális esemény adóügyi regisztrációt igényel-e.
1. Az adóregisztrációs folyamat beállításai alapján a FIF azonosít egy adóösszekötőt és egy megfelelő adódokumentum-szolgáltatót az adóregisztrációhoz.
1. A FIF az adódokumentum-szolgáltatót futtatja, amely a tranzakciót vagy eseményt reprezentáló fiskális bizonylatot (például XML-dokumentumot) állít elő.
1. A FIF visszaküldi a generált pénzügyi bizonylatot a POS-nak.
1. A POS kéri, hogy a FIF nyújtsa be az adódokumentumot az adóeszköznek vagy szolgáltatásnak.
1. A FIF futtatja a fiskális összekötőt, amely feldolgozza a pénzügyi bizonylatot, és elküldi azt a pénzügyi eszköznek vagy szolgáltatásnak.
1. A FIF visszaküldi a fiskális választ (vagyis az adóeszköz vagy szolgáltatás válaszát) a POS-nak.
1. A POS elemzi a fiskális választ annak megállapítására, hogy az adóregisztráció sikeres volt-e. Szükség esetén a POS kéri, hogy a FIF kezelje az esetleges hibákat. 
1. A POS kéri, hogy a FIF feldolgozza és mentse a fiskális választ.
1. Az adódokumentum-szolgáltató feldolgozza a fiskális választ. A feldolgozás részeként a pénzügyi bizonylat-szolgáltató elemzi a választ, és kivonja belőle a kiterjesztett adatokat.
1. A FIF a választ és a kiterjesztett adatokat a csatorna adatbázisba menti.
1. Szükség szerint a POS nyugtát nyomtat egy szokásos nyugtanyomtatón keresztül, amely a hardverállomáshoz csatlakozik. A nyugta tartalmazhatja a fiskális válaszból származó szükséges adatokat.
 
A következő példák a tipikus fiskális eszközök vagy szolgáltatások adóregisztrációs végrehajtási folyamatait mutatják be.
 
### <a name="fiscal-registration-is-done-via-a-device-connected-to-the-hardware-station"></a>Az adóbejegyzés a Hardver állomáshoz csatlakoztatott eszközön keresztül történik

Ez a konfiguráció akkor használatos, ha egy fizikai adóeszköz, például egy adónyomtató csatlakozik a hardverállomáshoz. Akkor is alkalmazható, ha a kommunikáció egy pénzügyi eszközzel vagy szolgáltatással a hardverállomásra telepített szoftveren keresztül történik. Ebben az esetben az adódokumentum-szolgáltató a következő helyen található:CRT, és a pénzügyi csatlakozó a Hardver állomáson található.

![Fiskális regisztráció a Hardver állomáshoz csatlakoztatott eszközön keresztül.](media/FIF-CRT-HWS.png)

### <a name="fiscal-registration-is-done-via-an-external-service"></a>Az adóbejegyzés külső szolgáltatáson keresztül történik

Ez a konfiguráció akkor használatos, ha az adóregisztráció külső szolgáltatáson, például az adóhatóság által üzemeltetett webszolgáltatáson keresztül történik. Ebben az esetben mind az adódokumentum-szolgáltató, mind a pénzügyi csatlakozó a következő helyen található:CRT.

![Az adóbejegyzés külső szolgáltatáson keresztül történik.](media/FIF-CRT-CRT.png)
 
### <a name="fiscal-registration-is-done-internally-in-the-crt"></a>Az adóbejegyzés belsőleg történik a CRT

Ez a konfiguráció akkor használatos, ha nincs szükség külső adóeszközre vagy szolgáltatásra az adóregisztrációhoz. Például akkor használatos, amikor az adóregisztráció az értékesítési tranzakciók digitális aláírásával történik. Ebben az esetben mind az adódokumentum-szolgáltató, mind a pénzügyi csatlakozó a következő helyen található:CRT.

![Az adóbejegyzés belsőleg történik a CRT.](media/FIF-CRT-CRT-SGN.png)

### <a name="fiscal-registration-is-done-via-a-device-or-service-in-the-local-network"></a>Az adóbejegyzés a helyi hálózaton lévő eszközön vagy szolgáltatáson keresztül történik

Ez a konfiguráció akkor használatos, ha egy fizikai adóeszköz vagy adószolgáltatás van jelen az áruház helyi hálózatában, és HTTPS alkalmazásprogramozási felületet (API) biztosít. Ebben az esetben az adódokumentum-szolgáltató a következő helyen található:CRT és a fiskális csatlakozó a POS-on található.

![Az adóbejegyzés a helyi hálózaton lévő eszközön vagy szolgáltatáson keresztül történik.](media/FIF-CRT-POS.png)

## <a name="error-handling"></a>Hibakezelés

A pénzügyi integrációs keretrendszer a hibák kezelésére a pénzügyi regisztráció során a következő lehetőségeket nyújtja:

- **Újrapróbálkozás** – Az operátorok használhatják ezt a lehetőséget, ha a hiba gyorsan feloldható, és a pénzügyi regisztrációt újrafuttathatja. Például ezt a lehetőséget használhatja, amikor a pénzügyi eszköz nincs csatlakoztatva, a pénzügyi nyomtatóból kifogyott a papír, vagy papírelakadás van a pénzügyi nyomtatóban.
- **Érvénytelenítés** – Ezzel a lehetőséggel az operátorok elhalaszthatják az aktuális tranzakció vagy esemény pénzügyi regisztrációját, ha sikertelen. A regisztráció elhalasztása után az operátor folytathatja a munkát a pénztában, és bármely műveletet végrehajthat, amihez nincs szükség a pénzügyi regisztrációra. Ha olyan esemény történik a pénztárban, amelyhez a pénzügyi regisztráció szükséges (például egy új tranzakciót nyitnak), a hibakezelési párbeszédpanel automatikusan megjelenik és értesíti az operátort, hogy a korábbi tranzakciót nem megfelelően regisztrálták, és hibakezelési lehetőségeket nyújt.
- **Kihagyás** – Az operátorok használhatják ezt a lehetőséget, amikor a pénzügyi regisztráció bizonyos feltételek fennállása esetén elhagyható, és az általános műveletek folytathatók a pénztárban. Ez a beállítás például használható, amikor egy értékesítési tranzakciót, amelynek a pénzügyi regisztrációja nem sikerült, a különleges papírnaplóban lehet regisztrálni.
- **Megjelölés regisztráltként** – Az operátorok használhatják ezt a lehetőséget, amikor a tranzakció ténylegesen regisztrálva van a pénzügyi eszközben (például egy pénzügyi nyugtát kinyomtattak), de hiba történt a pénzügyi válasz csatorna-adatbázisba mentése közben.
- **Elhalasztani** – Az üzemeltetők akkor használhatják ezt a lehetőséget, ha a tranzakciót nem regisztrálták, mert a regisztrációs szolgáltatás nem volt elérhető. 

> [!NOTE]
> A **Kihagyás**, **regisztráltként**, és **Elhalasztani** Az opciókat használatuk előtt aktiválni kell az adóregisztrációs folyamatban. Ezenkívül megfelelő engedélyt kell biztosítani az operátoroknak.

A **Kihagyás**, **regisztráltként**, és **Elhalasztani** Az opciók lehetővé teszik az információs kódok számára, hogy rögzítsenek bizonyos információkat a meghibásodásról, például a meghibásodás okát vagy az adóregisztráció kihagyásának indoklását vagy a tranzakció regisztráltként való megjelölését. Hibakezelési paraméterek beállításával kapcsolatos további tudnivalókat lásd: [Hibakezelési beállítások beállítása](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="optional-fiscal-registration"></a>Opcionális pénzügyi regisztráció

Pénzügyi regisztráció kötelező lehet az egyes műveletekhez, míg másoknál opcionális. Például előfordulhat, hogy a pénzügyi regisztráció normál értékesítések és visszáru esetében kötelező, de lehet, hogy a vevői letétekhez kapcsolódó műveletek pénzügyi regisztrációja nem kötelező. Ebben az esetben az eladás pénzügyi regisztrálásának elmulasztása blokkolja a további értékesítést, de a vevői letétet pénzügyi regisztrációjának elmulasztása nem akadályozza meg a további értékesítést. A kötelező és választható műveletek megkülönböztetéséhez ajánlott a különböző dokumentum szolgáltatókon keresztül kezelni azokat, és hogy külön lépéseket állítson be a pénzügyi regisztrációs folyamatban ezekhez a szolgáltatókhoz. A **Hiba esetén folytatás** paramétert engedélyezni kell minden lépéshez, amely kapcsolódik az opcionális pénzügyi regisztrációhoz. Hibakezelési paraméterek beállításával kapcsolatos további tudnivalókat lásd: [Hibakezelési beállítások beállítása](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="manually-rerun-fiscal-registration"></a>Futtassa újra a fiskális regisztrációt manuálisan

Ha egy tranzakció vagy esemény pénzügyi regisztrációja el lett halasztva egy hiba után (például akkor, ha a kezelő **Mégse** lehetőséget választotta hibakezelési párbeszédpanelen a), manuálisan újrafuttathatja a pénzügyi regisztrációt a hozzá tartozó művelet meghívásával. További részletekért lásd: [Elhalasztott pénzügyi regisztrációs manuális végrehajtásának engedélyezése](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).

### <a name="postpone-option"></a>Elhalasztási lehetőség

A **Elhalasztani** opció lehetővé teszi a fiskális regisztrációs folyamat folytatását, ha az aktuális lépés sikertelen. Akkor használható, ha van pénzügyi regisztrációs biztonsági mentési lehetőség.

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
> Az állapotfelmérés csak akkor fut le, ha az aktuális művelet adózási regisztrációt igényel, és ha a **Folytassa a hibával** paraméter le van tiltva az adóregisztrációs folyamat aktuális lépésében. További részletekért lásd: [Hibakezelés beállításainak megadása](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

## <a name="storing-fiscal-response-in-fiscal-transaction"></a>Pénzügyi válasz tárolása pénzügyi tranzakcióban

Ha egy tranzakció vagy esemény pénzügyi regisztrációja sikeres, a pénzügyi tranzakció létrejön a csatorna-adatbázisban, és az eredeti tranzakcióhoz vagy eseményhez kapcsolódik. Hasonlóképpen ha a **Kihagyás** vagy **Megjelölés regisztráltként** lehetőség ki van választva egy sikertelen pénzügyi regisztráció esetén, a pénzügyi tranzakció ezeket az adatokat tárolja. A pénzügyi tranzakció tárolja a pénzügyi eszköz vagy szolgáltatás pénzügyi válaszát. Ha a pénzügyi regisztrációs folyamat több lépésből áll, a sikeres vagy sikertelen regisztrációt eredményező folyamat minden egyes lépéséhez létrejön egy pénzügyi tranzakció.

A pénzügyi tranzakciókat a rendszer a Headquarters szolgáltatásba továbbítja a *P-feladat* segítségével, a tranzakciókkal együtt. A **Pénzügyi tranzakciók** gyorslapon az **Üzleti tranzakciók** oldalon belül megtekintheti azokat a pénzügyi tranzakciókat, amelyekhez tranzakciók kapcsolódnak.

A pénzügyi tranzakció tárolja a következő adatokat:

- Pénzügyi regisztrációs folyamat részletei (folyamat, csatlakozócsoport, csatlakozó stb). Szintén tárolja a pénzügyi eszköz sorozatszámát a **Pénztárgép száma** mezőben, ha ez az információ szerepel a pénzügyi válaszban.
- Az adóbejegyzés állapota: **Befejezve** a sikeres regisztrációhoz, **Kihagyva** ha az operátor a **Kihagyás** lehetőség sikertelen regisztráció esetén, **Regisztráltként megjelölve** ha az operátor a **Megjelölés regisztráltként** opció, ill **Elhalasztva** ha az operátor a **Elhalasztani** választási lehetőség.
- A kijelölt pénzügyi tranzakcióhoz kapcsolódó összes infókód-tranzakció. Az infokódos tranzakciók megtekintéséhez a **Fiskális tranzakciók** FastTab, válasszon ki egy pénzügyi tranzakciót, amelynek állapota: **Kihagyva**, **megjelölve**, vagy **Elhalasztva**, majd válassza ki **Info kódos tranzakciók**.

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

---
title: A Commerce-csatornák pénzügyi integrálásának áttekintése
description: Ez a témakör a Dynamics 365 Commerce szolgáltatásban rendelkezésre álló pénzügyi integrációs lehetőségekről ad áttekintést.
author: josaw
ms.date: 02/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: epopov
ms.search.validFrom: 2019-1-16
ms.dyn365.ops.version: 10
ms.openlocfilehash: 155056eb3a2acd0d66e0ace8d5558929678cb8e3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798781"
---
# <a name="overview-of-fiscal-integration-for-commerce-channels"></a>A Commerce-csatornák pénzügyi integrálásának áttekintése

[!include [banner](../includes/banner.md)]

## <a name="introduction"></a>Bevezetés

Ez a témakör a Dynamics 365 Commerce szolgáltatásban rendelkezésre álló pénzügyi integrációs lehetőségek áttekintése. A pénzügyi integráció tartalmazza a különböző pénzügyi eszközök és szolgáltatások integrációját, amelyek lehetővé teszik az értékesítések pénzügyi regisztrációját a helyi pénzügyi jogszabályokkal összhangban, amelyek célja az adócsalás megakadályozása a kiskereskedelmi iparágban. Alább láthatók olyan tipikus esetek, amelyek pénzügyi integrációval megoldhatók:

- Ertékesítés regisztrálása olyan pénzügyi eszközön, amely a pénztárhoz (POS) csatlakozik, például pénzügyi nyomtató, majd a pénzügyi nyugta nyomtatása a vevő számára.
- A Retail POS szolgáltatásban végrehajtott értékesítéshez és visszárukhoz kapcsolódó információk biztonságos elküldése külső webes szolgáltatásnak, amelyet az ahatóság üzemeltet.
- Segít az értékesítési tranzakcióadatok megmásíthatatlanságát digitális aláírások segítségével.

A pénzügyi integrációs funkció egy keretrendszer, amely közös megoldást kínál a Retail POS és a pénzügyi eszközök és szolgáltatások közti integráció továbbfejlesztésére és testreszabására. A funkció pénzügyi integráció mintákat is tartalmaz, amelyek támogatják az alapvető eseteket az adott országban vagy régiókban, és amelyek specifikus pénzügyi eszközökkel vagy szolgáltatásokkal működnek. Pénzügyi integráció minta a Commerce-összetevők számos kiterjesztését is tartalmazza, és szerepel a szoftverfejlesztő készletben (SDK). A pénzügyi integrációs sablonokkal kapcsolatos további tudnivalókat lásd: [Pénzügyi integrációs sablonok a Retail SDK-ban](#fiscal-integration-samples-in-the-retail-sdk). A Retail SDK telepítésével és használatával kapcsolatos tudnivalókat lásd: [Retail szoftverfejlesztői készlet (SDK) architektúrája](../dev-itpro/retail-sdk/retail-sdk-overview.md).

Az olyan helyzetek támogatásához, amelyeket nem támogat a pénzügyi integrációs minta, a Retail POS egyéb pénzügyi eszközökkel vagy szolgáltatásokkal való integrálásához, vagy a más országokban vagy régiókban levő követelmények lefedéséhez vagy ki kell terjesztenie a létező pénzügyi integrációs mintát, vagy új mintát kell létrehoznia egy meglévő minta példaként való használatával.

## <a name="fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices"></a>Pénzügyi regisztrációs folyamat és péntügyi integrációs minta pénzügyi eszközökhöz

A pénzügyi regisztrációs folyamat a Retail POS felületén egy vagy több lépésből állhat. Minden egyes lépés magában foglalja az adott tranzakciók vagy események pénzügyi regisztrációját egy pénzügyi eszközben vagy szolgáltatásban. A következő megoldás-összetevők részt vesznek a pénzügyi regisztrációban egy hardverállomáshoz kapcsolódó pénzügyi eszközben:

- A **Commerce runtime (CRT) kiterjesztése** – Ez az összetevő a tranzakció/esemény adatokat olyan formátumba alakítja, amelyet a pénzügyi eszközzel való együttműködéshez használnak, elemzi a pénzügyi eszköz válaszait, és tárolja a válaszokat a csatorna-adatbázisban. A kiterjesztés a regisztrálandó meghatározott tranzakciókat és eseményeket is meghatározza. Ezt az összetevőt gyakran nevezik *Pénzügyi dokumentumszolgáltatónak*.
- **Hardverállomás kiterjesztése** – Ez az összetevő a pénzügyi eszközzel kommunikációt indít, kéréseket és közvetlen parancsokat küld a pénzügyi eszköznek a tranzakció/esemény adatai alapján, amelyet a pénzügyi dokumentumból kivont, és válaszokat fogad a pénzügyi eszköztől. Ezt az összetevőt gyakran nevezik *Pénzügyi csatlakozónak*.

Egy pénzügyi eszköz pénzügyi integrációs mintája tartalmazza a CRT- és a hardverállomás-kiterjesztéseket egy pénzügyi dokumentumszolgáltatóra és egy pénzügyi csatlakozóra. A következő összetevő-konfigurációkat is tartalmazza:

- **Pénzügyi dokumentumszolgáltató konfigurációja** – Ez a beállítás meghatározza a pénzügyi dokumentumokhoz tartozó kimeneti módszert, valamint a formátumot. Az adatok hozzárendelését is tartalmazza az adókhoz és fizetési módokhoz, hogy a Retail POS adatai kompatibilisek legyenek a pénzügyi eszköz belső vezérlőprogramja által előre beállított értékekkel.
- **Pénzügyi csatlakozó konfigurációja** – Ez a beállítás határozza meg a fizikai kommunikációt az adott pénzügyi eszközzel.

Egy adott POS-pénztárgép pénzügyi regisztrációs folyamatát a pénztár funkcióprofiljának megfelelő beállítása határozza meg. A pénzügyi regisztrációs folyamat konfigurációjával, a pénzügyi dokumentumszolgáltató és pénzügyi csatlakozó konfigurációinak feltöltésével, és a paraméterek módosításával kapcsolatos további részletekért lásd: [Pénzügyi regisztrációs folyamat beállítása](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

A következő példa bemutatja a tipikus pénzügyi regisztrációs végrehajtási folyamatot egy pénzügyi eszközhöz. A folyamat a pénztárban történt eseménnyel kezdődik (például egy értékesítési tranzakció véglegesítése), és az alábbi lépéssorozatot hajtja végre:

1. A pénztár a CRT-ből pénzügyi bizonylatot kér.
2. A CRT határozza meg, hogy szükséges-e az aktuális eseményhez pénzügyi regisztráció.
3. A pénzügyi regisztrációs folyamat beállításainak megfelelően a CRT azonosít egy pénzügyi csatlakozót, és a hozzá tartozó pénzügyi dokumentumszolgáltatót, amelyet a pénzügyi nyilvántartáshoz használ majd.
4. A CRT futtatja a pénzügyi dokumentumszolgáltatót, amely egy pénzügyi dokumentumot hoz létre (például egy XML-dokumentumot), amely képviseli a tranzakciót vagy eseményt.
5. A pénztár elküldi a pénzügyi bizonylatot, amelyet a CRT előkészít a hardverállomás számára.
6. A hardverállomás lefuttatja a pénzügyi csatlakozót, amely feldolgozza a pénzügyi dokumentumot, és tájékoztatja a pénzügyi eszközt vagy szolgáltatást.
7. A pénztár elemzi a pénzügyi eszköz vagy szolgáltatás válaszát, és meghatározza, hogy sikeres volt-e a pénzügyi regisztráció.
8. A CRT elmenti a választ a csatorna-adatbázisba.

![Megoldási séma](media/emea-fiscal-integration-solution.png "Megoldási séma")

## <a name="error-handling"></a>Hibakezelés

A pénzügyi integrációs keretrendszer a hibák kezelésére a pénzügyi regisztráció során a következő lehetőségeket nyújtja:

- **Újrapróbálkozás** – Az operátorok használhatják ezt a lehetőséget, ha a hiba gyorsan feloldható, és a pénzügyi regisztrációt újrafuttathatja. Például ezt a lehetőséget használhatja, amikor a pénzügyi eszköz nincs csatlakoztatva, a pénzügyi nyomtatóból kifogyott a papír, vagy papírelakadás van a pénzügyi nyomtatóban.
- **Érvénytelenítés** – Ezzel a lehetőséggel az operátorok elhalaszthatják az aktuális tranzakció vagy esemény pénzügyi regisztrációját, ha sikertelen. A regisztráció elhalasztása után az operátor folytathatja a munkát a pénztában, és bármely műveletet végrehajthat, amihez nincs szükség a pénzügyi regisztrációra. Ha olyan esemény történik a pénztárban, amelyhez a pénzügyi regisztráció szükséges (például egy új tranzakciót nyitnak), a hibakezelési párbeszédpanel automatikusan megjelenik és értesíti az operátort, hogy a korábbi tranzakciót nem megfelelően regisztrálták, és hibakezelési lehetőségeket nyújt.
- **Kihagyás** – Az operátorok használhatják ezt a lehetőséget, amikor a pénzügyi regisztráció bizonyos feltételek fennállása esetén elhagyható, és az általános műveletek folytathatók a pénztárban. Ez a beállítás például használható, amikor egy értékesítési tranzakciót, amelynek a pénzügyi regisztrációja nem sikerült, a különleges papírnaplóban lehet regisztrálni.
- **Megjelölés regisztráltként** – Az operátorok használhatják ezt a lehetőséget, amikor a tranzakció ténylegesen regisztrálva van a pénzügyi eszközben (például egy pénzügyi nyugtát kinyomtattak), de hiba történt a pénzügyi válasz csatorna-adatbázisba mentése közben.

> [!NOTE]
> A **Kihagyás** és a **Megjelölés regisztráltként** beállításokat aktiválni kell a pénzügyi regisztrációs folyamatban a használatuk előtt. Ezenkívül megfelelő engedélyt kell biztosítani az operátoroknak.

A **Kihagyás** és **Megjelölés regisztráltként** beállítások lehetővé teszik az infókódok számára, hogy a hibával kapcsolatos meghatározott információkat rögzítsenek, például a hiba okát vagy a pénzügyi regisztráció kihagyásának indoklását, vagy a tranzakció regisztráltként való megjelölését. Hibakezelési paraméterek beállításával kapcsolatos további tudnivalókat lásd: [Hibakezelési beállítások beállítása](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="optional-fiscal-registration"></a>Opcionális pénzügyi regisztráció

Pénzügyi regisztráció kötelező lehet az egyes műveletekhez, míg másoknál opcionális. Például előfordulhat, hogy a pénzügyi regisztráció normál értékesítések és visszáru esetében kötelező, de lehet, hogy a vevői letétekhez kapcsolódó műveletek pénzügyi regisztrációja nem kötelező. Ebben az esetben az eladás pénzügyi regisztrálásának elmulasztása blokkolja a további értékesítést, de a vevői letétet pénzügyi regisztrációjának elmulasztása nem akadályozza meg a további értékesítést. A kötelező és választható műveletek megkülönböztetéséhez ajánlott a különböző dokumentum szolgáltatókon keresztül kezelni azokat, és hogy külön lépéseket állítson be a pénzügyi regisztrációs folyamatban ezekhez a szolgáltatókhoz. A **Hiba esetén folytatás** paramétert engedélyezni kell minden lépéshez, amely kapcsolódik az opcionális pénzügyi regisztrációhoz. Hibakezelési paraméterek beállításával kapcsolatos további tudnivalókat lásd: [Hibakezelési beállítások beállítása](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="manually-running-fiscal-registration"></a>Pénzügyi regisztráció manuális futtatása

Ha egy tranzakció vagy esemény pénzügyi regisztrációja el lett halasztva egy hiba után (például akkor, ha a kezelő **Mégse** lehetőséget választotta hibakezelési párbeszédpanelen a), manuálisan újrafuttathatja a pénzügyi regisztrációt a hozzá tartozó művelet meghívásával. További részletekért lásd: [Elhalasztott pénzügyi regisztrációs manuális végrehajtásának engedélyezése](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).

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
> Az állapotellenőrzés futtatása csak akkor történik meg, ha az aktuális művelethez pénzügyi regisztráció szükséges, és a **Hiba esetén folytatás** paraméter a pénzügyi regisztráció aktuális lépéséhez le van tiltva. További részletekért lásd: [Hibakezelés beállításainak megadása](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

## <a name="storing-fiscal-response-in-fiscal-transaction"></a>Pénzügyi válasz tárolása pénzügyi tranzakcióban

Ha egy tranzakció vagy esemény pénzügyi regisztrációja sikeres, a pénzügyi tranzakció létrejön a csatorna-adatbázisban, és az eredeti tranzakcióhoz vagy eseményhez kapcsolódik. Hasonlóképpen ha a **Kihagyás** vagy **Megjelölés regisztráltként** lehetőség ki van választva egy sikertelen pénzügyi regisztráció esetén, a pénzügyi tranzakció ezeket az adatokat tárolja. A pénzügyi tranzakció tárolja a pénzügyi eszköz vagy szolgáltatás pénzügyi válaszát. Ha a pénzügyi regisztrációs folyamat több lépésből áll, a sikeres vagy sikertelen regisztrációt eredményező folyamat minden egyes lépéséhez létrejön egy pénzügyi tranzakció.

A pénzügyi tranzakciókat a rendszer a Headquarters szolgáltatásba továbbítja a *P-feladat* segítségével, a tranzakciókkal együtt. A **Pénzügyi tranzakciók** gyorslapon az **Üzleti tranzakciók** oldalon belül megtekintheti azokat a pénzügyi tranzakciókat, amelyekhez tranzakciók kapcsolódnak.

A pénzügyi tranzakció tárolja a következő adatokat:

- Pénzügyi regisztrációs folyamat részletei (folyamat, csatlakozócsoport, csatlakozó stb). Szintén tárolja a pénzügyi eszköz sorozatszámát a **Pénztárgép száma** mezőben, ha ez az információ szerepel a pénzügyi válaszban.
- A pénzügyi regisztráció állapota: **Kész** sikeres regisztráció esetén, **Kihagyva**, ha az operátor a **Kihagyás** lehetőséget választotta egy sikertelen regisztráció esetén, vagy **Megjelölve regisztráltként**, ha az operátor bejelölte a **Megjelölés regisztráltként** lehetőséget.
- A kijelölt pénzügyi tranzakcióhoz kapcsolódó összes infókód-tranzakció. Az Infókód-tranzakciók megtekintéséhez a **Pénzügyi tranzakciók** gyorslapon válasszon egy olyan pénzügyi tranzakciót, amelynek állapota **Kihagyva** vagy **Megjelölve regisztráltként**, majd válassza ki **Infókód-tranzakciók** elemet.

## <a name="fiscal-texts-for-discounts"></a>Pénzügyi szövegek engedményekhez

Egyes országokban vagy régiókban különleges követelmények vannak érvényben a további szövegekkel kapcsolatban, amelyeket a pénzügyi nyugtára kell nyomtatni, amikor különböző engedményeket alkalmaznak. A pénzügyi integráció funkció segítségével beállíthat egy speciális szöveget az engedményhez, amelyet az engedmény sora után a pénzügyi nyugtára nyomtat. Manuális engedmények esetén, konfigurálhatja az infókódhoz megadott pénzügyi szöveget, amelyhez az infókód a **Termék engedménye** infókódként van megadva a pénztár funkcióprofilján. A pénzügyi szövegek engedményekhez való beállításával kapcsolatos további tudnivalókat lásd: [Pénzügyi szövegek beállítása engedményekhez](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-texts-for-discounts).

## <a name="printing-fiscal-x-and-fiscal-z-reports"></a>Pénzügyi X- és pénzügyi Z-jelentések nyomtatása

A pénzügyi integráció funkció támogatja az integrált pénzügyi eszköz vagy szolgáltatásra vonatkozóan egyedi napzáró kimutatások generálását:

- A megfelelő műveletek futtatására használatos új gombokat a pénztár képernyő-elrendezésén kell hozzáadni. További részletekért lásd: [Pénzügyi X/Z jelentések beállítása a pénztárból](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
- A pénzügyi integrációs mintában ezeket a műveleteket meg kell feleltetni a pénzügyi eszköz megfelelő műveleteivel.

## <a name="fiscal-integration-samples-in-the-retail-sdk"></a>Pénzügyi integrációs minták a Retail szoftverfejlesztői készletben (SDK)

A Retail SDK-ban jelenleg a következő pénzügyi integráció minták érhetők el:

- [Adóügyi nyomtató integrációját bemutató minta Olaszországra vonatkozóan](emea-ita-fpi-sample.md)
- [Adóügyi nyomtató integrációját bemutató minta Lengyelországra vonatkozóan](emea-pol-fpi-sample.md)
- [Adóügyi regisztrációs szolgáltatás integrációját bemutató minta Ausztriára vonatkozóan](emea-aut-fi-sample.md)
- [Adóügyi regisztrációs szolgáltatás integrációját bemutató minta Csehországra vonatkozóan](emea-cze-fi-sample.md)
- [Ellenőrzőegység integrációs mintája Svédország esetén](./emea-swe-fi-sample.md)
- [Adóügyi regisztrációs szolgáltatás integrációját bemutató minta Németországra vonatkozóan](./emea-deu-fi-sample.md)

A következő pénzügyi integrációs funkció szintén elérhető a Retail SDK-ban, de jelenleg használja ki a pénzügyi integrációs keretrendszer előnyeit. Ennek a funkciónak az áttelepítése a pénzügyi integrációs keretrendszerbe a későbbi frissítésekben tervezett.


- [Digitális aláírás Franciaország esetén](emea-fra-cash-registers.md)
- [Digitális aláírás Norvégia esetén](emea-nor-cash-registers.md)

A Retail SDK csomagban elérhető alábbi örökölt pénzügyi integrációs funkciók nem használják a pénzügyi integrációs keretrendszert, és a későbbi frissítésekkel elavulttá válnak:

- [Ellenőrzőegység integrációs mintája Svédország esetén (örökölt)](./retail-sdk-control-unit-sample.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
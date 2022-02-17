---
title: A Commerce csatornák pénzügyi integrálásának beállítása
description: Ez a témakör bemutatja, hogyan állíthatja be a pénzügyi integráció funkciót a Commerce csatornákhoz.
author: EvgenyPopovMBS
ms.date: 01/31/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: fd37934e1ebd103d66c5181e0bfb75047f4cb6a3
ms.sourcegitcommit: 5cefe7d2a71c6f220190afc3293e33e2b9119685
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2022
ms.locfileid: "8076963"
---
# <a name="set-up-the-fiscal-integration-for-commerce-channels"></a>A Commerce csatornák pénzügyi integrálásának beállítása

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Ez a témakör bemutatja, hogyan állíthatja be a pénzügyi integráció funkciót a Commerce csatornákhoz. A pénzügyi integráció kapcsolatos további tudnivalókat lásd: [A pénzügyi integráció áttekintése a Commerce csatornákhoz](fiscal-integration-for-retail-channel.md).

## <a name="set-up-commerce-parameters"></a>Állítsa be a Kereskedelmi paramétereket

1. A **Commerce megosztott paraméterek** oldalon, az **Általános** lapon a **Pénzügyi integráció engedélyezése** lehetőséget állítsa **Igen** értékre.
1. A **Számsorozatok** lapon határozza meg az alábbi hivatkozások számsorozatkódját:

    - Pénzügyi technikai profil száma
    - Pénzügyi csatlakozócsoport száma
    - Regisztrációs folyamat száma

1. A számsorozatot határozza meg a **Commerce paraméterek** lapon a pénzügyi funkcionális profilszám számára.

    > [!NOTE]
    > Számsorozatok megadása nem kötelező. Pénzügyi integráció entitásokhoz számok számsorozatokkal vagy manuálisan hozhatók létre.

## <a name="set-up-a-fiscal-registration-process"></a>A pénzügyi regisztrációs folyamat beállítása

A pénzügyi integráció beállításának folyamata a következő általános műveleteket tartalmazza:

- Állítsa be a pénzügyi csatlakozókat, amelyek megjelenítik pénzügyi eszközöket és a szolgáltatásokat, amelyek a pénzügyi nyilvántartásokhoz használatosak például a pénzügyi nyomtatókat.
- A dokumentum-szolgáltatók konfigurálása, amelyek pénzügyi dokumentumokat hoznak létre, amelyeket a pénzügyicsatlakozók regisztrálnak a pénzügyi eszközökbe vagy szolgáltatásokba.
- Állítsa be a pénzügyi regisztrációs folyamatot, amely meghatározza a pénzügyi regisztrációs lépéseket, valamint a pénzügyi csatlakozókat és a pénzügyi dokumentumszolgáltatókat, amelyeket az egyes lépésekhez lesznek használva.
- A pénztári (POS) funkcióprofilokhoz rendelje hozzá a pénzügyi regisztrációs eljárásokat.
- Csatlakozó technikai profilok hozzárendelése a hardverprofilokhoz.

### <a name="upload-configurations-of-fiscal-document-providers"></a>Töltse fel az adódokumentum-szolgáltatók konfigurációit

A pénzügyi bizonylatszolgáltató felelős a pénzügyi bizonylatok generálásáért, amelyek megfelelnek a pénztárban regisztrált pénzügyi tranzakcióknak és eseményeknek, olyan formátumban, amely felhasználható pénzügyi eszközzel vagy szolgáltatással is az interakcióhoz. Például egy pénzügyi bizonylatszolgáltató létrehozhat egy pénzügyi nyugtát XML-formátumban.

Az adódokumentum-szolgáltatók konfigurációinak feltöltéséhez kövesse az alábbi lépéseket.

1. A Kereskedelmi központban nyissa meg a **Fiskális dokumentumszolgáltatók** oldal (**Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Fiskális integráció \> Fiskális dokumentumszolgáltatók**).
1. Töltse fel az XML-konfigurációt minden egyes használni kívánt eszközhöz vagy szolgáltatáshoz.

> [!TIP]
> A **Nézet** kiválasztásával, meg lehet tekinteni minden funkcionális és technikai profilt, amelyek az aktuális dokumentumszolgáltatóhoz kapcsolódnak.

> [!NOTE]
> Az adatleképezést egy pénzügyi bizonylat szolgáltató részének kell tekinteni. Azonos összekötőhöz különböző adatleképezések beállításához (például államspecifikus előírások) eltérő pénzügyi bizonylat szolgáltatókat kell létrehozni.

### <a name="upload-configurations-of-fiscal-connectors"></a>Fiskális csatlakozók konfigurációinak feltöltése

A pénzügyi csatlakozó felelős a kommunikációért a pénzügyi eszközzel vagy szolgáltatással. Például egy pénzügyi csatlakozó elküldhet egy XML-formátumban létrehozott pénzügyi nyugtát, amelyet egy pénzügyi dokumentumszolgáltató hozott létre egy pénzügyi nyomtatónak. A fiskális integrációs összetevőkről további részletekért lásd: [Fiskális regisztrációs folyamat és fiskális integrációs minták a fiskális eszközökhöz és szolgáltatásokhoz](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

Kövesse az alábbi lépéseket az adóösszekötők konfigurációinak feltöltéséhez.

1. A Kereskedelmi központban nyissa meg a **Pénzügyi csatlakozók** oldal (**Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Fiskális integráció \> Pénzügyi csatlakozók**).
1. Töltsön fel XML-konfigurációt minden olyan eszközhöz vagy szolgáltatáshoz, amelyet fiskális integrációs célokra kíván használni.

> [!TIP]
> A **Nézet** kiválasztásával, meg lehet tekinteni minden funkcionális és technikai profilt, amelyek az aktuális pénzügyi csatlakozóhoz kapcsolódnak.

A fiskális csatlakozók és a fiskális dokumentumszolgáltatók konfigurációira vonatkozó példákért lásd: [Fiskális integrációs minták a Commerce SDK-ban](fiscal-integration-for-retail-channel.md#fiscal-integration-samples-in-the-commerce-sdk).

### <a name="create-connector-functional-profiles"></a>Csatlakozó funkcionális profilok létrehozása

Csatlakozó funkcionális profilok létrehozásához kövesse az alábbi lépéseket.

1. A Kereskedelmi központban nyissa meg a **Csatlakozók funkcionális profiljai** oldal (**Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Fiskális integráció \> Csatlakozók funkcionális profiljai**).
1. A pénzügyi összekötő és a pénzügyi dokumentum-szolgáltató minden egyes, ehhez a pénzügyi összekötőhöz kapcsolódó kombinációjához hozzon létre egy összekötő funkcionális profilt az alábbi lépések végrehajtásával:

    1. Válasszon ki egy összekötőnevet.
    1. Válasszon ki egy bizonylatszolgáltatót.

#### <a name="change-data-mapping-parameters-in-a-connector-functional-profile"></a>Adatleképezési paraméterek módosítása egy összekötő működési profiljában

Az adatok hozzárendelésének paramétereit a csatlakozó működési profiljában módosíthatja. Az alábbi táblázat néhány példát mutat be az adatleképezési paraméterekre az összekötő működési profiljában.

| Paraméter | Formátum | Példa |
|-----------|--------|---------|
| Áfaszázalékok beállítása | value : VATrate | 1 : 2000, 2 : 1800 |
| Áfakódok leképezése | VATcode : value | vat20 : 1, vat18 : 2 |
| Fizetőeszköz-típusok leképezése | TenderType : érték | Cash : 1, Card : 2 |

Az adódokumentum-szolgáltató konfigurációjában meghatározott alapértelmezett paraméterek visszaállításához válassza a lehetőséget **Frissítés** a **Csatlakozók funkcionális profiljai** oldalon.

> [!NOTE]
> Csatlakoztató működési profilok vállalatspecifikusak. Ha a pénzügyi összekötő és a pénzügyi bizonylat-szolgáltató ugyanazt a kombinációját tervezi használni különböző vállalatok számára, akkor minden vállalathoz létre kell hoznia egy összekötő funkcionális profilt.

### <a name="create-connector-technical-profiles"></a>Csatlakozó műszaki profilok létrehozása

Csatlakozási technikai profilok létrehozásához kövesse az alábbi lépéseket.

1. A Kereskedelmi központban nyissa meg a **Csatlakozók műszaki profiljai** oldal (**Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Fiskális integráció \> Csatlakozók műszaki profiljai**).
1. Hozzon létre egy csatlakozási technikai profilt minden egyes pénzügyi csatlakozóhoz az alábbi lépések végrehajtásával:

    1. Válasszon ki egy összekötőnevet.
    1. Válassza ki a csatlakozó típusát:

        - Hardverállomáshoz csatlakoztatott vagy a helyi hálózatban jelen lévő eszközök vagy szolgáltatások esetén válassza a lehetőséget **Helyi**.
        - Külső szolgáltatások esetén válassza a lehetőséget **Külső**.
        - A Commerce futtatókörnyezet belső csatlakozóihoz (CRT), válassza ki **Belső**. 

    1. Válassza ki a csatlakozó helyét:

        - Ha a csatlakozó a Hardver állomáson található, válassza a lehetőséget **Hardver állomás**.
        - Ha a csatlakozó a POS-regiszterben található, válassza a lehetőséget **Regisztráció**.

A paraméterek az **Eszköz** és **Beállítások** lapokon a csatlakozó műszaki profiljában módosíthatók. A pénzügyi csatlakozó konfigurációjában meghatározott alapértelmezett paraméterek visszaállításához válassza a **Frissítés** lehetőséget. Az XML-konfiguráció új verziójának betöltése közben egy üzenetet fog kapni, amely kijelenti, hogy a jelenlegi pénzügyi összekötő vagy adódokumentum-szolgáltató már használatban van. Ezzel az eljárással nem bírálja felül a manuális módosításokat, amelyeket korábban elvégzett a csatlakozó funkcionális profiljain és a csatlakozó műszaki profiljain. Az új konfiguráció alapértelmezett paraméterkészletének alkalmazásához válassza a lehetőséget **Frissítés** vagy a **Csatlakozók funkcionális profiljai** oldal vagy a **Csatlakozók műszaki profiljai** oldalon.

Ha konkrét paramétereket kell beállítania egy egyedi POS-regiszterhez vagy tárolóhoz, kövesse az alábbi lépéseket.

1. Válaszd ki a **Felülbírálás** menü tétel.
1. A **Felülbírálás** oldalon, hozzon létre egy új rekordot.
1. Válasszon egy üzletet vagy egy POS-nyilvántartást. Felülbírálhatja a kiválasztott műszaki profil paramétereit egy egyedi POS-regiszterhez vagy az összes POS-regiszterhez az egyes üzletekben.
1. A **Eszköz** lapon adja meg a kiválasztott POS-regiszter vagy tároló paramétereit.

### <a name="create-fiscal-connector-groups"></a>Fiskális csatlakozási csoportok létrehozása

A pénzügyi csatlakozócsoport azonos funkciókat végrehajtó, és a pénzügyi regisztrációs folyamat azonos szakaszában használt pénzügyi csatlakozókat kombinál. Például, ha több pénzügyi nyomtató modellt használnak üzletekben, azon pénzügyi nyomtatók pénzügyi csatlakozói egy csatlakozócsoportba kombinálhatók.

Kövesse az alábbi lépéseket egy adóösszekötő csoport létrehozásához.

1. Menj a **Pénzügyi összekötő csoport** oldal (**Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Fiskális integráció \> Fiskális összekötő csoportok**).
1. Hozzon létre egy új pénzügyi csatlakozási csoportot.
1. Működési profilok hozzáadása az összekötőcsoporthoz. A **Funkcionális profilok** lapon válassza a **Hozzáadás** lehetőséget, és válasszon egy profilszámot. Egy csatlakozócsoportban minden egyes fiskális csatlakozónak csak egy funkcionális profilja lehet.
1. A működési profil használatának felfüggesztéséhez, a **Letiltás** beállítása legyen **Igen**. Ez a módosítás csak az aktuális csatlakozócsoportot érinti. Ugyanazt a funkcionális profilt az egyéb csatlakozócsoportokban továbbra is használhatja.

### <a name="create-a-fiscal-registration-process"></a>Adóügyi regisztrációs folyamat létrehozása

A pénzügyi regisztrációs folyamatot a regisztrációs lépések sorrendje, és az egyes lépéseknél használt összekötőcsoport határozza meg.

Adóügyi regisztrációs folyamat létrehozásához kövesse az alábbi lépéseket.

1. A Kereskedelmi központban nyissa meg a **Adóügyi regisztrációs folyamat** oldal (**Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Fiskális integráció \> Adóügyi regisztrációs folyamatok**).
1. Hozzon létre egy új rekordot minden egyedi adóregisztrációs folyamathoz.
1. Adja hozzá a regisztrációs lépéseket a folyamathoz az alábbi lépésekkel:

    1. Válassza a **Hozzáadás** lehetőséget.
    1. Válasszon ki egy pénzügyi csatlakozó típust.
    1. A **Csoportszám** mezőben, válasszon ki egy megfelelő pénzügyi csatlakozócsoportot.

### <a name="assign-entities-of-the-fiscal-registration-process-to-pos-profiles"></a>Rendelje hozzá az adóregisztrációs folyamat entitásait a POS-profilokhoz

Az adóregisztrációs folyamat entitásainak POS-profilokhoz rendeléséhez kövesse az alábbi lépéseket.

1. A Kereskedelmi központban nyissa meg a **POS funkcióprofilok** oldal (**Kiskereskedelem és kereskedelem \> Csatorna beállítása \> POS beállítása \> POS profilok \> Funkcionalitási profilok**). 
1. Rendelje hozzá az adóregisztrációs folyamatot egy POS funkcióprofilhoz.
1. Válassza ki a **Szerkesztés** lehetőséget, majd a **Pénzügyi regisztrációs folyamat** lapon a **Feldolgozás száma** mezőben, válasszon ki egy folyamatot.
1. Menj a **POS hardverprofil** oldal (**Kiskereskedelem és kereskedelem \> Csatorna beállítása \> POS beállítása \> POS profilok \> Hardverprofilok**).
1. Csatlakozó műszaki profilok hozzárendelése egy hardverprofilhoz. 
1. Válassza ki **Szerkesztés**, majd a **Fiskális perifériák** fület, adjon hozzá egy sort. 
1. Ban,-ben **Profilszám** mezőben válassza ki a csatlakozó műszaki profilját.

> [!NOTE]
> Egy hardverprofilhoz több műszaki profilt adhat hozzá. Azonban a hardverprofil vagy a POS funkcióprofil csak egy helyen találkozhat bármelyik pénzügyi csatlakozóprofillal.

A fiskális regisztrációs folyamatot a fiskális regisztrációs folyamat, valamint a fiskális integrációs összetevők néhány paramétere határozza meg:CRT kiterjesztés az adódokumentum szolgáltatóhoz és a Hardver állomás bővítmény a pénzügyi csatlakozóhoz.

- A feliratkozások a pénzügyi regisztráció eseményeire és tranzakcióira a pénzügyi dokumentumszolgáltatóban vannak előre meghatározva.
- A pénzügyi bizonylat szolgáltató feladata továbbá a pénzügyi regisztrációhoz használt pénzügyi csatlakozó azonosítása. Ez illeszkedik a csatlakozó funkcionális profiljaihoz, amelyek szerepelnek a pénzügyi csatlakozócsoportban, amely meg van adva az aktuális lépéshez a pénzügyi regisztrációs folyamatban azzal a műszaki profillal, amely hozzá van rendelve annak a Hardverállomásnak a hardverprofiljához, amellyel a pénztár párosítva van.
- A pénzügyi bizonylat szolgáltató a pénzügyi dokumentumszolgáltató adattérképezési beállításait használja az olyan tranzakció-/eseményadatok átviteléhez, mint az adók és kifizetések, a pénzügyi dokumentum generálása során.
- Amikor pénzügyi dokumentumszolgáltató pénzügyi dokumentum hoz létre, a pénzügyi csatlakozó elküldheti azt változatlanul a pénzügyi eszköznek, vagy elemezheti és átalakíthatja azt parancssorozattá a alkalmazásprogramozási felület (API) számára, attól függően, hogy hogyan történik a kommunikáció kezelése.

### <a name="validate-the-fiscal-registration-process"></a>Érvényesítse a fiskális regisztrációs folyamatot

Javasoljuk, hogy az alábbi esetekben érvényesítse a fiskális regisztrációs folyamatot:

- Elvégezte az új regisztrációs folyamat összes beállítását. Ezek a beállítások magukban foglalják a regisztrációs folyamatok hozzárendelését a POS funkcióprofilokhoz és a hardverprofilokhoz.
- Módosított egy meglévő adóregisztrációs folyamatot, és ezek a módosítások azt eredményezhetik, hogy a rendszer futás közben egy másik pénzügyi csatlakozási szoftvert választ ki. (Például módosította a csatlakozási csoportot egy adóregisztrációs folyamat lépéséhez, engedélyezte az összekötő működési profilját egy csatlakozási csoportban, vagy új csatlakozási funkcióprofilt adott hozzá egy csatlakozási csoporthoz.)
- Módosította a csatlakozó műszaki profilok hardverprofilokhoz való hozzárendelését.

A fiskális regisztrációs folyamat érvényesítéséhez kövesse az alábbi lépéseket.

1. A Kereskedelmi központban nyissa meg a **Adóügyi regisztrációs folyamat** oldal (**Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Fiskális integráció \> Adóügyi regisztrációs folyamatok**).
1. Válassza ki **Érvényesít** a fiskális regisztrációs folyamat érvényesítéséhez.
1. Az **Elosztási ütemezés** lapon, futtassa a **1070** és **1090** feladatokat az adatok átviteléhez a csatorna-adatbázisba.

## <a name="set-up-fiscal-texts-for-discounts"></a>Pénzügyi szövegek beállítása engedményekhez

Bizonyos esetekben különleges szöveget nyomtatni egy pénzügyi nyugtára engedmény alkalmazása esetén. A kedvezményekhez tartozó pénzügyi szövegeket a **Pénzügyi csatlakozócsoport** lapon (**Retail és Commerce \> Csatorna beállításai \> Pénzügyi integráció \> Pénzügyi csatlakozócsoportok**) állíthatja be.

- A pénztárhoz alkalmazott manuális engedmények esetén, konfigurálja az infókódhoz vagy kódcsoporthoz megadott pénzügyi szöveget, amelyhez az infókód a **Termék engedménye** infókódként van megadva a pénztár funkcióprofilján.

    1. A **Pénzügyi csatlakozócsoport** oldalon válassza **A pénzügyi nyugta szövege** lehetőséget.
    1. Az **Infókódok** lapon jelölje be a **Hozzáadás** lehetőséget, és válassza ki az infókódot vagy infókódcsoportot.
    1. Az **Info kódszám** mezőben válasszon ki egy értéket.
    1. Az **Alkód száma** mezőben válasszon ki egy értéket, ha a kiválasztott infókódhoz szükséges alkód.
    1. A **Pénzügyi nyugta szövege** mezőben adja meg a pénzügyi szöveget, amelyet a pénzügyi nyugtára kell nyomtatni.
    1. Állítsa a **Felhasználói adatbevitel nyomtatása a pénzügyi nyugtára** lehetőséget **Igen** értékre, ha felül szeretné bírálni a szöveget egy pénzügyi nyugtán azzal, amit a felhasználó manuálisan megad a pénztárban. Ezt a lehetőséget csak azon infókódokra vonatkozik, amelyeknél van **Szöveg** bemenettípus.

    > [!NOTE]
    > Több infókódhoz is meghatározhat pénzügyi szöveget, így kezelhetők olyan helyzetek, ahol több infókódcsoportot, kapcsolt infókódokat és kiváltott infókódokat használnak. Ilyen esetekben a pénzügyi nyugta az összes infókódból származó szöveget tartalmazza, amelyek kapcsova vannak ahhoz a tranzakciós sorhoz, ahol a kedvezmény alkalmazva lett.

- Csatornaspecifikus engedményekhez az engedmény azonosítójában kell meghatározni a pénzügyi szöveget.

    1. A **Pénzügyi csatlakozócsoport** oldalon válassza **A pénzügyi nyugta szövege** lehetőséget.
    1. Az **Engedmények** lapon válassza a **Hozzáadás** lehetőséget, és válasszon egy engedmény-azonosítót.
    1. A **Pénzügyi nyugta szövege** mezőben adja meg a pénzügyi szöveget, amelyet a pénzügyi nyugtára kell nyomtatni.

    > [!NOTE]
    > Több engedmény alkalmazása esetén ugyanazon tranzakciósorhoz, a pénzügyi nyugta tartalmazza a pénzügyi szövegeket minden engedményből, amelyek kapcsolva vannak ahhoz a tranzakciós sorhoz.

## <a name="set-error-handling-settings"></a>Hibakezelés beállításainak megadása

A hibakezelési beállításokat, amelyek elérhetők a pénzügyi integrációban a pénzügyi regisztrációs folyamatban állítják be. A pénzügyi integrációban történő hibakezeléssel kapcsolatos további tudnivalókat lásd: [Hibakezelés](fiscal-integration-for-retail-channel.md#error-handling).

A hibakezelési beállítások megadásához kövesse az alábbi lépéseket.

1. A **Pénzügyi regisztrációs folyamat** oldalon (**Retail és Commerce \> Csatorna beállítása \> Pénzügyi integráció \> Pénzügyi regisztrációs eljárások**) a következő paramétereket állíthatja be a pénzügyi regisztrációs folyamat egyes lépéseihez:

    - **Kihagyás engedélyezése** – Ez a paraméter engedélyezi a **Kihagyás** lehetőséget a hibakezelés párbeszédpanelen.
    - **Regisztráltnak megjelölés engedélyezése** – Ez a paraméter bekapcsolja a **Megjelölése a regisztráltként** lehetőséget a hibakeresés párbeszédablakában.
    - **Halasztás engedélyezése** – Ez a paraméter lehetővé teszi a **Elhalasztani** opciót a hibakezelési párbeszédpanelen.
    - **Hiba esetén folytatás** – Ha ez a paraméter engedélyezve van, a pénzügyi regisztrációs folyamat folytatódhat a pénztárgépen, Ha egy tranzakciós esemény pénzügyi regisztrációja sikertelen. Ellenkező esetben a következő esemény vagy tranzakció pénzügyi regisztrációjának futtatásához, a kezelőnek kell újra kell próbálnia a sikertelen pénzügyi regisztrációt, ki kell hagynia vagy meg kell jelölnie a tranzakciót vagy esemény regisztráltként. További tudnivalókért lásd: [Opcionális pénzügyi regisztráció](fiscal-integration-for-retail-channel.md#optional-fiscal-registration).

    > [!NOTE]
    > Ha a **Hiba esetén folytatás** paraméter engedélyezve van, a **Kihagyása engedélyezése** és **Regisztráltnak megjelölés engedélyezése** paraméterek automatikusan le lesznek tiltva.

1. A **Kihagyás** és **Megjelölés regisztráltként** A hibakezelési párbeszédpanel beállításai megkövetelik, hogy a **Engedélyezze a regisztráció kihagyását vagy jelölje meg regisztráltként** engedélyt engedélyezni kell. Az engedély engedélyezéséhez lépjen a **Engedélycsoportok** oldal (**Kiskereskedelem és kereskedelem \> Alkalmazottak \> Engedélycsoportok**), és állítsa be a **Engedélyezze a regisztráció kihagyását vagy jelölje meg regisztráltként** opciót **Igen**.
1. A **Elhalasztani** opció a hibakezelési párbeszédpanelen megköveteli, hogy a **Halasztás engedélyezése** engedélyt engedélyezni kell. Az engedély engedélyezéséhez lépjen a **Engedélycsoportok** oldal (**Kiskereskedelem és kereskedelem \> Alkalmazottak \> Engedélycsoportok**), és állítsa be a **Halasztás engedélyezése** opciót **Igen**.
1. A **Kihagyás**, **regisztráltként**, és **Elhalasztani** Az opciók segítségével az üzemeltetők további információkat adhatnak meg, ha az adóregisztráció sikertelen. A funkció elérhetővé tételéhez meg kell adnia a **Kihagyás**, **regisztráltként**, és **Elhalasztani** információs kódok egy fiskális csatlakozási csoporton. A kezelők által megadott információk infókód-tranzakcióként lesznek mentve, amely a pénzügyi tranzakcióhoz van kapcsolva. Infókódokkal kapcsolatos további tudnivalókat lásd: [Infókódok és infókódcsoportok](../info-codes-retail.md).

    > [!NOTE]
    > A **Termék** funkció aktiválása nem támogatott azon infókódok esetében, amelyek a **Kihagyás** és **Megjelölés a regisztráltként** funkciókhoz használatosak a pénzügyi csatlakozócsoportokban.

    - A **Pénzügyi összekötő csoport** oldalon, a **Info kódok** lapon válassza ki az információs kódokat vagy az információs kódcsoportokat **Kihagyás**, **regisztráltként**, és **Elhalasztani** mezőket.

    > [!NOTE]
    > A pénzügyi regisztrációs folyamat minden lépésben egy pénzügyi és egy nem pénzügyi dokumentum hozható létre. A pénzügyi dokumentumszolgáltató bővítmény minden pénzügyi vagy a nem pénzügyi dokumentumokkal kapcsolatos tranzakció vagy esemény típusát azonosítja. A hibakezelési funkció csak a pénzügyi dokumentumokra vonatkozik.
    >
    > - **Pénzügyi dokumentum** – Kötelező dokumentum, amelyet sikeresen kell regisztrálni (például egy pénzügyi nyugta).
    > - **Nem pénzügyi dokumentum** – a tranzakció vagy esemény kiegészítő dokumentuma (például ajándékkártya-bizonylat).

1. Ha az operátornak képesnek kell lennie az aktuális művelet folytatására (például tranzakció létrehozása vagy véglegesítése) az állapotellenőrzési hiba után, engedélyezze a **Állapotellenőrzési hiba kihagyásának engedélyezése** engedélyt az **Engedélycsoportok** lapon (**Retail és Commerce \> Alkalmazottak \> Engedélycsoportok**). Az állapotellenőrzési eljárással kapcsolatos további tudnivalókat lásd: [Pénzügyi regisztráció állapotának ellenőrzése](fiscal-integration-for-retail-channel.md#fiscal-registration-health-check).

## <a name="set-up-fiscal-xz-reports-from-the-pos"></a>Pénzügyi X / Z-jelentések beállítása a pénztárból

Ahhoz, hogy pénzügyi X / Z-jelentés futtatását engedélyezze a pénztárból új gombokat kell hozzáadni a pénztár elrendezéséhez.

- A **Gombrácsok** oldalon hajtsa végre az [Pénztárműveletek hozzáadása pénztárelrendezésekhez a Gombrácstervezővel](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters) dokumentum lépéseit, a tervező telepítéséhez és a pénztár elrendezésének frissítéséhez.

    1. A frissítendő elrendezés kiválasztása. 
    1. Adja hozzá az új gombot, és és állítsa a **Pénzügyi X nyomtatása** gombtulajdonságot
    1. Adja hozzá az új gombot, és és állítsa a **Pénzügyi Z nyomtatása** gombtulajdonságot
    1. Az **Elosztási ütemezés** lapon, futtassa a **1090** feladatot a módosítások átviteléhez a csatorna-adatbázisba.

## <a name="enable-manual-execution-of-postponed-fiscal-registration"></a>Elhalasztott pénzügyi regisztrációs manuális végrehajtásának engedélyezése.

Az halasztott pénzügyi regisztráció kézi végrehajtásának engedélyezéséhez, egy új gombot kell hozzáadnia a pénztár elrendezéséhez.

- A **Gombrácsok** oldalon hajtsa végre az [Pénztárműveletek hozzáadása pénztárelrendezésekhez a Gombrácstervezővel](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters) dokumentum lépéseit, a tervező telepítéséhez és a pénztár elrendezésének frissítéséhez.

    1. A frissítendő elrendezés kiválasztása.
    1. Adja hozzá az új gombot, és és állítsa a **Pénzügyi regisztrációs folyamat befejezése** gombtulajdonságot.
    1. Az **Elosztási ütemezés** lapon, futtassa a **1090** feladatot a módosításai átviteléhez a csatorna-adatbázisba.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

---
title: A Commerce csatornák pénzügyi integrálásának beállítása
description: Ez a témakör bemutatja, hogyan állíthatja be a pénzügyi integráció funkciót a Commerce csatornákhoz.
author: josaw
ms.date: 08/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: epopov
ms.search.validFrom: 2018-11-1
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: 38ad2cc3dc7e511ac6e2ac9484d10ebd2d1d425d
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/13/2021
ms.locfileid: "7343313"
---
# <a name="set-up-the-fiscal-integration-for-commerce-channels"></a>A Commerce csatornák pénzügyi integrálásának beállítása

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan állíthatja be a pénzügyi integráció funkciót a Commerce csatornákhoz. A pénzügyi integráció kapcsolatos további tudnivalókat lásd: [A pénzügyi integráció áttekintése a Commerce csatornákhoz](fiscal-integration-for-retail-channel.md).

A pénzügyi integráció beállításának folyamata a következő általános műveleteket tartalmazza:

- Állítsa be a pénzügyi csatlakozókat, amelyek megjelenítik pénzügyi eszközöket és a szolgáltatásokat, amelyek a pénzügyi nyilvántartásokhoz használatosak például a pénzügyi nyomtatókat.
- A dokumentum-szolgáltatók konfigurálása, amelyek pénzügyi dokumentumokat hoznak létre, amelyeket a pénzügyicsatlakozók regisztrálnak a pénzügyi eszközökbe vagy szolgáltatásokba.
- Állítsa be a pénzügyi regisztrációs folyamatot, amely meghatározza a pénzügyi regisztrációs lépéseket, valamint a pénzügyi csatlakozókat és a pénzügyi dokumentumszolgáltatókat, amelyeket az egyes lépésekhez lesznek használva.
- A pénztári (POS) funkcióprofilokhoz rendelje hozzá a pénzügyi regisztrációs eljárásokat.
- Csatlakozó technikai profilok hozzárendelése a hardverprofilokhoz.

## <a name="set-up-a-fiscal-registration-process"></a>A pénzügyi regisztrációs folyamat beállítása

Mielőtt a pénzügyi integráció funkciót használná, konfigurálja a következő beállításokat.

1. Frissítse a Commerce paramétereket.

    1. A **Commerce megosztott paraméterek** oldalon, az **Általános** lapon a **Pénzügyi integráció engedélyezése** lehetőséget állítsa **Igen** értékre. A **Számsorozatok** lapon határozza meg az alábbi hivatkozások számsorozatkódját:

        - Pénzügyi technikai profil száma
        - Pénzügyi csatlakozócsoport száma
        - Regisztrációs folyamat száma

    1. A számsorozatot határozza meg a **Commerce paraméterek** lapon a pénzügyi funkcionális profilszám számára.

    > [!NOTE]
    > Számsorozatok megadása nem kötelező. Pénzügyi integráció entitásokhoz számok számsorozatokkal vagy manuálisan hozhatók létre.

1. Töltse fel a konfigurációkat a pénzügyi csatlakozók és a pénzügyi bizonylatszolgáltatók számára.

    A pénzügyi bizonylatszolgáltató felelős a pénzügyi bizonylatok generálásáért, amelyek megfelelnek a pénztárban regisztrált pénzügyi tranzakcióknak és eseményeknek, olyan formátumban, amely felhasználható pénzügyi eszközzel vagy szolgáltatással is az interakcióhoz. Például egy pénzügyi bizonylatszolgáltató létrehozhat egy pénzügyi nyugtát XML-formátumban.

    A pénzügyi csatlakozó felelős a kommunikációért a pénzügyi eszközzel vagy szolgáltatással. Például egy pénzügyi csatlakozó elküldhet egy XML-formátumban létrehozott pénzügyi nyugtát, amelyet egy pénzügyi dokumentumszolgáltató hozott létre egy pénzügyi nyomtatónak. Pénzügyi integráció összetevőinek kapcsolatos további tudnivalókat lásd: [Pénzügyi regisztráció folyamata és pénzügyi integrációs minták pénzügyi eszközökhöz](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices).

    1. A **Pénzügyi összekötők** oldalon (**Retail és Commerce\> Csatorna beállítása \> Pénzügyi integráció \> Pénzügyi összekötők**) töltsön fel egy XML-konfigurációt minden eszközhöz vagy szolgáltatáshoz, amelyet pénzügyi integrációs célokra tervez használni.

        > [!TIP]
        > A **Nézet** kiválasztásával, meg lehet tekinteni minden funkcionális és technikai profilt, amelyek az aktuális pénzügyi csatlakozóhoz kapcsolódnak.

    1. A **Pénzügyi dokumentumszolgáltatók** oldalon (**Retail és Commerce \> Csatorna beállítása \> Pénzügyi dokumentumszolgáltatók \> Pénzügyi összekötők**) töltsön fel egy XML-konfigurációt minden eszközhöz vagy szolgáltatáshoz, amelyet pénzügyi integrációs célokra tervez használni.

        > [!TIP]
        > A **Nézet** kiválasztásával, meg lehet tekinteni minden funkcionális és technikai profilt, amelyek az aktuális dokumentumszolgáltatóhoz kapcsolódnak.

    A fiskális csatlakozók és a fiskális dokumentumszolgáltatók konfigurációira vonatkozó példákért lásd: [Fiskális integrációs minták a Commerce SDK-ban](fiscal-integration-for-retail-channel.md#fiscal-integration-samples-in-the-commerce-sdk).

    > [!NOTE]
    > Az adatleképezést egy pénzügyi bizonylat szolgáltató részének kell tekinteni. Azonos összekötőhöz különböző adatleképezések beállításához (például államspecifikus előírások) eltérő pénzügyi bizonylat szolgáltatókat kell létrehozni.

1. Csatlakozó funkcionális profilok és csatlakozó műszaki profilok létrehozása.

    1. A **Csatlakozó működési profiljai** lapon (**Retail és Commerce \> Csatorna beállításai \> Pénzügyi integráció \> Csatlakozó működési profiljai**) hozzon létre egy csatlakozó működési profilt a pénzügyi csatlakozók és pénzügyi dokumentumszolgáltatók mindegyik kombinációjához, amely ehhez a pénzügyi csatlakozóhoz kapcsolódik.

        1. Válasszon ki egy összekötőnevet.
        1. Válasszon ki egy bizonylatszolgáltatót.

        Az adatok hozzárendelésének paramétereit a csatlakozó működési profiljában módosíthatja. A pénzügyi dokumentum-szolgáltató konfigurációjában meghatározott alapértelmezett paraméterek visszaállításához válassza a **Frissítés** lehetőséget.

        **Példák**

        | Paraméter  | Formátum | Példa |
        |---|--------|---------|
        | **Áfaszázalékok beállítása** | value : VATrate | 1 : 2000, 2 : 1800 |
        | **Áfakódok leképezése** | VATcode : value | vat20 : 1, vat18 : 2 |
        | **Fizetőeszköz-típusok leképezése** | TenderType : érték | Cash : 1, Card : 2 |

        > [!NOTE]
        > Csatlakoztató működési profilok vállalatspecifikusak. Ha eltérő vállalatokban szeretné használni pénzügyi csatlakozót és a pénzügyi dokumentumszolgáltatót, minden vállalathoz hozzon létre egy csatlakozó működési profilt.

    1. A **Csatlakozó műszaki profiljai** oldalon (**Retail és Commerce \> Csatorna beállítása \> Pénzügyi integráció \> Csatlakozó műszaki profiljai**) hozzon létre egy csatlakozó műszaki profilt az egyes pénzügyi csatlakozókhoz.

        1. Válasszon ki egy összekötőnevet.
        1. Válasszon ki egy összekötőtípust. Hardverállomáshoz kapcsolódó eszközök esetében, jelölje be a **Helyi** lehetőséget.

            > [!NOTE]
            > Jelenleg csak a helyi csatlakozók támogatottak.

        A paraméterek az **Eszköz** és **Beállítások** lapokon a csatlakozó műszaki profiljában módosíthatók. A pénzügyi csatlakozó konfigurációjában meghatározott alapértelmezett paraméterek visszaállításához válassza a **Frissítés** lehetőséget. Az XML-konfiguráció egy új verziójának betöltése során akkor egy üzenetet kap arról, hogy az aktuális pénzügyi csatlakozó vagy pénzügyi dokumentumszolgáltató már használatban van. Ezzel az eljárással nem bírálja felül a manuális módosításokat, amelyeket korábban elvégzett a csatlakozó funkcionális profiljain és a csatlakozó műszaki profiljain. Az alapértelmezett paraméterkészlet alkalmazásához egy új konfigurációból kattintson a **Frissítés** elemre a **Csatlakozó funkcionális profilja** lapon és válassza a **Frissítés** lehetőséget.

1. Hozzon létre pénzügyi csatlakozócsoportokat.

    A pénzügyi csatlakozócsoport azonos funkciókat végrehajtó, és a pénzügyi regisztrációs folyamat azonos szakaszában használt pénzügyi csatlakozókat kombinál. Például, ha több pénzügyi nyomtató modellt használnak üzletekben, azon pénzügyi nyomtatók pénzügyi csatlakozói egy csatlakozócsoportba kombinálhatók.

    1. Az **Pénzügyi csatlakozócsoport** lapon (**Retail és Commerce \> Csatorna beállításai \> Pénzügyi integráció \> Pénzügyi csatlakozócsoportok**), hozzon létre egy új pénzügyi csatlakozócsoportot.
    1. Működési profilok hozzáadása az összekötőcsoporthoz. A **Funkcionális profilok** lapon válassza a **Hozzáadás** lehetőséget, és válasszon egy profilszámot. Egy csatlakozócsoportban minden egyes fiskális csatlakozónak csak egy funkcionális profilja lehet.
    1. A működési profil használatának felfüggesztéséhez, a **Letiltás** beállítása legyen **Igen**. Ez a módosítás csak az aktuális csatlakozócsoportot érinti. Ugyanazt a funkcionális profilt az egyéb csatlakozócsoportokban továbbra is használhatja.

1. A pénzügyi regisztrációs folyamat létrehozása.

    A pénzügyi regisztrációs folyamatot a regisztrációs lépések sorrendje, és az egyes lépéseknél használt összekötőcsoport határozza meg.

    1. A **Pénzügyi regisztrációs folyamat** oldalon (**Retail és Commerce \> Csatorna beállítása \> Pénzügyi integráció \> Pénzügyi regisztrációs eljárások**) hozzon létre új rekordot a pénzügyi integráció minden egyedi folyamatához.
    1. Regisztráció lépéseket adjon hozzá a folyamathoz:

        1. Válassza a **Hozzáadás** lehetőséget.
        1. Válasszon ki egy pénzügyi csatlakozó típust.
        1. A **Csoportszám** mezőben, válasszon ki egy megfelelő pénzügyi csatlakozócsoportot.

1. A pénztári (POS) funkcióprofilokhoz rendelje hozzá a pénzügyi regisztrációs entitásokat.

    1. A **POS-funkcióprofilok** lapon (**Retail és Commerce \> Csatornabeállítások \> Pénztárbeállítások \> Pénztárprofilok \> Működési profilok**), rendelje hozzá a pénzügyi regisztrációs folyamatot pénztárműködési profilhoz. Válassza ki a **Szerkesztés** lehetőséget, majd a **Pénzügyi regisztrációs folyamat** lapon a **Feldolgozás száma** mezőben, válasszon ki egy folyamatot.
    1. A **POS-hardverprofil** lapon (**Retail és Commerce \> Csatornabeállítások \> Pénztárbeállítások \> Pénztárprofilok \> Hardverprofilok**), rendelje hozzá a csatlakozó műszaki profiljait egy hardverprofilhoz. Válassza a **Szerkesztés** lehetőséget, adjon hozzá egy sort a **Pénzügyi perifériák** lapon, majd a **Profil száma** mezőben, válasszon ki egy műszaki csatlakozóprofilt.

    > [!NOTE]
    > Egy hardverprofilhoz több műszaki profilt adhat hozzá. Azonban a hardverprofil vagy a POS funkcióprofil csak egy helyen találkozhat bármelyik pénzügyi csatlakozóprofillal.

    A pénzügyi regisztrációs folyamatot a pénzügyi regisztrációs folyamat határozza meg, valamint a pénzügyi integráció összetevőinek néhány paramétere: a pénzügyi dokumentum szolgáltató Commerce runtime-bővítménye és a pénzügyi csatlakozó Hardverállomás-bővítménye.

    - A feliratkozások a pénzügyi regisztráció eseményeire és tranzakcióira a pénzügyi dokumentumszolgáltatóban vannak előre meghatározva.
    - A pénzügyi bizonylat szolgáltató feladata továbbá a pénzügyi regisztrációhoz használt pénzügyi csatlakozó azonosítása. Ez illeszkedik a csatlakozó funkcionális profiljaihoz, amelyek szerepelnek a pénzügyi csatlakozócsoportban, amely meg van adva az aktuális lépéshez a pénzügyi regisztrációs folyamatban azzal a műszaki profillal, amely hozzá van rendelve annak a Hardverállomásnak a hardverprofiljához, amellyel a pénztár párosítva van.
    - A pénzügyi bizonylat szolgáltató a pénzügyi dokumentumszolgáltató adattérképezési beállításait használja az olyan tranzakció-/eseményadatok átviteléhez, mint az adók és kifizetések, a pénzügyi dokumentum generálása során.
    - Amikor pénzügyi dokumentumszolgáltató pénzügyi dokumentum hoz létre, a pénzügyi csatlakozó elküldheti azt változatlanul a pénzügyi eszköznek, vagy elemezheti és átalakíthatja azt parancssorozattá a alkalmazásprogramozási felület (API) számára, attól függően, hogy hogyan történik a kommunikáció kezelése.

1. A **Pénzügyi regisztrációs folyamat** oldalon (**Retail és Commerce \> Csatorna beállítása \> Pénzügyi integráció \> Pénzügyi regisztrációs eljárások**) válassza az **Ellenőrzés** lehetőséget a pénzügyi regisztrációs folyamat ellenőrzéséhez.

    Ajánljuk, hogy az ilyen típusú érvényesítési futtassa a következő esetekben:

    - Egy új regisztrációs folyamathoz, miután minden beállítás befejeződött, többek a regisztrációs folyamatok hozzárendelése a POS-funkcióprofilokhoz és hardverprofilokhoz.
    - Miután módosított egy meglévő pénzügyi regisztrációs folyamatot, és előfordulhat, hogy ezek a változtatások azt okozzák, hogy futásidőben egy másik pénzügyi csatlakozó lesz kiválasztva (például egy pénzügyi regisztrációs folyamat lépésének módosítja csatlakozócsoportját, engedélyez egy csatlakozó működési profilt a csatlakozócsoportban, vagy új csatlakozó funkcionális profilt ad hozzá egy csatlakozócsoporthoz).
    - Miután módosította a csatlakozó műszaki profilok hozzárendelését a a hardverprofilokhoz.

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

1. A **Pénzügyi regisztrációs folyamat** oldalon (**Retail és Commerce \> Csatorna beállítása \> Pénzügyi integráció \> Pénzügyi regisztrációs eljárások**) a következő paramétereket állíthatja be a pénzügyi regisztrációs folyamat egyes lépéseihez:

    - **Kihagyás engedélyezése** – Ez a paraméter engedélyezi a **Kihagyás** lehetőséget a hibakezelés párbeszédpanelen.
    - **Regisztráltnak megjelölés engedélyezése** – Ez a paraméter bekapcsolja a **Megjelölése a regisztráltként** lehetőséget a hibakeresés párbeszédablakában.
    - **Hiba esetén folytatás** – Ha ez a paraméter engedélyezve van, a pénzügyi regisztrációs folyamat folytatódhat a pénztárgépen, Ha egy tranzakciós esemény pénzügyi regisztrációja sikertelen. Ellenkező esetben a következő esemény vagy tranzakció pénzügyi regisztrációjának futtatásához, a kezelőnek kell újra kell próbálnia a sikertelen pénzügyi regisztrációt, ki kell hagynia vagy meg kell jelölnie a tranzakciót vagy esemény regisztráltként. További tudnivalókért lásd: [Opcionális pénzügyi regisztráció](fiscal-integration-for-retail-channel.md#optional-fiscal-registration).

    > [!NOTE]
    > Ha a **Hiba esetén folytatás** paraméter engedélyezve van, a **Kihagyása engedélyezése** és **Regisztráltnak megjelölés engedélyezése** paraméterek automatikusan le lesznek tiltva.

1. A **Kihagyás** és **Megjelölés regisztráltként** lehetőségekhez hibakezelés párbeszédpanelen szükséges **Regisztráció kihagyásának vagy regisztráltként megjelölés engedélyezése** engedély. Tehát az **Engedélycsoportok** lapon (**Retail és Commerce \> Alkalmazottak \> Engedélycsoportok**) kapcsolja be a **Regisztráció kihagyása vagy regisztráltként megjelölés engedélyezése** lehetőséget.
1. A **Kihagyás** és **Megjelölése a regisztráltként** beállítások lehetővé teszik a kezelőknek, hogy további információkat adjanak meg, ha a pénzügyi regisztráció meghiúsul. A funkció elérhetővé tételéhez, meg kell adnia a **Kihagyás** és **Megjelölése a regisztráltként** infókódokat a pénzügyi csatlakozócsoportban. A kezelők által megadott információk infókód-tranzakcióként lesznek mentve, amely a pénzügyi tranzakcióhoz van kapcsolva. Infókódokkal kapcsolatos további tudnivalókat lásd: [Infókódok és infókódcsoportok](../info-codes-retail.md).

    > [!NOTE]
    > A **Termék** funkció aktiválása nem támogatott azon infókódok esetében, amelyek a **Kihagyás** és **Megjelölés a regisztráltként** funkciókhoz használatosak a pénzügyi csatlakozócsoportokban.

    - A **Pénzügyi csatlakozócsoport** oldalon az **Infókódok** lapon válassza ki az infókódokat vagy a infókódcsoportokat a **Kihagyás** és **Megjelölés a regisztráltként** mezőkben.

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

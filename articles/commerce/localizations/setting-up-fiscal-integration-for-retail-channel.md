---
title: A Commerce csatornák pénzügyi integrálásának beállítása
description: Ez a cikk a Commerce csatornák pénzügyi integrációs funkcióinak beállításával kapcsolatos irányelveket tartalmaz.
author: EvgenyPopovMBS
ms.date: 04/28/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 695f3c1e704f2712f392d0d7179da63f47731f46
ms.sourcegitcommit: 6616b969afd6beb11a79d8e740560bf00016ea7f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/17/2022
ms.locfileid: "9027058"
---
# <a name="set-up-the-fiscal-integration-for-commerce-channels"></a>A Commerce csatornák pénzügyi integrálásának beállítása

[!include [banner](../includes/banner.md)]

Ez a cikk a Commerce csatornák pénzügyi integrációs funkcióinak beállításával kapcsolatos irányelveket tartalmaz. A pénzügyi integráció kapcsolatos további tudnivalókat lásd: [A pénzügyi integráció áttekintése a Commerce csatornákhoz](fiscal-integration-for-retail-channel.md).

## <a name="enable-features-in-commerce-headquarters"></a>A Commerce Headquarters szolgáltatásainak engedélyezése

A Commerce csatornák pénzügyi integrációs funkcióival kapcsolatos funkciók engedélyezéséhez kövesse ezeket a lépéseket.

1. A Commerce-központban lépjen a **Rendszerfelügyelet \> Munkaterületek \> Funkciókezelés** részre.
1. A következő funkciók megkeresik és engedélyezhetik:

    - **Közvetlen pénzügyi integráció POS-pénztárgépekkel** – ez a funkció a pénztárnál futtatott pénzügyi csatlakoztatók létrehozására való képesség felvételének lehetőséggel bővíti a pénzügyi integrációs keretrendszert. Az ilyen típusú csatlakoztató egy PÉNZÜGYI eszközzel vagy szolgáltatással kommunikál, amely HTTP alkalmazásprogramozási felületet (API) biztosít, és nem igényel külön fizikai gépet az üzletben. Ez a funkció például lehetővé teszi a pénzügyi integrációt mobileszközök esetében, a megosztott hardverállomás használata nélkül.
    - **Pénzügyi integráció technikai profil-felülbírálásai** – ez a funkció lehetővé teszi a pénzügyi integráció konfigurációjának kibontást, és lehetővé teszi a kapcsolati paraméterek ellenőrzését a POS-pénztárgép beállítási lapján. Ha ez a funkció engedélyezve van, akkor felülbírálhatja egy technikai profil paramétereit.
    - **PÉNZTÁRi pénztárgép** pénzügyi nyilvántartási állapota – ha ez a funkció engedélyezve van, akkor letilthatja a pénzügyi regisztrációs folyamatot az egyes PÉNZTÁRi pénztárgépekkel. Ha a PÉNZTÁRi pénztárgépen le van tiltva a pénzügyi regisztráció, akkor az értékesítési tranzakciókat nem lehet végrehajtani a pénztárgépen.
    - **Pénzügyi integráció - helyi tárolás** biztonsági mentése – ez a funkció kiterjeszti a pénzügyi integrációs keretrendszer hibakezelési lehetőségeit. Lehetővé teszi továbbá a pénzügyi regisztrációs adatok automatikus biztonsági mentését adatvesztés esetén, így az eszköz aktiválása közben a helyi tárolóban található adatok visszaállítása történik.

## <a name="set-up-commerce-parameters"></a>Commerce-paraméterek beállítása

A Commerce rendszer paramétereinek beállítását a következő lépések szerint hajtsa végre.

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
- Rendelje hozzá a pénzügyi regisztrációs folyamatot a POS funkcióprofiljaihoz.
- Csatlakozó technikai profilok hozzárendelése a hardverprofilokhoz.
- A csatlakoztató műszaki profilok hozzárendelése a POS hardver- vagy funkcióprofiljaihoz.

### <a name="upload-configurations-of-fiscal-document-providers"></a>Pénzügyi bizonylat-szolgáltatók konfigurációjának feltöltése

A pénzügyi bizonylatszolgáltató felelős a pénzügyi bizonylatok generálásáért, amelyek megfelelnek a pénztárban regisztrált pénzügyi tranzakcióknak és eseményeknek, olyan formátumban, amely felhasználható pénzügyi eszközzel vagy szolgáltatással is az interakcióhoz. Például egy pénzügyi bizonylatszolgáltató létrehozhat egy pénzügyi nyugtát XML-formátumban.

A következő lépések szerint töltheti fel a pénzügyi bizonylatok szolgáltatói konfigurációit.

1. A Commerce Headquarters szolgáltatásban kattintson **a** Pénzügyi dokumentumok szolgáltatói lapra (**Retail and Commerce \> Channel setup \> Fiscal integration \> Fiscal document providers**).
1. XML-konfiguráció feltöltése minden egyes eszközre vagy szolgáltatásra, amely használatban van.

> [!TIP]
> A **Nézet** kiválasztásával, meg lehet tekinteni minden funkcionális és technikai profilt, amelyek az aktuális dokumentumszolgáltatóhoz kapcsolódnak.

> [!NOTE]
> Az adatleképezést egy pénzügyi bizonylat szolgáltató részének kell tekinteni. Azonos összekötőhöz különböző adatleképezések beállításához (például államspecifikus előírások) eltérő pénzügyi bizonylat szolgáltatókat kell létrehozni.

### <a name="upload-configurations-of-fiscal-connectors"></a>Pénzügyi csatlakoztató konfigurációjának feltöltése

A pénzügyi csatlakozó felelős a kommunikációért a pénzügyi eszközzel vagy szolgáltatással. Például egy pénzügyi csatlakozó elküldhet egy XML-formátumban létrehozott pénzügyi nyugtát, amelyet egy pénzügyi dokumentumszolgáltató hozott létre egy pénzügyi nyomtatónak. A pénzügyi integráció összetevőiről a [pénzügyi eszközök és szolgáltatások pénzügyi nyilvántartási folyamata és pénzügyi integrációs mintái tartalmaznak további részleteket](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

A következő lépések szerint töltheti fel a pénzügyi csatlakoztató konfigurációit.

1. A Commerce Headquarters program Pénzügyi **csatlakoztatói lapon (** Retail és Commerce **Channel setup \> Fiscal integration \> Fiscal connectors \>) indul el**.
1. XML-konfiguráció feltöltése minden olyan eszközre vagy szolgáltatásra, amely pénzügyi integrációs célokra használni tervezi.

> [!TIP]
> A **Nézet** kiválasztásával, meg lehet tekinteni minden funkcionális és technikai profilt, amelyek az aktuális pénzügyi csatlakozóhoz kapcsolódnak.

A fiskális csatlakozók és a fiskális dokumentumszolgáltatók konfigurációira vonatkozó példákért lásd: [Fiskális integrációs minták a Commerce SDK-ban](fiscal-integration-for-retail-channel.md#fiscal-integration-samples-in-the-commerce-sdk).

### <a name="create-connector-functional-profiles"></a>Csatlakoztató funkcionális profilok létrehozása

A csatlakoztató funkcionális profiljainak létrehozásához kövesse ezeket a lépéseket.

1. A Commerce Headquarters területén kattintson **a Connector funkcionális profilok** oldalára (**Retail and Commerce \> Channel setup \> Fiscal integration \> Connector funkcionális profilok**).
1. A pénzügyi csatlakoztató és az ehhez a pénzügyi csatlakoztatóhoz kapcsolódó pénzügyi dokumentumszolgáltató minden egyes kombinációjához hozzon létre egy csatlakoztató funkcionális profilt a következő lépések segítségével:

    1. Válasszon ki egy összekötőnevet.
    1. Válasszon ki egy bizonylatszolgáltatót.

#### <a name="change-data-mapping-parameters-in-a-connector-functional-profile"></a>Adatleképezési paraméterek módosítása egy csatlakoztató funkcionális profiljában

Az adatok hozzárendelésének paramétereit a csatlakozó működési profiljában módosíthatja. Az alábbi táblázat néhány példát mutat be a csatlakoztató funkcionális profilja adatleképezési paramétereire.

| Paraméter | Formátum | Példa |
|-----------|--------|---------|
| Áfaszázalékok beállítása | value : VATrate | 1 : 2000, 2 : 1800 |
| Áfakódok leképezése | VATcode : value | vat20 : 1, vat18 : 2 |
| Fizetőeszköz-típusok leképezése | TenderType : érték | Cash : 1, Card : 2 |

A pénzügyi bizonylat szolgáltatói konfigurációjában **meghatározott alapértelmezett paraméterek visszaállításához válassza a Frissítés** lehetőséget **a Connector funkcionális profilok lapján**.

> [!NOTE]
> Csatlakoztató működési profilok vállalatspecifikusak. Ha azt tervezi, hogy a pénzügyi csatlakoztató és a különböző vállalatokhoz ugyanazt a pénzügyi dokumentumszolgáltató kombinációt használja, minden egyes vállalathoz létre kell hoznia egy funkcionális csatlakoztatóprofilt.

### <a name="create-connector-technical-profiles"></a>Csatlakoztató műszaki profilok létrehozása

A csatlakoztató műszaki profilok létrehozásához kövesse ezeket a lépéseket.

1. A Commerce Headquarters területén kattintson a Connector **műszaki profilok oldalára (** Retail and Commerce **Channel setup \> Fiscal integration \> Connector technical profiles \>).**
1. Hozzon létre egy csatlakoztató műszaki profilt mindegyik pénzügyi csatlakoztatóhoz a következő lépések segítségével:

    1. Válasszon ki egy összekötőnevet.
    1. Válassza ki a csatlakoztató típusát:

        - A Hardverállomáshoz csatlakoztatott, illetve a helyi hálózaton található eszközök és szolgáltatások esetében válassza a Helyi **lehetőséget**.
        - Külső szolgáltatásoknál válassza a Külső **lehetőséget**.
        - A Commerce runtime () belső csatlakoztatóihoz válassza CRT a Belső **lehetőséget**. 

    1. Válassza ki a csatlakoztató helyét:

        - Ha a csatlakoztató a hardverállomáson található, válassza a **Hardverállomást**.
        - Ha a csatlakoztató a POS-pénztárgépen található, válassza a Pénztár **lehetőséget**.

A paraméterek az **Eszköz** és **Beállítások** lapokon a csatlakozó műszaki profiljában módosíthatók. A pénzügyi csatlakozó konfigurációjában meghatározott alapértelmezett paraméterek visszaállításához válassza a **Frissítés** lehetőséget. Miközben betöltődik egy XML-konfiguráció egy új verziója, egy üzenet jelenik meg, amely szerint az aktuális pénzügyi csatlakoztató vagy pénzügyi dokumentumszolgáltató már használva van. Ezzel az eljárással nem bírálja felül a manuális módosításokat, amelyeket korábban elvégzett a csatlakozó funkcionális profiljain és a csatlakozó műszaki profiljain. Ha egy új konfiguráció alapértelmezett paramétereit is alkalmazni kívánta, **válassza a Frissítés** lehetőséget **vagy** a Connector funkcionális profilok lapján, **vagy a Connector műszaki profilok** lapján.

Ha egy adott POS-pénztárgéphez vagy üzlethez külön paramétereket kell beállítania, kövesse ezeket a lépéseket.

1. Válassza a **Felülbírálás** menüelemet.
1. Hozzon létre **egy** új rekordot a Felülbírálás lapon.
1. Válasszon ki egy üzletet vagy pénztárgépet. A kiválasztott technikai profil paramétereit felülbírálhatja egy adott POS-pénztárgépre vagy egy adott üzlet minden PÉNZTÁRgépére.
1. Az Eszköz **lapon** adja meg a kiválasztott POS-pénztárgép vagy üzlet paramétereit.

### <a name="create-fiscal-connector-groups"></a>Pénzügyi csatlakoztató csoportjainak létrehozása

A pénzügyi csatlakozócsoport azonos funkciókat végrehajtó, és a pénzügyi regisztrációs folyamat azonos szakaszában használt pénzügyi csatlakozókat kombinál. Például, ha több pénzügyi nyomtató modellt használnak üzletekben, azon pénzügyi nyomtatók pénzügyi csatlakozói egy csatlakozócsoportba kombinálhatók.

A következő lépések szerint hozzon létre egy pénzügyi csatlakoztatócsoportot.

1. Ugrás a Pénzügyi csatlakoztató csoportlapjára **(** Retail és Commerce **Csatorna beállítása Pénzügyi \> integráció \> – Pénzügyi csatlakoztatócsoportok \>**).
1. Pénzügyi csatlakoztató új csoportjának létrehozása.
1. Működési profilok hozzáadása az összekötőcsoporthoz. A **Funkcionális profilok** lapon válassza a **Hozzáadás** lehetőséget, és válasszon egy profilszámot. Egy csatlakozócsoportban minden egyes fiskális csatlakozónak csak egy funkcionális profilja lehet.
1. A működési profil használatának felfüggesztéséhez, a **Letiltás** beállítása legyen **Igen**. Ez a módosítás csak az aktuális csatlakozócsoportot érinti. Ugyanazt a funkcionális profilt az egyéb csatlakozócsoportokban továbbra is használhatja.

### <a name="create-a-fiscal-registration-process"></a>Pénzügyi regisztrációs folyamat létrehozása

A pénzügyi regisztrációs folyamatot a regisztrációs lépések sorrendje, és az egyes lépéseknél használt összekötőcsoport határozza meg.

A következő lépések szerint hozhatja létre a pénzügyi nyilvántartási folyamatot.

1. A Commerce Headquarters alkalmazás a **Pénzügyi nyilvántartási folyamat** lapra (**Retail and Commerce \> Csatorna beállítása Pénzügyi \> integráció \> pénzügyi regisztrációs folyamatai) indul el**.
1. Új rekord létrehozása minden egyes egyedi pénzügyi regisztrációs folyamathoz.
1. A következő lépésekkel adhat hozzá regisztrációs lépéseket a folyamathoz:

    1. Válassza a **Hozzáadás** lehetőséget.
    1. Válasszon ki egy pénzügyi csatlakozó típust.
    1. A **Csoportszám** mezőben, válasszon ki egy megfelelő pénzügyi csatlakozócsoportot.

### <a name="assign-entities-of-the-fiscal-registration-process-to-pos-profiles"></a>A pénzügyi regisztrációs folyamat entitásjainak hozzárendelése POS-profilokhoz

A következő lépések szerint rendelheti hozzá a pénzügyi regisztrációs folyamat entitásjait a POS-profilokhoz.

1. A Commerce Headquarters alkalmazás a **POS funkcióprofilok oldalára** indul el (**Retail and Commerce \> Channel setup \> POS setup \> POS \> profiles Functionality profiles**). 
1. Rendelje hozzá a pénzügyi regisztrációs folyamatot egy POS funkcióprofilhoz.
1. Válassza ki a **Szerkesztés** lehetőséget, majd a **Pénzügyi regisztrációs folyamat** lapon a **Feldolgozás száma** mezőben, válasszon ki egy folyamatot.
1. A Pénzügyi szolgáltatások **lapon** válassza ki a csatlakoztató műszaki profiljait a csatlakoztató **helyjegyzékével**.
1. Ugrás a POS hardverprofil oldalára **(** Retail and Commerce **Channel setup \> POS telepítő \> POS-profilok \> – Hardverprofilok \>**).
1. Csatlakoztató műszaki profilok hozzárendelése hardverprofilhoz. 
1. Válassza **a Szerkesztés** lehetőséget, majd a **Pénzügyi perifériák** lapon adjon hozzá egy sort. 
1. A Profil **száma mezőben** válasszon ki egy csatlakoztató műszaki profilt.
1. A Pénzügyi perifériák **lapon** válassza ki a csatlakoztató műszaki profiljait a hardverállomás csatlakoztató **helyével**.

> [!NOTE]
> Egy hardverprofilhoz több műszaki profilt adhat hozzá. Azonban a hardverprofil vagy a POS funkcióprofil csak egy helyen találkozhat bármelyik pénzügyi csatlakozóprofillal.

A pénzügyi nyilvántartási folyamatot a pénzügyi nyilvántartási folyamat határozza meg, valamint a pénzügyi integráció összetevőinek bizonyos paraméterei: CRT a pénzügyi bizonylat szolgáltatójának kiterjesztése és a pénzügyi csatlakoztató hardverállomás-bővítménye.

- A feliratkozások a pénzügyi regisztráció eseményeire és tranzakcióira a pénzügyi dokumentumszolgáltatóban vannak előre meghatározva.
- A pénzügyi bizonylat szolgáltató feladata továbbá a pénzügyi regisztrációhoz használt pénzügyi csatlakozó azonosítása. Ez illeszkedik a csatlakozó funkcionális profiljaihoz, amelyek szerepelnek a pénzügyi csatlakozócsoportban, amely meg van adva az aktuális lépéshez a pénzügyi regisztrációs folyamatban azzal a műszaki profillal, amely hozzá van rendelve annak a Hardverállomásnak a hardverprofiljához, amellyel a pénztár párosítva van.
- A pénzügyi bizonylat szolgáltató a pénzügyi dokumentumszolgáltató adattérképezési beállításait használja az olyan tranzakció-/eseményadatok átviteléhez, mint az adók és kifizetések, a pénzügyi dokumentum generálása során.
- Amikor a pénzügyi bizonylat szolgáltatója pénzügyi bizonylatot generál, a pénzügyi csatlakoztató vagy a megfelelő módon elküldheti a pénzügyi eszköznek, vagy elemezheti, és az eszköz API-parancssorozata szerint átalakíthatja azt, a kommunikáció kezelésétől függően.

### <a name="set-up-registers-with-fiscal-registration-restrictions"></a>Pénztárak beállítása pénzügyi regisztrációs korlátozásokkal

Kiválaszthatja azokat a pénztárgépeket, ahol a pénzügyi regisztráció tilos, például olyan esetekben, amikor csak nem pénzügyi műveleteket kell nyújtania, például termékkatalógus-keresést, vevőkeresést vagy tranzakciótervezet-létrehozást kell ezen az eszközön.

A következő lépések szerint állíthatja be a pénztárgépeket a pénzügyi nyilvántartási korlátozásokkal.

1. A Commerce Headquarters alkalmazás a **Retail és Commerce \> Channel beállításához kapcsolódó pénzügyi \> integráció \> pénzügyi regisztrációs folyamatainak egyikében található**.
1. Válassza ki a szükséges folyamatot.
1. Válassza ki **a pénzügyi folyamatokra vonatkozó korlátozásokkal együtt a POS-pénztárgépeket**.
1. Szükség szerint adja hozzá a pénzügyi folyamatra vonatkozó korlátozásokat megszabadó jegyzékeket.

### <a name="validate-the-fiscal-registration-process"></a>A pénzügyi regisztrációs folyamat ellenőrzése

A következő esetekben ajánlott a pénzügyi nyilvántartási folyamat ellenőrzése:

- Egy új regisztrációs folyamat minden beállítását befejezte. Ilyen beállítások közé tartozik a regisztrációs folyamatok hozzárendelése a POS funkcióprofiljaihoz és hardverprofiljaihoz.
- Egy meglévő pénzügyi regisztrációs folyamaton módosításokat végrehajtott, és előfordulhat, hogy futásidőben másik pénzügyi csatlakoztató lesz kiválasztva. (Módosította például egy pénzügyi regisztráció folyamatlépés csatlakoztatócsoportját, engedélyezte a csatlakoztató funkcionális profilját egy csatlakoztatócsoportban, vagy új funkcionális profilt adott hozzá egy csatlakoztatócsoporthoz.)
- A csatlakoztató műszaki profilok hardverprofilhoz való hozzárendelésében módosításokat eszközl.

A pénzügyi nyilvántartási folyamat ellenőrzéshez kövesse az alábbi lépéseket.

1. A Commerce Headquarters alkalmazás a **Pénzügyi nyilvántartási folyamat** lapra (**Retail and Commerce \> Csatorna beállítása Pénzügyi \> integráció \> pénzügyi regisztrációs folyamatai) indul el**.
1. A pénzügyi **regisztrációs** folyamat ellenőrzéshez válassza az Ellenőrzés lehetőséget.
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

A hibakezelési beállításokat a következő lépések szerint állíthatja be.

1. A **Pénzügyi regisztrációs folyamat** oldalon (**Retail és Commerce \> Csatorna beállítása \> Pénzügyi integráció \> Pénzügyi regisztrációs eljárások**) a következő paramétereket állíthatja be a pénzügyi regisztrációs folyamat egyes lépéseihez:

    - **Kihagyás engedélyezése** – Ez a paraméter engedélyezi a **Kihagyás** lehetőséget a hibakezelés párbeszédpanelen.
    - **Regisztráltnak megjelölés engedélyezése** – Ez a paraméter bekapcsolja a **Megjelölése a regisztráltként** lehetőséget a hibakeresés párbeszédablakában.
    - **Elhalasztás engedélyezése** – ez a paraméter engedélyezi **az Elhalasztás** lehetőséget a hibakezelési párbeszédpanelen.
    - **Hiba esetén folytatás** – Ha ez a paraméter engedélyezve van, a pénzügyi regisztrációs folyamat folytatódhat a pénztárgépen, Ha egy tranzakciós esemény pénzügyi regisztrációja sikertelen. Ellenkező esetben a következő esemény vagy tranzakció pénzügyi regisztrációjának futtatásához, a kezelőnek kell újra kell próbálnia a sikertelen pénzügyi regisztrációt, ki kell hagynia vagy meg kell jelölnie a tranzakciót vagy esemény regisztráltként. További tudnivalókért lásd: [Opcionális pénzügyi regisztráció](fiscal-integration-for-retail-channel.md#optional-fiscal-registration).

    > [!NOTE]
    > Ha a **Hiba esetén folytatás** paraméter engedélyezve van, a **Kihagyása engedélyezése** és **Regisztráltnak megjelölés engedélyezése** paraméterek automatikusan le lesznek tiltva.

1. A **Hibakezelési** párbeszédpanelEn **·** **a Kihagyás és a Megjelölés regisztrált beállításként beállítás esetén engedélyezni kell a Regisztrációk kihagyása és a Megjelölés regisztrált** engedélyként beállítást. Ennek az engedélynek az engedélyezéséhez menjen az Engedélycsoportok lapra (**Retail és Commerce** Employees **Permission groups \>), \> és állítsa a Regisztrációk kihagyása** **lehetőséget, vagy jelölje meg Regisztrálva beállításként Igen beállítást**.**·**
1. A **hibakezelési** párbeszédpanel Halasztás beállításához **engedélyezni kell az Elhalasztás** engedélyezése engedélyt. Az engedély engedélyezéséhez kattintson az Engedélycsoportok **lapra (** Retail és Commerce **Employees \> Permission groups \>), és állítsa** **Az Elhalasztás engedélyezése lehetőséget** Igen beállításra **.**
1. A **Kihagyás**, **Megjelölés regisztráltként és** **Halasztás** beállításokkal további adatokat is megadhatja a kezelők, ha a pénzügyi regisztráció sikertelen. Ahhoz, hogy ez a funkció használható legyen, **meg kell adnia a Skip**, **a Megjelölés regisztráltként** **és** az Infókódok elhalasztása kódot egy pénzügyi csatlakoztatócsoporthoz. A kezelők által megadott információk infókód-tranzakcióként lesznek mentve, amely a pénzügyi tranzakcióhoz van kapcsolva. Infókódokkal kapcsolatos további tudnivalókat lásd: [Infókódok és infókódcsoportok](../info-codes-retail.md).

    > [!NOTE]
    > A **Termék** funkció aktiválása nem támogatott azon infókódok esetében, amelyek a **Kihagyás** és **Megjelölés a regisztráltként** funkciókhoz használatosak a pénzügyi csatlakozócsoportokban.

    - A Pénzügyi csatlakoztató **csoport** lapján, **az Infókódok** lapon válassza ki az infókódokat **vagy infókódcsoportokat a Kihagyás**, **a Megjelölés regisztráltként** és a Halasztás **mezőben**.

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


## <a name="view-connection-parameters-and-other-information-in-pos"></a>A POS kapcsolati paramétereinek és egyéb információinak megtekintése

A pos rendszer kapcsolati paramétereinek és egyéb információinak megtekintéséhez kövesse ezeket a lépéseket.

1. Nyissa meg a Modern POS (MPOS) vagy a Felhő POS (CPOS) terminált.
1. Válassza a **Beállítások** lehetőséget. Ha engedélyezve van a pénzügyi integráció, **a** jobb oldalon található Pénzügyi integráció szakasz a következő adatokat mutatja:

    - A pénzügyi regisztráció állapota
    - A legutóbbi pénzügyi tranzakció állapota
    - A függő könyvvizsgálati események száma

1. A **részletek kiválasztásával** a következő információkat lehet megtekinteni:

    - Regisztrációs folyamat lépései
    - Kapcsolódási paraméterek
    - Könyvvizsgálati események részletei
 
[!INCLUDE[footer-include](../../includes/footer-banner.md)]

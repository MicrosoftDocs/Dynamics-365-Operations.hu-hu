---
title: Szállítók felvétele
description: Ez a témakör az új szállítók felvételének folyamatát mutatja be. Ismerteti, hogy a különböző szerepköröknek milyen műveleteket kell elvégezniük a folyamat közben.
author: mkirknel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationRequests, SysUserRequestListPage, VendRequestListPage, VendRequestCompanyProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 171d3b57333cc325fa675627e4c38f764d89f32c
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4429919"
---
# <a name="onboard-vendors"></a>Szállítók felvétele

[!include [banner](../includes/banner.md)]

---

Az új szállítók felvétele és szállítóként való regisztrálása a Microsoft Dynamics 365 Supply Chain Management rendszerben a szállítókat képviselő személyektől gyűjtött információk alapján történik.

A folyamat az alábbi lépésekből áll, amik közben a különböző szerepek műveleteket hajtanak végre a rendszerben.

1. **Adatkezelés OData** – Entitásimportálás - Az eredeti kérelem a potenciális szállító regisztrációs kérelme. A kérés általában olyan forrásból jön, amely engedélyezi a névtelen hozzáférést, mint például egy vevő által üzemeltetett webhely. A szállítók regisztrálhatnak az alapvető adatok megadása által, mint például a szállító neve, indoklása, szervezeti száma, és a kapcsolattartó személy neve és e-mail címe. A kérelmek importálása az adatkezelési felületen keresztül történik.
2. **Potenciális szállító regisztrációs kérelmének listaoldala** - A potenciális szállító regisztrációs kérelmében megadott információk alapján egy beszerző eldönti, hogy fel kell-e venni a szállítót. A beszerző megtekinti a beérkező kérelmet a **Potenciális szállító regisztrációs kérelmei** listaoldalon.
3. **Felhasználólétesítési munkafolyamat** – Ha a beszerző ellenőrizte az beérkező kérelemben található információkat és a felvételi folyamat folytatása mellett döntött, akkor a felhasználói kérelem munkafolyamat egy új felhasználót létesít, és küld egy meghívó e-mailt a kapcsolattartó személy hitelesített Microsoft Dynamics 365 felhasználóként való elfogadásának érdekében.
4. **Szállító regisztrációs varázsló** – a szállító kapcsolattartója bejelentkezik az új felhasználói fiók használatával. Ő befejezi a szállító regisztrációs varázslót, és ezzel olyan információkat nyújt, mint a címek, az üzleti adatok, a beszerzési kategóriák és a kérdőívekre adott válaszok.
5. **Jóváhagyási munkafolyamat** - Egy olyan szállítókérés jön létre, amely tartalmazza a regisztrációs információkat. A rendszer ezt a szállítókérést egy munkafolyamathoz küldi, és továbbítja felülvizsgálat és jóváhagyás céljából.
6. **Szállítói alapadatok létrehozása és a felhasználói szerepkör módosítása** - Ha a szállítókérés jóváhagyásra kerül, akkor egy új szállítói rekord jön létre. A szállító kapcsolattartójának felhasználói fiókja vagy megkapja a szállítói együttműködési engedélyt, vagy inaktiválásra kerül.

Az alábbi táblázat bemutatja a folyamatban részt vevő szerepköröket és a lépéseket.

| Szerepkör és "folyamat"       | Adatkezelés OData – Entitásimportálás | Potenciális szállítók regisztrálási kérelmének listalapja | Felhasználó-létesítő munkafolyamat | Szállító regisztrációs varázsló | Jóváhagyási munkafolyamat | Szállítói alapadatok létrehozása és a felhasználói szerepkör módosítása |
|--------------------------|---|---|---|---|---|---|
| System                   | Az új szállítóra való kérelem importálásra kerül. | | | | | A szállítókérés elfogadása után létrejön a szállítói rekord. |
| Beszerző | | A felvételi művelet indítása. | | | Ellenőrizze, és fogadja-, vagy utasítsa el a szállítókérést. | |
| Adminisztrátor            | | | Hozzon létre egy felhasználót a Supply Chain Management és a Microsoft Azure rendszerben. | | | |
| A szállító kapcsolattartója    | | | E-mail küldése a kapcsolattartónak. | Szállítói információ regisztrálása. | | |

Az új szállítók felvételi folyamatának gyors bemutatásáért nézze meg ezt a rövid YouTube-videót: [Új szállító beléptetése a Finance and Operations rendszerben](https://www.youtube.com/watch?v=0KUc3AGaTKk).

## <a name="importing-the-prospective-vendor-registration-request"></a>A potenciális szállító regisztrálási kérelmének importálása

A potenciális szállító regisztrációs kérelem egy entitás a Supply Chain Management rendszerben. Beállíthatja a rendszert úgy, hogy az adatok importálása ezen az entitáson keresztül történjen. 

Az alábbi táblázat bemutatja az entitás által tartalmazott információkat, amelyek importálhatóak.

| Mező                        | Leírás |
|------------------------------|-------------|
| Szállító neve                  | A szállító neve. |
| Üzleti alátámasztás       | A szállítókérés oka(i) |
| Szervezet száma          | Hivatalosan ismert regisztrációs szám. |
| Üzletág             | Az az üzletág, amelyben a szállító működik. |
| Kapcsolattartó utóneve  | A szállító adatainak regisztrálására meghívandó személy utóneve. |
| Kapcsolattartó második utóneve | A szállító adatainak regisztrálására meghívandó személy második utóneve. |
| A kapcsolattartó vezetékneve   | A szállító adatainak regisztrálására meghívandó személy vezetékneve. |
| Kapcsolattartó e-mail címe       | Az e-mail-cím, amellyel a Supply Chain Management új felhasználója létrejön, és amely regisztrálásra kerül a bérlő Azure Active Directory (Azure AD) fiókjában. |
| Elküldés dátuma               | A kérelem külső rendszerben való létrehozásának dátuma. |
| Jogi személy                 | A jogi személy, akinél a szállító benyújtotta a szállítói kérelmet. Ennek az értéknek olyan jogi személy kódnak kell lennie, amit már regisztráltak a Supply Chain Management rendszerben. Ha nem érkezik érték az importálási folyamat közben, akkor a beszerzési- és forrásparaméterekben található érték kerül használatra. |
| Szállítótípus                  | A szállító lehet szervezet vagy személy. A szállító típusa határozza meg, hogy a szállító végül milyen módon jön létre. |

A potenciális szállító regisztrációs kérelmének importálása után az megjelenik a **Potenciális szállító regisztrációs kérelme** listaoldalon. Erről a listaoldalról egy beszerző meghívhatja a felhasználót. Egy felhasználói kérelem felhasználó létesítéséről elküldésre kerül egy munkafolyamathoz.

## <a name="submitting-a-prospective-vendor-user-request"></a>Potenciális szállító felhasználói kérelmének elküldése

A potenciális szállító felhasználói kérelmének célja az eredeti kérést küldő személy létesítése, hogy ő bejelentkezhessen a Supply Chain Management rendszerbe a potenciális szállító regisztrációs kérelmében megadott e-mail-fiók használatával.

A potenciális szállító felhasználói kérelmét a felhasználói kérelem munkafolyamata dolgozza fel. Ez a munkafolyamat az Azure AD B2B együttműködésen keresztül kommunikál. Egy olyan felhasználót hoz létre a Supply Chain Management rendszerben, amely rendelkezik a megfelelő biztonsági beállításokkal.

A beállított új felhasználók a következő biztonsági szerepkörökkel rendelkeznek:

- Rendszer külső felhasználója
- Potenciális szállító (külső)

Az új felhasználó kap egy, a felhasználói kérelem munkafolyamat által generált e-mailt. Ez az e-mail felkéri a felhasználót, hogy jelentkezzen be a rendszerbe.

Az e-maillel, és általában a munkafolyamat konfigurációjával kapcsolatos információkért lásd a felhasználói kérelem munkafolyamat leírását itt: [Szállítói együttműködés beállítása és fenntartása](set-up-maintain-vendor-collaboration.md).

## <a name="vendor-registration"></a>Szállító regisztrálása

A Supply Chain Management rendszerbe bejelentkező potenciális szállítói felhasználó a szállítói regisztrációs varázsló első oldalát láthatja, ahol ő megadhatja a szállító információit.

A varázsló tükrözi a szállítói kérelem konfigurációját. Az ország vagy régió, ahol a szállító dolgozik meghatározza, hogy a varázsló milyen adatokat kérvényez, és milyen adatokat kötelező megadni.

További tudnivalókért a szállítókérési konfigurációval kapcsolatban lásd: [Szállítói együttműködés beállítása és fenntartása](set-up-maintain-vendor-collaboration.md). Az alábbi táblázat tartalmazza a varázsló oldalainak áttekintését, és minden egyes oldal célját.

| Oldal                       | Leírás |
|----------------------------|-------------|
| Ország/régió             | Az ország vagy régió meghatározza a szállítókérési konfigurációt, amely érvényes a varázsló további oldalain. Ez az **Adózási ország** keresésben található értékeket is meghatározza. |
| Feltételek és kikötések       | Ez az oldal lehet, hogy elérhető, a szállítókérési konfigurációtól függően. Ha elérhető, akkor a felhasználónak el kell ismernie a feltételeket és kikötéseket a folytatáshoz. |
| Szállító adatai         | Ez a lap tartalmazza a szállító nevét, amely automatikusan megjelenik a potenciális szállító eredeti regisztrációs kéréséből. Ezenkívül tartalmazza a szervezeti számot, a szállító telefonszámát, faxszámát és e-mail címét, illetve a szállító címeit különféle célokra. |
| Kapcsolattartó adatai | Ez az oldal tartalmazza a kapcsolattartó nevét, amely automatikusan megjelenik a potenciális szállító eredeti regisztrációs kéréséből. Ezenkívül tartalmazza a kapcsolattartó telefonszámát és e-mail címét, illetve a címét különféle célokra. |
| Üzleti adatok       | Ez az oldal az adószámokat (a különböző országokban vagy régiókban) és az alkalmazottak számát tartalmazza. Azt is mutatja, hogy az üzlet kisebbség tulajdonában van-e. |
| Beszerzési kategóriák     | Ez a lap azokat a beszerzési kategóriákat tartalmazza, amikre a szállító jóváhagyást kér. A felhasználó kiválaszthat kategóriákat a beszerzési kategóriahierarchiában. Beállíthatja a hierarchiában megjelenő szintek számát itt: **Beszerzési- és forrásparaméterek** &gt; **Szállítói együttműködés**, ez alatt: **Beszerzés és forrás** &gt; **Beállítás**. |
| Kérdőívek             | A varázsló tartalmazhat egy kérdőívcsoportot a szállító számára. A varázslóban megjelenő kérdőívek beállítása vagy a szállítókérésben, vagy beszerzési kategóriánként történik. Ha a kérdőív beállítása beszerzési kategóriánként történik, akkor a varázslóban megjelenő kérdőíveket azok a beszerzési kategóriák határozzák meg, amikre a szállító jóváhagyást kér. A **Beszerzési kategóriák** oldalon megadhat egy kérdőívet a kívánt kategória alatt és a tevékenységtípust átállíthatja erre: **Szállító felvétele**. |

Ha a potenciális szállítói felhasználó befejezte a szállítói regisztrációs varázslót, egy szállítókérés jön létre.

## <a name="manually-or-automatically-submit-a-vendor-request"></a>Szállítói kérelem manuális vagy automatikus elküldése

A szállítókérés vázlatként is létrejöhet, majd manuális elküldésre kerülhet egy munkafolyamathoz. Másik lehetőségként a szállítókérés munkafolyamathoz küldése automatikusan is történhet, a szállítói regisztrációs varázsló befejezése után. A kérelem elküldése történhet manuálisan, ha például egy beszerző meg szeretné állapítani, hogy a kérelmet továbbítani kell-e egy jóváhagyási folyamathoz, mielőtt elküldésre kerül a munkafolyamathoz.

- Válassza ki ezt: **Beszerzési- és forrásparaméterek** &gt; **Szállítói együttműködés**, majd ezt: **Potenciális szállítói regisztráció automatikus küldése a munkafolyamathoz** , ha be szeretné állítani, hogy a szállítókérés munkafolyamathoz küldése automatikusan történjen a szállítói regisztrációs varázsló befejezésekor.

## <a name="vendor-requests"></a>Szállítókérések

A szállítókérések a **Szállítói együttműködés felhasználói kérelmei** oldalon érhetőek el.

A szállítókérés tartalmazza az információkat, amiket a potenciális szállítói felhasználó megadott a szállítói regisztrációs varázslóban.

A kérelem segítségével áttekintheti a szállítói információkat, és eldöntheti, hogy a szállító regisztrált szállítóvá váljon-e.

A Szállítókérést egy munkafolyamathoz kell küldeni, illetve továbbítani kell a megfelelő ellenőrökhöz és jóváhagyókhoz. A munkafolyamatok beállításával kapcsolatban lásd: [Beszerzésekkel és forrásokkal kapcsolatos munkafolyamatok](procurement-sourcing-workflows.md).

Az alábbi táblázat bemutatja, hogy a szállítókérések milyen állapotúak lehetnek.

| Állapot                     | Leírás |
|----------------------------|-------------|
| Vázlat                      | A szállítókérés még még nincs elküldve. |
| Kérelem benyújtva          | A szállítókérés elküldése megtörtént, és a munkafolyamat első lépése feldolgozás alatt áll. |
| Ellenőrzésre vár             | Ha a munkafolyamatban több ellenőr is található, akkor az egyikük elfogadhatja a szállítókérés ellenőrzésének feladatát, és befejezheti az ellenőrzést. Ha csak egy ellenőr található, akkor ő befejezheti az ellenőrzést a **Befejeződött** opció kiválasztásával a munkafolyamat-műveletben. Neki nem szükséges elfogadnia a munkatételt. |
| Jóváhagyásra váró kérelem   | A szállítókérés továbbításra került a résztvevőkhöz jóváhagyás céljából, és lehetőség van további információk kérésére. Ha további adatokat kér, akkor a munkatétel visszaküldésre kerül a benyújtóhoz. A szállítókérés jóváhagyásra vagy elutasításra is kerülhet ebben az állapotban. |
| Pályázatmódosítási kérelem | A jóváhagyó további információkat kért, és a szállítókérés vissza lett küldve a benyújtó személyhez. A benyújtó hozzáadhatja a szükséges információkat, majd újból benyújthatja a szállítókérést. Ha a szállítókérés újraküldésre kerül, akkor az állapot ismét **Jóváhagyásra váró kérelem** lesz. |
| Kérés jóváhagyva           | Ez az állapot egy végső állapot. |
| Kérelem elutasítva           | Ez az állapot egy végső állapot. |

## <a name="approving-a-vendor-request"></a>Szállítókérés jóváhagyása

Ha a szállítókérés jóváhagyásra kerül, akkor egy szállítói számla jön létre, és a **Jóváhagyott** állapot megjelenik a kezdeti potenciális szállítói regisztrációs kérelmen és a szállítókérésen is.

Mielőtt jóváhagyja a szállítókérést az **Új szállító** oldalon, válasszon egy szállítói csoportot az **Általános** gyorslapon a **Szállítói csoport** opció választásával.

Ha a potenciális szállítói felhasználónak a szállítót képviselő szállítói együttműködéssel kapcsolatos felhasználói hozzáféréssel kell rendelkeznie a Supply Chain Management rendszerhez, akkor állítsa a szállítói együttműködéssel kapcsolatos hozzáférési engedélyt erre: **Igen**. Ha inaktiválni szeretné a potenciális szállító által regisztrálásra használt felhasználói fiókot, akkor állítsa az engedélyt erre: **Nem**.

Ha a szállítói együttműködéssel kapcsolatos hozzáférési engedély erre van állítva: **Igen**, és a szállítókérés jóváhagyásra kerül, akkor elküldésre kerül egy kérelem a felhasználó szerepköreinek módosítására olyan módon, hogy a felhasználó rendelkezzen a **Szállító** típusban, a **Külső szerepkörök** szakaszban leírt szerepkörökkel. Ha az engedély erre van állítva: **Nem**, és a szállítókérés jóváhagyásra kerül, akkor elküldésre kerül egy kérelem a felhasználó inaktiválására. Ebben az esetben be kell állítani a felhasználót inaktiváló munkafolyamatot.

Ahhoz, hogy a szállítókérés jóváhagyásakor egy szállítói számla jöjjön létre, a szállítók szállítókérésekből való létrehozásának számsorozatát erre kell állítani: **Automatikus**.

A szállítói együttműködéssel kapcsolatos felhasználó hozzáférési engedélyeinek áttekintéséért lásd: [Szállítói együttműködés beállítása és fenntartása](set-up-maintain-vendor-collaboration.md).

## <a name="rejecting-a-vendor-request"></a>Szállítókérés elutasítása

A szállítókérés elutasítása esetén meg kell adni az elutasítás okát a szállítókérésben.

Szállítói kérelem elutasításakor elküldésre kerül egy kérelem a felhasználó inaktiválására. Ebben az esetben be kell állítani a felhasználót inaktiváló munkafolyamatot. További információkért lásd: [Szállítói együttműködés beállítása és fenntartása](set-up-maintain-vendor-collaboration.md).

Ha a szállítókérés elutasításra kerül, akkor az **Elutasított** állapot megjelenik a kezdeti potenciális szállítói regisztrációs kérelmen és a szállítókérésen is.

## <a name="deleting-a-prospective-vendor-registration-request-in-various-statuses"></a>Potenciális szállító regisztrálási kérelmének törlése különböző állapotokban

A potenciális szállító regisztrálási kérelmének különböző állapotai áttekintést adnak a kérelem folyamatáról.

A **Törlés** művelet használatával a potenciális szállító regisztrálási kérelmén kiürítheti és eltávolíthatja a létrehozott rekordláncot, és így inaktiválhatja a felhasználói fiókot. A **Törlés** művelet végeredménye a potenciális szállító regisztrálási kérelmének állapotától függően változik, ahogy az alábbi táblázat is mutatja.


|          Állapot          |                                                                                     Állapot leírása                                                                                      |                                                                                                                                                            A törlés művelet végeredménye                                                                                                                                                             |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|           Új            |                                                                         A kérelem nem eredményezett semmilyen műveletet.                                                                          |                                                                                                                                              A potenciális szállító regisztrálási kérelme törlésre került.                                                                                                                                               |
|      Felhasználó kérelmezve      | Ha kiválasztja a <strong>Felhasználó meghívása</strong> opciót, akkor az állapot erre változik: <strong>Felhasználó által kérelmezve</strong>, és egy potenciális felhasználói kérelem jön létre, majd kerül elküldésre egy felhasználói kérelem munkafolyamathoz. |                                                                                                          Nem törölheti ki az ebben az állapotban található potenciális szállító regisztrálási kérelmeket, mivel a felhasználói kérelem munkafolyamat nem fejeződött be.                                                                                                          |
|       Felhasználó meghívva       |                                                               A felhasználói kérelem munkafolyamat jóváhagyásra kerül, és létrejön a felhasználó.                                                               |                                                                                                                      Létrejön egy kérelem a felhasználó inaktiválására, és a potenciális szállító regisztrálási kérelme törlésre kerül.                                                                                                                      |
| Regisztráció folyamatban |                                                         Az új felhasználó bejelentkezett, és elindította a szállítói regisztrációs varázslót.                                                          |                                                                                     Létrejön egy kérelem a felhasználó inaktiválására, és a potenciális szállító regisztrálási kérelme, valamint a szállítói regisztrációs varázslóban megadott adatok törlésre kerülnek.                                                                                      |
|  Szállítókérés létrehozva  |                                                                     A szállítói regisztrációs varázsló befejeződött.                                                                      | Létrejön egy kérelem a felhasználó inaktiválására, és a potenciális szállító regisztrálási kérelme, a szállítói regisztrációs varázslóban megadott adatok, valamint a szállítókérés törlésre kerülnek.<blockquote>[!NOTE]<br>Nem használhatja a <strong>Törlés</strong> műveletet, amikor a szállítókérés ellenőrzési folyamatban van a munkafolyamaton belül.</blockquote> |
|         Engedélyezve         |                                                                               A szállítókérés jóváhagyásra kerül.                                                                               |                                                                                                   A potenciális szállító regisztrálási kérelme, a szállítói regisztrációs varázslóban megadott adatok, valamint a szállítókérés törlésre kerülnek.                                                                                                    |
|         Elutasítva         |                                                                               A szállítókérést elutasították.                                                                               |                                                                                                   A potenciális szállító regisztrálási kérelme, a szállítói regisztrációs varázslóban megadott adatok, valamint a szállítókérés törlésre kerülnek.                                                                                                    |


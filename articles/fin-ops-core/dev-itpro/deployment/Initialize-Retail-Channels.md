---
title: A Commerce Scale Unit (felhő) inicializálása
description: Ez a témakör bemutatja a Commerce Scale Unit (felhő) inicializálását a következőben:Microsoft Dynamics 365 Commerce
author: jashanno
ms.date: 06/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jashanno
ms.search.validFrom: 2018-04-30
ms.openlocfilehash: f9d21de3e498b293394835d5cf564899338b9c18
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2022
ms.locfileid: "9474015"
---
# <a name="initialize-commerce-scale-unit-cloud"></a>A Commerce Scale Unit (felhő) inicializálása

[!include[banner](../includes/banner.md)]

Ez a témakör bemutatja a Commerce Scale Unit (felhő) inicializálását a következőben:Microsoft Dynamics 365 Commerce

Ha 8.1.2.x vagy újabb alkalmazásverziójú Tier-2 postafiókot vagy éles környezetet használ, inicializálni kell a Commerce Scale Unit (felhő) alkalmazást, mielőtt a kiskereskedelmi csatorna funkcióit használni tudja a pénztári (POS) műveletekhez vagy a Retail Server kiszolgálót a felhőben használó e-commerce műveletekhez. Az inicializálás egy Commerce Scale Unit (felhő) telepítésekor

> [!IMPORTANT]
> A kiskereskedelmi csatornák funkcióit a felhőben használó meglévő vevők számára a vállalat folyamatos és folyamatos támogatottságának biztosítása érdekében a Commerce Scale Unit használatához frissíteni kell a kiskereskedelmi csatornákat. A Commerce Scale Unit nélkül telepített új környezetek már nem kapják meg a felhőben tárolt kiskereskedelmi csatorna összetevőinek minőségi és szolgáltatási frissítéseit. Nincs szükség semmilyen műveletre az olyan vevők esetében, akik kizárólag a Commerce Scale Unit (ön által tárolt) egységet használják. Ha szüksége van egy bővítményre, forduljon a Microsoft FastTrack megoldástervezőjhez.

## <a name="prerequisites"></a>Előfeltételek

1. Telepítsen egy Tier-2 boxot vagy éles környezetet, amely 8.1.2.x vagy újabb verziójú.
2. Környezetenként legfeljebb 2 Commerce Scale Egység telepíthető önkiszolgáló rendszerként. Ha környezetenként több Mint 2 Commerce Scale Unit szükséges, Microsoft Dynamics hozzon létre egy támogatási kérést, és adja meg a Commerce Scale Unit **kiegészítő kérését, valamint adja meg a környezet azonosítóját, a Commerce Scale Units számát és a** kívánt adatforrás-régiókat. A kérelem öt munkanapon belül befejeződik. Ha nem szükséges környezetenként 2-nél több Commerce Scale Egység, akkor nem kell létrehozni egy támogatási kérelmet. 
3. A Commerce Scale Unit inicializálása előtt projekttulajdonosi engedélyekkel kell rendelkeznie a Lifecycle Services szolgáltatásban.
4. Győződjön meg arról, hogy a retail licenckulcsok engedélyezve vannak a környezetben. A további tudnivalókat lásd [a Licenckódok és a konfigurációs kulcsok jelentésében](../sysadmin/license-codes-configuration-keys-report.md). A Commerce Scale Unit használata csak akkor használható, ha a következő kulcsok be vannak kapcsolva.

    - RetailBasic
    - RetaileCommerce – ha az E-Commerce használatát tervezi a következőre:Dynamics 365 Commerce
    - RetailGiftCard – ajándékutalványok használata
    - RetailInvent – ha készlet használatát tervezi.
    - RetailModernPos – ha tervezi a pénztár (POS) használatát.
    - RetailReplenishment – ha feltöltéseket tervez.
    - RetailScheduler
    - RetailStores – ha a POS használatát tervezi.


## <a name="region-availability"></a>Régió elérhetősége
A Commerce Scale Unit szolgáltatás a következő régiókban érhető el telepítésre.

| Globális hely | Régió              | Elérhetőség        | Megjegyzések                  |
|-----------------|---------------------|---------------------|---------------------------|
| AMERIKA        | USA keleti régiója             | Általánosan elérhető |  Nincsenek megjegyzések.                         |
| AMERIKA        | USA keleti régiója 2           | Általánosan elérhető |  Nincsenek megjegyzések.                          |
| AMERIKA        | USA északi középső régiója    | Korlátozott kapacitás    |  Nincsenek megjegyzések.                            |
| AMERIKA        | USA déli középső régiója    | Korlátozott kapacitás    |  Nincsenek megjegyzések.                            |
| AMERIKA        | USA középső régiója          | Általánosan elérhető |  Nincsenek megjegyzések.                            |
| AMERIKA        | USA nyugati régiója             | Általánosan elérhető |  Nincsenek megjegyzések.                            |
| AMERIKA        | Nyugat-EGYESÜLT-2           | Általánosan elérhető |  Nincsenek megjegyzések.                            |
| AMERIKA        | Kanada – Közép-Kanada      | Korlátozott kapacitás    |  Nincsenek megjegyzések.                            |
| AMERIKA        | Kanada- és Kelet-         | Korlátozott kapacitás    |   Nincsenek megjegyzések.                           |
| AMERIKA        | Nyugat-Közép-Usa     | Korlátozott kapacitás    |   Nincsenek megjegyzések.                           |
| APAC            | Kelet-Ausztrália      | Általánosan elérhető |   Nincsenek megjegyzések.                           |
| APAC            | Délkelet-Ázsia      | Korlátozott kapacitás | Nem engedélyezett a telepítés.    |
| APAC            | Kelet-Japán          | Általánosan elérhető |  Nincsenek megjegyzések.                            |
| APAC            | Nyugat-Japán          | Általánosan elérhető |   Nincsenek megjegyzések.                           |
| APAC            | Délkelet-Ausztrália | Általánosan elérhető |   Nincsenek megjegyzések.                           |
| APAC            | Kelet-Ázsia           | Korlátozott kapacitás    |   Nincsenek megjegyzések.                           |
| APAC            | India- és Dél-India         | Korlátozott kapacitás | Nem engedélyezett a telepítés.    |
| APAC            | India – Közép-India       | Korlátozott kapacitás    | Jóváhagyási folyamat szükséges. |
| EMEA            | Nyugat-Európa         | Általánosan elérhető    |  Nincsenek megjegyzések. |
| EMEA            | Észak-Európa        | Általánosan elérhető    |  Nincsenek megjegyzések. |
| EMEA            | Egyesült Királyság - Dél            | Általánosan elérhető |    Nincsenek megjegyzések.                          |
| EMEA            | Egyesült Királyság – Nyugat             | Általánosan elérhető |    Nincsenek megjegyzések.                          |
| Uae             | Észak-Egyesült Arab Emírségek           | Korlátozott kapacitás    | Jóváhagyási folyamat szükséges. |

A korlátozott kapacitású régiók telepítési kapacitása rendkívül korlátozott. A telepítésre vonatkozó kéréseket eset szerint kell kiértékelni. Ha üzleti tevékenységre van szükség a korlátozott kapacitású régiókban való telepítéshez, támogatási kérést lehet kérni a várakozási listához való hozzáadásra. A korlátozott kapacitású területek jelenleg nem teszik lehetővé a Commerce Scale Unit telepítését. 

![A régió elérhetőségét mutató leképezés](media/Commerce-Scale-Unit-Region-Availability.png "A régió elérhetőségét mutató leképezés")

## <a name="initialize-commerce-scale-unit-as-part-of-a-new-environment-deployment"></a>Commerce Scale Unit inicializálása új környezettelepítés részeként

Győződjön meg róla, hogy a központ elérhető. Ez szükséges a mérlegegységnek a központnál való regisztrálásához az inicializálási folyamat során. Nem ajánlott olyan mérlegegységet inicializálni, amikor a központ karbantartás alatt áll, mert a karbantartás során esetleg nem lesz elérhető.

1. Győződjön meg róla, hogy a központi környezet elérhető, és nem Karbantartási [módban](../sysadmin/maintenance-mode.md).
2. Az LCS rendszer Környezeti részletek lapján válassza **a Commerce szolgáltatásokat \>**.
3. A Commerce telepítő telepítési lapján válassza az Inicializálás **lehetőséget**.
4. Válassza ki az inicializálni kívánt Commerce Scale Unit verzióját.
5. Válassza ki azt a régiót, amelynél inicializálni kell a Commerce Scale Unit inicializálását.

## <a name="configure-channels-to-use-commerce-scale-unit"></a>Csatornák konfigurálása a Commerce Scale Unit használatára

A Commerce Scale Unit telepítése után gondoskodnia kell arról, hogy a csatornák be vannak állítva az adatbázis használatára. 

A következő lépések szerint konfigurálhatja a csatornákat a Commerce Scale Unit adatbázis használatára.

1. A Commerce Headquarters rendszer a **Retail and Commerce \> Headquarters beállítás \> commerce Scheduler \> Channel adatbázisában található**.
1. A bal oldali ablakban válasszon ki egy csatorna-adatbázist.
1. A Kiskereskedelmi csatorna **gyorslistában** válassza a Hozzáadás **lehetőséget**, majd válassza ki a kiskereskedelmi csatornát a legördülő listából.
1. Válassza **a** Hozzáadás lehetőséget, majd válassza ki az online csatornát a legördülő listából. 

Ha végzett, **menjen a Retail and Commerce Retail és a Commerce \> IT \> Distribution ütemezéshez**, majd futtassa a 9999-es feladatot.

> [!NOTE] 
> A 9999-es feladat minden új terméket és vevőt szinkronizál a Commerce Scale Unit egységgel. Ez a folyamat hosszú ideig is hosszú ideig tart. Ha a csatornának csak az e-commerce webhelyszerkesztő konfigurációjában kell elérhetőnek lennie, a 9999-es feladat helyett a 1070-es feladatot is futtathatja.

### <a name="database-refresh-and-commerce-scale-units"></a>Adatbázis-frissítés és Commerce Scale Units

Mielőtt nekikezd, győződjön meg róla, [hogy jól ismeri a Commerce rendszer funkcióit igénybeó környezetek adatbázis-frissítés utáni lépéseit](../database/database-refresh.md).

A mérlegegység csatorna-adatbázisának rekordjai (a Csatorna-adatbázis képernyőn) nem mozgathatók át több környezetben az adatbázis-frissítés részeként. Ennek az az oka, hogy a rekordok a környezetspecifikus konfigurációnak megfelelőek.

Az adatbázis frissítése után újragenerálhatja a mérlegegység csatorna-adatbázisának rekordját úgy, hogy újra beveszi a mérlegegységet az LCS-be. A mérlegegységben található bármely telepítési vagy karbantartási művelet megpróbálja regisztrálni a mérlegegységet a központnál, ha a regisztráció hiányzóként észlelhető.

A mérlegegység újratelepítését az összetevők módosítása nélkül is kiadhatja úgy, hogy kiválasztja ugyanazt a verziót, amelynél a mérlegegység már telepítve van. Ezt a következő lépések szerint lehet az LCS-knél tenni:

1. Az LCS környezetvédelmi részletek lapján válassza a Kiskereskedelem környezeti **szolgáltatások lehetőséget \>**.
2. A telepítő telepítési lapján válassza ki az újratelepítéshez szükséges mérlegegységet.
3. Válassza a Frissítés lehetőséget a mérlegegység műveleti **menüjében**.
4. Az oldalon a **Select verzió** legördülő ében válassza ki **a Verzió megadása lehetőséget**.
5. A Verzió megadása csoport szövegmezőjében **írja be a** mérlegegységhez látható verziót az **Aktuális** verzió címkéje mellett.
6. Kattintson a Frissítés **gombra**.

A Frissítési bővítményeket **akkor** sem kell kiválasztani, ha korábban már alkalmazta a kiterjesztéseket, mivel a mérlegegységre alkalmazott utolsó kiterjesztéscsomagot a rendszer automatikusan kiválasztja a skálaegység frissítésekségekor.

Ha több mérlegegysége van, akkor a fenti műveletet kell végrehajtania minden egyes mérlegegységnél. Szükség esetén párhuzamosan is végrehajthatja ezeket a műveleteket.

## <a name="deploy-additional-commerce-scale-units-optional"></a>További commerce scale egységek telepítése (nem kötelező)

A Commerce Scale Unit inicializálása után ön telepíthet egy második mérlegegységet is, ha a licenc feljogosítja erre. Ha több mérlegegységet is telepít, akkor egy támogatási kérést kell létrehoznia. A támogatási kérésben a szükséges Commerce Scale Units számot, a környezet nevét és a kívánt régiókat kell megszabadni. A licencelésről a [Dynamics 365 licencelési útmutatója nyújt további tájékoztatást](https://go.microsoft.com/fwlink/?LinkId=866544&clcid=0x409). 

Az alábbi lépések segítségével minden további telepített Commerce Scale Unit egységhez javasoljuk, hogy hozzon létre egy külön csatorna-adatbáziscsoportot.

1. A Commerce commercei központ a **Retail and Commerce > Retail Headquarters > a Retail Scheduler beállítási > Csatorna-adatbáziscsoportban**.
2. Új csatornaadatbázis-csoport létrehozása
3. Menjen a **Retail and Commerce > Retail Headquarters > Retail Scheduler beállításhoz > Csatorna-adatbázishoz**, és válassza ki az újonnan létrehozott Commerce Scale Unitnek megfelelő csatorna-adatbázist.
4. Válassza a **Szerkesztés** lehetőséget, és válassza ki az új csatorna-adatbáziscsoportot.
5. Válassza a **Mentés** lehetőséget.
6. Jelölje be **a Teljes adatszinkronizálás futtatása** lehetőséget a kiválasztott csatorna-adatbázisra.

## <a name="additional-considerations-if-you-initialize-cloud-hosted-commerce-channel-components-in-an-existing-environment"></a>További szempontok a felhőben tárolt Commerce-csatornaösszetevők meglévő környezetben való inicializálása esetén

Ha már a felhőben tárolt Commerce-csatornaösszetevőket használja egy környezetben, a Commerce Scale Unit inicializálása az összetevők frissítése esetén csökkenti a leállást. A Commerce Scale Unit inicializálása előtt további tervezés szükséges.

Amikor az első Commerce Scale Unit inicializálása egy olyan környezetben történik, amely a felhőben tárolt Commerce csatorna-összetevőket használja, az inicializálási folyamat a felhőben tárolt csatornaösszetevőkhöz társított csatornákat az első skálaegységre áttelepítése. A store scale mértékegységekkel társított csatornák nem kapcsolódnak hez.

Az áttelepítési folyamat a csatornák számára transzparens. A mérlegegység inicializálásának indítása után a program automatikusan a következő műveleteket végzi:

1. Létrejön egy új Commerce Scale Unit, amely társítva lesz a környezethez.
2. A Commerce Scale Unit szolgáltatás elérhető csatorna-adatbázisként lesz regisztrálva a központban.
3. A központi Alapértelmezett **csatorna**-adatbázishoz hozzárendelt összes csatorna frissülni fog, hogy az új Commerce Scale Unit egységhez legyen leképezve.
4. A Commerce Data Exchange rendszer (CDX) teljes adatszinkronizálást hajt végre, hogy a csatornaadatokat az új skálaegységre vigye.

**A Commerce Scale Unit** inicializálásának tervezése és tesztelése Általános szabály, hogy a Commerce Scale Unit inicializálása során meg kell terveznie egy ötórás le leállási ablakot az üzletművelet számára, valamint a Retail Server vagy a Felhő Point of Sale típusú e-commerce csatornaműveleteket is.

1. Adatbázis-frissítés végrehajtása a termelési környezetről egy uAT-környezetre. 
2. A Commerce Scale Unit inicializálása az UAT környezetben. 
3. Jegyezze meg a Commerce Scale Unit inicializálási idejét. Ez hasonlít arra az időre, amelyet ez a művelet a termelési környezetben tart, és amelynek során az üzletműveletek és az e-kereskedelmi műveletek nem lesznek elérhetők.

A Commerce Scale Unit inicializálása előtt a következő további lépéseket kell végrehajtania.

- **Az összes POS-műszak bezárása** – az áttelepítés után a POS-felhasználók nem tudják lezárni az áttelepítési folyamat során aktív műszakokat.
- **Az összes P-feladat** sikeres befejezésének ellenőrzése – azt ajánljuk, hogy a P-feladatok szinkronizálják a függőben lévő tranzakciókat, mielőtt AZ inicializálás befejeződik.
- **Az összes POS-eszközből való kijelentkezés** – az áttelepítés során nem támogatottak a POS-műveletek.
- **A POS-terminálon felfüggesztett tranzakciók** visszahívása és érvénytelenítése – a felfüggesztett tranzakciók nem megmaradnak az inicializálás részeként.

> [!IMPORTANT]
> A Commerce Scale Unit inicializálásának részeként a korábbi felfüggesztett tranzakciók elvesznek, ezért nem lehet visszahívni őket. 

Itt történik az inicializálási időszak alatt:

- A felhőben tárolt Commerce-csatornák csak akkor működnek, ha be van kapcsolva a POS offline képesség.
- Az offline képességgel rendelkező POS-eszközök csökkentett funkciókat fognak tartalmazni.
- A Retail Server kiszolgálótól függő összes e-Commerce ügyfél megszakad.
- Ez nem érinti a Commerce Scale Units (ön által tárolt) rendszer által tárolt csatornákat.
- Ez a funkció nincs hatással a head office funkciókra.

Az inicializálás befejezése után a következő történik:

- Az összes aktivált POS-eszköz aktiválási állapota megőrződ, ami azt jelenti, hogy nem kell újraaktiválni az eszközöket.
- A különálló hardverállomás-példányok továbbra is működni fognak.
- A POS csatornaoldali jelentései alaphelyzetbe lesznek állítva, és nem fognak adatokat jelenni az inicializálás előtt.
- A naplóműveletet is alaphelyzetbe állítja, és az inicializálás előtt nem fogja mutatják az adatokat.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

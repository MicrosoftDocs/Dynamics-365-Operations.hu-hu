---
title: A Commerce Scale Unit (felhő) inicializálása
description: Ez a témakör bemutatja, hogyan inicializálható a Commerce Scale Unit (felhő) a következőben:Microsoft Dynamics 365 Commerce.
author: AamirAllaq
ms.date: 02/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: aamiral
ms.search.validFrom: 2018-4-30
ms.openlocfilehash: 84e70515accde161e7efa36755edec68d26be952
ms.sourcegitcommit: fefe93f3f44d8aa0b7e6d54cc4a3e5eca6e64feb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2022
ms.locfileid: "8092222"
---
# <a name="initialize-commerce-scale-unit-cloud"></a>A Commerce Scale Unit (felhő) inicializálása

[!include[banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan inicializálható a Commerce Scale Unit (felhő) a következőben:Microsoft Dynamics 365 Commerce.

Ha Tier-2 sandboxot vagy éles környezetet használ, amely az alkalmazás 8.1.2.x vagy újabb verziójával rendelkezik, akkor inicializálnia kell a Commerce Scale Unit (felhő) funkciót, mielőtt a kiskereskedelmi csatorna funkcióit értékesítési pont (POS) műveletekhez használhatná. vagy a Retail Servert a felhőben használó e-kereskedelmi műveletekhez. Az inicializálás egy kereskedelmi léptékű egységet (felhőt) telepít.

> [!IMPORTANT]
> A felhőben lévő kiskereskedelmi csatorna-funkcionalitást használó meglévő ügyfelek esetében a folyamatos és megszakítás nélküli támogatás érdekében megköveteljük, hogy frissítse kiskereskedelmi csatornáit a Commerce Scale Unit használatára. A Commerce Scale Unit nélkül telepített új környezetek a továbbiakban nem kapnak minőségi és szolgáltatási frissítéseket a felhőben tárolt kiskereskedelmi csatorna-összetevőkre vonatkozóan. Nincs szükség teendőkre azoknak az ügyfeleknek, akik kizárólag a Commerce Scale Unitot (saját üzemeltetésű) használják. Ha bővítményre van szüksége, forduljon a Microsoft FastTrack megoldástervezőjéhez.

## <a name="prerequisites"></a>Előfeltételek

1. 8.1.2.x vagy újabb verziójú Tier-2 sandbox vagy éles környezet üzembe helyezése.
2. Környezetenként legfeljebb 2 kereskedelmi méretegységet telepíthet önállóan. Ha környezetenként 2-nél több kereskedelmi léptékegységre van szüksége, akkor a Microsoft Dynamics Lifecycle Services (LCS), hozzon létre egy támogatási kérelmet, és lépjen be **Kérjen további kereskedelmi mérlegegységet** és adja meg a környezet azonosítóját, a Commerce Scale Units számát és a kívánt adatközponti régiókat. A kérelmet öt munkanapon belül teljesítik. Ha nincs szüksége 2-nél több kereskedelmi méretegységre környezetenként, akkor nem kell támogatási kérelmet létrehoznia. 
3. A Commerce Scale Unit inicializálásához Project Owner engedélyekkel kell rendelkeznie az Lifecycle Services szolgáltatásban.
4. Győződjön meg arról, hogy a kiskereskedelmi licenc konfigurációs kulcsai engedélyezve vannak a környezetben. További információkért lásd [Licenckódok és konfigurációs kulcsok jelentés](../sysadmin/license-codes-configuration-keys-report.md). A Commerce Scale Unit használatához a következő billentyűket kell bekapcsolni.

    - RetailBasic
    - RetaileCommerce – Ha az e-kereskedelmet a következőhöz tervezi használni Dynamics 365 Commerce.
    - RetailGiftCard – Ha ajándékkártyákat szeretne használni.
    - RetailInvent – Ha készletet kíván használni.
    - RetailModernPos – Ha értékesítési pontot (POS) kíván használni.
    - RetailReplenishment – Ha utánpótlást tervez használni.
    - RetailScheduler
    - Kiskereskedelmi üzletek – Ha POS-t tervez használni.


## <a name="region-availability"></a>A régió elérhetősége
A Commerce Scale Unit a következő régiókban telepíthető.

| Globális elhelyezkedés | Régió              | Elérhetőség        |
|-----------------|---------------------|---------------------|
| Egyesült Államok        | USA keleti régiója             | Általánosan elérhető |
| Egyesült Államok        | USA keleti régiója 2           | Általánosan elérhető |
| Egyesült Államok        | USA északi középső régiója    | Általánosan elérhető |
| Egyesült Államok        | USA déli középső régiója    | Általánosan elérhető |
| Egyesült Államok        | USA középső régiója          | Általánosan elérhető |
| Egyesült Államok        | USA nyugati régiója             | Általánosan elérhető |
| Egyesült Államok        | Nyugat-USA 2           | Általánosan elérhető |
| Egyesült Államok        | Kanada középső      | Korlátozott kapacitás    |
| Egyesült Államok        | Kanada Kelet         | Korlátozott kapacitás    |
| Egyesült Államok        | Nyugat-Közép-USA     | Korlátozott kapacitás    |
| APAC            | Kelet-Ausztrália      | Általánosan elérhető |
| APAC            | Délkelet-Ázsia      | Általánosan elérhető |
| APAC            | Kelet-Japán          | Általánosan elérhető |
| APAC            | Nyugat-Japán          | Általánosan elérhető |
| APAC            | Délkelet-Ausztrália | Korlátozott kapacitás    |
| APAC            | Kelet-Ázsia           | Korlátozott kapacitás    |
| APAC            | Dél-India         | Korlátozott kapacitás    |
| APAC            | Közép-India       | Korlátozott kapacitás    |
| EMEA            | Nyugat-Európa         | Általánosan elérhető |
| EMEA            | Észak-Európa        | Általánosan elérhető |
| EMEA            | Egyesült Királyság déli            | Korlátozott kapacitás    |
| EMEA            | UK West             | Korlátozott kapacitás    |

A korlátozott kapacitású régiókban a telepítési kapacitás rendkívül korlátozott. A telepítési kérelmeket eseti alapon értékeljük. Ha kényszerítő üzleti igénye van a korlátozott kapacitású régiókban történő telepítésre, benyújthat támogatási kérelmet, hogy felvegye a várólistára.

![A régió elérhetőségét mutató térkép.](media/Commerce-Scale-Unit-Region-Availability.png "A régió elérhetőségét mutató térkép")

## <a name="initialize-commerce-scale-unit-as-part-of-a-new-environment-deployment"></a>A Commerce Scale Unit inicializálása egy új környezeti telepítés részeként

Kérjük, győződjön meg arról, hogy a központ elérhető. Ez szükséges ahhoz, hogy az inicializálási folyamat során regisztrálják a mérlegegységet a központban. Nem javasolt a mérlegegység inicializálása, amikor a központ szervizelés alatt áll, mert előfordulhat, hogy a szervizelési folyamat során nem lesz elérhető.

1. Győződjön meg arról, hogy a központ környezete elérhető, és nincs benne [Karbantartás Mód](../sysadmin/maintenance-mode.md).
2. Az LCS-ben a környezet részleteinek oldalán válassza a lehetőséget **Környezeti jellemzők \> kereskedelem**.
3. A Kereskedelmi beállítások üzembe helyezése oldalon válassza a lehetőséget **Inicializálja**.
4. Válassza ki a Commerce Scale Unit inicializálandó verzióját.
5. Válassza ki a régiót a Commerce Scale Unit inicializálásához.

## <a name="configure-channels-to-use-commerce-scale-unit"></a>Konfigurálja a csatornákat a Commerce Scale Unit használatához

A Commerce Scale Unit telepítése után meg kell győződnie arról, hogy a csatornái az adatbázis használatára vannak beállítva. 

Ha csatornáit a Commerce Scale Unit adatbázis használatára szeretné beállítani, kövesse az alábbi lépéseket.

1. A Kereskedelmi központban lépjen a következőre: **Kiskereskedelem és kereskedelem \> A központ felállítása \> Kereskedelmi ütemező \> Csatorna adatbázis**.
1. A bal oldali ablaktáblában válasszon ki egy csatornaadatbázist.
1. A **Kiskereskedelmi csatorna** FastTab, válassza ki **Hozzáadás**, majd válassza ki kiskereskedelmi csatornáját a legördülő listából.
1. Válassza ki **Hozzáadás**, majd válassza ki online csatornáját a legördülő listából. 

Ha végzett, menjen a következőre **Kiskereskedelem és kereskedelem \> Kiskereskedelmi és kereskedelmi IT \> Elosztási ütemterv**, és futtassa a 9999-es feladatot.

> [!NOTE] 
> A Job 9999 szinkronizálja az összes új terméket és ügyfelet a Commerce Scale Unit-hoz. Ez a folyamat sokáig tarthat. Ha a csatornának csak az e-kereskedelmi webhely-készítő konfigurálásához kell elérhetőnek lennie, akkor a 9999-es helyett futtathatja az 1070-es feladatot.

### <a name="database-refresh-and-commerce-scale-units"></a>Adatbázis frissítése és Kereskedelmi Scale Units

Mielőtt elkezdené, győződjön meg arról, hogy ismeri [A Commerce funkciót használó környezetek adatbázis-frissítését követően végrehajtandó lépések](../database/database-refresh.md).

A méretezési egység csatorna adatbázis-rekordjai (a Csatornaadatbázis űrlapon) nem mozgathatók át a környezetek között az adatbázis-frissítés részeként. Ennek az az oka, hogy a rekordok környezetspecifikus konfigurációt képviselnek.

Az adatbázis frissítése után újragenerálhatja a méretezési egység csatornaadatbázis-rekordját a méretezési egység LCS-ben történő újratelepítésével. A mérlegegység bármely telepítési vagy szervizelési művelete megkísérli regisztrálni a mérlegegységet a központban, ha a regisztráció hiányzik.

Kiadhatja a méretezési egység újratelepítését az összetevők módosítása nélkül, ha kiválasztja a méretezési egység verziójának telepítését. Ez az LCS-ben a következő lépésekkel tehető meg:

1. Az LCS-ben a környezet részleteinek oldalán válassza a lehetőséget **Környezeti jellemzők \> Kiskereskedelem**.
2. A telepítési telepítési oldalon válassza ki az újratelepíteni kívánt méretezési egységet.
3. A mérleg egység műveleti menüjében válassza a lehetőséget **Frissítés**.
4. A csúszkán, a legördülő listán **Válasszon verziót**, válassza ki a lehetőséget **Adjon meg egy verziót**.
5. Alatti szövegdobozban **Adjon meg egy verziót**, írja be a skálaegységhez tartozó verziót, amely a mellett látható **Jelenlegi verzió** címke.
6. Kattintson **Frissítés** gomb.

Nem kell kiválasztani **Frissítse a bővítményeket**, még akkor is, ha korábban alkalmazott bővítményeket, mivel a skálaegység frissítésekor a rendszer automatikusan kiválasztja a skálaegységre utoljára alkalmazott bővítménycsomagot.

Ha több mérlegegysége van, akkor a fenti műveletet minden mérlegegységnél el kell végeznie. Ha szükséges, ezeket a műveleteket párhuzamosan is elvégezheti.

## <a name="deploy-additional-commerce-scale-units-optional"></a>További kereskedelmi mérlegegységek telepítése (opcionális)

A Commerce Scale Unit inicializálása után önállóan telepíthet egy második mérlegegységet, ha a licence feljogosítja erre. Kettőnél több méretezési egység telepítéséhez támogatási kérelmet kell létrehoznia. A támogatási kérelemben adja meg a szükséges kereskedelmi léptékű egységek számát, a környezet nevét és a kívánt régiókat. Az engedélyezéssel kapcsolatos további információkért lásd: [Dynamics 365 licencelési útmutató](https://go.microsoft.com/fwlink/?LinkId=866544&clcid=0x409). 

Javasoljuk, hogy minden további telepített kereskedelmi léptékű egységhez hozzon létre egy külön csatornaadatbázis-csoportot az alábbi lépések végrehajtásával.

1. A Kereskedelmi központban keresse fel a következőt: **Kiskereskedelem és kereskedelem >Retail Headquarters > Kiskereskedelmi ütemező beállítása > Csatorna adatbázis-csoport**.
2. Új csatornaadatbázis-csoport létrehozása
3. Menj a **Kiskereskedelem és kereskedelem >Retail Headquarters > Kiskereskedelmi ütemező beállítása > Csatornaadatbázis**, és válassza ki az újonnan létrehozott kereskedelmi skálaegységnek megfelelő csatornaadatbázist.
4. Válassza ki **Szerkesztés** és válassza ki az új csatorna adatbázis-csoportot.
5. Válassza a **Mentés** lehetőséget.
6. Válassza ki **Futtassa a Teljes adatszinkronizálást** a kiválasztott csatorna adatbázishoz.

## <a name="additional-considerations-if-you-initialize-cloud-hosted-commerce-channel-components-in-an-existing-environment"></a>További megfontolások, ha meglévő környezetben inicializálja a felhőalapú kereskedelmi csatorna összetevőit

Ha már használ felhőben tárolt kereskedelmi csatorna-összetevőket egy környezetben, a Commerce Scale Unit inicializálása segít csökkenteni az összetevők frissítése utáni leállást. További tervezésre van szükség a Commerce Scale Unit inicializálása előtt.

Amikor inicializálja az első Commerce Scale Unit olyan környezetben, amely felhőalapú kereskedelmi csatorna-összetevőket használ, az inicializálási folyamat áttelepíti a felhőben tárolt csatornakomponensekhez társított csatornáit az első méretezési egységhez. A Store Scale egységekhez társított csatornákat ez nem érinti.

A migrációs folyamat átlátható a csatornák számára. A skálaegység inicializálásának megkezdése után a következő műveletek automatikusan végrehajtásra kerülnek:

1. Egy új Kereskedelmi Scale Unit jön létre, és hozzá lesz rendelve a környezethez.
2. A Commerce Scale Unit elérhető csatornaadatbázisként lesz regisztrálva a központban.
3. Minden csatorna hozzárendelve a **Alapértelmezett** A központban lévő csatornaadatbázis frissítésre kerül, hogy megfeleljen az új kereskedelmi léptékű egységnek.
4. A Commerce Data Exchange (CDX) teljes adatszinkronizálásra kerül sor, hogy a csatornaadatokat az új skálaegységhez hozzák.

**A Commerce Scale Unit inicializálásának tervezése és tesztelése** Általános szabály, hogy a Commerce Scale Unit inicializálása során ötórás leállási időszakot kell beterveznie a bolti műveletekhez, valamint minden olyan e-kereskedelmi csatornaművelethez, amely Retail Servert vagy Cloud Point of Sale-t használ.

1. Végezzen adatbázis-frissítést éles környezetből sandbox UAT környezetbe. 
2. Inicializálja a Commerce Scale Unitot a sandbox UAT környezetben. 
3. Jegyezze fel a Commerce Scale Unit inicializálási idejét. Ez összehasonlítható lesz azzal az idővel, ameddig ez a művelet a termelési környezetben vesz igénybe, amely alatt az áruházi műveletek és az e-kereskedelmi műveletek nem lesznek elérhetők.

A Commerce Scale Unit inicializálása előtt végre kell hajtania a következő további lépéseket.

- **Zárja be az összes POS műszakot** - Az áttelepítés után a POS-felhasználók nem zárhatják be az áttelepítési folyamat során aktív műszakokat.
- **Ellenőrizze, hogy az összes P-feladat sikeresen befejeződött-e** - Javasoljuk, hogy a függőben lévő tranzakciók szinkronizálására szolgáló P-jobok befejeződjenek a CSU inicializálása előtt.
- **Jelentkezzen ki az összes POS-eszközről** - A POS műveletek nem támogatottak az áttelepítés során.
- **Az összes felfüggesztett tranzakció visszahívása és érvénytelenítése a POS-ban** - A felfüggesztett tranzakciók nem maradnak meg az inicializálás részeként.

> [!IMPORTANT]
> A Commerce Scale Unit inicializálásának részeként a korábban felfüggesztett tranzakciók elvesznek, és nem hívhatók vissza. 

Íme, mi történik az inicializálási időszakban:

- A felhőalapú kereskedelmi csatornák nem működnek, hacsak be nem kapcsolja a POS offline funkciót.
- A bekapcsolt offline funkcióval rendelkező POS-eszközök funkcionalitása csökkent.
- A Retail Servertől függő e-kereskedelmi kliensek működése megszakad.
- A Commerce Scale Units (saját hosztolású) csatornákat ez nem érinti.
- A központi iroda működését ez nem érinti.

Íme, mi történik az inicializálás befejezése után:

- Az összes aktivált POS eszköz eszközaktiválási állapota megmarad, ami azt jelenti, hogy az eszközöket nem kell újra aktiválni.
- Az önálló hardverállomás-példányok továbbra is működni fognak.
- A POS-csatorna oldali jelentések alaphelyzetbe állnak, és nem jelenítik meg az inicializálás előtti adatokat.
- A napló megjelenítése művelet szintén alaphelyzetbe áll, és nem jelennek meg az inicializálás előtti adatok.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

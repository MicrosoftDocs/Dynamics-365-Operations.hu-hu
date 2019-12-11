---
title: Az ügyfélkör áttekintése
description: Ez a témakör a kiskereskedelmi üzleti szolgáltatásban rendelkezésre álló új ügyfélkör-kezelési lehetőségekről ad áttekintést.
author: bebeale
manager: AnnBe
ms.date: 11/01/19
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: Version 10.0.7
ms.openlocfilehash: fb58022f61f9944d6e385874db1f2342bc111866
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773977"
---
# <a name="clienteling-overview"></a>Az ügyfélkör áttekintése

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Számos kiskereskedő (különösen a felső kategóriás, speciális kiskereskedők) azt szeretné, hogy az értékesítési munkatársak hosszú távú kapcsolatot létesítsenek a legfontosabb ügyfelekkel. A munkatársaknak ismerniük kell az ezen ügyfelek által kedvelt és nem kedvelt termékeket, az ügyfelek vásárlási előzményeit, termékpreferenciáit, illetve a hozzájuk kötődő fontos dátumokat, például az évfordulókat vagy a születésnapokat. A munkatársaknak olyan helyre van szükséges, ahol rögzíthetik ezeket az adatokat, és szükség esetén könnyen megtalálják őket. Ha ezek az információk egyetlen nézetben érhetők el, a munkatársak egyszerűen megcélozhatják az adott feltételeknek megfelelő vevőket. Megtalálják például az összes olyan vevőt, aki szívesen vásárolna kézitáskát, vagy akinél fontos esemény – például születésnap vagy évforduló – közeledik.

## <a name="client-book"></a>Ügyfélkönyv

A Microsoft Dynamics 365 Retail rendszerben a kiskereskedők az ügyfélkönyv funkcióval segítséget nyújthatnak a bolti munkatársaknak, hogy ők tartós kapcsolatot tudjanak létesíteni a legfontosabb vevőkkel.

Az ügyfélkönyv tartalmazza azokat a vevői kártyákat, amelyek az egyes vevők kapcsolattartási adatai mellett három további, a kiskereskedő által meghatározott és a Retail Headquarters alkalmazásban beállított további tulajdonságot jelenítenek meg. A kiskereskedők határozhatják meg azt a három legfontosabb dolgot, amit az értékesítési munkatársaknak tudniuk kell a vevőkről. Egy ékszerbolt esetében például érdemes lehet felvenni a fontos dátumokat – például az évfordulókat vagy a születésnapokat –, mivel ezek a dátumok olyan alkalmak, amikor általában több ékszert szoktak vásárolni. Egy ruházati üzletben pedig fontos lehet nyilvántartani a vevő által preferált márkákat.

Az ügyfélkönyv azt is lehetővé teszi, hogy a munkatársak úgy szűrjék a listát, hogy csak azok a vevők jelenjenek meg, akik adott feltételeknek megfelelnek. Egy új cipőkollekció érkezésekor például a munkatárs olyan vevőket szeretne tájékoztatni, akik gyakran vásárolnak cipőt. Ebben az esetben a munkatárs úgy szűrheti az ügyfélkönyvet, hogy megtalálja a megfelelő vevőket – ezután pedig további lépéseket tehet.

Ha egy vevő valamiért már nem tekinthető kulcsfontosságú vevőnek, ezért nem kell annyi időt ráfordítani, akkor az értékesítési munkatárs eltávolíthatja az ügyfélkönyvből.

Egyes kiskereskedők nem az értékesítési munkatársak szintjén szeretnék kezelni a vevőket, hanem az üzlet szintjén kezelnék a legfontosabb vevők listáját. Az ilyen kiskereskedők megtekinthetik az üzlet ügyfélkönyveiben lévő vevőket. Ennek a lehetőségnek a használatával a kiskereskedők az összes olyan értékesítési munkatárs ügyfélkönyvéből származó vevőket megtekinthetik, akinek a címjegyzéke megegyezik az aktuális üzlet címjegyzékével. Ilyen módon, ha egy munkatárs a jogi személy több üzletében dolgozik, akkor az ügyfélkönyv az összes ilyen üzlet vevőit megjeleníti. Ez a funkció további funkciókat is támogat. A vevők például átrendelhetők az egyik munkatárstól egy másikhoz. Ez a lehetőség akkor hasznos, ha a munkatársakat áthelyezik, vagy kilépnek a cégtől.

Minden értékesítési munkatárshoz jogi személyenként egy ügyfélkönyv tartozhat. A munkatársak több vevőt is hozzáadhatnak az ügyfélkönyvhöz. A Retail alkalmazásban a vevők jelenleg csak egy ügyfélkönyvbe vehetők fel. A Microsoft azonban egy olyan funkció hozzáadását tervezi, amely lehetővé teszi, hogy egy vevőt több ügyfélkönyvbe is fel lehessen venni.

> [!NOTE]
> A vevőkeresési funkciótól eltérően az ügyfélkönyv nem szűri a vevői rekordokat az üzlet címjegyzékei alapján.

## <a name="activities-and-notes"></a>Tevékenységek és jegyzetek

Az online csatornák lehetővé teszik, hogy a kiskereskedők anélkül ismerjék meg a vevői preferenciákat, hogy a vevők kifejezetten megadnák ezeket az információkat. Ezzel szemben, amikor a vevők kapcsolatba lépnek az üzletben lévő értékesítési munkatársakkal, közvetlenül megadják a preferenciáikat. Ez az információ azonban elveszhet a vásárlás után. Ha viszont ezeket az adatokat rögzítik, a kiskereskedők könnyebben megérthetik a vevőket, így jobb ajánlatokat és kellemesebb általános vásárlási élményt kínálhatnak nekik.

A vevők által megosztott kulcsfontosságú adatok rögzítéséhez az értékesítési munkatársak nemcsak az ügyfélkönyv attribútumait használhatják, hanem a tevékenységek és a megjegyzések funkcióját is. A kiskereskedők módosíthatják a tevékenységtípusokat, például az üzlet meglátogatására vonatkozó adatokat, az e-mail-címet, a telefonszámot és a találkozókat. A munkatársak által létrehozott tevékenységek idővonalként tekinthetők meg a pénztárban. Az adatok a Retail Headquarters **Tevékenyégek** lapján (**Minden vevő \> Általános** oldal) is megtekinthetők.

Az értékesítési munkatársak a megjegyzések segítségével olyan általános vevői adatokat rögzíthetnek, amelyek megtekinthetők az egyes interakciók előtt. Ezeket a megjegyzéseket a Retail Headquarters alkalmazásba menti a rendszer; a megjegyzések a vevői profilban vagy a hívásközpont telefonos ügyfélrészleteket tartalmazó oldalán tekinthetők meg.

> [!NOTE]
> Jelenleg minden megjegyzést és tevékenységet megtekinthet az adott jogi személy minden olyan értékesítési munkatársa, aki megtekintheti a vevőkre vonatkozó részleteket tartalmazó lapokat. A megjegyzések és a tevékenységeket nem csak az a munkatárs használhatja, aki felvette a vevőt az ügyfélkönyvbe.

## <a name="integration-with-dynamics-365-customer-insights"></a>Integráció a Dynamics 365 Customer Insights rendszerrel

A Dynamics 365 Customer Insights alkalmazás használatával a kiskereskedők összesíthetik a különböző olyan rendszerek adatait, amellyel a vevők kapcsolatot tartanak a kiskereskedő márkájával. Ezt követően ezeket az adatokat használva egyetlen nézetet hozhatnak létre a vevőhöz, és statisztikákat hozhatnak létre. A Customer Insights és a Retail integrációjával a kiskereskedők kiválaszthatnak olyan intézkedéseket, amelyeket meg kell jeleníteni az ügyfélkönyvben lévő vevői kártyán. A kiskereskedők például a Customer Insights adatai alapján kiszámítják a vevő „lemorzsolódásának valószínűségét”, és meghatározhatják a „következő legjobb műveletet”. Ha ezeket az értékeket intézkedésként definiálják, akkor a vevői kártyán is megjelenhetnek, és fontos információként szolgálhatnak az értékesítési munkatársak számára. A Customer Insights rendszerről a [Dynamics 365 Customer Insights](https://docs.microsoft.com/dynamics365/ai/customer-insights/overview) dokumentációjában található további információ. További információ az intézkedésekről: [Intézkedések](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).

## <a name="set-up-clienteling"></a>Az ügyfélkör beállítása

Ha be szeretné kapcsolni az Ügyfélkör funkciót, hajtsa végre az alábbi lépéseket.

1. A **Funkciókezelés** munkaterületen szűrje a modulokat a **Kiskereskedelem és kereskedelem** modul szerint.

    ![Az Ügyfélkör a Kiskereskedelem és kereskedelem modul szolgáltatásainak listájában](./media/Enable_clienteling.png "Az Ügyfélkör a Kiskereskedelem és kereskedelem modul szolgáltatásainak listájában")

2. Kapcsolja be az **Ügyfélkör** funkciót az **Engedélyezés most** lehetőséggel.
3. A **Kiskereskedelmi paraméterek** oldal **Számsorozat** lapján válassza ki az **Ügyfélkönyv azonosítója** sort. A **Számsorozat kódja** mezőben válasszon ki egy számsorozatot. A rendszer ezt a számsorozatot fogja használni az ügyfélkönyvekhez tartozó azonosítók hozzárendeléséhez.
4. Válassza a **Mentés** lehetőséget.
5. Hozzon létre egy olyan új attribútumcsoportot, amely tartalmazza azokat az attribútumokat, amelyeket rögzíteni szeretne az ügyfélkönyvekben kezelt vevőkhöz. Utasítások: [Attribútumok és attribútumcsoportok](https://docs.microsoft.com/dynamics365/retail/attribute-attributegroups-lifecycle).

    - A szükséges attribútumokat **Szűkíthetőként** definiálja. Az értékesítési munkatársak ezután ezekkel az attribútumokkal szűrhetik az ügyfélkönyvüket.
    - Állítsa be a megjelenítési sorrendet ezekhez az attribútumokhoz. Ez a megjelenítési sorrend határozza meg, hogy melyik attribútumok jelenjenek meg az ügyfélkönyv vevői kártyáján. Az 1. helyen lévő elem magasabb, mint a 2. helyen lévő. Ennek megfelelően az 1. megjelenítési helyen lévő attribútum előbb megjelenik, mint a 2. helyen lévő.

    > [!NOTE]
    > A Customer Insights ugyanarról az oldalról is elérhetővé tehető. Ehhez azonban Azure-alkalmazásazonosítót és titkos kulcsot kell létrehozni a hitelesítéshez. (A követelményekkel kapcsolatos további tudnivalók a témakör később következő, [A Customer Insights és a Retail integrációjának bekapcsolása](#turn-on-the-integration-of-customer-insights-with-retail) című szakaszában találhatók.) Ha be van kapcsolva a Customer Insights, és kiválaszt legalább egy olyan intézkedést, amelyet meg akar jeleníteni a vevő kártyáján, akkor ezek az intézkedések jelennek meg először. Ezután az ügyfélkönyv attribútumcsoportjai jelennek meg, a megjelenítési sorrend alapján. Ha például két intézkedést választ a Customer Insights rendszerből, akkor ez a két intézkedés és az ügyfélkönyv egyik attribútuma jelenik meg a vevő kártyáján. (Az ügyfélkönyv megjelenített attribútuma az az attribútum lesz, amelyik a legmagasabban van a megjelenítési sorrendben.)

6. A **Kiskereskedelmi paraméterek** oldal **ügyfélkör** lapjának **Ügyfélkönyv attribútumcsoportja** mezőjében válassza ki az éppen létrehozott attribútumcsoportot.

    ![Ügyfélkönyv kijelölt attribútumcsoportja](./media/Client%20book%20attributes.png "Ügyfélkönyv kijelölt attribútumcsoportja")

7. Ha rögzíteni szeretné a pénztári tevékenységeket, határozza meg a tevékenységtípusokat a **Tevékenységtípusok** oldalon (**Kiskereskedelem \> Vevők \> Tevékenységtípusok**).

    > [!NOTE]
    > A tevékenységtípusokat a Retail Server kéri le, amikor először kezdeményez valós idejű hívást. A tevékenységeket a lekérésük után néhány órán át gyorsítótárazza a rendszer. Ha módosítja a tevékenységtípusokat, várja meg, amíg a gyorsítótár érvénytelen lesz. Másik lehetőségként – nem termelési környezetek esetében – indítsa újra a Retail Server szolgáltatást.

8. Vegyen fel két gombot a megfelelő pénztári képernyő-elrendezésre, hogy az értékesítési munkatársak megtekinthessék a saját ügyfélkönyvüket és az üzlet ügyfélkönyvét. (Az üzlet ügyfélkönyvei között az összes olyan munkatárs ügyfélkönyvében szereplő ügyfél megtalálható, aki közös címjegyzéket használ az üzlettel.) A megfelelő műveletek neve **Vevők megtekintése az ügyfélkönyvben** és **A bolt ügyfélkönyvéből származó vevők megtekintése**. Az ügyfélkönyvekhez kapcsolódóan három további művelet érhető el. Ezek a műveletek határozzák meg, hogy melyik munkatársak adhatnak hozzá vevőket az ügyfélkönyvhöz, távolíthatnak el vevőket onnan, illetve rendelhetnek hozzá újra vevőket. A műveletek neve: **Vevő hozzáadása az ügyfélkönyvhöz**, **Vevő eltávolítása az ügyfélkönyvből**és **Vevő újbóli hozzárendelése az ügyfélkönyvhöz**.
9. Futtassa a következő felosztásütemezési feladatokat: 1040, 1150, 1110 és 1090.

Miután elvégezte ezt az eljárást, az értékesítési munkatársak meg tudják nyitni a vevő részleteit tartalmazó lapot a pénztárban, és hozzá tudnak adni vevőket az ügyfélkönyvhöz, megtekinthetik és rögzíthetik a vevőkhöz tartozó tevékenységeket és jegyzeteket, valamint a vevők és az ügyfélkönyv attribútumaival megcélozhatnak vevőket az ügyfélkönyv szűrésére. A következő ábrán az ügyfélkönyv képe látható.

![Példa ügyfélkönyvre](./media/client_book.png "Példa ügyfélkönyvre")

## <a name="turn-on-the-integration-of-customer-insights-with-retail"></a>A Customer Insights és a Retail integrációjának bekapcsolása

Ha be szeretné kapcsolni a Customer Insights és a Retail integrációját, akkor a Customer Insights aktív példányával kell rendelkeznie, annál a bérlőnél, amelyikhez a Retail telepítve van. Olyan Azure Active Directory- (Azure AD) felhasználói fiókkal is rendelkeznie kell, amelyhez tartozik Azure-előfizetés.

Az integráció beállításához hajtsa végre az alábbi lépéseket.

1. Az Azure-portálon regisztráljon egy pályázatot. Ezt a pályázatot használja majd a hitelesítéshez a Customer Insights rendszerhez. További tudnivalók: [Rövid útmutató: Pályázatok regisztrálása a Microsoft Identity platformmal](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).
2. Hozzon létre titkos kulcsot a pályázathoz. Jegyezze fel a titkos kulcsot, és őrizze meg, mert később szüksége lesz rá. Adja meg a titkos kulcs lejárati idejét is.

    > [!IMPORTANT]
    > Ügyeljen rá, hogy a lejárat előtt módosítani kell a titkos kulcsot, ellenkező esetben az integráció váratlanul megszűnik.

3. Hozzon létre Azure Key Vault tárolót, és mentse a pályázat titkos kulcsát. Lépések: [Rövid útmutató: Titkos kulcs beállítása és lekérése az Azure Key Vault tárolóból az Azure-portál használatával](https://docs.microsoft.com/azure/key-vault/quick-create-portal).
4. A Retail rendszerben kapcsolja be a hozzáférést az Azure Key Vault tárolóhoz. A lépés végrehajtásához rendelkeznie kell pályázatazonosítóval és titkos kulccsal. A pályázat lehet az 1. lépésben létrehozott pályázat, de lehet új is. (Más szóval az 1. lépésben létrehozott pályázat használható a Key Vaulthoz és a Customer Insights szolgáltatáshoz való hozzáféréshez, de az egyes hozzáférésekhez létrehozhat egyedi pályázatot is.) További tudnivaló: [Szolgáltatás elsődleges hitelesítő adatainak tárolása az Azure Stack Key Vault tárolóban](https://docs.microsoft.com/azure-stack/user/azure-stack-key-vault-store-credentials?view=azs-1908#create-a-service-principal).
5. A Retail Headquarters alkalmazásban lépjen a **Rendszerfelügyelet \> Beállítás \> Kulcstároló paraméterei** részre, és adja meg a szükséges adatokat a kulcstárolóhoz. Ezt követően a **Kulcstárolóügyfél** mezőbe írja be a 4. lépésben használt pályázati azonosítót, hogy a Retail hozzáférjen a kulcstárolóban lévő titkos kulcshoz.
6. Ha hozzá szeretné adni az 1. lépésben létrehozott pályázatot a biztonságos pályázatok listájához, nyissa meg a Customer Insights szolgáltatást, és adjon **Megtekintési** hozzáférést a pályázathoz. További tájékoztatás: [Engedélyek](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-permissions).
7. A Retail szolgáltatás **Kiskereskedelmi paraméterek** oldalán lévő **Ügyfélkör** lap **Dynamics 365 Customer Insights** gyorslapján hajtsa végre a következő lépéseket:

    1. A **Pályázat azonosítója** mezőbe írja be az 1. lépésben használt pályázati azonosítót.
    2. A **Titkos kulcs neve** mezőbe írja be az 5. lépésben létrehozott, a kulcstárolóban lévő titkos kulcs nevét.
    3. A **Customer Insights engedélyezése** beállításnál adja meg az **Igen** értéket. Ha a beállítás valamiért nem sikerül, akkor hibaüzenet jelenik meg, és a beállítás értéke **Nem** lesz.
    4. A Customer Insights szolgáltatásban több környezet is használható (pl. tesztkörnyezet és termelési környezet). A **Környezeti példányazonosítója** mezőbe írja be a megfelelő környezetet.
    5. A **Másodlagos vevőazonosító** mezőbe írja be a Customer Insights azon tulajdonságát, amelyet hozzárendelt a vevő számlaszámához. (A Retail szolgáltatásban a vevő számlaszáma a vevőazonosító.)
    6. A fennmaradó három tulajdonság az az intézkedés, amely megjelenik az ügyfélkönyvben lévő vevői kártyán. Legfeljebb három intézkedés jeleníthető meg a vevő kártyáján. (Nem kötelező azonban intézkedéseket megadni.) A korábban említettek szerint a rendszer ezeket az értékeket jeleníti meg először, majd az ügyfélkönyv attribútumcsoportjának az értékeit.
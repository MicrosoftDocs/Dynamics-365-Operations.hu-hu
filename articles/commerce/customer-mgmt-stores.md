---
title: Vevők kezelése az üzletekben
description: Ez a témakör bemutatja, hogyan engedélyezhetik a kiskereskedők a vevőkezelési képességeket a pénztárnál (POS) a Microsoft Dynamics 365 Commerce szolgáltatásban.
author: josaw1
manager: AnnBe
ms.date: 03/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 8a1b360ba6a2d32e38e101f25f108094a00190c8
ms.sourcegitcommit: 8a14eac1c27f10c2b1b02ac9ad82339f5e127602
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2021
ms.locfileid: "5555047"
---
# <a name="customer-management-in-stores"></a>Vevők kezelése az üzletekben

[!include [banner](includes/banner.md)]

Ez a témakör bemutatja, hogyan engedélyezhetik a kiskereskedők a vevőkezelési képességeket a pénztárnál (POS) a Microsoft Dynamics 365 Commerce szolgáltatásban.

Fontos, hogy az üzlet munkatársai vevőrekordokat hozhassanak létre és szerkeszthessenek a pénztárban. Ily módon rögzíthetik a vevői adatok esetleges frissítéseit, például az e-mail-címet, a telefonszámot és a címet. Ez az információ hasznos az olyan alsóbb rétegbeli rendszerekben, mint a marketing, mivel ezeknek a rendszereknek a hatékonysága az ügyféladatok pontosságától függ.

Az értékesítési munkatársak két pénztári belépési pontból tudják aktiválni a vevő létrehozásának munkafolyamatát. Kiválaszthat egy, a **Vevő hozzáadása** nevű művelethez hozzárendelt gombot, vagy k Keresési eredmények oldalon az alkalmazássávon a **Vevő létrehozása** lehetőséget. Mindkét esetben megjelenik az **Új vevő** párbeszédpanel, ahol az értékesítési munkatárs megadhatja a vevő szükséges adatait, például a vevő nevét, e-mail-címét, telefonszámát, címét és az üzleti tevékenység számára esetleges további, releváns információkat. Ezek a kiegészítő információk a vevőhöz társított vevőattribútumok segítségével is rögzítethetők. A vevőattribútumokkal kapcsolatos további tudnivalókat lásd: [Vevőattribútumok](dev-itpro/customer-attributes.md).

Az értékesítési munkatárs másodlagos e-mail-címeket és telefonszámokat is rögzíthet. Ezenkívül rögzítheti, hogy a vevő a másodlagos e-mail-címek vagy telefonszámok egyikén fogad-e marketinginformációkat. A funkció engedélyezéséhez a kiskereskedőknek be kell kapcsolniuk a **Több e-mail és telefonszám rögzítése és a marketinghez való hozzájárulás ezen kapcsolatok esetén** funkciót a Commerce központi felületének **Funkciókezelés** munkaterületén (**Rendszerfelügyelet \> Munkaterületek \> Funkciókezelés**).

## <a name="default-customer-properties"></a>Alapértelmezett vevőtulajdonságok

A kiskereskedők használhatják az **Összes üzlet** oldalt a Commerce központi felületén (**Retail és Commerce \> Csatornák \> Üzletek**) arra, hogy egy alapértelmezett vevőt társítsanak az egyes üzletekhez. A Commerce rendszer ezután átmásolja az alapértelmezett vevőhöz meghatározott tulajdonságokat az összes létrehozott új vevőrekordba. Például a **Vevő létrehozása** párbeszédpanelen azok a tulajdonságok jelennek meg, amelyek az üzlethez társított alapértelmezett vevőhöz vannak társítva. Ilyen tulajdonságok például a vevő típusa, a vevőcsoport, a kívánt nyugta, a pénznem és a nyelv. A fiókok (vevői csoportok) is az alapértelmezett vevőtől öröklődnek. A pénzügyi dimenziók azonban attól a vevői csoporttól öröklődnek, amely az alapértelmezett vevőhöz van társítva, nem pedig magától az alapértelmezett vevőtől.

Az értékesítési munkatársak több címet is rögzíthetnek egy vevőhöz. A vevő neve és telefonszáma az egyes címekhez társított kapcsolattartási adatokból öröklődik. A vevőrekord **Címek** gyorslapja tartalmaz egy **Cél** mezőt, amelyet az értékesítési munkatársak módosíthatnak. Ha a vevő típusa **Személy**, az alapértelmezett érték a **Kezdőlap**. Ha a vevő típusa **Szervezet**, az alapértelmezett érték a **Vállalat**. A mező által támogatott egyéb értékek közé tartozik a **Kezdőlap**, az **Iroda** és a **Postaláda**. A cím **Ország** mezőjének értéke abból az elsődleges címből öröklődik, amely a Commerce központi felületében az **Üzemi egység** oldalon van megadva a **Szervezeti adminisztráció \> Szervezetek \> Üzemi egységek** pontban.

## <a name="sync-customers-and-async-customers"></a>Szinkron vevők és Aszinkron vevők

A Commerce rendszerben két lehetőség van vevők létrehozására: a szinkron (vagy Sync) és az aszinkron (vagy Async). Alapértelmezés szerint a vevők létrehozása szinkronban történik. Más szóval a Commerce központi felületén jönnek létre valós időben. A Szinron vevő létrehozása módja azért előnyös, mert az új vevők azonnal kereshetők a különböző csatornákon keresztül. Ennek azonban van egy hátránya is. Mivel [Commerce Data Exchange Valós idejű szolgáltatás](dev-itpro/define-retail-channel-communications-cdx.md#realtime-service) típusú hívásokat generál a Commerce központi felülete irányába, befolyásolhatja a teljesítményt, ha a rendszer sok egyidejű vevői létrehozási hívást kezdeményez.

Ha a **Vevő létrehozása aszinkron módban** beállítás értéke **Igen** az üzlet funkcióprofiljában (**Retail és Commerce \> Csatorna beállítás \> Online áruház beállítása \> Funkcióprofilok**), akkor a valós idejű szolgáltatás típusú hívások nem használhatók vevőrekordok létrehozásához a csatorna-adatbázisban. A Vevők aszinkron létrehozása mód nincs hatással a Commerce központi felületének teljesítményére. A globálisan egyedi azonosítót (GUID) a rendszer minden új aszinkron vevői rekordhoz hozzárendeli és vevői számlaazonosítóként használja. Ez a GUID nem jelenik meg a pénztári felhasználóknak. Ehelyett ezek a felhasználók a **Függőben lévő szinkronizálás** lehetőséget látják vevői számlaazonosítóként. Bár ez a konfiguráció a vevők aszinkron létrehozására kényszerít, a vevői rekordok szerkesztése mindig szinkron módon történik.

### <a name="convert-async-customers-to-sync-customers"></a>Aszinkron vevők szinkron vevőkké történő konvertálása

Ahhoz, hogy az aszinkron vevőket szinkronizált vevőkké konvertálja, előbb futtatnia kell a P-feladatot, hogy az aszinkron vevőket a Commerce központi felületére küldje. Ezt követően futtassa a **Vevők és üzleti partnerek szinkronizálása aszinkron módból** feladatot a vevői számlaazonosítók létrehozásához. Végül futtassa az **1010** feladatot, hogy szinkronizálja az új vevői számlaazonosítókat a csatornákkal.

### <a name="async-customer-limitations"></a>Az aszinkron vevőkkel kapcsolatos korlátozások

Az aszinkron vevő funkcióra jelenleg a következő korlátozások vonatkoznak:

- Az aszinkron vevő rekordjai csak akkor szerkeszthetők, ha a vevőt a Commerce központi felületén hozták létre, és az új vevői számlaazonosítót már visszaszinkronizálták a csatornával.
- Aszinkron vevőkhöz nem társítható fiók. Emiatt az új aszinkron vevők nem öröklik a fiókokat az alapértelmezett vevőtől.
- Nem lehet hűségkártyákat kiadni az aszinkron vevőknek, amíg az új vevői számlaazonosító nincs visszaszinkronizálva a csatornával.
- Az aszinkron vevőkhöz nem lehet másodlagos e-mail-címeket és telefonszámokat rögzíteni.

### <a name="customer-creation-in-pos-offline-mode"></a>Vevő létrehozása pénztári offline módban

Ha a pénztár kapcsolat nélküli üzemmódba kerül a Vevő aszinkron létrehozása mód engedélyezése közben, az új vevőrekordok aszinkron módon jönnek létre. Ha a pénztár kapcsolat nélküli üzemmódba kerül, miközben a Vevő aszinkron létrehozási módja le van tiltva, a rendszer automatikusan átvált a Vevő aszinkron létrehozási módba. Vagyis a vevői rekordok aszinkron létrehozása akkor is lehetséges, ha a Vevő aszinkron létrehozása mód le van tiltva. Emiatt a Commerce központi felülete rendszergazdáinak ismétlődő kötegelt feladatot kell létrehozniuk és ütemezniük a P-feladathoz, a **Vevők és üzleti partnerek szinkronizálása aszinkron módból** feladathoz és az **1010** feladathoz, hogy a rendszer az aszinkron vevőket szinkron vevőkké konvertálja a Commerce központi felületén.

> [!NOTE]
> Ha a **Megosztott vevői adattáblák szűrése** beállítása **Igen** a **Commerce-csatorna sémája** oldalon (**Retail és Commerce \> Központ beállítása \> Kereskedelmi ütemező \> Csatorna-adatbázis-csoport**), a vevőrekordok nem jönnek létre, ha a pénztár offline módban van. További tudnivalókért lásd: [Offline adatok kizárása](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion).

## <a name="additional-resources"></a>További erőforrások

[Vevőattribútumok](dev-itpro/customer-attributes.md)

[Offline adatok kizárása](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)

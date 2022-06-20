---
title: Szállítói együttműködés beállítása és karbantartása
description: Ez a cikk bemutatja, hogyan lehet beállítani a szállítók együttműködési funkcióját Dynamics 365 Supply Chain Management. Bemutatja azt is, hogyan lehet új szállítói együttműködési felhasználókat létesíteni, és kezelni ezeknek a felhasználóknak a biztonsági szerepköreit.
author: GalynaFedorova
ms.date: 12/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DirExternalRole, SysUserRequestListPage, VendVendorPortalUsers, WorkflowTableListPageRnr
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: 220774
ms.assetid: 69d05e8b-7dc2-48ea-bc24-bea9ac963579
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 8fe4731f8ff23f4abe25fce57a2325e1fca979c4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890828"
---
# <a name="set-up-and-maintain-vendor-collaboration"></a>Szállítói együttműködés beállítása és karbantartása

[!include [banner](../includes/banner.md)]

A szállítói együttműködési felület a beszerzési rendelésekkel, a számlákkal és a külső szállító felhasználóknak szánt bizományos készlettel kapcsolatos korlátozott információkat jelenít meg. Ezen a felületen a szállítók válaszolhatnak ajánlatkérésekre (RFQ-k) is, és megtekinthetik és szerkeszthetik az alapvető vállalati adatokat.

Ez a cikk bemutatja, hogyan lehet beállítani a szállítók együttműködési funkcióját Dynamics 365 Supply Chain Management. Bemutatja azt is, hogyan munkafolyamatot beállítani új szállítói együttműködési felhasználók létesítéséhez, és hogyan lehet kezelni ezeknek a felhasználóknak a biztonsági szerepköreit.

> [!NOTE]
> A szállítói együttműködési biztonsági szerepkörök beállításával kapcsolatos információk csak a Pénzügy és műveletek aktuális verziójára vonatkoznak. A Microsoft Dynamics AX 7.0 (2016. február) és a Microsoft Dynamics AX 7.0.1 (2016. május) alkalmazásverziókban a **Szállítói portál** modul segítségével működhet együtt a szállítókkal. A szállítói portál felhasználói engedélyekkel kapcsolatos tudnivalókat a Microsoft Dynamics AX alkalmazásban lásd a [Szállítói portál felhasználói biztonsága](configure-security-vendor-portal-users.md) részben.

## <a name="set-up-vendor-collaboration-security-roles"></a>Szállítói együttműködés beállítása biztonsági szerepkörökhöz

Egy beszerző vagy a megfelelő jogosultságokkal rendelkező szállító kérheti egy kapcsolattartó felhasználóként való beállítását azáltal, hogy engedélyezi a **Szállítói felhasználó létrehozása** lehetőséget a kapcsolattartó rekordja számára. A létrehozási folyamat során a felhasználó jogosultságai ki vannak választva az új külső felhasználóhoz, és a rendszer elküldi az új szállítói felhasználói kérelmet. Fontos, hogy helyesen állítsa be a szállítói felhasználói kérelemben kiválasztásra elérhető felhasználói engedélyeket. Ellenkező esetben a szállítók hozzáférést kapnak az olyan információkhoz, amelyekhez nem volna szabad hozzáférniük a Supply Chain Management alkalmazásban.

### <a name="set-up-the-security-roles-that-are-available-for-selection-when-a-new-user-request-is-used-for-a-contact-person"></a>Állítsa be a biztonsági szerepköröket, amelyek elérhetők kiválasztásra, amikor új felhasználói kérelmet használnak egy kapcsolattartóhoz

1. Válassza ki a **Rendszerfelügyelet** &gt; **Biztonság** &gt; **Külső szerepkök** menüpontot.
2. Válassza az **Új** lehetőséget, majd válasszon egy biztonsági szerepkört és a **Szállító** fél szerepkörét.

Előfordulhat, hogy hozzáadja a Supply Chain Management szolgáltatásban elérhető **Szállítói rendszergazda (külső)** és **Szállító (külső)** szerepköröket. Másik lehetőségként használhatja a vállalat által létrehozott biztonsági szerepköröket is.

A **Szállítói rendszergazda (külső)** szerepkört csak akkor tegye elérhetővé, ha a szállítóknak lehetővé kell tenni új kapcsolattartók létrehozását, a szállítói együttműködési felhasználói kérelmek beküldését az új felhasználóknak és a felhasználói adatok módosításait, és ezeknek a kéréseknek a kezelését egy munkafolyamaton keresztül.

Ha manuálisan tervezi a szállítói kapcsolattartók és a felhasználók beállítását, akkor csak a **Szállító (külső)** szerepkört tegye elérhetővé. Ez a szerepkör lesz az egyetlen olyan szerepkör, amely a szállítói felhasználói kérelemben kérhető.

> [!NOTE]
> A **SystemUser** szerepkört automatikusan megadja a rendszer egy új felhasználói fiók manuális létrehozásakor. Ezért el kell távolítania ezt a szerepkört, és hozzá kell rendelnie a **SystemExternalUser** szerepkört. Ha új felhasználói fiókokat hoznak létre a szállítói felhasználói kérelem által kezdeményezett munkafolyamaton keresztül, akkor a rendszer hozzárendel egy vagy több olyan szerepkört, amelyet a szállítói együttműködésre beállított és a **SystemExternalUser** szerepkört.

#### <a name="vendor-admin-external-security-role"></a>Szállító rendszergazdai (külső) biztonsági szerepkör

A **Szállítói rendszergazda (külső)** szerepkör olyan külső szállítókhoz használható, amelyek karbantartják a szállító kapcsolattartási adatait, és kéréseket nyújtanak be új szállítói együttműködő felhasználók létrehozására. Az ilyen biztonsági szerepkörrel rendelkező külső felhasználók a következő feladatokat végezhetik el:

- A kapcsolattartóval kapcsolatos adatok, például a személy beosztása, e-mail címe és telefonszáma megtekintése és módosítása.
- Új vagy meglévő kapcsolattartó hozzáadása ahhoz a szállítói fiókhoz, amelynek ők kapcsolattartói.
- Törölhetik az általuk létrehozott kapcsolattartó személyeket.
- A kapcsolattartó és a szállítói fiók közötti társítás aktiválása vagy inaktiválása. Miután deaktiválták a kapcsolattartó és a szállítói fiók közötti társítást, nem lehet hivatkozni a kapcsolattartóra az új beszerzési rendeléseken és más dokumentumokon.
- A kapcsolattartók hozzáférésének megtagadása vagy engedélyezése a szállítói fiókhoz specifikus szállítói együttműködési felületen. Miután a kapcsolattartó és a szállítói fiók közötti társítást deaktiválták, a rendszer minden esetben megtagadja a hozzáférést a szállítói számlához specifikus dokumentumokhoz.
- Új felhasználói fiók kérése egy kapcsolattartónak a **Felhasználó létrehozása** művelettel.
- A kapcsolattartó felhasználói fiókja deaktiválásának kérése.
- A kapcsolattartó felhasználói fiókjának módosításának kérése biztonsági szerepkörök hozzáadása vagy eltávolítása érdekében.
- RFQ-k megtekintése.

#### <a name="vendor-external-security-role"></a>Szállító (külső) biztonsági szerepkör

A **Szállító (külső) szerepkör** a beszerzési rendelésekkel dolgozó szállítókhoz használható. Az ilyen biztonsági szerepkörrel rendelkező külső felhasználók a következő feladatokat végezhetik el:

- A beszerzési rendelésekkel kapcsolatos információk megválaszolása és megtekintése.
- Szállítói együttműködési számlák karbantartása.
- Bizományos készlet megtekintése.
- Ajánlatkérések megtekintése és megválaszolása.
- A szállítóval kapcsolatos információk megtekintése.

## <a name="set-up-security-roles-that-are-used-when-prospective-vendors-are-onboarded"></a>A potenciális szállítók beléptetésekor biztonsági szerepkörök beállítása

Szállítók beléptetéséhez potenciális szállítók regisztrálási kérelmével, a külső biztonsági szerepkört kell beállítani a külső szállítókhoz. Ezt a szerepkört az új felhasználókhoz rendeli hozzá a rendszer a **Felhasználói kérelem munkafolyamat (platform)** típusú munkafolyamat által szabályozott létrehozási folyamat során. A további tudnivalókat a [cikk](#set-up-workflows-to-process-vendor-collaboration-user-requests) későbbi, A szállítói együttműködési felhasználói kérelmek feldolgozására vonatkozó munkafolyamatok beállítása című részében olvashatja.

A potenciális szállítók felvételével kapcsolatos tudnivalókat lásd [Szállítók felvétele](vendor-onboarding.md).

### <a name="set-up-a-security-role-that-is-used-when-a-new-prospective-vendor-user-request-is-submitted"></a>Állítson be egy biztonsági szerepkört, amely új potenciális szállítók felhasználók kérelmének beküldésekor használatos

1. Válassza ki a **Rendszerfelügyelet** > **Biztonság** > **Külső szerepkök** menüpontot.
2. Válassza az **Új** lehetőséget, majd válasszon egy biztonsági szerepkört és a **Potenciális szállító** fél szerepkörét.

Adja hozzá az Supply Chain Management alkalmazásban megadott **Potenciális szállító (külső)** szerepkört.

A biztonsági szerepkör csak az új szállítóregisztráció varázslóhoz ad hozzáférést.

## <a name="set-up-workflows-to-process-vendor-collaboration-user-requests"></a>Munkafolyamatok beállítása a szállítói együttműködési felhasználói kérelmek feldolgozásához

Annak érdekében, hogy garantálható legyen az összes kapcsolódó feladat végrehajtása, valamint hogy a megfelelő jóváhagyások meg legyenek adva, be kell állítani a szállítói együttműködési felhasználói kérelmek kezelésével kapcsolatos munkafolyamatokat.

A szállítói együttműködési felhasználói kérelmeket vagy azok a külső szállítók nyújtották be, akik **Szállítói rendszergazdai (külső)** biztonsági szerepkörrel vagy hasonló engedélyekkel rendelkeznek, vagy a vállalat beszerzési szakemberei. A szállítók regisztrálási kéréseiből a szállítói beszállítói folyamat során is létre lehet ezeket hozni.

Háromféle kérelem van.

- Új felhasználó létesítésének kérelme
- Egy meglévő felhasználó inaktiválásának kérelme
- Egy meglévő felhasználó biztonsági szerepkörének módosításának kérelme

A szállítói együttműködő felhasználói kérelmekkel kapcsolatos további tudnivalókat lásd: [Szállítói együttműködés felhasználóinak kezelése](manage-vendor-collaboration-users.md).

A szállítói együttműködési felhasználói kérelmek mindhárom típusának feldolgozásához két vagy több munkafolyamatot kell létrehoznia. Az új munkafolyamatok létrehozása a **Felhasználói munkafolyamatok** lapon történik.

### <a name="example-of-a-workflow-for-provisioning-new-users-and-modifying-security-roles"></a>Példa új felhasználók létesítésére és a biztonsági szerepkörök módosítására vonatkozó munkafolyamatra

Az új felhasználók létrehozására és a biztonsági szerepkörök módosítására vonatkozó szállítói felhasználói kérelmek kezelésához a munkafolyamat elején elágazásos feltételt lehet felhozni. Ily módon a munkafolyamat eltérő ága használható attól függően, hogy a kérés új felhasználó létrehozására vagy egy meglévő felhasználó módosítására van-e szükség.

Az elágazás beállításához hozzon létre egy új **Felhasználói kérelem munkafolyamat (Platform)** típusú munkafolyamatot. A munkafolyamat ágai a következő elemeket tartalmazhatják.

#### <a name="branch-to-provision-new-users"></a>Ág új felhasználók létrehozásához

1. Jóváhagyási feladat hozzárendelése ahhoz a személyhez, aki felelős annak jóváhagyásáért, hogy az új felhasználóknak hozzáférést kell adni a szállítói együttműködési információkhoz.
2. Rendeljen feladatot ahhoz a személyhez, aki felelős új Microsoft Azure Active Directory (Azure AD) felhasználói fiókok kérelmezéséért az Azure portálon. A lépéshez használja az Előre meghatározott **Azure B2B felhasználói meghívó küldése** feladatot. A B2B felhasználók automatikusan exportálhatók az Azure AD-be. Használja az előre meghatározott **Azure AD B2B felhasználó létrehozása** feladatot. További információ: [B2B-felhasználók exportálása az Azure AD-be](../../fin-ops-core/dev-itpro/sysadmin/implement-b2b.md).
3. Rendeljen hozzá egy jóváhagyási feladatot ahhoz a személyhez, aki feltölt az Azure szolgáltatásba. Ha egy fiók létrehozása nem sikerült, ez a személy elutasítja a feladatot, és lezárja a munkafolyamatot. Ez a jóváhagyási feladat kihagyható, ha van olyan lépése, amely automatikusan exportálja az új felhasználói fiókokat az Azure szolgáltatásba a B2B alkalmazásprogramozási felület (API) segítségével.
4. Automatizált feladat hozzáadása, amely egy új felhasználót hoz létre. A lépéshez használja az előre meghatározott **Felhasználói automatizált létrehozása** feladatot.
5. Új feladat hozzáadása, amely az új felhasználót értesíti. Lehet, hogy üdvözlő e-mailt szeretne küldeni az új felhasználónak, amely tartalmazza a Supply Chain Management URL-címét. Ez az e-mail egy sablont használhat, amely az **E-mail üzenetek** lapon hozható létre, majd ki lehet választani a **Felhasználói munkafolyamat paraméterei** oldalon. A sablon tartalmazhatja a **%portalURL%** címkét. Az üdvözlő e-mail generálása során ezt a címkét lecseréli a Supply Chain Management bérlőjének URL-címére.

    > [!NOTE]
    > Ez a munkafolyamat több olyan helyzetben is használható, amelyek érintik a felhasználó beléptetését. Például akkor használható, amikor a potenciális szállítóknak vagy kapcsolattartóknak szállítói együttműködési fiókra van szükségük. Emiatt az e-mailt általános, többféle célra használható általános kifejezésként kell megfogalmazni.

#### <a name="branch-to-modify-security-roles"></a>Biztonsági szerepköröket módosító ág

1. Jóváhagyási feladat hozzárendelése a biztonsági szerepkörök módosításainak jóváhagyásáért felelős személyhez.
2. Adjon hozzá egy automatizált feladatot, amely hozzáadja vagy eltávolítja a megfelelő biztonsági szerepköröket. A lépéshez használja a **Felhasználó automatizált létrehozása** feladatot.

### <a name="example-of-a-workflow-for-inactivating-a-user"></a>Példa felhasználó inaktiválására szolgáló munkafolyamatra

Hozzon létre egy munkafolyamatot a **Felhasználói kérelem inaktiválása munkafolyamat-platform** típussal, majd adja hozzá a következő feladatokat.

1. Jóváhagyási feladat hozzárendelése a felhasználók deaktiválási kérelmeinek jóváhagyásáért felelős személyhez. A jóváhagyási lépés automatizálása érdekében feltételeket adhat meg.
2. Automatizált feladat hozzáadása, amely inaktiválja a felhasználót. A lépéshez használja a **Felhasználó automatizált deaktiválása** feladatot.
3. Adja hozzá a szükséges tisztítási feladatokat. Felvehet például egy feladatot, amely eltávolítja a fiókot az Azure-portál címtárából.

## <a name="enable-vendor-collaboration-for-a-specific-vendor"></a>Szállítói együttműködési lehetőségek engedélyezése egy adott szállítóhoz

Mielőtt létrehozna egy felhasználói fiókot valaki számára, aki a szállítói együttműködést fogja használni, be kell állítania a szállítót, hogy lehetővé váljon a szállítói együttműködés használata. Használja az **Együttműködés aktiválása** mezőt az **Általános** lapon, a **Szállítók** oldalon. Ehhez a következő lehetőségek állnak rendelkezésre:

- **Aktív (beszerzési rendelés automatikus megerősítése)**– A rendszer automatikusan megerősíti a beszerzési rendeléseket, ha a szállító módosítások kérése nélkül fogadja el azokat.
- **Aktív (beszerzési rendelés nincs automatikusan megerősítve)**– A beszerzési rendeléseket szervezetének manuálisan kell jóváhagynia, miután a szállító elfogadta őket.

> [!NOTE]
> Ezt a feladatot a vállalat beszerzési szakemberei is elvégezhetik.

## <a name="troubleshoot-the-provisioning-of-new-vendor-collaboration-users"></a>Új szállítói együttműködési felhasználók létesítésével kapcsolatos hibák elhárítása

Az új szállítói együttműködési felhasználók létesítése azon a munkafolyamaton keresztül történik, amelyet Ön állított be **Szállítói felhasználó létrehozása** típusú szállítói együttműködési felhasználói kérelmek feldolgozásához.

Ha egy új szállítói együttműködési felhasználó e-mail címe egy olyan tartományhoz tartozik, amely az Azure-ban bérlőként van regisztrálva (azaz ha ez egy felügyelt tartományú fiók), az e-mail címnek léteznie kell az Azure AD-fiókban. Ellenkező esetben nem lehet végrehajtani a létrehozási folyamatot.

Az **Azure B2B felhasználói meghívó küldése** feladat által a munkafolyamatban az Azure AD fiók kezelésére használt folyamattal kapcsolatos további tudnivalókat lásd az [Azure Active Directory B2B együttműködés](/azure/active-directory/external-identities/what-is-b2b) részben.

## <a name="additional-resources"></a>További erőforrások

[A külső szállítókkal történő szállítói együttműködés](vendor-collaboration-work-external-vendors.md)

Rövid videofelvétel megtekintése a szállítói felvételi folyamatról: [Új szállító felvétele](https://www.youtube.com/watch?v=0KUc3AGaTKk&feature=youtu.be)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

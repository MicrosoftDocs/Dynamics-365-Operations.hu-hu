---
title: Üzleti partner típusú felhasználók kezelése a B2B e-kereskedelmi webhelyeken
description: Ez a témakör azt ismerteti, hogyan adhatnak hozzá, szerkeszthetnek és törölhetnek a rendszergazdák üzleti partner típusú felhasználókat a B2B e-kereskedelmi webhelyeken.
author: josaw1
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7c1bd8d9cb494cef78fa7c14f6c391821d48749a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799853"
---
# <a name="manage-business-partner-users-on-b2b-e-commerce-websites"></a>Üzleti partner típusú felhasználók kezelése a B2B e-kereskedelmi webhelyeken

[!include [banner](../../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan adhatnak hozzá, szerkeszthetnek és törölhetnek a rendszergazdák üzleti partner típusú felhasználókat a B2B e-kereskedelmi webhelyeken.

A B2B e-kereskedelmi webhelyek esetén a szervezeteknek regisztrálniuk kell, hogy üzleti partnerekké váljanak. Miután egy szervezet elküldi a regisztrációs adatait egy B2B e-kereskedelmi webhelynek, minősítési folyamaton megy keresztül. Ha a szervezet minősítése sikeres, üzleti partnerként léptetik be.

Miután a szervezetet üzleti partnerként léptették be, az a szervezeti felhasználó, aki kezdeményezte az üzleti partnerré válás iránti kérelmet, rendszergazda típusú felhasználóként lesz meghatározva, és jogosultságokat kap a B2B e-kereskedelmi webhely további jogosult felhasználóinak beléptetésére. Ezek a jogosult felhasználók ezután az üzleti partner nevében rendeléseket adhatnak fel.

## <a name="turn-on-the-b2b-e-commerce-capabilities-feature-in-commerce-headquarters"></a>A B2B e-kereskedelmi képességek szolgáltatás bekapcsolása a Commerce központi felületén

A Commerce központi felületén a B2B e-kereskedelmi képességek szolgáltatás lehetővé teszi a szervezetek számára, hogy külső üzleti partnereket léptessenek be, valamint rendszergazdákat határozzanak meg. Ez a funkció lehetővé teszi a rendszergazdák számára azt is, hogy üzleti partner típusú felhasználókat és csapatokat hozznak létre és kezeljenek, valamint meghatározott szerepköröket rendeljenek hozzájuk. Végül lehetővé teszi az üzleti partner típusú felhasználóknak, hogy rendelési sablonokat hozzanak létre, és a meglévő rendeléseket használják a termékek újrarendelésére.

A B2B e-kereskedelmi képességek szolgáltatásnak a Commerce központi felületén történő bekapcsolásához kövesse az alábbi lépéseket.

1. Menjen a **Munkaterületek \> Funkciókezelés** lehetőségre.
1. A **Mind** lapon a **Kiskereskedelem és kereskedelem** kifejezés használatával szűrje a **Modul** mezőt.
1. Keresse meg és válassza ki a **B2B eCommerce képességek használatának engedélyezése** nevű funkciót, majd válassza az **Engedélyezés most** lehetőséget.

## <a name="create-a-number-sequence-and-add-it-to-commerce-shared-parameters"></a>Számsorozat létrehozása és hozzáadása a Commerce megosztott paramétereihez

A számsorozatokat az azonosítókat igénylő alapadatrekordok és tranzakciórekordok olvasható, egyedi azonosítóinak létrehozására használja a rendszer. A számsorozatokkal kapcsolatos további információkat lásd: [Számsorozatok áttekintése](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview).

Számsorozat létrehozásához és a Commerce központi felületén megosztott paraméterekhez való hozzáadásához kövesse az alábbi lépéseket.

1. Menjen a **Kiskereskedelem és kereskedelem \> Központi felület beállítása \> Számsorozatok \> Számsorozatok** pontra, és hozzon létre egy számsorozatot.
1. Lépjen a **Kiskereskedelem és kereskedelem \> Központi felület beállítása \> Paraméterek \> Commerce megosztott paraméterei** lehetőségre, és adja hozzá az új számsorozatot a **Vevőhierarchia-azonosító** hivatkozásához.

## <a name="set-up-the-administrator-user-for-a-new-business-partner"></a>A rendszergazda beállítása új üzleti partnerhez

A potenciális üzleti partnerek úgy kezdeményezhetik a beléptetési folyamatot egy B2B e-kereskedelmi webhelyre, hogy a webhelyen egy hivatkozás segítségével benyújtanak egy beléptetési kérést. Miután egy potenciális üzleti partner rákattint a hivatkozásra, megadhatja a beléptetéshez és a regisztrációhoz szükséges adatokat. A kérelem benyújtása után megjelenik egy elküldési visszaigazolási oldal. Ha az igénylést jóváhagyták, a kérelmező (azaz a beléptetést kezdeményező felhasználó) lesz az üzleti partner rendszergazdája.

Az üzleti partner rendszergazdájának a Commerce központi felületén történő jóváhagyásához és beállításához kövesse az alábbi lépéseket.

1. Ugorjon a **Kiskereskedelem és kereskedelem IT \> Elosztási ütemezéspont** lehetőségre.
1. Futtassa a **P-0001** feladatot az összes üzleti partnernek a Commerce központi felületre való beléptetése érdekében.
1. A **P-0001** feladat sikeres futtatása után lépjen a **Kiskereskedelem és kereskedelem IT \> Ügyfél** lehetőségre, és futtassa a **Vevők és üzleti partnerek szinkronizálása aszinkron módból** feladatot. A feladat sikeres futtatása után a beléptetési kérelmek létrejönnek a potenciális vevők rekordjaiként létrejönnek a Commerce központi felületén. Ezen rekordok **Típusazonosító** mezőjének értéke **B2B potenciális vevő**.
1. Lépjen a **Vevők \> Minden potenciális vevő** lehetőségre, és nyissa meg a Potenciális vevők oldalt.
1. Válassza ki az új üzleti partner potenciálisvevő-rekordját a potenciális vevő részletei oldal megnyitásához.
1. Az **Általános** lapon válassza a **Konvertálás \> Jóváhagyás/elutasítás** lehetőséget a beléptetési kérelem jóváhagyásához vagy elutasításához. Amikor megjelenik egy megerősítő üzenet, erősítse meg, hogy folytatni szeretné a folyamatot, majd hagyja jóvá a kérelmet. A rendszer a kérelmező e-mail-címére elküld egy e-mailes üzenetet, amely megerősíti, hogy a szervezetet jóváhagyták üzleti partnerként.

    A kérelem jóváhagyása után a potenciális vevő rekordja **Állapot** mezőjének beállítása **Jóváhagyva** lesz. Ezenkívül a rendszerben két új vevőrekord jön létre: az üzleti partner szervezetéhez egy **Szervezet típusa** vevőrekord, a kérelmezőhöz pedig egy **Személy típusa** vevőrekord. Az üzleti partnerhez egy vevői hierarchiarekord is létrejön. <!--(Please refer to the Org modeling of B2B customer section in this document for more information)-->

1. Lépjen a **Kiskereskedelem és kereskedelem IT \> Elosztási ütemezés** lehetőségre, majd futtassa **1010** (**Vevők**) feladatot az újonnan létrehozott vevő- és vevőhierarchia-rekordoknak a csatorna-adatbázisba való továbbküldése érdekében.

A kérelem jóváhagyása, valamint a vevő- és vevőhierarchia rekordjainak szinkronizálása után a kérelmező bejelentkezhet a B2B e-kereskedelmi webhelyre az igénylés elküldésekor megadott e-mail-cím használatával. A felhasználók a bejelentkezési folyamat során meghatározhatják a fiók jelszavát.

## <a name="onboard-additional-business-partner-users"></a>További üzleti partner típusú felhasználók beléptetése

Az üzleti partner rendszergazdája szükség esetén további üzleti partnereket is beléptethet a B2B e-kereskedelmi webhelyre.

További üzleti partnereknek a B2B e-kereskedelmi webhelyre történő beléptetéséhez kövesse az alábbi lépéseket.

1. Jelentkezzen be rendszergazdaként a B2B e-kereskedelmi webhelyre.
1. Lépjen a **Saját fiók \> Szervezeti felhasználók \> Részletek megtekintése** lehetőséget, és válassza a **Felhasználó hozzáadása** lehetőséget.
1. Adja meg a szükséges adatokat, majd kattintson a **Mentés** gombra. Az új felhasználó állapota **Függőben** lesz.

    A **P-0001** és a **Vevők és üzleti partnerek szinkronizálása aszinkron módból** feladatok futtatása után a Commerce központi felületén létrejön egy **Személy típusa** vevőrekord az új felhasználóhoz kapcsolódóan. Ez a vevőrekord az adott üzleti partner vevői hierarchiarekordjához is társítva van. Ezenkívül a rendszer e-mailt küld a felhasználó új e-mail-címére, amelyben tájékoztatja arról, hogy hozzáadta az üzleti partner szervezetének felhasználójaként, és most bejelentkezhet a B2B e-kereskedelmi webhelyre.

1. Futtassa a **1010** (**Vevők**) feladatot az új üzleti partner felhasználója és a csatorna-adatbázis szinkronizálásához.

A vevőrekord szinkronizálása után a B2B e-kereskedelmi webhelyen lévő felhasználó állapota **Aktív** lesz, és az új felhasználó az e-mail-címével bejelentkezhet a B2B e-kereskedelmi webhelyre. A felhasználók a bejelentkezési folyamat során meghatározhatják a fiók jelszavát.

## <a name="edit-business-partner-user-details"></a>Üzleti partner felhasználói adatainak szerkesztése

Az üzleti partner felhasználóinak szerkesztéséhez kövesse az alábbi lépéseket.

1. Jelentkezzen be rendszergazdaként a B2B e-kereskedelmi webhelyre.
1. Lépjen a **Saját fiók \> Szervezeti felhasználók \> Részletek megtekintése** lehetőségre, válassza a **Szerkesztés** gombot (ceruzaszimbólum), végezze el a szükséges módosításokat, majd kattintson a **Mentés** gombra. A módosítások csak a **P-0001**, a **Vevők és üzleti partnerek szinkronizálása aszinkron módból** és a **1010** (**Vevők**) feladatok futtatása után lépnek életbe.

## <a name="remove-a-business-partner-user"></a>Üzleti partner felhasználó eltávolítása

A rendszergazda szükség esetén eltávolíthatja egy üzleti partner szervezetének meglévő felhasználóit azon felhasználók listájáról, akik hozzáférhetnek a B2B e-kereskedelmi webhelyhez.

Az üzleti partner felhasználójának eltávolításához kövesse az alábbi lépéseket.

1. Jelentkezzen be rendszergazdaként a B2B e-kereskedelmi webhelyre.
1. Lépjen a **Saját fiók \> Szervezeti felhasználók \> Részletek megtekintése** lehetőséget, és válassza az **Eltávolítás** gombot (X szimbólum). Amikor megjelenik egy megerősítő üzenet, erősítse meg, hogy el szeretné távolítani a felhasználót. A módosítás csak a **P-0001**, a **Vevők és üzleti partnerek szinkronizálása aszinkron módból** és a **1010** (**Vevők**) feladatok futtatása után lép életbe.

> [!NOTE]
> Amikor eltávolít egy felhasználót azon felhasználók listájáról, akik hozzáférhetnek a B2B e-kereskedelmi webhelyhez, a megfelelő vevőrekord törlődik az üzleti partner vevői hierarchiarekordjáról. Ugyanakkor magát a vevőrekordot a rendszer nem törli a Commerce központi felületéről.

## <a name="onboard-business-partner-and-users-in-commerce-headquarters"></a>Üzleti partner és felhasználók beléptetése a Commerce központi felületén

A rendszergazdák közvetlenül beléptethetik az üzleti partnereket és a felhasználókat a Commerce központi felületén.

Az üzleti partnereknak és felhasználóknak a Commerce központi felületén történő beléptetéséhez kövesse az alábbi lépéseket.

1. Hozzon létre egy **Szervezet típusa** vevőrekordot az üzleti partner szervezetéhez.
1. Hozzon létre **Személy típusa** vevőrekordokat az üzleti partner felhasználói számára. Győződjön meg arról, hogy minden vevőnél legyen megadva egy elsődleges e-mail-cím.
1. Minden egyes, az üzleti partner szervezetének rendszergazdájaként megjelölendő **Személy típusa** vevőrekord esetén a **Kiskereskedelem** gyorslapon állítsa a **B2B rendszergazda** lehetőséget **Igen** értékre.
1. Hozzon létre vevőhierarchia-azonosítót. A **Név** mezőben adjon meg egy nevet.
1. A **Szervezet** mezőbe írja be az üzleti partner szervezetét.
1. Válassza ki a **Hozzáadás** lehetőséget, majd a **Név** mezőben válasszon egy vevőt.
1. Ismételje meg ezt a folyamatot, ha további vevőket szeretne hozzáadni a hierarchiához.

## <a name="additional-information"></a>További információk

- A témakörben említett összes feladat konfigurálható úgy, hogy kötegelt formátumban fusson meghatározott ütemezés alapján. A feltételezés az, hogy az üzleti partnerek a szükséges módon konfigurálják a kötegelt feladatokat.
- Jelenleg csak egy felhasználó-/vevőrekord jelölhető ki rendszergazdaként, és ez a szerepkör csak a Commerce központi felületén módosítható. Az önkiszolgáló rendszer funkciói nem támogatják azokat a lehetőségeket, amelyek lehetővé teszi az üzleti partnerek számára, hogy több rendszergazdát jelöljenek ki, vagy hogy a rendszergazdákat a B2B e-kereskedelmi webhelyekről módosítsák.
<!--- The modules and labels of the different fields referenced in the screenshots for e-commerce are only for illustration purposes. Customers have complete control on the placement of the B2B related modules and the labels.-->
- Bár a felhasználókra költségkereteket lehet meghatározni, a rendelésbeviteli folyamat során még nincs végrehajtva a költségkeretek érvényesítése.
- A felhasználók B2B e-kereskedelmi webhelyen szerzett tapasztalatainak minden üzleti logikája és érvényesítése a Commerce központi felületén lévő felhasználóhoz leképezett vevőrekord konfigurációján alapul.

## <a name="additional-resources"></a>További erőforrások

[B2B e-kereskedelmi webhely beállítása](set-up-b2b-site.md)

[Szervezeti modellezési hierarchiák létrehozása B2B szervezetek számára](org-model.md)

[A B2B e-commerce webhelyekhez használt vevői számlafizetési mód konfigurálása](payment-method.md)

[Termékmennyiség-korlátok beállítása B2B e-kereskedelmi webhelyekhez](quantity-limits.md)

[Számsorozatok áttekintése](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
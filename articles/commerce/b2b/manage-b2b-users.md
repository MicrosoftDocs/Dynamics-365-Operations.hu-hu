---
title: Üzleti partner típusú felhasználók kezelése a B2B e-kereskedelmi webhelyeken
description: Ez a témakör azt ismerteti, hogyan lehet üzleti partner felhasználóit hozzáadni, Microsoft Dynamics 365 Commerce törölni és szerkeszteni a vállalathoz – b2B – e-commerce webhelyeken és a Commerce Headquarters alkalmazáson keresztül.
author: josaw1
ms.date: 04/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4a3d1c7bf7e7ea545590315d9e185fa525b5d5e3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860295"
---
# <a name="manage-business-partner-users-on-b2b-e-commerce-websites"></a>Üzleti partner típusú felhasználók kezelése a B2B e-kereskedelmi webhelyeken

[!include [banner](../../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet üzleti partner felhasználóit hozzáadni, Microsoft Dynamics 365 Commerce törölni és szerkeszteni a vállalathoz – b2B – e-commerce webhelyeken és a Commerce Headquarters alkalmazáson keresztül.

> [!NOTE]
> - A [dokumentum előfeltétele a B2B üzleti partnerek kezelése a vevői hierarchiák](partners-customer-hierarchies.md) cikket használó felhasználók számára.
> - A Dokumentumtípusok képernyő megnyitásával inicializálja a dokumentumtípus-entitásokat a Commerce **Headquarters** **\>\> alkalmazásból, hogy megnyitja a Szervezet felügyelete dokumentumkezelési dokumentumtípusok képernyőt**.

A B2B e-kereskedelmi webhelyek esetén a szervezeteknek regisztrálniuk kell, hogy üzleti partnerekké váljanak. Miután egy szervezet elküldi a regisztrációs adatokat a B2B e-commerce webhelynek, a regisztrációra vonatkozó kérelem egy képesítési folyamaton megy keresztül. Ha a szervezet minősítése sikeres, üzleti partnerként léptetik be.

Miután a szervezetet üzleti partnerként léptették be, az a szervezeti felhasználó, aki kezdeményezte az üzleti partnerré válás iránti kérelmet, rendszergazda típusú felhasználóként lesz meghatározva, és jogosultságokat kap a B2B e-kereskedelmi webhely további jogosult felhasználóinak beléptetésére. Ezek a jogosult felhasználók ezután az üzleti partner nevében rendeléseket adhatnak fel.

## <a name="set-up-the-administrator-user-for-a-new-business-partner"></a>A rendszergazda beállítása új üzleti partnerhez

A potenciális üzleti partnerek úgy kezdeményezhetik a berakodási folyamatot egy B2B e-commerce webhelyre, hogy egy, a B2B webhelyen található hivatkozáson keresztül benyújtására vonatkozó kérést küldjenek el. Ezután a testreszabható képernyő használatával meg lehet adni a bejelentkezéshez és a regisztrációhoz szükséges részleteket. A kérelem benyújtása után megjelenik egy elküldési visszaigazolási oldal. Ha az igénylést jóváhagyták, akkor az a vállalat, amely az igénylést benyújtotta, üzleti partner lesz, és a kérelmező (a berakodási kérelmet kezdeményező felhasználó) lesz az üzleti partner rendszergazda felhasználója.

A következő lépések szerint hagyja jóvá az üzleti partnerekkel kapcsolatos kéréseket a Commerce Headquartersban.

1. Ugorjon a **Kiskereskedelem és kereskedelem IT \> Elosztási ütemezéspont** lehetőségre.
1. Futtassa a **P-0001** feladatot az összes üzleti partnernek a Commerce központi felületre való beléptetése érdekében.
1. **A P-0001** **feladat sikeres futtatása után menjen a Retail and Commerce it \> customer** ügyfélhez, és **futtassa** a Vevők és csatornakérések szinkronizálása feladatot. A feladat sikeres futtatása után **a berakodó kérések a Commerce Headquarters B2B** potenciális vevőtípusának potenciális vevőiként létrejönnek. 
1. Menjen a **Vevők – \> Minden potenciális** vevőhöz, és válassza ki az új üzleti partner potenciális vevői rekordját a potenciális vevő részletei lap megnyitásához.
1. Az Általános **lapon** válassza **\> a Jóváhagyás/** elutasítás konvertálása lehetőséget a berakodási kérelem jóváhagyásához. Amikor megjelenik a megerősítő üzenet, győződjön meg arról, hogy folytatni szeretné a folyamatot, majd hagyja jóvá a kérést. A jóváhagyás a potenciális vevői **rekord Állapot** mezőjét "Jóváhagyva" állapotúra **módosítja**. A rendszer a kérelmező e-mail-címére elküld egy e-mailes üzenetet, amely megerősíti, hogy a szervezetet jóváhagyták üzleti partnerként. Létrejön egy vevőhierarchia is, ahol a kérelmező hozzáadódik az üzleti partner rendszergazdájához.

    > [!NOTE]
    > A visszaigazoló e-mail küldése jelenleg azonnal megkezdődik a jóváhagyás után. A commerce rendszer jövőbeli funkcióival azonban a rendszergazda manuálisan aktiválhatja az e-maileket.

1. Menjen a **Retail and Commerce IT \> Distribution** ütemezéshez, **és futtassa a 1010 -es (Vevők)** feladatot, hogy az új vevő- és vevőhierarchia-rekordokat a csatorna-adatbázisba továbbküldése nyomtassa.

> [!NOTE]
> Annak érdekében, hogy az új vevőrekordok bekerültek a csatorna-adatbázisba, a vevőhöz társított címjegyzékek legalább egyének szerepelnie kell az online áruházhoz társított vevői címjegyzékben. Ezt a folyamatot automatizálhatja úgy, hogy az online áruház alapértelmezett vevőjére beállítva beállítva a címjegyzék értékét átmásolja minden új vevőnek.

Miután a vevőhierarchia rekordjai szinkronizálva vannak a csatorna-adatbázissal, a kérelmező bejelentkezhet a B2B e-commerce webhelyre a bejelentkezési kérelem elküldésekor megadott e-mail cím használatával. A felhasználók a bejelentkezési folyamat során meghatározhatják a fiók jelszavát. Az (Azure Active Directory Azure AD) B2C identitásszolgáltató rekordnak a potenciális vevő jóváhagyásánál létrehozott B2B [vevőrekordhoz való kapcsolásával kapcsolatban a következő tájékoztatás található: Automatikus csatolás engedélyezése](../identity-record-linking.md).

## <a name="notify-b2b-prospects-when-they-are-approved-or-rejected"></a>A B2B potenciális vevők értesítése jóváhagyás vagy elutasítás után

Ha jóváhagyja vagy elutasítja egy B2B potenciális vevő felhozott kérelmét, automatikusan elküldhető egy e-mail értesítés a potenciális vevőnek.

E-mail értesítések beállítására a Commerce Headquarters **szolgáltatásban a jóváhagyott B2B** **potenciális vevő vagy a B2B** potenciális vevő által elutasított értesítési típussal kapcsolatos eseményekről, kövesse ezeket a lépéseket.

1. E-mail sablonok létrehozása a potenciális vevőknek küldött e-mailekhez, amikor a **B2B** **potenciális vevő jóváhagyása vagy a B2B potenciális vevő által elutasított értesítési** típus megjelenik. Az értesítési típusok által támogatott helyőrzőkről az Értesítési típusok oldalon [található tájékoztatás](../email-templates-transactions.md#notification-types). Az e-mail-sablonok létrehozásával kapcsolatos további tudnivalókért tekintse meg az [E-mail-sablon létrehozása](../email-templates-transactions.md#create-an-email-template) részt.
1. Adja hozzá **a jóváhagyott B2B** **potenciális vevőt, és a B2B** potenciális vevő visszautasította az értesítési típusokat az e-mail értesítési profilhoz, majd leképezi őket a létrehozott e-mail sablonokra. További információt az értesítési profilokról az [E-mailes értékesítési profil beállítása](../email-notification-profiles.md) című témakörben talál.

## <a name="onboard-additional-business-partner-users"></a>További üzleti partner típusú felhasználók beléptetése

Az üzleti partner rendszergazdája szükség esetén további üzleti partnereket is beléptethet a B2B e-kereskedelmi webhelyre.

További üzleti partnereknek a B2B e-kereskedelmi webhelyre történő beléptetéséhez kövesse az alábbi lépéseket.

1. Jelentkezzen be rendszergazdaként a B2B e-kereskedelmi webhelyre.
1. Lépjen a **Saját fiók \> Szervezeti felhasználók \> Részletek megtekintése** lehetőséget, és válassza a **Felhasználó hozzáadása** lehetőséget.
1. Adja meg a szükséges adatokat, majd kattintson a **Mentés** gombra. Az új felhasználó állapota **Függőben** lesz.

**A P-0001** **és** a Vevők szinkronizálása és a csatornakérési feladatok futtatása után a **Commerce** Headquarters rendszer létrehoz egy Személy típusú vevőrekordot az új felhasználóhoz. Ez a vevőrekord az adott üzleti partner vevői hierarchiarekordjához is társítva van. Ezenkívül a rendszer e-mailt küld a felhasználó új e-mail-címére, amelyben tájékoztatja arról, hogy hozzáadta az üzleti partner szervezetének felhasználójaként, és most bejelentkezhet a B2B e-kereskedelmi webhelyre.

Ezután futtassa a **1010 -es (Vevők)** feladatot az új üzleti partner felhasználója és a csatorna-adatbázis szinkronizálásához.

A vevőrekord szinkronizálása után a B2B e-commerce **webhelyen** lévő felhasználó állapota Aktívra lesz állítva, és az új felhasználó e-mail címével bejelentkezhet a B2B e-commerce webhelyre. A felhasználók a bejelentkezési folyamat során meghatározhatják a fiók jelszavát. Az automatikus csatolás engedélyezése Azure AD a B2C-identitásszolgáltató rekordjának a Commerce Headquartersban [létrehozott B2B vevőrekordhoz való kapcsolásával kapcsolatban tartalmaz tájékoztatást](/dynamics365/commerce/identity-record-linking.md).

## <a name="edit-business-partner-user-details"></a>Üzleti partner felhasználói adatainak szerkesztése

Az üzleti partner felhasználóinak szerkesztéséhez kövesse az alábbi lépéseket.

1. Jelentkezzen be rendszergazdaként a B2B e-kereskedelmi webhelyre.
1. Lépjen a **Saját fiók \> Szervezeti felhasználók \> Részletek megtekintése** lehetőségre, válassza a **Szerkesztés** gombot (ceruzaszimbólum), végezze el a szükséges módosításokat, majd kattintson a **Mentés** gombra. A módosítások csak a **P-0001**, **a** Vevők és csatornakérések szinkronizálása, **valamint a 1010 -es (vevők)** feladat futtatása után lépnek érvénybe.

## <a name="remove-a-business-partner-user"></a>Üzleti partner felhasználó eltávolítása

A rendszergazda szükség esetén eltávolíthatja egy üzleti partner szervezetének meglévő felhasználóit azon felhasználók listájáról, akik hozzáférhetnek a B2B e-kereskedelmi webhelyhez.
Az üzleti partner felhasználójának eltávolításához kövesse az alábbi lépéseket.
- Jelentkezzen be rendszergazdaként a B2B e-kereskedelmi webhelyre.
- Menjen a Saját fiók **> Tekintse \>** meg a részletes adatokat, **és válassza az Eltávolítás** gombot ("X" szimbólum). Amikor megjelenik egy megerősítő üzenet, erősítse meg, hogy el szeretné távolítani a felhasználót. A módosítás csak a **P-0001**, **a** Vevők és csatornakérések szinkronizálása, **valamint a 1010 -es (vevők)** feladat futtatása után lép érvénybe.

> [!NOTE]
> Amikor eltávolít egy felhasználót azon felhasználók listájáról, akik hozzáférhetnek a B2B e-kereskedelmi webhelyhez, a megfelelő vevőrekord törlődik az üzleti partner vevői hierarchiarekordjáról. Ugyanakkor magát a vevőrekordot a rendszer nem törli a Commerce központi felületéről.

## <a name="onboard-existing-customers-as-business-partners-on-the-b2b-e-commerce-website"></a>Meglévő vevők elérhető üzleti partnerként a B2B e-commerce webhelyen

A rendszergazdák közvetlenül beléptethetik az üzleti partnereket és a felhasználókat a Commerce központi felületén. Ez a képesség jól használható a B2B e-commerce webhely meglévő üzleti partnerének a hajóra való felezésére.

Az üzleti partnereknak és felhasználóknak a Commerce központi felületén történő beléptetéséhez kövesse az alábbi lépéseket.

1. Az üzleti partnerként hozzáadni kívánt **Szervezet** típusú vevő létrehozása vagy kiválasztása.
1. Hozzon létre vagy válasszon ki egy Személy **típusú** vevőt, akit rendszergazdaként vagy felhasználóként szeretne hozzáadni az üzleti partnerhez. Győződjön meg arról, hogy az elsődleges e-mail címek a vevőkhöz vannak társítva. Ezek az e-mail címek a webhelyre való bejelentkezésre használhatók. 

    > [!NOTE]
    > A rendszernek képesnek kell lennie arra, hogy megtalálja a webhelyre bejelentkező felhasználók egyedi vevőrekordját. Ha a rendszer egynél több olyan vevőt keres, akinél ugyanaz az elsődleges e-mail cím található a jogi személynél, akkor a felhasználó nem fog tudni bejelentkezni a webhelyre.

1. Hozzon létre vevőhierarchia-azonosítót.
1. A **Név** mezőben adjon meg egy nevet.
1. A **Szervezet** mezőbe írja be az üzleti partner szervezetét.
1. Válassza a **Hozzáadás gombra** a Hierarchia gyorsététi **struktúrában**.
1. A Név **mezőben** válasszon ki egy Személy típusú **vevőt**.
1. Válassza ki **a rendszergazdaként** kijelölni kívánt vevő rendszergazdai szerepkörét.
1. Ismételje meg ezt a folyamatot, ha további vevőket szeretne felvenni a hierarchiába.

## <a name="additional-information"></a>További információk

- A cikk minden, a fenti feladat konfigurálható úgy, hogy kötegelt formátumban fusson az ütemezésen. A feltételezés az, hogy az üzleti partnerek a szükséges módon konfigurálják a kötegelt feladatokat.
- Jelenleg csak egy felhasználó-/vevőrekord jelölhető ki rendszergazdaként, és ez a szerepkör csak a Commerce központi felületén módosítható. Az önkiszolgáló rendszer funkciói nem támogatják azokat a lehetőségeket, amelyek lehetővé teszi az üzleti partnerek számára, hogy több rendszergazdát jelöljenek ki, vagy hogy a rendszergazdákat a B2B e-kereskedelmi webhelyekről módosítsák.
- Bár a felhasználókra költségkereteket lehet meghatározni, a rendelésbeviteli folyamat során még nincs végrehajtva a költségkeretek érvényesítése.
- A felhasználók B2B e-kereskedelmi webhelyen szerzett tapasztalatainak minden üzleti logikája és érvényesítése a Commerce központi felületén lévő felhasználóhoz leképezett vevőrekord konfigurációján alapul.

## <a name="additional-resources"></a>További erőforrások

[B2B e-kereskedelmi webhely beállítása](set-up-b2b-site.md)

[B2B üzleti partnerek kezelése vevőhierarchiák használatával](partners-customer-hierarchies.md)

[A B2B e-commerce webhelyekhez használt vevői számlafizetési mód konfigurálása](payment-method.md)

[Termékmennyiség-korlátok beállítása B2B e-kereskedelmi webhelyekhez](quantity-limits.md)

[Számsorozatok áttekintése](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

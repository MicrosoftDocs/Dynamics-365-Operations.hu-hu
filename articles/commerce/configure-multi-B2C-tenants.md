---
title: Több B2C bérlő konfigurálása egy Commerce-környezetben
description: Ez a témakör azt mutatja be, hogy mikor és hogyan lehet több csatornánkénti Microsoft Azure Active Directory (Azure AD) vállalat és ügyfél közötti (B2C) bérlőt beállítani felhasználói hitelesítésre egy kijelölt Dynamics 365 Commerce-környezetben.
author: BrianShook
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2020-02-12
ms.dyn365.ops.version: ''
ms.openlocfilehash: 0ad2a86fbc17f107a065330a56da6cdcca69e172
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6352566"
---
# <a name="configure-multiple-b2c-tenants-in-a-commerce-environment"></a>Több B2C bérlő konfigurálása egy Commerce-környezetben

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogy mikor és hogyan lehet csatornánként több Microsoft Azure Active Directory (Azure AD) vállalat és ügyfél közötti (B2C) bérlőt beállítani felhasználói hitelesítésre egy kijelölt Dynamics 365 Commerce-környezetben.

A Dynamics 365 Commerce az Azure AD B2C felhőalapú identitásszolgáltató segítségével támogatja a felhasználói hitelesítési adatokat és hitelesítési folyamatokat. A felhasználók a hitelesítési folyamatok segítségével regisztrálhatnak, jelentkezhetnek be, és alaphelyzetbe állíthatják a jelszavukat. Az Azure AD B2C érzékeny természetű felhasználói hitelesítési adatokat, például a felhasználónevet és a jelszót tárolja. A felhasználói rekord minden B2C bérlő számára egyedi, a felhasználó neve (e-mail-cím) hitelesítő adatait vagy a közösségi identitásszolgáltató adatait használja.

A legtöbb esetben egy Azure AD B2C-bérlőt használnak a Commerce-környezetben. A Commerce-felhasználók ezután több webhelyet is létrehozhatnak és közzétehetnek ugyanazon a Commerce-környezetben, és ugyanezek a vevői hitelesítő adatok is használhatók ezeken a helyeken. Ha azonban a környezet webhelyeit különböző márkákként kell kezelni, és a felhasználóknak külön vállalkozásként kell megjelenniük, akkor a B2C-bérlő beállítható a webhely/márka elválasztásához használt csatornához.

## <a name="considerations-when-multiple-b2c-tenants-are-set-up-per-channel"></a>Szempontok, amikor több B2C bérlő van beállítva csatornánként

Gyakran előfordul, hogy az egyes csatornák vagy webhelyek külön üzletágként kezelendők, és a felhasználói hitelesítési folyamatok szempontjából a legjobb megoldás a Commerce-ben a külön jogi személyek használata. Ha azonban az egyes csatornákat/helyeket ugyanabban a környezetben és jogi személyben szeretné tartani, de mindegyik helyhez külön felhasználói hitelesítést kíván használni, fontos, hogy a továbblépés előtt vegye figyelembe a következő szempontokat:

- A felhasználók mindegyik csatornához/webhelyhez külön hitelesítő adatokkal fognak rendelkezni.

    Egyazon személynek két külön fiókja lehet csatornánként vagy helyenként, mert mindegyik fiók egyedi bejegyzés lesz külön B2C-bérlőben.

- A Microsoft Dynamics környezetben a globális rekordok keresésekor külön vevői rekordok kerülnek visszaadásra.

    Ha egy felhasználó ugyanazokat az e-mail címeket használja a csatornák/helyek között, akkor a globális vevői keresések minden csatornához/helyhez visszaadják az eredményeket. (Egy csatornajelző jelenik meg.)

- A címjegyzék használható a felhasználók csoportosítása érdekében, hogy azok nyomon követhetők legyenek csatornánként.
- Előfordulhat, hogy a csatornán található vevői rekordok száma növekedni fog, és ez a növekedés hatással lehet a globális vevői keresések teljesítményére.
- A B2C-bérlőket gondosan kell leképezni egy csatornára, hogy megakadályozza azokat a helyzeteket, amikor a vevők helytelen bérlőbe regiszrtálnak. Máskülönben zavart vagy nyomonkövetési problémákat okozhat.

A következő ábra több B2C bérlőt mutat be a Commerce-környezetben.

![Több B2C-bérlő Commerce környezetben.](media/MultiB2C_In_Environment.png)

Ha úgy dönt, hogy a vállalat külön B2C bérlőket igényel csatornánként ugyanazon a Commerce-környezetben, hajtsa végre a következő szakaszokban ismertetett lépéseket a funkció kéréséhez.

## <a name="configure-b2c-tenants-in-your-environment"></a>B2C bérlők konfigurálása a környezetben

A B2C-bérlők konfigurálásához hajtsa végre a megfelelő eljárásokat ebben a szakaszban.

### <a name="add-an-azure-ad-b2c-tenant"></a>Azure AD B2C-bérlő felvétele

Ha Azure AD B2C-bérlőt szeretne hozzáadni a környezethez, hajtsa végre az alábbi lépéseket.

1. Rendszeradminisztrátorként jelentkezzen be a Commerce webhelykészítőbe a saját környezetében. Az Azure AD B2C-bérlők konfigurálásához rendszeradminisztrátornak kell lennie a Commerce környezethez.
1. A bal oldali navigációs panelen válassza a **Bérlőbeállítások** elemet a kibontáshoz.
1. Válassza a **B2C beállítások** lehetőséget, majd válassza ki a **Kezelés** pontot.
1. Válassza ki az **B2C-alkalmazás hozzáadása**, majd írja be a következő adatokat:

    - **Alkalmazás neve**: Adja meg azt a nevet, amelyet az alkalmazáshoz kell használni a Commerce-ben való kezelésével kapcsolatban. Azt ajánljuk, hogy a Azure AD B2C alkalmazások Azure portálon történő beállításakor használt alkalmazásnevet használja. Ily módon csökkenthető a zűrzavar a Commerce-ben a B2C-bérlők kezelése során.
    - **Bérlő neve**: adja meg az Azure portálon megjelenő B2C bérlő nevét.
    - **Jelszó elfelejtésére vonatkozó irányelv azonosítója**: adja meg az irányelv azonosítóját (a házirend nevét az Azure portálon).
    - **Regisztrációra és bejelentkezésre vonatkozó irányelv azonosítója**: adja meg az irányelv azonosítóját (a házirend nevét az Azure portálon).
    - **Ügyfél GUID-azonosítója**: adja meg az Azure portálon megjelenő Azure AD B2C bérlő azonosítóját (nem a B2C bérlő alkalmazásazonosítóját).
    - **Profil szerkesztésére vonatkozó irányelv azonosítója**: adja meg az irányelv azonosítóját (a házirend nevét az Azure portálon).

1. Ha befejezte megadni ezeket az adatokat, akkor a módosítások mentéséhez kattintson az **OK** gombra. Az új Azure AD B2C bérlő most a **B2C alkalmazások kezelése** területen jelenik meg a listán.

> [!NOTE]
> A **Hatókör**, **Nem interaktív irányelv azonosítója**, **Nem interaktív ügyfélazonosító**, **Bejelentkezés egyéni tartománya** és **Regisztrációs irányelv azonosítója** mezőket üresen, hacsak a Dynamics 365 Commerce-csapat nem kéri ezek beállítását.


### <a name="manage-or-delete-an-azure-ad-b2c-tenant"></a>Azure AD B2C-bérlő kezelése vagy törlése

1. Rendszeradminisztrátorként jelentkezzen be a Commerce webhelykészítőbe a saját környezetében. Az Azure AD B2C-bérlők konfigurálásához rendszeradminisztrátornak kell lennie a Commerce környezethez.
1. A bal oldali navigációs panelen válassza a **Bérlőbeállítások** elemet a kibontáshoz.
1. Válassza a **B2C beállítások** lehetőséget, majd válassza ki a **Kezelés** pontot.
1. A B2C-bérlő szerkesztéséhez válassza ki a mellette látható ceruza szimbólumát. A B2C-bérlő törléséhez jelölje be a mellette látható Szemetes jelet.
1. Válassza a **mentés** lehetőséget, majd a módosítások aktiválásához válassza a **közzététel** parancsot.

> [!WARNING]
> Amikor egy B2C bérlőt egy élő/közzétett webhelyhez konfigurálnak, előfordulhat, hogy a felhasználók a bérlőn jelen lévő fiókok használatával regisztráltak. Ha egy konfigurált bérlőt kitöröl a **Bérlőbeállítások \> B2C bérlő** menüben, eltávolítja az adott B2C bérlő társítását azokon a webhelyeken, amelyek a bérlő bármely csatornájával kapcsolatban vannak. Ebben az esetben előfordulhat, hogy a felhasználók nem tudnak bejelentkezni a saját fiókjukba. Ezért rendkívüli óvatosságot kell alkalmazni a konfigurált bérlő törlésekor.
>
> Egy konfigurált bérlő törlése esetén a B2C bérlő és a rekordok karbantartása továbbra is fennáll, de a bérlő Commerce rendszerkonfigurációját módosítani vagy törölni kell. Azoknak a felhasználóknak, akik megpróbálnak regisztrálni vagy bejelentkezni a webhelyre, új fiókrekordot hoznak létre az alapértelmezett vagy az újonnan társított B2C-bérlőben, amely a webhely csatornája számára be van állítva.

## <a name="configure-your-channel-with-a-b2c-tenant"></a>A csatorna konfigurálása a B2C-bérlővel

1. Rendszeradminisztrátorként jelentkezzen be a Commerce webhelykészítőbe a saját környezetében. Az Azure AD B2C-bérlők konfigurálásához rendszeradminisztrátornak kell lennie a Commerce környezethez.
1. A bal oldali navigációs panelen válassza a **Webhelybeállítások** elemet a kibontáshoz.
1. Válassza kia **Csatornák** elemet, majd válassza ki a konfigurálni kívánt csatornát.
1. A jobb oldali Tulajdonságok ablaktáblán, a **B2C alkalmazás kiválasztása** mezőben válassza ki a csatornához használni kívánt Azure AD B2C-bérlőt.
1. Az új vagy frissített konfiguráció véglegesítéséhez válassza a parancssáv **Mentés és közzététel** elemét.

> [!WARNING]
> Ha módosítja a csatornához társított B2C-alkalmazást, akkor eltávolíthatja azokat a jelenlegi hivatkozásokat, amelyek már létrejöttek a környezetben már feliratkozott felhasználók számára. Ebben az esetben az aktuálisan hozzárendelt B2C alkalmazáshoz társított hitelesítő adatok nem lesznek elérhetők a felhasználók számára. Ezért csak akkor változtassa meg a csatorna Azure AD B2C konfigurációját, ha első alkalommal állítja be a csatornát, és egyetlen felhasználó sem tudott feliratkozni. Ellenkező esetben előfordulhat, hogy a felhasználóknak újra kell regisztrálniuk az új Azure AD B2C-bérlőben lévő rekord létrehozásához.
## <a name="additional-resources"></a>További erőforrások

[Tartománynév konfigurálása](configure-your-domain-name.md)

[Új e-kereskedelmi bérlő telepítése](deploy-ecommerce-site.md)

[E-kereskedelmi webhely létrehozása](create-ecommerce-site.md)

[Dynamics 365 Commerce webhely társítása online csatornával](associate-site-online-store.md)

[robots.txt fájlok kezelése](manage-robots-txt-files.md)

[URL-átirányítások tömeges feltöltése](upload-bulk-redirects.md)

[B2C-bérlő beállítása a Commerce-ben](set-up-B2C-tenant.md)

[Felhasználói bejelentkezéshez használt egyéni lapok beállítása](custom-pages-user-logins.md)

[Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása](add-cdn-support.md)

[Helyalapú áruházészlelés engedélyezése](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

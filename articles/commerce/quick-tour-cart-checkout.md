---
title: Kosár és pénztár oldalainak áttekintése
description: Ez a cikk áttekintést nyújt a bevásárlókocsi és a pénztár lapról Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: c2fad50b58db8213ecc246376e28b2ae43f77a08
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286438"
---
# <a name="cart-and-checkout-pages-overview"></a>Kosár és pénztár oldalainak áttekintése

[!include [banner](includes/banner.md)]

Ez a cikk áttekintést nyújt a bevásárlókocsi és a pénztár lapról Microsoft Dynamics 365 Commerce.

Az e-kereskedelmi webhely kosár lapja minden olyan cikket megjelenít, amelyet egy vevő hozzáad a kosárhoz. A kosár lap a kosár modul segítségével épül fel. A kosár modul olyan tároló, amely az összes olyan modult tárolja, amely szükséges a kosárban található elemek megjelenítéséhez. A kosár modul más modulokat is használhat a rendelés összesítését és a vevői rendelésre alkalmazott promóciós kódok megjelenítéséhez.

Az e-kereskedelmi webhely pénztár lapja lépésről lépésre bemutatja azokat a lépéseket, amelyekkel a vevők megadhatják a rendelés leadásához szükséges összes adatot. A pénztári modulban szerepelhetnek olyan modulok, amelyek a szállítási címet, a szállítási módokat, a számlázási adatokat, a rendelési összesítéseket és a vevői rendelésekhez kapcsolódó egyéb információkat kezelik.

## <a name="cart-page"></a>Kosár oldal

A kosár lap egy bevásárlókosárként szolgál, és minden olyan cikket tartalmaz, amely a kosárba került.

A következő ábra egy olyan kosár-lapot mutat be, amely a modulkönyvtár és a „gyár” téma alapján készült.

![Példa a kosár oldalra.](./media/cart2.PNG)

A kosár lap fő törzse minden olyan cikket megjelenít, amelyet egy vevő hozzáadott a kosárhoz. Minden vonatkozó kedvezmény megjelenítésre kerül. A kedvezmények között a összetett kedvezmények is szerepelnek. A példák között szerepel a "„Vásároljon 3 terméket, és kap 10% kedvezményt” vagy a „Vásároljon egy üveget és egy hátizsákot, hogy 10% kedvezményt kapjon”. A rendelésösszesítő modul az engedmények, a szállítási költség, az adók stb. alkalmazása utáni összeget jeleníti meg. Van egy promóciós kód modul is, amely lehetővé teszi, hogy a vevő hozzáadja vagy eltávolítsa a promóciós kódokat.

A vevő névtelenül vagy bejelentkezett felhasználóként is vásárolhat. Ha egy vevő be van jelentkezve, akkor a kosárban lévő cikkek megőrződnek a munkamenetek között. Ily módon a vevő több eszközről is folytathatja a vásárlást.

A kosártól a vevő tovább mehet a pénztárhoz. A vevő a kifizetést a vendég felhasználóként vagy bejelentkezett felhasználóként is kezdeményezheti.

A kosár lap létrehozásával kapcsolatos további tudnivalókat lásd [A kosár modul hozzáadása egy oldalhoz](add-cart-module.md).

## <a name="checkout-page"></a>Pénztár lap

A pénztár oldalon a vevők a rendelés leadásához szükséges adatokat adják meg.

A következő ábra egy olyan pénztár lapot mutat be, amely a modulkönyvtár és a „gyár” téma alapján készült.

![Példa a pénztár oldalra.](./media/Checkout.PNG)

A pénztári lap fő törzse az a rész, ahol minden rendelési adatot gyűjtenek. Ez az információ tartalmazza a szállítási címet, a szállítási lehetőségeket és a fizetési adatokat. A pénztári folyamatoknak meghatározott lépéseket kell követnie, mivel az adatokat meghatározott sorrendben kell megadni a feldolgozáshoz. Például a szállítási címet meg kell adni, mielőtt a szállítási költségek kiszámíthatók lennének, és a kifizetés engedélyezhető lenne.

### <a name="shipping-address"></a>Szállítási cím

Ha az árukat szállítani kell, a szállítási cím megadása kötelező. Minden egyes területhez be lehet állítani a szállítási címek formátumát a Dynamics 365 Commerce alkalmazásban. Ha például a cikkek szállítása az Egyesült Államokba történik, a szállítási címnek tartalmaznia kell egy utcacímet, egy államot és egy irányítószámot. A szállítási cím mezőiben megtörténik néhány alapvető beviteli ellenőrzés, például az alfanumerikus karakterek, a maximális hossz és a számok ellenőrzése. Noha maga a cím érvényessége nincs ellenőrizve, ez az ellenőrzés a testreszabott külső szolgáltatások használatával elvégezhető.

A szállítási cím a kosár minden olyan cikkére érvényes, amelyre a „szállítás” beállítás ki van kiválasztva. Ha a modulkönyvtárban megadott pénztár folyamatot használja, akkor az egyes kosár cikkek nem szállíthatók különböző címekre. Ha szüksége van erre a lehetőségre, akkor a pénztár modulok testreszabásával lehet megvalósítani.

A szállítási cím megadása után megjelennek a Dynamics 365 Commerce online áruházból elérhető szállítási módok. A szállítási módokat és az általuk támogatott címeket a Commerce modulban konfigurálhatja.

### <a name="payment"></a>Fizetés

A pénztári folyamat következő lépése a fizetés. Az e-kereskedelemben több fizetési mód használható a rendelések leadásához, például a hitelkártyák, az ajándékutalványok és a hűségpontok. A fizetési módok kombinációja is használható. A használt fizetési módoktól függően előfordulhat, hogy további információk megadása szükséges. Például a hitelkártyás fizetéshez számlázási cím szükséges. A hitelkártyás fizetések feldolgozása a Adyen fizetési csatlakozó használatával történik.

#### <a name="loyalty-points"></a>Hűségpontok

A pénztári folyamat során a hűségprogram-tagsággal rendelkező vevő, aki rendelkezi összegyűjtött hűségpontokkal, beválthatja ezeket a hűségpontokat egy rendeléshez. A hűségpontok modul csak akkor jelenik meg, ha a vevőnek van már hűségprogram tagsága. A nem tagok és vendég felhasználók számára ez a modul rejtett.

#### <a name="gift-cards"></a>Ajándékutalványok

A modulkönyvtár lehetővé teszi belső ajándékutalványok beváltását a rendeléshez. Belső ajándékutalvány alkalmazásához a vevőnek be kell jelentkeznie. A további biztonság érdekében ajánlott a folyamatot úgy testreszabni, hogy a belső ajándékkártyákhoz személyes azonosítószám (PIN) legyen használva.

### <a name="signed-in-and-guest-users"></a>Bejelentkezett és vendég felhasználók

A vevő a fizetési folyamatot a vendég felhasználóként vagy bejelentkezett felhasználóként is elvégezheti. Ha a vevő bejelentkezik, akkor a program automatikusan lekéri a fiókhoz tartozó adatokat, például a mentett szállítási címeket és a mentett hitelkártyák adatait.

### <a name="order-summary"></a>Rendelésösszesítés

A pénztár a kosárban található cikkek összesítését megjeleníti, így a vevő ellenőrizheti a rendelést, mielőtt leadja azt. A sorokban szereplő cikkek nem szerkeszthetők a pénztári folyamat során. Azonban rendelkezésre áll egy a kosárra mutató hivatkozást, ha a felhasználó vissza szeretne lépni és szerkeszteni szeretné a sorokban szereplő cikkeket.

Miután a vevő megadta a szállítási és számlázási adatokat, a rendelési összesítés azt az összeget jeleníti meg amely a hűségpontok, ajándékutalványok és egyéb fizetések alkalmazása után esedékes.

### <a name="order-confirmation-and-email"></a>Rendelést megerősítése és e-mail.

Amikor a vevő lead egy rendelést, kap egy visszaigazolási számot. Ezen a ponton a kifizetés engedélyezve van, de még nincs beterhelve. A kifizetés csak akkor kerül terhelésre, ha a rendelés teljesítve van (azaz kiszállították vagy átvették).

Egy rendelés létrehozása után a vásárlónak egy rendelés-visszaigazolási e-mail lesz kiküldve.

A pénztár lap létrehozásával kapcsolatos további tudnivalókat lásd [Pénztár modul hozzáadása egy oldalhoz](add-checkout-module.md).

## <a name="additional-resources"></a>További erőforrások

[Kezdőlap áttekintése](quick-tour-home-page.md)

[Termékadatok oldalainak áttekintése](quick-tour-pdp.md)

[Fiókkezelési oldalak áttekintése](quick-tour-account-management.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Számlakezelési oldalak és modulok
description: Ez a témakör a fiókkezelési lapokkal és modulokkal foglalkozik a Microsoft Dynamics 365 Commerce alkalmazásban.
author: v-chgri
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: df4959a61f1b2948c62a558523a848ff8b2fe0a8
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796294"
---
# <a name="account-management-pages-and-modules"></a>Számlakezelési oldalak és modulok

[!include [banner](includes/banner.md)]

Ez a témakör a fiókkezelési lapokkal és modulokkal foglalkozik a Microsoft Dynamics 365 Commerce alkalmazásban.

A fiókkezelési lapok egy csoportjára vonatkozik, amelyek a felhasználói fiókkal kapcsolatos információk kezelésére szolgálnak a Dynamics 365 Commerce alkalmazásban. A fiókkezelési lapok közé tartozik a fiókkezelés nyitólapja, a felhasználói profil lapja, a felhasználói cím lapja, a rendeléselőzmények lapja, a rendelés részleteinek lapja, a hűségprogram lapja és a kívánságlista lapja.

### <a name="account-management-landing-page"></a>A fiókkezelés érkezési oldala

A fiókkezelés nyitólapja a következő modulokat használja:

- **Tároló** – az összes számlavezetési oldalmodult egy tárolón belül kell elhelyezni. 
- **Számla üdvözlőcsempéje** – Ez a modul a számlavezetési lap üdvözlő üzenetének biztosítására szolgál. A címsorhoz tartozó tulajdonságokat tartalmazza.
- **Számla általános csempéje** – ez a modul a számlavezetés oldalakhoz, például a "rendelési előzmények" vagy a "saját profil" oldalakhoz való hivatkozások biztosítására használható. Az általános csempe modul bármely lap csempéjének konfigurálására használható. A Fabrikamnál ez a modul a számlavezetés nyitóoldala "Order History" és "saját profil" hivatkozásához használatos.
- **Számla kívánságlista csempéje** – Ez a modul a vevői kívánságlistán szereplő cikkek összesítését biztosítja. Előfordulhat például, hogy a „10 cikk szerepel a kívánságlistáján.” felirat látható. A címsorra és a „részletek megtekintése” hivatkozásra vonatkozó tulajdonságokat tartalmaz. A „Részletek megtekintése” hivatkozást úgy kell konfigurálni, hogy a kívánságlista lapra irányítson át. 
- **Számla címcsempéje** – Ez a modul a felhasználó címének összefoglalóját biztosítja. Előfordulhat például, hogy itt a „2 cím van hozzáadva a fiókjához.” üzenet látható. A címsorra és a „részletek megtekintése” hivatkozásra vonatkozó tulajdonságokat tartalmaz. A „Részletek megtekintése” hivatkozást úgy kell konfigurálni, hogy a felhasználó címe lapra irányítson át.
- **Számla hűségprogram csempe** – Ez a modul a hűségprogrammal kapcsolatos információk megjelenítésére és hivatkozására szolgál. Ennek a csempének két állapota van: egy állapot a hűségprogramhoz való csatlakozásra mutató hivatkozásokat mutat be, ha a felhasználó még nem tagja. A másik állapot olyan hivatkozásokat mutat be, amelyek a hűségprogram részleteinak lapját jelenítik meg, ha a felhasználó már tag. A tulajdonságok között szerepel a címsor, a "Feliratkozás" hivatkozás, valamint a "hűségprogram megtekintése" hivatkozás. A „Hűségprogram megtekintése” hivatkozást úgy kell konfigurálni, hogy a hűségprogram lapra irányítson át. A „Feliratkozás” hivatkozást úgy kell beállítani, hogy egy olyan lapra irányítson át, amelyen a felhasználók csatlakozhatnak a hűségprogramhoz. 

### <a name="order-history-page"></a>Rendeléselőzmények lap

A rendeléselőzmények lap a rendeléselőzmények modulban jeleníti meg a felhasználó által a közelmúltban leadott összes rendelést.

### <a name="order-details-page"></a>Rendelés részleteit tartalmazó oldal

A rendelés részletei lap részletes adatokat tartalmaz minden rendelésről, és elérhető a rendeléselőzmények lapról. A rendelés részletei modult használja, amely az értékesítési azonosító vagy a tranzakció azonosítója segítségével kéri le a rendelés részleteit.

### <a name="my-profile-page"></a>Saját profillap

A Saját profil oldal a fiókprofil modul segítségével mutatja a felhasználó fiókprofil-adatait. Az oldalon megjelenik a felhasználó fiókjához társított e-mail-cím, valamint a fiókhoz megadott beállítások. Egyéni ügyfélattribútumok beállítása esetén a „További információk” szakasz is megjeleníti ezeket az attribútumokat. A felhasználók szerkeszthetik nevüket, preferenciáikat vagy további adataikat (ha vannak ilyenek).

### <a name="user-address-page"></a>Felhasználó címe lap

A felhasználó címe lapon látható a felhasználói fiókhoz társított címek listája. A felhasználó vagy a fizetés során adta meg a címeit, vagy közvetlenül ezen az oldalon. A felhasználói cím modul a címek hozzáadására és szerkesztésére, az elsődleges cím beállítására, valamint a meglévő címek megjelenítésére szolgál a lapon.

### <a name="wish-list-page"></a>Kívánságlista lap

A kívánságlista lap megjeleníti azokat a cikkeket, amelyeket hozzáadtak a vevői kívánságlistához. A kívánságlista modult használja a kívánságlistán szereplő cikkek megjelenítéséhez.

### <a name="loyalty-page"></a>Hűségprogram oldala

A hűségprogram lapon a vevők megtekinthetik a hűségprogramjuk részleteit, ha már tagok egy hűségprogramban. Megtekinthetik a legutóbbi tranzakciók során az általuk gyűjtött és beváltott pontokat is. A lap a hűségprogram részletei modulban bemutatja a hűségprogram adatait. 

A hűségprogramhoz való csatlakozáshoz létre lehet hozni egy marketinges lapot a hűségprogramra való feliratkozás és a hűségprogram feltételei modulokkal. Ha a felhasználó nem tagja egy hűségprogramnak, akkor ezek a modulok lehetővé teszik a felhasználó számára a feliratkozást.

## <a name="additional-resources"></a>További erőforrások

[Modulkönyvtár – áttekintés](starter-kit-overview.md)

[Tárolómodul](add-container-module.md)

[Vásárlásmező-modul](add-buy-box.md)

[Kosármodul](add-cart-module.md)

[Pénztármodul](add-checkout-module.md)

[Rendelésmegerősítési modul](order-confirmation-module.md)

[Fejlécmodul](author-header-module.md)

[Láblécmodul](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
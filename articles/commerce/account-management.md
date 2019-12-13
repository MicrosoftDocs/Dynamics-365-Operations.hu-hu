---
title: Fiókkezelési lapok és modulok
description: Ez a témakör a fiókkezelési lapokkal és modulokkal foglalkozik a Microsoft Dynamics 365 Commerce alkalmazásban.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3986505a7e0e8d33d5b8ff2c06f493335731a8d9
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785380"
---
# <a name="account-management-pages-and-modules"></a>Fiókkezelési lapok és modulok

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör a fiókkezelési lapokkal és modulokkal foglalkozik a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A fiókkezelési lapok egy csoportjára vonatkozik, amelyek a felhasználói fiókkal kapcsolatos információk kezelésére szolgálnak a Dynamics 365 Commerce alkalmazásban. A fiókkezelési lapok közé tartozik a fiókkezelés nyitólapja, a felhasználói profil lapja, a felhasználói cím lapja, a rendeléselőzmények lapja, a rendelés részleteinek lapja, a hűségprogram lapja és a kívánságlista lapja.

### <a name="account-management-landing-page"></a>A fiókkezelés érkezési oldala

A fiókkezelés nyitólapja a következő modulokat használja:

- **Tartalomelhelyezés** – Ez a modul egy tárolómodul, amely a fiókkezelés nyitólapjának összes modulját tartalmazza.
- **Fiók üdvözlőeleme** – Ez a modul a fiókkezelési lap üdvözlő üzenetének biztosítására szolgál. A fejlécre és a csempeméretre vonatkozó tulajdonságokat tartalmaz. A **Csempeméret** tulajdonság meghatározza a modul szélességét a tartalomelhelyezési modulban. Az értékek **1** és **12** között lehetnek, ahol a **12** a tartalomelhelyezési tároló teljes szélességét jelenti.
- **Fiók rendelésleadási eleme** – Ez a modul a felhasználói fiók által leadott rendelések számának összefoglalására szolgál. A fejlécre, a csempeméretre és a „részletek megtekintése” hivatkozásra vonatkozó tulajdonságokat tartalmaz. A „részletek megtekintése” hivatkozást úgy kell konfigurálni, hogy a rendeléselőzmények lapra irányítson át.
- **Fiók profil elhelyezési eleme** – Ez a modul a felhasználói profil összesítését biztosítja. A fejlécre, a csempeméretre és a „részletek megtekintése” hivatkozásra vonatkozó tulajdonságokat tartalmaz. A „részletek megtekintése” hivatkozást úgy kell konfigurálni, hogy a felhasználói profil lapra irányítson át.
- **Fiók kívánságlista eleme** – Ez a modul a vevői kívánságlistán szereplő cikkek összesítését biztosítja. Előfordulhat például, hogy a „10 cikk szerepel a kívánságlistáján.” felirat látható. A fejlécre, a csempeméretre és a „részletek megtekintése” hivatkozásra vonatkozó tulajdonságokat tartalmaz. A „részletek megtekintése” hivatkozást úgy kell konfigurálni, hogy a kívánságlista lapra irányítson át.
- **Fiók cím eleme** – Ez a modul a felhasználó címének összefoglalóját biztosítja. Előfordulhat például, hogy itt a „2 cím van hozzáadva a fiókjához.” üzenet látható. A fejlécre, a csempeméretre és a „részletek megtekintése” hivatkozásra vonatkozó tulajdonságokat tartalmaz. A „részletek megtekintése” hivatkozást úgy kell konfigurálni, hogy a felhasználó címe lapra irányítson át.
- **Fiók hűségprogram elem** – Ez a modul a hűségprogrammal kapcsolatos információk megjelenítésére és hivatkozására szolgál. A fejlécre, a csempeméretre, a „részletek megtekintése” hivatkozásra és a „legyen tag” hivatkozásra vonatkozó tulajdonságokat tartalmaz. A „részletek megtekintése” hivatkozást úgy kell konfigurálni, hogy a hűségprogram lapra irányítson át. A „legyen tag„ hivatkozást úgy kell beállítani, hogy egy olyan lapra irányítson át, amelyen a felhasználók csatlakozhatnak a hűségprogramhoz.

### <a name="order-history-page"></a>Rendeléselőzmények lap

A rendeléselőzmények lap a rendeléselőzmények modulban jeleníti meg a felhasználó által a közelmúltban leadott összes rendelést.

### <a name="order-details-page"></a>Rendelés részleteit tartalmazó oldal

A rendelés részletei lap részletes adatokat tartalmaz minden rendelésről, és elérhető a rendeléselőzmények lapról. A rendelés részletei modult használja, amely az értékesítési azonosító vagy a tranzakció azonosítója segítségével kéri le a rendelés részleteit.

### <a name="user-profile-page"></a>Felhasználói profil lap

A felhasználói profil lap a felhasználói fiók adatait jeleníti meg, például a felhasználó nevét és e-mail-címét. A felhasználói profil modult használja. Annak ellenére, hogy az e-mail-cím nem távolítható el, lehetőség van a szerkesztésére.

### <a name="user-address-page"></a>Felhasználó címe lap

A felhasználó címe lapon látható a felhasználói fiókhoz társított címek listája. A felhasználó vagy a fizetés során adta meg a címeit, vagy közvetlenül ezen az oldalon. A felhasználói cím modul a címek hozzáadására és szerkesztésére, az elsődleges cím beállítására, valamint a meglévő címek megjelenítésére szolgál a lapon.

### <a name="wish-list-page"></a>Kívánságlista lap

A kívánságlista lap megjeleníti azokat a cikkeket, amelyeket hozzáadtak a vevői kívánságlistához. A kívánságlista modult használja a kívánságlistán szereplő cikkek megjelenítéséhez.

### <a name="loyalty-page"></a>Hűségprogram oldala

A hűségprogram lapon a vevők csatlakozhatnak egy hűségprogramhoz, vagy ha már tagok egy hűségprogramban, megtekinthetik a programjuk részleteit. Megtekinthetik a legutóbbi tranzakciók során az általuk gyűjtött és beváltott pontokat is.

## <a name="additional-resources"></a>További erőforrások

[Kezdő csomag áttekintése](starter-kit-overview.md)

[Tárolómodul](add-container-module.md)

[Vásárlásmező-modul](add-buy-box.md)

[Kosármodul](add-cart-module.md)

[Fizetésmodul](add-checkout-module.md)

[Rendelésmegerősítési modul](order-confirmation-module.md)

[Fejlécmodul](author-header-module.md)

[Láblécmodul](author-footer-module.md)

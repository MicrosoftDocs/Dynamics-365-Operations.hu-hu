---
title: Ajándékutalvány-modul
description: Ez a témakör az ajándékutalvány-modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5a4aaf8e072f6547fe1dcf6fa156d2e144fd03ed806a2dc809a2cedb991461f7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6728339"
---
# <a name="gift-card-module"></a>Ajándékutalvány modul

[!include [banner](includes/banner.md)]

Ez a témakör az ajándékutalvány-modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

Az ajándékutalvány egy gyakori fizetési mód, és az ajándékutalvány modulok használható az e-kereskedelmi tranzakciókban az ajándékutalványok elfogadására. Az ajándékutalvány modul támogatja a Dynamics 365, SVS és a Givex ajándékutalványokat. A SVS és a Givex ajándékutalványok a Adyen fizetési szolgáltatón keresztül válthatók be. A külső ajándékutalványok (például SVS és Givex) támogatásával kapcsolatos további tudnivalókat lásd: [Támogatás a külső ajándékutalványokhoz](./dev-itpro/gift-card.md).

> [!NOTE]
> A pénztári folyamat során történő SVS- és Givex-ajándékutalvány beváltásához nyújtott támogatás a Dynamics 365 Commerce 10.0.11-es kiadásban érhető el. 

Két ajándékutalvány-modul érhető el:

- **Ajándékutalvány** – Ez a modul a pénztár oldalon használható egy ajándékutalvány fizetőeszközként történő beváltására. 
- **Ajándékutalvány egyenlegének ellenőrzése** – Ez a modul bármilyen oldalon használható az ajándékutalvány egyenlegének ellenőrzésére. Ez a modul elérhető a Commerce alkalmazás 10.0.14 vagy újabb verziójában.

> [!NOTE]
> Az ajándékutalvány-egyenleget ellenőrző modul támogatása a Dynamics 365 Commerce 10.0.14-es kiadásában érhető el.

A következő kép egy Pénztár oldalon használt ajándékutalvány modul egy példáját jeleníti meg.

![Példa egy ajándékutalvány-modulra.](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a>Modul tulajdonságai

- **További mezők megjelenítése** – Ez a tulajdonság határozza meg, hogy milyen mezőket kell megjeleníteni az ajándékutalványokhozaz ajándékutalvány számán túl, amely alapértelmezés szerint mindig látható. Például egyes ajándékutalványok támogatják a személyes azonosítószám (PIN-kód) megjelenítését, mások a PIN-kód és a lejárati dátum megjelenítését. Másik lehetőségként a tulajdonság értéke „Nincs” lehet, amely csak az ajándékutalvány számát jeleníti meg, és további mezőket nem.

    A következő értékek támogatottak:

    - PIN-kód
    - Lejárati dátum
    - PIN és lejárati dátum 
    - None

- **Engedélyezés a vendégfelhasználók számára** – Ha ez a tulajdonság engedélyezve van, a vendégfelhasználók beválthatják vagy ellenőrizhetik az ajándékutalványok egyenlegét. Ez a tulajdonság megköveteli, hogy az ajándékutalványok anonim (vendég) hozzáférése engedélyezve legyen a Commerce központban. A további tudnivalókat lásd: [Ajándékutalványos fizetések engedélyezése vendégkifizetéshez](#enable-gift-card-payments-for-guest-checkout).

> [!IMPORTANT]
> Az **Engedélyezés a vendégfelhasználók számára** tulajdonság a Commerce 10.0.21-es verziójától érhető el. Ehhez a Commerce modultárcsomag 9.31-es verziójának telepítése szükséges.

## <a name="site-settings-for-gift-card-modules"></a>Ajándékutalvány-modulok webhely-beállításai

A Commerce webhelykészítő **Webhelybeállítások \> Bővítmények** területén van egy ajándékutalvány-modul, amelynek neve **Támogatott ajándékutalvány-típus**. Ez a beállítás három értéket támogat:
- **Dynamics 365 ajándékutalvány** – Ha ezt a beállítást alkalmazza, akkor az ajándékutalvány modul csak a Dynamics 365 utalványok beváltását teszi lehetővé. Ez a beállítás csak az e-Commerce webhely bejelentkezett felhasználóinak esetében támogatott.
- **SVS és Givex ajándékutalványok** – Ha ezt a beállítást alkalmazza, akkor az ajándékutalvány modul csak a Givex és SVS utalványok beváltását teszi lehetővé. Ez a beállítás az e-Commerce webhely bejelentkezett és névtelen felhasználói esetében támogatott.
- **Dynamics 365, SVS és Givex ajándékutalványok** – Ha ezt a beállítást alkalmazza, akkor az ajándékutalvány modul a Dynamics 365, Givex és SVS utalványok beváltását teszi lehetővé. Ez a beállítás csak az e-Commerce webhely bejelentkezett felhasználóinak esetében támogatott.

> [!IMPORTANT]
> Ezek a beállítások a Dynamics 365 Commerce 10.0.11-es verziójában érhetők el, és csak akkor szükségesek, ha támogatásra van szüksége az SVS- vagy Givex-ajándékutalványok használatakor. Ha a Dynamics 365 Commerce egy korábbi verziójáról frissít, akkor manuálisan kell frissítenie az appsettings.json fájlt. Az appsettings.json fájlok frissítésével kapcsolatos tudnivalókat lásd az [SDK- és modulkönyvtár-frissítések](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file) témakörben. 

## <a name="extend-internal-gift-cards-for-use-in-e-commerce-storefronts"></a>Belső ajándékutalványok kiterjesztése az e-kereskedelmi áruházakban való használatra

Alapértelmezés szerint a belső ajándékutalványok nincsenek az e-kereskedelmi üzletben való használatra optimalizálva. Ezért mielőtt engedélyezné, hogy a belső ajándékutalványok használhatók legyenek fizetésre, be kell állítania azokat a bővítményeket, amelyek biztonságossá teszik őket. Itt vannak azok az ajándékutalvány-területek, amelyek a belső ajándékutalványok termelésben való használatának engedélyezése előtt bővítenie kell:

- **Ajándékutalvány száma** – A számsorozatok a belső ajándékutalványok ajándékutalvány-számának előállítására használhatók. Mivel a számsorozatok könnyen kitalálhatók, ki kell terjesztenie az ajándékutalvány-számok létrehozását úgy, hogy a kiadott ajándékutalvány-számokhoz véletlenszerű, kriptográfiai szempontból biztonságos sztringeket használjon.
- **GetBalance** – a **GetBalance** API használatával lehet megkeresni az ajándékutalvány-egyenlegeket. Alapértelmezés szerint ez az API nyilvános. Ha nincs szükség PIN-kódra az ajándékutalvány-egyenlegek kereséséhez, kockázatot jelent, hogy a találgatásos támadások a **GetBalance** API-t használják az egyenleget tartalmazó ajándékutalványok számainak megkereséséhez. A belső ajándékutalványokra és API-szabályozásra vonatkozó PIN-követelmények megvalósításával csökkenthető a kockázat.
- **PIN** - Alapértelmezés szerint a belső ajándékutalványok nem támogatják a PIN-kódokat. A belső ajándékutalványokat ki kell terjeszteni, hogy az egyenlegek ellenőrzéséhez PIN-kód legyen szükséges. Ez a funkció az ajándékutalványok zárolására is használható, ha egymás után több helytelen kísérlet történt a PIN-kód megadására.

## <a name="enable-gift-card-payments-for-guest-checkout"></a>Ajándékutalványos fizetések engedélyezése vendégkifizetéshez

Alapértelmezés szerint a vendég (névtelen) fizetésnél az ajándékutalványos fizetések nem engedélyezettek. Kövesse az alábbi lépéseket az engedélyezésükhöz.

1. A Commerce központi felületén lépjen a **Kiskereskedelem és kereskedelem \> Csatornabeállítás \> Pénztárbeállítás \> Pénztár \> Pénztárműveletek** elemre.
1. Válassza ki és tartsa lenyomva a rács fejlécét (vagy kattintson rá a jobb gombbal), majd válassza az **Oszlopok beszúrása** lehetőséget.
1. Az **Oszlopok beszúrása** párbeszédpanelen jelölje be az **AllowAnonymousAccess** jelölőnégyzetet.
1. Válassza ki a **Frissítés** lehetőséget.
1. Az **520** (Ajándékutalván egyenlege) és **214** műveleteknél állítsa az **AllowAnonymousAccess** értékét **1**-re.
1. Válassza a **Mentés** lehetőséget.
1. Futtassa az **1090** ütemezési feladatot a módosítások szinkronizálására a csatornaadatbázisba. 

## <a name="add-a-gift-card-module-to-a-page"></a>Ajándékutalvány-modul felvétele egy oldalra

Az ajándékutalvány-modulnak a pénztár lapra történő hozzáadásával és a szükséges tulajdonságok beállításával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Fizetésmodul](add-checkout-module.md).

## <a name="additional-resources"></a>További erőforrások

[Kosármodul](add-cart-module.md)

[Kosárikon modul](cart-icon-module.md)

[Fizetésmodul](add-checkout-module.md)

[Fizetési modul](payment-module.md)

[Szállítási cím modul](ship-address-module.md)

[Szállítási lehetőségek modul](delivery-options-module.md)

[Átvételi információk modul](pickup-info-module.md)

[Rendelési részletek modul](order-confirmation-module.md)

[Támogatás külső ajándékutalványokhoz](./dev-itpro/gift-card.md)

[SDK- és modulkönyvtár-frissítések](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

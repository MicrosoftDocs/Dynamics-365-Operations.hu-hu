---
title: Fejlécmodul
description: Ez a témakör a fejlécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet oldalfejléceket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: efadd19681bbb21ea5b2b469e55bc6f4b0535046
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025661"
---
# <a name="header-module"></a>Fejlécmodul


[!include [banner](includes/banner.md)]

Ez a témakör a fejlécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet oldalfejléceket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A Dynamics 365 Commerce szolgáltatásban egy oldalfejléc több modulból áll, például a fejlécből, a navigációs menüből, a keresésből, a promóciós szalagcímből és a cookie-hozzájárulás moduljaiból. 

A fejlécmodul tartalmaz egy webhelyemblémát, a navigációs hierarchiára mutató hivatkozásokat, a webhely egyéb oldalaira mutató hivatkozásokat, egy kosár-szimbólumot, egy kívánságlista szimbólumot, bejelentkezési beállításokat és a keresési sávot. A program automatikusan optimalizálja a fejlécmodult arra az eszközre, amelyről a webhelyet megtekintik (azaz egy asztali eszközre vagy egy mobileszközre). Egy mobileszköz esetében például a navigációs sáv össze van csukva egy **Menü** gombba (amelyet néha *hamburger menünek* neveznek).

## <a name="properties-of-a-header-module"></a>Fejlécmodul tulajdonságai

A fejlécmodul az **Emblémakép**, **Embléma hivatkozása** és **Saját fiókhivatkozások** tulajdonságokat támogatja. 

Az **Emblémakép** és az **Emblémahivatkozás** tulajdonságokkal adható meg az embléma az oldalon. További tudnivalók: [Embléma hozzáadása](add-logo.md). 

A **Saját fiókhivatkozások** tulajdonsággal megadhatók olyan fiókoldalak, amelyekre mutató hivatkozásokat a webhelytulajdonos meg akar jeleníteni a fejlécben.

## <a name="modules-that-are-available-in-a-header-module"></a>A fejlécmodulban elérhető modulok

A következő modulban használható a fejlécmodulban:

- **Navigációs menü** – A navigációs menü a csatorna navigációs hierarchiáját és más statikus navigációs hivatkozásokat jelenít meg. A csatorna navigációs hierarchiája a Dynamics 365 Commerce alkalmazásban állítható be. A navigációs menü egy **navigációs forrás** tulajdonsággal rendelkezik, amellyel megadhatók a Retail Server navigációs menüelemei és a statikus menüelemek forrásként. Ha a statikus menüelemek forrásként vannak megadva, akkor a webhely más lapjaihoz kapcsolódó relatív hivatkozásokat is meg lehet adni. A konfigurált elemek ezután fejlécnavigációként jelennek meg. 
- **Keresősáv** – A keresőmodul lehetővé teszi a felhasználók számára, hogy keresési kifejezéseket írjanak be, amelyekkel termékeket kereshetnek. Az alapértelmezett keresési lap URL-jét és a keresési lekérdezések paramétereit a **Webhelybeállítások \> Bővítmények** részben kell megadni. A keresési modulnak van olyan tulajdonsága, amely lehetővé teszi a keresési gomb vagy címke elrejtését szükség esetén. A keresési modul olyan automatikus javaslati beállításokat is támogat, mint a termék, a kulcsszó és a kategória keresési eredményei.

## <a name="create-a-header-module-for-a-page"></a>Fejlécmodul létrehozása egy oldalhoz

Fejlécmodul létrehozásához kövesse az alábbi lépéseket.

1. Hozzon létre egy **Fejléctöredék** nevű töredéket, majd adjon hozzá egy tárolómodult.
1. A tárolómodul tulajdonságlapján a **Szélesség** tulajdonságot állítsa **Tároló kitöltése** értékre.
1. Adjon a tárolómodulhoz promóciós szalagcímet tartalmazó és cookie-kkal kapcsolatos hozzájárulásra vonatkozó modulokat.
1. Adjon másik tárolómodult a töredékhez, és a **Szélesség** tulajdonságot állítsa **Tároló kitöltése** értékre.
1. Vegyen fel egy fejlécmodult a második tárolómodulba.
1. A fejlécmodul **Navigációs menü** helyére adja hozzá a navigációsmenü-modult. 
1. A navigációs menü modul tulajdonságlapján konfigurálja a navigációs menü modul tulajdonságait.
1. A fejlécmodul **Keresés** helyén adjon hozzá egy keresési modult. 
1. A keresési modul tulajdonságlapján konfigurálja a keresési modul tulajdonságait. 
1. Mentse az oldaltöredéket, fejezze be a szerkesztését, majd tegye közzé. 

Ha azt szeretné, hogy minden lapon megjelenjen a fejléc, hajtsa végre az alábbi lépéseket a webhelyhez létrehozott összes oldalsablon esetében.

1. Az alapértelmezett lap **Fő** helyén adja hozzá a fejlécmodul-töredéket, amely tartalmazza a fejléc fejlécmodulját.
1. Mentse a sablont, fejezze be a szerkesztését, majd tegye közzé.

## <a name="additional-resources"></a>További erőforrások

[Kezdő csomag áttekintése](starter-kit-overview.md)

[Tárolómodul](add-container-module.md)

[Vásárlásmező-modul](add-buy-box.md)

[Kosármodul](add-cart-module.md)

[Fizetésmodul](add-checkout-module.md)

[Rendelésmegerősítési modul](order-confirmation-module.md)

[Fejlécmodul](author-header-module.md)

[Láblécmodul](author-footer-module.md)

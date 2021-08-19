---
title: Adventure Works téma áttekintése
description: Ez a témakör áttekintést nyújt az Adventure Works témáról, és bemutatja, hogyan alkalmazható a téma a webhelyoldalakra a Microsoft Dynamics 365 Commerce rendszerében.
author: anupamar-ms
ms.date: 07/21/2021
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
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 5bade39b1b327a0784272669ce074d9762a318c2cad6d4105f0d186c91d2593f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6733228"
---
# <a name="adventure-works-theme-overview"></a>Adventure Works téma áttekintése

[!include [banner](includes/banner.md)]

Ez a témakör áttekintést nyújt az Adventure Works témáról, és bemutatja, hogyan alkalmazható a téma a webhelyoldalakra a Microsoft Dynamics 365 Commerce rendszerében.

A Dynamics 365 Commerce rendelkezik egy Adventure Works nevű e-kereskedelmi témával. Az Adventure Works téma sport- és szabadidős termékeket mutat be, és úgy van el optimalizálva, hogy fejlett, multimédiás történetmesélési élményt biztosítson. Modern megjelenést, új elrendezéseket és animációs effekteket biztosítva hoz létre lebilincselő és elkötelezettséget erősítő online vásárlási élményt az e-kereskedelmi ügyfelek számára.

## <a name="trial-environments-in-commerce"></a>Próbakörnyezetek a Commerce-ben

Ha szeretné megnézni, hogyan néz ki a z Adventure Works, ha business-to-consumer (B2C)C és a business-to-business (B2B) webhelyekre telepítik, keresse fel a következő próbawebhelyeket:

- [Adventure Works B2C webhely](https://www.adventure-works.com/)
- [Adventure Works B2B webhely](https://www.adventure-works.com/business)

## <a name="theme-capabilities"></a>Témaképességek

Az Adventure Works téma a következő új képességeket biztosítja:

- A videólejátszó modul mostantól támogatja a címsor-, bekezdés- és hivatkozásfunkciókat a hatékonyabb történetmeséléshez.
- Az animáción használatával jobb lett a tartalmak közötti átmenet.
- A „Hozzáadás a kosárhoz” művelet értesítés helyett a mini bevásárlókocsit hívja meg.
- A gyorsnézet modul egy olyan ablaktábla, amely a számítógépes és a mobilos nézetablakokban is becsúszik.
- A webhelyoldalaknak új elrendezése van. 
- A marketingtartalmak konfigurálhatók a kosárhoz és a mini kosárhoz, ha azok üresek.
- A mini kosárban akciós üzenetek is megjelenhetnek, például "Ingyenes szállítás 50 dollár fölötti rendelésekre".
- A leíráskártyák a keresési és kategóriaoldalakon vannak megjelenítve.

Az Adventure Works téma immár a következő történetmesélési modulokat tartalmazza a Commerce modultárban:

- [Csempelistamodul](tile-list-module.md)
- [Interaktív funkciómodul](interactive-feature-module.md)
- [Aktívképmodul](active-image-module.md)
- [Előfizetési modul](subscribe-module.md)
- [Képlistamodul](image-list-module.md)

Az Adventure Works téma teljesen reszponzív, és optimalizált élményt kínál számítógépes, mobilos és táblagépes nézetben is.

> [!IMPORTANT]
> Az Adventure Works téma és az új modulok a Dynamics 365 Commerce 10.0.20-as kiadásában érhetők el.

Az alábbi ábra egy olyan kezdőlapra mutat példát, amely az Adventure Works témát használja.

![Példa egy olyan kezdőlapra, amely az Adventure Works témát használja](./media/aw_b2c.PNG)

Az alábbi ábra egy olyan listaoldalra mutat példát, amely az Adventure Works témát használja.

![Példa egy olyan listaoldalra, amely az Adventure Works témát használja](./media/Aw_list.PNG)

Az alábbi ábra egy olyan részletes termékoldalra (PDP) mutat példát, amely az Adventure Works témát használja.

![Példa egy olyan részletes termékoldalra (PDP), amely az Adventure Works témát használja](./media/aw_pdp.PNG)

## <a name="use-the-adventure-works-theme-for-b2b-sites"></a>Az Adventure Works téma használata B2B-webhelyekhez

Az Adventure Works téma referenciatéma is a B2B-webhelyek számára. Minden B2B-modul és munkafolyamat bemutatásra kerül az Adventure Works témában. A B2B-webhely beállításával kapcsolatos további információkért lásd: [B2B-webhely beállítása](./b2b/set-up-b2b-site.md).

Az alábbi ábra egy olyan B2B-kezdőlapra mutat példát, amely az Adventure Works témát használja.

![Példa egy olyan B2B-kezdőlapra, amely az Adventure Works témát használja](./media/aw_b2b.PNG)

## <a name="theme-extensions"></a>Témabővítmények

Az Adventure Works téma számos témabővítményt tartalmaz, például a **Nézetbővítmények** és a **Moduldefiníció** típusú bővítményeket. Az Adventure Works téma használható referenciatémaként a hasonló bővítmények összeállításához. Például az Adventure Works téma listaoldala egy vízszintes finomítóval rendelkező nézetbővítményként van megvalósítva. (Ezzel szemben a bal oldali panel finomítója a Fabrikam témában használatos.)

Ehhez hasonlóan más modulok is tartalmaznak moduldefiníciós bővítményeket. Például a [bevásárlókocsi ikonjának modulja](cart-icon-module.md) két további **Üres kosár** és **Promóciós tartalom** nevű helyet tartalmaz, amelyek a moduldefiníciós bővítmények segítségével vannak megvalósítva. Emellett a fejlécmodulhoz egy új **Mobileembléma** tulajdonság van hozzáadva, amely a mobilos nézetablakok emblémáját támogatja. Ez a tulajdonság fejlécmodul-definíciós kiterjesztésként van megvalósítva.

A témabővítményekkel kapcsolatos további tudnivalókat lásd a [Témabővítmények](e-commerce-extensibility/theme-module-extensions.md) című témakörben.

## <a name="install-the-adventure-works-theme"></a>Az Adventure Works téma telepítése

Az Adventure Works téma telepítésével kapcsolatos tudnivalókat lásd [Az Adventure Works téma telepítése](install-adventure-works.md) témakörben.

## <a name="additional-resources"></a>További erőforrások

[Modultár áttekintése](starter-kit-overview.md)

[Csempelistamodul](tile-list-module.md)

[Interaktívfunkció-modul](interactive-feature-module.md)

[Aktívképmodul](active-image-module.md)

[Feliratkozási modul](subscribe-module.md)

[Képlista modul](image-list-module.md)

[Témabővítmények](e-commerce-extensibility/theme-module-extensions.md)

[Kosárikon modul](cart-icon-module.md)

[B2B e-kereskedelmi webhely beállítása](./b2b/set-up-b2b-site.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Az e-kereskedelem felhasználóinak és szerepköreinek kezelése
description: Ez a cikk bemutatja, hogy hogyan lehet hozzáférést biztosít a felhasználóknak a webhelyre vonatkozó szerzője környezethez Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: 180fc5c0a9c9e247d5bd6ec7f469f313463526df
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279502"
---
# <a name="manage-e-commerce-users-and-roles"></a>Az e-kereskedelem felhasználóinak és szerepköreinek kezelése


[!include [banner](includes/banner.md)]

Ez a cikk bemutatja, hogy hogyan lehet hozzáférést biztosít a felhasználóknak a webhelyre vonatkozó szerzője környezethez Microsoft Dynamics 365 Commerce.

A felhasználói hozzáférés szabályozására és a felhasználóknak a meghatározott feladatok végrehajtásához való jogosultságának biztosítására a webhelyszerkesztő környezet a Microsoft Azure Active Directory (Azure AD) felületen létrehozott biztonsági csoportokat használja. Először egy új vagy meglévő biztonsági csoportot kell társítania a fejlesztői környezet minden szerepköréhez az Azure AD felületről. Ezt követően megadhatja vagy visszavonhatja az egyes felhasználók engedélyeit, ha hozzáadja ezeket a felhasználókat egy megfelelő biztonsági csoporthoz, vagy eltávolítja őket egy biztonsági csoportból.

## <a name="overview-of-roles-in-the-authoring-environment"></a>A szerkesztői környezet szerepköreinek áttekintése

A Dynamics 365 for Commerce szerkesztői környezet a következő szerepköröket támogatja.

| Szerep                 | Leírás |
|----------------------|-------------|
| Rendszergazda | Azoknak a felhasználóknak, akik ezzel a szerepkörrel rendelkeznek hozzáférésük van az összes eszközhöz és az összes értékeléshez és minősítéshez. Webhelyeket is létrehozhatnak. |
| Adminisztrátor   | Azoknak a felhasználóknak, akik ezzel a szerepkörrel rendelkeznek jogosultságuk van minden eszköz, illetve értékelés és minősítés elérésére egy adott webhelystruktúrában. |
| Webes gyártó         | A ezzel a szerepkörrel rendelkező felhasználók lapokat, töredékeket és sablonokat hozhatnak létre, feltölthetik és kezelhetik az eszközöket, valamint gazdagítják a termékeket és kategóriákat. |
| Olvasó               | Az ezzel a szerepkörrel rendelkező felhasználók megtekinthetik a lapokat, a sablonokat, eszközöket, töredékeket, elrendezéseket és a beállításokat, de nem módosíthatják őket. |
| RnR-moderátor        | Az ezzel a szerepkörrel rendelkező felhasználók moderálhatják a termékértékeléseket. |

## <a name="system-administrator-role"></a>Rendszergazda szerepkör

A mikor telepíti a Dynamics 365 Commerce példányt a Microsoft Dynamics Lifecycle Services (LCS) környezetbe, a rendszer ara kéri, hogy adjon meg egy biztonsági csoportot a **Rendszergazda** szerepkörhöz. Ezt a szerepkört a program automatikusan alkalmazza minden olyan webhelyre, amelyet az Ön által konfigurált környezetben hoz létre. Ennek a szerepkörnek a biztonsági csoportja csak az LCS-ben frissíthető. Az **Webhely kezelése** lapon az összes webhelyhez írásvédettként jeleni meg, és csak tájékoztatásul szolgál.

## <a name="administrator-role"></a>Adminisztrátor szerepkör

Amikor új webhelyet hoz létre a Commerce szolgáltatásban, meg kell adnia egy biztonsági csoportot s **Rendszergazda** szerepkörhöz. A témakör korábbi táblázatában található a szerep által adott engedélyek áttekintése.

## <a name="add-or-update-security-groups"></a>Biztonsági csoportok hozzáadása vagy frissítése

Miután létrehozta a webhelyet, csak azok a felhasználók férhetnek hozzá a webhely szerzői környezetéhez, akik **Rendszergazda** és az **Adminisztrátor** szerepkörökhöz társított biztonsági csoportnak tagjai. Ha felhasználókat szeretne hozzárendelni a **Webes gyártó**, **RnR moderátor** és a **Olvasó** szerepkörökhöz biztonsági csoportokat kell hozzárendelnie azokhoz a szerepkörökhöz. Ha egy szerepkörhöz egy biztonsági csoportot szeretne hozzáadni, vagy egy szerepkörhöz aktuálisan hozzárendelt biztonsági csoportot szeretne frissíteni, hajtsa végre az alábbi lépéseket.

1. Menjen a frissíteni kívánt webhelyre.
1. A **Webhely kezelése** modulban nyissa meg a **Biztonság** lapot.
1. Válassza ki a módosítani kívánt szerepkört.
1. Adja hozzá a biztonsági csoportokat a szerepkörökhöz, vagy távolítson el biztonsági csoportokat a szerepköröktől.

## <a name="additional-resources"></a>További erőforrások

[Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához](add-telemetry.md)

[A webhely keresőmotor-optimalizálási (SEO) szempontjai](search-engine-optimization-considerations.md)

[Tartalomra vonatkozó biztonsági házirend (CSP) kezelése](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

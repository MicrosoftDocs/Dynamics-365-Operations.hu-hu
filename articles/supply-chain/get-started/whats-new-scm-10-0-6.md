---
title: Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.6 alkalmazásban (2019. november)
description: Ez a témakör olyan funkciókat ír le, amelyek vagy Dynamics 365 Supply Chain Management újak, vagy módosulnak a 10.0.6-ban.
author: kamaybac
ms.date: 10/28/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 8c97e4e5544c49d2e6a13b34061abfbf50e2932a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844438"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-1006-november-2019"></a>Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.6 alkalmazásban (2019. november)

[!include [banner](../includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Supply Chain Management 10.0.6 új vagy módosított szolgáltatásait ismerteti. Ennek a verziónak a buildszáma 10.0.234. Az általános elérhetőségi dátum novemberben, az új szolgáltatások októberben a korai kiadásokban érhetők el. A 10.0.6 verzióval kapcsolatos további tájékoztatásért lásd: [Kiegészítő források](whats-new-scm-10-0-6.md#additional-resources).

## <a name="product-configuration-models-v2-data-entity"></a>Termékkonfigurálási modellek V2 adatentitás

Megjelent a „termékkonfigurálási modellek” adatentitás második verziója (ennek neve „termékkonfigurálási modellek v2”). Az alapértelmezett sablon a „418 – termék konfigurációs modell” is szükséges, így az új „termékkonfigurálási modellek v2” adatentitást használja a keretrendszer-sablonok importálásához és exportálásához. A sablon nem lesz automatikusan frissítve, így a sablont Önnek kell manuálisan betölteni az alapértelmezésből. A V2 entitás nem beágyazva, hanem külön fájlként exportál egy sort egy mellékletbe, a V1 entitás méretkorlátainak feloldásához. 
 
Mit kell tennie ennek a módosításnak az alkalmazásához?
-    Mivel a V1 entitás elavult, meg kell kezdeni az áttelepítést a V1-ről a V2-re. Ha használja a „418-termék konfigurációs modell” sablont, akkor az „alapértelmezett sablonok betöltést” gombra kattintva újratöltheti a „418 – termékkonfigurációs modellek” sablont
-    Ha meg kell őriznie a meglévő rendszerekkel való kompatibilitást, akkor most továbbra is használhatja a meglévő sablont és az (elavult) v1 entitást mindaddig, amíg az új sablonba át nem helyezi az integrációkat. 

## <a name="feature-management-enhancements"></a>Funkciókezelési fejlesztések
A funkciókezelés immár lehetővé teszi az összes új funkció alapértelmezett engedélyezését, de a funkció engedélyezéséhez megerősítés szükséges, és minden még nem engedélyezett funkciót engedélyezni kell. 


## <a name="purchase-agreement-responsible-party"></a>Beszerzési szerződésért felelős fél
Most lehetősége van arra, hogy a Beszerzési szerződés osztályozási képernyőjén és a létrejövő Beszerzési szerződéseknél elsődleges és másodlagos felelős feleket határozzon meg.  Ez biztosítja, hogy a felhasználók hozzáférjenek a szerződésekhez.

## <a name="rfq-link-on-the-purchase-order-line"></a>Árajánlatkérés hivatkozás a Beszerzési rendelés során
A beszerzési rendelési sorokhoz hozzáadhat egy hivatkozást, amely visszamutat arra az árajánlatkérésre, amelyből származik, így a felhasználó könnyedén elérheti az alátámasztó árajánlatkérési dokumentumot.

## <a name="additional-resources"></a>További erőforrások

### <a name="bug-fixes"></a>Hibajavítások
Ha további tájékoztatást szeretne kapni a 10.0.6 részét képező frissítésekben található hibajavításokról, lépjen be a Lifecycle Services (LCS) szolgáltatásokba, és tekintse meg a [Tudásbázis cikket](https://fix.lcs.dynamics.com/Issue/Details?bugId=369581&dbType=3&qc=ba058110be40fe16a39469298041b1a7baf82eb65bb9df4d864602d2c6bf93d7).

### <a name="platform-update-30"></a>Platform update 30
A Microsoft Dynamics 365 Supply Chain Management 10.0.6 a 30-as platform frissítést tartalmazza. A 30-as platform frissítésével kapcsolatos további tudnivalókat lásd: [Újdonságok vagy módosítások a 30-as platformfrissítésben](../../fin-ops-core/fin-ops/get-started/whats-new-platform-update-30.md).

### <a name="dynamics-365-2019-release-wave-2-plan"></a>Dynamics 365: 2019-es 2. hullám tervei
Kíváncsi a bármelyik üzleti alkalmazásával vagy platformjával kapcsolatos, közelgő és a közelmúltban bevezetett lehetőségekre?

Lásd: [Dynamics 365: 2019-as 2. frissítési hullám tervét](/dynamics365-release-plan/2019wave2/). A részleteket minden apró információmorzsáig bezárólag egyetlen dokumentumban rögzítettük, amelyet felhasználhat a tervezés során.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Eltávolított és elavult Supply Chain Management szolgáltatások

A [cikk Eltávolított Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) vagy elavult funkciói olyan funkciókat írnak le, amelyek már el vannak távolítva, illetve amelyek már el vannak távolítva vagy elavultak az Ellátásilánc-kezeléshez.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Mielőtt a funkciót eltávolítanának a termékből, [Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) az értékcsökkenési értesítés 12 hónappal az eltávolítás előtt törlődik az Eltávolított vagy elavult funkciókból.

Olyan módosítások esetén, amelyek csak a fordítási időt érintik, de binárisan kompatibilisek a tesztkörnyezettel és a termelési környezettel, az elavulási idő 12 hónapnál rövidebb lesz. Ezek általában olyan funkcionális frissítések, amelyeket a fordítón kell elvégezni.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
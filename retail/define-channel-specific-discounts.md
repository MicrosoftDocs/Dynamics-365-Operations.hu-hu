---
title: "Csatornaspecifikus engedmények definiálása"
description: "A kiskereskedők gyakran különböző engedményeket állítanak be a különböző csatornákon. Ez a témakör ellenőrzi azokat a fogalmakat, amelyeket a megadott csatornára vonatkozó engedmények létrehozásához tudnia kell."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: RetailAffiliationPriceGroup, RetailCatalogPriceGroup, RetailChannelPriceGroup, RetailDiscountPriceGroup, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailStoreItemPriceList, RetailStoreTable
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16401
ms.assetid: d807fd51-86aa-47a0-8e00-6c5ddd21ff6b
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b21fd97426b331726c12ea29f89817a46dd445c3
ms.openlocfilehash: b2f59db59ea49925c3bb5e1d75beee95191220d0
ms.lasthandoff: 03/31/2017


---

# <a name="define-channel-specific-discounts"></a>Csatornaspecifikus engedmények definiálása

A kiskereskedők gyakran különböző engedményeket állítanak be a különböző csatornákon. Ez a témakör ellenőrzi azokat a fogalmakat, amelyeket a megadott csatornára vonatkozó engedmények létrehozásához tudnia kell. 

<a name="channel-specific-discounts"></a>Csatornaspecifikus engedmények
--------------------------

Kereskedők gyakran kínálnak különböző engedményeket számítani a különböző csatornákon. Ez a május megfelelhessen a helyi piacon vagy versengő kiskereskedők foglalkozni kell végrehajtani.

Kiskereskedelmi és kereskedelmi műveletek a Microsoft Dynamics 365 árcsoportok segítségével csatorna-specifikus engedmények megadása. Az árcsoportok a következő entitások egy vagy több lehetőségéhez rendelhetők hozzá: csatornák, katalógusok, fiókok és hűségprogramok. A cikk a csatornákat tárgyalja, de az azonos koncepciók a katalógus engedményekre, fiók engedményekre és a hűséges engedményekre vonatkoznak.

## <a name="price-groups"></a>Árcsoportok
\[felirat azonosítója = "melléklet\_256084" igazítás = "alignnone" szélesség "640" =\][![csoportok ár](./media/price-groups-1024x608.png)](./media/price-groups.png) csoport kapcsolatok kiskereskedelmi ár\[/felirat\]

A fenti ábra azt szemlélteti, entitás, amely lehet, hogy egy tranzakcióban (csatorna, katalógus, kapcsolat, vevői, hűségkártya) és a különböző engedménytípusokra vonatkozókat konfigurálható közötti kapcsolat. Minden tranzakció fordul elő egy csatorna, a csatorna garantáltan jelen a tranzakció. A fennmaradó entitások megadása nem kötelező. Minden egyes alapadat lapon van egy hivatkozás a kapcsolódó árcsoportok lapjához, ahol megtekintheti az árcsoportokat és szükség szerint hozzá is adhat árcsoportokat. Árcsoportot segítségével négy különböző típusú entitások engedményeket, a szervizdíj-helyesbítés és a kereskedelmi megállapodások vonatkoznak. Azt javasoljuk, hogy azt tervezi, hogyan fog nevet az árcsoportok rendszerezetten tárolhatja őket a stratégia. Betű vagy szám előtag vagy utótag használata, amelyekkel megkülönböztethetők egymástól a különféle több lehetőség lenne. Például 1-xxxxx csatorna árcsoportok és 2-xxxxx katalógus ár csoportok számára. Négy lekérdezési oldal van, amely valamennyi engedményekhez rendelt kiskereskedelmi entitásra fókuszál.

-   **Kiskereskedelmi csatorna árcsoportjai **– Ez a lap megjeleníti a minden egyes árcsoporthoz kapcsolódó engedmények és csatornák listáját.
-   **Katalógus árcsoportjai **– Ez a lap megjeleníti a minden egyes árcsoporthoz kapcsolódó engedmények és katalógusok listáját.
-   **Hűség árcsoportjai **– Ez a lap megjeleníti a minden egyes árcsoporthoz kapcsolódó engedmények és hűségprogramok listáját.
-   **Fiók árcsoportjai **– Ez a lap megjeleníti a minden egyes árcsoporthoz kapcsolódó engedmények és fiókok listáját.

## <a name="example-channel-discount-set-up"></a>Csatorna kedvezmény beállítás példája
A következő példa bemutatja egy csatorna engedmény beállításába bevont feladatokat.

1.  Ebben a példában egy úgynevezett **Houston**csatornával rendelkezik, és egy **Vissza az iskolába**nevezett új engedményt fog létrehozni.
2.  Mivel az árképzés és az engedmény stratégia csatorna engedmények lehetőségét tartalmazza, mindig létrehoz csatornaspecifikus árcsoportot egy csatorna létrehozásakor.
3.  **Houston-PG** árcsoporttal rendelkezik és ez hozzá van rendelve a **Houston** csatornához.
4.  Miután létrehozta az új **Vissza az iskolába** engedményt, akkor kattintson **Árcsoportok** az **Engedmény** lap tetején. Az **Árcsoportok engedménye engedmény** oldal jelenik meg. Ezután kattintson **Új** , és válassza ki a **Houston-PG** árcsoportot.
5.  Ezután engedélyezheti a kedvezményt és űthelyezheti a csatornába.

 

<a name="see-also"></a>Lásd még
--------

[Price adjustments and discounts](price-adjustments-discounts.md)



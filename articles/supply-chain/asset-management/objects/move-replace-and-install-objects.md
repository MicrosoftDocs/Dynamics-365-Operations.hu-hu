---
title: Eszközök áthelyezése, cseréje és telepítése
description: Ez a témakör ismerteti, hogyan lehet áthelyezni, lecserélni és telepíteni az eszközöket az Eszközkezelésben.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectReplace, EntAssetObjectInstallLookup, EntAssetObjectMove, EntAssetObjectTableEditSubObjects
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e1454f41bb0b43e22c5278463f63aa4178696eef
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872124"
---
# <a name="move-replace-and-install-assets"></a>Eszközök áthelyezése, cseréje és telepítése

[!include [banner](../../includes/banner.md)]

 

Ez a témakör ismerteti, hogyan lehet áthelyezni, lecserélni és telepíteni az eszközöket az Eszközkezelésben. Létrehozhat olyan egyedi eszközöket, amelyeknek nincs kapcsolata más eszközökkel, vagy létrehozhat egy olyan eszközstruktúrát, amely egy fölérendelt eszközt (legfelső szintű eszköz) és a kapcsolódó alárendelt eszközöket (aleszközök) tartalmaz. Az Eszközkezelésben három módszerrel mozgathatja az eszközt és módosíthatja a helyét:

- **Áthelyezés** – Az eszköz áthelyezése egy másik eszközszerkezetbe vagy ugyanazon eszközstruktúra más helyére.
- **Csere** – Ideiglenesen eltávolít egy eszközt az eszközstruktúrából javítási vagy felújítási céllal, majd visszahelyezi a javított eszközt később az eszközstruktúrába. Vagy véglegesen lecserélheti a használt eszközt egy új eszközre.
- **Telepítés** – Egy fölérendelt eszközt és bármely kapcsolódó alárendelt eszközt telepít egy munkavégzési helyszínre.

> [!NOTE]
> A mozgatott, áthelyezett vagy telepített eszköz kapcsolódhat másik munkavégzési helyszínhez is. Ebben az esetben előfordulhat, hogy az eszköz a munkavégzési helyszín pénzügyi dimenzióit használja. A **Munkavégzési helyszíntípusok** lapon állíthatja be a pénzügyi dimenziók kezelését a munkavégzési helyszíneken.

## <a name="move-asset"></a>Eszköz áthelyezése

Az **Eszköz áthelyezése** funkcióval egy másik eszközszerkezetbe vagy ugyanazon eszközstruktúra más helyére helyezheti át az eszközt. Az eszközt ki is veheti egy eszközszerkezetből úgy, hogy önálló eszközként álljon, amelynek nincsenek szerkezeti kapcsolatai.

> [!NOTE]
> Ne használja ezt a funkciót, ha az eszközöket javítja, vagy csak ideiglenesen lecseréli. Ehelyett használja a Jelen cikk **későbbi leírásában ismertetett Eszköz** cseréje funkciót.

1. Válassza ki az **Eszközkezelés** \> **Általános** \> **Eszközök** \> **Összes eszköz** vagy **Aktív eszközök** lehetőséget.
2. A listából válassza ki az áthelyezni kívánt eszközt. Ha az eszköz rendelkezik alárendelt eszközökkel, akkor ezeket az eszközöket is áthelyezi.
3. Válassza az **Eszköz áthelyezése** lehetőséget.
4. Ha úgy szeretné áthelyezni az eszközt, hogy az eszközstruktúra részévé váljon, válassza ki az új fölérendelt eszközt a **Fölérendelt eszköz** mezőben. Ha alárendelt eszközt helyez át, vagy különálló, szerkeszeti kapcsolatokkal nem rendelkező eszközzé szeretné alakítani, hagyja üresen a **fölérendelt eszköz** mezőt.
5. Alapértelmezett módon a **Hatályos** mező értéke az aktuális dátum és időpont lesz. Választhat azonban másik dátumot és időpontot is, amikortól az eszköz áthelyezése hatályos.
6. Válassza ki az **OK** lehetőséget.

## <a name="replace-asset"></a>Eszköz cseréje

Az **Eszköz cseréje** funkció használata az elhasználódott eszköz javítási, felújítási vagy tartós lecserélésére használható egy új eszköz által. Ennek a funkciónak a segítségével helyettesítheti az alárendelt eszközöket egy eszközstruktúrában. A fölérendelt eszközöknél (az olyan eszközöknél, amelyek aktuálisan nem rendelkeznek fölérendelt eszközzel), a cserét a munkavégzési helyszínen hajtják végre. A fölérendelt eszközök munkavégzési helyszínen való cseréjével kapcsolatos további információkért tekintse meg az [Eszközök telepítése munkavégzési helyszíneken](../functional-locations/install-objects-on-functional-locations.md) című részt.

> [!NOTE]
> Ha a termeléi osztályhoz javítóműhely is kapcsolódik, akkor létrehozhat olyan munkavégzési helyszíneket, mint **Javítás**, **Selejt** és **Tárolás**, amellyel az eszközök javítása és cseréje kezelhető.

1. Válassza ki az **Eszközkezelés** \> **Általános** \> **Eszközök** \> **Összes eszköz** vagy **Aktív eszközök** lehetőséget.
2. Válassza ki a listából a lecserélni kívánt alárendelt eszközt. Ha az eszköz rendelkezik alárendelt eszközökkel, akkor ezeket az eszközöket is lecseréli.
3. Válassza az **Eszköz cseréje** lehetőséget.

    A **Struktúraváltozás** mezőben látható a kiválasztott eszköz és a kapcsolódó alárendelt eszközök eszközszerkezetben történt legutóbbi mozgatásának dátuma és időpontja.

4. A **Kiválasztott eszköz** szakasz **Cél munkavégzési helyszín** mezőjében válassza ki azt a munkavégzési helyszínt, ahova mozgatni szeretné az eszközt. Válassza például a **Javítás** vagy a **Selejt** helyet.

    A **fölérendelt eszköz** szakasz **Hatályos** mezője azt az utolsó dátumot és időpontot mutatja, amikor a fölérendelt eszköz és a kapcsolódó alárendelt eszközök telepítése vagy áthelyezése az aktuális munkavégzési helyszínen megtörtént.

5. Az **Új eszköz** szakasz **Eszköz** mezőjében válassza ki azt az eszközt, amelyet a kijelölt eszköz ideiglenes vagy végleges helyettesítési eszközeként kíván beszúrni. Előfordulhat, hogy az eszköz jelenleg egy másik munkavégzési helyszínen található, például a **Tárolás** helyen.
7. A **Hatályosság kezdete** szakaszban a **Hatályos** mező értéke alapértelmezett módon az aktuális dátum és időpont lesz. Választhat azonban másik dátumot és időpontot is, amikortól az eszköz cseréje hatályos.
8. Válassza ki az **OK** lehetőséget.

## <a name="install-asset"></a>Eszköz telepítése

Az **Eszköz telepítése** funkcióval egy eszközstruktúrát telepíthet egy munkavégzési helyszínre.

> [!NOTE]
> Mindig jelöljön ki egy fölérendelt eszközt. A fölérendelt eszköz és a kapcsolódó alárendelt eszközök a kijelölt munkavégzési helyszínre kerülnek.

1. Válassza ki az **Eszközkezelés** \> **Általános** \> **Eszközök** \> **Összes eszköz** vagy **Aktív eszközök** lehetőséget.
2. A listában jelölje ki a fölérendelt eszközt, amelyet másik munkavégzési helyszínen szeretne telepíteni.
3. Válassza az **Eszköz telepítése** lehetőséget.

    Az **Attribútumok** szakasz mutatja a fölérendelt eszköznél beállított eszközattribútumokat.

4. A **Munkavégzési helyszín** mezőben válassza ki az új helyet.
5. Alapértelmezett módon a **Hatályos** mező értéke az aktuális dátum és időpont lesz. Választhat azonban másik dátumot és időpontot is, amikortól az eszközstruktúra telepítése hatályos.
6. Válassza ki az **OK** lehetőséget.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
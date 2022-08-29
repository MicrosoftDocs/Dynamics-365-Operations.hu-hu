---
title: A termelésben felhasznált anyagok alapértelmezett foglalási elvének felülbírálása
description: Ez a témakör bemutatja, hogyan lehet beállítani alapértelmezett foglalási elvet az egyes cikkmodell-csoportokhoz, hogy automatikusan eltérő foglalási elvek alkalmazhatók legyen minden olyan cikkre, amely része egy termelési anyagjegyzéknek vagy egy kötegrendelési receptúrának.
author: johanhoffmann
ms.date: 08/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-10
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 87f10efd7eebdc034af3f7c9081d2674a6190b38
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334595"
---
# <a name="override-the-default-reservation-principle-for-materials-in-production"></a>A termelésben felhasznált anyagok alapértelmezett foglalási elvének felülbírálása

[!include [banner](../includes/banner.md)]

Az *Alapértelmezett termelési foglalás felülbírálása* funkcióval minden cikkmodellcsoporthoz alapértelmezett foglalási elvet állíthat be. Ezért automatikusan különböző foglalási elvek alkalmazhatók minden olyan cikkre, amely része egy termelési anyagjegyzéknek (BOM) vagy kötegrendelési receptúrának. Beállíthatja, hogy az egyes cikkmodellcsoportok felülbírálják-e a rendelésre beállított alapértelmezett foglalási elvet, és hogy melyik foglalási elvet használja helyette (*manuális*, *becslés*, *ütemezés*, *kiadás* vagy *indítás*).

Új termelési rendelés vagy kötegrendelés létrehozásakor a program kéri, hogy válassza ki azt a foglalási elvet, amelyet a rendelésre, illetve annak minden anyagjegyzéksorára vagy receptúrasorára alkalmazni kell. Ha az *Alapértelmezett termelési foglalás felülbírálása* funkciót használja, akkor az anyagjegyzék- vagy receptúrasorok egy része vagy egésze felülbírálhatja ezt a foglalási elvet, és ehelyett a megfelelő cikkmodellcsoporthoz beállított foglalási elvet használhatja.

Ha például nyersanyagokat vagy összetevőket használ, amelyekhez kitárolási munka szükséges, az ilyen termékekhez létrehozott anyagjegyzék- vagy receptúrasorok esetében fizikai foglalásra van szükség, mivel a raktári munka generálásának a fizikai foglalás az előfeltétele. Ha azt szeretné, hogy a foglalás automatikus legyen, a következő foglalási elvek közül választhat: *becslés*, *ütemezés*, *kiadás* vagy *indítás*. Ha azonban olyan anyagok vagy összetevők vannak, amelyekhez nem szükséges kitárolási munka, mivel közvetlenül egy helyről használják fel őket, akkor általában a *kézi* foglalási elvet kell választani, amely nem hoz létre fizikai foglalást és nem generál kitárolási munkát.

## <a name="turn-the-override-default-production-reservation-feature-on-or-off"></a>Az Alapértelmezett termelési foglalás felülbírálása funkció be- és kikapcsolása

A funkció használatához be kell kapcsolva lennie a rendszeren. Az Ellátásilánc-kezelés 10.0.25-ös verziója szerint a funkció alapértelmezés szerint be van kapcsolva. Az Ellátásilánc-kezelés 10.0.29-es verziója szerint a funkció kötelező, és nem lehet kikapcsolni. Ha 10.0.29-esnél régebbi verziót futtat, *·*[akkor](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) a rendszergazdák be- vagy kikapcsolhatják ezt a funkciót, ha a Szolgáltatáskezelés munkaterület Alapértelmezett termelési foglalás felülbírálása szolgáltatását keresi.

## <a name="assign-a-production-reservation-policy-to-an-item-model-group"></a>Termelésfoglalási irányelv hozzárendelése cikkmodellcsoporthoz

1. Lépjen ide: **Költséggazdálkodás \> Készletkönyvelési irányelvek beállítása \> Cikkmodellcsoportok**.
1. Válasszon ki vagy hozzon létre egy cikkmodellcsoportot.
1. A **Készletszabályok** gyorslapon jelölje be a **Cikk termelési foglalásának felülbírálása** jelölőnégyzetet.
1. A **Foglalás** mezőben válassza ki a kiválasztott modellcsoportba tartozó cikkek foglalási elvét. (Ezek a cikkek anyagjegyzéken vagy receptúrasoron lévő cikkeket tartalmaznak.)

    - **Kézi** – a modellcsoportban található cikkeket a rendszer nem foglalja le automatikusan a termeléshez. Azonban szükség esetén manuálisan is lefoglalhatók.
    - **Becslés** – a modellcsoportban lévő cikkeket a rendszer ténylegesen lefoglalja a termelési rendelés becslése során.
    - **Ütemezés** – a modellcsoportban lévő cikkeket a rendszer ténylegesen lefoglalja a termelési rendelés ütemezése során.
    - **Kiadás** – a modellcsoportban lévő cikkeket a rendszer ténylegesen lefoglalja a termelési rendelés kiadásakor.
    - **Indítás** – a modellcsoportban lévő cikkeket a rendszer ténylegesen lefoglalja a termelési rendelés indításakor.

## <a name="example-using-reservation-principles-in-a-bulkpack-scenario"></a>Példa: foglalási elvek használata ömlesztett/csomagolási helyzetben

Egy ömlesztett kenőanyag 1000 literes keverőben készül. Miután az ömlesztett anyag elkészült, több töltőállomáshoz kerül, ahol különböző méretű üvegeket töltenek meg vele. A töltés befejezése után az üvegeket dobozokba csomagolják. A dobozokat ezután raklapokra csomagolják.

Ebben az esetben kötegrendelés jön létre 1000 liter ömlesztett anyagra. (Ez a rendelés az ömlesztett rendelés.) Amikor a kötegrendelés elkészült, a rendszer készként jelenti a töltőállomások anyagbetöltési helyére. Ezt követően létrejön egy kötegrendelés az egyes üvegméretek megtöltésére és becsomagolására. (Ezek a rendelések csomagrendelések.) A csomagrendelések olyan képletet tartalmaznak, amely az ömlesztett anyagból, üres üvegből, címkéből és más csomagolóanyagokból áll. Mivel az ömlesztett anyag közvetlenül a keverőtől a töltőállomásokig folyik, nem szükséges raktári munka az összetevő kitárolásához, és az ömlesztett anyag felhasználása közvetlenül a bemeneti helyről történik. A foglalási elv ennek megfelelően *manuális* értékre van állítva. A többi anyag kitárolási munkával kerül a töltőállomásra. Emiatt ezeknek a soroknak a foglalási elve például *kiadás* értékre van beállítva, hogy a foglalás automatikusan megtörténjen a csomagrendelés kiadásakor.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
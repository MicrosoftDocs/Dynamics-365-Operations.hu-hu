---
title: Kísérlet csatlakoztatása és változatok szerkesztése
description: Ez a témakör azt mutatja be, hogyan lehet egy külső szolgáltatásból származó kísérletet csatlakoztatni a Dynamics 365 Commerce rendszerhez, illetve hogyan lehet szerkeszteni a kísérlet változatait.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 2a33897d01dd98d446c2fb49e417abd9db9f403a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010024"
---
# <a name="connect-an-experiment-and-edit-variations"></a>Kísérlet csatlakoztatása és változatok szerkesztése

Ez a témakör azt mutatja be, kísérletét hogyan csatlakoztathatja a Commerce modulban, illetve hogyan módosíthatja az egyes változatokat úgy, hogy azok egybevágjanak a hipotézisével. 

A következő ábra azokat a lépéseket mutatja be, amelyekkel egy e-kereskedelmi webhelyhez tartozó kísérletet lehet létrehozni és futtatni a Dynamics 365 Commerce rendszerben. A további lépések külön témákban szerepelnek.

[![Kísérletezés felhasználói interakciósorozata – Csatlakoztatás és szerkesztés](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)

Miután a [kísérletet beállította](experimentation-setup.md) egy harmadik fél szolgáltatásban, csatlakoztathatja a kísérletet a Dynamics 365 Commerce rendszerben, és szerkesztheti a kísérlet változatait.

## <a name="planning-considerations"></a>Tervezési szempontok

Mielőtt a kísérletet a Commerce modulban csatlakoztatja, el kell döntenie, hogy milyen módon kezelje a Commerce a tartalmat.

### <a name="determine-the-scope-of-your-experiment"></a>A kísérlet hatókörének meghatározása
Amikor egy kísérletet csatlakoztat, a program felkéri arra, hogy határozza meg a kísérlet hatókörét. A kísérletek rendelkezhetnek **részleges** vagy **teljes** hatókörrel.
- A **részleges** lehetőséget akkor válassza, ha a kísérletet egy oldal meghatározott részén kívánja végrehajtani. Ha ezt a lehetőséget választja, akkor meg kell adnia, hogy mely modulok szerepeljenek a kísérletben. Az alapértelmezett oldal vagy töredék azon részein végrehajtott változtatások, amelyek nem kapcsolódnak a kísérlethez, automatikusan szinkronizáltak lesznek a változatok között.
- A **teljes** lehetőséget akkor válassza, ha egy teljes oldalon vagy töredéken szeretne kísérletet végezni. Az alapértelmezett oldal vagy töredék külön példányai jönnek létre. Azt nem kell kiválasztania, hogy mely modulok kerüljenek a kísérletbe, mivel a szerkesztési felület egésze módosítható. Szükség szerint modulokat adhat hozzá, törölhet vagy rendelhet újra. Ha azonban a kísérlethez társított alapértelmezett oldalon vagy töredékben módosítások történnek, akkor ezeket a módosításokat manuálisan kell szinkronizálni a változatok között.

<!-- not to editors, we're adding an image here to illustrate the difference. it will help.) -->

> [!NOTE]
> Ha egy elrendezést használó oldalhoz társítja a kísérletet, akkor a kísérlet hatóköre csak **egészre** állítható.

### <a name="decide-if-you-want-to-schedule-when-your-experiment-is-published"></a>Döntse el, hogy a kísérlet közzétételét be kívánja-e ütemezni
Ha szeretné beütemezni, hogy kísérlete mikor kerüljön ki az élő webhelyre, akkor ellenőrizze, hogy a kísérlethez társítani kívánt tartalom elérhető-e egy közzétételi csoportban, még *mielőtt* csatlakoztatná a kísérletet. 

A közzétételi csoportokkal kapcsolatos további tudnivalókat lásd: [Munka a közzétételi csoportokkal](publish-groups.md).


## <a name="connect-your-experiment"></a>A kísérlet csatlakoztatása
A kísérlet csatlakoztatásához a **Kísérlet csatlakoztatása** varázslót indítsa el. A varázsló végigvezeti a kísérlet csatlakoztatásához szükséges lépéseken. Amikor a varázsló végére ér, a kísérlet csatlakoztatottá válik, és a változatok jönnek létre, amelyek készen állnak a szerkesztésre.

A Commerce webhelykészítőben a kísérlethez történő csatlakozás elkezdéséhez hajtsa végre az alábbi lépéseket.

1. A **Kísérlet csatlakoztatása** varázsló indításához válassza a bal oldali navigációs panel **Kísérletek** elemét, majd a **Csatlakozás** lehetőséget. Azt is megteheti, hogy a varázslót az oldal vagy a töredék szerkesztőjéből nyitja meg úgy, hogy szerkeszti, és kiválasztja a **Kísérlet csatlakoztatása** elemet a parancssorból.

    > [!NOTE]
    > Egy oldal egyszerre csak egy kísérlethez kapcsolható. Ha egy másik kísérlethez szeretne egy oldalt csatlakoztatni, először törölje azt a kísérletet, amelyhez az oldal aktuálisan kapcsolódik.

1. Válassza ki azt az oldalt vagy töredéket, amelyen futtatni szeretné a kísérletet.
1. A kísérletezési hatókört **részlegesre** vagy **egészre** kell állítani a fenti [Kísérlet hatókörének meghatározása](#determine-the-scope-of-your-experiment) szakaszban kiválasztott beállítástól függően.
    > [!NOTE]
    > Ha teljes oldalon vagy töredéken szeretne kísérletezni, akkor engedélyezni kell a **Kísérlet oldalakon vagy töredékeken** zászlót. További tudnivalókért lásd a [Kísérletezés a Dynamics 365 Commerce rendszerben](experimentation-overview.md) témakört.
    
1. A varázsló utolsó lépésében válassza ki a **Változatok létrehozása és kilépés a varázslóból**. A kísérlethez változatok jönnek létre. 

## <a name="edit-your-variations"></a>A változatok szerkesztése
A varázslóból való kilépéskor a változatok jönnek létre. 

Ezt követően úgy szerkesztheti a változatokat, hogy azok tükrözzék azokat a választásokat, amelyeket igazolni szeretne a kísérlet hipotézisében. Válassza ki a következő eljárások közül azt, amelyik megfelel a kísérlethez a fenti [Kísérlet hatókörének meghatározása](#determine-the-scope-of-your-experiment) szakaszban választott hatókörnek.

### <a name="edit-variations-for-experiments-with-partial-scope"></a>Részleges hatókörű kísérletek változatainak szerkesztése
Ha a **Kísérlet csatlakoztatása** varázslóban a kísérlet hatókörét **részlegesre** állította, akkor a következő lépéseket hajtsa végre.

1. A szerkesztő nézetben a parancssor alatt található változatok legördülő menü segítségével szerkessze az egyes változatokat az eredeti hipotézisének megfelelően. Egy ellenőrző- vagy alapváltozatot is létre lehet hozni úgy, hogy a változatok valamelyikét változatlanul hagyja.
1. Válassza ki azt a modult, amelyen a kísérletet el szeretné végezni, aztán a kipontozást (...) és a **Kísérlet hozzáadása** elemet válassza ki.

### <a name="edit-variations-for-experiments-with-entire-scope"></a>Teljes hatókörű kísérletek változatainak szerkesztése
Ha a kísérlethez **teljes** hatókört állított be a **Kísérlet csatlakoztatása** varázslóban, akkor szerkesztő nézetben a parancssor alatti változatok legördülő menü segítségével szerkessze az egyes változatokat az eredeti hipotézisének megfelelően. 

> [!NOTE]
> Mindkét esetben létrehozhat egy ellenőrző- vagy alapváltozatot úgy, hogy a változatok valamelyikét változatlanul hagyja.

## <a name="previous-step"></a>Előző lépés
[Kísérlet beállítása](experimentation-setup.md) 


## <a name="next-step"></a>Következő lépés
[Kísérlet előnézetének megtekintése és közzététele](experimentation-preview-publish.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
---
title: Eszközkritikusságok típusai
description: Ez a témakör bemutatja az eszközkritikussági típusokat az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetCriticality, EntAssetObjectCriticality
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4b7d6e3dea1b3c1ef47490df678f639c036cdd5c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429428"
---
# <a name="asset-criticality-types"></a>Eszközkritikusságok típusai

[!include [banner](../../includes/banner.md)]

 

Ez a témakör bemutatja az eszközkritikussági típusokat az Eszközkezelés modulban. Az eszközkritikusság kapcsolódik az eszközökhöz, és átkerül a munkarendelésekre. A munkarendeléseken nem módosítható. Az eszközkritikusság segítségével kiszámíthatja a munkarendelés kritikusságát a munkarendelés ütemezése során. Más szavakkal élve, annak kiszámítására használják, hogy egy eszköz karbantartási feladata milyen mértékben befolyásolja a vállalat termelési ütemezését és termelékenységét. A munkarendelés ütemezéséhez szükséges értékelési pontszámok kiszámításával kapcsolatos beállításra vonatkozó további információkat az [Eszközkezelés paraméterei](../setup-for-objects/enterprise-asset-management-parameters.md) részben találhat.

A kritikusság beállításához először létre kell hozni a kritikusságtípusokat, amelyeket az eszköz beállítása során kell használni. Ezután beállíthat eszközkritikusságokat.

## <a name="set-up-criticality-types"></a>Kritikusságtípusok beállítása

1. Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Eszközök** \> **Kritikusságtípusok** elemet.
2. Válassza az **Új** lehetőséget egy rekord létrehozásához.
3. A **Kritikusság** mezőben adjon meg egy számot, amely a kritikusságot jelzi.
4. A **Név** mezőbe írja be a kritikussátípus nevét.
5. A **Szorzó** mezőben adjon meg egy szorzót. A rendszer ezt a szorzót használja a munkarendelés-ütemezés számítása során, amellyel megállapítja a használandó kritikusságrekordot. (A rendszer mindig a legmagasabb szorzójú rekordot használja.) Ez a beállítás akkor releváns, ha – ahogy a következő ábrán látható – olyan kritikussági sorokat hoznak létre, amelyek kritikussági értéke megegyezik.

    ![Kritikussági típusok oldal](media/23-setup-for-objects.png)

## <a name="set-up-asset-criticalities"></a>Eszközkritikusságok beállítása

1. Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Eszközkritikusságok** elemet.
2. Válassza az **Új** lehetőséget egy rekord létrehozásához.
3. Az eszközkritikusság részletességének szükséges szintjétől függően végezze el a releváns kiválasztásokat a **Munkavégzési helyszín**, **Eszköztípus**, **Gyártó**, **Modell**, **Eszköz**, **Feladattípus-kategória**, **Feladattípus**, **Feladattípus változata** és **Feladat követelménye** mezőkben.

    > [!NOTE]
    > Ha kiválasztotta az eszközkritikusságot, az Eszközkezelés végigmegy az összes eszközkritikussági rekordon lehetséges egyezést keresve. Mindig a leginkább meghatározott kombinációt ellenőrzi először. Más szavakkal az Eszközkezelés először a **Feladat követelménye** értékét ellenőrzi. Ha nem talál egyezést, ellenőrzi a **Munkatípus-változat** értékét. Ha nem talál egyezést, ellenőrzi a **Munkatípus** értékét, és így tovább. Ahogy az az oldal elrendezésében is látható, ez a viselkedésmód azt jelenti, hogy a legspecifikusabb kombináció megkereséséhez az Eszközkezelés minden egyes rekordot jobbról balra ellenőriz egyezést keresve. Ha nem talál egyezést, akkor a rendszer azt az „alapértelmezett” rekordot használja, amelynél nincsenek kiválasztások.

4. A **Kritikusság** mezőben válasszon egyet az előző eljárás során létrehozott kritikussági értékek közül.

### <a name="notes-about-criticality-setup"></a>Megjegyzések a kritikusság beállításáról

- Ha a beállítás során módosítja az eszköz kritikusságát, miután már használta egy munkarendelésen, a munkarendelés kritikussága nem frissül ennek megfelelően.
- A program minden alkalommal újraszámolja a munkarendelésen szereplő kritikusságot, amikor a munkarendeléshez hozzáadnak vagy róla eltávolítanak egy munkarendelési sort.
- Ha a munkarendelés számos munkarendelési feladatot tartalmaz, akkor a rendszer mindig a **Kritikusságtípus** oldal **Szorzó** mezője szerinti legmagasabb kritikusságút használja a munkarendelésen.
- Általában az eszközök kritikussága idővel változhat. A kritikusságot új berendezések vásárlása, felújítások stb. befolyásolhatják. Javasoljuk az eszközkritikusságok rendszeres időközönkénti felülvizsgálatát (például évente egyszer vagy kétévente), hogy biztosítsa, hogy a kritikussági meghatározások megfelelnek az aktuális termelési beállításoknak.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
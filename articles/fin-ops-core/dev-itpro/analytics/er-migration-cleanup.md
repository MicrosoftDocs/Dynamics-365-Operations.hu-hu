---
title: ER-áttelepítéshez tartozó adattisztítás
description: Ez a cikk bemutatja, hogy hogyan lehet az ER áttelepítési tisztítási funkcióval megoldani az ER-sablonokkal kapcsolatos problémákat.
author: kfend
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: AX 8.0.0
ms.custom: ''
ms.assetid: ''
ms.search.form: ERSolutionTable, ERWorkspace, ERParameters, ERMigrationCleanup
ms.openlocfilehash: bf32981ed5f43647038018bf2cd98e55ce233b3f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285091"
---
# <a name="er-migration-cleanup"></a>ER-áttelepítéshez tartozó adattisztítás 

[!include[banner](../includes/banner.md)]

A Finance példányok kezelésekor úgy is dönthet, hogy áttelepíti az aktuális példányát egy másik helyre. Előfordulhat például, hogy egy új tesztkörnyezetbe szeretné áttelepíteni a termelési példányt. Ha úgy állította be az Elektronikus jelentéskészítés (ER) keretrendszert, hogy a Microsoft Azure Blob-tárolóban tárolja a sablonokat, akkor az új tesztkörnyezet **DocuValue** táblája a Blob tárhely példányára hivatkozik atermelési környezetben. Ez a példány azonban nem érhető el a tesztkörnyezetből, mivel az áttelepítési folyamat nem támogatja a Blob-tárolóban található összetevők áttelepítését. Ehelyett, a várakozás az, hogy a tesztkörnyezetben, a Blob-tároló olyan példányára hivatkozik, amely még nem, tartalmazza az ER-sablonokat.

Ha tehát olyan ER formátumot próbál futtatni, amely sablon alapján üzleti dokumentumokat hoz létre, akkor kivétel történik, és a program értesíti a hiányzó sablonról. A program arra kéri, hogy használja az ER-áttelepítéshez tartozó adattisztítás lehetőséget, majd importálja újra az ER formátumkonfigurációt, amely a sablont tartalmazza.

[![ER-formátum futtatása.](./media/er-migration-cleanup-run.png)](./media/er-migration-cleanup-run.png)

Hasonló hibaüzenet jelenik meg, ha a **Konfigurációk** lapra navigál (**Szervezeti adminisztráció** \> **Elektronikus jelentéskészítési** \> **Konfigurációk**) és a konfigurációk fában egy sablont használó ER-formátumkonfigurációt próbál törölni.

[![ER-formátum törlése.](./media/er-migration-cleanup-delete.png)](./media/er-migration-cleanup-delete.png)

Hajtsa végre a következő lépéseket a nem elérhető ER-sablonokkal kapcsolatos problémák megoldásához.

1.  Nyissa meg a **Szervezeti adminisztráció** \> **Időszakos** \> **Áttelepítéshez tartozó adattisztítás** oldalt.
2.  Válassza ki azt az ER-formátumkonfigurációt, amely nem hajtható végre vagy nem törölhető.
3.  Válassza a **Törlés** lehetőséget.
4.  A kijelölt ER formátumkonfiguráció törlésének jóváhagyása.
5.  [Importálja](download-electronic-reporting-configuration-lcs.md) a törölt ER-formátumkonfigurációt az aktuális Finance példányba.

## <a name="applicability"></a>Alkalmazhatóság

> [Fontos] Az **Áttelepítéshez tartozó adattisztítás** beállítás csak a nem hozzáférhető, nem elérhető ER-sablonokat tartalmazó formátum-konfigurációkat célozza. Ha az **Áttelepítéshez tartozó adattisztítás** lehetőséggel törli az ER-formátumkonfigurációt, akkor az ER törli azokat a sablonokat, amelyek kapcsolódnak a konfigurációs műtermékhez az egyetlen alkalmazás adatbázisában. A blob-tárolóban található megfelelő fizikai fájlok létezését a program nem ellenőrzi. Ehelyett, azt feltételezi, hogy nincsenek ilyenek. Ezért ne használja az **Áttelepítéshez tartozó adattisztítás** lehetőséget a **Konfigurációk** lapon található ER konfiguráció törlése funkció helyett. Csak akkor használja az **Áttelepítéshez tartozó adattisztítás** lehetőséget ha **Konfigurációk** lapon található ER konfiguráció törlése funkció nem járt sikerrel.
>
> Ha az **Áttelepítéshez tartozó adattisztítás** lehetőséggel töröl egy ER-formátumkonfigurációt, ha a hivatkozott sablon rendelkezésre álla a Blob-tárolóban, akkor a kapcsolódó konfigurációs műtermékeket csak az alkalmazás adatbázisában törli. A blob-tárolóban található sablon fizikai fájlja megmarad. A Blob-tárolóban lévő fájlok felülírása már nem engedélyezett. További tájékoztatás: [KB4557217](https://fix.lcs.dynamics.com/Issue/Details?kb=4557217). Ezenkívül már nem fogja tudni újra importálni a konfigurációkat, amelyeket az Áttelepítéshez tartozó adattisztítás funkcióval törölt ebben a környezetben. A probléma megoldásához meg kell keresnie a megfelelő fájlt a Blob-tárolóban, és manuálisan törölnie kell azt.

[![ER-formátum importálása.](./media/er-migration-cleanup-import.png)](./media/er-migration-cleanup-import.png)

Egy hasonló hiba merülhet felé, ha az alkalmazás példányát egy másik helyre telepíti át, amelyet már többször áttelepítési célhelyként alkalmaztak, és amelyhez a Blob-tárhely már tartalmaz ER-sablonfájlokat.

Mivel előfordulhat, hogy a több ER formátumkonfigurációja is van, ez a folyamat időigényes lehet. Ennek megfelelően javasoljuk, hogy hibás hivatkozásokkal rendelkező sablonok automatikus helyreállításához használja az [ER-sablonok biztonságimentés-tárhelye](er-backup-storage-templates.md) funkciót.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

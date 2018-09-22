---
title: "Projekt költségkategóriák szinkronizálása a Finance and Operations és a Project Service Automation között"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a projekt költségkategóriáinak Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Project Service Automation közötti szinkronizálásra használhatók."
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: c4d09fde2cf4335553243c136590f9f3135db97a
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---

# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a>Projekt költségkategóriák szinkronizálása a Finance and Operations és a Project Service Automation között

[!include[banner](../includes/banner.md)]

Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a projekt költségkategóriáinak Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Project Service Automation közötti szinkronizálásra használhatók.

> [!NOTE]
> - Projektfeladat integrációja, költségtranzakció-kategóriák, munkaóra-becslés, költségbecslések és a funkciók zárolása a Microsoft Dynamics 365 for Finance and Operations 8.0-ás verziójában érhetők el.
> - A tényleges adatok integrációja a Microsoft Dynamics 365 for Finance and Operations 8.01-es vagy újabb verziójában érhető el.
> - Amennyiben a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0-ás verziót használja, a KB 4132657 és KB 4132660 telepítését követően, használhat sablonokat projektfeladatok, kiadási tranzakciókategóriák, becsült órák, becsült kiadások és a tényleges értékek integrálásához, és a funkciók zárolásának beállításához. Ha a könyvelési felosztásokat kell visszaállítania, ajánlott a KB 4131710 telepítése is.

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a>Adatáramlás a Project Service Automation és a Finance and Operations esetében

A Project Service Automation és a Finance and Operations közötti integrációs megoldás az adatintegrációs funkciót használja a Project Service Automation és Finance and Operations példányok közötti szinkronizáláshoz. Az integrációs sablonok, amelyek elérhetőek az adatintegrációs funkcióval lehetővé teszik a projektköltségtranzakció-kategóriákkal kapcsolatos adatáramlást a Project Service Automation és Finance and Operations alkalmazások között.

Ha a projektköltség-kategóriák a Finance and Operations alkalmazásban vannak kezelve, az integrációs folyamat először a Finance and Operations és a Project Service Automation között történik. A projektköltség integrációs azonosítói ezt követően frissítve lesznek a Project Service Automation és a Finance and Operations közötti szinkronizálással.

Ha a projektköltség-kategóriák a Project Service Automation alkalmazásban vannak kezelve, az integrációs folyamat először a Project Service Automation és a Finance and Operations között történik. A projektkategóriákat már azelőtt konfigurálni kell a Finance and Operations alkalmazásban, mielőtt szinkronizálná a Project Service Automation alkalmazásba. Majd szinkronizálja vissza a Finance and Operations alkalmazásból a Project Service Automation alkalmazásba, majd ismét a Project Service Automation alkalmazásból a Finance and Operations alkalmazásba. Ezzel a módszerrel segíthet garantálni, hogy a kategóriák kapcsolva legyenek és ne legyenek ismétlődő elemek létrehozva.

> [!NOTE]
> Általában a projektköltség-kategóriák a Finance and Operations alkalmazásban vannak kezelve. Azonban, ha azok nem a Finance and Operations alkalmazásban vannak kezelve, vagy a költségkategóriák már létre lettek hozva a Project Service Automation alkalmazásban, először szinkronizálni kell a Projektkiadás-tranzakció kategóriák sablon használatával (Fin és Ops PSA). Majd szinkronizálja a Projektköltség-tranzakció kategóriák (Fin and Ops to PSA) sablonnal Még egyszer futtatnia kell a szinkronizálást a Project Service Automation és a Finance and Operations között.
>
> Ha először a Project Service Automation alkalmazásból szinkronizál, az alábbi követelményeknek teljesülnie kell a Finance and Operations alkalmazásban a szinkronizálás futtatása előtt:
>
> - A megosztott kategória, amely megfelel a projektkategóriának, amely be van állítva a Project Service Automation alkalmazásban léteznie kell, és is engedélyezni kell a **Projekthez** és **Költséghez** is.
> - Az egyes Finance and Operations jogi személyekhez, amelyeket integrálni kell, a következő projektkategóriáknak léteznie kell:
>
>     - **Projektkategória** létezik. 
>     - **Használat a költségmodulban** engedélyezve van.
>     - **Aktív a naplóban** engedélyezve van.
>     - A **Tranzakciótípus** beállítása **Kiadás**.

A következő ábra bemutatja a Project Service Automation és a Finance and Operations közötti adatszinkronizálást.

[![Adatáramlás a Project Service Automation és a Finance and Operations integrációjához](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)

## <a name="project-expense-category-synchronization-from-finance-and-operations-to-project-service-automation"></a>Projekt költségkategóriák szinkronizálása a Finance and Operations alkalmazásból a Project Service Automation alkalmazásba

### <a name="template-and-task"></a>Sablon és feladat

A rendelkezésre álló sablon eléréséhez a Microsoft PowerApps admin centerben válassza a **Projektek** lehetőséget, majd kattintson a jobb felső sarkában **Új projekt** lehetőségre a nyilvános sablonok kiválasztásához.

A következő sablon és alapul szolgáló feladat használható az aktuális projektköltség-kategóriák szinkronizálásához a Finance and Operations között és a Project Service Automation között:

- **Sablon neve az adatintegrációban:** Projektköltség-tranzakció kategóriák (Fin and Ops to PSA)
- **A feladat neve a projektben** Sync categories to PSA (Kategóriák szinkronizálása PSA-ba)

### <a name="entity-set"></a>Entitás beállítása

| Finance and Operations            | Projekt szolgáltatásautomatizálása |
|-----------------------------------|----------------------------|
| Integrációs entitás a kategóriákhoz | Tranzakciókategóriák.     |

### <a name="entity-flow"></a>Entitás folyamata

Projektköltség-kategóriák kezelése a Finance and Operations alkalmazásban történik, majd ezek szinkronizálva lesznek a Project Service Automation alkalmazásba tranzakciókategóriaként.

### <a name="power-query"></a>Power Query

Microsoft Power Queryt for Excelt kell használnia a számlázási típus beállításához a tranzakciókategórián, amikor a Project Service Automation alkalmazásba szinkronizál. A Projektkiadás-tranzakció kategóriák (Fin and Ops to PSA) sablonban található egy alapértelmezett oszlop, és a hozzárendelés már rendelkezésre áll. Ha saját sablont hoz létre, hozzá kell adnia egy feltételes oszlopot a Power Query-ben. Kövesse ezeket a lépéseket.

1. Kattintson a nyílra a projekt költség-kategóriák hozzárendelésének megnyitásához a Projektköltség-tranzakció kategóriák t (Fin és a PSA Ops) sablonban.
2. Kattintson a **Speciális lekérdezés és szűrés** hivatkozásra a Power Query megnyitásához.
2. Válassza a **Feltételes oszlop hozzáadása** lehetőséget.
3. Adjon meg egy nevet az új oszlopnak, például **BillingType**.
4. Adja meg a következő feltételt: **if CATEGORYID not equal to null then 19235001, Otherwise null**.
5. Kattintson a **OK** elemre az oszlopon.
6. Ügyeljen arra, hogy ez az új oszlop hozzá legyen rendelve a hozzárendelés oldalon.

Az alábbi ábrán egy példát mutat a sablonfeladat hozzárendelésére az Adatintegrációban A leképezés mutatja, hogy melyik mezőadatok szinkronizálódnak a Finance and Operations – Project Service Automation irányban.

[![Sablon-hozzárendelés](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)

## <a name="project-expense-category-synchronization-from-project-service-automation-to-finance-and-operations"></a>Projekt költségkategóriák szinkronizálása a Project Service Automation alkalmazásból a Finance and Operations alkalmazásba

### <a name="template-and-task"></a>Sablon és feladat

A következő sablon és alapul szolgáló feladat használható az aktuális projektköltség-kategóriák szinkronizálásához a Project Service Automation és a Finance and Operations között:

- **Sablon neve az adatintegrációban:** Projektköltség-tranzakció kategóriák (PSA to Fin and Ops)
- **A feladat neve a projektben** Sync categories to Fin Ops (Kategóriák szinkronizálása Fin Ops-ba)

### <a name="entity-set"></a>Entitás beállítása

| Projekt szolgáltatásautomatizálása | Finance and Operations            |
|----------------------------|-----------------------------------|
| Tranzakciókategóriák.     | Integrációs entitás a kategóriákhoz |

### <a name="entity-flow"></a>Entitás folyamata

Projektköltség-kategóriák kezelése a Finance and Operations alkalmazásban történik, majd ezek szinkronizálva lesznek a Project Service Automation alkalmazásba tranzakciókategóriaként. A visszaszinkronizálás Finance and Operations alkalmazásba frissíti a projektkategóriát a Finance and Operations alkalmazásban a Project Service Automation alkalmazás integrációs azonosítójával.

### <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrán egy példát mutat a sablonfeladat hozzárendelésére az Adatintegrációban

> [!NOTE]
> A leképezés mutatja, hogy melyik mezőadatok szinkronizálódnak a Project Service Automation – Finance and Operations irányban.

[![Sablon-hozzárendelés](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)

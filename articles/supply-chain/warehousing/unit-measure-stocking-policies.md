---
title: "Mértékegység és rakodási irányelvek"
description: "Ez a cikk leírja, hogy az alapértelmezett egységek, egységsorozatok és egységátváltások hogyan vannak felhasználva a raktári folyamatokban."
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetails, EcoResProductDetailsExtended, EcoResStorageDimensionGroup, InventItemOrderSetup, UnitOfMeasureConversion, WHSRFMenuItem, WHSUOMSeqGroupTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 29611
ms.assetid: 4b5ca875-9a06-416d-9ac0-cc3ab8f7338e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: e0a22e07f5a0e5bc30c8ad9dc87c5a506d62847d
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="unit-of-measure-and-stocking-policies"></a>Mértékegység és rakodási irányelvek

[!INCLUDE [banner](../includes/banner.md)]

Ez a cikk leírja, hogy az alapértelmezett egységek, egységsorozatok és egységátváltások hogyan vannak felhasználva a raktári folyamatokban.

Az egységszekvencia-csoportok a raktári műveletek során használható egységek sorrendjét határozzák meg. Az **Egységszekvencia-csoportok** oldalon hozhatók létre. A szekvencia megmutatja a különböző egységek közötti kapcsolatot. Például raklapokat tárol, amelyek egyes cikkeket tartalmazó dobozokat foglalnak magukba. Ebben az esetben meg kell adnia a három különböző egységet és a rétegek logikai sorrendjét. Egységszekvencia-csoportok segítségével határozhatja meg az azonosítótáblák csoportosítását meghatározó szabályokat, és az alapértelmezett egységet, amelyeket a különböző raktári folyamatokhoz kell használni. Ez a cikk vonatkozik a speciális raktározási megoldásra, amely a Raktárkezelés résznél érhető el, illetve a Készletkezelés modulban rendelkezésre álló alapvetőbb raktározási megoldásra.

## <a name="unit-sequence-groups-for-released-products"></a>Egységszekvencia-csoportok kiadott termékekhez
Ha kiadott termékeket kíván használni raktár-munkafolyamatokon belül, egy egységszekvenciacsoporthoz kell rendelni őket. Ha egy Tárolási dimenziócsoportottal társított terméket érvényesít és a **Raktárkezelési folyamatok használata** lehetőséget a Tárolásidimenzió-csoport értéke az **Igen** lehetőségre van állítva, hibaüzenetet kap, ha egy egységszekvencia-csoport azonosítójához nincs termék definiálva. Ha a használt egységszekvencia-csoport több sort tartalmaz (és ennélfogva több egységet tartalmaz), be kell állítania a mértékegység-átváltást az egységek között. Ezt a beállítást a hajtsa végre az **Egységátváltások** oldalon. Egy cikkhez rendelt egységszekvencia-csoport legkisebb egysége meg kell hogy egyezzen a kapcsolódó kiadott termékhez hozzárendelt készletegységgel. A készletegység az az egység, amely az aktuális készlet számításainak alapjául szolgál. Használatával mértékegység-átváltásokat állíthat be alaptermékek termékváltozataihoz a **Mértékegység-átváltások engedélyezése** lehetőségnél.

## <a name="license-plate-grouping"></a>Azonosítótábla-csoportosítás
Meghatározhatja, hogy az egy adott egységnél kisebb vagy nagyobb mennyiségű beérkező tételeket a rendszer összecsoportosítsa egy azonosítótábla alá, vagy minden egységhez külön azonosítótáblát rendeljen. Ennek a viselkedésnek a beállításához használja az **Azonosítótábla-csoportosítás** beállítást a **Sor adatai** lapon, amely az **Egységszekvencia-csoportok** oldalon van. Ha az azonosítótábla-csoportosítást mobileszközös munkafeldolgozáshoz kívánja használni, akkor válassza ki az **Azonosítótáblák csoportosítása** opciót a **Mobileszköz** menüjében. Például mobileszközt használunk egy két sort tartalmazó egységszekvenciacsoporttal társított cikk regisztrálásához. Az első sor a Darabra van beállítva, és az **Azonosítótábla-csoportosítás** beállítás **Igen**. A második sor a Raklap egységre van beállítva, és az **Azonosítótábla-csoportosítás** beállítás **Nem**. Ebben az esetben a rendszer automatikusan segítséget nyújt az azonosítótáblák felosztásához és létrehozásához, 100 darabonként.

## <a name="units-for-cycle-counting"></a>Ciklikus leltározáskor használt egységek
Ha meg akarja határozni, hogy mely egységeket kell használni a ciklikus leltározási folyamatok részeként, jelölje be az **Egység használata a ciklikus leltározáshoz** beállítást az **Egységszekvencia-csoportok** oldalon. Egy szekvenciacsoportban maximum négy egységet választhat ki. Ha négynél több egységet ad meg, a további egységek nem jelennek meg a mobileszközön.

## <a name="default-units-for-mobile-device-receiving-processes"></a>A mobileszköz alapértelmezett egységei fogadófolyamatokhoz
Az alapértelmezett egységek beállításához, amelyeket mobileszközökön a fogadófolyamatokhoz akar használni, engedélyezze a **Beszerzés és átmozgatás alapértelmezett egysége** és **Termelés alapértelmezett egysége** a lehetőségeket az **Egységszekvencia-csoportok** lapon. Megadhatja például, hogy alapértelmezés szerint a rendszer Raklapmennyiségeket használjon, ha mobileszköz használatával a beszerzési rendeléssel aktuális készletet bevételeznek, de a készletkezelési egység Darab legyen. Az átalakításhoz, amely tartalmazza az egyes raklapok darabszámát, meg kell adnia a mértékegység-átváltást, például 100 db = 1 raklap.

## <a name="default-order-settings"></a>Alapértelmezett rendelésbeállítások
A kiadott termékek létrehozásának részeként, ki kell választania alapértelmezett mértékegységeket a beszerzéshez, értékesítéshez és a készlethez, a különféle rendelések feldolgozására. Az alapértelmezett egységeket és mennyiségeket a különféle forrásdokumentumokhoz beállíthatja az **Alapértelmezett rendelésbeállítások** és a **Helyspecifikus rendelésbeállítások** lapokon. Ezeket a lapokat a **Kiadott termékek** oldalon érheti el.





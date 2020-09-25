---
title: Projekterőforrások beállítása
description: Ez a témakör a projekterőforrások beállításával vagy kérésével kapcsolatban tartalmaz tájékoztatást.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c882e23794e3937f85b3e73774b36deaf28ac3ed
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760568"
---
# <a name="set-up-project-resources"></a>Projekterőforrások beállítása

[!include [banner](../includes/banner.md)]

Be kell állítania egy új naptárt és hozzá kell rendelnie egy alkalmazottat vagy egy dolgozót. A naptár a projekthez fenntartott erőforrások munkaidejének és a projektek ütemezésére lesz használva. A naptár beállítása alatt a projektvezető az erőforrás optimalizálásának részeként elvégezheti az erőforrás-kiegyenlítést. A naptár-ütemezés alapján korlátozások helyezhetők az erőforrásokra. Beállíthat egy naptárat a **Naptárak** oldalon.

Dolgozó projekt-erőforrásként való beállításakor választhat a vállalatnál dolgozó dolgozók közül, amelyhez beállítja az erőforrásokat. Másik megoldásként a szervezet más cégeinél dolgozó dolgozókat is választhat. Ezeket a dolgozókat vállalatközi erőforrásoknak nevezik.

Az alábbi eljárások bemutatják, hogyan állítható be egy dolgozó projekterőforrásként a vállalaton belül, és hogyan állítható be egy vállalatközi projekterőforrás.

## <a name="set-up-a-worker-as-a-project-resource"></a>Dolgozó beállítása, mint projekterőforrás

1. A **Dolgozók** oldalon, a **Dolgozók** listában jelölje ki azt a dolgozót, akit projekterőforrásként szeretne hozzáadni, majd nyissa meg a dolgozó rekordot.
2. A Műveleti ablaktáblán válassza a **Projekt** &gt; **Beállítás** &gt; **Projektbeállítás** lehetőséget.
3. Válasszon ki egy naptárt, és zárja be a lapot.

Meghatározhat alapértelmezett projekteket az erőforráshoz, mint előzetes hozzárendelés típus. Az előzetes hozzárendelések akkor használhatóak, ha az erőforrás-kezelő vagy a projektkezelő előre tudja, hogy az erőforrás milyen projekteken fog dolgozni. Az előzetes hozzárendelések alapulhatnak a projekttámogató vagy a vevő kérelmein. A projekt előzetes hozzárendeléséhez a **Projektek hozzárendelése** oldalon a **Projektek** lapon a **Fennmaradó projektet** listáján jelölje ki a megfelelő projektet.

## <a name="set-up-an-intercompany-resource"></a>Egy vállalatközi erőforrás beállítása

A munkavállaló vállalatközi erőforrásként való beállításakor el kell végezni a beállítást a kölcsönbe adó és a kölcsönbe vevő vállalatnál.

### <a name="in-the-lending-company"></a>A kölcsönbe adó vállalatnál

1. A Finance rendszerben ellenőrizze, hogy a kölcsönbe adó vállalat ki legyen jelölve, majd végezze el az előző szakaszban leírt eljárást: „Dolgozó beállítása projekterőforrásként”.
2. A **Vállalatközi könyvelés** oldalon válassza az **Új** lehetőséget.
3. A **Jogi személy azonosítója** mezőben válassza ki a kölcsönbe adó vállalatot. Töltse ki a többi megfelelő mezőt, és válassza a **Mentés** elemet.
4. A **Transzferár** oldalon válassza az **Új** lehetőséget.
5. A **Kölcsönbe vevő jogi személy** mezőben válassza ki a megfelelő vállalatot.
6. Ha a kölcsönbe vevő vállalat számára csak az e szakasz elején létrehozott erőforrást szeretné kölcsönbe adni, az **Erőforrás** mezőben válassza ki a létrehozott erőforrás nevét. Ha a kölcsönbe adó vállalat összes erőforrását elérhetővé szeretné tenni a kölcsönbe vevő vállalat számára, hagyja üresen az **Erőforrás** mezőt.
7. A **Projektvezetési és könyvelési paraméterek** oldalon a **Vállalatközi** lapon állítsa a **Vállalatközi erőforrás-ütemezés és időnyilvántartások engedélyezése** mező értékét az **Igen** értékre.

### <a name="in-the-borrowing-company"></a>A kölcsönbe vevő vállalatnál

- Az **Erőforrások listája** oldalon a keresési szűrőbe írja be a nevét a kölcsönbe adó vállalathoz létrehozott erőforrásnak annak az ellenőrzéséhez, hogy az erőforrás szerepel a kölcsönbe vevő vállalat erőforráslistájában.

## <a name="request-project-resources"></a>Projekterőforrás kérése
A projekterőforrás-ütemezési szolgáltatás csak a személyzettel ellátott erőforrások vagy előjegyzések elosztását engedi az erőforrás-kezelőknek. A funkció engedélyezéséhez végezze el a következő feladatokat, vagy győződjön meg arról, hogy befejeződtek:

- Számsorozatok beállítása.
- Munkafolyamatok beállítása a projektvezetéshez és a könyveléshez.
- Engedélyezze az erőforrás-kérelem munkafolyamatokat.

Miután az előző feladatok befejeződtek, elvégezheti az alábbi feladatokat, szükség szerint:

- Erőforrás-igénylés létrehozása ideiglenesen lefoglalt személyzettel ellátott erőforráshoz.
- Erőforrás-kérelmek figyelése.
- Erőforrás-kérelmek teljesítése.
- Személyzettel ellátott erőforrás kérése WBS-től.
- Erőforrások foglalása egy projekthez személyzettel ellátott erőforrások iránti kérelem nélkül.

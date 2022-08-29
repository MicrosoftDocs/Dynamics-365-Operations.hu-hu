---
title: Elektronikus jelentések formátumának módosítása Excel-sablonok újbóli alkalmazásával
description: Ez a témakör azt mutatja be, hogyan lehet módosítani az üzleti dokumentumok előállításához használt elektronikus jelentési (ER) formátumot a módosított Excel-sablonok újra alkalmazásával.
author: kfend
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 27621
ms.assetid: e3f7960d-2e01-46a7-9ac8-c355ac933cd6
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
ms.openlocfilehash: 02423a75d96bef0452b8555f8c7a9f0aca0b6771
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283528"
---
# <a name="modify-electronic-reporting-formats-by-reapplying-excel-templates"></a>Elektronikus jelentés formátumainak módosítása Microsoft Excel sablonok újbóli alkalmazásával

[!include [banner](../includes/banner.md)]

Az elektronikus jelentési (ER) eszköz üzleti dokumentumok elektronikus formában való létrehozásához használatos. Üzleti dokumentum létrehozásához ER-formátumot kell létrehozni, és ezután az ER-tervező segítségével meg kell határozni az üzleti dokumentum elrendezését, és megadni az adatokat, amelyeknek szerepelniük kell benne. Ezt követően futtathatja az üzleti dokumentum létrehozásához az ER-formátumot.

Az ER-eszközzel üzleti dokumentumokat lehet létrehozni Microsoft Excel-fájlok formájában. Egy Excel-dokumentumot lehet sablonként használni a dokumentumokhoz. Dokumentumelrendezés definiálásához az ER-tervezőben importálhatja a sablonként használni kívánt az Excel-dokumentum tartalmát a meghatározott ER-formátumba. A folyamat további részleteivel kapcsolatban, valamint gyakorlásként hajtsa végre az **ER Az OPENXML formátumban létrejövő jelentésekre vonatkozó konfigurációk tervezése** című feladat-útmutatót (a 7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677) üzleti folyamat része). A feladat útmutatójának excel-sablon importálásához használja a Kifizetési jelentés Excel-fájljának kiindulási sablonját([SampleVendPaymWsReport)](https://download.microsoft.com/download/e/6/b/e6bb79f0-cc08-44af-96fa-49c7929d4fb8/SampleVendPaymWsReport.xlsx).

Ha módosítja az Excel-dokumentumot, amely üzletidokumentum-sablonként szolgál, az új ER-funkció lehetővé teszi a frissített sablon újbóli alkalmazását az ER-formátumra. Az ER-formátum ekkor frissül, hogy megfeleljen a frissített sablonnak. A funkcióval kapcsolatos további részletekért hajtsa végre az **Elektronikus jelentés formátumának módosítása Microsoft Excel sablon újbóli alkalmazásával** című feladat-útmutatót (a 7.5.5.3 Módosított informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10683)). A feladat útmutatójának lépésében, amelyben frissített sablont importál, [használja a Fizetési jelentés Excel-fájljának (SampleVendPaymWsReport2) módosított sablonját](https://download.microsoft.com/download/3/1/0/3104d397-c9c5-4227-b68e-f98625313801/SampleVendPaymWsReport2.xlsx).

## <a name="additional-resources"></a>További erőforrások

[Sablon frissítése](er-fillable-excel.md#update-a-template)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

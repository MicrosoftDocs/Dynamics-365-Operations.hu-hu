---
title: "Elektronikus jelentéskészítési formátum módosítása egy Microsoft Excel-sablon ismételt alkalmazásával"
description: "Ez a témakör azt ismerteti, hogyan módosíthatja az elektronikus jelentési (ER) formátumot, amely az üzleti dokumentumok létrehozásához használatos, egy módosított Excel-sablon újbóli alkalmazásával."
author: NickSelin
manager: AnnBe
ms.date: 06/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.search.scope: Operations
ms.custom: 27621
ms.assetid: e3f7960d-2e01-46a7-9ac8-c355ac933cd6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: af7f9a373496eee4df354d5dd9e5a25c51317c43
ms.openlocfilehash: fca7fb75b965886c2ebc06b12940434f2ffc2543
ms.contentlocale: hu-hu
ms.lasthandoff: 02/27/2018

---
# <a name="modify-an-electronic-reporting-format-by-reapplying-a-microsoft-excel-template"></a>Elektronikus jelentéskészítési formátum módosítása egy Microsoft Excel-sablon ismételt alkalmazásával

[!include [banner](../includes/banner.md)]

Az elektronikus jelentési (ER) eszköz üzleti dokumentumok elektronikus formában való létrehozásához használatos. Üzleti dokumentum létrehozásához ER-formátumot kell létrehozni, és ezután az ER-tervező segítségével meg kell határozni az üzleti dokumentum elrendezését, és megadni az adatokat, amelyeknek szerepelniük kell benne. Ezt követően futtathatja az üzleti dokumentum létrehozásához az ER-formátumot.

Az ER-eszközzel üzleti dokumentumokat lehet létrehozni Microsoft Excel-fájlok formájában. Egy Excel-dokumentumot lehet sablonként használni a dokumentumokhoz. Dokumentumelrendezés definiálásához az ER-tervezőben importálhatja a sablonként használni kívánt az Excel-dokumentum tartalmát a meghatározott ER-formátumba. A folyamat további részleteivel kapcsolatban, valamint gyakorlásként hajtsa végre az **ER Az OPENXML formátumban létrejövő jelentésekre vonatkozó konfigurációk tervezése** című feladat-útmutatót (a 7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677) üzleti folyamat része).

Ha módosítja az Excel-dokumentumot, amely üzletidokumentum-sablonként szolgál, az új ER-funkció lehetővé teszi a frissített sablon újbóli alkalmazását az ER-formátumra. Az ER-formátum ekkor frissül, hogy megfeleljen a frissített sablonnak. A funkcióval kapcsolatos további részletekért hajtsa végre az **Elektronikus jelentés formátumának módosítása Microsoft Excel sablon újbóli alkalmazásával** című feladat-útmutatót (a 7.5.5.3 Módosított informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10683)). A frissített sablon importálása feladatútmutató-lépésben használja a kifizetési jelentés Excel fájl módosított sablonját (SampleVendPaymWsReport2) sablonként.


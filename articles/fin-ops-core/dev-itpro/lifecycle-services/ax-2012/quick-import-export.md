---
title: Gyors importálás/exportálás
description: A Gyors importálás-exportálás célja lehetővé tenni a behozatalt és kivitelt kevesebb lépésben.
author: margoc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: dynamics-ax-2012
ms.service: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 89041
ms.assetid: 990d64e6-d436-4c79-9bb5-bf8c5c5a048f
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: ''
ms.dyn365.ops.version: AX 2012 R3 CU8
ms.openlocfilehash: c5425f53ba66b4123457154386bf51342697fbd1
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683202"
---
# <a name="quick-import-export"></a><span data-ttu-id="ac58c-103">Gyors importálás/exportálás</span><span class="sxs-lookup"><span data-stu-id="ac58c-103">Quick import export</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ac58c-104">A Gyors importálás-exportálás célja lehetővé tenni a behozatalt és kivitelt kevesebb lépésben.</span><span class="sxs-lookup"><span data-stu-id="ac58c-104">The purpose of Quick import export is to let you import and export with fewer steps.</span></span>

<span data-ttu-id="ac58c-105">Elérhetővé tettük a Gyors importálás/exportálás szolgáltatást, amely a felhasználók számára lehetővé teszi egyszerű feladatok importálását vagy exportálását a feladatok gyors elvégzéséhez.</span><span class="sxs-lookup"><span data-stu-id="ac58c-105">We added the Quick Import Export feature to let users import or export simple jobs that they want to execute quickly.</span></span> <span data-ttu-id="ac58c-106">Ideális esetben ez a szolgáltatás olyan esetekben használatos, amikor a fájl automatikusan feltérképezi a rendszert és a felhasználónak nem kell végigjárni a speciális feltérképezést vagy behozatali vagy kiviteli feladatok ismételt létrehozását.</span><span class="sxs-lookup"><span data-stu-id="ac58c-106">Ideally this feature is used in scenarios in which a file automatically maps to the system and user does not need to go through advanced mapping or create repeated import or export jobs.</span></span>

- <span data-ttu-id="ac58c-107">E szolgáltatás támogatja mind a kulcsrakész, mind az egyéni entitásokat.</span><span class="sxs-lookup"><span data-stu-id="ac58c-107">This feature supports working with both out-of-the-box and custom entities.</span></span>
- <span data-ttu-id="ac58c-108">Fájlokból importálhat, és ha ODBC-adatforrást használ, lekérdezés választásával meghatározhatja az importálást.</span><span class="sxs-lookup"><span data-stu-id="ac58c-108">You can import from files, and if you are using an ODBC data source, you can select a query to use to define your import.</span></span>
- <span data-ttu-id="ac58c-109">Korábban meg kellett határoznia akár az AX, akár a Fájl forrásadatainak formátumát , és tudnia kell, hol találhatóak ezek.</span><span class="sxs-lookup"><span data-stu-id="ac58c-109">You must have previously defined source data formats for either AX or File, and know where they are located.</span></span>
- <span data-ttu-id="ac58c-110">A gyors importálási/exportálás lehetőséghez nem kell feldolgozás csoportot létrehoznia, ez automatikusan létrehozásra kerül a rendszer által a behozatali vagy kiviteli feladat végrehajtásakor.</span><span class="sxs-lookup"><span data-stu-id="ac58c-110">You do not need to create a processing group to use quick import/export, one will be automatically created by the system when executing the import or export job.</span></span> <span data-ttu-id="ac58c-111">Választhatja a gyors import-export által importált adatok előzményeinek megőrzését is.</span><span class="sxs-lookup"><span data-stu-id="ac58c-111">You can also choose keep the history of the data imported by the quick import/export.</span></span>

  <span data-ttu-id="ac58c-112">Vegye figyelembe, hogy a gyors importálás és exportálás feltételezi, hogy jártas a DIXF-fel kapcsolatos fogalmakban.</span><span class="sxs-lookup"><span data-stu-id="ac58c-112">Note that Quick import export assumes that you are familiar with the concepts of DIXF.</span></span>




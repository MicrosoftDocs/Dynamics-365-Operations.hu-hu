---
title: Felvételi folyamatsablon létrehozása az Attract alkalmazásban
description: Ez a témakör információt nyújt a felvételi folyamatsablonok létrehozásáról az Attract alkalmazásban.
author: andreabichsel
manager: AnnBe
ms.date: 10/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: AX 8.1
ms.openlocfilehash: 82046d43cf7366b760c140bdb8b017337b4f41da
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/25/2019
ms.locfileid: "2832558"
---
# <a name="create-a-hiring-process-template-in-attract"></a><span data-ttu-id="21f70-103">Felvételi folyamatsablon létrehozása az Attract alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="21f70-103">Create a hiring process template in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="21f70-104">A *Felvételi folyamat sablonja* egy állás felvételi folyamatának összes tevékenységet tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="21f70-104">A *hiring process template* contains all the activities that should be included as part of the hiring process for a job.</span></span> <span data-ttu-id="21f70-105">Ez a témakör ismerteti az folyamatsablonnal kapcsolatos elemeket az Microsoft Dynamics 365 Talent: Attract alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="21f70-105">This topic describes the elements of a process template in Microsoft Dynamics 365 Talent: Attract.</span></span> <span data-ttu-id="21f70-106">Azt is bemutatja, hogyan lehet létrehozni egy sablont.</span><span class="sxs-lookup"><span data-stu-id="21f70-106">It also explains how to create a template.</span></span>

> [!NOTE]
> <span data-ttu-id="21f70-107">A sablon-létrehozás az Attract alkalmazás Átfogó felvételi bővítményének része.</span><span class="sxs-lookup"><span data-stu-id="21f70-107">Template creation is part of the Comprehensive Hiring Add-on for Attract.</span></span>

## <a name="template-management"></a><span data-ttu-id="21f70-108">Sablonkezelés</span><span class="sxs-lookup"><span data-stu-id="21f70-108">Template management</span></span>

<span data-ttu-id="21f70-109">A szervezetek eldöntheti, hogy csak a rendszergazdák vagy a csoport tagjai is létrehozhatnak folyamatsablonokat az Attract alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="21f70-109">Organizations can decide whether team members or only admins can create process templates in Attract.</span></span> <span data-ttu-id="21f70-110">A sablonkezelés konfigurálásához kattintson az **Adminisztrációs Központ** \> **Sablonkezelés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="21f70-110">To configure template management, go to **Admin Center** \> **Template management**.</span></span> <span data-ttu-id="21f70-111">Ahhoz, hogy a csapattagok saját sablonokat hozhassanak létre, kapcsolja be a sablonkezelést.</span><span class="sxs-lookup"><span data-stu-id="21f70-111">To let team members create their own templates, turn on template management.</span></span> <span data-ttu-id="21f70-112">Ha nem kapcsolja be a sablonkezelést, csak rendszergazdák hozhatnak létre sablonokat.</span><span class="sxs-lookup"><span data-stu-id="21f70-112">If you don't turn on template management, only admins can create templates.</span></span>

## <a name="default-template"></a><span data-ttu-id="21f70-113">Alapértelmezett sablon</span><span class="sxs-lookup"><span data-stu-id="21f70-113">Default template</span></span>

<span data-ttu-id="21f70-114">Csak a rendszergazdák állíthatják be az alapértelmezett sablont.</span><span class="sxs-lookup"><span data-stu-id="21f70-114">Only admins can set the default template.</span></span> <span data-ttu-id="21f70-115">Az alapértelmezett sablont használja a rendszer, ha az állás létrehozásakor nincs sablon kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="21f70-115">The default template is used if a template isn't selected when a job is created.</span></span> <span data-ttu-id="21f70-116">Az alapértelmezett sablon beállításához kattintson az **Adminisztrációs Központ** \> **Sablonkezelés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="21f70-116">To set the default template, go to **Admin Center** \> **Template management**.</span></span> <span data-ttu-id="21f70-117">Az alapértelmezettnek kiválasztott sablon kártyáján válassza a hármaspont gombot (**…**), majd válassza a **Beállítás alapértelmezettként** beállítást.</span><span class="sxs-lookup"><span data-stu-id="21f70-117">On the card for the template that should be the default template, select the ellipsis button (**...**), and then select **Set as default**.</span></span>

## <a name="create-a-process-template"></a><span data-ttu-id="21f70-118">Folyamatsablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="21f70-118">Create a process template</span></span>

<span data-ttu-id="21f70-119">Rendszergazdák, toborzásért felelős személyek és a vezetők hozhatnak létre folyamatsablonokat.</span><span class="sxs-lookup"><span data-stu-id="21f70-119">Admins, recruiters, and hiring managers can create process templates.</span></span> <span data-ttu-id="21f70-120">Egy folyamatsablon *fokozatokból* és *tevékenységekből* áll.</span><span class="sxs-lookup"><span data-stu-id="21f70-120">A process template consists of *stages* and *activities*.</span></span> <span data-ttu-id="21f70-121">A fokozatok egy vagy több tevékenységet csoportosítanak.</span><span class="sxs-lookup"><span data-stu-id="21f70-121">Stages group together one or more activities.</span></span> <span data-ttu-id="21f70-122">Alapértelmezés szerint minden folyamatsablonban vannak Jelöltre, Pályázatra és Ajánlatra vonatkozó tevékenységek.</span><span class="sxs-lookup"><span data-stu-id="21f70-122">By default, every process template has Prospect, Application, and Offer activities.</span></span> <span data-ttu-id="21f70-123">Azokat a fokozatokat lehet átnevezni, amelyek tartalmazzák ezeket a tevékenységeket.</span><span class="sxs-lookup"><span data-stu-id="21f70-123">The stages that contain these activities can be renamed.</span></span> <span data-ttu-id="21f70-124">Több fokozatot is hozzáadhat a **+ Új fokozat** kiválasztásával.</span><span class="sxs-lookup"><span data-stu-id="21f70-124">You can add more stages by selecting **+ New Stage**.</span></span> <span data-ttu-id="21f70-125">A tevékenységeket fokozatokhoz adhatja vagy a megfelelő fokozatra húzással vagy ha a tevékenységlistában duplán kattint rájuk.</span><span class="sxs-lookup"><span data-stu-id="21f70-125">You can add activities to a stage either by dragging them to the appropriate stage or by double-clicking them in the activity list.</span></span>

> [!NOTE]
> <span data-ttu-id="21f70-126">A fokozatok nevei a jelöltek számára láthetók a **Pályázat állapota** oldalon.</span><span class="sxs-lookup"><span data-stu-id="21f70-126">Stage names are visible to candidates on the **Application status** page.</span></span> <span data-ttu-id="21f70-127">Vegye figyelembe ezt, amikor elnevezi a fokozatokat.</span><span class="sxs-lookup"><span data-stu-id="21f70-127">You should consider this fact when you choose names for stages.</span></span>

<span data-ttu-id="21f70-128">Tevékenységekkel kapcsolatos további tudnivalókért tekintse meg a [Felvételi folyamatok tevékenységei](./activities-attract.md) részt.</span><span class="sxs-lookup"><span data-stu-id="21f70-128">To learn more about activities, see [Activities in hiring processes](./activities-attract.md).</span></span>

<span data-ttu-id="21f70-129">Felvételi folyamatsablon létrehozásához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="21f70-129">Follow these steps to create a hiring process template.</span></span>

1. <span data-ttu-id="21f70-130">Ugorjon a **Sablonok** részre.</span><span class="sxs-lookup"><span data-stu-id="21f70-130">Go to **Templates**.</span></span>
2. <span data-ttu-id="21f70-131">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="21f70-131">Select **New**.</span></span>
3. <span data-ttu-id="21f70-132">Adja meg a sablon nevét a **Sablon neve** mezőben, majd kattintson a **Létrehozás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="21f70-132">In the **Template name** field, enter a name for the template, and then select **Create**.</span></span>
4. <span data-ttu-id="21f70-133">A **Jóváhagyási folyamat kiválasztása** listában válassza ki az **Alapértelmezett** lehetőséget, hogy jóváhagyást kérjen egy álláshoz.</span><span class="sxs-lookup"><span data-stu-id="21f70-133">In the **Choose the approval process** list, select **Default** to require approval for a job.</span></span>
5. <span data-ttu-id="21f70-134">Bejelölésével engedélyezheti vagy letilthatja a jelölteket.</span><span class="sxs-lookup"><span data-stu-id="21f70-134">Select to enable or disable prospects.</span></span>
6. <span data-ttu-id="21f70-135">Választható: Fokozatok hozzáadása vagy eltávolítása.</span><span class="sxs-lookup"><span data-stu-id="21f70-135">Optional: Add or remove stages.</span></span>

    - <span data-ttu-id="21f70-136">Egy szakasz hozzáadásához jelölje ki a **+ Új szakasz** elemet.</span><span class="sxs-lookup"><span data-stu-id="21f70-136">To add a stage, select **+ New Stage**.</span></span>
    - <span data-ttu-id="21f70-137">Egy fokozat eltávolításához vigye a kurzort a fokozat fölé, majd válassza ki a megjelenő szemeteskuka gombot.</span><span class="sxs-lookup"><span data-stu-id="21f70-137">To remove a stage, hover the pointer over the stage, and then select the trash can button that appears.</span></span>

        > [!NOTE]
        > <span data-ttu-id="21f70-138">A Jelölt, Pályázat és Ajánlat fokozatokat nem lehet eltávolítani, de át lehet őket nevezni.</span><span class="sxs-lookup"><span data-stu-id="21f70-138">Prospect, Application, and Offer stages can't be removed, but they can be renamed.</span></span>

7. <span data-ttu-id="21f70-139">Választható: Tevékenységek hozzáadása vagy eltávolítása.</span><span class="sxs-lookup"><span data-stu-id="21f70-139">Optional: Add or remove activities.</span></span>

    - <span data-ttu-id="21f70-140">Egy tevékenység hozzáadásához húzza át azt a jobb oldalon található tevékenységek listájáról a megfelelő fokozatra.</span><span class="sxs-lookup"><span data-stu-id="21f70-140">To add an activity, drag it from the activity list on the right to the appropriate stage.</span></span> <span data-ttu-id="21f70-141">Másik lehetőségként kattintson duplán a tevékenységre, és válassza ki a szakaszt, amelyikhez hozzá szeretné adni.</span><span class="sxs-lookup"><span data-stu-id="21f70-141">Alternatively, double-click the activity, and then select the stage to add it to.</span></span>
    - <span data-ttu-id="21f70-142">Egy tevékenység eltávolításához bontsa ki azt, majd kattintson a tevékenység fejlécében a szemeteskuka gombra.</span><span class="sxs-lookup"><span data-stu-id="21f70-142">To remove an activity, expand it, and then select the trash can button on the activity header.</span></span>

8. <span data-ttu-id="21f70-143">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="21f70-143">Select **Save**.</span></span>

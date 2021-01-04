---
title: A rekordsablonok áttekintése
description: Ez a cikk bevezetőként szolgál a rekordsablonok koncepciójába és bemutatja, hogyan alkalmazhatóak új, információ megosztására alkalmas rekordok létrehozására.
author: pvillads
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 16101
ms.assetid: 61ada2d8-84c3-44bc-b4c5-516b1aeac3d1
ms.search.region: Global
ms.author: pvillads
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0b55046e6c523398b4a30e674dc9f77bb6fedf3
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693208"
---
# <a name="record-templates-overview"></a><span data-ttu-id="299b5-103">A rekordsablonok áttekintése</span><span class="sxs-lookup"><span data-stu-id="299b5-103">Record templates overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="299b5-104">Ez a cikk bevezetőként szolgál a rekordsablonok koncepciójába és bemutatja, hogyan alkalmazhatóak új, információ megosztására alkalmas rekordok létrehozására.</span><span class="sxs-lookup"><span data-stu-id="299b5-104">This article introduces the concept of record templates and explains how they can be used to create records that share information.</span></span>

<span data-ttu-id="299b5-105">A rekordsablon segít a rekordok gyorsabb létrehozásában, de bizonyos bejegyzéstípusokhoz csak rekord sablonokat lehet létrehozni.</span><span class="sxs-lookup"><span data-stu-id="299b5-105">Record templates can help you to create records more quickly, however you can only create record templates for some record types.</span></span>

<span data-ttu-id="299b5-106">Például képzelje el, hogy bérleti információt ad meg egy San Franciscóban található autókölcsönző vállalkozáshoz.</span><span class="sxs-lookup"><span data-stu-id="299b5-106">For example, imagine you are entering rental information for a car rental business that is located in San Francisco.</span></span> <span data-ttu-id="299b5-107">Mivel a legtöbb ügyfél valószínűleg San Franciscóból és környékéről származik majd, jó lenne automatikusan kitölteni az **Állam**, **Ország** és **Város** értékeket a bérleti képernyőn.</span><span class="sxs-lookup"><span data-stu-id="299b5-107">Since most of the customers are likely to be from the San Francisco area, it would be nice if you could automatically fill in the values for the **State**, **Country**, and **City** fields on the rental form.</span></span>

> [!NOTE]
> <span data-ttu-id="299b5-108">Csak azokban a részekben alkalmazhat sablonokat, amelyekhez van hozzáférése.</span><span class="sxs-lookup"><span data-stu-id="299b5-108">You can apply templates only in areas that you have access to.</span></span> <span data-ttu-id="299b5-109">Azonban minden sabloncím látható, amikor új rekordot hoz létre, és más felhasználók számára is, ha az összes felhasználó számára rendelkezésre álló sablonokat hoz létre.</span><span class="sxs-lookup"><span data-stu-id="299b5-109">However all template titles are visible to you when you create a new record, and to other users as well, if you are creating templates that will be available for all users.</span></span> <span data-ttu-id="299b5-110">Ezt mindenképpen figyelembe kell venni a sablonok elnevezésekor.</span><span class="sxs-lookup"><span data-stu-id="299b5-110">Be sure to consider this when naming templates.</span></span> <span data-ttu-id="299b5-111">Ha például bizalmasan kell kezelni, hogy a vállalat egyes alkalmazottai jutalékalapú fizetést kapnak, akkor kerülni kell az olyan elnevezéseket, amelyekben a jutalék szó szerepel.</span><span class="sxs-lookup"><span data-stu-id="299b5-111">For example, avoid using names that include words, such as "commission," if is confidential that some employees in the company have commission-based salaries.</span></span>

<span data-ttu-id="299b5-112">Ha egy adott képernyőhöz egy vagy több olyan sablon áll rendelkezésre, melyekhez Ön hozzáfér, és egy új rekordot próbál létrehozni a képernyőn, akkor megjelenik az **Egy sablon kiválasztása...** oldal.</span><span class="sxs-lookup"><span data-stu-id="299b5-112">When one or more templates that you have access to exist for a specific form and you attempt to create a new record in the form, the **Select a template for** page is displayed.</span></span> <span data-ttu-id="299b5-113">Amikor kiválasztja a sablont a listából, a kiválasztott sablon alapján létrejön egy alapértelmezett adatokat tartalmazó új rekord.</span><span class="sxs-lookup"><span data-stu-id="299b5-113">When you select a template from the list, the new record is created and contains default information that is based on the template that you selected.</span></span> <span data-ttu-id="299b5-114">Ha nem szeretne sablonokat használni az új rekordok létrehozásához, akkor jelölje be a **Ne jelenjen meg többet ez a kérdés** jelölőnégyzetet az **Egy sablon kiválasztása...** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="299b5-114">If you do not want to use templates when you create new records, select the **Do not ask again** check box in the **Select a template for** page.</span></span> <span data-ttu-id="299b5-115">A sablonválasztási párbeszédpanel újbóli megjelenítéséhez kattintson bármelyik rekordra a jobb gombbal, kattintson a **Rekord adatai** elemre, majd kattintson a **Sablonkiválasztás megjelenítése** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="299b5-115">To display the template selection dialog box again, right-click any record, click **Record info**, and then click **Show template selection**.</span></span>

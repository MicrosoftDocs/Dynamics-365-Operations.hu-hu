---
title: Kiadott termékre nem lehet sablont alkalmazni
description: Kiadott termékre nem lehet sablont alkalmazni.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1ad6efdced9bce924fbf5bc207c92fa2c3a6c79d
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026568"
---
# <a name="you-cant-apply-a-template-to-create-a-released-product"></a><span data-ttu-id="442d6-103">Kiadott termék létrehozásához nem lehet sablont alkalmazni</span><span class="sxs-lookup"><span data-stu-id="442d6-103">You can't apply a template to create a released product</span></span>

<span data-ttu-id="442d6-104">Tudásbáziscikk száma: 4612097</span><span class="sxs-lookup"><span data-stu-id="442d6-104">KB number: 4612097</span></span>

## <a name="symptoms"></a><span data-ttu-id="442d6-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="442d6-105">Symptoms</span></span>

<span data-ttu-id="442d6-106">Amikor új kiadott terméket hoz létre az **Új kiadott termék** párbeszédpanelen, ki lehet választani egy sablont.</span><span class="sxs-lookup"><span data-stu-id="442d6-106">When you create a new released product by using the **New released product** dialog box, you can select a template.</span></span> <span data-ttu-id="442d6-107">A sablonnak az új kiadott termék számos mezőjéhez alapértelmezett beállításokat kell adnia.</span><span class="sxs-lookup"><span data-stu-id="442d6-107">The template is supposed to provide default settings for many fields of the new released product.</span></span> <span data-ttu-id="442d6-108">A sablon kiválasztása után azonban néhány vagy az összes mező nem lesz beállítva.</span><span class="sxs-lookup"><span data-stu-id="442d6-108">However, some or all of the fields aren't set after you select the template.</span></span>

## <a name="cause"></a><span data-ttu-id="442d6-109">Ok</span><span class="sxs-lookup"><span data-stu-id="442d6-109">Cause</span></span>

<span data-ttu-id="442d6-110">A Microsoft Dynamics 365 Supply Chain Management számos lapja lehetőséget ad olyan sablon létrehozására, amely meghatározza az ilyen lapokon megjelenő rekordok kezdeti beállításait.</span><span class="sxs-lookup"><span data-stu-id="442d6-110">Many pages in Microsoft Dynamics 365 Supply Chain Management let you create a template that establishes initial settings for the records that are shown on those pages.</span></span> <span data-ttu-id="442d6-111">Egy ilyen sablont úgy hozhat létre, hogy kiválasztja a **Rekordadatok** lehetőséget a Műveleti panel **Beállítások** lapján.</span><span class="sxs-lookup"><span data-stu-id="442d6-111">You can create one of these templates by selecting **Record info** on the **Options** tab of the Action Pane.</span></span> <span data-ttu-id="442d6-112">A kiadott termékek azonban összetettebbek, mint a legtöbb más rekordtípus.</span><span class="sxs-lookup"><span data-stu-id="442d6-112">However, released products are much more complex than most other types of records.</span></span> <span data-ttu-id="442d6-113">Bár a **Kiadott termékek** lapon **Rekordadatokat** választhat sablon létrehozásához, és bár a sablont ki is választhatja a kiadott termékek létrehozásakor, a sablon nem fogja tartalmazni az új kiadott termék várt mezőértékeit.</span><span class="sxs-lookup"><span data-stu-id="442d6-113">Although you can select **Record info** on the **Released products** page to create a template, and although you can select that template when you create a released product, the template won't provide the expected field values for the new released product.</span></span> <span data-ttu-id="442d6-114">Így a kiadott termékekhez nem használhatja a "rekordinformációk" sablonokat.</span><span class="sxs-lookup"><span data-stu-id="442d6-114">Therefore, you can't use "record info" templates for released products.</span></span> <span data-ttu-id="442d6-115">Ehelyett külön terméksablonokat kell létrehoznia.</span><span class="sxs-lookup"><span data-stu-id="442d6-115">Instead, you must create dedicated product templates.</span></span>

## <a name="resolution"></a><span data-ttu-id="442d6-116">Felbontás</span><span class="sxs-lookup"><span data-stu-id="442d6-116">Resolution</span></span>

<span data-ttu-id="442d6-117">Terméksablon létrehozásához használja a Munkaablak **Termék** lapján található **Sablon** menüt, nem pedig a **Beállítások** lap **Rekordinformációk** lapját.</span><span class="sxs-lookup"><span data-stu-id="442d6-117">To create a product template, use the **Template** menu on the **Product** tab of the Action Pane, not the **Record info** button on the **Options** tab.</span></span>

1. <span data-ttu-id="442d6-118">Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="442d6-118">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="442d6-119">A Műveleti panelen a **Termék** lapon, az **Új** csoportban válassza a **Sablon** lehetőséget, majd válassza a **Személyes sablon létrehozása** vagy a **Megosztott sablon létrehozása** lehetőséget igény szerint.</span><span class="sxs-lookup"><span data-stu-id="442d6-119">On the Action Pane, on the **Product** tab, in the **New** group, select **Template**, and then select either **Create personal template** or **Create shared template**, as appropriate.</span></span>

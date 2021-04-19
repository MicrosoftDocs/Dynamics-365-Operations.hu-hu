---
title: Retail funkcióprofil létrehozása
description: Ez a témakör azt mutatja be, hogyan lehet egy új funkcióprofilt létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: b8d481597485775796290f61de19ef7682cb9f43
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791997"
---
# <a name="create-a-retail-functionality-profile"></a><span data-ttu-id="8e8dd-103">Retail funkcióprofil létrehozása</span><span class="sxs-lookup"><span data-stu-id="8e8dd-103">Create a retail functionality profile</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8e8dd-104">Ez a témakör azt mutatja be, hogyan lehet egy új funkcióprofilt létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="8e8dd-104">This topic describes how to create a functionality profile in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="8e8dd-105">A funkcióprofil különböző beállításokat biztosít az online csatornákhoz.</span><span class="sxs-lookup"><span data-stu-id="8e8dd-105">The commerce functionality profile provides various settings used for online channels.</span></span> <span data-ttu-id="8e8dd-106">Minden csatornának meg kell adnia egy funkciókat tartalmazó profilt.</span><span class="sxs-lookup"><span data-stu-id="8e8dd-106">Each channel must specify a functionality profile.</span></span>

## <a name="create-a-functionality-profile"></a><span data-ttu-id="8e8dd-107">Funkcióprofil létrehozása</span><span class="sxs-lookup"><span data-stu-id="8e8dd-107">Create a functionality profile</span></span>

<span data-ttu-id="8e8dd-108">Új funkcióprofil létrehozásához az alábbi lépéseket hajtsa végre.</span><span class="sxs-lookup"><span data-stu-id="8e8dd-108">To create a functionality profile, follow these steps.</span></span>

1. <span data-ttu-id="8e8dd-109">A navigációs ablaktáblán ugorjon a **Modulok \> Csatorna beállítás \> Pénztárprofilok  \> Funkcióprofilok** elemre.</span><span class="sxs-lookup"><span data-stu-id="8e8dd-109">In the navigation pane, go to **Modules \> Channel setup \> POS profiles \> Functionality profiles**.</span></span>
1. <span data-ttu-id="8e8dd-110">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="8e8dd-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="8e8dd-111">A **Profil** mezőbe írjon be egy azonosítót a profilhoz (a lenti következő példában szereplő képen: „FN006”).</span><span class="sxs-lookup"><span data-stu-id="8e8dd-111">In the **Profile** field, enter an ID for the profile ("FN006" in the example image below).</span></span>
1. <span data-ttu-id="8e8dd-112">A **Leírás** mezőbe írjon be egy értéket (a lenti példában szereplő képen: „Kalandorbolt-profil”).</span><span class="sxs-lookup"><span data-stu-id="8e8dd-112">In the **Description** field, enter a value ("Adventure Works Profile" in the example image below).</span></span>
1. <span data-ttu-id="8e8dd-113">Az **Általános** részben válasszon ki egy országot az **ISO** területi beállításhoz.</span><span class="sxs-lookup"><span data-stu-id="8e8dd-113">In the **General** section, select a country for the **ISO** locale.</span></span>
1. <span data-ttu-id="8e8dd-114">Szükség szerint módosítsa az **Általános** szakasz egyéb beállításait.</span><span class="sxs-lookup"><span data-stu-id="8e8dd-114">In the **General** section, modify other settings, as needed.</span></span>
1. <span data-ttu-id="8e8dd-115">Az **Általános** részben válassza ki a **Nyugtaprofil azonosítóját** az e-mailes nyugtákhoz.</span><span class="sxs-lookup"><span data-stu-id="8e8dd-115">In the **General** section, select a **Receipt profile ID** for email receipts.</span></span>
1. <span data-ttu-id="8e8dd-116">Szükség szerint módosítsa a **Funkciók** szakasz beállításait.</span><span class="sxs-lookup"><span data-stu-id="8e8dd-116">In the **Functions** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="8e8dd-117">Szükség szerint módosítsa az **Összeg** szakasz beállításait.</span><span class="sxs-lookup"><span data-stu-id="8e8dd-117">In the **Amount** section, modify settings as, needed.</span></span>
1. <span data-ttu-id="8e8dd-118">Szükség szerint módosítsa az **Infókódok** szakasz beállításait.</span><span class="sxs-lookup"><span data-stu-id="8e8dd-118">In the **Info Codes** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="8e8dd-119">Szükség szerint módosítsa a **Nyugta számozása** szakasz egyéb beállításait.</span><span class="sxs-lookup"><span data-stu-id="8e8dd-119">In the **Receipt numbering** section, modify settings, as needed.</span></span> 
  
<span data-ttu-id="8e8dd-120">A következő kép egy példát mutat a funkcióprofilra.</span><span class="sxs-lookup"><span data-stu-id="8e8dd-120">The following image shows an example functionality profile.</span></span>
  
![Példa a funkcióprofilra](media/retail-functionality-profile.png)

## <a name="additional-resources"></a><span data-ttu-id="8e8dd-122">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8e8dd-122">Additional resources</span></span>

[<span data-ttu-id="8e8dd-123">Infókódok és infókódcsoportok</span><span class="sxs-lookup"><span data-stu-id="8e8dd-123">Info codes and info code groups</span></span>](info-codes-retail.md)           

[<span data-ttu-id="8e8dd-124">Új címjegyzék létrehozása</span><span class="sxs-lookup"><span data-stu-id="8e8dd-124">Create new address book</span></span>](new-address-book.md) 

[<span data-ttu-id="8e8dd-125">Képernyő-elrendezés áttekintése</span><span class="sxs-lookup"><span data-stu-id="8e8dd-125">Screen layout overview</span></span>](pos-screen-layouts.md)       

[<span data-ttu-id="8e8dd-126">A Retail Hardware Station konfigurálása és telepítése</span><span class="sxs-lookup"><span data-stu-id="8e8dd-126">Configure and install Retail hardware station</span></span>](retail-hardware-station-configuration-installation.md) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]

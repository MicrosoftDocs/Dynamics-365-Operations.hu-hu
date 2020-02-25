---
title: " Pénztárgépek létrehozása és hozzárendelése"
description: Ez az eljárás azt mutatja be, hogy hogyan lehet pénztár (POS) jegyzéket létrehozni.
author: rubencdelgado
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailTerminalTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2ac5135d0606ffc9816c841637aa032826f87e28
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022783"
---
# <a name="create-and-associate-registers"></a><span data-ttu-id="6e7c4-103"> Pénztárgépek létrehozása és hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="6e7c4-103">Create and associate registers</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="6e7c4-104">Ez az eljárás azt mutatja be, hogy hogyan lehet pénztár (POS) jegyzéket létrehozni.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-104">This procedure demonstrates how to create a point of sale (POS) register.</span></span> <span data-ttu-id="6e7c4-105">Ez az eljárás az USRT bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-105">This procedure uses the demo data company USRT.</span></span>

1. <span data-ttu-id="6e7c4-106">Ugorjon a Kiskereskedelem és kereskedelem > Csatorna beállítás > Pénztár beállítás > Pénztárgépek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-106">Go to Retail and commerce > Channel setup > POS setup > Registers.</span></span>
2. <span data-ttu-id="6e7c4-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-107">Click New.</span></span>
3. <span data-ttu-id="6e7c4-108">Adjon meg egy azonosítót az új jegyzékre vonatkozóan a Pénztárgép száma mezőben.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-108">In the Register number field, type an ID for the new register.</span></span>
    * <span data-ttu-id="6e7c4-109">A regisztrációs azonosító általában tartalmazza azokat a kódokat, amelyek segítik a pénztárgép az üzlethez és az üzleten belüli helyéhez történő hozzárendelését, amelyhez tartozik.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-109">The register ID typically includes codes that help map the register to the store to which it belongs, and the location within the store.</span></span>  
4. <span data-ttu-id="6e7c4-110">Írjon be egy jól felismerhető nevet a Név mezőbe a pénztárhoz.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-110">In the Name field, type a descriptive name for the register..</span></span>
5. <span data-ttu-id="6e7c4-111">Az Üzlet száma mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-111">In the Store number field, enter or select a value.</span></span>
6. <span data-ttu-id="6e7c4-112">A Hardverprofil mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-112">In the Hardware profile field, enter or select a value.</span></span>
    * <span data-ttu-id="6e7c4-113">A hardverprofilok segítségével meghatározhatja azokat a kiskereskedelmi perifériás eszközöket, amelyek olyan pénztárhoz vannak csatlakoztatva, mint például a pénztárfiók és a nyugtanyomtató.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-113">Hardware profiles are used to specify the retail peripherals that will be connected to the register, such as cash drawer and receipt printer.</span></span>  
7. <span data-ttu-id="6e7c4-114">A Vizuális profil mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-114">In the Visual profile field, enter or select a value.</span></span>
    * <span data-ttu-id="6e7c4-115">A vizuális profilok segítségével adhatja meg a POS háttérben látható képeket, a bejelentkezési oldalt, illetve a POS-nál használt témákat.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-115">Visual profiles are used to specify the images used in the POS background and login page as well as themes for the POS.</span></span>  
8. <span data-ttu-id="6e7c4-116">Írjon be egy értéket az EFT POS pénztárgép száma mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-116">In the EFT POS register number field, type a value.</span></span>
    * <span data-ttu-id="6e7c4-117">Az EFT POS pénztárgép száma arra szolgál, hogy tájékoztassa a fizetés feldolgozóját arról, hogy melyik fizetési terminál küld engedélyezésre vonatkozó kéréseket.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-117">The EFT POS register number is used to inform the payment processor which payment terminal is sending authorization requests.</span></span> <span data-ttu-id="6e7c4-118">Ezt az értéket gyakran a „Terminál azonosítója” vagy „TID” néven nevezik.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-118">This value is often called the "Terminal ID" or “TID”.</span></span> <span data-ttu-id="6e7c4-119">A TID általában a fizetésre szolgáló eszközön lévő címkén található.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-119">The TID can generally be found on a sticker on the payment device.</span></span>  
9. <span data-ttu-id="6e7c4-120">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-120">Click Save.</span></span>


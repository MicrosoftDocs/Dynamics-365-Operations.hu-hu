---
title: "Termelések kimeneti helye"
description: "Ez a témakör leírja a hierarchiát, amely azonosítja a termelés kimeneti helyét."
author: johanhoffmann
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: e53c8e96579dba3b47bef0c00e55b8fa786fc55c
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---

# <a name="production-output-location"></a><span data-ttu-id="00d22-103">Termelések kimeneti helye</span><span class="sxs-lookup"><span data-stu-id="00d22-103">Production output location</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="00d22-104">Ez a témakör leírja a hierarchiát, amely azonosítja a termelés kimeneti helyét.</span><span class="sxs-lookup"><span data-stu-id="00d22-104">This topic describes the hierarchy that is used to identify the production output location.</span></span>

<span data-ttu-id="00d22-105">A termelés kimeneti helye az a hely, ahol a készterméket először tárolják az előállítását követően.</span><span class="sxs-lookup"><span data-stu-id="00d22-105">The production output location is the location where a finished good is first stored after it's produced.</span></span> <span data-ttu-id="00d22-106">Általában ez a hely közel van a termelési folyamathoz, amely előállítja a készterméket.</span><span class="sxs-lookup"><span data-stu-id="00d22-106">Usually, this location is close to the production process that produces the finished good.</span></span> <span data-ttu-id="00d22-107">A termelés kimeneti helyét köztes raktárként használja a rendszer az anyag számára, mielőtt az a szállítási területre, raktárba, illetve termelési bemeneti helyre kerülne egy folytatólagos termelési folyamathoz stb.</span><span class="sxs-lookup"><span data-stu-id="00d22-107">The production output location is used as intermediate storage for the material before it's moved on to the shipment area, a storage location, a production input location for a downstream production process, and so on.</span></span> 

<span data-ttu-id="00d22-108">Alapértelmezett termelési kimeneti hely van beállítva olyankor, amikor a készrermékeket jelentik egy termelési rendelésben vagy kötegrendelésben.</span><span class="sxs-lookup"><span data-stu-id="00d22-108">A default production output location is set when finished goods are reported on a production order or batch order.</span></span> <span data-ttu-id="00d22-109">Az alábbi hierarchia a kimeneti hely azonosítására szolgál:</span><span class="sxs-lookup"><span data-stu-id="00d22-109">The following hierarchy is used to identify this output location:</span></span>

1. <span data-ttu-id="00d22-110">A termelési rendelés vagy a kötegrendelés fejlécében megadott kimeneti helyet használja.</span><span class="sxs-lookup"><span data-stu-id="00d22-110">Use the output location that is defined on the production order or batch order header.</span></span>
2. <span data-ttu-id="00d22-111">Ha ott nem található hely, használja azt a kimeneti helyet, amelyet annál az erőforrásnál határozott meg, amelyet az utolsó olyan művelet vett igénybe, amelyiket a termelési útvonalban határoztak meg.</span><span class="sxs-lookup"><span data-stu-id="00d22-111">If no location is found there, use the output location that is defined on the resource that is used by the last operation that is defined in the production route.</span></span>
3. <span data-ttu-id="00d22-112">Ha ott nem található hely, használja azt a kimeneti helyet, amelyet annál az erőforráscsoportnál határozott meg, amelyet az utolsó olyan művelet erőforrása vett igénybe, amelyiket a termelési útvonalban határoztak meg.</span><span class="sxs-lookup"><span data-stu-id="00d22-112">If no location is found there, use the output location that is defined on the resource group that is used by the resource for the last operation that is defined in the production route.</span></span>
4. <span data-ttu-id="00d22-113">Ha ott nem található hely, használja azt a kimeneti helyet, amelyet annál a raktárnál adtak meg, amely a termelési rendelésnél lett meghatározva.</span><span class="sxs-lookup"><span data-stu-id="00d22-113">If no location is found there, use the output location that is defined on the warehouse that is defined for the production order.</span></span>

<span data-ttu-id="00d22-114">Alapértelmezett termelési kimeneti hely csak olyan termékeknél van beállítva, amelyeket speciális raktárkezelési folyamatok segítségével állítottak be.</span><span class="sxs-lookup"><span data-stu-id="00d22-114">A default production output location is set only for products that are set up by using advanced warehouse processes.</span></span> <span data-ttu-id="00d22-115">Ha ilyen típusú cikkek készként vannak jelentve, a **Késztermékek betárolása** vagy a **Társtermék és melléktermék betárolása** raktározási feladata jön létre.</span><span class="sxs-lookup"><span data-stu-id="00d22-115">When this type of item is reported as finished, warehouse work of the **Finished goods put away** or **Co-product and by-product put away** type is created.</span></span> <span data-ttu-id="00d22-116">Az ilyen típusú munka a termelés kimeneti helyét használja kitárolási helyként.</span><span class="sxs-lookup"><span data-stu-id="00d22-116">This type of work uses the production output location as the pick location.</span></span> <span data-ttu-id="00d22-117">A betárolási helyet a helyutasítások határozzák meg.</span><span class="sxs-lookup"><span data-stu-id="00d22-117">The put-away location is determined by the location directives.</span></span>


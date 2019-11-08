---
title: Mobil vonalkód-támogatás
description: Ez a témakör azt mutatja be, hogyan kezelje a raktári mobil beolvasási alkalmazást Android-kompatibilis eszközökön.
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BarcodeSetup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: Mirzaab
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3f4f61da42e02bfbf648bd5f6f5fe60c97abf532
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/03/2019
ms.locfileid: "2552186"
---
# <a name="mobile-barcode-support"></a><span data-ttu-id="35688-103">Mobil vonalkód-támogatás</span><span class="sxs-lookup"><span data-stu-id="35688-103">Mobile barcode support</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="35688-104">Mivel az Android nyílt forrású projekt, minden raktári vonalkódbeolvasó-hardvert gyártó cég készíthet olyan eszközöket, amelyek az Android operációs rendszert futtatják.</span><span class="sxs-lookup"><span data-stu-id="35688-104">Because Android is an open source project, any manufacturer of hardware for warehouse bar code scanners can build a device to run the Android operating system.</span></span> <span data-ttu-id="35688-105">Egy eszköz csak akkor Android-kompatibilis, ha képes az Android végrehajtási környezethez írt alkalmazások futtatására.</span><span class="sxs-lookup"><span data-stu-id="35688-105">A device is only Android-compatible if it can run apps that are written for the Android execution environment.</span></span>
<span data-ttu-id="35688-106">Azonban a hardverszállító létrehozhat és módosíthat felületeket a hardverén futó Android verzióhoz.</span><span class="sxs-lookup"><span data-stu-id="35688-106">However, a hardware vendor can modify and create overlays for the Android version that runs on their hardware.</span></span> <span data-ttu-id="35688-107">A Microsoft nem vállal semmilyen felelősséget sem azért, hogy az Android rendszerre tervezett mobil vonalkódolvasó alkalmazás kompatibilis a gyártó vonalkód-beolvasási hardvereszközével, valamint a rajta futó Android verzióval.</span><span class="sxs-lookup"><span data-stu-id="35688-107">Microsoft cannot take any responsibility to ensure that a mobile bar code scanning app for Android is compatible with a manufacturer’s bar code scanning hardware and the Android version that runs on it.</span></span> 

<span data-ttu-id="35688-108">A Dynamics 365 Supply Chain Management Raktárkezelés alkalmazását több Android alapú eszközzel teszteltek a vonalkódok beolvasására.</span><span class="sxs-lookup"><span data-stu-id="35688-108">The Dynamics 365 Supply Chain Management - Warehousing app has been tested with a selection of Android powered devices for bar code scanning.</span></span> <span data-ttu-id="35688-109">A tesztek csak a piacon elérhető eszközök egy részét fedték le.</span><span class="sxs-lookup"><span data-stu-id="35688-109">These tests only cover a sample of the devices that are available on the market.</span></span>

<span data-ttu-id="35688-110">Vevőként ajánlott a raktári mobil beolvasási alkalmazás tesztelése a kijelölt hardveren, mielőtt döntene a megvásárolni kívánt hardverről.</span><span class="sxs-lookup"><span data-stu-id="35688-110">As a customer, we recommend that you test the Warehouse mobile scanning app on selected hardware before you decide on the hardware that you want to buy.</span></span>


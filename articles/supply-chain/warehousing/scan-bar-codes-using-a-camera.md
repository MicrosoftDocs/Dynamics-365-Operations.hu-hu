---
title: "Vonalkódok beolvasása kamerával a Dynamics 365 for Finance and Operations szolgáltatásban – Raktárkezelés"
description: "Ez a témakör bemutatja, hogy miként állítható be a Dynamics 365 for Finance and Operations – Raktárkezelés arra, hogy vonalkódokat olvasson be egy mobileszköz kamerájának használatához."
author: MarkusFogelberg
manager: AnnBe
ms.date: 01/03/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 2f71c15dfe066359ff189ae00a52a87a5ec661f5
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---

# <a name="scan-bar-codes-using-a-camera-in-dynamics-365-for-finance-and-operations--warehousing"></a><span data-ttu-id="f6228-103">Vonalkódok beolvasása kamerával a Dynamics 365 for Finance and Operations szolgáltatásban – Raktárkezelés</span><span class="sxs-lookup"><span data-stu-id="f6228-103">Scan bar codes using a camera in Dynamics 365 for Finance and Operations – Warehousing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f6228-104">Ez a témakör bemutatja, hogy miként állítható be a Dynamics 365 for Finance and Operations – Raktárkezelés arra, hogy vonalkódokat olvasson be egy mobileszköz kamerájának használatához.</span><span class="sxs-lookup"><span data-stu-id="f6228-104">This topic explains how to set up Dynamics 365 for Finance and Operations – Warehousing to scan bar codes using a camera on a mobile device.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="f6228-105">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="f6228-105">Prerequisites</span></span>
<span data-ttu-id="f6228-106">A funkció használatához a Raktárkezelés 1.2.0.0-s verziójának kell telepítve lennie, és eszközén lennie kell kamerának.</span><span class="sxs-lookup"><span data-stu-id="f6228-106">To use this feature, you need to have version 1.2.0.0 of Warehousing installed, and your device must have a camera.</span></span> <span data-ttu-id="f6228-107">Ha megnyitja az alkalmazást a frissítést követően, akkor a rendszer felajánlja az engedélyezést a Dynamics 365 for Finance and Operations – Raktárkezelés alkalmazás számára a kamera használatára.</span><span class="sxs-lookup"><span data-stu-id="f6228-107">When you open the app after updating, you will be prompted to allow the Dynamics 365 for Finance and Operations – Warehousing application to use the camera.</span></span> <span data-ttu-id="f6228-108">Ha az eszközön nincs kamera, akkor nem jelenik meg a felajánlás, és akkor nem tud kamerát használni a beolvasásra.</span><span class="sxs-lookup"><span data-stu-id="f6228-108">If your device doesn’t have a camera, no prompt will be shown, and you will not be able to use a camera as a scanner.</span></span> 

## <a name="setup"></a><span data-ttu-id="f6228-109">Beállítás</span><span class="sxs-lookup"><span data-stu-id="f6228-109">Setup</span></span>
<span data-ttu-id="f6228-110">A Raktárkezelés alkalmazás Megjelenítési beállítások szakaszában kiválaszthatja, hogy a kamerát szeretné-e használni a vonalkódok beolvasására.</span><span class="sxs-lookup"><span data-stu-id="f6228-110">In the Display settings of the Warehousing application, you can select if the camera should be used for bar code scanning.</span></span> <span data-ttu-id="f6228-111">Ha engedélyezi a **Kamera használata beolvasásra** lehetőséget, akkor használhatja a kamerát mindegyik olyan beviteli mezőn, amelynél az előnyben részesített beviteli mód a **Beolvasás**.</span><span class="sxs-lookup"><span data-stu-id="f6228-111">If you enable **Use the camera as scanner**, you can use the camera on every input field that has the preferred input mode set to **Scanning**.</span></span> 

<span data-ttu-id="f6228-112">Annak irányításához, hogy egy beviteli mező beolvasható legyen-e, a Dynamics 365 for Finance and Operations **A raktári alkalmazáson belüli mezőnevek** lapján állítsa a **Preferált beviteli mód** beállítást **Beolvasás** értékre.</span><span class="sxs-lookup"><span data-stu-id="f6228-112">To control whether an input field should be scannable, on the **Warehouse app field names** page in Dynamics 365 for Finance and Operations, set **Preferred input mode** to **Scanning**.</span></span> <span data-ttu-id="f6228-113">Ha ez a beállítás van kijelölve, egy kamera használható beolvasásra a Raktárkezelés alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="f6228-113">When this option is selected, a camera can be used for scanning in the Warehousing app.</span></span> <span data-ttu-id="f6228-114">Ha információt szeretne arról, hogy miként konfigurálhatók az alkalmazásmezőnevek a Raktárkezelésnél, lásd a következőt: [A Warehousing alkalmazás alkalmazás-mezőneveinek konfigurálása](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).</span><span class="sxs-lookup"><span data-stu-id="f6228-114">For information about how to configure app field names in Warehousing, see [Configure app field names in Warehousing app](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).</span></span>

## <a name="supported-bar-code-formats"></a><span data-ttu-id="f6228-115">Támogatott vonalkódformátumok</span><span class="sxs-lookup"><span data-stu-id="f6228-115">Supported bar code formats</span></span>
<span data-ttu-id="f6228-116">A leggyakoribb vonalkódformátumok támogatottak, beleértve a következőket: Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A és QR-kódok.</span><span class="sxs-lookup"><span data-stu-id="f6228-116">The most common bar code formats are supported, including Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A, and QR codes.</span></span> 

## <a name="navigation"></a><span data-ttu-id="f6228-117">Navigáció</span><span class="sxs-lookup"><span data-stu-id="f6228-117">Navigation</span></span>
<span data-ttu-id="f6228-118">A kamera lap minden olyan oldalnál elindul, ahol a beviteli mezőnél a preferált beviteli mód a Beolvasás, amikor a Kamera oldalon a következő lehetőségek közül választhat:</span><span class="sxs-lookup"><span data-stu-id="f6228-118">The camera page will be initiated on each page where the input field has the preferred input mode set to Scanning, when you are on the Camera page use the following options to navigate:</span></span>
- <span data-ttu-id="f6228-119">Kattintson a Vissza gombra a Feladatok és részletes adatok oldalára való visszatéréshez.</span><span class="sxs-lookup"><span data-stu-id="f6228-119">Click the back button to go back to the Task and details page.</span></span> 
- <span data-ttu-id="f6228-120">Kattintson a ceruza ikonra a Feladatok és részletes adatok oldalán, hogy arra a lapra juthasson, ahol az értéket manuálisan adhatja meg.</span><span class="sxs-lookup"><span data-stu-id="f6228-120">Click the pencil on the Task and details page to go to the page where you can type input manually.</span></span>
- <span data-ttu-id="f6228-121">Kattintson a kamerára a Feladatok és részletes adatok oldalán a Kamera lapra való visszatéréshez.</span><span class="sxs-lookup"><span data-stu-id="f6228-121">Click the camera on the Task and details page to go back to the Camera page.</span></span> 

| <span data-ttu-id="f6228-122">Feladatok és részletes adatok oldala</span><span class="sxs-lookup"><span data-stu-id="f6228-122">Task and details page</span></span> | <span data-ttu-id="f6228-123">Kamera lap</span><span class="sxs-lookup"><span data-stu-id="f6228-123">Camera page</span></span> | 
| :---------------------: | :--------------------: |
| ![camera-scanning-example-task-detail-page](./media/camera-scanning-example-task-detail-page50.png)          | ![camera-scanning-example-camera-page-smaller](./media/camera-scanning-example-camera-page50.png)          |

<span data-ttu-id="f6228-126">Ha a kamera lapján a Kamera gombra kattint, akkor az kiszürkítve jelenik meg, amikor megpróbál azonosítani egy vonalkódot.</span><span class="sxs-lookup"><span data-stu-id="f6228-126">On the camera page, when you click the Camera button, it will appear dimmed while trying to identify a bar code.</span></span> <span data-ttu-id="f6228-127">Ha a vonalkód azonosítása nem történik meg 5 másodpercen belül, akkor a folyamat időkorlátja lejár, és a Kamera gomb ismét elérhető lesz.</span><span class="sxs-lookup"><span data-stu-id="f6228-127">If a bar code is not identified within 5 seconds, the process will time out and the Camera button will become available again.</span></span> <span data-ttu-id="f6228-128">Ezután ismét megpróbálja beolvasni a vonalkódot.</span><span class="sxs-lookup"><span data-stu-id="f6228-128">You will then be able to try to scan a bar code again.</span></span>

<span data-ttu-id="f6228-129">Amikor a kamerával egy vonalkódra céloz, tartsa a vonalkódot egy vonalban a keretekkel a legjobb eredmény elérése érdekében.</span><span class="sxs-lookup"><span data-stu-id="f6228-129">When you aim the camera at a bar code, keep the bar code aligned within the brackets for best result.</span></span> <span data-ttu-id="f6228-130">Amikor megtörténik egy vonalkód sikeres beolvasása, megtörténik a folyamat feldolgozása, és Ön a következő lépéshez jut.</span><span class="sxs-lookup"><span data-stu-id="f6228-130">When a bar code is scanned successfully, the result will be processed, and you will be taken to the next step.</span></span> <span data-ttu-id="f6228-131">Ha a következő lépés egy másik beviteli mezőt tartalmaz, és a preferált beviteli mód a Beolvasás, akkor újraindul a kamera lapja.</span><span class="sxs-lookup"><span data-stu-id="f6228-131">If the next step contains another input field with the preferred input mode set to Scanning, the camera page will start again.</span></span> <span data-ttu-id="f6228-132">Ha a következő lépésként nem egy beolvasási mező jelenik meg, akkor nem indul el a kamera lap.</span><span class="sxs-lookup"><span data-stu-id="f6228-132">If the next step is not a scanning field, then the camera page will not be initiated.</span></span>



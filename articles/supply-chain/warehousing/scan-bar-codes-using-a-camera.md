---
title: Vonalkódok beolvasása a Raktárkezelés mobilalkalmazás kamerája segítségével
description: Ez a témakör bemutatja, hogy miként állítható be a Raktárkezelés mobilalkalmazás arra, hogy vonalkódokat olvasson be egy mobileszköz kamerájának használatához.
author: MarkusFogelberg
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 2f61f9c45b95b730a7f1743963658ec00abfbb56
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831218"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-management-mobile-app"></a><span data-ttu-id="727f2-103">Vonalkódok beolvasása a Raktárkezelés mobilalkalmazás kamerája segítségével</span><span class="sxs-lookup"><span data-stu-id="727f2-103">Scan bar codes using a camera in the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="727f2-104">Ez a témakör bemutatja, hogy miként állítható be a Raktárkezelés mobilalkalmazás arra, hogy vonalkódokat olvasson be egy mobileszköz kamerájának használatához.</span><span class="sxs-lookup"><span data-stu-id="727f2-104">This topic explains how to set up the Warehouse Management mobile app to scan bar codes using a camera on a mobile device.</span></span>

## <a name="setup"></a><span data-ttu-id="727f2-105">Beállítás</span><span class="sxs-lookup"><span data-stu-id="727f2-105">Setup</span></span>

<span data-ttu-id="727f2-106">A Raktárkezelés mobilalkalmazás Megjelenítési beállítások szakaszában kiválaszthatja, hogy a kamerát szeretné-e használni a vonalkódok beolvasására.</span><span class="sxs-lookup"><span data-stu-id="727f2-106">In the display settings of the Warehouse Management mobile app, you can select if the camera should be used for bar code scanning.</span></span> <span data-ttu-id="727f2-107">Ha engedélyezi a **Kamera használata beolvasásra** lehetőséget, akkor használhatja a kamerát mindegyik olyan beviteli mezőn, amelynél az előnyben részesített beviteli mód a **Beolvasás**.</span><span class="sxs-lookup"><span data-stu-id="727f2-107">If you enable **Use the camera as scanner**, you can use the camera on every input field that has the preferred input mode set to **Scanning**.</span></span>

<span data-ttu-id="727f2-108">Annak irányításához, hogy egy beviteli mező beolvasható legyen-e, **A raktári alkalmazáson belüli mezőnevek** lapján állítsa a **Preferált beviteli mód** beállítást **Beolvasás** értékre.</span><span class="sxs-lookup"><span data-stu-id="727f2-108">To control whether an input field should be scannable, on the **Warehouse app field names** page, set **Preferred input mode** to **Scanning**.</span></span> <span data-ttu-id="727f2-109">Ha ez a beállítás van kijelölve, egy kamera használható beolvasásra a Raktárkezelés mobilalkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="727f2-109">When this option is selected, a camera can be used for scanning in the Warehouse Management mobile app.</span></span> <span data-ttu-id="727f2-110">ovábbi információ: [A Raktárkezelés mobilalkalmazás mezőinek konfigurálása](configure-app-field-names-priorities-warehouse.md).</span><span class="sxs-lookup"><span data-stu-id="727f2-110">For more information, see [Configure fields for the Warehouse Management mobile app](configure-app-field-names-priorities-warehouse.md).</span></span>

## <a name="supported-bar-code-formats"></a><span data-ttu-id="727f2-111">Támogatott vonalkódformátumok</span><span class="sxs-lookup"><span data-stu-id="727f2-111">Supported bar code formats</span></span>

<span data-ttu-id="727f2-112">A leggyakoribb vonalkódformátumok támogatottak, beleértve a következőket: Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A és QR-kódok.</span><span class="sxs-lookup"><span data-stu-id="727f2-112">The most common bar code formats are supported, including Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A, and QR codes.</span></span>

## <a name="navigation"></a><span data-ttu-id="727f2-113">Navigáció</span><span class="sxs-lookup"><span data-stu-id="727f2-113">Navigation</span></span>

<span data-ttu-id="727f2-114">A kamera lap minden olyan oldalnál elindul, ahol a beviteli mezőnél a **Preferált beviteli mód** értéke a *Beolvasás*, amikor a Kamera oldalon a következő lehetőségek közül választhat:</span><span class="sxs-lookup"><span data-stu-id="727f2-114">The camera page will be initiated on each page where the input field has its **Preferred input mode** set to *Scanning*, when you are on the camera page use the following options to navigate:</span></span>

- <span data-ttu-id="727f2-115">Válassza a Vissza gombot a **Feladatok és részletes adatok** oldalára való visszatéréshez.</span><span class="sxs-lookup"><span data-stu-id="727f2-115">Select the back button to go back to the **Task and details** page.</span></span>
- <span data-ttu-id="727f2-116">Válassza a ceruza ikont a **Feladatok és részletes adatok** oldalán, hogy arra a lapra juthasson, ahol az értéket manuálisan adhatja meg.</span><span class="sxs-lookup"><span data-stu-id="727f2-116">Select the pencil on the **Task and details** page to go to the page where you can type input manually.</span></span>
- <span data-ttu-id="727f2-117">Válassza ki a kamerát a **Feladatok és részletes adatok** oldalán a Kamera lapra való visszatéréshez.</span><span class="sxs-lookup"><span data-stu-id="727f2-117">Select the camera on the **Task and details** page to go back to the camera page.</span></span>

<span data-ttu-id="727f2-118">Ha a kamera lapján a Kamera gombot választják, akkor az kiszürkítve jelenik meg, amikor megpróbál azonosítani egy vonalkódot.</span><span class="sxs-lookup"><span data-stu-id="727f2-118">On the camera page, when you select the camera button, it will appear dimmed while trying to identify a bar code.</span></span> <span data-ttu-id="727f2-119">Ha a vonalkód azonosítása nem történik meg 5 másodpercen belül, akkor a folyamat időkorlátja lejár, és a Kamera gomb ismét elérhető lesz.</span><span class="sxs-lookup"><span data-stu-id="727f2-119">If a bar code is not identified within 5 seconds, the process will time out and the camera button will become available again.</span></span> <span data-ttu-id="727f2-120">Ezután ismét megpróbálja beolvasni a vonalkódot.</span><span class="sxs-lookup"><span data-stu-id="727f2-120">You will then be able to try to scan a bar code again.</span></span>

<span data-ttu-id="727f2-121">Amikor a kamerával egy vonalkódra céloz, tartsa a vonalkódot egy vonalban a keretekkel a legjobb eredmény elérése érdekében.</span><span class="sxs-lookup"><span data-stu-id="727f2-121">When you aim the camera at a bar code, keep the bar code aligned within the brackets for best result.</span></span> <span data-ttu-id="727f2-122">Amikor megtörténik egy vonalkód sikeres beolvasása, megtörténik a folyamat feldolgozása, és Ön a következő lépéshez jut.</span><span class="sxs-lookup"><span data-stu-id="727f2-122">When a bar code is scanned successfully, the result will be processed, and you will be taken to the next step.</span></span> <span data-ttu-id="727f2-123">Ha a következő lépés egy másik beviteli mezőt tartalmaz, és a preferált beviteli mód a Beolvasás, akkor újraindul a kamera lapja.</span><span class="sxs-lookup"><span data-stu-id="727f2-123">If the next step contains another input field with the preferred input mode set to Scanning, the camera page will start again.</span></span> <span data-ttu-id="727f2-124">Ha a következő lépésként nem egy beolvasási mező jelenik meg, akkor nem indul el a kamera lap.</span><span class="sxs-lookup"><span data-stu-id="727f2-124">If the next step is not a scanning field, then the camera page will not be initiated.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
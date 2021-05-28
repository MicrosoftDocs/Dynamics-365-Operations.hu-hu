---
title: Hibaelhárítás – Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújtanak a Microsoft Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz alkalmazással kapcsolatos problémák esetén.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 707efeba9553b996e4e33a4754e42a9d22643e33
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019589"
---
# <a name="troubleshoot-dynamics-365-payment-connector-for-adyen-issues"></a><span data-ttu-id="c9a54-103">Hibaelhárítás – Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz</span><span class="sxs-lookup"><span data-stu-id="c9a54-103">Troubleshoot Dynamics 365 Payment Connector for Adyen issues</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c9a54-104">Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújtanak a Microsoft Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz alkalmazással kapcsolatos problémák esetén.</span><span class="sxs-lookup"><span data-stu-id="c9a54-104">This topic provides troubleshooting guidance that can help you get support when you have issues with the Microsoft Dynamics 365 Payment Connector for Adyen.</span></span>

## <a name="description"></a><span data-ttu-id="c9a54-105">Leírás</span><span class="sxs-lookup"><span data-stu-id="c9a54-105">Description</span></span>

<span data-ttu-id="c9a54-106">A következő területeken problémák vannak a Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz termékkel, és az Adyen csapat segítségére van szüksége:</span><span class="sxs-lookup"><span data-stu-id="c9a54-106">You have issues with the Dynamics 365 Payment Connector for Adyen in the following areas, and you require support from the Adyen team:</span></span>

- <span data-ttu-id="c9a54-107">A pénztár (POS), a modern pénztár (MPOS), a hívásközpont vagy a Dynamics 365 Commerce konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c9a54-107">Configuration of Point of sale (POS), Modern point of sale (MPOS), call center, or Dynamics 365 Commerce</span></span>
- <span data-ttu-id="c9a54-108">Az Adyen fizetési szolgáltató (PSP) hivatkozási száma (például ha kérdései vannak az elutasításokkal kapcsolatban, ideértve a manuális kulcsbevitel \[MKE\]-elutasításokat)</span><span class="sxs-lookup"><span data-stu-id="c9a54-108">The Adyen payment service provider (PSP) reference number (for example, if you have questions about refusals, including manual key entry \[MKE\] refusals)</span></span>
- <span data-ttu-id="c9a54-109">Bármi, ami nem működik teszt- vagy élő kereskedői környezetben</span><span class="sxs-lookup"><span data-stu-id="c9a54-109">Anything that isn't working in test or live merchant environments</span></span>

## <a name="resolution"></a><span data-ttu-id="c9a54-110">Felbontás</span><span class="sxs-lookup"><span data-stu-id="c9a54-110">Resolution</span></span>

<span data-ttu-id="c9a54-111">A következő e-mail-sablon használatával elindíthatja a támogatási folyamatot az Adyen csapatával.</span><span class="sxs-lookup"><span data-stu-id="c9a54-111">Use the following email template to start the support process with the Adyen team.</span></span> <span data-ttu-id="c9a54-112">A hibaelhárítás felgyorsítása érdekében győződjön meg arról, hogy az e-mail-cím tartalmazza az összes szükséges adatot.</span><span class="sxs-lookup"><span data-stu-id="c9a54-112">To expedite troubleshooting, make sure that the email contains all the required details.</span></span>

| <span data-ttu-id="c9a54-113">Mező</span><span class="sxs-lookup"><span data-stu-id="c9a54-113">Field</span></span>        | <span data-ttu-id="c9a54-114">Érték</span><span class="sxs-lookup"><span data-stu-id="c9a54-114">Value</span></span> |
|--------------|-------|
| <span data-ttu-id="c9a54-115">Záró időpont</span><span class="sxs-lookup"><span data-stu-id="c9a54-115">To</span></span>           | `support@adyen.com` |
| <span data-ttu-id="c9a54-116">Másolatot kap</span><span class="sxs-lookup"><span data-stu-id="c9a54-116">Cc</span></span>           | |
| <span data-ttu-id="c9a54-117">Tárgysor</span><span class="sxs-lookup"><span data-stu-id="c9a54-117">Subject line</span></span> | <span data-ttu-id="c9a54-118">Microsoft Dynamics támogatási kérés</span><span class="sxs-lookup"><span data-stu-id="c9a54-118">Microsoft Dynamics Support Request</span></span> |
| <span data-ttu-id="c9a54-119">Törzs</span><span class="sxs-lookup"><span data-stu-id="c9a54-119">Body</span></span>         | <p><span data-ttu-id="c9a54-120">Tisztelt ügyféltámogatási szolgálat!</span><span class="sxs-lookup"><span data-stu-id="c9a54-120">Hi Support,</span></span></p><p><span data-ttu-id="c9a54-121">Támogatásra van szükségem a következő probléma megoldásában:</span><span class="sxs-lookup"><span data-stu-id="c9a54-121">Please provide support for the following issue:</span></span></p><ul><li><span data-ttu-id="c9a54-122">Kereskedői számla</span><span class="sxs-lookup"><span data-stu-id="c9a54-122">Merchant account</span></span></li><li><span data-ttu-id="c9a54-123">Környezet (teszt/éles)</span><span class="sxs-lookup"><span data-stu-id="c9a54-123">Environment (Test/Prod)</span></span></li><li><span data-ttu-id="c9a54-124">Csatorna (POS/hívásközpont/Commerce e-kereskedelem)</span><span class="sxs-lookup"><span data-stu-id="c9a54-124">Channel (POS/call center/Commerce e-commerce)</span></span></li><li><span data-ttu-id="c9a54-125">Fizetési szolgáltató hivatkozási száma, ha a probléma egy konkrét tranzakciót érint (a fizetési szolgáltató hivatkozási számát a nyugtán, az Adyen vevőterületen vagy a pénztárterminál tranzakciókat tartalmazó menüjében találja.)</span><span class="sxs-lookup"><span data-stu-id="c9a54-125">PSP reference number, if the issue involved a specific transaction (You can find the PSP reference number on the receipt, in the Adyen Customer Area, or on the transactions menu on the POS terminal.)</span></span></li><li><span data-ttu-id="c9a54-126">Képernyőkép vagy fénykép a hibaüzenetről, ha van ilyen</span><span class="sxs-lookup"><span data-stu-id="c9a54-126">Screenshot or photo of the error message, if applicable</span></span></li><li><span data-ttu-id="c9a54-127">Eseménynaplók (.txt formátumban)</span><span class="sxs-lookup"><span data-stu-id="c9a54-127">Event Viewer logs (in .txt format)</span></span></li><li><span data-ttu-id="c9a54-128">A hibe leírása és az Ön által megpróbált és hibaelhárítási lépések bemutatása</span><span class="sxs-lookup"><span data-stu-id="c9a54-128">Description of the issue and troubleshooting steps that you've tried</span></span></li></ul> |

## <a name="additional-resources"></a><span data-ttu-id="c9a54-129">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c9a54-129">Additional resources</span></span>

[<span data-ttu-id="c9a54-130">Kifizetések elfogadása a Dynamics 365 Commerce Adyen összekötőjével</span><span class="sxs-lookup"><span data-stu-id="c9a54-130">Accept payments with the Adyen connector for Dynamics 365 Commerce</span></span>](https://www.adyen.com/partners/dynamics-365-commerce)

[<span data-ttu-id="c9a54-131">Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz</span><span class="sxs-lookup"><span data-stu-id="c9a54-131">Dynamics 365 Payment Connector for Adyen</span></span>](../dev-itpro/adyen-connector.md)

[<span data-ttu-id="c9a54-132">Adyen fizetési összekötő a Dynamics 365 szolgáltatáshoz</span><span class="sxs-lookup"><span data-stu-id="c9a54-132">Set up the Adyen payment connector for Dynamics 365</span></span>](https://docs.adyen.com/plugins/microsoft-dynamics)

---
title: QR-kód vagy vonalkód hozzáadása tranzakciós és bevételezési e-mailekhez
description: Ez a témakör bemutatja, hogy hogyan lehet a rendelési azonosítókat képviselő QR-kódokat és vonalkódokat beszúrni a tranzakciós és bevételezési e-mailekbe a Microsoft Dynamics 365 Commerce rendszerben.
author: bicyclingfool
manager: annbe
ms.date: 03/04/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Commerce, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-02-16
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 3cc4fcb1237f8409a89b3d4818c132c60c57b5a0
ms.sourcegitcommit: 88babb2fffe97e93bbde543633fc492120f2a4fc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/06/2021
ms.locfileid: "5555422"
---
# <a name="add-a-qr-code-or-bar-code-to-transactional-and-receipt-emails"></a><span data-ttu-id="1a65f-103">QR-kód vagy vonalkód hozzáadása tranzakciós és bevételezési e-mailekhez</span><span class="sxs-lookup"><span data-stu-id="1a65f-103">Add a QR code or bar code to transactional and receipt emails</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="1a65f-104">Ez a témakör bemutatja, hogy hogyan lehet a rendelési azonosítókat képviselő QR-kódokat és vonalkódokat beszúrni a tranzakciós és bevételezési e-mailekbe a Microsoft Dynamics 365 Commerce rendszerben.</span><span class="sxs-lookup"><span data-stu-id="1a65f-104">This topic explains how to insert QR codes and bar codes that represent order IDs into transactional and receipt emails in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="1a65f-105">A QR-kódok és vonalkódok könnyen beemelhetők a tranzakciós e-mailekbe, hogy felgyorsítsák a rendeléskeresési folyamatot kiskereskedelmi környezetben.</span><span class="sxs-lookup"><span data-stu-id="1a65f-105">You can easily include QR codes and bar codes in transactional emails to help speed up the order lookup process in a retail environment.</span></span> <span data-ttu-id="1a65f-106">A QR-kódok és vonalkódok e-mailbe történő beszúrása során egy HTML **\<img\>** címkét kell használni, amely egy generáló és renderelő szolgáltatástól QR-kódot vagy vonalkódképet kér.</span><span class="sxs-lookup"><span data-stu-id="1a65f-106">To insert QR codes and bar codes into emails, you use an HTML **\<img\>** tag that requests a QR code or bar code image from a generation and rendering service.</span></span> <span data-ttu-id="1a65f-107">A Microsoft nem biztosítja ezt a szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="1a65f-107">Microsoft doesn't provide this service.</span></span> <span data-ttu-id="1a65f-108">Vannak azonban olyan ingyenes vagy olyan szolgáltatások, amelyek kiszolgálnak olyan QR-kódokat vagy vonalkódokat, amelyek dinamikusan, lekérdezési sztringben átadott érték alapján jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="1a65f-108">However, there are many free or inexpensive services that can serve QR codes or bar codes that are dynamically generated based on a value that is passed in a query string.</span></span>

## <a name="add-a-qr-code-or-bar-code-to-a-transactional-email"></a><span data-ttu-id="1a65f-109">QR-kód vagy vonalkód hozzáadása tranzakciós e-mailhez</span><span class="sxs-lookup"><span data-stu-id="1a65f-109">Add a QR code or bar code to a transactional email</span></span>

<span data-ttu-id="1a65f-110">Ha egy e-kereskedelmi beszerzés részeként küldött tranzakciós e-mailbe QR-kódot vagy vonalkódot szeretne beilleszteni, kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1a65f-110">To insert a QR code or bar code into a transactional email that is sent as part of an e-commerce purchase, follow these steps.</span></span>

1. <span data-ttu-id="1a65f-111">Nyissa meg a tranzakciós e-mail-sablon forrás HTML-jét, és adjon hozzá egy HTML **\<img\>** címkét, amely a QR-kód- vagy a vonalkód-szolgáltatásra mutat.</span><span class="sxs-lookup"><span data-stu-id="1a65f-111">Open the source HTML for the transactional email template, and add an HTML **\<img\>** tag that points to your QR code or bar code service.</span></span> <span data-ttu-id="1a65f-112">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="1a65f-112">Here is an example.</span></span>

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%salesid%&param1=value1&param2=value2" alt="%salesid%" />
    ```

    <span data-ttu-id="1a65f-113">Itt látható az előző példa magyarázata:</span><span class="sxs-lookup"><span data-stu-id="1a65f-113">Here is an explanation of the preceding example:</span></span>

    - <span data-ttu-id="1a65f-114">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE**: a QR-kód- vagy vonalkódszolgáltatás tartománya.</span><span class="sxs-lookup"><span data-stu-id="1a65f-114">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** represents the domain of your QR code or bar code service.</span></span>
    - <span data-ttu-id="1a65f-115">**data**: az a paraméter, amelyet a QR-kód- vagy a vonalkód-szolgáltatás használ a QR-kódként vagy vonalkódként renderelni kívánt tartalom fogadására.</span><span class="sxs-lookup"><span data-stu-id="1a65f-115">**data** represents the parameter that the QR code or bar code service uses to receive the content that should be rendered as a QR code or bar code.</span></span>

        <span data-ttu-id="1a65f-116">A **%salesid%** értéket hozzá kell rendelni ehhez a paraméterhez.</span><span class="sxs-lookup"><span data-stu-id="1a65f-116">The value **%salesid%** must be assigned to this parameter.</span></span> <span data-ttu-id="1a65f-117">Ebben a példában figyelje meg, hogy a rendszer az értéket a kép helyettesítő szövegeként is használja.</span><span class="sxs-lookup"><span data-stu-id="1a65f-117">In this example, notice that the value is also used as alt text for the image.</span></span>

    - <span data-ttu-id="1a65f-118">**param1** és **param2**: további, nem kötelező paraméterek.</span><span class="sxs-lookup"><span data-stu-id="1a65f-118">**param1** and **param2** represent additional optional parameters.</span></span>

1. <span data-ttu-id="1a65f-119">Menjen a **Retail és Commerce \> Központ beállítása \> Paraméterek \> Szervezeti e-mail-sablonok** pontra, és töltse fel a frissített HTML-kódot a megfelelő tranzakciós e-mail-sablonba.</span><span class="sxs-lookup"><span data-stu-id="1a65f-119">Go to **Retail and Commerce \> Headquarters setup \> Parameters \> Organization email templates**, and upload the updated HTML to the appropriate transactional email template.</span></span>

> [!NOTE]
> <span data-ttu-id="1a65f-120">A paraméterek eltérhetnek a QR-kód- és vonalkód-szolgáltatók függvényében.</span><span class="sxs-lookup"><span data-stu-id="1a65f-120">Parameters might differ among QR code and bar code service providers.</span></span> <span data-ttu-id="1a65f-121">Ezért mindenképpen forduljon a szolgáltatóhoz, és erősítse meg a paramétereket, amelyekhez értékeket kell rendelnie.</span><span class="sxs-lookup"><span data-stu-id="1a65f-121">Therefore, be sure to contact your service provider to confirm the parameters that you must assign values to.</span></span>

## <a name="add-a-qr-code-or-bar-code-to-a-receipt-email"></a><span data-ttu-id="1a65f-122">QR-kód vagy vonalkód hozzáadása bevételezési e-mailhez</span><span class="sxs-lookup"><span data-stu-id="1a65f-122">Add a QR code or bar code to a receipt email</span></span> 

<span data-ttu-id="1a65f-123">Ha egy QR-kódot vagy vonalkódot szeretne beilleszteni a pénztárnál (POS) történő vásárlás után elküldendő bevételezési e-mailbe, kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1a65f-123">To insert a QR code or bar code into a receipt email that can be sent after a purchase is made at the point of sale (POS), follow these steps.</span></span>

1. <span data-ttu-id="1a65f-124">Nyissa meg a bevételezési e-mail-sablon forrás HTML-jét, és adjon hozzá egy HTML **\<img\>** címkét, amely a QR-kód- vagy a vonalkód-szolgáltatásra mutat.</span><span class="sxs-lookup"><span data-stu-id="1a65f-124">Open the source HTML for the receipt email template, and add an HTML **\<img\>** tag that points to your QR code or bar code service.</span></span> <span data-ttu-id="1a65f-125">Alább látható egy példa.</span><span class="sxs-lookup"><span data-stu-id="1a65f-125">Here is an example below.</span></span>

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%receiptid%&param1=value1&param2=value2" alt="%receiptid%" />
    ```

    <span data-ttu-id="1a65f-126">Itt látható az előző példa magyarázata:</span><span class="sxs-lookup"><span data-stu-id="1a65f-126">Here is an explanation of the preceding example:</span></span>

    - <span data-ttu-id="1a65f-127">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE**: a QR-kód- vagy vonalkódszolgáltatás tartománya.</span><span class="sxs-lookup"><span data-stu-id="1a65f-127">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** represents the domain of your QR code or bar code service.</span></span>
    - <span data-ttu-id="1a65f-128">**data**: az a paraméter, amelyet a QR-kód- vagy a vonalkód-szolgáltatás használ a QR-kódként vagy vonalkódként renderelni kívánt tartalom fogadására.</span><span class="sxs-lookup"><span data-stu-id="1a65f-128">**data** represents the parameter that the QR code or bar code service uses to receive the content that should be rendered as a QR code or bar code.</span></span>

        <span data-ttu-id="1a65f-129">A **%receiptid%** értéket hozzá kell rendelni ehhez a paraméterhez.</span><span class="sxs-lookup"><span data-stu-id="1a65f-129">The value **%receiptid%** must be assigned to this parameter.</span></span> <span data-ttu-id="1a65f-130">Ebben a példában figyelje meg, hogy a rendszer az értéket a kép helyettesítő szövegeként is használja.</span><span class="sxs-lookup"><span data-stu-id="1a65f-130">In this example, notice that the value is also used as alt text for the image.</span></span>

    - <span data-ttu-id="1a65f-131">**param1** és **param2**: további, nem kötelező paraméterek.</span><span class="sxs-lookup"><span data-stu-id="1a65f-131">**param1** and **param2** represent additional optional parameters.</span></span>

1. <span data-ttu-id="1a65f-132">Menjen a **Retail és Commerce \> Központ beállítása \> Paraméterek \> Szervezeti e-mail-sablonok** pontra, és töltse fel a frissített HTML-kódot abba az e-mail-sablonba, amelynek e-mail-azonosítója: **emailrecpt**.</span><span class="sxs-lookup"><span data-stu-id="1a65f-132">Go to **Retail and Commerce \> Headquarters setup \> Parameters \> Organization email templates**, and upload the updated HTML to the email template that has the email ID **emailrecpt**.</span></span>

> [!NOTE]
> <span data-ttu-id="1a65f-133">A paraméterek eltérhetnek a QR-kód- és vonalkód-szolgáltatók függvényében.</span><span class="sxs-lookup"><span data-stu-id="1a65f-133">Parameters might differ among QR code and bar code service providers.</span></span> <span data-ttu-id="1a65f-134">Ezért mindenképpen forduljon a szolgáltatóhoz, és erősítse meg a paramétereket, amelyekhez értékeket kell rendelnie.</span><span class="sxs-lookup"><span data-stu-id="1a65f-134">Therefore, be sure to contact your service provider to confirm the parameters that you must assign values to.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1a65f-135">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="1a65f-135">Additional resources</span></span>

[<span data-ttu-id="1a65f-136">E-mailes nyugták küldése Modern POS (MPOS) szolgáltatásból</span><span class="sxs-lookup"><span data-stu-id="1a65f-136">Send email receipts from Modern POS (MPOS)</span></span>](email-receipts.md)

[<span data-ttu-id="1a65f-137">E-mail-sablonok létrehozása tranzakciós eseményekhez</span><span class="sxs-lookup"><span data-stu-id="1a65f-137">Create email templates for transactional events</span></span>](email-templates-transactions.md)

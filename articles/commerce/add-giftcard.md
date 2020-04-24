---
title: Ajándékutalvány-modul
description: Ez a témakör az ajándékutalvány-modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 70047376cec44523cc9cfe4df792bde23c776d8c
ms.sourcegitcommit: ac966ea3a6c557fb5f9634b187b0e788d3e82d4d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261571"
---
# <a name="gift-card-module"></a><span data-ttu-id="5c717-103">Ajándékutalvány-modul</span><span class="sxs-lookup"><span data-stu-id="5c717-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5c717-104">Ez a témakör az ajándékutalvány-modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="5c717-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="5c717-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="5c717-105">Overview</span></span>

<span data-ttu-id="5c717-106">Az ajándékutalvány egy gyakori fizetési mód, és az ajándékutalvány modul használható a pénztár modulban az ajándékutalványok elfogadására.</span><span class="sxs-lookup"><span data-stu-id="5c717-106">Gift cards are a common form of payment, and the gift card module can be used in a checkout module to accept gift cards.</span></span> <span data-ttu-id="5c717-107">Az ajándékutalvány modul támogatja a Dynamics 365, SVS és a Givex ajándékutalványokat.</span><span class="sxs-lookup"><span data-stu-id="5c717-107">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="5c717-108">A SVS és a Givex ajándékutalványok a Adyen fizetési szolgáltatón keresztül válthatók be.</span><span class="sxs-lookup"><span data-stu-id="5c717-108">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span>

<span data-ttu-id="5c717-109">A külső ajándékutalványok (például SVS és Givex) támogatásával kapcsolatos további tudnivalókat lásd: [Támogatás a külső ajándékutalványokhoz](./dev-itpro/gift-card.md)</span><span class="sxs-lookup"><span data-stu-id="5c717-109">For more information on support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md)</span></span>

## <a name="module-properties"></a><span data-ttu-id="5c717-110">Modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="5c717-110">Module properties</span></span>

- <span data-ttu-id="5c717-111">**További mezők megjelenítése** – Ez a tulajdonság határozza meg, hogy milyen mezőket kell megjeleníteni az ajándékutalványokhozaz ajándékutalvány számán túl, amely alapértelmezés szerint mindig látható.</span><span class="sxs-lookup"><span data-stu-id="5c717-111">**Show additional fields** - This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="5c717-112">Például egyes ajándékutalványok támogatják a személyes azonosítószám (PIN-kód) megjelenítését, mások a PIN-kód és a lejárati dátum megjelenítését.</span><span class="sxs-lookup"><span data-stu-id="5c717-112">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="5c717-113">Másik lehetőségként a tulajdonság értéke „Nincs” lehet, amely csak az ajándékutalvány számát jeleníti meg, és további mezőket nem.</span><span class="sxs-lookup"><span data-stu-id="5c717-113">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="5c717-114">Támogatott értékek:</span><span class="sxs-lookup"><span data-stu-id="5c717-114">Supported values:</span></span>
-   <span data-ttu-id="5c717-115">PIN-kód</span><span class="sxs-lookup"><span data-stu-id="5c717-115">PIN</span></span>
-   <span data-ttu-id="5c717-116">Lejárat dátuma</span><span class="sxs-lookup"><span data-stu-id="5c717-116">Expiration date</span></span>
-   <span data-ttu-id="5c717-117">PIN és lejárati dátum</span><span class="sxs-lookup"><span data-stu-id="5c717-117">PIN and expiration date</span></span> 
-   <span data-ttu-id="5c717-118">None</span><span class="sxs-lookup"><span data-stu-id="5c717-118">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="5c717-119">Ajándékutalvány-modulok webhely-beállításai</span><span class="sxs-lookup"><span data-stu-id="5c717-119">Site settings for gift card modules</span></span>

<span data-ttu-id="5c717-120">A Commerce webhelykészítő **Webhelybeállítások \> Bővítmények** területén van egy ajándékutalvány-modul, amelynek neve **Támogatott ajándékutalvány-típus**.</span><span class="sxs-lookup"><span data-stu-id="5c717-120">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="5c717-121">Ez a beállítás három értéket támogat:</span><span class="sxs-lookup"><span data-stu-id="5c717-121">This setting supports three values:</span></span>
- <span data-ttu-id="5c717-122">**Dynamics 365 ajándékutalvány** – Ha ezt a beállítást alkalmazza, akkor az ajándékutalvány modul csak a Dynamics 365 utalványok beváltását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="5c717-122">**Dynamics 365 gift card** - When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="5c717-123">Ez a beállítás csak az e-Commerce webhely bejelentkezett felhasználóinak esetében támogatott.</span><span class="sxs-lookup"><span data-stu-id="5c717-123">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="5c717-124">**SVS és Givex ajándékutalványok** – Ha ezt a beállítást alkalmazza, akkor az ajándékutalvány modul csak a Givex és SVS utalványok beváltását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="5c717-124">**SVS and Givex gift cards** - When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="5c717-125">Ez a beállítás az e-Commerce webhely bejelentkezett és névtelen felhasználói esetében támogatott.</span><span class="sxs-lookup"><span data-stu-id="5c717-125">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="5c717-126">**Dynamics 365, SVS és Givex ajándékutalványok** – Ha ezt a beállítást alkalmazza, akkor az ajándékutalvány modul a Dynamics 365, Givex és SVS utalványok beváltását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="5c717-126">**Dynamics 365, SVS, and Givex gift cards** - When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="5c717-127">Ez a beállítás csak az e-Commerce webhely bejelentkezett felhasználóinak esetében támogatott.</span><span class="sxs-lookup"><span data-stu-id="5c717-127">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="5c717-128">Ajándékutalvány-modul felvétele egy oldalra</span><span class="sxs-lookup"><span data-stu-id="5c717-128">Add a gift card module to a page</span></span>

<span data-ttu-id="5c717-129">Az ajándékutalvány-modulnak a pénztár lapra történő hozzáadásával és a szükséges tulajdonságok beállításával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Fizetésmodul](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="5c717-129">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5c717-130">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="5c717-130">Additional resources</span></span>

[<span data-ttu-id="5c717-131">Kezdő csomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="5c717-131">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="5c717-132">Fizetésmodul</span><span class="sxs-lookup"><span data-stu-id="5c717-132">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="5c717-133">Támogatás külső ajándékutalványokhoz</span><span class="sxs-lookup"><span data-stu-id="5c717-133">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)

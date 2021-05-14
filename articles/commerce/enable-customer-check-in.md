---
title: Vevői bejelentkezéssel kapcsolatos értesítések engedélyezése a pénztárnál (POS)
description: Ez a témakör azt ismerteti, hogyan lehet engedélyezni a Microsoft Dynamics 365 Commerce pénztár (POS) szolgáltatásban engedélyezni a vevői bejelentkezéssel kapcsolatos értesítéseket.
author: bicyclingfool
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: e4defc15d9ef198a361934d51e31016747dbb5ab
ms.sourcegitcommit: 593438a145672c55ff6a910eabce2939300b40ad
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2021
ms.locfileid: "5937588"
---
# <a name="enable-customer-check-in-notifications-in-point-of-sale-pos"></a><span data-ttu-id="c6e38-103">Vevői bejelentkezéssel kapcsolatos értesítések engedélyezése a pénztárnál (POS)</span><span class="sxs-lookup"><span data-stu-id="c6e38-103">Enable customer check-in notifications in point of sale (POS)</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="c6e38-104">Ez a témakör azt ismerteti, hogyan lehet engedélyezni a Microsoft Dynamics 365 Commerce pénztár (POS) szolgáltatásban engedélyezni a vevői bejelentkezéssel kapcsolatos értesítéseket.</span><span class="sxs-lookup"><span data-stu-id="c6e38-104">This topic describes how to enable customer check-in notifications in Microsoft Dynamics 365 Commerce point of sale (POS).</span></span>

<span data-ttu-id="c6e38-105">A szervezet a „rendelés készen áll a felvételre” e-mailjeiben egy hivatkozást vagy gombot biztosít, hogy a vevők értesítsék az üzletet arról, hogy a létesítményben vannak, és arra várnak, hogy kihozzák hozzájuk a csomagjukat.</span><span class="sxs-lookup"><span data-stu-id="c6e38-105">In their "order ready for pickup" emails, organizations can provide a link or button that lets customers notify the store that they are on the premises and waiting for their package to be brought out to them.</span></span> <span data-ttu-id="c6e38-106">A vevők ezt követően megerősítést kapnak a bejelentkezésükről, és az üzlet értesítést kap a pénztár alkalmazásában.</span><span class="sxs-lookup"><span data-stu-id="c6e38-106">Customers then receive a check-in confirmation, and the store receives a notification as a task in its POS application.</span></span> <span data-ttu-id="c6e38-107">Ez a feladat arra kéri az értékesítési munkatársat, hogy a rendelést kivigye a vevő járművéhez.</span><span class="sxs-lookup"><span data-stu-id="c6e38-107">This task serves as a prompt for a sales associate to deliver the order to the customer's vehicle.</span></span> <span data-ttu-id="c6e38-108">A vevőnek tehát nem kell bemennie az üzletbe.</span><span class="sxs-lookup"><span data-stu-id="c6e38-108">Therefore, the customer doesn't have to enter the store.</span></span>

<span data-ttu-id="c6e38-109">A vevői bejelentkezés munkafolyamata a vevőkkel kapcsolatos további adatok gyűjtésére is beállítható – például a parkolási hely száma, a jármű márkája, modellje, színe, illetve a szállítási utasítások.</span><span class="sxs-lookup"><span data-stu-id="c6e38-109">The customer check-in workflow can also be configured to collect additional information from customers, such as their parking spot number, the make, model, and color of their vehicle, and delivery instructions.</span></span> <span data-ttu-id="c6e38-110">A kiskereskedelmi üzlet munkatársa ezt az információt a rendelés teljesítésének megkönnyítése érdekében felhasználhatja.</span><span class="sxs-lookup"><span data-stu-id="c6e38-110">The retail store attendant can use this information to facilitate order fulfillment.</span></span>

## <a name="enable-customer-check-in"></a><span data-ttu-id="c6e38-111">Vevői bejelentkezés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="c6e38-111">Enable customer check-in</span></span>

<span data-ttu-id="c6e38-112">Ha be van kapcsolva a vevői bejelentkezés funkció, a Commerce létrehoz egy rendelésvisszaigazolási azonosítót (más néven csatornahivatkozási azonosítót).</span><span class="sxs-lookup"><span data-stu-id="c6e38-112">When the customer check-in feature is turned on, Commerce generates an order confirmation ID (also known as the channel reference ID).</span></span> <span data-ttu-id="c6e38-113">Rendelés-visszaigazolási azonosítókat is létrehoz a pénztári (POS) csatornákon vagy hívásközponti csatornákon keresztül létrehozott rendelésekhez.</span><span class="sxs-lookup"><span data-stu-id="c6e38-113">It also generates order confirmation IDs for orders that are created through point of sale (POS) or call center channels.</span></span> 

<span data-ttu-id="c6e38-114">A vevői bejelentkezés funkciónak a Commerce központi felületén történő bekapcsolásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c6e38-114">To turn on the customer check-in feature in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="c6e38-115">Menjen a **Munkaterületek \> Funkciókezelés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c6e38-115">Go to **Workspaces \> Feature management**.</span></span>
2. <span data-ttu-id="c6e38-116">Keresse meg a **Konzisztens csatornahivatkozási azonosító formátum létrehozása a csatornák között** funkciót.</span><span class="sxs-lookup"><span data-stu-id="c6e38-116">Search for the **Generate a consistent channel reference ID format across channels** feature.</span></span> 
3. <span data-ttu-id="c6e38-117">Válassza ki a funkciót, majd a tulajdonsások ablaktáblán válassza az **Engedélyezés most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c6e38-117">Select the feature, and then select **Enable now** in the properties pane.</span></span> 

## <a name="create-a-check-in-confirmation-page"></a><span data-ttu-id="c6e38-118">Bejelentkezést megerősítő oldal létrehozása</span><span class="sxs-lookup"><span data-stu-id="c6e38-118">Create a check-in confirmation page</span></span>

<span data-ttu-id="c6e38-119">Az e-kereskedelmi webhelyen létre kell hoznia egy új oldalt, amely a bejelentkezés megerősítésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="c6e38-119">On your e-commerce site, you must create a new page that will serve as the check-in confirmation experience.</span></span> <span data-ttu-id="c6e38-120">A további konfigurációkon keresztül a lap egy olyan képernyőt is tartalmazhat, amely további adatokat gyűjt a vevőktől, hogy megkönnyítse a rendelés teljesítését.</span><span class="sxs-lookup"><span data-stu-id="c6e38-120">Through additional configuration, the page can also include a form that collects additional information from customers to facilitate order fulfillment.</span></span> <span data-ttu-id="c6e38-121">Az oldal és a modul beállításával kapcsolatos további információért lásd: [Vevői bejelentkezés modul](check-in-pickup-module.md).</span><span class="sxs-lookup"><span data-stu-id="c6e38-121">For information about how to set up the page and module, see [Customer check-in module](check-in-pickup-module.md).</span></span>

## <a name="configure-the-transactional-email-template"></a><span data-ttu-id="c6e38-122">A tranzakciós e-mail-sablon konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c6e38-122">Configure the transactional email template</span></span>

<span data-ttu-id="c6e38-123">Ahhoz a tranzakciós e-mail-sablonhoz, amit a vevők akkor kapnak, amikor a rendelésük készen áll a felvételre, egy **Itt vagyok** hivatkozást vagy gombot kell hozzáadnia.</span><span class="sxs-lookup"><span data-stu-id="c6e38-123">You must add an **I am here** link or button to the template for the transactional email that customers receive when their order is ready for pickup.</span></span> <span data-ttu-id="c6e38-124">A vevők ezzel a hivatkozással vagy gombbal értesítik az üzletet, hogy megérkeztek, és felveszik a rendelésüket.</span><span class="sxs-lookup"><span data-stu-id="c6e38-124">Customers will use this link or button to notify the store that they have arrived to pick up their order.</span></span> 

<span data-ttu-id="c6e38-125">A **Csomagolás befejezve** értesítési típushoz lekérdezett sablonhoz kapcsolható hivatkozás vagy gomb, valamint a határidős rendelés teljesítéséhez használt szállítási mód hozzáadása.</span><span class="sxs-lookup"><span data-stu-id="c6e38-125">Add the link or button to the template that is mapped to the **Packing completed** notification type and the mode of delivery that you're using for curbside order fulfillment.</span></span> <span data-ttu-id="c6e38-126">A sablonban hozzon létre egy HTML-hivatkozást vagy gombot, amely a létrehozott bejelentkezést megerősítő lap URL-címére mutat.</span><span class="sxs-lookup"><span data-stu-id="c6e38-126">In the template, create an HTML link or button that points to the URL of the check-in confirmation page that you created.</span></span> <span data-ttu-id="c6e38-127">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="c6e38-127">Here is an example.</span></span>

```
<a href="https://[YOUR_SITE_DOMAIN]/[CHECK-IN_CONFIRMATION_PAGE]?channelReferenceId=%channelreferenceid%&channelId=%channelid%&packingSlipId=%packingslipid%" target="_blank">I am here!</a>
```
<span data-ttu-id="c6e38-128">Az e-mail-sablonok konfigurálási módjával kapcsolatos további információért lásd: [Tranzakciós e-mailek testreszabása kézbesítési mód szerint](customize-email-delivery-mode.md).</span><span class="sxs-lookup"><span data-stu-id="c6e38-128">For more information about how to configure email templates, see [Customize transactional emails by mode of delivery](customize-email-delivery-mode.md).</span></span> 

## <a name="a-check-in-confirmation-task-is-created-in-pos"></a><span data-ttu-id="c6e38-129">A pénztárban létrejön egy bejelentkezést megerősítő feladat</span><span class="sxs-lookup"><span data-stu-id="c6e38-129">A check-in confirmation task is created in POS</span></span>

<span data-ttu-id="c6e38-130">Miután a vevő értesíti az üzletet, hogy megérkezett a rendelésfelvételre, megerősítést kap a bejelentkezésről, és a pénztárfeladatok listájában létrejön egy feladat azon üzlet számára, ahol a vevő felveszi a rendelést.</span><span class="sxs-lookup"><span data-stu-id="c6e38-130">After a customer notifies the store that they are present for pickup, they receive a check-in confirmation notification, and a task is created in the tasks list in POS for the store where the customer is picking up the order.</span></span> <span data-ttu-id="c6e38-131">A feladat a rendelés teljesítéséhez szükséges összes vevő- és rendelésinformációt tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="c6e38-131">The task contains all the customer and order information that is required to fulfill the order.</span></span> <span data-ttu-id="c6e38-132">A feladatban az utasítás mezőben látható minden olyan információ, amely a vevőtől a kiegészítő információs űrlapon keresztül lett összegyűjtve.</span><span class="sxs-lookup"><span data-stu-id="c6e38-132">In the task, the instructions field shows any information that was collected from the customer through the additional information form.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="c6e38-133">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c6e38-133">Additional resources</span></span>

[<span data-ttu-id="c6e38-134">Bejelentkezés az átvételi modulba</span><span class="sxs-lookup"><span data-stu-id="c6e38-134">Check-in for pickup module</span></span>](check-in-pickup-module.md)

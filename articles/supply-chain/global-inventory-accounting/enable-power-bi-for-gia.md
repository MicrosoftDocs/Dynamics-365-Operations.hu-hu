---
title: Válassza a Globális Inventory Accounting Power BI-t
description: Ez a témakör azt ismerteti, hogyan lehet engedélyezni a Global Inventory Accounting Microsoft Power BI-t.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d7979ed18b98ee6133774cd91bc866d6fca92d5f
ms.sourcegitcommit: eceae470f4ae58000ec33fea34db34b7a7a1af43
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/18/2021
ms.locfileid: "6273167"
---
# <a name="enable-power-bi-for-global-inventory-accounting"></a><span data-ttu-id="df469-103">Válassza a Globális Inventory Accounting Power BI-t</span><span class="sxs-lookup"><span data-stu-id="df469-103">Enable Power BI for Global Inventory Accounting</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="df469-104">Csempéket, irányítópultokat és jelentéseket rögzíthet [a PowerBI.com](https://powerbi.com/) fiókjából a Microsoft Dynamics 365 alkalmazás munkaterületére.</span><span class="sxs-lookup"><span data-stu-id="df469-104">You can pin tiles, dashboards, and reports from your [PowerBI.com](https://powerbi.com/) account to your Microsoft Dynamics 365 application workspace.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="df469-105">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="df469-105">Prerequisites</span></span>

<span data-ttu-id="df469-106">A Power BI jelentés engedélyezéséhez a következő előfeltételeknek kell lenniük:</span><span class="sxs-lookup"><span data-stu-id="df469-106">The following prerequisites must be in place before you can enable Power BI reporting:</span></span>

- <span data-ttu-id="df469-107">Rendszergazdaként kell részt vennie a Dynamics 365 alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="df469-107">You must be a system administrator in the Dynamics 365 application.</span></span>
- <span data-ttu-id="df469-108">Rendelkeznie kell [egy PowerBI.com](https://powerbi.com/) számlával.</span><span class="sxs-lookup"><span data-stu-id="df469-108">You must have a [PowerBI.com](https://powerbi.com/) account.</span></span>
- <span data-ttu-id="df469-109">Legalább egy irányítópultnak és egy jelentésnek kell lennie a Power BI fiókjában.</span><span class="sxs-lookup"><span data-stu-id="df469-109">You must have at least one dashboard and one report in your Power BI account.</span></span>
- <span data-ttu-id="df469-110">Rendszergazdaként kell rendelkeznie a Azure Active Directory (Azure AD) fiókjához.</span><span class="sxs-lookup"><span data-stu-id="df469-110">You must be an administrator for your Azure Active Directory (Azure AD) account.</span></span>
- <span data-ttu-id="df469-111">A Azure AD tartománynak ugyanazzal a tartománysal kell rendelkeznie, amelyet a [PowerBI.com](https://powerbi.com/) fiókjához használt.</span><span class="sxs-lookup"><span data-stu-id="df469-111">The Azure AD domain must be the same domain that you used for your [PowerBI.com](https://powerbi.com/) account.</span></span>

## <a name="setup"></a><span data-ttu-id="df469-112">Beállítás</span><span class="sxs-lookup"><span data-stu-id="df469-112">Setup</span></span>

<span data-ttu-id="df469-113">A Power BI integráció beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="df469-113">To set up the Power BI integration, follow these steps.</span></span>

1. <span data-ttu-id="df469-114">Jelentkezzen be a [Microsoft Dynamics LifeCycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="df469-114">Sign in to [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span></span>
1. <span data-ttu-id="df469-115">Lépjen a **Megosztott eszközkönyvtárba**, válassza ki a **Power BI jelentésmodellt** eszköztípusként, és töltse le a **Global Inventory Accounting** csomagot.</span><span class="sxs-lookup"><span data-stu-id="df469-115">Go to **Shared asset library**, select **Power BI report model** as the asset type, and download the **Global Inventory Accounting** package.</span></span> 
1. <span data-ttu-id="df469-116">Jelentkezzen be [a PowerBI.com](https://app.powerbi.com/), és töltse fel a **Global Inventory Accounting** számviteli jelentés Power BI fájlját az alábbi lépésekben:</span><span class="sxs-lookup"><span data-stu-id="df469-116">Sign in to [PowerBI.com](https://app.powerbi.com/), and upload the **Global Inventory Accounting** Power BI report file by following these steps:</span></span>

    1. <span data-ttu-id="df469-117">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="df469-117">Select **New**.</span></span>
    1. <span data-ttu-id="df469-118">Válassza a **Fájl feltöltése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="df469-118">Select **Upload a file**.</span></span>
    1. <span data-ttu-id="df469-119">Válassza ki a **Global Inventory Accounting** Power BI jelentésfájlt.</span><span class="sxs-lookup"><span data-stu-id="df469-119">Select the **Global Inventory Accounting** Power BI report file.</span></span>

1. <span data-ttu-id="df469-120">Konfigurálja a **Global Inventory Accounting** Power BI jelentést az alábbi lépésekkel:</span><span class="sxs-lookup"><span data-stu-id="df469-120">Configure the **Global Inventory Accounting** Power BI report by following these steps:</span></span>

    1. <span data-ttu-id="df469-121">Lépjen a **Saját** munkaterületre, keresse meg a Global Inventory Accounting adatkészletét, majd a **Beállítások** menü **Beállítások** parancsát válassza.</span><span class="sxs-lookup"><span data-stu-id="df469-121">Go to **My workspace**, find the dataset for Global Inventory Accounting, and then, on the **Options** menu, select **Settings**.</span></span>
    1. <span data-ttu-id="df469-122">A **Global inventory accounting** beállításai csoportban bővítse a **paramétereket**, és szükség szerint frissítse az összes paramétert.</span><span class="sxs-lookup"><span data-stu-id="df469-122">In **Settings for Global inventory accounting**, expand **Parameters**, and update all parameters as required.</span></span>

1. <span data-ttu-id="df469-123">Regisztrálja az alkalmazást a [Konfigurálás PowerBI.com](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md#registration-process) szerint.</span><span class="sxs-lookup"><span data-stu-id="df469-123">Register the application as described in [Configure PowerBI.com integration](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md#registration-process).</span></span>
1. <span data-ttu-id="df469-124">Integrálja a **Global Inventory Accounting** Power BI jelentésfájlt a Dynamics 365 Supply Chain Management szolgáltatásra az alábbi lépésekkel:</span><span class="sxs-lookup"><span data-stu-id="df469-124">Integrate the **Global Inventory Accounting** Power BI report file into Dynamics 365 Supply Chain Management by following these steps:</span></span>

    1. <span data-ttu-id="df469-125">Lépjen a **Rendszerfelügyelet \> Beállítás \> PowerBI.com konfiguráció** elemre.</span><span class="sxs-lookup"><span data-stu-id="df469-125">Go to **System administration \> Setup \> PowerBI.com configuration**.</span></span>
    1. <span data-ttu-id="df469-126">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="df469-126">Select **Edit**.</span></span>
    1. <span data-ttu-id="df469-127">Válassza a **PowerBI.Com integráció** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="df469-127">Select **Enable PowerBI.Com integration**.</span></span>
    1. <span data-ttu-id="df469-128">Írja be az alkalmazásazonosítót az **Alkalmazás azonosítója** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="df469-128">In the **Application ID** field, enter the application ID.</span></span>
    1. <span data-ttu-id="df469-129">Írja be az alkalmazáskulcs az **Alkalmazás kulcsa** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="df469-129">In the **Application key** field, enter the application key.</span></span>
    1. <span data-ttu-id="df469-130">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="df469-130">Select **Save**.</span></span>

1. <span data-ttu-id="df469-131">Frissítse az oldalt úgy, hogy a Power BI bejelentkezési párbeszédpanel is megjelenik.</span><span class="sxs-lookup"><span data-stu-id="df469-131">Refresh the page so that the Power BI sign-in dialog box appears.</span></span>
1. <span data-ttu-id="df469-132">A **Beállítások** lapon válassza a **Jelentéskatalógus megnyitása** lehetőséget, majd válassza a korábban feltöltött **Global Inventory Accounting** Power BI jelentésfájlt.</span><span class="sxs-lookup"><span data-stu-id="df469-132">On the **Options** tab, select **Open report catalog**, and then select the **Global Inventory Accounting** Power BI report file that you uploaded earlier.</span></span>
1. <span data-ttu-id="df469-133">Frissítse a lapot..</span><span class="sxs-lookup"><span data-stu-id="df469-133">Refresh the page.</span></span> <span data-ttu-id="df469-134">Látnia kell, hogy a jelentés hozzá van adva.</span><span class="sxs-lookup"><span data-stu-id="df469-134">You should see that your report has been added.</span></span>
1. <span data-ttu-id="df469-135">Válassza ki a **Global Inventory Accounting** linket a **Power BI jelentések** alatt.</span><span class="sxs-lookup"><span data-stu-id="df469-135">Under **Power BI reports**, select the **Global Inventory Accounting** link.</span></span>

<span data-ttu-id="df469-136">További tudnivalókért lásd: [PowerBI.com-integráció konfigurálása](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md).</span><span class="sxs-lookup"><span data-stu-id="df469-136">For more information, see [Configure PowerBI.com integration](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md).</span></span>

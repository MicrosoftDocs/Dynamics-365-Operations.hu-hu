---
title: Azure Active Directory-hitelesítés engedélyezése a pénztári bejelentkezéshez
description: Ez a témakör azt mutatja be, hogyan lehet konfigurálni a Microsoft Dynamics 365 Commerce pénztár (POS) bejelentkezési élményét, hogy a Azure Active Directory-hitelesítést használja.
author: boycezhu
manager: annbe
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycezhu
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: 4f5a02348e8cef44424ae5d6a49de02d762ba245
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410035"
---
# <a name="enable-azure-active-directory-authentication-for-pos-sign-in"></a><span data-ttu-id="58b9f-103">Azure Active Directory-hitelesítés engedélyezése a pénztári bejelentkezéshez</span><span class="sxs-lookup"><span data-stu-id="58b9f-103">Enable Azure Active Directory authentication for POS sign-in</span></span>
[!include [banner](includes/banner.md)]


<span data-ttu-id="58b9f-104">A Microsoft Dynamics 365 Commerce szolgáltatást használó számos felhasználó szintén használ felhőalapú Microsoft szolgáltatásokat, és lehet, hogy Azure Active Directory (Azure AD) szolgáltatással kezelik az adott szolgáltatások felhasználói hitelesítő adatait.</span><span class="sxs-lookup"><span data-stu-id="58b9f-104">Many customers who use Microsoft Dynamics 365 Commerce also use other Microsoft cloud services, and they might use Azure Active Directory (Azure AD) to manage user credentials for those services.</span></span> <span data-ttu-id="58b9f-105">Ezekben az esetekben előfordulhat, hogy a vevők ugyanazt az Azure AD fiókot szeretnének használni több alkalmazásnál.</span><span class="sxs-lookup"><span data-stu-id="58b9f-105">In those cases, the customers might want to use the same Azure AD account across applications.</span></span> <span data-ttu-id="58b9f-106">Ez a témakör azt mutatja be, hogyan lehet konfigurálni a Commerce pénztár (POS) bejelentkezési élményét, hogy a Azure AD-hitelesítést használja.</span><span class="sxs-lookup"><span data-stu-id="58b9f-106">This topic explains how to configure the Commerce point of sale (POS) sign-in experience to use Azure AD authentication.</span></span>

## <a name="configure-azure-ad-authentication"></a><span data-ttu-id="58b9f-107">Azure AD-hitelesítés konfigurálása</span><span class="sxs-lookup"><span data-stu-id="58b9f-107">Configure Azure AD authentication</span></span>

<span data-ttu-id="58b9f-108">Ahhoz, hogy az Azure AD az üzlet pénztári bejelentkezésének hitelesítési módszere legyen, konfigurálnia kell az üzlet funkcióprofiljának beállításait, majd alkalmazni a beállítást a pénztárkliensre.</span><span class="sxs-lookup"><span data-stu-id="58b9f-108">To make Azure AD available as the authentication method for POS sign-in for a store, you must configure the settings of the store's functionality profile and then apply those setting to POS clients.</span></span>

<span data-ttu-id="58b9f-109">A funkcióprofil konfigurálásához az alábbi lépéseket hajtsa végre.</span><span class="sxs-lookup"><span data-stu-id="58b9f-109">To configure a functionality profile, follow these steps.</span></span>

1. <span data-ttu-id="58b9f-110">Ugorjon a következő elemre: **Retail és Commerce** \> **Csatorna beállítása** \> **Pénztárbeállítás** \> **Pénztárprofilok** \> **Funkcióprofilok**.</span><span class="sxs-lookup"><span data-stu-id="58b9f-110">Go to **Retail and Commerce** \> **Channel setup** \> **POS setup** \> **POS profiles** \> **Functionality profiles**.</span></span>
1. <span data-ttu-id="58b9f-111">Válassza ki a módosítani kívánt funkcióprofilt.</span><span class="sxs-lookup"><span data-stu-id="58b9f-111">Select the functionality profile to change.</span></span>
1. <span data-ttu-id="58b9f-112">A **Funkciók**gyorslapon, a **Pénztár személyzeti bejelentkezés** szakaszban módosítsa a **Bejelentkezés hitelesítési módja** mező értékét **Személyzeti aozonosító és jelszó** értékről **Azure Active Directory** értékre.</span><span class="sxs-lookup"><span data-stu-id="58b9f-112">On the **Functions** FastTab, in the **POS staff logon** section, change the value of the **Logon Authentication Method** field from **Personnel ID and Password** to **Azure Active Directory**.</span></span>

<span data-ttu-id="58b9f-113">Alapértelmezés szerint az összes funkcióprofil **személyzeti azonosítót és jelszót** használ a pénztár hitelesítési módszerként.</span><span class="sxs-lookup"><span data-stu-id="58b9f-113">By default, all functionality profiles use **Personnel ID and Password** as the POS authentication method.</span></span> <span data-ttu-id="58b9f-114">Ennek megfelelően módosítania kell **Bejelentkezés hitelesítési módja** mező értékét, ha Azure AD-t szeretne használni.</span><span class="sxs-lookup"><span data-stu-id="58b9f-114">Therefore, you must change the value of the **Logon Authentication Method** field if you want to use Azure AD.</span></span> <span data-ttu-id="58b9f-115">A módosítás hatással van minden olyan kiskereskedelmi üzletre, amely a kiválasztott funkcióprofilhoz van társítva.</span><span class="sxs-lookup"><span data-stu-id="58b9f-115">Every retail store that is linked to the selected functionality profile will be affected by this change.</span></span>

<span data-ttu-id="58b9f-116">A beállítások alkalmazásához a pénztárkliensre kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="58b9f-116">To apply the settings to POS clients, follow these steps.</span></span>

1. <span data-ttu-id="58b9f-117">Ugorjon a **Kiskereskedelem és kereskedelem** \> **Kiskereskedelem és kereskedelem informatika** \> **Elosztási ütemezés** pontra.</span><span class="sxs-lookup"><span data-stu-id="58b9f-117">Go to **Retail and Commerce** \> **Retail and Commerce IT** \> **Distribution schedule**.</span></span>
1. <span data-ttu-id="58b9f-118">Futtassa a **1070** (**Csatornakonfiguráció**) elosztási ütemezést.</span><span class="sxs-lookup"><span data-stu-id="58b9f-118">Run the **1070** (**Channel configuration**) distribution schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="58b9f-119">Azure AD-hitelesítéshez internetkapcsolat szükséges.</span><span class="sxs-lookup"><span data-stu-id="58b9f-119">Azure AD authentication requires an internet connection.</span></span> <span data-ttu-id="58b9f-120">Nem működik, ha a pénztár offline módban van.</span><span class="sxs-lookup"><span data-stu-id="58b9f-120">It won't work when POS is in offline mode.</span></span>
> 
> <span data-ttu-id="58b9f-121">Jelenleg a **Vezetői felülbírálás** funkció nem támogatja a Azure AD-t hitelesítési módszerként.</span><span class="sxs-lookup"><span data-stu-id="58b9f-121">Currently, the **Manager override** function doesn't support Azure AD as an authentication method.</span></span> <span data-ttu-id="58b9f-122">Még akkor is szükség van egy kezelői azonosítóra és jelszóra és jelszóra, ha a POS-bejelentkezés hitelesítési módszerének Azure AD van beállítva.</span><span class="sxs-lookup"><span data-stu-id="58b9f-122">An operator ID and password are required even if Azure AD is configured as the authentication method for POS sign-in.</span></span>

## <a name="associate-an-azure-ad-account-with-a-worker"></a><span data-ttu-id="58b9f-123">Azure AD-fiók társítása dolgozóval</span><span class="sxs-lookup"><span data-stu-id="58b9f-123">Associate an Azure AD account with a worker</span></span>

<span data-ttu-id="58b9f-124">Ahhoz, hogy egy üzlet dolgozója Azure AD-fiókkal jelentkezhessen be a pénztáralkalmazásba, az Azure AD-fiókot az adott dolgozóhoz kell társítani.</span><span class="sxs-lookup"><span data-stu-id="58b9f-124">Before a store worker can use an Azure AD account to sign in to the POS application, the Azure AD account must be associated with that worker.</span></span>

<span data-ttu-id="58b9f-125">Az Azure AD-fiók dolgozóhoz való társításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="58b9f-125">To associate an Azure AD account with a worker, follow these steps.</span></span>

1. <span data-ttu-id="58b9f-126">Nyissa meg a következőt: **Kiskereskedelem és kereskedelem** \> **Alkalmazottak** \> **Dolgozók**.</span><span class="sxs-lookup"><span data-stu-id="58b9f-126">Go to **Retail and Commerce** \> **Employees** \> **Workers**.</span></span>
1. <span data-ttu-id="58b9f-127">A dolgozó részletes lapjának megnyitása.</span><span class="sxs-lookup"><span data-stu-id="58b9f-127">Open the details page for a worker.</span></span>
1. <span data-ttu-id="58b9f-128">A műveleti ablaktáblán a **Kereskedelem** lapon a **Külső identitás** csoportban válassza a **Meglévő identitás társítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="58b9f-128">On the Action Pane, on the **Commerce** tab, in the **External identity** group, select **Associate existing identity**.</span></span>
1. <span data-ttu-id="58b9f-129">A **Meglévő külső identitás használata** párbeszédpanelen válassza a **Keresés e-maillel** parancsot, adja meg Azure AD-e-mail címet, majd válassza a **Keresés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="58b9f-129">In the **Use existing external identity** dialog box, select **Search using email**, enter an Azure AD email address, and then select **Search**.</span></span>
1. <span data-ttu-id="58b9f-130">Válassza ki a visszaadott Azure AD-fiókot, majd az **OK** elemet.</span><span class="sxs-lookup"><span data-stu-id="58b9f-130">Select the Azure AD account that is returned, and then select **OK**.</span></span>

<span data-ttu-id="58b9f-131">A rendszer kitölti az **Alias**, **UPN**, **Külső részazonosító** mezőket a dolgozó adatainak oldalának **Commerce** oldalán.</span><span class="sxs-lookup"><span data-stu-id="58b9f-131">The **Alias**, **UPN**, and **External sub identifier** fields on the **Commerce** tab of the worker's details page will be filled in.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="58b9f-132">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="58b9f-132">Additional resources</span></span>

[<span data-ttu-id="58b9f-133">Kiterjesztett bejelentkezési funkció beállítása az MPOS-hez és a felhőalapú pénztárhoz</span><span class="sxs-lookup"><span data-stu-id="58b9f-133">Set up extended logon functionality for MPOS and Cloud POS</span></span>](extended-logon.md)

[<span data-ttu-id="58b9f-134">Retail funkcióprofil létrehozása</span><span class="sxs-lookup"><span data-stu-id="58b9f-134">Create a retail functionality profile</span></span>](retail-functionality-profile.md)

[<span data-ttu-id="58b9f-135"> Dolgozó konfigurálása</span><span class="sxs-lookup"><span data-stu-id="58b9f-135">Configure a worker</span></span>](https://docs.microsoft.com/dynamics365/commerce/tasks/worker)

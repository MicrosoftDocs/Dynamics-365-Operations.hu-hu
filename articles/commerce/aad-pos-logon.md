---
title: Azure Active Directory-hitelesítés engedélyezése a pénztári bejelentkezéshez
description: Ez a témakör azt mutatja be, hogyan lehet konfigurálni a Microsoft Dynamics 365 Commerce pénztár (POS) bejelentkezési élményét, hogy az Azure Active Directory-hitelesítést használja.
author: boycezhu
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: 50088aee8c2474708682c9041251d2336e84d971
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796342"
---
# <a name="enable-azure-active-directory-authentication-for-pos-sign-in"></a><span data-ttu-id="50ff7-103">Azure Active Directory-hitelesítés engedélyezése a pénztári bejelentkezéshez</span><span class="sxs-lookup"><span data-stu-id="50ff7-103">Enable Azure Active Directory authentication for POS sign-in</span></span>
[!include [banner](includes/banner.md)]


<span data-ttu-id="50ff7-104">A Microsoft Dynamics 365 Commerce szolgáltatást használó számos felhasználó szintén használ felhőalapú Microsoft szolgáltatásokat, és lehet, hogy Azure Active Directory (Azure AD) szolgáltatással kezelik az adott szolgáltatások felhasználói hitelesítő adatait.</span><span class="sxs-lookup"><span data-stu-id="50ff7-104">Many customers who use Microsoft Dynamics 365 Commerce also use other Microsoft cloud services, and they might use Azure Active Directory (Azure AD) to manage user credentials for those services.</span></span> <span data-ttu-id="50ff7-105">Ezekben az esetekben előfordulhat, hogy a vevők ugyanazt az Azure AD fiókot szeretnének használni több alkalmazásnál.</span><span class="sxs-lookup"><span data-stu-id="50ff7-105">In those cases, the customers might want to use the same Azure AD account across applications.</span></span> <span data-ttu-id="50ff7-106">Ez a témakör azt mutatja be, hogyan lehet konfigurálni a Commerce pénztár (POS) bejelentkezési élményét, hogy a Azure AD-hitelesítést használja.</span><span class="sxs-lookup"><span data-stu-id="50ff7-106">This topic explains how to configure the Commerce point of sale (POS) sign-in experience to use Azure AD authentication.</span></span>

## <a name="configure-azure-ad-authentication"></a><span data-ttu-id="50ff7-107">Azure AD-hitelesítés konfigurálása</span><span class="sxs-lookup"><span data-stu-id="50ff7-107">Configure Azure AD authentication</span></span>

<span data-ttu-id="50ff7-108">Ahhoz, hogy az Azure AD az üzlet pénztári bejelentkezésének hitelesítési módszere legyen, konfigurálnia kell az üzlet funkcióprofiljának beállításait, majd alkalmazni a beállítást a pénztárkliensre.</span><span class="sxs-lookup"><span data-stu-id="50ff7-108">To make Azure AD available as the authentication method for POS sign-in for a store, you must configure the settings of the store's functionality profile and then apply those setting to POS clients.</span></span>

<span data-ttu-id="50ff7-109">A funkcióprofil konfigurálásához az alábbi lépéseket hajtsa végre.</span><span class="sxs-lookup"><span data-stu-id="50ff7-109">To configure a functionality profile, follow these steps.</span></span>

1. <span data-ttu-id="50ff7-110">Ugorjon a következő elemre: **Retail és Commerce** \> **Csatorna beállítása** \> **Pénztárbeállítás** \> **Pénztárprofilok** \> **Funkcióprofilok**.</span><span class="sxs-lookup"><span data-stu-id="50ff7-110">Go to **Retail and Commerce** \> **Channel setup** \> **POS setup** \> **POS profiles** \> **Functionality profiles**.</span></span>
1. <span data-ttu-id="50ff7-111">Válassza ki a módosítani kívánt funkcióprofilt.</span><span class="sxs-lookup"><span data-stu-id="50ff7-111">Select the functionality profile to change.</span></span>
1. <span data-ttu-id="50ff7-112">A **Funkciók** gyorslapon, a **Pénztár személyzeti bejelentkezés** szakaszban módosítsa a **Bejelentkezés hitelesítési módja** mező értékét **Személyzeti aozonosító és jelszó** értékről **Azure Active Directory** értékre.</span><span class="sxs-lookup"><span data-stu-id="50ff7-112">On the **Functions** FastTab, in the **POS staff logon** section, change the value of the **Logon Authentication Method** field from **Personnel ID and Password** to **Azure Active Directory**.</span></span>

<span data-ttu-id="50ff7-113">Alapértelmezés szerint az összes funkcióprofil **személyzeti azonosítót és jelszót** használ a pénztár hitelesítési módszerként.</span><span class="sxs-lookup"><span data-stu-id="50ff7-113">By default, all functionality profiles use **Personnel ID and Password** as the POS authentication method.</span></span> <span data-ttu-id="50ff7-114">Ennek megfelelően módosítania kell **Bejelentkezés hitelesítési módja** mező értékét, ha Azure AD-t szeretne használni.</span><span class="sxs-lookup"><span data-stu-id="50ff7-114">Therefore, you must change the value of the **Logon Authentication Method** field if you want to use Azure AD.</span></span> <span data-ttu-id="50ff7-115">A módosítás hatással van minden olyan kiskereskedelmi üzletre, amely a kiválasztott funkcióprofilhoz van társítva.</span><span class="sxs-lookup"><span data-stu-id="50ff7-115">Every retail store that is linked to the selected functionality profile will be affected by this change.</span></span>

<span data-ttu-id="50ff7-116">A beállítások alkalmazásához a pénztárkliensre kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="50ff7-116">To apply the settings to POS clients, follow these steps.</span></span>

1. <span data-ttu-id="50ff7-117">Ugorjon a **Kiskereskedelem és kereskedelem** \> **Kiskereskedelem és kereskedelem informatika** \> **Elosztási ütemezés** pontra.</span><span class="sxs-lookup"><span data-stu-id="50ff7-117">Go to **Retail and Commerce** \> **Retail and Commerce IT** \> **Distribution schedule**.</span></span>
1. <span data-ttu-id="50ff7-118">Futtassa a **1070** (**Csatornakonfiguráció**) elosztási ütemezést.</span><span class="sxs-lookup"><span data-stu-id="50ff7-118">Run the **1070** (**Channel configuration**) distribution schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="50ff7-119">Azure AD-hitelesítéshez internetkapcsolat szükséges.</span><span class="sxs-lookup"><span data-stu-id="50ff7-119">Azure AD authentication requires an internet connection.</span></span> <span data-ttu-id="50ff7-120">Nem működik, ha a pénztár offline módban van.</span><span class="sxs-lookup"><span data-stu-id="50ff7-120">It won't work when POS is in offline mode.</span></span>
> 
> <span data-ttu-id="50ff7-121">Jelenleg a **Vezetői felülbírálás** funkció nem támogatja a Azure AD-t hitelesítési módszerként.</span><span class="sxs-lookup"><span data-stu-id="50ff7-121">Currently, the **Manager override** function doesn't support Azure AD as an authentication method.</span></span> <span data-ttu-id="50ff7-122">Még akkor is szükség van egy kezelői azonosítóra és jelszóra és jelszóra, ha a POS-bejelentkezés hitelesítési módszerének Azure AD van beállítva.</span><span class="sxs-lookup"><span data-stu-id="50ff7-122">An operator ID and password are required even if Azure AD is configured as the authentication method for POS sign-in.</span></span>

## <a name="associate-an-azure-ad-account-with-a-worker"></a><span data-ttu-id="50ff7-123">Azure AD-fiók társítása dolgozóval</span><span class="sxs-lookup"><span data-stu-id="50ff7-123">Associate an Azure AD account with a worker</span></span>

<span data-ttu-id="50ff7-124">Ahhoz, hogy egy üzlet dolgozója Azure AD-fiókkal jelentkezhessen be a pénztáralkalmazásba, az Azure AD-fiókot az adott dolgozóhoz kell társítani.</span><span class="sxs-lookup"><span data-stu-id="50ff7-124">Before a store worker can use an Azure AD account to sign in to the POS application, the Azure AD account must be associated with that worker.</span></span>

<span data-ttu-id="50ff7-125">Az Azure AD-fiók dolgozóhoz való társításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="50ff7-125">To associate an Azure AD account with a worker, follow these steps.</span></span>

1. <span data-ttu-id="50ff7-126">Nyissa meg a következőt: **Kiskereskedelem és kereskedelem** \> **Alkalmazottak** \> **Dolgozók**.</span><span class="sxs-lookup"><span data-stu-id="50ff7-126">Go to **Retail and Commerce** \> **Employees** \> **Workers**.</span></span>
1. <span data-ttu-id="50ff7-127">A dolgozó részletes lapjának megnyitása.</span><span class="sxs-lookup"><span data-stu-id="50ff7-127">Open the details page for a worker.</span></span>
1. <span data-ttu-id="50ff7-128">A műveleti ablaktáblán a **Kereskedelem** lapon a **Külső identitás** csoportban válassza a **Meglévő identitás társítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="50ff7-128">On the Action Pane, on the **Commerce** tab, in the **External identity** group, select **Associate existing identity**.</span></span>
1. <span data-ttu-id="50ff7-129">A **Meglévő külső identitás használata** párbeszédpanelen válassza a **Keresés e-maillel** parancsot, adja meg Azure AD-e-mail címet, majd válassza a **Keresés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="50ff7-129">In the **Use existing external identity** dialog box, select **Search using email**, enter an Azure AD email address, and then select **Search**.</span></span>
1. <span data-ttu-id="50ff7-130">Válassza ki a visszaadott Azure AD-fiókot, majd az **OK** elemet.</span><span class="sxs-lookup"><span data-stu-id="50ff7-130">Select the Azure AD account that is returned, and then select **OK**.</span></span>

<span data-ttu-id="50ff7-131">A rendszer kitölti az **Alias**, **UPN**, **Külső részazonosító** mezőket a dolgozó adatainak oldalának **Commerce** oldalán.</span><span class="sxs-lookup"><span data-stu-id="50ff7-131">The **Alias**, **UPN**, and **External sub identifier** fields on the **Commerce** tab of the worker's details page will be filled in.</span></span>

> [!NOTE]
> <span data-ttu-id="50ff7-132">A dolgozói rekord frissítése után – például ha egy új Azure AD számlát társítanak hozzá – megváltozik egy jelszó vagy frissül egy dolgozói címjegyzék, javasoljuk, hogy futtassa az **1060** (**Személyzet**) elosztási ütemezést a legfrissebb személyzeti adatok csatornához történő szinkronizálásához.</span><span class="sxs-lookup"><span data-stu-id="50ff7-132">After a worker record is updated, for example if a new Azure AD account is associated, a password is changed, or an employee address book is updated, it’s recommended that you run **1060** (**Staff**) distribution schedule to synchronize the latest staff information to the channel.</span></span> <span data-ttu-id="50ff7-133">Így a pénztár alkalmazás be tudja olvasni a megfelelő adatokat a felhasználó hitelesítéséhez és a hitelesítés ellenőrzéséhez.</span><span class="sxs-lookup"><span data-stu-id="50ff7-133">That way, the POS application can fetch the correct data for user authentication and authorization check.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="50ff7-134">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="50ff7-134">Additional resources</span></span>

[<span data-ttu-id="50ff7-135">Kiterjesztett bejelentkezési funkció beállítása az MPOS-hez és a Cloud POS-hoz</span><span class="sxs-lookup"><span data-stu-id="50ff7-135">Set up extended logon functionality for MPOS and Cloud POS</span></span>](extended-logon.md)

[<span data-ttu-id="50ff7-136">Retail funkcióprofil létrehozása</span><span class="sxs-lookup"><span data-stu-id="50ff7-136">Create a retail functionality profile</span></span>](retail-functionality-profile.md)

[<span data-ttu-id="50ff7-137"> Dolgozó konfigurálása</span><span class="sxs-lookup"><span data-stu-id="50ff7-137">Configure a worker</span></span>](https://docs.microsoft.com/dynamics365/commerce/tasks/worker)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
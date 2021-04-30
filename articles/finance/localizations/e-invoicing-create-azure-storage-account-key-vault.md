---
title: Hozzon létre Azure tárfiókot és egy kulcstartót
description: Ez a témakör azt mutatja be, hogyan lehet egy Azure tárfiókot és egy kulcstartót létrehozni.
author: gionoder
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 2786d350fde2399aadb35dc653bc15123e0e6d91
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893802"
---
# <a name="create-an-azure-storage-account-and-a-key-vault"></a><span data-ttu-id="b6ad9-103">Hozzon létre Azure tárfiókot és egy kulcstartót</span><span class="sxs-lookup"><span data-stu-id="b6ad9-103">Create an Azure storage account and a key vault</span></span>

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="b6ad9-104">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="b6ad9-104">Prerequisites</span></span>

<span data-ttu-id="b6ad9-105">Mielőtt teljesítené az ebben a témakörben ismertetett lépéseket, bizonyosodjon meg arról, hogy a következő feladatok el lettek végezve:</span><span class="sxs-lookup"><span data-stu-id="b6ad9-105">Before you can complete the steps in this topic, you must make sure that the following tasks have been completed:</span></span>

- <span data-ttu-id="b6ad9-106">Kulcstartó-erőforrás létrehozása az Azure szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-106">Create a key vault resource in Azure.</span></span> <span data-ttu-id="b6ad9-107">További információkért lásd [Az Azure Key Vaulról](/azure/key-vault/general/overview) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-107">For more information, see [About Azure Key Vault](/azure/key-vault/general/overview).</span></span>
- <span data-ttu-id="b6ad9-108">Hozzon létre egy Azure tárfiókot (Blob-tároló).</span><span class="sxs-lookup"><span data-stu-id="b6ad9-108">Create an Azure storage account (Blob storage).</span></span> <span data-ttu-id="b6ad9-109">További információkért lásd a [Azure tárfiók karbantartása](/azure/storage/blobs/) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-109">For more information, see [Maintaining Azure Storage Account](/azure/storage/blobs/).</span></span>

## <a name="overview"></a><span data-ttu-id="b6ad9-110">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="b6ad9-110">Overview</span></span>

<span data-ttu-id="b6ad9-111">Ebben a témakörben két fő lépést kell végrehajtania:</span><span class="sxs-lookup"><span data-stu-id="b6ad9-111">In this topic, you will complete two main steps:</span></span>

- <span data-ttu-id="b6ad9-112">Az Azure tárfiók beállítása a tárfiók URI-azonosítójának megszerzéséhez.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-112">Set up the Azure storage account to get the storage account URI.</span></span>
- <span data-ttu-id="b6ad9-113">A kulcstartó beállítása a tárfiók URI-azonosítójának tárolásához.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-113">Set up the key vault to store the storage account URI.</span></span>

## <a name="set-up-the-azure-storage-account-to-get-the-storage-account-uri"></a><span data-ttu-id="b6ad9-114">Az Azure tárfiók beállítása a tárfiók URI-azonosítójának megszerzéséhez</span><span class="sxs-lookup"><span data-stu-id="b6ad9-114">Set up the Azure storage account to get the storage account URI</span></span>

1. <span data-ttu-id="b6ad9-115">Nyissa meg az elektronikus számlázással használni kívánt tárfiókot.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-115">Open the storage account that you plan to use with Electronic invoicing.</span></span>
2. <span data-ttu-id="b6ad9-116">Nyissa meg a **Blob-szolgáltatás** \> **Tárolók** lehetőséget, és hozzon létre egy új tárolót.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-116">Go to **Blob service** \> **Containers**, and create a new container.</span></span>
3. <span data-ttu-id="b6ad9-117">Adjon egy nevet a tárolónak, majd állítsa a **Nyilvános hozzáférési szint** mezőt **Privát (névtelen hozzáférés nem lehetséges)** értékre.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-117">Enter a name for the container, and set the **Public access level** field to **Private (no anonymous access)**.</span></span>
4. <span data-ttu-id="b6ad9-118">Nyissa ki a tárolót, és menjen a **Beállítások \> Hozzáférési szabályzat** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-118">Open the container, and go to **Settings \> Access policy**.</span></span>
5. <span data-ttu-id="b6ad9-119">Válassza ki a **Szabályzat hozzáadása** lehetőséget a tárolt hozzáférési szabályok hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-119">Select **Add policy** to add a stored access policy.</span></span>
6. <span data-ttu-id="b6ad9-120">Megfelelő módon adja állítsa be az **Azonosító** és az **Engedélyek** mezőt.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-120">Set the **Identifier** and **Permissions** fields as appropriate.</span></span> <span data-ttu-id="b6ad9-121">Az **Engedélyek** mezőben válassza ki az összes engedélyt.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-121">In the **Permissions** field, you should select all permissions.</span></span>

    ![Blob-tárterület-engedély megadása](media/e-Invoicing-services-create-azure-resources-grant-blob-permissions.png)

7. <span data-ttu-id="b6ad9-123">Adja meg a kezdő és lejárati dátumokat.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-123">Enter the start and expiry dates.</span></span> <span data-ttu-id="b6ad9-124">A lejárati dátumnak jövőbeli dátumnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-124">The expiry date should be in future.</span></span>
8. <span data-ttu-id="b6ad9-125">Válassza az **OK** gombot a szabályzat mentéséhez, majd mentse a módosításokat a tárolóba.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-125">Select **OK** to save the policy, and then save your changes to the container.</span></span>
9. <span data-ttu-id="b6ad9-126">Térjen vissza a tárfiókhoz, és nyissa meg a **Storage Explorer (előzetes verzió)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-126">Return to the storage account, and open **Storage Explorer (preview)**.</span></span>
10. <span data-ttu-id="b6ad9-127">Kattintson a jobb egérgombbal a tárolóra, majd válassza a **Közös hozzáférésű jogosultságkód megszerzése** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-127">Right-click the container, and then select **Get Shared Access Signature**.</span></span>
11. <span data-ttu-id="b6ad9-128">A **Közös hozzáférésű jogosultságkód** párbeszédpanelen másolja és tárolja az értéket az **URI** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-128">In the **Shared Access Signature** dialog box, copy and store the value in the **URI** field.</span></span> <span data-ttu-id="b6ad9-129">Ezt az értéket használja a rendszer a következő eljárásban, és *Közös hozzáférésű jogosultságkód URI* néven fog rá hivatkozni.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-129">This value will be used in the next procedure and will be referred to as the *shared access signature URI*.</span></span>

    ![Az URI-érték kiválasztása és másolása](media/e-Invoicing-services-create-azure-resources-select-and-copy-uri.png)

## <a name="set-up-the-key-vault-to-store-the-storage-account-uri"></a><span data-ttu-id="b6ad9-131">A kulcstartó beállítása a tárfiók URI-azonosítójának tárolásához</span><span class="sxs-lookup"><span data-stu-id="b6ad9-131">Set up the key vault to store the storage account URI</span></span>

1. <span data-ttu-id="b6ad9-132">Nyissa meg az elektronikus számlázással használni kívánt kulcstartót.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-132">Open the key vault that you intend to use with Electronic invoicing.</span></span>
2. <span data-ttu-id="b6ad9-133">Menjen a **Beállítások** \> **Titkok** lehetőségre, majd válassza a **Létrehozás/importálás** elemet az új titok létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-133">Go to **Settings** \> **Secrets**, and then select **Generate/Import** to create a new secret.</span></span>
3. <span data-ttu-id="b6ad9-134">A **Titok létrehozása** oldal **Feltöltési beállítások** mezőjében válassza a **Manuális** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-134">On the **Create a secret** page, in the **Upload options** field, select **Manual**.</span></span>
4. <span data-ttu-id="b6ad9-135">Adja meg a titok nevét.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-135">Enter the name of the secret.</span></span> <span data-ttu-id="b6ad9-136">Ezt a nevet fogják használni a szolgáltatás Regulatory Configuration Service (RCS) szolgáltatásban történő beállításakor, illetve *kulcstartó titok* néven fognak rá hivatkozni.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-136">This name will be used during setup of the service in Regulatory Configuration Service (RCS) and will be referred to as the *key vault secret name*.</span></span>
5. <span data-ttu-id="b6ad9-137">Az **Érték** mezőben válassza a **Közös hozzáférésű jogosultságkód URI** lehetőséget, majd a **Létrehozás** elemet.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-137">In the **Value** field, select **Shared Access Signature URI**, and then select **Create**.</span></span>
6. <span data-ttu-id="b6ad9-138">Állítsa be a hozzáférési szabályzatot, hogy az Elektronikus számlázás megfelelő biztonsági hozzáférési szintet tudjon engedélyezni a létrehozott titoknak.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-138">Set up the access policy to grant Electronic invoicing the correct level of secure access to the secret you created.</span></span> <span data-ttu-id="b6ad9-139">Menjen a **Beállítások \> Hozzáférési szabályzat** lehetőségre, és válassza a **Hozzáférési szabályzat hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-139">Go to **Settings \> Access policy**, and select **Add Access Policy**.</span></span>
7. <span data-ttu-id="b6ad9-140">Állítsa be a **Megszerzés** és a **Lista** műveleteihez tartozó titkos engedélyeket.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-140">Set the secret permissions for the **Get** and **List** operations.</span></span>

    ![Szolgáltatáshozzáférés megadása](media/e-Invoicing-services-create-azure-resources-grant-service-access.png)

8. <span data-ttu-id="b6ad9-142">Állítsa be a **Megszerzés** és a **Lista** műveleteihez tartozó tanúsítványengedélyeket.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-142">Set the certificate permissions for **Get** and **List** operations.</span></span>

    ![Tanúsítványengedély megadása](media/e-Invoicing-services-create-azure-resources-grant-certificate-permission.png)

9. <span data-ttu-id="b6ad9-144">A **Rendszerbiztonsági tag kiválasztása** mezőben válassza a **Nincs kiválasztva** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-144">In the **Select principal** field, select **None selected**.</span></span>
10. <span data-ttu-id="b6ad9-145">A **Rendszerbiztonsági tag** párbeszédpanelen válassza ki a rendszerbiztonsági tagot az **e-számlázási szolgáltatás** hozzáadásával.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-145">In the **Principal** dialog box, select the principal by adding **e-Invoicing Service**.</span></span>
11. <span data-ttu-id="b6ad9-146">Válassza a **Hozzáadás** lehetőséget, majd a **Key Vault-módosítások mentése** elemet.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-146">Select **Add**, and then select **Save Key Vault changes**.</span></span>
12. <span data-ttu-id="b6ad9-147">Az **Áttekintés** oldalról másolja át a **DNS név** lehetőséghez tartozó kulcstartó értékét.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-147">On the **Overview** page, copy the **DNS name** value for the key vault.</span></span> <span data-ttu-id="b6ad9-148">Ezt az értéket fogják használni a szolgáltatás RCS-ben történő beállításakor, illetve *kulcstartó URI* néven fognak rá hivatkozni.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-148">This value will be used during setup of the service in RCS and will be referred as the *key vault URI*.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
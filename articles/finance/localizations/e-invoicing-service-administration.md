---
title: Az elektronikus számlázási bővítmény adminisztrációs összetevői
description: Ez a témakör az Elektronikus számlázási bővítmény adminisztrációval kapcsolatos összetevőiről nyújt tájékoztatást.
author: gionoder
manager: AnnBe
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 70ef47dd45200a14c9d780f3c280c554d0e52ac3
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592574"
---
# <a name="electronic-invoicing-add-on-administration-components"></a><span data-ttu-id="683c0-103">Az elektronikus számlázási bővítmény adminisztrációs összetevői</span><span class="sxs-lookup"><span data-stu-id="683c0-103">Electronic invoicing add-on administration components</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="683c0-104">Ez a témakör az Elektronikus számlázási bővítmény adminisztrációval kapcsolatos összetevőiről nyújt tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="683c0-104">This topic provides information about the components that are related to administration of the Electronic invoicing add-on.</span></span> <span data-ttu-id="683c0-105">Arról is tájékoztatást tartalmaz, hogyan kell konfigurálni az Elektronikus számlázási bővítmény szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="683c0-105">It also provides information about how to configure the Electronic invoicing add-on service.</span></span>

## <a name="azure"></a><span data-ttu-id="683c0-106">Azure</span><span class="sxs-lookup"><span data-stu-id="683c0-106">Azure</span></span>

<span data-ttu-id="683c0-107">A Microsoft Azure használatával létrehozhatja a kulcstartó és a tárfiók titkos kódjait.</span><span class="sxs-lookup"><span data-stu-id="683c0-107">Use Microsoft Azure to create the secrets for the key vault and storage account.</span></span> <span data-ttu-id="683c0-108">Ezután használja az Elektronikus számlázási bővítmény konfigurációjában használt titkos kódokat.</span><span class="sxs-lookup"><span data-stu-id="683c0-108">Then use the secrets in the configuration of the Electronic invoicing add-on.</span></span>

## <a name="lifecycle-services"></a><span data-ttu-id="683c0-109">Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="683c0-109">Lifecycle Services</span></span>

<span data-ttu-id="683c0-110">A Microsoft Dynamics Lifecycle Services (LCS) használatával engedélyezze a bővítményt az LCS-telepítési projekt mikroszolgáltatásai számára.</span><span class="sxs-lookup"><span data-stu-id="683c0-110">Use Microsoft Dynamics Lifecycle Services (LCS) to enable the add-on for the microservices for your LCS deployment project.</span></span>

> [!NOTE]
> <span data-ttu-id="683c0-111">A mikroszolgáltatások bővítményének LCS-szolgáltatásba való telepítéséhez legalább egy 2. szintű virtuális gép szükséges.</span><span class="sxs-lookup"><span data-stu-id="683c0-111">The installation of the microservice add-on in LCS requires at least a Tier 2 virtual machine.</span></span> <span data-ttu-id="683c0-112">A környezet tervezésével kapcsolatos további tudnivalókat lásd: [Környezet tervezése](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="683c0-112">For more information about environment planning, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
 

## <a name="regulatory-configuration-services"></a><span data-ttu-id="683c0-113">Regulatory Configuration Services</span><span class="sxs-lookup"><span data-stu-id="683c0-113">Regulatory Configuration Services</span></span>

<span data-ttu-id="683c0-114">A Dynamics 365 Regulatory Configuration Services (RCS) interfész segítségével konfigurálhatja az Elektronikus számlázási bővítményt.</span><span class="sxs-lookup"><span data-stu-id="683c0-114">Dynamics 365 Regulatory Configuration Services (RCS) is the interface that is used to configure the Electronic invoicing add-on.</span></span> <span data-ttu-id="683c0-115">Az erőforrások, például a környezetek és az elektronikus számlázási funkciók létrehozása, karbantartása és tárolása az RCS-rendszerben történik.</span><span class="sxs-lookup"><span data-stu-id="683c0-115">Resources such as environments and electronic invoicing features are created, maintained, and hosted in RCS.</span></span> <span data-ttu-id="683c0-116">Amikor az erőforrások készen állnak, a rendszer közzéteszi őket az Elektronikus számlázási bővítményben.</span><span class="sxs-lookup"><span data-stu-id="683c0-116">When the resources are ready, they are published to the Electronic invoicing add-on service.</span></span>

<span data-ttu-id="683c0-117">Az RCS-regisztrációval kapcsolatban lásd: [Regulatory services](https://marketing.configure.global.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="683c0-117">For RCS sign-up, see [Regulatory services](https://marketing.configure.global.dynamics.com/).</span></span>

<span data-ttu-id="683c0-118">Az RCS-szel kapcsolatos további információért lásd a [Regulatory Configuration Services (RCS) szolgáltatás – Globalizációs funkciók](rcs-globalization-feature.md) részt.</span><span class="sxs-lookup"><span data-stu-id="683c0-118">For more information about RCS, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md)</span></span>

### <a name="integration-with-the-electronic-invoicing-add-on"></a><span data-ttu-id="683c0-119">Integráció az elektronikus számlázási bővítménnyel</span><span class="sxs-lookup"><span data-stu-id="683c0-119">Integration with the Electronic invoicing add-on</span></span>

<span data-ttu-id="683c0-120">Ahhoz, hogy az RCS használatával konfigurálni tudja az elektronikus számlákat, be kell állítania, hogy az RCS lehetővé tegye a kommunikációt az Elektronikus számlázási bővítménnyel.</span><span class="sxs-lookup"><span data-stu-id="683c0-120">Before you can use RCS to configure electronic invoices, you must configure RCS to allow for communication with the Electronic invoicing add-on.</span></span> <span data-ttu-id="683c0-121">Ezt a konfigurációt az **Elektronikus jelentéskészítés paraméterei** oldal **Elektronikus számlázási bővítmény** lapján lehet végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="683c0-121">You complete this configuration on the **Electronic invoicing add-on** tab of the **Electronic reporting parameters** page.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="683c0-122">Szolgáltatás végpontja</span><span class="sxs-lookup"><span data-stu-id="683c0-122">Service endpoint</span></span>

<span data-ttu-id="683c0-123">Az Elektronikus számlázásbővítmény számos Azure adatközpont földrajzi régióban elérhető.</span><span class="sxs-lookup"><span data-stu-id="683c0-123">The Electronic invoicing add-on is available in several Azure datacenter geographies.</span></span> <span data-ttu-id="683c0-124">Az alábbi tábla felsorolja a régiónkénti elérhetőségeket.</span><span class="sxs-lookup"><span data-stu-id="683c0-124">The following table lists the availability per region.</span></span>

| <span data-ttu-id="683c0-125">Azure adatközpont földrajzi régió</span><span class="sxs-lookup"><span data-stu-id="683c0-125">Azure datacenter geography</span></span> |
|----------------------------|
| <span data-ttu-id="683c0-126">USA keleti régiója</span><span class="sxs-lookup"><span data-stu-id="683c0-126">East US</span></span>                    |
| <span data-ttu-id="683c0-127">USA nyugati régiója</span><span class="sxs-lookup"><span data-stu-id="683c0-127">West US</span></span>                    |
| <span data-ttu-id="683c0-128">Észak-EU</span><span class="sxs-lookup"><span data-stu-id="683c0-128">North EU</span></span>                   |
| <span data-ttu-id="683c0-129">Nyugat-EU</span><span class="sxs-lookup"><span data-stu-id="683c0-129">West EU</span></span>                    |

### <a name="service-environments"></a><span data-ttu-id="683c0-130">Szolgáltatáskörnyezetek</span><span class="sxs-lookup"><span data-stu-id="683c0-130">Service environments</span></span>

<span data-ttu-id="683c0-131">A szolgáltatási környezetek olyan logikai partíciók, amelyek az Elektronikus számlázási bővítmény elektronikus számlázási funkcióinak végrehajtását támogatják.</span><span class="sxs-lookup"><span data-stu-id="683c0-131">Service environments are logical partitions that are created to support execution of the electronic invoicing features in the Electronic invoicing add-on.</span></span> <span data-ttu-id="683c0-132">A biztonsági titkos kódokat és digitális tanúsítványokat, valamint a cégirányítást (azaz a hozzáférési engedélyeket) a szolgáltatási környezet szintjén kell konfigurálni.</span><span class="sxs-lookup"><span data-stu-id="683c0-132">The security secrets and digital certificates, and the governance (that is, access permissions), must be configured at the service environment level.</span></span>

<span data-ttu-id="683c0-133">Az ügyfelek annyi szolgáltatási környezetet hozhatnak létre, amennyit csak akarnak.</span><span class="sxs-lookup"><span data-stu-id="683c0-133">Customers can create as many service environments as they want.</span></span> <span data-ttu-id="683c0-134">Az ügyfél által létrehozott összes szolgáltatási környezetek egymástól függetlenek.</span><span class="sxs-lookup"><span data-stu-id="683c0-134">All the service environments that a customer creates are independent of each other.</span></span>

<span data-ttu-id="683c0-135">A szolgáltatási környezeteket RCS-ben kell létrehozni és karbantartani.</span><span class="sxs-lookup"><span data-stu-id="683c0-135">Service environments must be created and maintained in RCS.</span></span> <span data-ttu-id="683c0-136">Amikor a szolgáltatási környezetek készen állnak, a közzé kell őket tenni az Elektronikus számlázási bővítményben.</span><span class="sxs-lookup"><span data-stu-id="683c0-136">When the service environments are ready, they must be published to the Electronic invoicing add-on.</span></span>

#### <a name="service-environment-status"></a><span data-ttu-id="683c0-137">Szolgáltatási környezet állapota</span><span class="sxs-lookup"><span data-stu-id="683c0-137">Service environment status</span></span>

<span data-ttu-id="683c0-138">A szolgáltatási környezeteket kezelése állapotokkal történik.</span><span class="sxs-lookup"><span data-stu-id="683c0-138">Service environments can be managed through status.</span></span> <span data-ttu-id="683c0-139">Lehetséges választások:</span><span class="sxs-lookup"><span data-stu-id="683c0-139">The possible options are:</span></span>

- <span data-ttu-id="683c0-140">**Nincs közzétéve** – a környezetet létrehozták, de még nincs közzétéve.</span><span class="sxs-lookup"><span data-stu-id="683c0-140">**Not published** – The environment has been created, but it hasn't yet been published.</span></span>
- <span data-ttu-id="683c0-141">**Közzétéve** – a környezetet közzétették az Elektronikus számlázási bővítményben.</span><span class="sxs-lookup"><span data-stu-id="683c0-141">**Published** – The environment has been published to the Electronic invoicing add-on.</span></span>
- <span data-ttu-id="683c0-142">**Módosítva** – a közzétett környezet attribútumai megváltoztak, de a módosítások még nincsenek közzétéve.</span><span class="sxs-lookup"><span data-stu-id="683c0-142">**Changed** – The attributes of a published environment have been changed, but the changes haven't yet been published.</span></span>

#### <a name="customer-secrets"></a><span data-ttu-id="683c0-143">Vevő titkos kódjai</span><span class="sxs-lookup"><span data-stu-id="683c0-143">Customer secrets</span></span>

<span data-ttu-id="683c0-144">Az Elektronikus számlázásbővítmény szolgáltatás a felelős a vállalat tulajdonában lévő Azure-erőforrásokban lévő összes üzleti adatának tárolásáért.</span><span class="sxs-lookup"><span data-stu-id="683c0-144">The Electronic invoicing add-on service is responsible for storing all your business data in the Azure resources that your company owns.</span></span> <span data-ttu-id="683c0-145">Ha biztosítani szeretné, hogy a szolgáltatás megfelelően működjön, és hogy az elektronikus számlázásbővítményhez szükséges, illetve az általa létrehozott összes üzleti adat csak a bővítmény számára legyen érhető el, akkor két fő Azure-erőforrást kell létrehoznia:</span><span class="sxs-lookup"><span data-stu-id="683c0-145">To ensure that the service works correctly, and that all the business data that is required for and generated by the Electronic invoicing add-on is accessed only by the add-on, you must create two main Azure resources:</span></span>

- <span data-ttu-id="683c0-146">Az elektronikus számlák tárolásához szükséges Azure tárfiókot (Blob-tároló)</span><span class="sxs-lookup"><span data-stu-id="683c0-146">An Azure storage account (Blob storage) that will store electronic invoices</span></span>
- <span data-ttu-id="683c0-147">Egy Azure-kulcstartót a tanúsítványok és a tárolási fiók Uniform Resource Identifier (URI) tárolásához</span><span class="sxs-lookup"><span data-stu-id="683c0-147">An Azure key vault that will store certificates and the uniform resource identifier (URI) of the storage account</span></span>

> [!NOTE]
> <span data-ttu-id="683c0-148">A dedikált kulcstartót és a vevői tárfiókot kifejezetten az Elektronikus számlázásbővítménnyel történő használatra kell felosztani.</span><span class="sxs-lookup"><span data-stu-id="683c0-148">A dedicated key vault and customer storage account must be allocated specifically for use with the Electronic invoicing add-on.</span></span>

<span data-ttu-id="683c0-149">További információért lásd az [Azure tárfiók és kulcstartó létrehozása](e-invoicing-create-azure-storage-account-key-vault.md) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683c0-149">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

#### <a name="users"></a><span data-ttu-id="683c0-150">Felhasználók</span><span class="sxs-lookup"><span data-stu-id="683c0-150">Users</span></span>

<span data-ttu-id="683c0-151">Minden szolgáltatási környezetben fel kell sorolni azokat a felhasználókat, akik csatlakozni tudnak a Dynamics 365 Finance és a Dynamics 365 Supply Chain Management modulból az Elektronikus számlázási bővítményhez.</span><span class="sxs-lookup"><span data-stu-id="683c0-151">Each service environment must list the users who can connect from Dynamics 365 Finance and Dynamics 365 Supply Chain Management in the Electronic invoicing add-on.</span></span>

#### <a name="publication"></a><span data-ttu-id="683c0-152">Közzététel</span><span class="sxs-lookup"><span data-stu-id="683c0-152">Publication</span></span>

<span data-ttu-id="683c0-153">A szolgáltatási környezeteket használat előtt közzé kell őket tenni az Elektronikus számlázási bővítményben.</span><span class="sxs-lookup"><span data-stu-id="683c0-153">Service environments must be published to the Electronic invoicing add-on before they can be used.</span></span> <span data-ttu-id="683c0-154">A Finance and Supply Chain Management modul csak közzétett környezeteket tud elérni.</span><span class="sxs-lookup"><span data-stu-id="683c0-154">Only published environments can be accessed by Finance and Supply Chain Management.</span></span> <span data-ttu-id="683c0-155">Ezenkívül a szolgáltatási környezetet közzé kell tenni, mielőtt az attribútumainak frissítése hatályba lép az elektronikus számlázási szolgáltatáson.</span><span class="sxs-lookup"><span data-stu-id="683c0-155">Additionally, a service environment must be published before any updates to its attributes will take effect on the electronic invoicing service.</span></span>

### <a name="connected-applications"></a><span data-ttu-id="683c0-156">Csatlakoztatott alkalmazások</span><span class="sxs-lookup"><span data-stu-id="683c0-156">Connected applications</span></span>

<span data-ttu-id="683c0-157">A csatlakoztatott alkalmazások Finance and Supply Chain Management modul példányai, amelyeket az RCS-rendszer segítségével érdemes elérni.</span><span class="sxs-lookup"><span data-stu-id="683c0-157">Connected applications are the instances of Finance and Supply Chain Management that you might want to reach through RCS.</span></span> <span data-ttu-id="683c0-158">Az alkalmazás URL-címe és bérlője mellett a csatlakoztatott alkalmazás tartalmazza azokat a hitelesítő adatokat, amelyek alapján az RCS csatlakozhat a környezethez.</span><span class="sxs-lookup"><span data-stu-id="683c0-158">Besides the application URL and its tenant, a connected application contains the credentials that enable RCS to connect to the environment.</span></span>

<span data-ttu-id="683c0-159">A csatlakoztatott alkalmazásokon keresztül a Finance and Supply Chain Management modul elektronikus számlázási szolgáltatásának egy részét konfigurálni lehet, hogy a teljes elektronikus számlázási funkció működjön.</span><span class="sxs-lookup"><span data-stu-id="683c0-159">Through the connected applications, you can configure part of the electronic invoicing feature in Finance and Supply Chain Management to make the whole electronic invoicing feature work.</span></span>

## <a name="finance-and-supply-chain-management"></a><span data-ttu-id="683c0-160">Finance and Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="683c0-160">Finance and Supply Chain Management</span></span>

### <a name="integration-with-electronic-invoicing-add-on"></a><span data-ttu-id="683c0-161">Integráció az Elektronikus számlázási bővítménnyel</span><span class="sxs-lookup"><span data-stu-id="683c0-161">Integration with Electronic invoicing add-on</span></span>

<span data-ttu-id="683c0-162">Ahhoz, hogy a Finance and Supply Chain Management modul segítségével elektronikus számlákat tudjon kiállítani az Elektronikus számlázási bővítményen keresztül, a bővítményt úgy kell konfigurálni, hogy lehetővé tegye a szolgáltatással való kommunikációt.</span><span class="sxs-lookup"><span data-stu-id="683c0-162">Before you can use Finance and Supply Chain Management to issue electronic invoices through the Electronic invoicing add-on, the add-on must be configured to allow for communication with the service.</span></span>

#### <a name="electronic-invoicing-add-on-integration-feature"></a><span data-ttu-id="683c0-163">Az Elektronikus számlázási bővítmény integrációs funkciója</span><span class="sxs-lookup"><span data-stu-id="683c0-163">Electronic invoicing add-on integration feature</span></span>

<span data-ttu-id="683c0-164">A Finance and Supply Chain Management modul és az Elektronikus számlázási bővítmény közötti kommunikáció engedélyezéséhez be kell kapcsolnia az **Elektronikus számlázási bővítmény integrációja** funkciót a **Funkciókezelés** munkaterületen.</span><span class="sxs-lookup"><span data-stu-id="683c0-164">To enable communication between Finance and Supply Chain Management and the Electronic invoicing add-on, you must turn on the **Electronic Invoicing add-on integration** feature in the **Feature management** workspace.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="683c0-165">Szolgáltatás végpontja</span><span class="sxs-lookup"><span data-stu-id="683c0-165">Service endpoint</span></span>

<span data-ttu-id="683c0-166">A szolgáltatásvégpont az az URL-cím, ahol az Elektronikus számlázási bővítmény található.</span><span class="sxs-lookup"><span data-stu-id="683c0-166">The service endpoint is the URL where the Electronic invoicing add-on is located.</span></span> <span data-ttu-id="683c0-167">Ahhoz, hogy a Finance and Supply Chain Management modul segítségével elektronikus számlákat tudjon kiállítani a szolgáltatásvégpontot úgy kell konfigurálni, hogy lehetővé tegye a szolgáltatással való kommunikációt.</span><span class="sxs-lookup"><span data-stu-id="683c0-167">Before electronic invoices can be issued, the service endpoint must be configured in Finance and Supply Chain Management to allow for communication with the service.</span></span>

<span data-ttu-id="683c0-168">A szolgáltatásvégpont beállításához lépjen a **Szervezeti adminisztráció \> Beállítás \> Elektronikus dokumentum paramétere** lehetőségre, majd a **Benyújtási szolgáltatások** oldal **Elektronikus számlázási bővítmény URL-címe** mezőben adja meg az URL-címet a **Szolgáltatávégpont** szakaszban ismertetett módon.</span><span class="sxs-lookup"><span data-stu-id="683c0-168">To configure the service endpoint, go to **Organization administration \> Setup \> Electronic document parameter**, and then, on the **Submission services** tab, in the **Electronic invoicing add-on URL** field, enter the URL as described in the table described in section **Service endpoint**.</span></span>

#### <a name="environments"></a><span data-ttu-id="683c0-169">Környezetek</span><span class="sxs-lookup"><span data-stu-id="683c0-169">Environments</span></span>

<span data-ttu-id="683c0-170">A Finance and Supply Chain Management modulban megadott környezetnév annak a környezetnek a nevére vonatkozik, amelyet az RCS-ben hoztak létre, és az Elektronikus számlázási bővítményben tettek közzé.</span><span class="sxs-lookup"><span data-stu-id="683c0-170">The environment name that is entered in Finance and Supply Chain Management refers to the name of the environment that is created in RCS and published to the Electronic invoicing add-on.</span></span>

<span data-ttu-id="683c0-171">A környezetet be kell állítani az **Elektronikus dokumentum paraméter** oldal **Benyújtási szolgáltatások** lapján, hogy minden elektronikus számla kiadási kérése tartalmazza azt a környezetet, ahol az Elektronikus számlázási bővítmény eldöntheti, hogy melyik elektronikus számlázási funkciónak kell feldolgoznia a kérést.</span><span class="sxs-lookup"><span data-stu-id="683c0-171">The environment must be configured on the **Submission services** tab of the **Electronic document parameter** page, so that every request to issue electronic invoices contains the environment where the Electronic invoicing add-on can determine which electronic invoicing feature must process the request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="683c0-172">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="683c0-172">Additional resources</span></span>

- [<span data-ttu-id="683c0-173">Elektronikus számlák konfigurálása az RCS szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="683c0-173">Configure electronic invoices in RCS</span></span>](e-invoicing-configuration-rcs.md)
- [<span data-ttu-id="683c0-174">Elektronikus számlák kibocstása a Finance és Supply Chain Management szolgáltatásokban</span><span class="sxs-lookup"><span data-stu-id="683c0-174">Issue electronic invoices in Finance and Supply Chain Management</span></span>](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

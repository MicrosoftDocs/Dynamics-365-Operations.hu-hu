---
title: Ügyfélfigyelmeztetések értesítései e-mailben
description: Ez a témaköz a szabályok beállításáról ad információt, amelyekkel előre megadott esemény bekövetkezésekor e-mailes értesítéseket küld.
author: tjvass
manager: AnnBe
ms.date: 02/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: kfend
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2019-1-29
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 9545731af20a96c322b4e92c17f3a46b7077295b
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1546962"
---
# <a name="client-alert-notifications-by-email"></a><span data-ttu-id="6a90c-103">Ügyfélfigyelmeztetések értesítései e-mailben</span><span class="sxs-lookup"><span data-stu-id="6a90c-103">Client alert notifications by email</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="6a90c-104">A Microsoft Dynamics 365 for Finance and Operations szolgáltatásban megadhat egyéni figyelmeztetési szabályokat, amelyek az adatok szűrt nézeteit figyeli, és automatikusan értesítő e-maileket küld előre megadott esemény bekövetkezésekor.</span><span class="sxs-lookup"><span data-stu-id="6a90c-104">In Microsoft Dynamics 365 for Finance and Operations, you can define custom alert rules that monitor filtered views of data and automatically send email notifications when predefined events occur.</span></span> <span data-ttu-id="6a90c-105">Az értesítő e-mailek küldése beállítás minden támogatott figyelmeztetési típus esetében elérhető, és be lehet kapcsolni meglévő figyelmeztetési szabályhoz.</span><span class="sxs-lookup"><span data-stu-id="6a90c-105">The option to send email notifications is available for all supported alert types and can also be turned on for existing alert rules.</span></span>

<span data-ttu-id="6a90c-106">Beépített vezérlőkkel létrehozhat figyelmeztetési szabályokat, amelyek a szűrt nézetekkel nyomon követik a rendszer kötegelt feladatait.</span><span class="sxs-lookup"><span data-stu-id="6a90c-106">You can use built-in controls to create alert rules that monitor the filtered views of system batch jobs.</span></span> <span data-ttu-id="6a90c-107">Az **Állapot** mező értékeinek követésével Ön is beállíthat figyelmeztetési szabályokat, amelyek e-mailt küldenek a kötegelt feladat sikertelensége esetén.</span><span class="sxs-lookup"><span data-stu-id="6a90c-107">By monitoring the value of the **Status** field, you can also configure alert rules that send email when a batch job fails.</span></span> <span data-ttu-id="6a90c-108">A figyelmeztetési szabályok létrehozása után már nem kell az üzleti adatokban végzett módosításokhoz jelentéseket ellenőriznie.</span><span class="sxs-lookup"><span data-stu-id="6a90c-108">After these alert rules are created, you no longer have to check reports for changes to business data.</span></span> <span data-ttu-id="6a90c-109">Ehelyett beállítható, hogy a Finance and Operations intelligens módosításészlelési szolgáltatása végezze a nyomon követést.</span><span class="sxs-lookup"><span data-stu-id="6a90c-109">Instead, you can let the Finance and Operations intelligent change detection service do the monitoring for you.</span></span>

<span data-ttu-id="6a90c-110">Az ügyfélfigyelmeztetések függenek az e-mail-alrendszer Microsoft Office rendszerrel való integrációjától.</span><span class="sxs-lookup"><span data-stu-id="6a90c-110">Client alerts depend on the email subsystem that is provided through integration with Microsoft Office.</span></span> <span data-ttu-id="6a90c-111">Azt ajánljuk, hogy a Simple Mail Transfer Protocol (SMTP) szolgáltatót használja, hogy az e-mail terjesztésnek nem kell helyi levelezési kliensre támaszkodnia.</span><span class="sxs-lookup"><span data-stu-id="6a90c-111">We recommend that you use the Simple Mail Transfer Protocol (SMTP) provider, so that email distribution doesn't have to rely on a local mail client.</span></span>

<span data-ttu-id="6a90c-112">Az e-mailes értesítések küldéséhez a vevőknek konfigurálnia kell az integrált e-mail-szolgáltatásokat.</span><span class="sxs-lookup"><span data-stu-id="6a90c-112">To send notifications by email, customers must configure integrated email services.</span></span> <span data-ttu-id="6a90c-113">E-mail-értesítéseket a címzetteknek a figyelmeztetési tulajdonosok nevében küldik.</span><span class="sxs-lookup"><span data-stu-id="6a90c-113">Email notifications are sent to recipients on behalf of alert owners.</span></span>

<span data-ttu-id="6a90c-114">A Finance and Operations szolgáltatásban az e-mail konfigurálásával kapcsolatos további tudnivalókat lásd: [E-mail konfigurálása és küldése](../organization-administration/configure-email.md).</span><span class="sxs-lookup"><span data-stu-id="6a90c-114">For more information about how to configure email in Finance and Operations, see [Configure and send email](../organization-administration/configure-email.md).</span></span>

<span data-ttu-id="6a90c-115">A következő kép a **Figyelmeztetési szabály létrehozása** párbeszédpanelt mutatja, amely már tartalmazza az **E-mail küldése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6a90c-115">The following image shows the **Create alert rule** dialog box, which now includes a **Send email** option.</span></span>

<span data-ttu-id="6a90c-116">[![Figyelmeztetési szabály létrehozása párbeszédpanel, ahol az E-mail küldése beállítás értéke Igen](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)</span><span class="sxs-lookup"><span data-stu-id="6a90c-116">[![Create alert rule dialog box, where the Send email option is set to Yes](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)</span></span>

> [!NOTE]
> <span data-ttu-id="6a90c-117">Ha az **E-mail küldése** beállítás értéke **Igen**, a figyelmeztetési értesítéseket továbbra is a Műveleti központból kézbesítik.</span><span class="sxs-lookup"><span data-stu-id="6a90c-117">When the **Send email** option is set to **Yes**, alert notifications will continue to be delivered from the Action Center.</span></span>

## <a name="alert-notification-email-templates"></a><span data-ttu-id="6a90c-118">Figyelmeztetési értesítések e-mail sablonjai</span><span class="sxs-lookup"><span data-stu-id="6a90c-118">Alert notification email templates</span></span>

<span data-ttu-id="6a90c-119">A szolgáltatás e-mailes értesítéseket küld előre megadott e-mail-sablonokkal, amelyekkel a figyelmeztetési értesítés alapadatait kézbesíti.</span><span class="sxs-lookup"><span data-stu-id="6a90c-119">The service sends email notifications by using predefined email templates that deliver the basic details of the alert notification.</span></span>

<span data-ttu-id="6a90c-120">A következő kép a figyelmeztetési értesítés szerkezetét mutatja e-mail fogadásakor.</span><span class="sxs-lookup"><span data-stu-id="6a90c-120">The following image show the structure of the alert notifications when they are received by email.</span></span>

<span data-ttu-id="6a90c-121">[![Sablonalapú figyelmeztetési értesítések rekord létrehozásához, mező módosításához és sablon törléséhez](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)</span><span class="sxs-lookup"><span data-stu-id="6a90c-121">[![Template-based alert notifications for record creation, field changes, and template deletion](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)</span></span>

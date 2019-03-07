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
ms.openlocfilehash: 314f04eec04a75aed058c9c38066738e8758f653
ms.sourcegitcommit: 440ebe14ad26574ba227d23ee8370f6b6110645b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2019
ms.locfileid: "373779"
---
# <a name="client-alert-notifications-by-email"></a>Ügyfélfigyelmeztetések értesítései e-mailben

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

A Microsoft Dynamics 365 for Finance and Operations szolgáltatásban megadhat egyéni figyelmeztetési szabályokat, amelyek az adatok szűrt nézeteit figyeli, és automatikusan értesítő e-maileket küld előre megadott esemény bekövetkezésekor. Az értesítő e-mailek küldése beállítás minden támogatott figyelmeztetési típus esetében elérhető, és be lehet kapcsolni meglévő figyelmeztetési szabályhoz.

Beépített vezérlőkkel létrehozhat figyelmeztetési szabályokat, amelyek a szűrt nézetekkel nyomon követik a rendszer kötegelt feladatait. Az **Állapot** mező értékeinek követésével Ön is beállíthat figyelmeztetési szabályokat, amelyek e-mailt küldenek a kötegelt feladat sikertelensége esetén. A figyelmeztetési szabályok létrehozása után már nem kell az üzleti adatokban végzett módosításokhoz jelentéseket ellenőriznie. Ehelyett beállítható, hogy a Finance and Operations intelligens módosításészlelési szolgáltatása végezze a nyomon követést.

Az ügyfélfigyelmeztetések függenek az e-mail-alrendszer Microsoft Office rendszerrel való integrációjától. Azt ajánljuk, hogy a Simple Mail Transfer Protocol (SMTP) szolgáltatót használja, hogy az e-mail terjesztésnek nem kell helyi levelezési kliensre támaszkodnia.

Az e-mailes értesítések küldéséhez a vevőknek konfigurálnia kell az integrált e-mail-szolgáltatásokat. E-mail-értesítéseket a címzetteknek a figyelmeztetési tulajdonosok nevében küldik.

A Finance and Operations szolgáltatásban az e-mail konfigurálásával kapcsolatos további tudnivalókat lásd: [E-mail konfigurálása és küldése](../organization-administration/configure-email.md).

A következő kép a **Figyelmeztetési szabály létrehozása** párbeszédpanelt mutatja, amely már tartalmazza az **E-mail küldése** lehetőséget.

[![Figyelmeztetési szabály létrehozása párbeszédpanel, ahol az E-mail küldése beállítás értéke Igen](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)

> [!NOTE]
> Ha az **E-mail küldése** beállítás értéke **Igen**, a figyelmeztetési értesítéseket továbbra is a Műveleti központból kézbesítik.

## <a name="alert-notification-email-templates"></a>Figyelmeztetési értesítések e-mail sablonjai

A szolgáltatás e-mailes értesítéseket küld előre megadott e-mail-sablonokkal, amelyekkel a figyelmeztetési értesítés alapadatait kézbesíti. Ezek az adatok közvetlen hivatkozást tartalmaznak az oldalra, amelyen a figyelmeztetési szabályt meghatározták.

A következő kép a figyelmeztetési értesítés szerkezetét mutatja e-mail fogadásakor.

[![Sablonalapú figyelmeztetési értesítések rekord létrehozásához, mező módosításához és sablon törléséhez](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)

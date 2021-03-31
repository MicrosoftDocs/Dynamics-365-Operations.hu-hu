---
title: Csatornák áttekintése
description: Ez a témakör áttekintést nyújt a csatornákról a Microsoft Dynamics 365 Commerce szolgáltatásban.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 8ac188832bdaeba430eed7f08e91a9c2214a0e15
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5219101"
---
# <a name="channels-overview"></a>Csatornák áttekintése


[!include [banner](includes/banner.md)]

Ez a témakör áttekintést nyújt a csatornákról a Microsoft Dynamics 365 Commerce szolgáltatásban. Az egyes csatornák beállítása előtt és után elvégzendő feladatokkal kapcsolatban is itt tájékozódhat.

## <a name="types-of-channels"></a>Csatornák típusai

Dynamics 365 Commerce három különböző típusú csatornát támogat: kiskereskedelmi, hívásközpont és online csatornákat.

### <a name="retail-channels"></a>Kiskereskedelmi csatornák

A kiskereskedelmi csatornák megszokott, fizikai üzleteket jelentik. Az üzletek saját pénztárgépekkel (POS), bevételi és kiadási számlákkal, valamint munkatársakkal rendelkezhetnek. 

### <a name="call-center-channels"></a>Hívásközponti csatornák

A hívásközpont-csatornák a hívásközpontok rendelés- és ügyfélkezelését jelentik.

### <a name="online-channels"></a>Online csatornák

Az online csatornák online e-kereskedelmi üzleteket jelentenek. Online csatorna létrehozása után létre kell hozni egy webhelyet a Microsoft Dynamics 365 Commerce webhelykészítő eszközével vagy más külső fél e-kereskedelmi megoldásával.

## <a name="channel-setup-basics"></a>Csatorna beállítása – alapvető tudnivalók

A csatorna beállítása a Commerce eszközben történik. Minden csatornához tartozhatnak saját fizetési módok, árcsoportok, termékhierarchiák, szortimentek és termékek készlete. Miután létrehozta a csatornát, rendelje hozzá az üzlet által kezelendő és értékesítendő termékeket. Minden csatorna típusának egyedi funkciói lehetnek, amelyekhez konfigurálni kell. Például egy kiskereskedelmi csatornához alkalmazottakat, pénztárgépeket és vevőket kell hozzárendelni. Az új csatorna létrehozása után társítani kell hozzá egy szervezeti hierarchiát.

## <a name="channel-setup-prerequisites"></a>Csatornák beállításának előfeltételei

A csatorna beállítása előtt be kell fejeznie a csatorna típusától függő néhány előfeltétel-feladatot. További tájékoztatás: [Csatornabeállítási előfeltételek](channels-prerequisites.md).

## <a name="set-up-a-channel"></a>Csatorna beállítása

Az előfeltétel-feladatok végrehajtása után a további beállítási útmutató a következő hivatkozásokkal érhető el.

- [Kiskereskedelmi csatorna beállítása](channel-setup-retail.md)
- [Hívásközpont csatorna beállítása](channel-setup-callcenter.md)
- [Online csatorna beállítása](channel-setup-online.md)

<!--
## Post-channel configuration

After you create a channel, you may need to complete some of the below tasks:

- [Add channel to an organizational hierarchy](add-channel-org-hierarchy.md)
- Set up fulfillment groups. (LINK TBD)
- Configure the POS registers for the store. (LINK TBD)
- Assign product assortments to the store. (LINK TBD)
- Process assortments to generate the list of products that are included in the assortment and to make the products available in the retail store. (LINK TBD)
- Send data such as number sequences, hardware profiles, and POS screen layouts to the Retail POS registers.(LINK TBD)
- Publish the retail store to send store data to Retail POS. (LINK TBD)
- Run the jobs to send the store data to Retail POS. (LINK TBD)
-->

## <a name="additional-resources"></a>További erőforrások

[Csatornák beállításának előfeltételei](channels-prerequisites.md)

[Kiskereskedelmi csatorna beállítása](channel-setup-retail.md)
    
[Online csatorna beállítása](channel-setup-online.md)

[Hívásközpont csatorna beállítása](channel-setup-callcenter.md)

[Szervezeti hierarchiák beállítása](channels-org-hierarchies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
---
title: Azure-erőforrások beállítása elektronikus számlázáshoz
description: Ez a témakör áttekintést nyújt Microsoft Azure az elektronikus számlázás erőforrás-beállításának folyamatával kapcsolatban.
author: dkalyuzh
ms.date: 01/26/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: cb1fcddce1054aebf9ef70ba69eb7aca98093cbe
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371887"
---
# <a name="set-up-azure-resources-for-electronic-invoicing"></a>Azure-erőforrások beállítása elektronikus számlázáshoz

[!include [banner](../includes/banner.md)]

Az elektronikus számlázás erőforrás-beállításának Microsoft Azure folyamata három lépésből áll. Az első két lépés kötelező lépés: "Azure-kulcs létrehozása az Azure-portálon" és "Azure-tárolási fiók létrehozása az Azure-portálon". A harmadik lépés, a SharePoint "Kapcsolat konfigurálása" nem kötelező lépés.

## <a name="create-an-azure-key-vault-in-the-azure-portal"></a>Azure-kulcs használatának létrehozása az Azure-portálon

Kulcskulcs létrehozása Az Azure-előfizetésben. Javasoljuk, hogy hozzon létre egy külön kulcskulcsot az elektronikus számlázáshoz, és ne kombinálja ezeket a többi alkalmazással. Hozzon létre annyi tanúsítványt és tanúsítványt, amennyit az elektronikus dokumentumokban megkövetelt. Legalább egy titkos tárolót létre kell hoznia ahhoz, hogy a következő lépésben létrehozva az Azure-tárolási fiók megosztott hozzáférési aláírási (SAS) jogkivonatát tárolja.

A lépés befejezéséről [az Azure-kulcsok létrehozása az Azure-portálon található tájékoztatás](e-invoicing-create-azure-key-vault-azure-portal.md).

## <a name="create-an-azure-storage-account-in-the-azure-portal"></a>Azure-tárolási fiók létrehozása az Azure-portálon

A felhasználó a sajátja minden olyan elektronikus dokumentumnak és fájlnak, amelyet az Elektronikus számlázási szolgáltatás generál, illetve amely a szolgáltatás beíródik. Ezeket a dokumentumokat és fájlokat Az Azure-előfizetésben létrehozott Azure-tárhelyfiók tárolja. A szolgáltatás az Ön tárolási fiókjához annak a SAS jogkivonatnak a használatával fér hozzá, amely a Kulcs Titkos titkos kulcsból van átveve.

A lépéssel kapcsolatos tudnivalókat [lásd: Hozzon létre egy Azure-tárolási fiókot az Azure-portálon](e-invoicing-create-azure-storage-account-azure-portal.md).

## <a name="configure-a-sharepoint-connection"></a>SharePoint Kapcsolat konfigurálása

Bizonyos helyzetekben előfordulhat, hogy mentenie kell az elektronikus fájlokat SharePoint, és be kellolvasnia őket onnan SharePoint. Annak érdekében, hogy az elektronikus számlázási szolgáltatás hozzáférjen a mappákhoz SharePoint, konfigurálja a hozzáférést a mappához SharePoint.

A lépés befejezéséről a Kapcsolat konfigurálása tudnivalókat [tartalmaz SharePoint](e-invoicing-create-sharepoint-connection.md).

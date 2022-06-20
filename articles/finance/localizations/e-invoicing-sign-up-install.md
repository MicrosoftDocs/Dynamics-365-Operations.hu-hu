---
title: Az elektronikus számlázási szolgáltatás regisztrációja és telepítése
description: Ez a cikk az elektronikus számlázási szolgáltatásra való regisztrációval és telepítésvel kapcsolatban tartalmaz tájékoztatást.
author: dkalyuzh
ms.date: 02/07/2022
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
ms.openlocfilehash: 57314058883e60599bc51d91a65b0daeae724bb7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8865526"
---
# <a name="sign-up-for-and-install-the-electronic-invoicing-service"></a>Az elektronikus számlázási szolgáltatás regisztrációja és telepítése

[!include [banner](../includes/banner.md)]

Ez a cikk az elektronikus számlázási szolgáltatásra való regisztrációval és telepítésvel kapcsolatban tartalmaz tájékoztatást. A folyamat négy lépésből áll. Az 1–3. lépés kötelező, a 4. lépés pedig nem kötelező.

### <a name="step-1-sign-up-for-regulatory-configuration-service"></a>1. lépés: Regisztráció a konfigurációs szolgáltatásra

Az RCS (Regulatory Configuration Service) szolgáltatja az elektronikus számlázás konfigurálásában használt konfigurálási és tervezési tapasztalatokat. Az erőforrások, például a környezetek és az elektronikus számlázás funkcióját az RCS szolgáltatásban lehet létrehozni, karbantartani és kezelni. Amikor az erőforrások készen állnak, megjelennek az elektronikus számlázási szolgáltatásban.

Az RCS-ekkel kapcsolatos további információ: [Regulatory Configuration Services (RCS) – globalizációs funkciók](rcs-globalization-feature.md).

Az RCS regisztrációját a Szabályozó konfigurációs [szolgáltatás oldalon regisztrálja](https://marketing.configure.global.dynamics.com/).

### <a name="step-2-install-the-add-in-for-microservices-in-microsoft-dynamics-lifecycle-services"></a>2. lépés: A Microsoft Dynamics mikroszolgáltatások bővítményének telepítése a Lifecycle Services szolgáltatásba

Az elektronikus számlázási szolgáltatás a Microsoft-adatforrásokban tárolt mikroszolgáltatások halmaza. Alapértelmezés szerint a Dynamics 365 Pénzügy Dynamics 365 Supply Chain Management felhasználóinak nincs hozzáférésük az elektronikus számlázási szolgáltatáshoz. Telepítenie kell bővítményként a Microsoft Dynamics Lifecycle Services (LCS) bővítményeként. A bővítmény telepítésekor a pénzügyi és az ellátásilánc-kezelési környezet regisztrálva van az elektronikus számlázási szolgáltatáshoz való csatlakozásra engedélyezett alkalmazások nyilvántartásában.

Ezt a lépést a [mikroszolgáltatások bővítményének telepítése a Lifecycle Services szolgáltatásba lépésenként tudja végrehajtani](e-invoicing-install-add-in-microservices-lcs.md).

### <a name="step-3-set-up-rcs"></a>3. lépés: RCS beállítása

Az RCS és az elektronikus számlázási szolgáltatás közötti integrációt be kell állítani. A fő összetevőket is be kell állítani.

Ezt a lépést az [RCS (Regulatory Configuration Service) beállítása útmutatóban lehet végrehajtani](e-invoicing-set-up-rcs.md).

### <a name="step-4-microsoft-power-platform-plug-in-admin-reference"></a>4. lépés: Microsoft Power Platform beépülő modul rendszergazdai hivatkozása

Egyes esetek esetében integráció szükséges a Dataverse hatókörben Microsoft Power Platform.

Ez a beállítás jelenleg kötelező, ha az indonéz elektronikus számlázási helyzetekben az Elektronikus számlázási megoldások modult használja. A szaúd-arábiai elektronikus számlázás esetén azonban nem kötelező. A további tudnivalókat [lásd az Elektronikus számlázás funkció elérhetősége ország vagy régió szerint](e-invoicing-country-specific-availability.md).

Ezt a lépést a beépülő modul [Microsoft Power Platform rendszergazdai hivatkozásában lehet végrehajtani](e-invoicing-power-platform-plug-in.md).

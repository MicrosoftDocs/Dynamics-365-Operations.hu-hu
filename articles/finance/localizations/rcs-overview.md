---
title: Regulatory Configuration Service
description: Ez a cikk áttekintést nyújt a szabályozó konfigurációs szolgáltatás (RCS) lehetőségeiről, és bemutatja a szolgáltatáshoz való hozzáférést.
author: kfend
ms.date: 06/04/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.custom: 97423,  ""intro-internal
ms.assetid: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization
ms.openlocfilehash: c04b13ef05424b27b5abcc2ac7490a7b75797bf5
ms.sourcegitcommit: c6c2486be2359bd30106f7f52bda788239147d8c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/22/2022
ms.locfileid: "9713917"
---
# <a name="regulatory-configuration-service"></a>Regulatory Configuration Service

[!include [banner](../includes/banner.md)]

A Regulatory Configuration Service (RCS) önálló tervezői és életciklus-kezelési szolgáltatás a kódmentes/alacsony kódú globalizációs funkciókhoz. Az RCS lehetővé teszi, hogy a globalizációs felek bővítsék és testreszabják az adózás, az e-számlázás, a hatósági jelentések, a bank és az üzleti dokumentumok globalizációs területeit, anélkül, hogy a fejlesztőket be kell vonni. Ez a kódmentes/alacsony kódú globalizációs megközelítés a létrehozáshoz vagy a kiterjesztéshez egyszerűbbé, gyorsabbá és költség hatékonyabbá teszi a globalizációt.

Az RCS a következő funkciókat kínálja:

- Az elektronikus jelentés (ER) által biztosított összes funkció támogatása.
- Előfeltétele az új globalizációs mikroszolgáltatások konfigurálásának.
- Elektronikus számlázás támogatása. További tájékoztatásért lásd: [Elektronikus számlázás](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/electronic-invoicing-add-on-dynamics-365-ga).
- Támogatja az adószámítást. További információ: [Adószolgáltatás](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/tax-service-preview).
- A globalizációs funkció új funkcióinak támogatása, amely egyszerűbbé teszi a többösszetevős funkciók életciklus-kezelését, és további lehetőségeket biztosít a műveletek konfigurálása és a funkcióparaméterek beállítása során. A további tudnivalókat lásd: [Regulatory Configuration Service – egyszerűsített globalizációs funkciókezelés a globalizációs szolgáltatásoknál](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services).
- Az egyéni konfigurációk központosított közzétételének, tárolásának és megosztásának támogatása a globális tárházban a konfigurálás egyszerűsítése érdekében, a Microsoft Dynamics Lifecycle Services (LCS) használata nélkül.

## <a name="access-rcs"></a>RCS-hozzáférés

Az RCS szolgáltatásra a [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/) lapon regisztrálhat, illetve bejelentkezhet oda.

![RCS feliratkozás és bejelentkezés.](media/202103_RCS%20Marketing%20page_updated_1.jpg)

A **Regulatory Configuration Service** oldalon ellenőrizze és fogadja el a szolgáltatás használatára vonatkozó kiegészítő feltételeket, majd válasszon a következő gombok közül:

- **Regisztrálja magát**, ha első alkalommal használja a szolgáltatást, és egy üzleti e-mail-címet használ a szervezet számára szolgáltatási környezet nyújtásához.
- **Jelentkezzen be**, ha korábban már regisztrált a szolgáltatásra, és szeretné elérni a szervezeti környezetet.

> [!NOTE] 
> A regisztráció után javasoljuk, hogy adjon hozzá egy további SysAdmin felhasználót az RCS-környezethez. Ez a felhasználó lesz a környezet társadminisztrátora. Ez segít az RCS-környezethez való hozzáférés stabilitásának biztosításában, mivel a SysAdmin szerepkör a környezet felhasználóinak kezelésére szolgál. Felhasználókat az **RCS munkaterület > Rendszeradminisztráció** használatával adhat hozzá.

## <a name="regional-availability"></a>Regionális elérhetőség

Az RCS általában a következő régiókban érhető el:

- Amerikai Egyesült Államok
- India
- Franciaország
- Európa

A régiók teljes listájáért lásd: [Dynamics 365 és Power Platform: Elérhetőség, adatok helye, nyelv és honosítás](https://aka.ms/dynamics_365_international_availability_deck).

> [!NOTE] 
> Az RCS jelenleg nem érhető el a Kormányzati közösségi felhő (GCC) számára.

## <a name="rcs-default-company"></a>RCS alapértelmezett vállalat

Az RCS által használt időtervezési funkciók az összes vállalat között meg vannak osztva. Nincsenek vállalatspecifikus funkciók. Ezért javasoljuk, hogy az RCS-környezetben egy vállalatot, a **DAT** vállalatot használja.

Bizonyos helyzetekben azonban érdemes az ER-formátumokat egy adott jogi személyhez kapcsolódó paraméterekkel használni. Csak ilyen esetben érdemes az alapértelmezett vállalatváltót használni. Például lásd: [ER-formátum konfigurálása a jogi személyenként meghatározott paraméterek használatára](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-configure-format.md).

## <a name="related-rcs-documentation"></a>Kapcsolódó RCS-dokumentáció

A következő témakörökben bővebben olvashat a kapcsolódó összetevőkről:

- **RCS:**

    - [Hozzon létre ER-konfigurációkat a RCS-ben, és töltse fel őket a globális tárházba](rcs-global-repo-upload.md)

- **Globális adattár:**

    - [ER-konfiguráció létrehozása és feltöltés a globális adattárba](rcs-global-repo-upload.md)
    - [Konfiguráció megosztása a globális adattárban](rcs-global-repo-share-configuration.md)
    - [Továbbfejlesztett szűrés a globális adattárban](enhanced-filtering-global-repo.md)
    - [ER-konfigurációk letöltése a globális adattárból](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md)
    - [Konfigurációk megszüntetése a globális adattárban](discontinuing-configurations-rcs-global-repo.md)
    - [Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) tárhely kivezetése](rcs-lcs-repo-dep-faq.md)

- **Globalizációs funkciók:**

    - [Regulatory Configuration Service (RCS) – Globalizációs jellemzők](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services)


## <a name="troubleshooting-rcs-sign-up"></a>RCS feliratkozás hibaelhárítása

Ha a szolgáltatási oldalról regisztrál RCS-re, akkor a következő, az Azure Active Directory (Azure AD) szolgáltatással kapcsolatos probléma merülhet fel. A kapott hibaüzenet azt jelzi, hogy az RCS regisztrációja jelenleg ki van kapcsolva, és be kell kapcsolni, mielőtt befejezheti a regisztrációt.

![RCS-regisztráció hibaüzenete.](media/01_RCSSignUpError.jpg)

A probléma oka az, hogy blokkolva van az ad hoc előfizetés regisztrációja, ezért az `AllowAdHocSubscriptions` tulajdonságot engedélyezni kell a bérlőben. 

- Ha az IT részleg kezeli a szervezet Azure-bérlőit, vegye fel a kapcsolatot az osztállyal, és jelentse a problémát.
- Ha Ön felelős az Azure-bérlők kezeléséért, a problémákat javíthatja a [Mi az Önálló Azure Active Directory-regisztráció](/azure/active-directory/enterprise-users/directory-self-service-signup#how-do-i-control-self-service-settings) rész lépéseivel.

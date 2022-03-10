---
title: Szolgáltatási környezetek és a kapcsolódó alkalmazások konfigurálása
description: Ez a témakör arról nyújt tájékoztatást, hogyan kell konfigurálni a szolgáltatási környezeteket és a kapcsolódó alkalmazásokat.
author: dkalyuzh
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: c3366e75b4a6d3f33a1aac9e444236d9ae57c829
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371880"
---
# <a name="configure-service-environments-and-connected-applications"></a>Szolgáltatási környezetek és a kapcsolódó alkalmazások konfigurálása

[!include [banner](../includes/banner.md)]

Ez a témakör arról nyújt tájékoztatást, hogyan kell konfigurálni a szolgáltatási környezeteket és a kapcsolódó alkalmazásokat. Ehhez a folyamathoz három lépésből kell áll. Az 1. lépést kötelező megadni, a 2. és a 3. lépést pedig nem kötelező megadni.

## <a name="step-1-create-a-service-environment"></a>1. lépés: Szolgáltatási környezet létrehozása

A szolgáltatási környezet létrehozása során határozza meg azon felhasználók listáját, akik telepítheti a globálisítási funkciókat. Bizonyos helyzetekben megadhatja a külső alkalmazások listáját, amelyek kommunikálhatnak az elektronikus számlázási szolgáltatással. Állítsa be a számsorozatokat, ha használni fogja őket az adott helyzetben.

Ezt a lépést a szolgáltatási környezetekben [lehet végrehajtani](e-invoicing-service-environments.md).

## <a name="step-2-add-certificates-and-secrets"></a>2. lépés: Tanúsítványok és tanúsítványok hozzáadása

Hivatkozás hozzáadása a kulcshoz Microsoft Azure és az 5000-hez, hogy az esetekben használva legyenek. Ezt a lépést kötelező megadni, ha a feldolgozási folyamatban található műveletek tanúsítványokat és tanúsítványokat használnak a digitális aláíráshoz vagy a külső webes szolgáltatásokkal való kommunikációhoz.

Ezt a lépést a vevői tanúsítványok és [azok tanúsítványainél kell végrehajtani](e-invoicing-customer-certificates-secrets.md).

## <a name="step-3-configure-connected-applications"></a>3. lépés: A csatlakoztatott alkalmazások konfigurálása

Dynamics 365 Finance Dynamics 365 Supply Chain Management Az alkalmazások és az elektronikus számlázás közötti kommunikáció beállításához konfigurálnia kell a Pénzügy vagy az Ellátásilánc-kezelés modult, hogy az elektronikus számlázási szolgáltatás hívását összeállítva az üzleti adatokat egy egységes szerkezetben készítse elő, és a szükséges elektronikus formátumra átalakítható egységes struktúrában. A alkalmazásoknak a szolgáltatástól kapott válaszokat is helyesen kell feldolgozniuk. Ezt a konfigurációt közvetlenül a Pénzügyi vagy ellátásilánc-kezelési környezetben, vagy a szabályozó konfigurációs szolgáltatásban (RCS) is befejezheti. Ha az RCS szolgáltatásban konfigurálja a konfigurációt, akkor azt telepítheti a Pénzügyi vagy Ellátásilánc-kezelési környezetben. Ebben a lépésben regisztrálja a csatlakoztatott alkalmazást paramétertelepítésre.

Ezt a lépést a Kapcsolódó alkalmazásoknál [lehet végrehajtani](e-invoicing-connected-applications.md).

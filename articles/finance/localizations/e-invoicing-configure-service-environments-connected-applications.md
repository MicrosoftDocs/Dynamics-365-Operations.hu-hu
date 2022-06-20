---
title: Szolgáltatáskörnyezetek és csatlakoztatott alkalmazások konfigurálása
description: Ez a cikk a szolgáltatási környezetek és a csatlakoztatott alkalmazások konfigurálásán keresztül nyújt tájékoztatást.
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
ms.openlocfilehash: c1bb3f784148f04c01223ac4e280a18bacfe0e51
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853222"
---
# <a name="configure-service-environments-and-connected-applications"></a>Szolgáltatáskörnyezetek és csatlakoztatott alkalmazások konfigurálása

[!include [banner](../includes/banner.md)]

Ez a cikk a szolgáltatási környezetek és a csatlakoztatott alkalmazások konfigurálásán keresztül nyújt tájékoztatást. Ehhez a folyamathoz három lépésből kell áll. Az 1. lépést kötelező megadni, a 2. és a 3. lépést pedig nem kötelező megadni.

## <a name="step-1-create-a-service-environment"></a>1. lépés: Szolgáltatási környezet létrehozása

A szolgáltatási környezet létrehozása során határozza meg azon felhasználók listáját, akik telepítheti a globálisítási funkciókat. Bizonyos helyzetekben megadhatja a külső alkalmazások listáját, amelyek kommunikálhatnak az elektronikus számlázási szolgáltatással. Állítsa be a számsorozatokat, ha használni fogja őket az adott helyzetben.

Ezt a lépést a szolgáltatási környezetekben [lehet végrehajtani](e-invoicing-service-environments.md).

## <a name="step-2-add-certificates-and-secrets"></a>2. lépés: Tanúsítványok és tanúsítványok hozzáadása

Hivatkozás hozzáadása a kulcshoz Microsoft Azure és az 5000-hez, hogy az esetekben használva legyenek. Ezt a lépést kötelező megadni, ha a feldolgozási folyamatban található műveletek tanúsítványokat és tanúsítványokat használnak a digitális aláíráshoz vagy a külső webes szolgáltatásokkal való kommunikációhoz.

Ezt a lépést a vevői tanúsítványok és [azok tanúsítványainél kell végrehajtani](e-invoicing-customer-certificates-secrets.md).

## <a name="step-3-configure-connected-applications"></a>3. lépés: A csatlakoztatott alkalmazások konfigurálása

A Dynamics 365 Pénzügy Dynamics 365 Supply Chain Management és az Elektronikus számlázás közötti kommunikáció beállításához konfigurálnia kell a Pénzügy vagy az Ellátásilánc-kezelés modult, hogy az elektronikus számlázási szolgáltatás hívását össze kell állítani, és az üzleti adatokat egységes szerkezetben kell előkészíteni, és a szükséges elektronikus formátumra átalakítható egységes struktúrában. A alkalmazásoknak a szolgáltatástól kapott válaszokat is helyesen kell feldolgozniuk. Ezt a konfigurációt közvetlenül a Pénzügyi vagy ellátásilánc-kezelési környezetben, vagy a szabályozó konfigurációs szolgáltatásban (RCS) is befejezheti. Ha az RCS szolgáltatásban konfigurálja a konfigurációt, akkor azt telepítheti a Pénzügyi vagy Ellátásilánc-kezelési környezetben. Ebben a lépésben regisztrálja a csatlakoztatott alkalmazást paramétertelepítésre.

Ezt a lépést a Kapcsolódó alkalmazásoknál [lehet végrehajtani](e-invoicing-connected-applications.md).

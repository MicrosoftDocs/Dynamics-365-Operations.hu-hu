---
title: Vevői tanúsítványok és tanúsítványok
description: Ez a témakör bemutatja, hogy hogyan lehet beállítani a vevői tanúsítványokat és az elektronikus számlázást.
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
ms.openlocfilehash: 1325cad95e9a6dc470691f5f168439fccaaa78e1
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371899"
---
# <a name="customer-certificates-and-secrets"></a>Vevői tanúsítványok és tanúsítványok

[!include [banner](../includes/banner.md)]

Ha már létezik kulcsHivatkozás a szabályozó konfigurációs szolgáltatásban (RCS), létrehozhat hivatkozásokat a Microsoft Azure fő tanúsítványra és tanúsítványra. Ha még nem tartalmaz KeyKulcs hivatkozást, [akkor](e-invoicing-service-environments.md) a létrehozásukról a szolgáltatási környezetekben található tájékoztatás.

## <a name="create-certificates-and-secrets"></a>Tanúsítványok és tanúsítványok létrehozása

A következő lépések szerint hozhatja létre és állíthatja be a tanúsítványokat és tanúsítványokat.

1. Jelentkezzen be a RCS-fiókba.
2. A **Globalizációs funkció** munkaterületen a **Környezet** szakaszban válassza ki az **Elektronikus számlázás bővítmény** csempét.
3. A Környezet **beállítása lapon**, a munkaablakban válassza a Szolgáltatáskörnyezetek **beállítást**.
4. A Szolgáltatási **környezetek** lapon, a munkaablakban válassza ki **a Kulcs paramétereit**.
5. A Kulcs **– Paraméterek** lapon válasszon ki egy Key Inss Key Paraméter-hivatkozást, **majd** a Tanúsítványok szakaszban válassza a Hozzáadás **gombra**.
6. A Név **mezőbe** írja be a kulcs tanúsítványának vagy titkos tanúsítványának nevét. A további tudnivalókat [lásd Az Azure-tárfiók létrehozása az Azure-portálon](e-invoicing-create-azure-storage-account-azure-portal.md).
7. Adjon meg egy leírást a **Leírás** mezőben.
8. A Típus **mezőben** válassza a Tanúsítvány lehetőséget, **ha** a kulcstárolóban tárolt tanúsítványra hivatkozik. Válassza **a Titkos** lehetőséget, ha a kulcskulcsban tárolt titkos információra hivatkozik.
9. Válassza a **Mentés** lehetőséget.

> [!NOTE]
> Bizonyos helyzetekben az .cer fájlnév kiterjesztésű nyilvános tanúsítványokat kell használni. A Kulcs Raktározás kulcs nem támogatja azonban az ilyen típusú tanúsítványok importálását és tárolását főkénttanúsítványként. Ilyen esetben az .cer fájlt Base-64 kódolású X.509 (fájlként kell menteni. CER) karakterlánc. Ezután egy Titkos kulcs titkos kulcsában tárolja azt a karakterláncot, **amely a BEGIN** **CERTIFICATE** sor és a fájl ZÁRÓ TANÚSÍTVÁNYsora között megjelenik. A szolgáltatási környezetben továbbra is létre kell hoznia a kulcsrekordra való hivatkozást, és tanúsítványra kell állítania a Típus **mezőt** **·**.

## <a name="create-a-chain-of-certificates"></a>Tanúsítványlánc létrehozása

Ha az ország-/régióspecifikus számlák tanúsítványlánccal kell digitális aláírást alkalmazni, illetve biztonságos (Secure Sockets Layer \[SSL\]) kapcsolatot kell létesíteni a külső webes szolgáltatásokkal, hozzon létre tanúsítványláncot, ahol a tanúsítványok a következő sorrendben vannak:

1. Főtanúsítványok
2. Köztes tanúsítványok
3. Végfelhasználói tanúsítványok

A legfelső szintű tanúsítvány-hatóságok a tanúsítványok megbízható forrásai. A köztes hitelesítésszolgáltatói tanúsítványok olyan áthidaló tanúsítványok, amelyek összekapcsolják a végfelhasználói tanúsítványokat a legfelső szintű hitelesítésszolgáltatói tanúsítványokkal.

A következő lépések szerint hozhatja létre és állíthatja be a tanúsítványláncot.

1. Válassza a Kulcs **Paraméterei** oldal munkaablakában a Tanúsítványlánc **lehetőséget**.
2. Tanúsítványlánc létrehozásához válassza az **Új** lehetőséget.
3. A Név **mezőbe** írja be a tanúsítványlánc nevét.
4. Adjon meg egy leírást a **Leírás** mezőben.
5. A **Tanúsítványok** szakaszban válassza a **Hozzáadás** lehetőséget, ha tanúsítványt szeretne hozzáadni a lánchoz.
6. A **Fel** és a **Le** gombbal módosíthatja a tanúsítványnak a láncon belül elfoglalt pozícióját. A hitelesítésszolgáltatói gyökértanúsítványt a lista tetején, a végfelhasználói tanúsítványt pedig alul tartsa meg.
7. Válassza a **Mentés** lehetőséget.

Az RCS-ben annyi kulcshivatkozást hozhat létre, amennyit csak szeretne. Ne feledje, hogy a tárolás megosztott hozzáférési aláírásának (SAS) titkos kulcsa segítségével egy adott szolgáltatási környezetet kapcsolhat a Key Társítás hivatkozáshoz. Hivatkozni lehet a kulcs tanúsítványára és tanúsítványára, amelyek a szolgáltatási környezet beállítása során használt tároló SAS-token titkos tárolójában vannak tárolva.

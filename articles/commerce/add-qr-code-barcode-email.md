---
title: QR-kód vagy vonalkód hozzáadása tranzakciós és bevételezési e-mailekhez
description: Ez a témakör bemutatja, hogy hogyan lehet a rendelési azonosítókat képviselő QR-kódokat és vonalkódokat beszúrni a tranzakciós és bevételezési e-mailekbe a Microsoft Dynamics 365 Commerce rendszerben.
author: bicyclingfool
ms.date: 03/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Commerce, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-02-16
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 9eea69f9618d4387f5d6320620dfee5d74813fc0
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019539"
---
# <a name="add-a-qr-code-or-bar-code-to-transactional-and-receipt-emails"></a>QR-kód vagy vonalkód hozzáadása tranzakciós és bevételezési e-mailekhez

[!include [banner](includes/banner.md)]

Ez a témakör bemutatja, hogy hogyan lehet a rendelési azonosítókat képviselő QR-kódokat és vonalkódokat beszúrni a tranzakciós és bevételezési e-mailekbe a Microsoft Dynamics 365 Commerce rendszerben.

A QR-kódok és vonalkódok könnyen beemelhetők a tranzakciós e-mailekbe, hogy felgyorsítsák a rendeléskeresési folyamatot kiskereskedelmi környezetben. A QR-kódok és vonalkódok e-mailbe történő beszúrása során egy HTML **\<img\>** címkét kell használni, amely egy generáló és renderelő szolgáltatástól QR-kódot vagy vonalkódképet kér. A Microsoft nem biztosítja ezt a szolgáltatást. Vannak azonban olyan ingyenes vagy olyan szolgáltatások, amelyek kiszolgálnak olyan QR-kódokat vagy vonalkódokat, amelyek dinamikusan, lekérdezési sztringben átadott érték alapján jönnek létre.

## <a name="add-a-qr-code-or-bar-code-to-a-transactional-email"></a>QR-kód vagy vonalkód hozzáadása tranzakciós e-mailhez

Ha egy e-kereskedelmi beszerzés részeként küldött tranzakciós e-mailbe QR-kódot vagy vonalkódot szeretne beilleszteni, kövesse ezeket a lépéseket.

1. Nyissa meg a tranzakciós e-mail-sablon forrás HTML-jét, és adjon hozzá egy HTML **\<img\>** címkét, amely a QR-kód- vagy a vonalkód-szolgáltatásra mutat. Íme, egy példa.

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%salesid%&param1=value1&param2=value2" alt="%salesid%" />
    ```

    Itt látható az előző példa magyarázata:

    - **YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE**: a QR-kód- vagy vonalkódszolgáltatás tartománya.
    - **data**: az a paraméter, amelyet a QR-kód- vagy a vonalkód-szolgáltatás használ a QR-kódként vagy vonalkódként renderelni kívánt tartalom fogadására.

        A **%salesid%** értéket hozzá kell rendelni ehhez a paraméterhez. Ebben a példában figyelje meg, hogy a rendszer az értéket a kép helyettesítő szövegeként is használja.

    - **param1** és **param2**: további, nem kötelező paraméterek.

1. Menjen a **Retail és Commerce \> Központ beállítása \> Paraméterek \> Szervezeti e-mail-sablonok** pontra, és töltse fel a frissített HTML-kódot a megfelelő tranzakciós e-mail-sablonba.

> [!NOTE]
> A paraméterek eltérhetnek a QR-kód- és vonalkód-szolgáltatók függvényében. Ezért mindenképpen forduljon a szolgáltatóhoz, és erősítse meg a paramétereket, amelyekhez értékeket kell rendelnie.

## <a name="add-a-qr-code-or-bar-code-to-a-receipt-email"></a>QR-kód vagy vonalkód hozzáadása bevételezési e-mailhez 

Ha egy QR-kódot vagy vonalkódot szeretne beilleszteni a pénztárnál (POS) történő vásárlás után elküldendő bevételezési e-mailbe, kövesse ezeket a lépéseket.

1. Nyissa meg a bevételezési e-mail-sablon forrás HTML-jét, és adjon hozzá egy HTML **\<img\>** címkét, amely a QR-kód- vagy a vonalkód-szolgáltatásra mutat. Alább látható egy példa.

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%receiptid%&param1=value1&param2=value2" alt="%receiptid%" />
    ```

    Itt látható az előző példa magyarázata:

    - **YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE**: a QR-kód- vagy vonalkódszolgáltatás tartománya.
    - **data**: az a paraméter, amelyet a QR-kód- vagy a vonalkód-szolgáltatás használ a QR-kódként vagy vonalkódként renderelni kívánt tartalom fogadására.

        A **%receiptid%** értéket hozzá kell rendelni ehhez a paraméterhez. Ebben a példában figyelje meg, hogy a rendszer az értéket a kép helyettesítő szövegeként is használja.

    - **param1** és **param2**: további, nem kötelező paraméterek.

1. Menjen a **Retail és Commerce \> Központ beállítása \> Paraméterek \> Szervezeti e-mail-sablonok** pontra, és töltse fel a frissített HTML-kódot abba az e-mail-sablonba, amelynek e-mail-azonosítója: **emailrecpt**.

> [!NOTE]
> A paraméterek eltérhetnek a QR-kód- és vonalkód-szolgáltatók függvényében. Ezért mindenképpen forduljon a szolgáltatóhoz, és erősítse meg a paramétereket, amelyekhez értékeket kell rendelnie.

## <a name="additional-resources"></a>További erőforrások

[E-mailes nyugták küldése Modern POS (MPOS) szolgáltatásból](email-receipts.md)

[E-mail-sablonok létrehozása tranzakciós eseményekhez](email-templates-transactions.md)

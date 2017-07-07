---
title: "Adatfrissítés védőfalkörnyezetben"
description: "Ez a témakör bemutatja, hogyan végezhető el az adatfrissítés AX 2012 rendszerről Dynamics 365 for Finance and Operations rendszerre védőfalkörnyezetben."
author: tariqbell
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Operations, UnifiedOperations, Platform
ms.search.region: Global
ms.author: tabell
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: Platform update 8
ms.translationtype: Human Translation
ms.sourcegitcommit: 6816e3820ab77c71bbf9bde4a068375448331671
ms.openlocfilehash: 7140bf740f37a5eb970a5103750a7095d12a33cc
ms.contentlocale: hu-hu
ms.lasthandoff: 06/15/2017

---

# <a name="data-upgrade-in-a-sandbox-environment"></a>Adatfrissítés védőfalkörnyezetben

[!include[banner](../includes/banner.md)]

[!include[upgrade banner](../includes/upgrade-banner.md)]

A feladat kimenete egy védőfalkörnyezetben használható frissített adatbázis. A védőfalkörnyezet olyan környezet, amelyben az üzleti felhasználók és a funkcionális csapat tagjai ellenőrizhetik az alkalmazás funkcióit. Ez a funkció magában foglalja a testreszabásokat és a Microsoft Dynamics AX 2012 rendszerből származó adatokat.

Hangsúlyosan javasoljuk, hogy az adatfrissítési folyamatot fejlesztői környezetben futtassa megosztott fejlesztői környezetben történő futtatása előtt, mert ez a megközelítés csökkenti a sikeres adatfrissítéshez szükséges teljes időt. További információkért lásd: [Frissítés – Adatfrissítés fejlesztői környezetben](prepare-data-upgrade.md)

## <a name="overview-of-the-sandbox-data-upgrade-process"></a>A védőfalkörnyezetben történő adatfrissítési művelet áttekintése

Az adatfrissítés védőfalkörnyezetben történő elvégzése előtt az adatokat már fejlesztői környezetben frissítette a következő részben leírtaknak megfelelően: [Adatfrissítés fejlesztői környezetben](prepare-data-upgrade.md). A két folyamat nagyon hasonló. A fő különbség hogy a védőfalkörnyezet a Microsoft Azure SQL adatbázist használja az adattárolásra, a fejlesztői környezet pedig Microsoft SQL Server rendszert használ. Az adatbázis rétegében levő műszaki különbség miatt némiképp módosítania kell az adatfrissítési eljárást egy védőfalkörnyezetben, mert az AX 2012 adatbázispéldány másolata nem állítható vissza egyszerű kattintással az SQL Database adatbázisba.

![Védőfalkörnyezet frissítés folyamata](./media/data-upgrade-sandbox.png)

A frissítési folyamat során az alábbi magas szintű lépéseket kell elvégezni.

1. Készítsen másolatot az AX 2012 adatbázisról. Azt ajánljuk, hogy használja a másolatot, mivel az exportálandó másolatban törölnie kell bizonyos objektumokat.
2. Exportálja az adatbázis másolatát egy bacpac fájlba az SQLPackage.exe nevű ingyenes SQL Server eszközzel. Ez az eszköz egy speciális típusú adatbázismentést biztosít, amelyet az SQL Database adatbázisba importálhat.
3. Töltse fel a bacpac fájlt az Azure-tárhelyre.
4. Töltse le a bacpac fájlt az Application Object Server (AOS) gépre a védőfalkörnyezetben, majd importálja azt az SQLPackage.exe használatával. Ezután futtatnia kell egy parancsfájlt az importált adatbázisra az SQL adatbázis-felhasználók alaphelyzetbe állításához.
5. Futtassa a MajorVersionDataUpgrade.zip csomagot az adatfrissítés importált adatbázisra történő futtatásához.

## <a name="create-a-copy-of-the-ax-2012-database"></a>Másolat készítése az AX 2012 adatbázisról

Létre kell hoznia egy másolatot a frissíteni kívánt AX 2012 adatbázisról, mivel bizonyos objektumokat törölnie kell az adatbázisból. Ezek az objektumok magukban foglalják a Microsoft Windows hitelesítési felhasználókat. Ezek a változtatások használhatatlanná teszik a módosított adatbázist az AX 2012 rendszeren. Ebben a lépésben létre fogja hozni az adatbázis biztonsági másolatát, és törölni fogja ezeket az objektumokat.

Ezt a lépést az adatbázis-rendszergazdának (DBA) vagy hasonló tudással és tapasztalattal rendelkező személynek kell végrehajtania.

Az adatbázis másolatának létrehozásához készítsen biztonsági másolatot az eredeti adatbázisről, és állítsa vissza az új néven. Győződjön meg arról, hogy elég hely áll rendelkezésre mindkét adatbázishoz. A másolatot más kiszolgálón is létrehozhatja. Az adatbázist futtató SQL Server példányának verziója nem fontos.

Íme egy példa az adatbázis másolatát létrehozó kódra. Ezt a példát a megadott adatbázis nevének megfelelően kell módosítania.

    BACKUP DATABASE [AxDB] TO  DISK = N'D:\Backups\axdb_copyForUpgrade.bak' WITH NOFORMAT, NOINIT,  
    NAME = N'AxDB_copyForUpgrade-Full Database Backup', SKIP, NOREWIND, NOUNLOAD, COMPRESSION,  STATS = 10
    GO

    RESTORE DATABASE [AxDB_copyForUpgrade] FROM  DISK = N'D:\Backups\axdb_copyForUpgrade.bak'   WITH  FILE = 1,  
    MOVE N'AXDBBuild_Data' TO N'F:\MSSQL_DATA\AxDB_copyForUpgrade.mdf',  
    MOVE N'AXDBBuild_Log' TO N'G:\MSSQL_LOGS\AxDB_CopyForUpgrade.ldf',  
    NOUNLOAD,  STATS = 5

A másolat létrehozása után futtassa a következő (T-SQL) Transact-SQL parancsfájlt.
TEENDŐ 

### <a name="export-the-copied-database-to-a-bacpac-file"></a>Az adatbázis másolatának bacpac fájlba történő exportálása

Exportálja az adatbázis másolatát egy bacpac fájlba az SQLPackage.exe nevű eszközzel. Ezt a lépést az adatbázis-rendszergazdának vagy a csoport ezzel egyenértékű tudással rendelkező tagjának kell végrehajtania.

Nagyon fontos, hogy telepítse az SQL Server Management Studio legújabb verzióját a lépés megkezdése előtt. Annak ellenére, hogy a Management Studio korábbi verzióiban szerepel a SQLPackage, nem fog megfelelően működni ehhez a lépéshez a legújabb verzió telepítése nélkül.

Ez a lépés fontos, mivel az exportálást újra el kell végezni a leállás során az élesítés előtt. Néhány tanács:

- A bacpac nagyon igénybe veszi az operációs rendszert és a processzort. Ezért futtassa az exportálást nagy teljesítményű gépen.
- Az SQLPackage programot helyileg, az adatbázist tároló számítógépen kell futtatni. Ne futtassa az SQLPackage programot azon a helyi hordozható számítógépen, amellyel az adatbázist tároló számítógéphez csatlakozik, mert ez a folyamat hálózatigényes is.

Ezután nyisson meg egy **parancssori** ablakot rendszergazdai módban, majd futtassa a következő parancsokat.

    cd C:\Program Files (x86)\Microsoft SQL Server\130\DAC\bin\

    SqlPackage.exe /a:export /ssn:localhost /sdn:<database to export> /tf:D:\Exportedbacpac\my.bacpac /p:CommandTimeout=1200 /p:VerifyFullTextDocumentTypesSupported=false

Itt látható a paraméterek magyarázata:

- **ssn** (forráskiszolgáló neve) – Az exportálásra használni kívánt SQL Server neve. A folyamathoz ez a paraméter mindig legyen **localhost** értékre állítva.
- **sdn** (forrásadatbázis neve) – Az exportálandó adatbázis neve.
- **tf** (célfájl) – Az exportálási célfájl elérési útja és fájlneve. A mappának már léteznie kell, de a fájlt a folyamat hozza létre.
- **/p:CommandTimeout** – A lekérdezésenkénti időtúllépés. Ez a paraméter lehetővé teszi a nagyobb táblázatok időtúllépés nélkül történő exportálását.

### <a name="upload-the-bacpac-file-to-azure-storage"></a>A bacpac fájl feltöltése az Azure-tárhelyre

Töltse fel a bacpac fájlt az Azure-tárhelyre. Lásd: UsingStorageExplorer.docx TEENDŐ

### <a name="import-the-bacpac-file-into-sql-database"></a>A bacpac fájl importálása az SQL Database adatbázisba

Ebben a lépésben importálni fogja az exportált bacpac fájlt az SQL Database azon példányába, amelyet a védőfalkörnyezet használ. Előbb telepítenie kell a Management Studio legújabb verzióját a védőfalkörnyezet AOS-számítógépén. Ezután importálja a fájlt a SQLPackage.exe eszközzel.

Ezeket a feladatokat közvetlenül az AOS-számítógépen fogja végezni a védőfalkörnyezetben, mivel a tűzfalszabályok korlátozzák a hozzáférést az SQL Database példányához. Azonban az AOS-számítógép használatával hozzáférhet.

Az exportáláshoz rendelkeznie kell a Management Studio legújabb verziójával még az importálás előtt. Ez a lépés nem működik régebbi verzió esetén.

A megfelelő teljesítmény érdekében azt ajánljuk, hogy a bacpac fájlt az AOS-számítógépen a D meghajtóra helyezze. Azure virtuális gépeken (VMs) a D meghajtó egy fizikai lemez, amelynek teljesítménye általában nagyobb, mint a többi elérhető lemezé.

Nyisson meg egy **parancssori** ablakot rendszergazdai módban, majd futtassa a következő parancsokat.

    cd C:\Program Files (x86)\Microsoft SQL Server\130\DAC\bin\

    SqlPackage.exe /a:import /sf:D:\Exportedbacpac\my.bacpac /tsn:<azure sql database server name>.database.windows.net /tu:sqladmin /tp:<password from LCS> /tdn:<New database name> /p:CommandTimeout=1200 /p:DatabaseEdition=Premium /p:DatabaseServiceObjective=P1

Itt látható a paraméterek magyarázata:

- **tsn** (célkiszolgáló neve) – Az SQL Azure kiszolgáló neve, ahova importálni szeretne. A név megtalálható az LCS szolgáltatásban. Adja hozzáa a **. database.windows.net** utótagot.
- **tdn** (céladatbázis neve) – Azon adatbázis neve, ahova importálni szeretne. Az adatbázis már nem létezhet. Az importálási folyamat hozza létre az adatbázist.
- **sf** (forrásfájl) – Azon fájl neve és útvonala, ahonnan importálni szeretne.
- **tp** (céljelszó) – A cél SQL Database példány SQL-jelszava.
- **tu** (célfelhasználó) – A cél SQL Database példány SQL-felhasználója. Az **sqladmin** használatát javasoljuk. A felhasználó jelszavát lekérheti az LCS projektből.
- **/p:CommandTimeout** – A lekérdezésenkénti időtúllépés. Ez a paraméter lehetővé teszi a nagyobb táblázatok időtúllépés nélkül történő exportálását.
- **/p:DatabaseServiceObjective** – A létrehozott adatbázis szolgáltatási szintje. A Management Studio segítségével ellenőrizheti a meglévő adatbázis értékét. Kattintson a jobb gombbal az adatbázisra, majd válassza a **Tulajdonságok** lehetőséget.

A parancsok futtatása után a következő figyelmeztetést fogja kapni. Nyugodtan figyelmen kívül hagyhatja azt.

![Védőfalkörnyezet-hiba](./media/sandbox-2.png)
 
### <a name="run-the-majorversiondataupgradezip-package"></a>Futtassa a MajorVersionDataUpgrade.zip csomagot

Futtassa az adatfrissítési telepíthető adatcsomagot a leírtak szerint [Adatok frissítése a fejlesztői, bemutató vagy védőfalkörnyezetben](upgrade-data-to-latest-update.md).

### <a name="upgrade-a-copy-of-the-database-in-a-development-environment"></a>Az adatbázis egy példányának frissítése fejlesztői környezetben

Hasznos ugyanazon adatbázis példányának frissítése fejlesztői környezetben. Ha a fejlesztői környezetekhez rendelkezésre álló adatbázis-másolata van, sokkal könnyebb lesz megvizsgálni a frissített védőfalkörnyezetben talált hibákat.


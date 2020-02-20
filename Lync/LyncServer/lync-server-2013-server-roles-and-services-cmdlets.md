---
title: 'Lync Server 2013: 서버 역할 및 서비스 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles and services cmdlets
ms:assetid: ff3561de-043e-4071-88f7-8de3cded52f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415683(v=OCS.15)
ms:contentKeyID: 48185971
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92fb368f71d0af3ba876eed033c9c533dfdaf31d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-roles-and-services-cmdlets-in-lync-server-2013"></a><span data-ttu-id="e41dd-102">Lync Server 2013의 서버 역할 및 서비스 cmdlet</span><span class="sxs-lookup"><span data-stu-id="e41dd-102">Server roles and services cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e41dd-103">_**마지막으로 수정 된 항목:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="e41dd-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="e41dd-104">대부분의 Microsoft Lync Server 2013 구성 요소는 서버 역할 또는 서비스로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e41dd-104">Many Microsoft Lync Server 2013 components run as server roles or as services.</span></span> <span data-ttu-id="e41dd-105">Lync Server 2013에는 이러한 서버 역할 및 서비스를 관리 하는 데 사용할 수 있는 다양 한 cmdlet이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e41dd-105">Lync Server 2013 ships with a number of cmdlets that enable you to manage these server roles and services.</span></span>

<div>

## <a name="server-roles-and-services-cmdlets"></a><span data-ttu-id="e41dd-106">서버 역할 및 서비스 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e41dd-106">Server Roles and Services Cmdlets</span></span>

<span data-ttu-id="e41dd-107">서버 및 서비스 역할에 적용 되는 관리 작업 중 대부분은 Lync Server 제어판에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e41dd-107">Many (but not all) of the management tasks that apply to servers and service roles can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="e41dd-108">예를 들어 Lync Server 제어판을 사용 하 여 보관 서버 설정을 관리할 수 있으 나 주소록 서버 설정에서는 관리 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e41dd-108">For example, you can manage Archiving Server settings but not Address Book Server settings by using Lync Server Control Panel.</span></span> <span data-ttu-id="e41dd-109">그러나 이러한 모든 작업은 Lync Server 관리 셸 또는 스크립트 내에서 cmdlet을 사용 하 여 수행할 수 있습니다. 스크립트를 사용 하면 특정 작업을 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e41dd-109">However, all these tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script; using a script enables you to automate certain tasks.</span></span> <span data-ttu-id="e41dd-110">다음은 서버 역할 및 서비스 관리와 직접 관련 된 cmdlet 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="e41dd-110">The following is a list of cmdlets that relate directly to managing server roles and services:</span></span>

<span data-ttu-id="e41dd-111">**[Lync Server 2013의 주소록 서버 cmdlet](lync-server-2013-address-book-server-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="e41dd-111">**[Address Book Server cmdlets in Lync Server 2013](lync-server-2013-address-book-server-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-112">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-112">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-113">[새-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-113">[New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-114">[CsAddressBookConfiguration 제거](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-114">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-115">[설정-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-115">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-116">[업데이트-Update-csaddressbook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-116">[Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-117">[디버그-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-117">[Debug-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-118">[테스트-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-118">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-119">[테스트-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-119">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span></span>

<span data-ttu-id="e41dd-120">**[Lync Server 2013의 보관 및 모니터링 cmdlet](lync-server-2013-archiving-and-monitoring-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="e41dd-120">**[Archiving and Monitoring cmdlets in Lync Server 2013](lync-server-2013-archiving-and-monitoring-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-121">[Get-csarchivingconfiguration](https://technet.microsoft.com/library/Gg399012(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-121">[Get-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg399012(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-122">[Get-csarchivingconfiguration](https://technet.microsoft.com/library/Gg398471(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-122">[New-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg398471(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-123">[Get-csarchivingconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398951(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-123">[Remove-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg398951(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-124">[Get-csarchivingconfiguration](https://technet.microsoft.com/library/Gg413030(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-124">[Set-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg413030(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-125">[Export-csarchivingdata](https://technet.microsoft.com/library/Gg398452(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-125">[Export-CsArchivingData](https://technet.microsoft.com/library/Gg398452(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-126">[Invoke-csarchivingdatabasepurge-를 호출 합니다.](https://technet.microsoft.com/library/JJ204627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-126">[Invoke-CsArchivingDatabasePurge](https://technet.microsoft.com/library/JJ204627(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-127">[Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg425731(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-127">[Get-CsArchivingPolicy](https://technet.microsoft.com/library/Gg425731(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-128">[Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg398475(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-128">[Grant-CsArchivingPolicy](https://technet.microsoft.com/library/Gg398475(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-129">[Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg399032(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-129">[New-CsArchivingPolicy](https://technet.microsoft.com/library/Gg399032(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-130">[Grant-csarchivingpolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg425924(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-130">[Remove-CsArchivingPolicy](https://technet.microsoft.com/library/Gg425924(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-131">[Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg398294(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-131">[Set-CsArchivingPolicy](https://technet.microsoft.com/library/Gg398294(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-132">[CsArchivingServer](https://technet.microsoft.com/library/Gg398923(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-132">[Set-CsArchivingServer](https://technet.microsoft.com/library/Gg398923(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-133">[Get-cscdrconfiguration](https://technet.microsoft.com/library/Gg398298(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-133">[Get-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398298(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-134">[Get-cscdrconfiguration](https://technet.microsoft.com/library/Gg399018(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-134">[New-CsCdrConfiguration](https://technet.microsoft.com/library/Gg399018(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-135">[Get-cscdrconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398451(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-135">[Remove-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398451(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-136">[Get-cscdrconfiguration](https://technet.microsoft.com/library/Gg398774(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-136">[Set-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398774(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-137">[CsMonitoringServer](https://technet.microsoft.com/library/Gg425776(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-137">[Set-CsMonitoringServer](https://technet.microsoft.com/library/Gg425776(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-138">[Remove-csqoeconfiguration](https://technet.microsoft.com/library/Gg399004(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-138">[Get-CsQoEConfiguration](https://technet.microsoft.com/library/Gg399004(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-139">[Remove-csqoeconfiguration](https://technet.microsoft.com/library/Gg398325(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-139">[New-CsQoEConfiguration](https://technet.microsoft.com/library/Gg398325(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-140">[Remove-csqoeconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg425879(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-140">[Remove-CsQoEConfiguration](https://technet.microsoft.com/library/Gg425879(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-141">[Remove-csqoeconfiguration](https://technet.microsoft.com/library/Gg398245(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-141">[Set-CsQoEConfiguration](https://technet.microsoft.com/library/Gg398245(v=OCS.15))</span></span>

<span data-ttu-id="e41dd-142">[Invoke-cscdrdatabasepurge-를 호출 합니다.](https://technet.microsoft.com/library/JJ205113(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-142">[Invoke-CsCdrDatabasePurge](https://technet.microsoft.com/library/JJ205113(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-143">[Export-csarchivingdata](https://technet.microsoft.com/library/Gg398452(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-143">[Export-CsArchivingData](https://technet.microsoft.com/library/Gg398452(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-144">[-CsQoEDatabasePurge를 호출 합니다.](https://technet.microsoft.com/library/JJ205247(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-144">[Invoke-CsQoEDatabasePurge](https://technet.microsoft.com/library/JJ205247(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-145">[Get-csreportingconfiguration](https://technet.microsoft.com/library/JJ205356(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-145">[Get-CsReportingConfiguration](https://technet.microsoft.com/library/JJ205356(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-146">[Get-csreportingconfiguration](https://technet.microsoft.com/library/JJ204787(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-146">[New-CsReportingConfiguration](https://technet.microsoft.com/library/JJ204787(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-147">[Get-csreportingconfiguration을 제거 합니다.](https://technet.microsoft.com/library/JJ204711(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-147">[Remove-CsReportingConfiguration](https://technet.microsoft.com/library/JJ204711(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-148">[Get-csreportingconfiguration](https://technet.microsoft.com/library/JJ205075(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-148">[Set-CsReportingConfiguration](https://technet.microsoft.com/library/JJ205075(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-149">[Get-cstestusercredential](https://technet.microsoft.com/library/JJ204759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-149">[Get-CsTestUserCredential](https://technet.microsoft.com/library/JJ204759(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-150">[Get-cstestusercredential을 제거 합니다.](https://technet.microsoft.com/library/JJ204870(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-150">[Remove-CsTestUserCredential](https://technet.microsoft.com/library/JJ204870(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-151">[Get-cstestusercredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-151">[Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-152">[Get-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-152">[Get-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204739(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-153">[Get-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ205254(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-153">[New-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ205254(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-154">[Get-cswatchernodeconfiguration을 제거 합니다.](https://technet.microsoft.com/library/JJ204926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-154">[Remove-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204926(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-155">[Get-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204620(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-155">[Set-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204620(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-156">[Get-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204652(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-156">[Test-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204652(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-157">[New-csextendedtest](https://technet.microsoft.com/library/JJ205275(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-157">[New-CsExtendedTest](https://technet.microsoft.com/library/JJ205275(v=OCS.15))</span></span>

<span data-ttu-id="e41dd-158">**[Lync Server 2013의 데이터베이스 및 관리 서버 cmdlet](lync-server-2013-database-and-management-server-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="e41dd-158">**[Database and Management Server cmdlets in Lync Server 2013](lync-server-2013-database-and-management-server-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-159">[Remove-csconfigurationstorelocation](https://technet.microsoft.com/library/Gg412814(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-159">[Get-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg412814(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-160">[Remove-csconfigurationstorelocation을 제거 합니다.](https://technet.microsoft.com/library/Gg398214(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-160">[Remove-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398214(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-161">[Remove-csconfigurationstorelocation](https://technet.microsoft.com/library/Gg398258(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-161">[Set-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398258(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-162">[설치-CsDatabase](https://technet.microsoft.com/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-162">[Install-CsDatabase](https://technet.microsoft.com/library/Gg399044(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-163">[테스트-CsDatabase](https://technet.microsoft.com/library/JJ204839(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-163">[Test-CsDatabase](https://technet.microsoft.com/library/JJ204839(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-164">[제거-CsDatabase](unhttps://technet.microsoft.com/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-164">[Uninstall-CsDatabase](unhttps://technet.microsoft.com/library/Gg399044(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e41dd-165">[CsDatabaseFailover 조치 (failover)](https://technet.microsoft.com/library/JJ204744(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-165">[Invoke-CsDatabaseFailover](https://technet.microsoft.com/library/JJ204744(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e41dd-166">[Get-csdatabasemirrorstate](https://technet.microsoft.com/library/JJ204845(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-166">[Get-CsDatabaseMirrorState](https://technet.microsoft.com/library/JJ204845(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e41dd-167">[설치-CsMirrorDatabase](https://technet.microsoft.com/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-167">[Install-CsMirrorDatabase](https://technet.microsoft.com/library/JJ204986(v=OCS.15))</span></span>

  - <span data-ttu-id="e41dd-168">[제거-CsMirrorDatabase](unhttps://technet.microsoft.com/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-168">[Uninstall-CsMirrorDatabase](unhttps://technet.microsoft.com/library/JJ204986(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-169">[Get-CsUserDatabaseState](https://technet.microsoft.com/library/Gg398831(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-169">[Get-CsUserDatabaseState](https://technet.microsoft.com/library/Gg398831(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-170">[설정-CsUserDatabaseState](https://technet.microsoft.com/library/Gg412973(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-170">[Set-CsUserDatabaseState](https://technet.microsoft.com/library/Gg412973(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-171">[업데이트-CsUserDatabase](https://technet.microsoft.com/library/Gg398682(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-171">[Update-CsUserDatabase](https://technet.microsoft.com/library/Gg398682(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-172">[이동-Move-csmanagementserver](https://technet.microsoft.com/library/Gg412921(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-172">[Move-CsManagementServer](https://technet.microsoft.com/library/Gg412921(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-173">[Move-csmanagementserver](https://technet.microsoft.com/library/Gg398465(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-173">[Set-CsManagementServer](https://technet.microsoft.com/library/Gg398465(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e41dd-174">[-CsManagementServerFailover 조치 (failover)](https://technet.microsoft.com/library/JJ204647(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-174">[Invoke-CsManagementServerFailover](https://technet.microsoft.com/library/JJ204647(v=OCS.15))</span></span>

<span data-ttu-id="e41dd-175">**[Lync Server 2013의에 지 서버 cmdlet](lync-server-2013-edge-server-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="e41dd-175">**[Edge Server cmdlets in Lync Server 2013](lync-server-2013-edge-server-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-176">[Set-csaccessedgeconfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-176">[Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-177">[Set-csaccessedgeconfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-177">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-178">[Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-178">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-179">[Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-179">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-180">[Get-csavedgeconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-180">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-181">[Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-181">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-182">[Test-csavedgeconnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-182">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-183">[Set-csedgeserver](https://technet.microsoft.com/library/Gg398859(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-183">[Set-CsEdgeServer](https://technet.microsoft.com/library/Gg398859(v=OCS.15))</span></span>

<span data-ttu-id="e41dd-184">**[Lync Server 2013의 기타 서버 역할 cmdlet](lync-server-2013-other-server-role-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="e41dd-184">**[Other server role cmdlets in Lync Server 2013](lync-server-2013-other-server-role-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-185">[Set-csconferenceserver](https://technet.microsoft.com/library/Gg398738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-185">[Set-CsConferenceServer](https://technet.microsoft.com/library/Gg398738(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-186">[설정-CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-186">[Set-CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))</span></span>

<span data-ttu-id="e41dd-187">**[Lync Server 2013의 등록자 및 디렉터 cmdlet](lync-server-2013-registrar-and-director-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="e41dd-187">**[Registrar and Director cmdlets in Lync Server 2013](lync-server-2013-registrar-and-director-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-188">[설정-CsDirector](https://technet.microsoft.com/library/Gg398565(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-188">[Set-CsDirector](https://technet.microsoft.com/library/Gg398565(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-189">[Reset-Reset-cspoolregistrarstate](https://technet.microsoft.com/library/JJ619172(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-189">[Reset-CsPoolRegistrarState](https://technet.microsoft.com/library/JJ619172(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-190">[CsRegistrar](https://technet.microsoft.com/library/Gg398993(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-190">[Set-CsRegistrar](https://technet.microsoft.com/library/Gg398993(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-191">[Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg398483(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-191">[Get-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398483(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-192">[Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg425893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-192">[New-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg425893(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-193">[Get-csregistrarconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398482(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-193">[Remove-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398482(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-194">[Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg398764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-194">[Set-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398764(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-195">[테스트-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-195">[Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15))</span></span>

<span data-ttu-id="e41dd-196">**[Lync Server 2013의 서비스 cmdlet](lync-server-2013-services-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="e41dd-196">**[Services cmdlets in Lync Server 2013](lync-server-2013-services-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-197">[Get-CsService](https://technet.microsoft.com/library/Gg413038(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-197">[Get-CsService](https://technet.microsoft.com/library/Gg413038(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-198">[Get-CsWindowsService](https://technet.microsoft.com/library/Gg398803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-198">[Get-CsWindowsService](https://technet.microsoft.com/library/Gg398803(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-199">[시작-CsWindowsService](https://technet.microsoft.com/library/Gg398561(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-199">[Start-CsWindowsService](https://technet.microsoft.com/library/Gg398561(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-200">[CsWindowsService](https://technet.microsoft.com/library/Gg398426(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-200">[Stop-CsWindowsService](https://technet.microsoft.com/library/Gg398426(v=OCS.15))</span></span>

<span data-ttu-id="e41dd-201">**[Lync Server 2013의 서버 역할 및 서비스 cmdlet 문제 해결](lync-server-2013-troubleshooting-server-roles-and-services-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="e41dd-201">**[Troubleshooting server roles and services cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-server-roles-and-services-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-202">[Get-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg412984(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-202">[Get-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg412984(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-203">[설정-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg398907(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-203">[Set-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg398907(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-204">[Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg398667(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-204">[Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398667(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-205">[Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg398718(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-205">[New-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398718(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-206">[Get-cshealthmonitoringconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg425794(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-206">[Remove-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425794(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-207">[Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg425847(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-207">[Set-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425847(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-208">[Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg413034(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-208">[Get-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg413034(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-209">[Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg398733(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-209">[New-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg398733(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-210">[Get-csdiagnosticconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg412853(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-210">[Remove-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg412853(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-211">[Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg425734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-211">[Set-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg425734(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-212">[New-csdiagnosticsfilter](https://technet.microsoft.com/library/Gg413009(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-212">[New-CsDiagnosticsFilter](https://technet.microsoft.com/library/Gg413009(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-213">[Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg412774(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-213">[Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg412774(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-214">[Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg398350(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-214">[New-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398350(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-215">[Get-csdiagnosticheaderconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398941(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-215">[Remove-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398941(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-216">[Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg399045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-216">[Set-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg399045(v=OCS.15))</span></span>

<span data-ttu-id="e41dd-217">**[Lync Server 2013의 웹 서버 및 서비스 cmdlet](lync-server-2013-web-server-and-services-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="e41dd-217">**[Web server and services cmdlets in Lync Server 2013](lync-server-2013-web-server-and-services-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-218">[New-cssimpleurl](https://technet.microsoft.com/library/Gg398180(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-218">[New-CsSimpleUrl](https://technet.microsoft.com/library/Gg398180(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-219">[Get-cssimpleurlconfiguration](https://technet.microsoft.com/library/Gg398392(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-219">[Get-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398392(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-220">[Get-cssimpleurlconfiguration](https://technet.microsoft.com/library/Gg425813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-220">[New-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg425813(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-221">[Get-cssimpleurlconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398515(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-221">[Remove-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398515(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-222">[Get-cssimpleurlconfiguration](https://technet.microsoft.com/library/Gg412991(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-222">[Set-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg412991(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-223">[New-cssimpleurlentry](https://technet.microsoft.com/library/Gg425902(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-223">[New-CsSimpleUrlEntry](https://technet.microsoft.com/library/Gg425902(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-224">[Set-CsWebServer](https://technet.microsoft.com/library/Gg398759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-224">[Set-CsWebServer](https://technet.microsoft.com/library/Gg398759(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-225">[Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg425751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-225">[Get-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg425751(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-226">[Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg398440(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-226">[New-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398440(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-227">[Set-cswebserviceconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398266(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-227">[Remove-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398266(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-228">[Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg398396(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-228">[Set-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398396(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-229">[New-cswebtrustedcacertificate](https://technet.microsoft.com/library/Gg412746(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-229">[New-CsWebTrustedCACertificate](https://technet.microsoft.com/library/Gg412746(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-230">[새-C고 Ercosaccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-230">[New-CsKerberosAccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-231">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-231">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-232">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-232">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-233">[Get-cskerberosaccountassignment을 제거 합니다.](https://technet.microsoft.com/library/Gg413052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-233">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-234">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-234">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e41dd-235">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-235">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e41dd-236">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-236">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e41dd-237">[Test-cswebapp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-237">[Test-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span></span>

  - <span data-ttu-id="e41dd-238">[Test-cswebappanonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e41dd-238">[Test-CsWebAppAnonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e41dd-239">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e41dd-239">See Also</span></span>


[<span data-ttu-id="e41dd-240">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="e41dd-240">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


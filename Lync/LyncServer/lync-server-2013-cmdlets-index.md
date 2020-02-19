---
title: 'Lync Server 2013: cmdlet 인덱스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 cmdlets index
ms:assetid: cd37aba7-3d27-4db9-b69f-3a6da1fb4b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398867(v=OCS.15)
ms:contentKeyID: 48185661
ms.date: 04/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb713c1f328258bcb80173e0ff7e61ddd8304075
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-cmdlets-index"></a><span data-ttu-id="25deb-102">Lync Server 2013 cmdlet 인덱스</span><span class="sxs-lookup"><span data-stu-id="25deb-102">Lync Server 2013 cmdlets index</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25deb-103">_**마지막으로 수정 된 항목:** 2016-04-12_</span><span class="sxs-lookup"><span data-stu-id="25deb-103">_**Topic Last Modified:** 2016-04-12_</span></span>

<span data-ttu-id="25deb-104">Microsoft Lync Server 2013에는 관리자가 명령줄에서 Lync Server 2013을 관리 하도록 해 주는 700 cmdlet이 더 이상 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25deb-104">Microsoft Lync Server 2013 ships with more than 700 cmdlets that enable administrators to manage Lync Server 2013 from the command line.</span></span> <span data-ttu-id="25deb-105">Lync Server cmdlet은 일반적으로 Lync Server 관리 셸에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25deb-105">The Lync Server cmdlets are typically used with the Lync Server Management Shell.</span></span> <span data-ttu-id="25deb-106">Lync server 관리 셸을 사용 하는 한 가지 방법은 Lync Server 서비스 또는 서버 역할을 실행 하는 컴퓨터에 로그온 하 고 **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 관리 셸을**클릭 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="25deb-106">One way to use the Lync Server Management Shell is to log on to a computer running a Lync Server service or server role, click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="25deb-107">관리 셸이 열린 후에는 다음과 같은 명령을 입력 하 여 명령줄에서 직접 cmdlet에 대 한 도움말을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25deb-107">After the Management Shell is open you can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="25deb-108">위 명령은 **set-csvoicepolicy** cmdlet에 사용할 수 있는 전체 도움말을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="25deb-108">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="25deb-109">다른 cmdlet에 대 한 도움말을 보려면 **set-csvoicepolicy** 를 도움말을 검색 하려는 cmdlet의 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="25deb-109">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>

<span data-ttu-id="25deb-110">Lync Server 관리에 사용할 수 있는 전체 cmdlet 목록을 검색 하려면 Lync Server 관리 셸 명령 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="25deb-110">To retrieve a full list of cmdlets available for managing Lync Server, type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Command * -Module Lync -CommandType cmdlet

<span data-ttu-id="25deb-111">Lync Server 관리 셸을 사용 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="25deb-111">For details about using the Lync Server Management Shell, see the Lync Server Windows PowerShell blog at [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150).</span></span>

<div>

## <a name="lync-server-2013-cmdlets"></a><span data-ttu-id="25deb-112">Lync Server 2013 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="25deb-112">Lync Server 2013 Cmdlets</span></span>

<span data-ttu-id="25deb-113">다음은 Lync Server 2013와 함께 제공 되는 cmdlet 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="25deb-113">Following is a list of the cmdlets that ship with Lync Server 2013:</span></span>

  - <span data-ttu-id="25deb-114">[CsSlaDelegates 추가](https://technet.microsoft.com/library/Mt703199(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-114">[Add-CsSlaDelegates](https://technet.microsoft.com/library/Mt703199(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-115">[승인-Get-csdeviceupdaterule](https://technet.microsoft.com/library/Gg398949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-115">[Approve-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398949(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-116">[백업-CsPool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-116">[Backup-CsPool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-117">[일반-CsDeviceUpdateFile](https://technet.microsoft.com/library/Gg425835(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-117">[Clear-CsDeviceUpdateFile](https://technet.microsoft.com/library/Gg425835(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-118">[일반-CsDeviceUpdateLog](https://technet.microsoft.com/library/Gg412738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-118">[Clear-CsDeviceUpdateLog](https://technet.microsoft.com/library/Gg412738(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-119">[일반-Clear-cspersistentchatroom](https://technet.microsoft.com/library/JJ204976(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-119">[Clear-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204976(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-120">[변환-CsUserData](https://technet.microsoft.com/library/JJ205337(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-120">[Convert-CsUserData](https://technet.microsoft.com/library/JJ205337(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-121">[디버그-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-121">[Debug-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-122">[Debug-csintrapoolreplication](https://technet.microsoft.com/library/JJ205103(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-122">[Debug-CsIntraPoolReplication](https://technet.microsoft.com/library/JJ205103(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-123">[Export-cslisconfiguration](https://technet.microsoft.com/library/Gg398710(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-123">[Debug-CsLisConfiguration](https://technet.microsoft.com/library/Gg398710(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-124">[사용 안 함-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-124">[Disable-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-125">[사용 안 함-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-125">[Disable-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-126">[사용 안 함-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-126">[Disable-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-127">[사용 안 함-CsHostingProvider](https://technet.microsoft.com/library/Gg398481(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-127">[Disable-CsHostingProvider](https://technet.microsoft.com/library/Gg398481(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-128">[사용 안 함-Enable-csmeetingroom](https://technet.microsoft.com/library/JJ204723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-128">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/JJ204723(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-129">[사용 안 함-Disable-cspublicprovider](https://technet.microsoft.com/library/Gg398984(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-129">[Disable-CsPublicProvider](https://technet.microsoft.com/library/Gg398984(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-130">[사용 안 함-CsUser](https://technet.microsoft.com/library/Gg398747(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-130">[Disable-CsUser](https://technet.microsoft.com/library/Gg398747(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-131">[Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-131">[Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-132">[Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-132">[Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-133">[사용-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-133">[Enable-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-134">[Enable-CsHostingProvider](https://technet.microsoft.com/library/Gg398166(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-134">[Enable-CsHostingProvider](https://technet.microsoft.com/library/Gg398166(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-135">[Enable-Enable-csmeetingroom](https://technet.microsoft.com/library/JJ205062(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-135">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/JJ205062(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-136">[Enable-Disable-cspublicprovider](https://technet.microsoft.com/library/Gg398780(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-136">[Enable-CsPublicProvider](https://technet.microsoft.com/library/Gg398780(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-137">[사용-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-137">[Enable-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-138">[Enable-Enable-cstopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-138">[Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-139">[Enable-CsUser](https://technet.microsoft.com/library/Gg398711(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-139">[Enable-CsUser](https://technet.microsoft.com/library/Gg398711(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-140">[Export-csarchivingdata](https://technet.microsoft.com/library/Gg398452(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-140">[Export-CsArchivingData](https://technet.microsoft.com/library/Gg398452(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-141">[수출-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-141">[Export-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-142">[Export-cslisconfiguration](https://technet.microsoft.com/library/Gg398539(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-142">[Export-CsLisConfiguration](https://technet.microsoft.com/library/Gg398539(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-143">[Export-cspersistentchatdata](https://technet.microsoft.com/library/JJ205378(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-143">[Export-CsPersistentChatData](https://technet.microsoft.com/library/JJ205378(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-144">[Export-csrgsconfiguration](https://technet.microsoft.com/library/JJ205011(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-144">[Export-CsRgsConfiguration](https://technet.microsoft.com/library/JJ205011(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-145">[수출-CsUserData](https://technet.microsoft.com/library/JJ204897(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-145">[Export-CsUserData](https://technet.microsoft.com/library/JJ204897(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-146">[Set-csaccessedgeconfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-146">[Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-147">[Get-CsAdContact](https://technet.microsoft.com/library/Gg412776(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-147">[Get-CsAdContact](https://technet.microsoft.com/library/Gg412776(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-148">[Get-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-148">[Get-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-149">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-149">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-150">[Get-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-150">[Get-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-151">[Get-CsAdminRole](https://technet.microsoft.com/library/Gg399050(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-151">[Get-CsAdminRole](https://technet.microsoft.com/library/Gg399050(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-152">[Get-CsAdminRoleAssignment](https://technet.microsoft.com/library/Gg398434(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-152">[Get-CsAdminRoleAssignment](https://technet.microsoft.com/library/Gg398434(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-153">[Get-CsAdPrincipal](https://technet.microsoft.com/library/JJ205326(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-153">[Get-CsAdPrincipal](https://technet.microsoft.com/library/JJ205326(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-154">[Get-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-154">[Get-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-155">[Get-CsAdUser](https://technet.microsoft.com/library/Gg398592(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-155">[Get-CsAdUser](https://technet.microsoft.com/library/Gg398592(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-156">[Get-CsAllowedDomain](https://technet.microsoft.com/library/Gg398164(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-156">[Get-CsAllowedDomain](https://technet.microsoft.com/library/Gg398164(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-157">[Move-csanalogdevice](https://technet.microsoft.com/library/Gg398748(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-157">[Get-CsAnalogDevice](https://technet.microsoft.com/library/Gg398748(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-158">[Get-CsAnnouncement](https://technet.microsoft.com/library/Gg398937(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-158">[Get-CsAnnouncement](https://technet.microsoft.com/library/Gg398937(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-159">[Get-CsApplicationEndpoint](https://technet.microsoft.com/library/Gg398655(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-159">[Get-CsApplicationEndpoint](https://technet.microsoft.com/library/Gg398655(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-160">[Get-csarchivingconfiguration](https://technet.microsoft.com/library/Gg399012(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-160">[Get-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg399012(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-161">[Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg425731(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-161">[Get-CsArchivingPolicy](https://technet.microsoft.com/library/Gg425731(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-162">[Get-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg412984(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-162">[Get-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg412984(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-163">[Get-csautodiscoverconfiguration](https://technet.microsoft.com/library/Hh690014(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-163">[Get-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh690014(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-164">[Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-164">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-165">[Get-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ205087(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-165">[Get-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205087(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-166">[Get-csbackupservicestatus](https://technet.microsoft.com/library/JJ205032(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-166">[Get-CsBackupServiceStatus](https://technet.microsoft.com/library/JJ205032(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-167">[CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412727(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-167">[Get-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412727(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-168">[Get-csblockeddomain](https://technet.microsoft.com/library/Gg398424(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-168">[Get-CsBlockedDomain](https://technet.microsoft.com/library/Gg398424(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-169">[Get-cscallparkorbit](https://technet.microsoft.com/library/Gg398554(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-169">[Get-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398554(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-170">[Get-cscdrconfiguration](https://technet.microsoft.com/library/Gg398298(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-170">[Get-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398298(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-171">[Set-cscertificate](https://technet.microsoft.com/library/Gg398227(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-171">[Get-CsCertificate](https://technet.microsoft.com/library/Gg398227(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-172">[Get-CsClientAccessLicense](https://technet.microsoft.com/library/JJ204853(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-172">[Get-CsClientAccessLicense](https://technet.microsoft.com/library/JJ204853(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-173">[Get-csclientcertificate](https://technet.microsoft.com/library/Gg398143(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-173">[Get-CsClientCertificate](https://technet.microsoft.com/library/Gg398143(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-174">[Get-CsClientPinInfo](https://technet.microsoft.com/library/Gg425947(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-174">[Get-CsClientPinInfo](https://technet.microsoft.com/library/Gg425947(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-175">[Get-CsClientPolicy](https://technet.microsoft.com/library/Gg398830(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-175">[Get-CsClientPolicy](https://technet.microsoft.com/library/Gg398830(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-176">[Get-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399072(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-176">[Get-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399072(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-177">[Get-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-177">[Get-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398957(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-178">[Get-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg413048(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-178">[Get-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg413048(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-179">[Get-CsClsRegion](https://technet.microsoft.com/library/JJ204879(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-179">[Get-CsClsRegion](https://technet.microsoft.com/library/JJ204879(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-180">[Get-CsClsSearchTerm](https://technet.microsoft.com/library/JJ205061(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-180">[Get-CsClsSearchTerm](https://technet.microsoft.com/library/JJ205061(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-181">[Get-CsClsScenario](https://technet.microsoft.com/library/JJ205091(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-181">[Get-CsClsScenario](https://technet.microsoft.com/library/JJ205091(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-182">[Get-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205285(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-182">[Get-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205285(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-183">[Move-cscommonareaphone](https://technet.microsoft.com/library/Gg412934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-183">[Get-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg412934(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-184">[온-CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-184">[Get-CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-185">[Get-csconferencedirectory](https://technet.microsoft.com/library/Gg425771(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-185">[Get-CsConferenceDirectory](https://technet.microsoft.com/library/Gg425771(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-186">[Get-csconferencedisclaimer](https://technet.microsoft.com/library/Gg425714(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-186">[Get-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg425714(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-187">[Get-csconferencingconfiguration](https://technet.microsoft.com/library/Gg398965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-187">[Get-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg398965(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-188">[Get-csconferencingpolicy](https://technet.microsoft.com/library/Gg398293(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-188">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398293(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-189">[Remove-csconfigurationstorelocation](https://technet.microsoft.com/library/Gg412814(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-189">[Get-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg412814(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-190">[New-cscpsconfiguration](https://technet.microsoft.com/library/Gg398948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-190">[Get-CsCpsConfiguration](https://technet.microsoft.com/library/Gg398948(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-191">[Get-csdatabasemirrorstate](https://technet.microsoft.com/library/JJ204845(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-191">[Get-CsDatabaseMirrorState](https://technet.microsoft.com/library/JJ204845(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-192">[New-csdeviceupdateconfiguration](https://technet.microsoft.com/library/Gg399030(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-192">[Get-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg399030(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-193">[Get-csdeviceupdaterule](https://technet.microsoft.com/library/Gg398215(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-193">[Get-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398215(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-194">[Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg413034(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-194">[Get-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg413034(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-195">[Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg412774(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-195">[Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg412774(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-196">[Get-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg413015(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-196">[Get-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg413015(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-197">[Get-csdialinconferencingconfiguration](https://technet.microsoft.com/library/Gg398575(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-197">[Get-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398575(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-198">[Set-csdialinconferencingdtmfconfiguration](https://technet.microsoft.com/library/Gg398578(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-198">[Get-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg398578(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-199">[Get-csdialinconferencinglanguagelist](https://technet.microsoft.com/library/Gg425869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-199">[Get-CsDialInConferencingLanguageList](https://technet.microsoft.com/library/Gg425869(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-200">[Get-CsDialPlan 플랜](https://technet.microsoft.com/library/Gg413043(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-200">[Get-CsDialPlan](https://technet.microsoft.com/library/Gg413043(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-201">[Get-cseffectivepolicy](https://technet.microsoft.com/library/JJ204636(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-201">[Get-CsEffectivePolicy](https://technet.microsoft.com/library/JJ204636(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-202">[CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg412877(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-202">[Get-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg412877(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-203">[Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-203">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-204">[Get-CsExUmContact](https://technet.microsoft.com/library/Gg412725(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-204">[Get-CsExUmContact](https://technet.microsoft.com/library/Gg412725(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-205">[CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg398527(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-205">[Get-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg398527(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-206">[Get-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ204904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-206">[Get-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ204904(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-207">[Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg398667(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-207">[Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398667(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-208">[Set-cshostedvoicemailpolicy](https://technet.microsoft.com/library/Gg398348(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-208">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398348(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-209">[Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-209">[Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-210">[Get-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398980(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-210">[Get-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398980(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-211">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-211">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-212">[Test-csliscivicaddress](https://technet.microsoft.com/library/Gg398459(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-212">[Get-CsLisCivicAddress](https://technet.microsoft.com/library/Gg398459(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-213">[Get-cslislocation](https://technet.microsoft.com/library/Gg412834(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-213">[Get-CsLisLocation](https://technet.microsoft.com/library/Gg412834(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-214">[CsLisPort](https://technet.microsoft.com/library/Gg398820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-214">[Get-CsLisPort](https://technet.microsoft.com/library/Gg398820(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-215">[CsLisServiceProvider](https://technet.microsoft.com/library/Gg398116(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-215">[Get-CsLisServiceProvider](https://technet.microsoft.com/library/Gg398116(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-216">[CsLisSubnet](https://technet.microsoft.com/library/Gg398473(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-216">[Get-CsLisSubnet](https://technet.microsoft.com/library/Gg398473(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-217">[CsLisSwitch](https://technet.microsoft.com/library/Gg425769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-217">[Get-CsLisSwitch](https://technet.microsoft.com/library/Gg425769(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-218">[CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398117(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-218">[Get-CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398117(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-219">[Get-CsLocationPolicy](https://technet.microsoft.com/library/Gg398911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-219">[Get-CsLocationPolicy](https://technet.microsoft.com/library/Gg398911(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-220">[Get-CsManagementConnection](https://technet.microsoft.com/library/Gg412849(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-220">[Get-CsManagementConnection](https://technet.microsoft.com/library/Gg412849(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-221">[Get-csmanagementstorereplicationstatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-221">[Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-222">[Get-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690031(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-222">[Get-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690031(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-223">[Get-csmediaconfiguration](https://technet.microsoft.com/library/Gg398128(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-223">[Get-CsMediaConfiguration](https://technet.microsoft.com/library/Gg398128(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-224">[Get-csmeetingconfiguration](https://technet.microsoft.com/library/Gg425875(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-224">[Get-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg425875(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-225">[Enable-csmeetingroom](https://technet.microsoft.com/library/JJ205277(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-225">[Get-CsMeetingRoom](https://technet.microsoft.com/library/JJ205277(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-226">[Get-csmobilitypolicy](https://technet.microsoft.com/library/Hh690017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-226">[Get-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690017(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-227">[Get-csnetworkbandwidthpolicyprofile](https://technet.microsoft.com/library/Gg425815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-227">[Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg425815(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-228">[Get-csnetworkconfiguration](https://technet.microsoft.com/library/Gg398140(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-228">[Get-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398140(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-229">[Get-csnetworkinterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-229">[Get-CsNetworkInterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-230">[Get-Csnetworkinterroute](https://technet.microsoft.com/library/Gg425817(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-230">[Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg425817(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-231">[Remove-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg412769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-231">[Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg412769(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-232">[Get-CsNetworkRegion](https://technet.microsoft.com/library/Gg398406(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-232">[Get-CsNetworkRegion](https://technet.microsoft.com/library/Gg398406(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-233">[Get-Csnetwork지역 링크](https://technet.microsoft.com/library/Gg398972(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-233">[Get-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398972(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-234">[Get-CsNetworkSite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-234">[Get-CsNetworkSite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-235">[Get-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412825(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-235">[Get-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412825(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-236">[Get-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ205155(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-236">[Get-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ205155(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-237">[Get-CsOAuthServer](https://technet.microsoft.com/library/JJ205238(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-237">[Get-CsOAuthServer](https://technet.microsoft.com/library/JJ205238(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-238">[Get-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ204962(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-238">[Get-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ204962(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-239">[New-csoutboundtranslationrule](https://technet.microsoft.com/library/Gg398104(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-239">[Get-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398104(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-240">[Get-cspartnerapplication](https://technet.microsoft.com/library/JJ205128(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-240">[Get-CsPartnerApplication](https://technet.microsoft.com/library/JJ205128(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-241">[Get-cspersistentchataddin](https://technet.microsoft.com/library/JJ204670(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-241">[Get-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ204670(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-242">[Get-cspersistentchatcategory](https://technet.microsoft.com/library/JJ204771(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-242">[Get-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204771(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-243">[Get-cspersistentchatcomplianceconfiguration](https://technet.microsoft.com/library/JJ204625(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-243">[Get-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ204625(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-244">[Get-cspersistentchatconfiguration](https://technet.microsoft.com/library/JJ205140(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-244">[Get-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ205140(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-245">[Get-cspersistentchateligibleprincipal](https://technet.microsoft.com/library/JJ204891(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-245">[Get-CsPersistentChatEligiblePrincipal](https://technet.microsoft.com/library/JJ204891(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-246">[Get-cspersistentchatendpoint](https://technet.microsoft.com/library/JJ204764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-246">[Get-CsPersistentChatEndpoint](https://technet.microsoft.com/library/JJ204764(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-247">[Grant-cspersistentchatpolicy](https://technet.microsoft.com/library/JJ204673(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-247">[Get-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ204673(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-248">[Clear-cspersistentchatroom](https://technet.microsoft.com/library/JJ205123(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-248">[Get-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ205123(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-249">[Set-cspersistentchatstate](https://technet.microsoft.com/library/JJ204915(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-249">[Get-CsPersistentChatState](https://technet.microsoft.com/library/JJ204915(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-250">[Get-cspinpolicy](https://technet.microsoft.com/library/Gg398262(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-250">[Get-CsPinPolicy](https://technet.microsoft.com/library/Gg398262(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-251">[Get-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-251">[Get-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-252">[Get-cspoolbackuprelationship](https://technet.microsoft.com/library/JJ204745(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-252">[Get-CsPoolBackupRelationship](https://technet.microsoft.com/library/JJ204745(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-253">[Get-cspoolupgradereadinessstate](https://technet.microsoft.com/library/JJ204689(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-253">[Get-CsPoolUpgradeReadinessState](https://technet.microsoft.com/library/JJ204689(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-254">[Get-cspresencepolicy](https://technet.microsoft.com/library/Gg398463(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-254">[Get-CsPresencePolicy](https://technet.microsoft.com/library/Gg398463(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-255">[Remove-cspresenceprovider](https://technet.microsoft.com/library/JJ204705(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-255">[Get-CsPresenceProvider](https://technet.microsoft.com/library/JJ204705(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-256">[Get-csprivacyconfiguration](https://technet.microsoft.com/library/Gg413002(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-256">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg413002(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-257">[Get-CsProxyConfiguration](https://technet.microsoft.com/library/Gg399011(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-257">[Get-CsProxyConfiguration](https://technet.microsoft.com/library/Gg399011(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-258">[G-CsPstnUsage 사용](https://technet.microsoft.com/library/Gg412734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-258">[Get-CsPstnUsage](https://technet.microsoft.com/library/Gg412734(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-259">[Disable-cspublicprovider](https://technet.microsoft.com/library/Gg412945(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-259">[Get-CsPublicProvider](https://technet.microsoft.com/library/Gg412945(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-260">[Get-cspushnotificationconfiguration](https://technet.microsoft.com/library/Hh690049(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-260">[Get-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690049(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-261">[Remove-csqoeconfiguration](https://technet.microsoft.com/library/Gg399004(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-261">[Get-CsQoEConfiguration](https://technet.microsoft.com/library/Gg399004(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-262">[Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg398483(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-262">[Get-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398483(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-263">[Get-csreportingconfiguration](https://technet.microsoft.com/library/JJ205356(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-263">[Get-CsReportingConfiguration](https://technet.microsoft.com/library/JJ205356(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-264">[Get-csrgsagentgroup](https://technet.microsoft.com/library/Gg425793(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-264">[Get-CsRgsAgentGroup](https://technet.microsoft.com/library/Gg425793(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-265">[Export-csrgsconfiguration](https://technet.microsoft.com/library/Gg412762(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-265">[Get-CsRgsConfiguration](https://technet.microsoft.com/library/Gg412762(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-266">[New-csrgsholidayset](https://technet.microsoft.com/library/Gg412983(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-266">[Get-CsRgsHolidaySet](https://technet.microsoft.com/library/Gg412983(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-267">[Get-csrgshoursofbusiness](https://technet.microsoft.com/library/Gg398284(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-267">[Get-CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg398284(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-268">[Get-csrgsqueue](https://technet.microsoft.com/library/Gg412759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-268">[Get-CsRgsQueue](https://technet.microsoft.com/library/Gg412759(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-269">[Get-csrgsworkflow](https://technet.microsoft.com/library/Gg425766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-269">[Get-CsRgsWorkflow](https://technet.microsoft.com/library/Gg425766(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-270">[Get-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg425851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-270">[Get-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg425851(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-271">[Get-CsServerApplication](https://technet.microsoft.com/library/Gg425948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-271">[Get-CsServerApplication](https://technet.microsoft.com/library/Gg425948(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-272">[Get-CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-272">[Get-CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-273">[Get-CsService](https://technet.microsoft.com/library/Gg413038(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-273">[Get-CsService](https://technet.microsoft.com/library/Gg413038(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-274">[Get-cssimpleurlconfiguration](https://technet.microsoft.com/library/Gg398392(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-274">[Get-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398392(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-275">[New-cssipdomain](https://technet.microsoft.com/library/Gg398701(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-275">[Get-CsSipDomain](https://technet.microsoft.com/library/Gg398701(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-276">[Get-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg398130(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-276">[Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg398130(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-277">[CsSlaConfiguration](https://technet.microsoft.com/library/Mt703200(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-277">[Get-CsSlaConfiguration](https://technet.microsoft.com/library/Mt703200(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-278">[Get-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-278">[Get-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-279">[Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398754(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-279">[Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398754(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-280">[Get-CsTestDevice](https://technet.microsoft.com/library/Gg398304(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-280">[Get-CsTestDevice](https://technet.microsoft.com/library/Gg398304(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-281">[Get-cstestusercredential](https://technet.microsoft.com/library/JJ204759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-281">[Get-CsTestUserCredential](https://technet.microsoft.com/library/JJ204759(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-282">[Enable-cstopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-282">[Get-CsTopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-283">[Get-cstrunk](https://technet.microsoft.com/library/JJ205244(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-283">[Get-CsTrunk](https://technet.microsoft.com/library/JJ205244(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-284">[Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg398224(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-284">[Get-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398224(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-285">[New-cstrustedapplication](https://technet.microsoft.com/library/Gg399025(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-285">[Get-CsTrustedApplication](https://technet.microsoft.com/library/Gg399025(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-286">[CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg425843(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-286">[Get-CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg425843(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-287">[CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg413035(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-287">[Get-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg413035(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-288">[New-cstrustedapplicationpool](https://technet.microsoft.com/library/Gg413055(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-288">[Get-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg413055(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-289">[Set-csucphoneconfiguration](https://technet.microsoft.com/library/Gg398070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-289">[Get-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398070(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-290">[Get-csuiculture](https://technet.microsoft.com/library/Gg412900(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-290">[Get-CsUICulture](https://technet.microsoft.com/library/Gg412900(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-291">[New-csunassignednumber](https://technet.microsoft.com/library/Gg412792(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-291">[Get-CsUnassignedNumber](https://technet.microsoft.com/library/Gg412792(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-292">[Get-CsUser](https://technet.microsoft.com/library/Gg398125(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-292">[Get-CsUser](https://technet.microsoft.com/library/Gg398125(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-293">[Get-CsUserAcp](https://technet.microsoft.com/library/Gg398978(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-293">[Get-CsUserAcp](https://technet.microsoft.com/library/Gg398978(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-294">[Get-CsUserDatabaseState](https://technet.microsoft.com/library/Gg398831(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-294">[Get-CsUserDatabaseState](https://technet.microsoft.com/library/Gg398831(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-295">[Get-CsUserPoolInfo](https://technet.microsoft.com/library/Gg398615(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-295">[Get-CsUserPoolInfo](https://technet.microsoft.com/library/Gg398615(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-296">[Get-csuserreplicatorconfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-296">[Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-297">[Get-Csuser서비스 구성](https://technet.microsoft.com/library/Gg398133(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-297">[Get-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398133(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-298">[Get-Csuser서비스 정책](https://technet.microsoft.com/library/JJ204838(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-298">[Get-CsUserServicesPolicy](https://technet.microsoft.com/library/JJ204838(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-299">[CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-299">[Get-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398815(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-300">[New-csvoicemailreroutingconfiguration](https://technet.microsoft.com/library/Gg425732(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-300">[Get-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg425732(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-301">[Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg398393(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-301">[Get-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398393(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-302">[Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398101(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-302">[Get-CsVoicePolicy](https://technet.microsoft.com/library/Gg398101(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-303">[Get-csvoiceroute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-303">[Get-CsVoiceRoute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-304">[Get-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ204940(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-304">[Get-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ204940(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-305">[수정한 구성은 test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg412957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-305">[Get-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412957(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-306">[Get-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-306">[Get-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204739(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-307">[Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg425751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-307">[Get-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg425751(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-308">[Get-CsWindowsService](https://technet.microsoft.com/library/Gg398803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-308">[Get-CsWindowsService](https://technet.microsoft.com/library/Gg398803(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-309">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-309">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-310">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-310">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-311">[Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg398475(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-311">[Grant-CsArchivingPolicy](https://technet.microsoft.com/library/Gg398475(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-312">[부여-CsClientPolicy](https://technet.microsoft.com/library/Gg412942(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-312">[Grant-CsClientPolicy](https://technet.microsoft.com/library/Gg412942(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-313">[부여-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg412903(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-313">[Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg412903(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-314">[Get-csconferencingpolicy](https://technet.microsoft.com/library/Gg425937(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-314">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/Gg425937(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-315">[부여-CsDialPlan 플랜](https://technet.microsoft.com/library/Gg398547(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-315">[Grant-CsDialPlan](https://technet.microsoft.com/library/Gg398547(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-316">[Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg425942(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-316">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425942(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-317">[Set-cshostedvoicemailpolicy](https://technet.microsoft.com/library/Gg412829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-317">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg412829(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-318">[부여-CsLocationPolicy](https://technet.microsoft.com/library/Gg413049(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-318">[Grant-CsLocationPolicy](https://technet.microsoft.com/library/Gg413049(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-319">[Get-csmobilitypolicy](https://technet.microsoft.com/library/Hh690038(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-319">[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690038(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-320">[부여-CsOUPermission](https://technet.microsoft.com/library/Gg425739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-320">[Grant-CsOUPermission](https://technet.microsoft.com/library/Gg425739(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-321">[Grant-cspersistentchatpolicy](https://technet.microsoft.com/library/JJ204907(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-321">[Grant-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ204907(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-322">[Get-cspinpolicy](https://technet.microsoft.com/library/Gg398871(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-322">[Grant-CsPinPolicy](https://technet.microsoft.com/library/Gg398871(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-323">[Get-cspresencepolicy](https://technet.microsoft.com/library/Gg398571(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-323">[Grant-CsPresencePolicy](https://technet.microsoft.com/library/Gg398571(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-324">[부여-CsSetupPermission](https://technet.microsoft.com/library/Gg398569(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-324">[Grant-CsSetupPermission](https://technet.microsoft.com/library/Gg398569(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-325">[부여-Csuser서비스 정책](https://technet.microsoft.com/library/JJ205388(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-325">[Grant-CsUserServicesPolicy](https://technet.microsoft.com/library/JJ205388(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-326">[Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398828(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-326">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/Gg398828(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-327">[Get-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ205141(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-327">[Grant-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205141(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-328">[경우 import-csannouncementfile](https://technet.microsoft.com/library/Gg398472(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-328">[Import-CsAnnouncementFile](https://technet.microsoft.com/library/Gg398472(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-329">[Set-cscertificate](https://technet.microsoft.com/library/Gg398688(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-329">[Import-CsCertificate](https://technet.microsoft.com/library/Gg398688(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-330">[가져오기-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-330">[Import-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-331">[가져오기-CsDeviceUpdate](https://technet.microsoft.com/library/Gg398861(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-331">[Import-CsDeviceUpdate](https://technet.microsoft.com/library/Gg398861(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-332">[Import-cslegacyconferencedirectory](https://technet.microsoft.com/library/Gg398418(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-332">[Import-CsLegacyConferenceDirectory](https://technet.microsoft.com/library/Gg398418(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-333">[Import-cslegacyconfiguration](https://technet.microsoft.com/library/Gg412923(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-333">[Import-CsLegacyConfiguration](https://technet.microsoft.com/library/Gg412923(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-334">[Export-cslisconfiguration](https://technet.microsoft.com/library/Gg398380(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-334">[Import-CsLisConfiguration](https://technet.microsoft.com/library/Gg398380(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-335">[Export-cspersistentchatdata](https://technet.microsoft.com/library/JJ204709(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-335">[Import-CsPersistentChatData](https://technet.microsoft.com/library/JJ204709(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-336">[Import-csrgsaudiofile](https://technet.microsoft.com/library/Gg412830(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-336">[Import-CsRgsAudioFile](https://technet.microsoft.com/library/Gg412830(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-337">[Export-csrgsconfiguration](https://technet.microsoft.com/library/JJ205245(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-337">[Import-CsRgsConfiguration](https://technet.microsoft.com/library/JJ205245(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-338">[가져오기-CsUserData](https://technet.microsoft.com/library/JJ205373(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-338">[Import-CsUserData](https://technet.microsoft.com/library/JJ205373(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-339">[설치-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-339">[Install-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-340">[설치-CsDatabase](https://technet.microsoft.com/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-340">[Install-CsDatabase](https://technet.microsoft.com/library/Gg399044(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-341">[설치-CsMirrorDatabase](https://technet.microsoft.com/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-341">[Install-CsMirrorDatabase](https://technet.microsoft.com/library/JJ204986(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-342">[Invoke-csarchivingdatabasepurge-를 호출 합니다.](https://technet.microsoft.com/library/JJ204627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-342">[Invoke-CsArchivingDatabasePurge](https://technet.microsoft.com/library/JJ204627(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-343">[Invoke-csbackupservicesync-를 호출 합니다.](https://technet.microsoft.com/library/JJ205374(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-343">[Invoke-CsBackupServiceSync](https://technet.microsoft.com/library/JJ205374(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-344">[Invoke-cscdrdatabasepurge-를 호출 합니다.](https://technet.microsoft.com/library/JJ205113(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-344">[Invoke-CsCdrDatabasePurge](https://technet.microsoft.com/library/JJ205113(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-345">[CsDatabaseFailover 조치 (failover)](https://technet.microsoft.com/library/JJ204744(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-345">[Invoke-CsDatabaseFailover](https://technet.microsoft.com/library/JJ204744(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-346">[-CsManagementServerFailover 조치 (failover)](https://technet.microsoft.com/library/JJ204647(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-346">[Invoke-CsManagementServerFailover](https://technet.microsoft.com/library/JJ204647(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-347">[Invoke-csmanagementstorereplication-를 호출 합니다.](https://technet.microsoft.com/library/Gg413060(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-347">[Invoke-CsManagementStoreReplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-348">[Invoke-cspoolfailback-를 호출 합니다.](https://technet.microsoft.com/library/JJ204873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-348">[Invoke-CsPoolFailBack](https://technet.microsoft.com/library/JJ204873(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-349">[Initialize-cspoolfailover-를 호출 합니다.](https://technet.microsoft.com/library/JJ205189(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-349">[Invoke-CsPoolFailOver](https://technet.microsoft.com/library/JJ205189(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-350">[-CsQoEDatabasePurge를 호출 합니다.](https://technet.microsoft.com/library/JJ205247(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-350">[Invoke-CsQoEDatabasePurge](https://technet.microsoft.com/library/JJ205247(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-351">[Invoke-csucsrollback-를 호출 합니다.](https://technet.microsoft.com/library/JJ204661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-351">[Invoke-CsUcsRollback](https://technet.microsoft.com/library/JJ204661(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-352">[잠금-CsClientPin](https://technet.microsoft.com/library/Gg398650(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-352">[Lock-CsClientPin](https://technet.microsoft.com/library/Gg398650(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-353">[병합-Merge-cslegacytopology](https://technet.microsoft.com/library/Gg425870(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-353">[Merge-CsLegacyTopology](https://technet.microsoft.com/library/Gg425870(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-354">[이동-Move-csanalogdevice](https://technet.microsoft.com/library/Gg398816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-354">[Move-CsAnalogDevice](https://technet.microsoft.com/library/Gg398816(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-355">[CsApplicationEndpoint 이동](https://technet.microsoft.com/library/Gg398188(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-355">[Move-CsApplicationEndpoint](https://technet.microsoft.com/library/Gg398188(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-356">[이동-Move-cscommonareaphone](https://technet.microsoft.com/library/Gg412837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-356">[Move-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg412837(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-357">[이동-Get-csconferencedirectory](https://technet.microsoft.com/library/Gg412968(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-357">[Move-CsConferenceDirectory](https://technet.microsoft.com/library/Gg412968(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-358">[이사-CsExUmContact](https://technet.microsoft.com/library/Gg425842(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-358">[Move-CsExUmContact](https://technet.microsoft.com/library/Gg425842(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-359">[이동-Move-cslegacyuser](https://technet.microsoft.com/library/Gg413025(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-359">[Move-CsLegacyUser](https://technet.microsoft.com/library/Gg413025(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-360">[이동-Move-csmanagementserver](https://technet.microsoft.com/library/Gg412921(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-360">[Move-CsManagementServer](https://technet.microsoft.com/library/Gg412921(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-361">[이동-Enable-csmeetingroom](https://technet.microsoft.com/library/JJ204889(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-361">[Move-CsMeetingRoom](https://technet.microsoft.com/library/JJ204889(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-362">[이동-Export-csrgsconfiguration](https://technet.microsoft.com/library/Gg398782(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-362">[Move-CsRgsConfiguration](https://technet.microsoft.com/library/Gg398782(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-363">[CsUser 이동](https://technet.microsoft.com/library/Gg398528(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-363">[Move-CsUser](https://technet.microsoft.com/library/Gg398528(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-364">[새-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-364">[New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-365">[새-CsAdminRole](https://technet.microsoft.com/library/Gg398271(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-365">[New-CsAdminRole](https://technet.microsoft.com/library/Gg398271(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-366">[새-CsAllowedDomain](https://technet.microsoft.com/library/Gg398628(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-366">[New-CsAllowedDomain](https://technet.microsoft.com/library/Gg398628(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-367">[Move-csanalogdevice](https://technet.microsoft.com/library/Gg412937(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-367">[New-CsAnalogDevice](https://technet.microsoft.com/library/Gg412937(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-368">[새 CsAnnouncement](https://technet.microsoft.com/library/Gg398522(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-368">[New-CsAnnouncement](https://technet.microsoft.com/library/Gg398522(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-369">[Get-csarchivingconfiguration](https://technet.microsoft.com/library/Gg398471(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-369">[New-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg398471(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-370">[Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg399032(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-370">[New-CsArchivingPolicy](https://technet.microsoft.com/library/Gg399032(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-371">[Get-csautodiscoverconfiguration](https://technet.microsoft.com/library/Hh690022(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-371">[New-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh690022(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-372">[Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-372">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-373">[CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398175(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-373">[New-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398175(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-374">[Get-csblockeddomain](https://technet.microsoft.com/library/Gg398822(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-374">[New-CsBlockedDomain](https://technet.microsoft.com/library/Gg398822(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-375">[Get-cscallparkorbit](https://technet.microsoft.com/library/Gg398936(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-375">[New-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398936(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-376">[Get-cscdrconfiguration](https://technet.microsoft.com/library/Gg399018(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-376">[New-CsCdrConfiguration](https://technet.microsoft.com/library/Gg399018(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-377">[신규-CsClientPolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-377">[New-CsClientPolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-378">[새-CsClientPolicyEntry](https://technet.microsoft.com/library/Gg399046(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-378">[New-CsClientPolicyEntry](https://technet.microsoft.com/library/Gg399046(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-379">[새-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-379">[New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-380">[새-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398709(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-380">[New-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398709(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-381">[새-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398905(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-381">[New-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398905(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-382">[새-CsClsRegion](https://technet.microsoft.com/library/JJ204658(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-382">[New-CsClsRegion](https://technet.microsoft.com/library/JJ204658(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-383">[새 CsClsScenario](https://technet.microsoft.com/library/JJ205022(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-383">[New-CsClsScenario](https://technet.microsoft.com/library/JJ205022(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-384">[새-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205359(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-384">[New-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205359(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-385">[Move-cscommonareaphone](https://technet.microsoft.com/library/Gg398430(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-385">[New-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398430(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-386">[Get-csconferencedirectory](https://technet.microsoft.com/library/Gg413080(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-386">[New-CsConferenceDirectory](https://technet.microsoft.com/library/Gg413080(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-387">[Get-csconferencingconfiguration](https://technet.microsoft.com/library/Gg412967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-387">[New-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412967(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-388">[Get-csconferencingpolicy](https://technet.microsoft.com/library/Gg413019(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-388">[New-CsConferencingPolicy](https://technet.microsoft.com/library/Gg413019(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-389">[New-cscpsconfiguration](https://technet.microsoft.com/library/Gg412919(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-389">[New-CsCpsConfiguration](https://technet.microsoft.com/library/Gg412919(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-390">[New-csdeviceupdateconfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-390">[New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-391">[Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg398733(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-391">[New-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg398733(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-392">[Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg398350(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-392">[New-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398350(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-393">[New-csdiagnosticsfilter](https://technet.microsoft.com/library/Gg413009(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-393">[New-CsDiagnosticsFilter](https://technet.microsoft.com/library/Gg413009(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-394">[Get-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg398818(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-394">[New-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg398818(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-395">[Get-csdialinconferencingconfiguration](https://technet.microsoft.com/library/Gg412816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-395">[New-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg412816(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-396">[Set-csdialinconferencingdtmfconfiguration](https://technet.microsoft.com/library/Gg425792(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-396">[New-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425792(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-397">[새 CsDialPlan 플랜](https://technet.microsoft.com/library/Gg425860(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-397">[New-CsDialPlan](https://technet.microsoft.com/library/Gg425860(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-398">[New-csextendedtest](https://technet.microsoft.com/library/JJ205275(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-398">[New-CsExtendedTest](https://technet.microsoft.com/library/JJ205275(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-399">[Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg398441(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-399">[New-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398441(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-400">[새 전자 메일 주소](https://technet.microsoft.com/library/Gg398139(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-400">[New-CsExUmContact](https://technet.microsoft.com/library/Gg398139(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-401">[CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425897(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-401">[New-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425897(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-402">[새-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205114(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-402">[New-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205114(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-403">[Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg398718(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-403">[New-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398718(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-404">[Set-cshostedvoicemailpolicy](https://technet.microsoft.com/library/Gg398653(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-404">[New-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398653(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-405">[새-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-405">[New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-406">[새-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398244(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-406">[New-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398244(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-407">[New-csissuedcertid](https://technet.microsoft.com/library/Gg425814(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-407">[New-CsIssuedCertId](https://technet.microsoft.com/library/Gg425814(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-408">[새-C고 Ercosaccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-408">[New-CsKerberosAccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-409">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-409">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-410">[새-CsLocationPolicy](https://technet.microsoft.com/library/Gg398231(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-410">[New-CsLocationPolicy](https://technet.microsoft.com/library/Gg398231(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-411">[새-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690035(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-411">[New-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690035(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-412">[Get-csmediaconfiguration](https://technet.microsoft.com/library/Gg425881(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-412">[New-CsMediaConfiguration](https://technet.microsoft.com/library/Gg425881(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-413">[Get-csmeetingconfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-413">[New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-414">[Get-csmobilitypolicy](https://technet.microsoft.com/library/Hh689987(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-414">[New-CsMobilityPolicy](https://technet.microsoft.com/library/Hh689987(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-415">[Get-csnetworkbandwidthpolicyprofile](https://technet.microsoft.com/library/Gg398675(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-415">[New-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398675(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-416">[CsNetworkBWAlternatePath](https://technet.microsoft.com/library/Gg398732(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-416">[New-CsNetworkBWAlternatePath](https://technet.microsoft.com/library/Gg398732(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-417">[새-CsNetworkBWPolicy](https://technet.microsoft.com/library/Gg412916(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-417">[New-CsNetworkBWPolicy](https://technet.microsoft.com/library/Gg412916(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-418">[새-Csnetworkinterroute](https://technet.microsoft.com/library/Gg398779(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-418">[New-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398779(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-419">[Remove-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg398994(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-419">[New-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398994(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-420">[새-CsNetworkMediaBypassConfiguration](https://technet.microsoft.com/library/Gg425718(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-420">[New-CsNetworkMediaBypassConfiguration](https://technet.microsoft.com/library/Gg425718(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-421">[새-CsNetworkRegion](https://technet.microsoft.com/library/Gg425829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-421">[New-CsNetworkRegion](https://technet.microsoft.com/library/Gg425829(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-422">[새-Csnetwork지역 링크](https://technet.microsoft.com/library/Gg398437(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-422">[New-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398437(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-423">[새-CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-423">[New-CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-424">[새-CsNetworkSubnet](https://technet.microsoft.com/library/Gg398226(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-424">[New-CsNetworkSubnet](https://technet.microsoft.com/library/Gg398226(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-425">[새-CsOAuthServer](https://technet.microsoft.com/library/JJ205206(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-425">[New-CsOAuthServer](https://technet.microsoft.com/library/JJ205206(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-426">[Get-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ205097(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-426">[New-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ205097(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-427">[New-csoutboundtranslationrule](https://technet.microsoft.com/library/Gg412803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-427">[New-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg412803(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-428">[Get-cspartnerapplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-428">[New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-429">[Get-cspersistentchataddin](https://technet.microsoft.com/library/JJ204641(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-429">[New-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ204641(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-430">[Get-cspersistentchatcategory](https://technet.microsoft.com/library/JJ204803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-430">[New-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204803(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-431">[Get-cspersistentchatcomplianceconfiguration](https://technet.microsoft.com/library/JJ205163(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-431">[New-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ205163(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-432">[Get-cspersistentchatconfiguration](https://technet.microsoft.com/library/JJ205330(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-432">[New-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ205330(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-433">[Get-cspersistentchatendpoint](https://technet.microsoft.com/library/JJ204811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-433">[New-CsPersistentChatEndpoint](https://technet.microsoft.com/library/JJ204811(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-434">[Grant-cspersistentchatpolicy](https://technet.microsoft.com/library/JJ205396(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-434">[New-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ205396(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-435">[Clear-cspersistentchatroom](https://technet.microsoft.com/library/JJ205166(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-435">[New-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ205166(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-436">[Get-cspinpolicy](https://technet.microsoft.com/library/Gg398935(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-436">[New-CsPinPolicy](https://technet.microsoft.com/library/Gg398935(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-437">[Get-cspresencepolicy](https://technet.microsoft.com/library/Gg412747(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-437">[New-CsPresencePolicy](https://technet.microsoft.com/library/Gg412747(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-438">[Remove-cspresenceprovider](https://technet.microsoft.com/library/JJ204895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-438">[New-CsPresenceProvider](https://technet.microsoft.com/library/JJ204895(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-439">[Get-csprivacyconfiguration](https://technet.microsoft.com/library/Gg398807(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-439">[New-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398807(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-440">[새-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398335(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-440">[New-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398335(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-441">[Disable-cspublicprovider](https://technet.microsoft.com/library/Gg398161(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-441">[New-CsPublicProvider](https://technet.microsoft.com/library/Gg398161(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-442">[Get-cspushnotificationconfiguration](https://technet.microsoft.com/library/Hh690027(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-442">[New-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690027(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-443">[Remove-csqoeconfiguration](https://technet.microsoft.com/library/Gg398325(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-443">[New-CsQoEConfiguration](https://technet.microsoft.com/library/Gg398325(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-444">[Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg425893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-444">[New-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg425893(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-445">[Get-csreportingconfiguration](https://technet.microsoft.com/library/JJ204787(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-445">[New-CsReportingConfiguration](https://technet.microsoft.com/library/JJ204787(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-446">[Get-csrgsagentgroup](https://technet.microsoft.com/library/Gg413065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-446">[New-CsRgsAgentGroup](https://technet.microsoft.com/library/Gg413065(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-447">[New-csrgsanswer](https://technet.microsoft.com/library/Gg412812(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-447">[New-CsRgsAnswer](https://technet.microsoft.com/library/Gg412812(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-448">[New-csrgscallaction](https://technet.microsoft.com/library/Gg398136(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-448">[New-CsRgsCallAction](https://technet.microsoft.com/library/Gg398136(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-449">[New-csrgsholiday](https://technet.microsoft.com/library/Gg398075(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-449">[New-CsRgsHoliday](https://technet.microsoft.com/library/Gg398075(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-450">[New-csrgsholidayset](https://technet.microsoft.com/library/Gg398403(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-450">[New-CsRgsHolidaySet](https://technet.microsoft.com/library/Gg398403(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-451">[Get-csrgshoursofbusiness](https://technet.microsoft.com/library/Gg398291(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-451">[New-CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg398291(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-452">[New-csrgsprompt](https://technet.microsoft.com/library/Gg398486(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-452">[New-CsRgsPrompt](https://technet.microsoft.com/library/Gg398486(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-453">[New-csrgsquestion](https://technet.microsoft.com/library/Gg398186(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-453">[New-CsRgsQuestion](https://technet.microsoft.com/library/Gg398186(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-454">[Get-csrgsqueue](https://technet.microsoft.com/library/Gg398989(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-454">[New-CsRgsQueue](https://technet.microsoft.com/library/Gg398989(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-455">[New-csrgstimerange](https://technet.microsoft.com/library/Gg399040(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-455">[New-CsRgsTimeRange](https://technet.microsoft.com/library/Gg399040(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-456">[Get-csrgsworkflow](https://technet.microsoft.com/library/Gg398246(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-456">[New-CsRgsWorkflow](https://technet.microsoft.com/library/Gg398246(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-457">[새-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-457">[New-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-458">[새-CsServerApplication](https://technet.microsoft.com/library/Gg398096(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-458">[New-CsServerApplication](https://technet.microsoft.com/library/Gg398096(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-459">[New-cssimpleurl](https://technet.microsoft.com/library/Gg398180(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-459">[New-CsSimpleUrl](https://technet.microsoft.com/library/Gg398180(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-460">[Get-cssimpleurlconfiguration](https://technet.microsoft.com/library/Gg425813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-460">[New-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg425813(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-461">[New-cssimpleurlentry](https://technet.microsoft.com/library/Gg425902(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-461">[New-CsSimpleUrlEntry](https://technet.microsoft.com/library/Gg425902(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-462">[New-cssipdomain](https://technet.microsoft.com/library/Gg425857(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-462">[New-CsSipDomain](https://technet.microsoft.com/library/Gg425857(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-463">[New-cssipproxycustom](https://technet.microsoft.com/library/Gg425904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-463">[New-CsSipProxyCustom](https://technet.microsoft.com/library/Gg425904(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-464">[New-cssipproxyrealm](https://technet.microsoft.com/library/Gg413084(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-464">[New-CsSipProxyRealm](https://technet.microsoft.com/library/Gg413084(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-465">[New-cssipproxytcp](https://technet.microsoft.com/library/Gg425745(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-465">[New-CsSipProxyTCP](https://technet.microsoft.com/library/Gg425745(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-466">[New-cssipproxytls](https://technet.microsoft.com/library/Gg398629(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-466">[New-CsSipProxyTLS](https://technet.microsoft.com/library/Gg398629(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-467">[New-cssipproxytransport](https://technet.microsoft.com/library/Gg398489(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-467">[New-CsSipProxyTransport](https://technet.microsoft.com/library/Gg398489(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-468">[New-cssipproxyusedefault](https://technet.microsoft.com/library/Gg398274(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-468">[New-CsSipProxyUseDefault](https://technet.microsoft.com/library/Gg398274(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-469">[New-cssipproxyusedefaultcert](https://technet.microsoft.com/library/Gg425858(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-469">[New-CsSipProxyUseDefaultCert](https://technet.microsoft.com/library/Gg425858(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-470">[Get-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg413041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-470">[New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg413041(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-471">[새-CsStaticRoute](https://technet.microsoft.com/library/Gg398265(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-471">[New-CsStaticRoute](https://technet.microsoft.com/library/Gg398265(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-472">[새-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg425811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-472">[New-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg425811(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-473">[신규-CsTestDevice](https://technet.microsoft.com/library/Gg425899(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-473">[New-CsTestDevice](https://technet.microsoft.com/library/Gg425899(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-474">[Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg413021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-474">[New-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg413021(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-475">[New-cstrustedapplication](https://technet.microsoft.com/library/Gg398259(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-475">[New-CsTrustedApplication](https://technet.microsoft.com/library/Gg398259(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-476">[CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398405(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-476">[New-CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398405(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-477">[CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398594(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-477">[New-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398594(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-478">[New-cstrustedapplicationpool](https://technet.microsoft.com/library/Gg425804(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-478">[New-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg425804(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-479">[Set-csucphoneconfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-479">[New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-480">[New-csunassignednumber](https://technet.microsoft.com/library/Gg398651(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-480">[New-CsUnassignedNumber](https://technet.microsoft.com/library/Gg398651(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-481">[Get-csuserreplicatorconfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-481">[New-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-482">[새-Csuser서비스 구성](https://technet.microsoft.com/library/Gg412926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-482">[New-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg412926(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-483">[새-Csuser서비스 정책](https://technet.microsoft.com/library/JJ205072(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-483">[New-CsUserServicesPolicy](https://technet.microsoft.com/library/JJ205072(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-484">[New-csvoicemailreroutingconfiguration](https://technet.microsoft.com/library/Gg425849(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-484">[New-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg425849(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-485">[Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg398240(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-485">[New-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398240(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-486">[Set-csvoicepolicy](https://technet.microsoft.com/library/Gg425856(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-486">[New-CsVoicePolicy](https://technet.microsoft.com/library/Gg425856(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-487">[CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-487">[New-CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-488">[Get-csvoiceroute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-488">[New-CsVoiceRoute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-489">[Get-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ205135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-489">[New-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205135(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-490">[수정한 구성은 test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398961(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-490">[New-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398961(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-491">[Get-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ205254(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-491">[New-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ205254(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-492">[은 new-csweblink](https://technet.microsoft.com/library/Hh690053(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-492">[New-CsWebLink](https://technet.microsoft.com/library/Hh690053(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-493">[Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg398440(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-493">[New-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398440(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-494">[New-cswebtrustedcacertificate](https://technet.microsoft.com/library/Gg412746(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-494">[New-CsWebTrustedCACertificate](https://technet.microsoft.com/library/Gg412746(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-495">[새-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204631(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-495">[New-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204631(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-496">[게시-Export-cslisconfiguration](https://technet.microsoft.com/library/Gg398364(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-496">[Publish-CsLisConfiguration](https://technet.microsoft.com/library/Gg398364(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-497">[게시-Enable-cstopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-497">[Publish-CsTopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-498">[CsAddressBookConfiguration 제거](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-498">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-499">[제거-CsAdminRole](https://technet.microsoft.com/library/Gg413036(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-499">[Remove-CsAdminRole](https://technet.microsoft.com/library/Gg413036(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-500">[제거-CsAllowedDomain](https://technet.microsoft.com/library/Gg398913(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-500">[Remove-CsAllowedDomain](https://technet.microsoft.com/library/Gg398913(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-501">[Move-csanalogdevice을 제거 합니다.](rehttps://technet.microsoft.com/library/Gg398816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-501">[Remove-CsAnalogDevice](rehttps://technet.microsoft.com/library/Gg398816(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-502">[CsAnnouncement-사후 알림](https://technet.microsoft.com/library/Gg412766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-502">[Remove-CsAnnouncement](https://technet.microsoft.com/library/Gg412766(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-503">[Get-csarchivingconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398951(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-503">[Remove-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg398951(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-504">[Grant-csarchivingpolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg425924(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-504">[Remove-CsArchivingPolicy](https://technet.microsoft.com/library/Gg425924(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-505">[Get-csautodiscoverconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Hh690054(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-505">[Remove-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh690054(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-506">[Get-csavedgeconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-506">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-507">[Get-csbackupserviceconfiguration을 제거 합니다.](https://technet.microsoft.com/library/JJ204903(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-507">[Remove-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ204903(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-508">[CsBandwidthPolicyServiceConfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398877(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-508">[Remove-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398877(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-509">[Get-csblockeddomain을 제거 합니다.](https://technet.microsoft.com/library/Gg425832(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-509">[Remove-CsBlockedDomain](https://technet.microsoft.com/library/Gg425832(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-510">[Get-cscallparkorbit을 제거 합니다.](https://technet.microsoft.com/library/Gg412901(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-510">[Remove-CsCallParkOrbit](https://technet.microsoft.com/library/Gg412901(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-511">[Get-cscdrconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398451(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-511">[Remove-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398451(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-512">[Set-cscertificate을 제거 합니다.](https://technet.microsoft.com/library/Gg412895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-512">[Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-513">[제거-CsClientPolicy](https://technet.microsoft.com/library/Gg425772(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-513">[Remove-CsClientPolicy](https://technet.microsoft.com/library/Gg425772(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-514">[제거-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-514">[Remove-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-515">[제거-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg425801(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-515">[Remove-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg425801(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-516">[제거-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398541(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-516">[Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398541(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-517">[-CsClsRegion 제거](https://technet.microsoft.com/library/JJ204971(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-517">[Remove-CsClsRegion](https://technet.microsoft.com/library/JJ204971(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-518">[제거-CsClsScenario](https://technet.microsoft.com/library/JJ205010(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-518">[Remove-CsClsScenario](https://technet.microsoft.com/library/JJ205010(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-519">[제거-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204958(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-519">[Remove-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204958(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-520">[Move-cscommonareaphone을 제거 합니다.](rehttps://technet.microsoft.com/library/Gg412837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-520">[Remove-CsCommonAreaPhone](rehttps://technet.microsoft.com/library/Gg412837(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-521">[Get-csconferencedirectory을 제거 합니다.](rehttps://technet.microsoft.com/library/Gg412968(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-521">[Remove-CsConferenceDirectory](rehttps://technet.microsoft.com/library/Gg412968(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-522">[Get-csconferencedisclaimer을 제거 합니다.](https://technet.microsoft.com/library/Gg398243(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-522">[Remove-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398243(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-523">[Get-csconferencingconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg412767(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-523">[Remove-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412767(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-524">[Get-csconferencingpolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg398728(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-524">[Remove-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398728(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-525">[Remove-csconfigurationstorelocation을 제거 합니다.](https://technet.microsoft.com/library/Gg398214(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-525">[Remove-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398214(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-526">[New-cscpsconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398358(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-526">[Remove-CsCpsConfiguration](https://technet.microsoft.com/library/Gg398358(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-527">[New-csdeviceupdateconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg425933(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-527">[Remove-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425933(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-528">[Get-csdeviceupdaterule을 제거 합니다.](https://technet.microsoft.com/library/Gg425930(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-528">[Remove-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg425930(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-529">[Get-csdiagnosticconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg412853(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-529">[Remove-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg412853(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-530">[Get-csdiagnosticheaderconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398941(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-530">[Remove-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398941(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-531">[Get-csdialinconferencingaccessnumber을 제거 합니다.](https://technet.microsoft.com/library/Gg412782(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-531">[Remove-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg412782(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-532">[Get-csdialinconferencingconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398174(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-532">[Remove-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398174(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-533">[Set-csdialinconferencingdtmfconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg425894(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-533">[Remove-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425894(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-534">[CsDialPlan 다이얼 플랜 제거](https://technet.microsoft.com/library/Gg398791(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-534">[Remove-CsDialPlan](https://technet.microsoft.com/library/Gg398791(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-535">[CsEnhancedEmergencyServiceDisclaimer을 제거 합니다.](https://technet.microsoft.com/library/Gg425810(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-535">[Remove-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg425810(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-536">[Get-csexternalaccesspolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg399057(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-536">[Remove-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg399057(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-537">[제거-CsExUmContact](rehttps://technet.microsoft.com/library/Gg425842(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-537">[Remove-CsExUmContact](rehttps://technet.microsoft.com/library/Gg425842(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-538">[CsFileTransferFilterConfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg413064(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-538">[Remove-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg413064(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-539">[제거-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205201(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-539">[Remove-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205201(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-540">[Get-cshealthmonitoringconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg425794(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-540">[Remove-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425794(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-541">[Set-cshostedvoicemailpolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg398211(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-541">[Remove-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398211(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-542">[제거-CsHostingProvider](https://technet.microsoft.com/library/Gg425809(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-542">[Remove-CsHostingProvider](https://technet.microsoft.com/library/Gg425809(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-543">[제거-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398171(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-543">[Remove-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398171(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-544">[Get-cskerberosaccountassignment을 제거 합니다.](https://technet.microsoft.com/library/Gg413052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-544">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-545">[Get-cslislocation을 제거 합니다.](https://technet.microsoft.com/library/Gg425722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-545">[Remove-CsLisLocation](https://technet.microsoft.com/library/Gg425722(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-546">[CsLisPort을 제거 합니다.](https://technet.microsoft.com/library/Gg412899(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-546">[Remove-CsLisPort](https://technet.microsoft.com/library/Gg412899(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-547">[CsLisServiceProvider을 제거 합니다.](https://technet.microsoft.com/library/Gg398904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-547">[Remove-CsLisServiceProvider](https://technet.microsoft.com/library/Gg398904(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-548">[CsLisSubnet을 제거 합니다.](https://technet.microsoft.com/library/Gg413053(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-548">[Remove-CsLisSubnet](https://technet.microsoft.com/library/Gg413053(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-549">[CsLisSwitch을 제거 합니다.](https://technet.microsoft.com/library/Gg398352(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-549">[Remove-CsLisSwitch](https://technet.microsoft.com/library/Gg398352(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-550">[CsLisWirelessAccessPoint을 제거 합니다.](https://technet.microsoft.com/library/Gg398461(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-550">[Remove-CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398461(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-551">[제거-CsLocationPolicy](https://technet.microsoft.com/library/Gg398727(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-551">[Remove-CsLocationPolicy](https://technet.microsoft.com/library/Gg398727(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-552">[제거-CsManagementConnection](https://technet.microsoft.com/library/Gg425803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-552">[Remove-CsManagementConnection](https://technet.microsoft.com/library/Gg425803(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-553">[-CsMcxConfiguration을 제거 합니다.](https://technet.microsoft.com/library/Hh690026(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-553">[Remove-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690026(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-554">[Get-csmediaconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398705(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-554">[Remove-CsMediaConfiguration](https://technet.microsoft.com/library/Gg398705(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-555">[Get-csmeetingconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg412775(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-555">[Remove-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-556">[Get-csmobilitypolicy을 제거 합니다.](https://technet.microsoft.com/library/Hh690048(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-556">[Remove-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690048(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-557">[Get-csnetworkbandwidthpolicyprofile을 제거 합니다.](https://technet.microsoft.com/library/Gg398609(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-557">[Remove-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398609(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-558">[Get-csnetworkconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-558">[Remove-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398938(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-559">[제거-Csnetworkinterroute](https://technet.microsoft.com/library/Gg398743(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-559">[Remove-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398743(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-560">[Remove-csnetworkintersitepolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg398963(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-560">[Remove-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398963(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-561">[CsNetworkRegion 제거](https://technet.microsoft.com/library/Gg398466(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-561">[Remove-CsNetworkRegion](https://technet.microsoft.com/library/Gg398466(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-562">[-Csnetwork지역 링크 제거](https://technet.microsoft.com/library/Gg413012(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-562">[Remove-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg413012(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-563">[CsNetworkSite를 제거 합니다.](https://technet.microsoft.com/library/Gg398135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-563">[Remove-CsNetworkSite](https://technet.microsoft.com/library/Gg398135(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-564">[제거-CsNetworkSubnet](https://technet.microsoft.com/library/Gg425726(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-564">[Remove-CsNetworkSubnet](https://technet.microsoft.com/library/Gg425726(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-565">[CsOAuthServer 제거](https://technet.microsoft.com/library/JJ205408(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-565">[Remove-CsOAuthServer](https://technet.microsoft.com/library/JJ205408(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-566">[Get-csoutboundcallingnumbertranslationrule을 제거 합니다.](https://technet.microsoft.com/library/JJ204836(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-566">[Remove-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ204836(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-567">[New-csoutboundtranslationrule을 제거 합니다.](https://technet.microsoft.com/library/Gg398556(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-567">[Remove-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398556(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-568">[Get-cspartnerapplication을 제거 합니다.](https://technet.microsoft.com/library/JJ204820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-568">[Remove-CsPartnerApplication](https://technet.microsoft.com/library/JJ204820(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-569">[Get-cspersistentchataddin을 제거 합니다.](https://technet.microsoft.com/library/JJ205350(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-569">[Remove-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ205350(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-570">[Get-cspersistentchatcategory을 제거 합니다.](https://technet.microsoft.com/library/JJ204660(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-570">[Remove-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204660(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-571">[Get-cspersistentchatcomplianceconfiguration을 제거 합니다.](https://technet.microsoft.com/library/JJ204767(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-571">[Remove-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ204767(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-572">[Get-cspersistentchatconfiguration을 제거 합니다.](https://technet.microsoft.com/library/JJ204927(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-572">[Remove-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ204927(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-573">[Get-cspersistentchatendpoint을 제거 합니다.](https://technet.microsoft.com/library/JJ204626(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-573">[Remove-CsPersistentChatEndpoint](https://technet.microsoft.com/library/JJ204626(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-574">[Test-cspersistentchatmessage을 제거 합니다.](https://technet.microsoft.com/library/JJ204668(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-574">[Remove-CsPersistentChatMessage](https://technet.microsoft.com/library/JJ204668(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-575">[Grant-cspersistentchatpolicy을 제거 합니다.](https://technet.microsoft.com/library/JJ205301(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-575">[Remove-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ205301(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-576">[Clear-cspersistentchatroom을 제거 합니다.](https://technet.microsoft.com/library/JJ204639(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-576">[Remove-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204639(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-577">[Get-cspinpolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg398431(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-577">[Remove-CsPinPolicy](https://technet.microsoft.com/library/Gg398431(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-578">[Get-cspresencepolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg399070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-578">[Remove-CsPresencePolicy](https://technet.microsoft.com/library/Gg399070(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-579">[Remove-cspresenceprovider을 제거 합니다.](https://technet.microsoft.com/library/JJ205036(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-579">[Remove-CsPresenceProvider](https://technet.microsoft.com/library/JJ205036(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-580">[Get-csprivacyconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg425821(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-580">[Remove-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg425821(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-581">[CsProxyConfiguration 제거](https://technet.microsoft.com/library/Gg398553(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-581">[Remove-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398553(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-582">[Disable-cspublicprovider을 제거 합니다.](https://technet.microsoft.com/library/Gg412906(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-582">[Remove-CsPublicProvider](https://technet.microsoft.com/library/Gg412906(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-583">[Get-cspushnotificationconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Hh690028(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-583">[Remove-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690028(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-584">[Remove-csqoeconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg425879(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-584">[Remove-CsQoEConfiguration](https://technet.microsoft.com/library/Gg425879(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-585">[Get-csregistrarconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398482(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-585">[Remove-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398482(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-586">[Get-csreportingconfiguration을 제거 합니다.](https://technet.microsoft.com/library/JJ204711(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-586">[Remove-CsReportingConfiguration](https://technet.microsoft.com/library/JJ204711(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-587">[Get-csrgsagentgroup을 제거 합니다.](https://technet.microsoft.com/library/Gg398969(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-587">[Remove-CsRgsAgentGroup](https://technet.microsoft.com/library/Gg398969(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-588">[New-csrgsholidayset을 제거 합니다.](https://technet.microsoft.com/library/Gg398521(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-588">[Remove-CsRgsHolidaySet](https://technet.microsoft.com/library/Gg398521(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-589">[Get-csrgshoursofbusiness을 제거 합니다.](https://technet.microsoft.com/library/Gg398568(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-589">[Remove-CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg398568(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-590">[Get-csrgsqueue을 제거 합니다.](https://technet.microsoft.com/library/Gg398576(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-590">[Remove-CsRgsQueue](https://technet.microsoft.com/library/Gg398576(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-591">[Get-csrgsworkflow을 제거 합니다.](https://technet.microsoft.com/library/Gg398765(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-591">[Remove-CsRgsWorkflow](https://technet.microsoft.com/library/Gg398765(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-592">[제거-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg398643(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-592">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg398643(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-593">[CsServerApplication 제거](https://technet.microsoft.com/library/Gg398366(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-593">[Remove-CsServerApplication](https://technet.microsoft.com/library/Gg398366(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-594">[Get-cssimpleurlconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398515(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-594">[Remove-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398515(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-595">[New-cssipdomain을 제거 합니다.](https://technet.microsoft.com/library/Gg398865(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-595">[Remove-CsSipDomain](https://technet.microsoft.com/library/Gg398865(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-596">[Get-cssipresponsecodetranslationrule을 제거 합니다.](https://technet.microsoft.com/library/Gg412932(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-596">[Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg412932(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-597">[CsSlaConfiguration을 제거 합니다.](https://technet.microsoft.com/library/Mt703201(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-597">[Remove-CsSlaConfiguration](https://technet.microsoft.com/library/Mt703201(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-598">[CsSlaDelegates을 제거 합니다.](https://technet.microsoft.com/library/Mt703203(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-598">[Remove-CsSlaDelegates](https://technet.microsoft.com/library/Mt703203(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-599">[제거-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398668(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-599">[Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398668(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-600">[제거-CsTestDevice](https://technet.microsoft.com/library/Gg398790(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-600">[Remove-CsTestDevice](https://technet.microsoft.com/library/Gg398790(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-601">[Get-cstestusercredential을 제거 합니다.](https://technet.microsoft.com/library/JJ204870(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-601">[Remove-CsTestUserCredential](https://technet.microsoft.com/library/JJ204870(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-602">[Get-cstrunkconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg425943(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-602">[Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-603">[New-cstrustedapplication을 제거 합니다.](https://technet.microsoft.com/library/Gg398176(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-603">[Remove-CsTrustedApplication](https://technet.microsoft.com/library/Gg398176(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-604">[CsTrustedApplicationComputer을 제거 합니다.](https://technet.microsoft.com/library/Gg398838(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-604">[Remove-CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398838(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-605">[CsTrustedApplicationEndpoint을 제거 합니다.](https://technet.microsoft.com/library/Gg398837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-605">[Remove-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398837(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-606">[New-cstrustedapplicationpool을 제거 합니다.](https://technet.microsoft.com/library/Gg398750(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-606">[Remove-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg398750(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-607">[Set-csucphoneconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398249(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-607">[Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-608">[New-csunassignednumber을 제거 합니다.](https://technet.microsoft.com/library/Gg398209(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-608">[Remove-CsUnassignedNumber](https://technet.microsoft.com/library/Gg398209(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-609">[제거-CsUserAcp](https://technet.microsoft.com/library/Gg398982(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-609">[Remove-CsUserAcp](https://technet.microsoft.com/library/Gg398982(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-610">[Get-csuserreplicatorconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg425738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-610">[Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-611">[Csuser서비스 구성 제거](https://technet.microsoft.com/library/Gg398722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-611">[Remove-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398722(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-612">[Csuser서비스 정책 제거](https://technet.microsoft.com/library/JJ204629(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-612">[Remove-CsUserServicesPolicy](https://technet.microsoft.com/library/JJ204629(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-613">[CsUserStoreBackupData 제거](https://technet.microsoft.com/library/JJ205003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-613">[Remove-CsUserStoreBackupData](https://technet.microsoft.com/library/JJ205003(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-614">[CsVoiceConfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398804(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-614">[Remove-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398804(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-615">[New-csvoicemailreroutingconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398573(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-615">[Remove-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg398573(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-616">[Get-csvoicenormalizationrule을 제거 합니다.](https://technet.microsoft.com/library/Gg398501(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-616">[Remove-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398501(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-617">[Set-csvoicepolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg398309(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-617">[Remove-CsVoicePolicy](https://technet.microsoft.com/library/Gg398309(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-618">[Get-csvoiceroute을 제거 합니다.](https://technet.microsoft.com/library/Gg398468(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-618">[Remove-CsVoiceRoute](https://technet.microsoft.com/library/Gg398468(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-619">[Get-csvoiceroutingpolicy을 제거 합니다.](https://technet.microsoft.com/library/JJ204799(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-619">[Remove-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ204799(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-620">[수정한 구성은 test-csvoicetestconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg412813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-620">[Remove-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412813(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-621">[Get-cswatchernodeconfiguration을 제거 합니다.](https://technet.microsoft.com/library/JJ204926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-621">[Remove-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204926(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-622">[Set-cswebserviceconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398266(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-622">[Remove-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398266(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-623">[제거-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ205055(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-623">[Remove-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ205055(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-624">[요청-Set-cscertificate](https://technet.microsoft.com/library/Gg425723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-624">[Request-CsCertificate](https://technet.microsoft.com/library/Gg425723(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-625">[Reset-Get-csdeviceupdaterule](https://technet.microsoft.com/library/Gg398181(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-625">[Reset-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398181(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-626">[복원-Get-csdeviceupdaterule](https://technet.microsoft.com/library/Gg398305(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-626">[Restore-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398305(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-627">[Get-csclientcertificate](https://technet.microsoft.com/library/Gg425748(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-627">[Revoke-CsClientCertificate](https://technet.microsoft.com/library/Gg425748(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-628">[CsOUPermission](https://technet.microsoft.com/library/Gg398977(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-628">[Revoke-CsOUPermission](https://technet.microsoft.com/library/Gg398977(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-629">[CsSetupPermission](https://technet.microsoft.com/library/Gg425834(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-629">[Revoke-CsSetupPermission](https://technet.microsoft.com/library/Gg425834(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-630">[Set-csaccessedgeconfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-630">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-631">[설정-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-631">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-632">[설정-CsAdminRole](https://technet.microsoft.com/library/Gg399066(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-632">[Set-CsAdminRole](https://technet.microsoft.com/library/Gg399066(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-633">[설정-CsAllowedDomain](https://technet.microsoft.com/library/Gg398931(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-633">[Set-CsAllowedDomain](https://technet.microsoft.com/library/Gg398931(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-634">[Move-csanalogdevice](https://technet.microsoft.com/library/Gg412843(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-634">[Set-CsAnalogDevice](https://technet.microsoft.com/library/Gg412843(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-635">[CsAnnouncement](https://technet.microsoft.com/library/Gg425752(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-635">[Set-CsAnnouncement](https://technet.microsoft.com/library/Gg425752(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-636">[설정-CsApplicationServer](https://technet.microsoft.com/library/Gg398562(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-636">[Set-CsApplicationServer](https://technet.microsoft.com/library/Gg398562(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-637">[Get-csarchivingconfiguration](https://technet.microsoft.com/library/Gg413030(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-637">[Set-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg413030(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-638">[Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg398294(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-638">[Set-CsArchivingPolicy](https://technet.microsoft.com/library/Gg398294(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-639">[CsArchivingServer](https://technet.microsoft.com/library/Gg398923(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-639">[Set-CsArchivingServer](https://technet.microsoft.com/library/Gg398923(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-640">[설정-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg398907(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-640">[Set-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg398907(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-641">[Get-csautodiscoverconfiguration](https://technet.microsoft.com/library/Hh689980(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-641">[Set-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh689980(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-642">[Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-642">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-643">[Get-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ205006(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-643">[Set-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205006(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-644">[CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412863(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-644">[Set-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412863(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-645">[Get-csblockeddomain](https://technet.microsoft.com/library/Gg398090(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-645">[Set-CsBlockedDomain](https://technet.microsoft.com/library/Gg398090(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-646">[Get-cscallparkorbit](https://technet.microsoft.com/library/Gg398796(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-646">[Set-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398796(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-647">[Set-cscallparkservicemusiconholdfile](https://technet.microsoft.com/library/Gg412836(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-647">[Set-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/library/Gg412836(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-648">[Get-cscdrconfiguration](https://technet.microsoft.com/library/Gg398774(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-648">[Set-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398774(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-649">[Set-cscertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-649">[Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-650">[설정-CsClientPin](https://technet.microsoft.com/library/Gg398929(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-650">[Set-CsClientPin](https://technet.microsoft.com/library/Gg398929(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-651">[설정-CsClientPolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-651">[Set-CsClientPolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-652">[설정-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-652">[Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-653">[설정-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-653">[Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-654">[설정-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg425790(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-654">[Set-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg425790(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-655">[설정-CsClsRegion](https://technet.microsoft.com/library/JJ204746(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-655">[Set-CsClsRegion](https://technet.microsoft.com/library/JJ204746(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-656">[설정-CsClsScenario](https://technet.microsoft.com/library/JJ204622(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-656">[Set-CsClsScenario](https://technet.microsoft.com/library/JJ204622(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-657">[설정-CsClsSearchTerm](https://technet.microsoft.com/library/JJ204911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-657">[Set-CsClsSearchTerm](https://technet.microsoft.com/library/JJ204911(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-658">[설정-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204700(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-658">[Set-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204700(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-659">[Move-cscommonareaphone](https://technet.microsoft.com/library/Gg398579(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-659">[Set-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398579(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-660">[Get-csconferencedisclaimer](https://technet.microsoft.com/library/Gg398776(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-660">[Set-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398776(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-661">[Set-csconferenceserver](https://technet.microsoft.com/library/Gg398738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-661">[Set-CsConferenceServer](https://technet.microsoft.com/library/Gg398738(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-662">[Get-csconferencingconfiguration](https://technet.microsoft.com/library/Gg412969(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-662">[Set-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412969(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-663">[Get-csconferencingpolicy](https://technet.microsoft.com/library/Gg425788(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-663">[Set-CsConferencingPolicy](https://technet.microsoft.com/library/Gg425788(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-664">[Remove-csconfigurationstorelocation](https://technet.microsoft.com/library/Gg398258(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-664">[Set-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398258(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-665">[New-cscpsconfiguration](https://technet.microsoft.com/library/Gg412721(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-665">[Set-CsCpsConfiguration](https://technet.microsoft.com/library/Gg412721(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-666">[New-csdeviceupdateconfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-666">[Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-667">[Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg425734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-667">[Set-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg425734(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-668">[Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg399045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-668">[Set-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg399045(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-669">[Get-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg425770(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-669">[Set-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg425770(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-670">[Get-csdialinconferencingconfiguration](https://technet.microsoft.com/library/Gg425825(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-670">[Set-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg425825(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-671">[Set-csdialinconferencingdtmfconfiguration](https://technet.microsoft.com/library/Gg398860(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-671">[Set-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg398860(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-672">[설정-CsDialPlan 플랜](https://technet.microsoft.com/library/Gg398644(v=OCS.15)) 설정-CsDialPlan 플랜</span><span class="sxs-lookup"><span data-stu-id="25deb-672">[Set-CsDialPlan](https://technet.microsoft.com/library/Gg398644(v=OCS.15))Set-CsDialPlan</span></span>

  - <span data-ttu-id="25deb-673">[설정-CsDirector](https://technet.microsoft.com/library/Gg398565(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-673">[Set-CsDirector](https://technet.microsoft.com/library/Gg398565(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-674">[Set-csedgeserver](https://technet.microsoft.com/library/Gg398859(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-674">[Set-CsEdgeServer](https://technet.microsoft.com/library/Gg398859(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-675">[CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg398620(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-675">[Set-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg398620(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-676">[Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg398916(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-676">[Set-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398916(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-677">[Set-CsExUmContact](https://technet.microsoft.com/library/Gg412944(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-677">[Set-CsExUmContact](https://technet.microsoft.com/library/Gg412944(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-678">[CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425736(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-678">[Set-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425736(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-679">[설정-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205084(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-679">[Set-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205084(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-680">[Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg425847(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-680">[Set-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425847(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-681">[Set-cshostedvoicemailpolicy](https://technet.microsoft.com/library/Gg412722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-681">[Set-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg412722(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-682">[Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-682">[Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-683">[Set-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg412960(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-683">[Set-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg412960(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-684">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-684">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-685">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-685">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-686">[Get-cslislocation](https://technet.microsoft.com/library/Gg398757(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-686">[Set-CsLisLocation](https://technet.microsoft.com/library/Gg398757(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-687">[CsLisPort](https://technet.microsoft.com/library/Gg398700(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-687">[Set-CsLisPort](https://technet.microsoft.com/library/Gg398700(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-688">[CsLisServiceProvider](https://technet.microsoft.com/library/Gg425911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-688">[Set-CsLisServiceProvider](https://technet.microsoft.com/library/Gg425911(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-689">[CsLisSubnet](https://technet.microsoft.com/library/Gg399016(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-689">[Set-CsLisSubnet](https://technet.microsoft.com/library/Gg399016(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-690">[CsLisSwitch](https://technet.microsoft.com/library/Gg412823(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-690">[Set-CsLisSwitch](https://technet.microsoft.com/library/Gg412823(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-691">[CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg412723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-691">[Set-CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg412723(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-692">[설정-CsLocationPolicy](https://technet.microsoft.com/library/Gg412987(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-692">[Set-CsLocationPolicy](https://technet.microsoft.com/library/Gg412987(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-693">[설정-CsManagementConnection](https://technet.microsoft.com/library/Gg413045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-693">[Set-CsManagementConnection](https://technet.microsoft.com/library/Gg413045(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-694">[-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690050(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-694">[Set-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690050(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-695">[Move-csmanagementserver](https://technet.microsoft.com/library/Gg398465(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-695">[Set-CsManagementServer](https://technet.microsoft.com/library/Gg398465(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-696">[Get-csmediaconfiguration](https://technet.microsoft.com/library/Gg398580(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-696">[Set-CsMediaConfiguration](https://technet.microsoft.com/library/Gg398580(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-697">[Set-CsMediationServer](https://technet.microsoft.com/library/Gg398213(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-697">[Set-CsMediationServer](https://technet.microsoft.com/library/Gg398213(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-698">[Get-csmeetingconfiguration](https://technet.microsoft.com/library/Gg398648(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-698">[Set-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398648(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-699">[Enable-csmeetingroom](https://technet.microsoft.com/library/JJ204831(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-699">[Set-CsMeetingRoom](https://technet.microsoft.com/library/JJ204831(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-700">[Get-csmobilitypolicy](https://technet.microsoft.com/library/Hh690021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-700">[Set-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690021(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-701">[CsMonitoringServer](https://technet.microsoft.com/library/Gg425776(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-701">[Set-CsMonitoringServer](https://technet.microsoft.com/library/Gg425776(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-702">[Get-csnetworkbandwidthpolicyprofile](https://technet.microsoft.com/library/Gg398338(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-702">[Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398338(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-703">[Get-csnetworkconfiguration](https://technet.microsoft.com/library/Gg398927(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-703">[Set-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398927(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-704">[설정-Csnetworkinter지역 경로](https://technet.microsoft.com/library/Gg398410(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-704">[Set-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398410(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-705">[Remove-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg398772(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-705">[Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398772(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-706">[설정-CsNetworkRegion](https://technet.microsoft.com/library/Gg413089(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-706">[Set-CsNetworkRegion](https://technet.microsoft.com/library/Gg413089(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-707">[설정-Csnetwork지역 링크](https://technet.microsoft.com/library/Gg412867(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-707">[Set-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg412867(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-708">[설정-CsNetworkSite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-708">[Set-CsNetworkSite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-709">[설정-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-709">[Set-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412739(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-710">[Set-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ204841(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-710">[Set-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ204841(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-711">[Set-CsOAuthServer](https://technet.microsoft.com/library/JJ204896(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-711">[Set-CsOAuthServer](https://technet.microsoft.com/library/JJ204896(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-712">[Get-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ205400(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-712">[Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ205400(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-713">[New-csoutboundtranslationrule](https://technet.microsoft.com/library/Gg413073(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-713">[Set-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg413073(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-714">[Get-cspartnerapplication](https://technet.microsoft.com/library/JJ204755(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-714">[Set-CsPartnerApplication](https://technet.microsoft.com/library/JJ204755(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-715">[Set-cspersistentchatactiveserver](https://technet.microsoft.com/library/JJ205065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-715">[Set-CsPersistentChatActiveServer](https://technet.microsoft.com/library/JJ205065(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-716">[Get-cspersistentchataddin](https://technet.microsoft.com/library/JJ204721(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-716">[Set-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ204721(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-717">[Get-cspersistentchatcategory](https://technet.microsoft.com/library/JJ204952(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-717">[Set-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204952(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-718">[Get-cspersistentchatcomplianceconfiguration](https://technet.microsoft.com/library/JJ204949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-718">[Set-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ204949(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-719">[Get-cspersistentchatconfiguration](https://technet.microsoft.com/library/JJ205122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-719">[Set-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ205122(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-720">[Grant-cspersistentchatpolicy](https://technet.microsoft.com/library/JJ205192(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-720">[Set-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ205192(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-721">[Clear-cspersistentchatroom](https://technet.microsoft.com/library/JJ204801(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-721">[Set-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204801(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-722">[Set-cspersistentchatstate](https://technet.microsoft.com/library/JJ205109(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-722">[Set-CsPersistentChatState](https://technet.microsoft.com/library/JJ205109(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-723">[Get-cspinpolicy](https://technet.microsoft.com/library/Gg412997(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-723">[Set-CsPinPolicy](https://technet.microsoft.com/library/Gg412997(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-724">[Get-cspresencepolicy](https://technet.microsoft.com/library/Gg425782(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-724">[Set-CsPresencePolicy](https://technet.microsoft.com/library/Gg425782(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-725">[Remove-cspresenceprovider](https://technet.microsoft.com/library/JJ204833(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-725">[Set-CsPresenceProvider](https://technet.microsoft.com/library/JJ204833(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-726">[Get-csprivacyconfiguration](https://technet.microsoft.com/library/Gg398484(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-726">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398484(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-727">[설정-CsProxyConfiguration](https://technet.microsoft.com/library/Gg425796(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-727">[Set-CsProxyConfiguration](https://technet.microsoft.com/library/Gg425796(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-728">[설정-CsPstnGateway](https://technet.microsoft.com/library/Gg398408(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-728">[Set-CsPstnGateway](https://technet.microsoft.com/library/Gg398408(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-729">[설정-CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-729">[Set-CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-730">[Disable-cspublicprovider](https://technet.microsoft.com/library/Gg413087(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-730">[Set-CsPublicProvider](https://technet.microsoft.com/library/Gg413087(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-731">[Get-cspushnotificationconfiguration](https://technet.microsoft.com/library/Hh690013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-731">[Set-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690013(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-732">[Remove-csqoeconfiguration](https://technet.microsoft.com/library/Gg398245(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-732">[Set-CsQoEConfiguration](https://technet.microsoft.com/library/Gg398245(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-733">[CsRegistrar](https://technet.microsoft.com/library/Gg398993(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-733">[Set-CsRegistrar](https://technet.microsoft.com/library/Gg398993(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-734">[Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg398764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-734">[Set-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398764(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-735">[Get-csreportingconfiguration](https://technet.microsoft.com/library/JJ205075(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-735">[Set-CsReportingConfiguration](https://technet.microsoft.com/library/JJ205075(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-736">[Get-csrgsagentgroup](https://technet.microsoft.com/library/Gg425955(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-736">[Set-CsRgsAgentGroup](https://technet.microsoft.com/library/Gg425955(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-737">[Export-csrgsconfiguration](https://technet.microsoft.com/library/Gg425728(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-737">[Set-CsRgsConfiguration](https://technet.microsoft.com/library/Gg425728(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-738">[New-csrgsholidayset](https://technet.microsoft.com/library/Gg398736(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-738">[Set-CsRgsHolidaySet](https://technet.microsoft.com/library/Gg398736(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-739">[Get-csrgshoursofbusiness](https://technet.microsoft.com/library/Gg412929(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-739">[Set-CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg412929(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-740">[Get-csrgsqueue](https://technet.microsoft.com/library/Gg412947(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-740">[Set-CsRgsQueue](https://technet.microsoft.com/library/Gg412947(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-741">[Get-csrgsworkflow](https://technet.microsoft.com/library/Gg425845(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-741">[Set-CsRgsWorkflow](https://technet.microsoft.com/library/Gg425845(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-742">[설정-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg412811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-742">[Set-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg412811(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-743">[설정-CsServerApplication](https://technet.microsoft.com/library/Gg412850(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-743">[Set-CsServerApplication](https://technet.microsoft.com/library/Gg412850(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-744">[Get-cssimpleurlconfiguration](https://technet.microsoft.com/library/Gg412991(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-744">[Set-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg412991(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-745">[New-cssipdomain](https://technet.microsoft.com/library/Gg412949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-745">[Set-CsSipDomain](https://technet.microsoft.com/library/Gg412949(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-746">[Get-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg425895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-746">[Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg425895(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-747">[설정-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-747">[Set-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-748">[CsSlaConfiguration](https://technet.microsoft.com/library/Mt703202(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-748">[Set-CsSlaConfiguration](https://technet.microsoft.com/library/Mt703202(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-749">[설정-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398724(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-749">[Set-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398724(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-750">[설정-CsTestDevice](https://technet.microsoft.com/library/Gg398156(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-750">[Set-CsTestDevice](https://technet.microsoft.com/library/Gg398156(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-751">[Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg398238(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-751">[Set-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398238(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-752">[New-cstrustedapplication](https://technet.microsoft.com/library/Gg425840(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-752">[Set-CsTrustedApplication](https://technet.microsoft.com/library/Gg425840(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-753">[CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398509(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-753">[Set-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398509(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-754">[New-cstrustedapplicationpool](https://technet.microsoft.com/library/Gg398187(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-754">[Set-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg398187(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-755">[Set-csucphoneconfiguration](https://technet.microsoft.com/library/Gg413042(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-755">[Set-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg413042(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-756">[Get-csuiculture](https://technet.microsoft.com/library/Gg398354(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-756">[Set-CsUICulture](https://technet.microsoft.com/library/Gg398354(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-757">[New-csunassignednumber](https://technet.microsoft.com/library/Gg399033(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-757">[Set-CsUnassignedNumber](https://technet.microsoft.com/library/Gg399033(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-758">[설정-CsUser](https://technet.microsoft.com/library/Gg398510(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-758">[Set-CsUser](https://technet.microsoft.com/library/Gg398510(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-759">[설정-CsUserAcp](https://technet.microsoft.com/library/Gg413018(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-759">[Set-CsUserAcp](https://technet.microsoft.com/library/Gg413018(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-760">[설정-CsUserDatabaseState](https://technet.microsoft.com/library/Gg412973(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-760">[Set-CsUserDatabaseState](https://technet.microsoft.com/library/Gg412973(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-761">[Get-csuserreplicatorconfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-761">[Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-762">[설정-CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-762">[Set-CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-763">[Csuser서비스 구성](https://technet.microsoft.com/library/Gg398340(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-763">[Set-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398340(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-764">[설정-Csuser서비스 정책](https://technet.microsoft.com/library/JJ205414(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-764">[Set-CsUserServicesPolicy](https://technet.microsoft.com/library/JJ205414(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-765">[CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-765">[Set-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398967(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-766">[New-csvoicemailreroutingconfiguration](https://technet.microsoft.com/library/Gg412948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-766">[Set-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg412948(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-767">[Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg398491(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-767">[Set-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398491(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-768">[Set-csvoicepolicy](https://technet.microsoft.com/library/Gg399021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-768">[Set-CsVoicePolicy](https://technet.microsoft.com/library/Gg399021(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-769">[Get-csvoiceroute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-769">[Set-CsVoiceRoute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-770">[Get-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ205313(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-770">[Set-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205313(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-771">[수정한 구성은 test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398614(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-771">[Set-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398614(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-772">[Get-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204620(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-772">[Set-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204620(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-773">[Set-CsWebServer](https://technet.microsoft.com/library/Gg398759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-773">[Set-CsWebServer](https://technet.microsoft.com/library/Gg398759(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-774">[Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg398396(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-774">[Set-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398396(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-775">[설정-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204686(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-775">[Set-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204686(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-776">[설정-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-776">[Set-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204769(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-777">[시작-CsWindowsService](https://technet.microsoft.com/library/Gg398561(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-777">[Start-CsWindowsService](https://technet.microsoft.com/library/Gg398561(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-778">[CsWindowsService](https://technet.microsoft.com/library/Gg398426(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-778">[Stop-CsWindowsService](https://technet.microsoft.com/library/Gg398426(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-779">[동기화-CsUserData](https://technet.microsoft.com/library/JJ205242(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-779">[Sync-CsUserData](https://technet.microsoft.com/library/JJ205242(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-780">[테스트-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-780">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-781">[테스트-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-781">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-782">[테스트-CsASConference](https://technet.microsoft.com/library/JJ205227(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-782">[Test-CsASConference](https://technet.microsoft.com/library/JJ205227(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-783">[Test-csaudioconferencingprovider](https://technet.microsoft.com/library/JJ205117(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-783">[Test-CsAudioConferencingProvider](https://technet.microsoft.com/library/JJ205117(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-784">[CsAVConference 테스트](https://technet.microsoft.com/library/Gg412749(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-784">[Test-CsAVConference](https://technet.microsoft.com/library/Gg412749(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-785">[Test-csavedgeconnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-785">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-786">[Test-cscertificateconfiguration](https://technet.microsoft.com/library/Gg398647(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-786">[Test-CsCertificateConfiguration](https://technet.microsoft.com/library/Gg398647(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-787">[테스트-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-787">[Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-788">[테스트-CsDatabase](https://technet.microsoft.com/library/JJ204839(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-788">[Test-CsDatabase](https://technet.microsoft.com/library/JJ204839(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-789">[Test-csdataconference](https://technet.microsoft.com/library/JJ205219(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-789">[Test-CsDataConference](https://technet.microsoft.com/library/JJ205219(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-790">[Test-csdialinconferencing](https://technet.microsoft.com/library/Gg399013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-790">[Test-CsDialInConferencing](https://technet.microsoft.com/library/Gg399013(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-791">[테스트-CsDialPlan 플랜](https://technet.microsoft.com/library/Gg399024(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-791">[Test-CsDialPlan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-792">[Test-csexstorageconnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-792">[Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-793">[Test-csexstoragenotification](https://technet.microsoft.com/library/JJ205331(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-793">[Test-CsExStorageNotification](https://technet.microsoft.com/library/JJ205331(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-794">[Test-csexumconnectivity](https://technet.microsoft.com/library/JJ204784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-794">[Test-CsExUMConnectivity](https://technet.microsoft.com/library/JJ204784(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-795">[테스트-CsExUMVoiceMail 메일](https://technet.microsoft.com/library/JJ205058(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-795">[Test-CsExUMVoiceMail](https://technet.microsoft.com/library/JJ205058(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-796">[Test-csfederatedpartner](https://technet.microsoft.com/library/Gg398281(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-796">[Test-CsFederatedPartner](https://technet.microsoft.com/library/Gg398281(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-797">[테스트-CsGroupExpansion](https://technet.microsoft.com/library/Gg399009(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-797">[Test-CsGroupExpansion](https://technet.microsoft.com/library/Gg399009(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-798">[테스트-CsGroupIM](https://technet.microsoft.com/library/Gg398273(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-798">[Test-CsGroupIM](https://technet.microsoft.com/library/Gg398273(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-799">[Test-CsIM](https://technet.microsoft.com/library/Gg425802(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-799">[Test-CsIM](https://technet.microsoft.com/library/Gg425802(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-800">[Test-csintertrunkrouting](https://technet.microsoft.com/library/JJ204741(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-800">[Test-CsInterTrunkRouting](https://technet.microsoft.com/library/JJ204741(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-801">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-801">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-802">[Test-csliscivicaddress](https://technet.microsoft.com/library/Gg425914(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-802">[Test-CsLisCivicAddress](https://technet.microsoft.com/library/Gg425914(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-803">[Export-cslisconfiguration](https://technet.microsoft.com/library/Gg398497(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-803">[Test-CsLisConfiguration](https://technet.microsoft.com/library/Gg398497(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-804">[테스트-CsLocationPolicy](https://technet.microsoft.com/library/Gg425962(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-804">[Test-CsLocationPolicy](https://technet.microsoft.com/library/Gg425962(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-805">[Test-CsMcxConference](https://technet.microsoft.com/library/Hh690045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-805">[Test-CsMcxConference](https://technet.microsoft.com/library/Hh690045(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-806">[Test-csmcxp2pim](https://technet.microsoft.com/library/Hh690020(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-806">[Test-CsMcxP2PIM](https://technet.microsoft.com/library/Hh690020(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-807">[Test-CsMcxPushNotification](https://technet.microsoft.com/library/Hh690043(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-807">[Test-CsMcxPushNotification](https://technet.microsoft.com/library/Hh690043(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-808">[테스트-CsOUPermission](https://technet.microsoft.com/library/Gg398787(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-808">[Test-CsOUPermission](https://technet.microsoft.com/library/Gg398787(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-809">[Test-csp2pav](https://technet.microsoft.com/library/Gg412821(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-809">[Test-CsP2PAV](https://technet.microsoft.com/library/Gg412821(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-810">[Test-cspersistentchatmessage](https://technet.microsoft.com/library/JJ204656(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-810">[Test-CsPersistentChatMessage](https://technet.microsoft.com/library/JJ204656(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-811">[Test-csphonebootstrap](https://technet.microsoft.com/library/Gg412852(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-811">[Test-CsPhoneBootstrap](https://technet.microsoft.com/library/Gg412852(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-812">[테스트-cspres](https://technet.microsoft.com/library/Gg398148(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-812">[Test-CsPresence](https://technet.microsoft.com/library/Gg398148(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-813">[Test-cspstnoutboundcall](https://technet.microsoft.com/library/Gg398207(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-813">[Test-CsPstnOutboundCall](https://technet.microsoft.com/library/Gg398207(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-814">[테스트-CsPstnPeerToPeerCall](https://technet.microsoft.com/library/Gg398662(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-814">[Test-CsPstnPeerToPeerCall](https://technet.microsoft.com/library/Gg398662(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-815">[테스트-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-815">[Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-816">[테스트-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-816">[Test-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-817">[테스트-CsSetupPermission](https://technet.microsoft.com/library/Gg398428(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-817">[Test-CsSetupPermission](https://technet.microsoft.com/library/Gg398428(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-818">[Enable-cstopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-818">[Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-819">[Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg398137(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-819">[Test-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398137(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-820">[Test-csunifiedcontactstore](https://technet.microsoft.com/library/JJ204662(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-820">[Test-CsUnifiedContactStore](https://technet.microsoft.com/library/JJ204662(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-821">[Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-821">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-822">[Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-822">[Test-CsVoicePolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-823">[Get-csvoiceroute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-823">[Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-824">[수정한 구성은 test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398260(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-824">[Test-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398260(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-825">[CsVoiceUser](https://technet.microsoft.com/library/Gg413013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-825">[Test-CsVoiceUser](https://technet.microsoft.com/library/Gg413013(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-826">[Get-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204652(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-826">[Test-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204652(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-827">[Test-cswebapp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-827">[Test-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-828">[Test-cswebappanonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-828">[Test-CsWebAppAnonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-829">[테스트-CsWebScheduler](https://technet.microsoft.com/library/JJ204829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-829">[Test-CsWebScheduler](https://technet.microsoft.com/library/JJ204829(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-830">[테스트-CsXmppIM](https://technet.microsoft.com/library/JJ205423(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-830">[Test-CsXmppIM](https://technet.microsoft.com/library/JJ205423(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-831">[제거-CsDatabase](unhttps://technet.microsoft.com/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-831">[Uninstall-CsDatabase](unhttps://technet.microsoft.com/library/Gg399044(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-832">[제거-CsMirrorDatabase](unhttps://technet.microsoft.com/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-832">[Uninstall-CsMirrorDatabase](unhttps://technet.microsoft.com/library/JJ204986(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-833">[잠금 해제-CsClientPin](unhttps://technet.microsoft.com/library/Gg398650(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-833">[Unlock-CsClientPin](unhttps://technet.microsoft.com/library/Gg398650(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-834">[게시 취소-Export-cslisconfiguration](unhttps://technet.microsoft.com/library/Gg398364(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-834">[Unpublish-CsLisConfiguration](unhttps://technet.microsoft.com/library/Gg398364(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-835">[업데이트-Update-csaddressbook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-835">[Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-836">[업데이트-CsAdminRole](https://technet.microsoft.com/library/JJ204851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-836">[Update-CsAdminRole](https://technet.microsoft.com/library/JJ204851(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-837">[업데이트-CsTenantMeetingUrl](https://technet.microsoft.com/library/Dn424754(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-837">[Update-CsTenantMeetingUrl](https://technet.microsoft.com/library/Dn424754(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-838">[업데이트-CsUserData](https://technet.microsoft.com/library/JJ205358(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-838">[Update-CsUserData](https://technet.microsoft.com/library/JJ205358(v=OCS.15))</span></span>

  - <span data-ttu-id="25deb-839">[업데이트-CsUserDatabase](https://technet.microsoft.com/library/Gg398682(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25deb-839">[Update-CsUserDatabase](https://technet.microsoft.com/library/Gg398682(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2010 회의 디렉터리를 Lync Server 2013으로 이동
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move Conference Directories
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62387565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa32bb5be86d72d4f18d11bb85d5ce0b57a96725
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a><span data-ttu-id="8249e-102">회의 디렉터리 이동</span><span class="sxs-lookup"><span data-stu-id="8249e-102">Move Conference Directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8249e-103">_**마지막으로 수정한 주제:** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="8249e-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="8249e-104">풀을 서비스 해제 하기 전에 Lync Server 2010 풀의 각 회의 디렉터리에 대해 다음 절차를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8249e-104">Before decommissioning a pool you must perform the following procedure for each conference directory in your Lync Server 2010 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="8249e-105">회의 디렉터리를 Lync Server 2013로 이동 하려면 다음을 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8249e-105">To Move a Conference Directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="8249e-106">Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8249e-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="8249e-107">조직에서 회의 디렉터리의 id를 가져오려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8249e-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="8249e-108">앞의 명령은 조직의 모든 회의 디렉터리를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8249e-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="8249e-109">따라서 역할을 해제 하려는 풀로 결과를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8249e-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="8249e-110">예를 들어 FQDN (정규화 된 도메인 이름) pool01.contoso.net을 사용 하 여 풀을 해제 하는 경우이 명령을 사용 하 여 반환 된 데이터를 해당 풀의 컨퍼런스 디렉터리로 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="8249e-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="8249e-111">이 명령은 ServiceID 속성에 FQDN pool01.contoso.net이 포함 된 컨퍼런스 디렉터리만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8249e-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="8249e-112">회의 디렉터리를 이동 하려면 풀의 각 회의 디렉터리에 대해 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8249e-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="8249e-113">예를 들어 회의 디렉터리 3을 이동 하려면 다음 명령을 사용 하 여 Lync Server 2013 풀을 TargetPool로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8249e-113">For example, to move conference directory 3 use this command, specifying a Lync Server 2013 pool as the TargetPool:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    <span data-ttu-id="8249e-114">풀의 모든 회의 디렉터리를 이동 하려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8249e-114">If you want to move all the conference directories on a pool then use a command similar to the following:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

<span data-ttu-id="8249e-115">Lync 2010 풀을 폐기 하는 방법에 대 한 자세한 단계별 지침은 "Microsoft Lync Server 2010 제거 및 [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)서버 역할 제거" (다운로드할 수 있는) 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8249e-115">Please see the document "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles" (which can be downloaded from [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)) for comprehensive, step-by-step instructions on decommissioning Lync 2010 pools.</span></span>

<span data-ttu-id="8249e-116">회의 디렉터리를 이동할 때 다음과 같은 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8249e-116">When moving conference directories you might encounter the following error:</span></span>

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

<span data-ttu-id="8249e-117">이 오류는 작업을 완료 하기 위해 Lync Server 관리 셸에서 업데이트 된 Active Directory 권한 집합이 필요한 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="8249e-117">This error typically occurs when the Lync Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="8249e-118">이 문제를 해결 하려면 관리 셸의 현재 인스턴스를 닫은 다음 셸의 새 인스턴스를 열고, 회의 디렉터리를 이동 하기 위해 명령을 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8249e-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command in order to move the conference directory.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


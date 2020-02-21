---
title: Lync server 2010 회의 디렉터리를 Lync Server 2013로 이동
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move Conference Directories
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62387565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 049472022a26d7a3a6e8e78e20a20ccaa46ff5fb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a><span data-ttu-id="478b0-102">회의 디렉터리 이동</span><span class="sxs-lookup"><span data-stu-id="478b0-102">Move Conference Directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="478b0-103">_**마지막으로 수정 된 항목:** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="478b0-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="478b0-104">풀을 해제 하기 전에 Lync Server 2010 풀의 각 전화 회의 디렉터리에 대해 다음 절차를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="478b0-104">Before decommissioning a pool you must perform the following procedure for each conference directory in your Lync Server 2010 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="478b0-105">전화 회의 디렉터리를 Lync Server 2013로 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="478b0-105">To Move a Conference Directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="478b0-106">Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="478b0-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="478b0-107">조직에서 회의 디렉터리의 id를 가져오려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="478b0-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="478b0-108">위의 명령은 조직의 모든 전화 회의 디렉터리를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="478b0-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="478b0-109">따라서 역할을 해제 하는 풀로 결과를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="478b0-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="478b0-110">예를 들어 FQDN (정규화 된 도메인 이름) pool01.contoso.net을 사용 하 여 풀을 제거 하는 경우이 명령을 사용 하 여 반환 되는 데이터를 해당 풀의 전화 회의 디렉터리로 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="478b0-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="478b0-111">이 명령은 ServiceID 속성에 FQDN pool01.contoso.net가 포함 된 전화 회의 디렉터리만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="478b0-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="478b0-112">전화 회의 디렉터리를 이동 하려면 풀의 각 전화 회의 디렉터리에 대해 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="478b0-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="478b0-113">예를 들어 전화 회의 디렉터리 3을 이동 하려면 다음 명령을 사용 하 여 Lync Server 2013 풀을 TargetPool로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="478b0-113">For example, to move conference directory 3 use this command, specifying a Lync Server 2013 pool as the TargetPool:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    <span data-ttu-id="478b0-114">풀의 모든 전화 회의 디렉터리를 이동 하려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="478b0-114">If you want to move all the conference directories on a pool then use a command similar to the following:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

<span data-ttu-id="478b0-115">Lync 2010 풀을 해제 하는 방법에 대 한 단계별 지침은 "Microsoft Lync Server 2010 제거 및 서버 [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227)역할 제거" (다운로드 가능) 문서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="478b0-115">Please see the document "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles" (which can be downloaded from [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227)) for comprehensive, step-by-step instructions on decommissioning Lync 2010 pools.</span></span>

<span data-ttu-id="478b0-116">전화 회의 디렉터리를 이동할 때 다음과 같은 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="478b0-116">When moving conference directories you might encounter the following error:</span></span>

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

<span data-ttu-id="478b0-117">이 오류는 일반적으로 Lync Server 관리 셸에서 작업을 완료 하기 위해 업데이트 된 Active Directory 사용 권한 집합이 필요한 경우 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="478b0-117">This error typically occurs when the Lync Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="478b0-118">이 문제를 해결 하려면 관리 셸의 현재 인스턴스를 닫은 다음 셸의 새 인스턴스를 열고이 명령을 다시 실행 하 여 전화 회의 디렉터리를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="478b0-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command in order to move the conference directory.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


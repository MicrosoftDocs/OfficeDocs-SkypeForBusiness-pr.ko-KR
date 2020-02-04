---
title: 회의 디렉터리 이동
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ae7633d638571410c93cfefe87d9e333731a4bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a><span data-ttu-id="2c4c4-102">회의 디렉터리 이동</span><span class="sxs-lookup"><span data-stu-id="2c4c4-102">Move conference directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c4c4-103">_**마지막으로 수정한 주제:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="2c4c4-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="2c4c4-104">풀을 서비스 해제 하기 전에 Office Communications Server 2007 R2 풀의 각 전화 회의 디렉터리에 대해 다음 절차를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c4c4-104">Before decommissioning a pool, you need to perform the following procedure for each conference directory in your Office Communications Server 2007 R2 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="2c4c4-105">회의 디렉터리를 Lync Server 2013로 이동 하려면 다음을 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c4c4-105">To move a conference directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="2c4c4-106">Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2c4c4-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="2c4c4-107">조직에서 회의 디렉터리의 id를 가져오려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c4c4-107">To obtain the identity of the conference directories in your organization, run the following commands:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="2c4c4-108">이 cmdlet은 조직의 모든 컨퍼런스 디렉터리를 반환 하기 때문에 역할을 해제 하려는 풀로만 결과를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c4c4-108">Because this cmdlet returns all the conference directories in your organization, you may want to limit the results to only the pool you want to decommission.</span></span> <span data-ttu-id="2c4c4-109">예를 들어 FQDN (정규화 된 도메인 이름) pool01.contoso.net를 사용 하 여 풀을 서비스 해제 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c4c4-109">For example, if you want to decommission a pool with the fully qualified domain name (FQDN) pool01.contoso.net:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="2c4c4-110">이 cmdlet은 서비스 ID가 FQDN pool01.contoso.net를 포함 하는 모든 회의 디렉터리를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c4c4-110">This cmdlet returns all the conference directories where service ID contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="2c4c4-111">회의 디렉터리를 이동 하려면 풀의 각 회의 디렉터리에 대해 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c4c4-111">To move conference directories, run the following for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="2c4c4-112">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2c4c4-112">For example:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> <span data-ttu-id="2c4c4-113">Active Directory에서 업데이트 된 사용 권한 집합을 요구 하는 Lync Server Management Shell 때문에 다음과 같은 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c4c4-113">You may experience an error, shown below, that is caused by the Lync Server Management Shell requiring an updated set of permissions from Active Directory.</span></span> <span data-ttu-id="2c4c4-114">오류를 해결 하려면 현재 창을 닫고 새 Lync Server 관리 셸을 연 다음 명령을 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c4c4-114">To resolve the error, closed the current window and open a new Lync Server Management Shell and run the command again.</span></span>



</div>

<span data-ttu-id="2c4c4-115">![Move-CsConferenceDirectory 오류 출력](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory 오류 출력")</span><span class="sxs-lookup"><span data-stu-id="2c4c4-115">![Move-CsConferenceDirectory error output](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory error output")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


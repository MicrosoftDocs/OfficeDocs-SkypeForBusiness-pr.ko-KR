---
title: 'Lync Server 2013: 주소록 관리를 위한 Get-help CsWebServiceConfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsWebServiceConfiguration for Address Book management
ms:assetid: 0b223733-5224-47d1-9b47-2109e6f135c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429692(v=OCS.15)
ms:contentKeyID: 48183372
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c04cc523e27d655aa69b05f522efccf8153a37ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="get-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="685ea-102">Lync Server 2013의 주소록 관리를 위한 get-help CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="685ea-102">Get-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="685ea-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="685ea-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="685ea-104">이 cmdlet을 실행할 수 있는 사람: 기본적으로 다음 그룹의 구성원은 Get-CsWebServiceConfiguration cmdlet을 로컬로 실행할 권한이 있습니다. RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="685ea-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsWebServiceConfiguration cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span> <span data-ttu-id="685ea-105">이 cmdlet이 할당 된 모든 RBAC (역할 기반 액세스 제어) 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="685ea-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsWebServiceConfiguration"}

<span data-ttu-id="685ea-106">Get-CsWebServiceConfiguration는 조직에서 현재 사용 중인 웹 서비스 구성의 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="685ea-106">Get-CsWebServiceConfiguration returns information of the Web Services configuration currently in use in your organization.</span></span> <span data-ttu-id="685ea-107">주소록 서비스의 주요 기능은 메일 그룹 확장 기능의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="685ea-107">Of interest to the Address Book Services is the status of Distribution List Expansion function.</span></span> <span data-ttu-id="685ea-108">EnableGroupExpansion 특성이 True 인 경우 조직에서 현재 그룹 확장을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="685ea-108">If the attribute EnableGroupExpansion is True, your organization currently allows group expansion.</span></span>

<span data-ttu-id="685ea-109">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="685ea-109">For example:</span></span>

    Get-CsWebServiceConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a><span data-ttu-id="685ea-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="685ea-110">See Also</span></span>


[<span data-ttu-id="685ea-111">Get-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="685ea-111">Get-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


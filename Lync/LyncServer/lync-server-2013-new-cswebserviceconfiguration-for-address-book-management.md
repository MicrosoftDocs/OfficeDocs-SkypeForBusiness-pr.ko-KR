---
title: 'Lync Server 2013: 주소록 관리를 위한 새로운 CsWebServiceConfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New-CsWebServiceConfiguration for Address Book management
ms:assetid: 49e4ecc5-aa3e-4dd4-a32c-b0dea3758fab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429703(v=OCS.15)
ms:contentKeyID: 48184067
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03a973ca1086a9d2ca1ce2d8f19bbb64ba8aae19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="f531a-102">CsWebServiceConfiguration-Lync Server 2013의 주소록 관리를 위한 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="f531a-102">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f531a-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f531a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f531a-104">이 cmdlet을 실행할 수 있는 사람: 기본적으로 다음 그룹의 구성원에 게 CsWebServiceConfiguration cmdlet을 로컬로 실행할 권한이 있습니다. RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f531a-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="f531a-105">이 cmdlet이 할당 된 모든 RBAC (역할 기반 액세스 제어) 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f531a-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

<span data-ttu-id="f531a-106">Cmdlet CsWebServiceConfiguration는 조직의 웹 서비스에 대 한 새 구성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f531a-106">The cmdlet New-CsWebServiceConfiguration defines a new configuration for Web Services in your organization.</span></span> <span data-ttu-id="f531a-107">웹 서비스 구성의 범위는 사이트 또는 서비스 수준 에서만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="f531a-107">The scope for the Web Services configuration can only be at the site or service level.</span></span> <span data-ttu-id="f531a-108">전역 수준에서 새 웹 서비스 구성을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f531a-108">It cannot create a new Web Services configuration at the global level.</span></span> <span data-ttu-id="f531a-109">특히 주소록에 관심이 있는 것은 EnableGroupExansion 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f531a-109">Specifically of interest to the Address Book is the EnableGroupExansion attribute.</span></span> <span data-ttu-id="f531a-110">True로 설정 되 면 웹 서비스는 그룹 확장에 대 한 요청에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f531a-110">If set to True, the Web Services can respond to requests for group expansion.</span></span>

<span data-ttu-id="f531a-111">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f531a-111">For example:</span></span>

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

<div>

## <a name="see-also"></a><span data-ttu-id="f531a-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f531a-112">See Also</span></span>


[<span data-ttu-id="f531a-113">New-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="f531a-113">New-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


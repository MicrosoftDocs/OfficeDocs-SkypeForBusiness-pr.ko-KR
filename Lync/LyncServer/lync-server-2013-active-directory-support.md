---
title: Lync Server 2013 Active Directory 지원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory support
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48183679
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd35b9444f0ede4abc9b66ab6b5513d049df57ee
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a><span data-ttu-id="ab080-102">Lync Server 2013의 Active Directory 지원</span><span class="sxs-lookup"><span data-stu-id="ab080-102">Active Directory support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab080-103">_**마지막으로 수정한 주제:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="ab080-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="ab080-104">Lync Server 2013에서 지원 되는 Active Directory 도메인 서비스 온-프레미스 토폴로지는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab080-104">The Active Directory Domain Services on-premises topologies that are supported by Lync Server 2013 are as follows:</span></span>

  - <span data-ttu-id="ab080-105">단일 도메인이 있는 단일 포리스트</span><span class="sxs-lookup"><span data-stu-id="ab080-105">Single forest with single domain</span></span>

  - <span data-ttu-id="ab080-106">단일 트리 및 여러 도메인이 있는 단일 포리스트</span><span class="sxs-lookup"><span data-stu-id="ab080-106">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="ab080-107">여러 트리 및 분리 네임 스페이스가 있는 단일 포리스트</span><span class="sxs-lookup"><span data-stu-id="ab080-107">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="ab080-108">중앙 포리스트 토폴로지의 여러 포리스트</span><span class="sxs-lookup"><span data-stu-id="ab080-108">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="ab080-109">리소스 포리스트 토폴로지의 여러 포리스트</span><span class="sxs-lookup"><span data-stu-id="ab080-109">Multiple forests in a resource forest topology</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ab080-110">Lync Server 2013는 단일 레이블 도메인을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab080-110">Lync Server 2013 does not support single-label domains.</span></span> <span data-ttu-id="ab080-111">예를 들어, <STRONG>contoso. local</STRONG> 이라는 루트 도메인이 있는 포리스트는 지원 되지만 <STRONG>local</STRONG> 이라는 단일 레이블 루트 도메인은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab080-111">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a single-label root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="ab080-112">자세한 내용은 Microsoft 기술 자료 문서 300684, "단일 레이블 DNS 이름을 사용 하 여 Windows 구성에 대 한 정보"를 참조 <A href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</A>하세요.</span><span class="sxs-lookup"><span data-stu-id="ab080-112">For details, see Microsoft Knowledge Base article 300684, "Information about configuring Windows for domains with single-label DNS names," at <A href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ab080-113">Lync Server 2013는 도메인 이름 바꾸기를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab080-113">Lync Server 2013 does not support renaming domains.</span></span> <span data-ttu-id="ab080-114">Lync Server를 배포 하는 도메인의 이름을 변경 해야 하는 경우 먼저 Lync Server를 제거 하 고 도메인 이름을 바꾼 다음 Lync Server를 다시 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab080-114">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

<span data-ttu-id="ab080-115">온-프레미스 배포에 대해 지원 되는 토폴로지와 요구 사항에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 Active Directory 도메인 서비스 요구 사항, 지원 및 토폴로지](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ab080-115">For details about supported topologies and requirements for on-premises deployments, see [Active Directory Domain Services requirements, support, and topologies in Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


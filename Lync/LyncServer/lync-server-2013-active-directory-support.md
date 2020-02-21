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
ms.openlocfilehash: 8a7da4487c376ceea4c5c3e41e20a55874b27f06
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a><span data-ttu-id="cbf53-102">Lync Server 2013의 Active Directory 지원</span><span class="sxs-lookup"><span data-stu-id="cbf53-102">Active Directory support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbf53-103">_**마지막으로 수정 된 항목:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="cbf53-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="cbf53-104">Lync Server 2013에서 지원 되는 Active Directory 도메인 서비스 온-프레미스 토폴로지는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf53-104">The Active Directory Domain Services on-premises topologies that are supported by Lync Server 2013 are as follows:</span></span>

  - <span data-ttu-id="cbf53-105">도메인이 하나인 단일 포리스트</span><span class="sxs-lookup"><span data-stu-id="cbf53-105">Single forest with single domain</span></span>

  - <span data-ttu-id="cbf53-106">트리가 하나이고 도메인이 여러 개인 단일 포리스트</span><span class="sxs-lookup"><span data-stu-id="cbf53-106">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="cbf53-107">트리 여러 개와 연결되지 않은 네임스페이스가 포함된 단일 포리스트</span><span class="sxs-lookup"><span data-stu-id="cbf53-107">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="cbf53-108">중앙 포리스트 토폴로지의 다중 포리스트</span><span class="sxs-lookup"><span data-stu-id="cbf53-108">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="cbf53-109">리소스 포리스트 토폴로지의 다중 포리스트</span><span class="sxs-lookup"><span data-stu-id="cbf53-109">Multiple forests in a resource forest topology</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cbf53-110">Lync Server 2013에서는 단일 레이블 도메인을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf53-110">Lync Server 2013 does not support single-label domains.</span></span> <span data-ttu-id="cbf53-111">예를 들어 <STRONG>contoso. local</STRONG> 이라는 루트 도메인을 사용 하는 포리스트는 지원 되지만 <STRONG>로컬</STRONG> 이라는 단일 레이블 루트 도메인은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf53-111">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a single-label root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="cbf53-112">자세한 내용은 Microsoft 기술 자료 문서 300684, "단일 레이블 DNS 이름이 있는 도메인에 대 한 Windows 구성 정보"를 참조 하세요 <A href="https://go.microsoft.com/fwlink/p/?linkid=143752">https://go.microsoft.com/fwlink/p/?linkId=143752</A>.</span><span class="sxs-lookup"><span data-stu-id="cbf53-112">For details, see Microsoft Knowledge Base article 300684, "Information about configuring Windows for domains with single-label DNS names," at <A href="https://go.microsoft.com/fwlink/p/?linkid=143752">https://go.microsoft.com/fwlink/p/?linkId=143752</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="cbf53-113">Lync Server 2013에서는 도메인 이름을 바꿀 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf53-113">Lync Server 2013 does not support renaming domains.</span></span> <span data-ttu-id="cbf53-114">Lync Server가 배포 되는 도메인의 이름을 바꾸려는 경우에는 먼저 Lync Server를 제거한 다음 도메인 이름을 바꾼 다음 Lync Server를 다시 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbf53-114">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

<span data-ttu-id="cbf53-115">온-프레미스 배포를 위한 지원 되는 토폴로지 및 요구 사항에 대 한 자세한 내용은 계획 설명서에서 [Active Directory 도메인 서비스 요구 사항, 지원 및 토폴로지를 Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cbf53-115">For details about supported topologies and requirements for on-premises deployments, see [Active Directory Domain Services requirements, support, and topologies in Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


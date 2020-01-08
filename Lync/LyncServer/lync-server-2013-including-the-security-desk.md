---
title: 'Lync 서버 2013: 보안 데스크 포함'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Including the security desk
ms:assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398299(v=OCS.15)
ms:contentKeyID: 48184084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41c60b7f67f22393bf4a6972e68b2d0bdc2ca8a9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="including-the-security-desk-in-lync-server-2013"></a><span data-ttu-id="858c4-102">Lync Server 2013에서 보안 데스크 포함</span><span class="sxs-lookup"><span data-stu-id="858c4-102">Including the security desk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="858c4-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="858c4-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="858c4-104">회사에서 긴급 통화에 참여 하려면 보안 지원팀이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="858c4-104">Your company may require the security desk to become involved in an emergency call.</span></span> <span data-ttu-id="858c4-105">E9에서 보안 데스크를 통합 하는 방법을 결정 하려면-1-1 배포를 선택 하는 방법에 대 한 자세한 내용은 다음 질문에 대답 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="858c4-105">To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>

  - <span data-ttu-id="858c4-106">**긴급 통화 시 보안 지원팀에 알림을 받도록 하 고 싶으신가요?**</span><span class="sxs-lookup"><span data-stu-id="858c4-106">**Do you want the security desk to be notified when there is an emergency call?**</span></span>  
    <span data-ttu-id="858c4-107">Lync Server가 한 명 이상의 보안 사용자의 Lync SIP 주소로 메신저 대화 알림을 보내도록 위치 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="858c4-107">You can configure the location policy so that Lync Server sends instant messaging (IM) alerts to the Lync SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="858c4-108">이러한 경고에는 비상 전화를 걸고 있는 사람의 이름, 번호, 위치가 포함 되며, 긴급 상황에 대 한 지원으로 보안 인력이 이용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="858c4-108">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>

<!-- end list -->

  - <span data-ttu-id="858c4-109">**각 비상 전화를 통해 보안 지원팀에 회의를 하 고 싶으신가요?**</span><span class="sxs-lookup"><span data-stu-id="858c4-109">**Do you want to conference the security desk in on each emergency call?**</span></span>  
    <span data-ttu-id="858c4-110">비상 서비스 서비스 제공 업체에서 지원 되는 경우, 각 비상 전화에 콜백 번호를 포함 하도록 위치 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="858c4-110">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call.</span></span> <span data-ttu-id="858c4-111">공급자는이 번호를 사용 하 여 조직의 보안 담당자에 게 긴급 통화로 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="858c4-111">This number is then used by the provider to conference your organization's security personnel into emergency calls.</span></span> <span data-ttu-id="858c4-112">이 회의는 위치 정책에서 단방향 (수신 전용) 또는 양방향 (양방향)으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="858c4-112">This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="858c4-113">원하는 경우 각 위치 정책에 대해 서로 다른 응급 인력을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="858c4-113">If desired, you can configure different emergency personnel for each location policy.</span></span> <span data-ttu-id="858c4-114">이렇게 하면 회사 내의 다른 영역에 대 한 응답을 사용자 지정 하거나 네트워크 외부가 아닌 내부에서 시작 된 비상 전화에 대해 다른 동작을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="858c4-114">This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network.</span></span> <span data-ttu-id="858c4-115">메일 그룹을 사용 하 여 알림을 받을 사람을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="858c4-115">You can use distribution groups to specify the personnel you want to notify.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: 보안 책상 포함'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Including the security desk
ms:assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398299(v=OCS.15)
ms:contentKeyID: 48184084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c4f42225d4694c707e4967c198b09014ab6fa17
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="including-the-security-desk-in-lync-server-2013"></a><span data-ttu-id="5d981-102">Lync Server 2013의 보안 센터 포함</span><span class="sxs-lookup"><span data-stu-id="5d981-102">Including the security desk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d981-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5d981-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5d981-p101">회사에서 긴급 통화를 처리하기 위한 보안 데스크가 필요한 경우가 있습니다. E9-1-1 배포에 보안 데스크를 통합하는 방법을 결정하려면 다음과 같은 사항을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d981-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>

  - <span data-ttu-id="5d981-106">**긴급 통화가 있는 경우 보안 데스크에 알림을 보낼지 여부**</span><span class="sxs-lookup"><span data-stu-id="5d981-106">**Do you want the security desk to be notified when there is an emergency call?**</span></span>  
    <span data-ttu-id="5d981-107">Lync Server에서 IM (인스턴트 메시징) 알림을 하나 이상의 보안 담당자의 Lync SIP 주소로 보내도록 위치 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d981-107">You can configure the location policy so that Lync Server sends instant messaging (IM) alerts to the Lync SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="5d981-108">이러한 경고는 긴급 통화를 거는 사용자의 이름, 번호 및 위치를 포함하며 보안 담당자가 긴급 상황을 지원하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d981-108">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>

<!-- end list -->

  - <span data-ttu-id="5d981-109">**각 긴급 통화에 대해 보안 데스크와 전화 회의를 할지 여부**</span><span class="sxs-lookup"><span data-stu-id="5d981-109">**Do you want to conference the security desk in on each emergency call?**</span></span>  
    <span data-ttu-id="5d981-p103">긴급 서비스 공급자에서 지원되는 경우 각 긴급 통화에 콜백 번호를 포함하도록 위치 정책을 구성할 수 있습니다. 이 번호는 공급자가 조직의 보안 담당자를 긴급 통화에 참조로 포함하는 데 사용됩니다. 이러한 참조는 위치 정책에서 단방향(듣기만) 또는 양방향으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d981-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5d981-p104">필요에 따라 각 위치 정책에 대해 서로 다른 긴급 담당자를 구성할 수 있습니다. 이렇게 하면 회사 내 여러 영역에 대한 응답성을 사용자 지정하거나, 내부의 긴급 통화와 네트워크 외부의 긴급 통화에 대해 서로 다른 동작을 만들 수 있습니다. 메일 그룹을 사용해서 알림을 제공할 담당자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d981-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


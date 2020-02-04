---
title: 'Lync Server 2013: 원격 통화 제어 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying remote call control
ms:assetid: 763037f7-7a2a-49ae-acc3-9781b0bff7e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558664(v=OCS.15)
ms:contentKeyID: 48184536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6651c9cb15322498d68fa9b6cd705b68dc601c6d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="d9775-102">Lync Server 2013에서 원격 통화 제어 배포</span><span class="sxs-lookup"><span data-stu-id="d9775-102">Deploying remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9775-103">_**마지막으로 수정한 주제:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="d9775-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="d9775-104">이 섹션에서는 조직의 사용자에 게 원격 통화 제어 기능을 배포 하는 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9775-104">This section guides you through the process of deploying remote call control functionality to users in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d9775-105">원격 통화 제어 기능은 조직의 방화벽 외부에 있는 동안에도 사용할 수 있지만, 외부 액세스 시나리오를 배포 하는 방법에 대 한 자세한 내용은이 설명서의 범위를 벗어납니다.</span><span class="sxs-lookup"><span data-stu-id="d9775-105">Although remote call control features are available to remote users while they are outside of your organization’s firewall, details about deploying external access scenarios are beyond the scope of this documentation.</span></span> <span data-ttu-id="d9775-106">외부 사용자 액세스를 배포 하는 방법에 대 한 자세한 내용은 배포 설명서의 <A href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013에서 외부 사용자 액세스 배포</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9775-106">For details about deploying external user access, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d9775-107">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="d9775-107">In This Section</span></span>

  - [<span data-ttu-id="d9775-108">SIP/CSTA 게이트웨이로 라우팅하도록 Lync Server 2013 구성</span><span class="sxs-lookup"><span data-stu-id="d9775-108">Configuring Lync Server 2013 to route to a SIP/CSTA gateway</span></span>](lync-server-2013-configuring-lync-server-to-route-to-a-sip-csta-gateway.md)

  - [<span data-ttu-id="d9775-109">Lync Server 2013에서 원격 통화 제어에 대한 고정 경로 구성</span><span class="sxs-lookup"><span data-stu-id="d9775-109">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)

  - [<span data-ttu-id="d9775-110">Lync Server 2013에서 원격 통화 제어를 위한 신뢰할 수 있는 응용 프로그램 항목 구성</span><span class="sxs-lookup"><span data-stu-id="d9775-110">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

  - <span data-ttu-id="d9775-111">[Lync Server 2013에서 SIP/CSTA 게이트웨이 IP 주소 정의](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (게이트웨이가 TCP를 사용 하도록 구성 된 경우에만)</span><span class="sxs-lookup"><span data-stu-id="d9775-111">[Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (only if the gateway is configured to use TCP)</span></span>

  - [<span data-ttu-id="d9775-112">Lync Server 2013에서 Lync 사용자가 원격 통화 제어를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="d9775-112">Enable Lync users for remote call control in Lync Server 2013</span></span>](lync-server-2013-enable-lync-users-for-remote-call-control.md)

  - [<span data-ttu-id="d9775-113">Lync Server 2013의 원격 통화 제어 및 전화 번호 정규화</span><span class="sxs-lookup"><span data-stu-id="d9775-113">Remote call control and phone number normalization in Lync Server 2013</span></span>](lync-server-2013-remote-call-control-and-phone-number-normalization.md)

  - <span data-ttu-id="d9775-114">[Lync Server 2013에서 레거시 권한 있는 호스트 제거 (선택 사항)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (사용자가 이전에 원격 통화 제어에 대해 사용 하도록 설정 된 경우에만)</span><span class="sxs-lookup"><span data-stu-id="d9775-114">[Remove a legacy authorized host in Lync Server 2013 (optional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (only if you are migrating users previously enabled for remote call control)</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="d9775-115">관련 단원</span><span class="sxs-lookup"><span data-stu-id="d9775-115">Related Sections</span></span>

[<span data-ttu-id="d9775-116">Lync Server 2013의 원격 통화 제어 계획</span><span class="sxs-lookup"><span data-stu-id="d9775-116">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


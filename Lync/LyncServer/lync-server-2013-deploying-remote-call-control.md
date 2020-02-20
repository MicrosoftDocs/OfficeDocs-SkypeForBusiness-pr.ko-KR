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
ms.openlocfilehash: c0ca285312264a66113e038c0f5020e47567a5f3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="208be-102">Lync Server 2013에서 원격 통화 제어 배포</span><span class="sxs-lookup"><span data-stu-id="208be-102">Deploying remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="208be-103">_**마지막으로 수정 된 항목:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="208be-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="208be-104">이 섹션에서는 조직의 사용자에게 원격 통화 제어 기능을 배포하는 프로세스를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="208be-104">This section guides you through the process of deploying remote call control functionality to users in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="208be-105">원격 사용자가 조직의 방화벽 외부에 있는 동안에도 원격 통화 제어 기능을 사용할 수 있기는 하지만 외부 액세스 배포 시나리오에 대한 자세한 내용은 이 설명서의 범위를 벗어납니다.</span><span class="sxs-lookup"><span data-stu-id="208be-105">Although remote call control features are available to remote users while they are outside of your organization’s firewall, details about deploying external access scenarios are beyond the scope of this documentation.</span></span> <span data-ttu-id="208be-106">외부 사용자 액세스를 배포 하는 방법에 대 한 자세한 내용은 배포 설명서에서 <A href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013의 외부 사용자 액세스 배포</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="208be-106">For details about deploying external user access, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="208be-107">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="208be-107">In This Section</span></span>

  - [<span data-ttu-id="208be-108">SIP/CSTA 게이트웨이로 라우팅하도록 Lync Server 2013 구성</span><span class="sxs-lookup"><span data-stu-id="208be-108">Configuring Lync Server 2013 to route to a SIP/CSTA gateway</span></span>](lync-server-2013-configuring-lync-server-to-route-to-a-sip-csta-gateway.md)

  - [<span data-ttu-id="208be-109">Lync Server 2013에서 원격 통화 제어에 대 한 고정 경로 구성</span><span class="sxs-lookup"><span data-stu-id="208be-109">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)

  - [<span data-ttu-id="208be-110">Lync Server 2013에서 원격 통화 제어에 대 한 신뢰할 수 있는 응용 프로그램 항목 구성</span><span class="sxs-lookup"><span data-stu-id="208be-110">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

  - <span data-ttu-id="208be-111">Lync Server 2013 (게이트웨이가 TCP를 사용 하도록 구성 된 경우에만) [에서 SIP/CSTA 게이트웨이 IP 주소를 정의](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="208be-111">[Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (only if the gateway is configured to use TCP)</span></span>

  - [<span data-ttu-id="208be-112">Lync Server 2013에서 Lync 사용자가 원격 통화 제어를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="208be-112">Enable Lync users for remote call control in Lync Server 2013</span></span>](lync-server-2013-enable-lync-users-for-remote-call-control.md)

  - [<span data-ttu-id="208be-113">Lync Server 2013의 원격 통화 제어 및 전화 번호 정규화</span><span class="sxs-lookup"><span data-stu-id="208be-113">Remote call control and phone number normalization in Lync Server 2013</span></span>](lync-server-2013-remote-call-control-and-phone-number-normalization.md)

  - <span data-ttu-id="208be-114">[Lync Server 2013에서 권한이 부여 된 기존 호스트 제거 (선택 사항)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (이전에 원격 통화 제어에 사용 하도록 설정 된 사용자를 마이그레이션하는 경우에만)</span><span class="sxs-lookup"><span data-stu-id="208be-114">[Remove a legacy authorized host in Lync Server 2013 (optional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (only if you are migrating users previously enabled for remote call control)</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="208be-115">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="208be-115">Related Sections</span></span>

[<span data-ttu-id="208be-116">Lync Server 2013의 원격 통화 제어 계획</span><span class="sxs-lookup"><span data-stu-id="208be-116">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 새 연결 방지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: c2df1c491384f8a248f70b67880511a2d496c173
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817457"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a><span data-ttu-id="956f6-102">비즈니스용 Skype 서버 유지 관리에 대 한 새 연결 방지</span><span class="sxs-lookup"><span data-stu-id="956f6-102">Preventing new connections to Skype for Business Server for server maintenance</span></span>


<span data-ttu-id="956f6-103">비즈니스용 Skype Server를 통해 사용자에 게 서비스를 손실 하지 않고 서버를 오프 라인으로 전환 (예: 소프트웨어 또는 하드웨어 업그레이드 적용) 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956f6-103">Skype for Business Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="956f6-104">풀에서 서버에 대 한 새 연결이 나 호출을 방지 하는 옵션을 지정 하는 경우,이 옵션을 구현 하는 즉시 새 연결 및 통화가 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="956f6-104">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option.</span></span> <span data-ttu-id="956f6-105">이러한 새 연결 및 통화는 풀의 다른 서버를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="956f6-105">These new connections and calls are routed through other servers in the pool.</span></span> <span data-ttu-id="956f6-106">새 연결을 차단 하는 서버는 기존 연결의 세션이 자연스럽 게 끝날 때까지 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956f6-106">A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end.</span></span> <span data-ttu-id="956f6-107">모든 기존 세션이 종료 되 면 서버를 오프 라인 상태로 전환할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="956f6-107">When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="956f6-108">프런트 엔드 서버에 대 한 새 연결을 차단 하는 경우 일부 비즈니스용 Skype 서버 기능 및 서비스가 DNS 로드 균형 조정에 의존 하 여 제대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="956f6-108">When you prevent new connections to a Front End Server, some Skype for Business Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="956f6-109">풀에서 DNS 부하 분산을 사용 하지 않는 경우 서버에서 새 연결을 차단 하는 기간 동안 이러한 서비스를 통한 연결이 다른 서버로 다시 라우팅되지 않을 수 있으며, 따라서 서버가 오프 라인 상태가 되 면 일부 세션 및 호출이 발생할 수 있습니다. 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="956f6-109">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="956f6-110">이 옵션이 올바르게 작동 하는지 확인 하기 위해 DNS 로드 균형 조정에 의존 하는 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="956f6-110">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="956f6-111">리소스만</span><span class="sxs-lookup"><span data-stu-id="956f6-111">Attendant</span></span>

  - <span data-ttu-id="956f6-112">회의 알림 신청</span><span class="sxs-lookup"><span data-stu-id="956f6-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="956f6-113">응답 그룹 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="956f6-113">Response Group application</span></span>

  - <span data-ttu-id="956f6-114">알림 신청</span><span class="sxs-lookup"><span data-stu-id="956f6-114">Announcement application</span></span>

  - <span data-ttu-id="956f6-115">통화 공원 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="956f6-115">Call Park application</span></span>

<span data-ttu-id="956f6-116">DNS 부하 분산에 대 한 자세한 내용은 [부하 분산 요구 사항을](../../plan-your-deployment/network-requirements/load-balancing.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="956f6-116">For details about DNS load balancing, see [Load balancing requirements](../../plan-your-deployment/network-requirements/load-balancing.md).</span></span>

<span data-ttu-id="956f6-117">비즈니스용 Skype Server를 실행 하는 서버에 있는 모든 서비스에 대해 새 연결을 방지 하는 것 외에, 개별 비즈니스용 Skype Server 서비스에 대 한 새로운 연결을 막을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956f6-117">In addition to preventing new connections for all services on a server running Skype for Business Server, you can also prevent new connections for individual Skype for Business Server services.</span></span> <span data-ttu-id="956f6-118">예를 들어이 방법은 전체 서버를 종료할 필요가 없는 비즈니스용 Skype 서버 업데이트를 적용 해야 하는 상황에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="956f6-118">For example, this method is useful in a situation where you need to apply a Skype for Business Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="956f6-119">한 서비스에 대 한 연결을 방지 하려면 서비스가 그룹화 되 고 서비스의 Windows 목록에 표시 되는 서비스를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="956f6-119">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="956f6-120">예를 들어 비즈니스용 Skype Server 프런트 엔드 서비스 및 모니터링에 대 한 데이터 수집 에이전트는 별도의 비즈니스용 Skype Server services 이지만 Windows 서비스 목록에서 통합 되어 비즈니스용 Skype 서버 프런트 엔드로 표시 됩니다. services.</span><span class="sxs-lookup"><span data-stu-id="956f6-120">For example, the Skype for Business Server Front-End service and the data collection agent for Monitoring are separate Skype for Business Server services, but in the Windows services list they are consolidated and shown as the Skype for Business Server Front End service.</span></span> <span data-ttu-id="956f6-121">비즈니스용 Skype Server 프런트 엔드 서비스에 대 한 새 연결을 막을 수는 있지만,이 두 가지 기본 비즈니스용 Skype Server 서비스에 대 한 새 연결을 개별적으로 막을 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="956f6-121">You can prevent new connections for the Skype for Business Server Front End service, but you cannot prevent new connections for these two individual underlying Skype for Business Server services separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="956f6-122">새 연결을 방지 하도록 서버를 설정한 다음 서버를 다시 시작 하면 기본적으로 서버가 시작 된 후 새 연결을 즉시 수락 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="956f6-122">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="956f6-123">이를 방지 하려면 서버를 다시 시작 하기 전에 서버를 일시 중지 했다가 수동으로 다시 시작 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="956f6-123">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a><span data-ttu-id="956f6-124">비즈니스용 Skype 서버에 대 한 새 연결을 방지 하려면</span><span class="sxs-lookup"><span data-stu-id="956f6-124">To prevent new connections to Skype for Business Server</span></span>

1.  <span data-ttu-id="956f6-125">로컬 컴퓨터에 관리자 그룹의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="956f6-125">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="956f6-126">**시작**을 클릭 하 고 **모든 프로그램**, **관리 도구**를 차례로 가리킨 다음 **서비스**를 클릭 하 여 서비스 스냅인 콘솔을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="956f6-126">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="956f6-127">목록에서 새 연결을 방지 하려는 비즈니스용 Skype 서버 Windows 서비스를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="956f6-127">In the list, double-click the Skype for Business Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="956f6-128">속성 대화 상자의 **서비스 상태: 시작**에서 **일시 중지**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="956f6-128">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="956f6-129">또는 **시작 유형**옆에 있는 **수동**을 클릭 합니다 (선택 사항).</span><span class="sxs-lookup"><span data-stu-id="956f6-129">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="956f6-130">새 연결을 방지 하도록 서버를 설정한 다음 서버를 다시 시작 하면 기본적으로 서버가 시작 된 후 새 연결을 즉시 수락 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="956f6-130">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="956f6-131">이를 방지 하려면 서버를 다시 시작 하기 전에 서버를 일시 중지 했다가 수동으로 다시 시작 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="956f6-131">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

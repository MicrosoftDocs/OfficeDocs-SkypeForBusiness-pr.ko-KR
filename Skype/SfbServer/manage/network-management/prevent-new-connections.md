---
title: 새 연결 방지
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 3f2ca560f934f5b907d05a1f768a0cadd8435f2a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823468"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a><span data-ttu-id="8c8ff-102">서버 유지 관리에 대해 비즈니스용 Skype 서버에 대한 새 연결 방지</span><span class="sxs-lookup"><span data-stu-id="8c8ff-102">Preventing new connections to Skype for Business Server for server maintenance</span></span>


<span data-ttu-id="8c8ff-103">비즈니스용 Skype 서버를 사용하면 사용자에게 서비스를 손실하지 않고도 서버를 오프라인으로 전환할 수 있습니다(예: 소프트웨어 또는 하드웨어 업그레이드 적용).</span><span class="sxs-lookup"><span data-stu-id="8c8ff-103">Skype for Business Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="8c8ff-104">풀의 서버에 대한 새 연결 또는 통화를 방지하기 위한 옵션을 지정하면 이 옵션을 구현하는 즉시 새 연결 및 호출 수행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c8ff-104">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option.</span></span> <span data-ttu-id="8c8ff-105">이러한 새 연결 및 통화는 풀의 다른 서버를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c8ff-105">These new connections and calls are routed through other servers in the pool.</span></span> <span data-ttu-id="8c8ff-106">새 연결을 방지하는 서버는 기존 연결의 세션을 자연적으로 종료될 때까지 둡니다.</span><span class="sxs-lookup"><span data-stu-id="8c8ff-106">A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end.</span></span> <span data-ttu-id="8c8ff-107">모든 기존 세션이 종료되면 서버를 오프라인으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c8ff-107">When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="8c8ff-108">프런트 엔드 서버에 대한 새 연결을 방지하는 경우 일부 비즈니스용 Skype 서버 기능 및 서비스는 DNS 부하 분산을 사용하여 제대로 작동하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c8ff-108">When you prevent new connections to a Front End Server, some Skype for Business Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="8c8ff-109">풀에서 DNS 부하 분산을 사용하지 않는 경우, 이러한 서비스를 통한 연결이 서버가 새 연결을 방지하는 기간 동안 다른 서버로 다시 라우팅되지 않아 서버가 오프라인으로 설정될 때 일부 세션 및 통화가 중단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c8ff-109">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="8c8ff-110">이 옵션이 적절하게 작동하도록 하기 위해 DNS 부하 분산을 사용하는 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8c8ff-110">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="8c8ff-111">도우미</span><span class="sxs-lookup"><span data-stu-id="8c8ff-111">Attendant</span></span>

  - <span data-ttu-id="8c8ff-112">회의 알림 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="8c8ff-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="8c8ff-113">응답 그룹 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="8c8ff-113">Response Group application</span></span>

  - <span data-ttu-id="8c8ff-114">Announcement application(알림 응용 프로그램)</span><span class="sxs-lookup"><span data-stu-id="8c8ff-114">Announcement application</span></span>

  - <span data-ttu-id="8c8ff-115">통화 파크 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="8c8ff-115">Call Park application</span></span>

<span data-ttu-id="8c8ff-116">DNS 부하 분산에 대한 자세한 내용은 부하 분산 요구 [사항을 참조하세요.](../../plan-your-deployment/network-requirements/load-balancing.md)</span><span class="sxs-lookup"><span data-stu-id="8c8ff-116">For details about DNS load balancing, see [Load balancing requirements](../../plan-your-deployment/network-requirements/load-balancing.md).</span></span>

<span data-ttu-id="8c8ff-117">비즈니스용 Skype 서버를 실행하는 서버의 모든 서비스에 대해 새 연결을 차단하는 것 외에도 개별 비즈니스용 Skype 서버 서비스에 대한 새 연결을 방지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c8ff-117">In addition to preventing new connections for all services on a server running Skype for Business Server, you can also prevent new connections for individual Skype for Business Server services.</span></span> <span data-ttu-id="8c8ff-118">예를 들어 이 방법은 전체 서버를 종료할 필요가 없는 비즈니스용 Skype 서버 업데이트를 적용해야 하는 상황에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="8c8ff-118">For example, this method is useful in a situation where you need to apply a Skype for Business Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="8c8ff-119">특정 서비스에 대한 연결을 방지할 때는 Windows 서비스 목록에서 그룹화되어 표시되는 서비스를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c8ff-119">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="8c8ff-120">예를 들어 비즈니스용 Skype 서버 Front-End 서비스 및 모니터링용 데이터 수집 에이전트는 별도의 비즈니스용 Skype 서버 서비스이지만 Windows 서비스 목록에서는 통합되어 비즈니스용 Skype 서버 프런트 엔드 서비스로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c8ff-120">For example, the Skype for Business Server Front-End service and the data collection agent for Monitoring are separate Skype for Business Server services, but in the Windows services list they are consolidated and shown as the Skype for Business Server Front End service.</span></span> <span data-ttu-id="8c8ff-121">비즈니스용 Skype 서버 프런트 엔드 서비스에 대한 새 연결을 방지할 수는 있지만 이러한 두 개의 개별 비즈니스용 Skype 서버 서비스에 대한 새 연결을 별도로 차단할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8c8ff-121">You can prevent new connections for the Skype for Business Server Front End service, but you cannot prevent new connections for these two individual underlying Skype for Business Server services separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c8ff-p104">새 연결을 차단하도록 서버를 설정한 후에 서버를 다시 시작하면 기본적으로 서버가 시작된 직후 새 연결을 허용하기 시작합니다. 이러한 현상을 방지하려면 서버를 다시 시작하기 전에 서버를 수동으로만 일시 중지 및 다시 시작하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c8ff-p104">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a><span data-ttu-id="8c8ff-124">비즈니스용 Skype 서버에 대한 새 연결을 방지</span><span class="sxs-lookup"><span data-stu-id="8c8ff-124">To prevent new connections to Skype for Business Server</span></span>

1.  <span data-ttu-id="8c8ff-125">Administrators 그룹의 구성원으로 로컬 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="8c8ff-125">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="8c8ff-126">서비스 스냅인 콘솔을 여는 경우: **시작,** 모든 프로그램, 관리 도구를 클릭한 다음 **서비스를 클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="8c8ff-126">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="8c8ff-127">목록에서 새 연결을 방지할 비즈니스용 Skype 서버 Windows 서비스를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8c8ff-127">In the list, double-click the Skype for Business Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="8c8ff-128">속성 대화 상자의 **서비스 상태: 시작함,** 일시 **중지를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8c8ff-128">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="8c8ff-129">선택적으로 시작 유형 옆에 있는 **수동을** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8c8ff-129">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8c8ff-p105">새 연결을 차단하도록 서버를 설정한 후에 서버를 다시 시작하면 기본적으로 서버가 시작된 직후 새 연결을 허용하기 시작합니다. 이러한 현상을 방지하려면 서버를 다시 시작하기 전에 서버를 수동으로만 일시 중지 및 다시 시작하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c8ff-p105">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

---
title: 'Lync Server 2013: 지원 되는 가상화 기술 및 알려진 제한 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c81b56fd8d0922b011840aa2b3133ce05d32ad13
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a><span data-ttu-id="0ff54-102">Lync Server 2013의 지원 되는 가상화 기술 및 알려진 제한 사항</span><span class="sxs-lookup"><span data-stu-id="0ff54-102">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ff54-103">_**마지막으로 수정 된 항목:** 2017-02-06_</span><span class="sxs-lookup"><span data-stu-id="0ff54-103">_**Topic Last Modified:** 2017-02-06_</span></span>

<span data-ttu-id="0ff54-104">Lync VDI 플러그 인을 사용 하면 지원 되는 가상화 기술에 대 한 오디오 및 비디오 통화를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff54-104">The Lync VDI plug-in allows audio and video calling for supported virtualization technologies.</span></span> <span data-ttu-id="0ff54-105">이는 [Microsoft lync 2010 백서에서 클라이언트 가상화](https://go.microsoft.com/fwlink/?linkid=330447) 의 Microsoft lync Server 2010에 대해 설명 된 기능을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff54-105">This extends the functionality outlined for Microsoft Lync Server 2010 in the [Client Virtualization in Microsoft Lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) white paper.</span></span> <span data-ttu-id="0ff54-106">표준 전화 규정 준수에는 E911에 대 한 지원도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff54-106">In compliance with standard telephone regulations, support for E911 is also included.</span></span> <span data-ttu-id="0ff54-107">다음 섹션에서는 Lync VDI 플러그 인 및 알려진 기능 제한에 의해 지원 되는 가상화 기술에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff54-107">The following sections describe the virtualization technologies that are supported by the Lync VDI plug-in and the known feature limitations.</span></span>

<div>

## <a name="support-for-virtualization-technologies"></a><span data-ttu-id="0ff54-108">가상화 기술 지원</span><span class="sxs-lookup"><span data-stu-id="0ff54-108">Support for Virtualization Technologies</span></span>

<span data-ttu-id="0ff54-109">Lync VDI 플러그 인은 개인 가상 데스크톱 시나리오에서는 전체 데스크톱 원격을 지원 하지만 원격 데스크톱 세션 시나리오에는 해당 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff54-109">The Lync VDI plug-in supports full desktop remoting in the personal virtual desktop scenario, but not in the remote desktop session scenario.</span></span> <span data-ttu-id="0ff54-110">이러한 시나리오는 다음과 같이 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff54-110">These scenarios can be described as follows:</span></span>

  - <span data-ttu-id="0ff54-111">**지원: 개인 설정 된 가상 데스크톱 또는 VDI (가상 데스크톱 인프라)**    이 시나리오에서는 각 사용자가 맞춤형 가상 데스크톱에 로그온 하 고 세션 간에 지속 되는 파일을 데스크톱에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff54-111">**Supported: Personalized Virtual Desktops or Virtual Desktop Infrastructure (VDI).**   In this scenario, each user logs on to a customizable virtual desktop and is able to save files on the desktop that persist across sessions.</span></span> <span data-ttu-id="0ff54-112">Microsoft 원격 데스크톱 서비스, VMware 수평 보기 및 Citrix XenDesktop은 Lync에서 사용 하도록 테스트 된 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="0ff54-112">Microsoft Remote Desktop Services, VMware Horizon View, and Citrix XenDesktop are implementations that have been tested for use with Lync.</span></span> <span data-ttu-id="0ff54-113">Microsoft에서 테스트 한 공급 업체별 VDI 환경 및 클라이언트 하드웨어에 대 한 자세한 내용은 [Microsoft Lync의 인프라 자격](https://go.microsoft.com/fwlink/?linkid=313435)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0ff54-113">For information about vendor-specific VDI environments and client hardware that have been tested by Microsoft, see [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span></span>

  - <span data-ttu-id="0ff54-114">**지원 되지 않음: 원격 데스크톱 세션**    이 시나리오에서 각 사용자는 사용자 지정할 수 없는 일반 가상 데스크톱 세션에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff54-114">**Not supported: Remote Desktop Sessions.**   In this scenario, each user logs on to a generic virtual desktop session that cannot be customized.</span></span> <span data-ttu-id="0ff54-115">예제 구현에는 Microsoft RDSH (원격 데스크톱 세션) 및 citrix 수신기와 함께 사용 되는 Citrix XenApp 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff54-115">Example implementations include Microsoft Remote Desktop Sessions (RDSH) and Citrix XenApp combined with Citrix Receiver.</span></span>

<span data-ttu-id="0ff54-116">Lync VDI 플러그 인은 전체 응용 프로그램을 로컬로 설치 하지 않고도 응용 프로그램을 사용할 수 있도록 하는 응용 프로그램 가상화와 같은 다른 가상화 기술을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff54-116">The Lync VDI plug-in does not support other virtualization technologies, such as application virtualization, which allows the use of an application without requiring installation of the full application locally.</span></span> <span data-ttu-id="0ff54-117">예제 구현에는 Citrix XenApp 및 Microsoft Application Virtualization (App-v)이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff54-117">Example implementations include Citrix XenApp and Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="0ff54-118">응용 프로그램 스트리밍, 응용 프로그램 원격 및 혼합 가상화 모드 (예: 전체 데스크톱 원격에서의 응용 프로그램 원격)는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff54-118">Application streaming, application remoting, and mixed virtualization modes (for example, application remoting in full desktop remoting) are not supported.</span></span>

<span data-ttu-id="0ff54-119">확장성을 허용 하기 위해 Lync VDI 플러그 인은 DVCs (동적 가상 채널) 라는 플랫폼 독립적 Api를 사용 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff54-119">To allow extensibility, the Lync VDI plug-in was designed to use platform-independent APIs called Dynamic Virtual Channels (DVCs).</span></span> <span data-ttu-id="0ff54-120">Lync에서 명시적으로 지원 하지 않는 시나리오는 VDI solution provider의 지원 문을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0ff54-120">For scenarios that are not explicitly supported by Lync, refer to support statements from the VDI solution provider.</span></span>

</div>

<div>

## <a name="known-feature-limitations"></a><span data-ttu-id="0ff54-121">알려진 기능 제한 사항</span><span class="sxs-lookup"><span data-stu-id="0ff54-121">Known Feature Limitations</span></span>

<span data-ttu-id="0ff54-122">VDI 환경에서 Lync 2013을 사용 하는 경우의 알려진 제한은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff54-122">The following are known limitations when you use Lync 2013 in a VDI environment:</span></span>

  - <span data-ttu-id="0ff54-123">통화 위임 및 응답 그룹 에이전트 익명화 기능에 대 한 지원은 제한적입니다.</span><span class="sxs-lookup"><span data-stu-id="0ff54-123">There is limited support for Call Delegation and Response Group Agent Anonymization features.</span></span>

  - <span data-ttu-id="0ff54-124">다음 기능은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff54-124">There is no support for the following features:</span></span>
    
      - <span data-ttu-id="0ff54-125">통합 오디오 장치 및 비디오 장치 조정 페이지</span><span class="sxs-lookup"><span data-stu-id="0ff54-125">Integrated Audio Device and Video Device tuning pages.</span></span>
    
      - <span data-ttu-id="0ff54-126">다중 보기 비디오</span><span class="sxs-lookup"><span data-stu-id="0ff54-126">Multiple-view video.</span></span>
    
      - <span data-ttu-id="0ff54-127">대화 기록</span><span class="sxs-lookup"><span data-stu-id="0ff54-127">Recording of conversations.</span></span>
    
      - <span data-ttu-id="0ff54-128">RDS (원격 데스크톱 서비스)</span><span class="sxs-lookup"><span data-stu-id="0ff54-128">Remote Desktop Services (RDS).</span></span>
    
      - <span data-ttu-id="0ff54-129">익명으로 모임 참가 (즉, 조직과 페더레이션 되지 않는 조직에서 호스팅하는 Lync 모임 참가)</span><span class="sxs-lookup"><span data-stu-id="0ff54-129">Joining meetings anonymously (that is, joining Lync meetings hosted by an organization that does not federate with your organization).</span></span>
    
      - <span data-ttu-id="0ff54-130">Lync Phone Edition 장치와 함께 Lync VDI 플러그 인 사용</span><span class="sxs-lookup"><span data-stu-id="0ff54-130">Using the Lync VDI plug-in along with a Lync Phone Edition device.</span></span>
    
      - <span data-ttu-id="0ff54-131">네트워크 중단이 발생 하는 경우의 통화 연속성</span><span class="sxs-lookup"><span data-stu-id="0ff54-131">Call continuity in case of a network outage.</span></span>
    
      - <span data-ttu-id="0ff54-132">사용자 지정 된 벨 소리 및 보류 된 음악 기능</span><span class="sxs-lookup"><span data-stu-id="0ff54-132">Customized ringtones and music-on-hold features.</span></span>

  - <span data-ttu-id="0ff54-133">Lync VDI 플러그 인은 Office 365 환경에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff54-133">The Lync VDI plug-in is not supported in an Office 365 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


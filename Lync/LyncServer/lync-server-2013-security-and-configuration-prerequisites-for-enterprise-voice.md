---
title: Enterprise Voice에 대 한 보안 및 구성 선행 조건
description: Enterprise Voice에 대 한 보안 및 구성 선행 조건
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security and configuration prerequisites for Enterprise Voice
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398221(v=OCS.15)
ms:contentKeyID: 48183495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03d0940450889c6bf26cb7761bebbce5e6c2d3f2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551474"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="32406-103">Lync Server 2013의 Enterprise Voice에 대 한 보안 및 구성 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="32406-103">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32406-104">_**마지막으로 수정 된 항목:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="32406-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="32406-105">인프라가 다음과 같은 보안, 사용자 구성 및 시나리오별 하드웨어 필수 구성 요소를 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="32406-105">Verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span>

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="32406-106">관리 권한 및 인증서 인프라</span><span class="sxs-lookup"><span data-stu-id="32406-106">Administrative Rights and Certificate Infrastructure</span></span>

<span data-ttu-id="32406-107">환경이 Enterprise Voice 배포 프로세스 중에 사용할 다음과 같은 관리 사용자 그룹 및 인증서 인프라로 구성되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="32406-107">Be sure that your environment is configured with the following administrative user groups and certificate infrastructure for use during the Enterprise Voice deployment process.</span></span>

  - <span data-ttu-id="32406-108">Enterprise Voice를 배포하는 관리자는 RTCUniversalServerAdmins 그룹의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32406-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="32406-109">구성 작업을 수행하는 관리자에게는 적절한 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32406-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
      - <span data-ttu-id="32406-110">**CsVoiceAdministrator:** 이 관리자 역할은 음성 구성 작업을 수행하고, 음성 응용 프로그램을 관리하고, 최종 사용자에게 음성 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32406-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
      - <span data-ttu-id="32406-p101">**CsUserAdministrator:** 이 관리자 역할은 사용자에 대해 Enterprise Voice를 사용하도록 설정하는 것과 같이 사용자 속성을 관리할 수 있습니다. 또한 이 관리자 역할은 사용자별 정책도 할당할 수 있습니다. 단, 보관 정책/사용자 이동/공통 영역 전화 및 아날로그 장치 관리는 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="32406-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
      - <span data-ttu-id="32406-113">**CsAdministrator:** 이 관리자 역할은 CsVoiceAdministrator 및 CsUserAdministrator의 모든 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32406-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="32406-114">위임 기능을 사용 하면 리소스에 대 한 불필요 한 액세스를 열지 않고도 더 많은 관리자가 Lync Server 배포에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32406-114">Delegation enables more administrators to participate in your Lync Server deployment without opening up unnecessary access to resources.</span></span>

    
    </div>

  - <span data-ttu-id="32406-115">Microsoft 또는 타사 CA(인증 기관) 인프라를 사용하여 MKI(관리 키 인프라)가 배포 및 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="32406-115">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="32406-116">Lync Server의 인증서 요구 사항에 대 한 자세한 내용은 계획 설명서에서 <A href="lync-server-2013-certificate-infrastructure-requirements.md">Lync server 2013의 인증서 인프라 요구 사항</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="32406-116">For details about certificate requirements in Lync Server, see <A href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="user-configuration"></a><span data-ttu-id="32406-117">사용자 구성</span><span class="sxs-lookup"><span data-stu-id="32406-117">User Configuration</span></span>

<span data-ttu-id="32406-118">프런트 엔드 배포 중에 중재 서버를 각 프런트 엔드 풀 또는 Standard Edition 서버에 배치 된 하는 경우 Enterprise Voice에 필요한 사용자 설정이 해당 서버 역할에 대 한 파일을 설치 하는 동안 자동으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32406-118">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>

<span data-ttu-id="32406-119">Enterprise Voice 작업을 새로 배포하는 경우에는 배포 프로세스를 시작하기 전에 Enterprise Voice를 사용하도록 설정할 각 사용자에 대해 기본 전화 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="32406-119">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="32406-120">관리자는 이 번호가 고유한지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32406-120">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="32406-121">구현 하기 전에 모든 기본 전화 번호의 형식을 올바르게 지정 하 고 Lync Server 제어판을 사용 하 여 각 사용자의 **줄 URI** 속성에 복사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32406-121">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user’s **Line URI** property using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="32406-122">Enterprise Voice 배포에 필요한 기본 전화 번호의 예는 계획 설명서의 <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync server 2013에서 다이얼 플랜 및 정규화 규칙</A> 의 <A href="lync-server-2013-dial-plans-and-normalization-rules.md">lync server 2013 섹션에 있는 다이얼 플랜 및 정규화 규칙</A> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="32406-122">For examples of primary phone numbers required for Enterprise Voice deployment, see the <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> section of <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="32406-123">다음 단계: 파일 설치 또는 PSTN 연결 구성</span><span class="sxs-lookup"><span data-stu-id="32406-123">Next Steps: Install Files or Configure PSTN Connectivity</span></span>

<span data-ttu-id="32406-124">Enterprise Voice에 대한 소프트웨어 및 환경 필수 구성 요소를 확인한 후에는 다음 콘텐츠를 참조하여 아래와 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32406-124">After verifying software and environmental prerequisites for Enterprise Voice, you can use the following content to either:</span></span>

  - <span data-ttu-id="32406-125">배치 된 때 중재 서버가 프런트 엔드 풀 또는 Standard Edition Server 배포 프로세스의 일부로 설치 된 경우에만, 독립 실행형 중재 서버 또는 풀을 배포 하려는 경우에만 [2013](lync-server-2013-install-the-files-for-mediation-server.md)에 설명 된 대로 중재 서버를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="32406-125">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

  - <span data-ttu-id="32406-126">또는 [Lync Server 2013에서 트렁크을 구성](lync-server-2013-configuring-trunks.md)하는 방법에 설명 된 대로 Enterprise Voice 사용자에 대 한 통화를 라우팅하도록 설정 구성을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="32406-126">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


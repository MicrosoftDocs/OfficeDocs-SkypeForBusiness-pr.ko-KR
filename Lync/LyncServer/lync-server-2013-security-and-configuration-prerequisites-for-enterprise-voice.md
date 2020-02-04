---
title: Enterprise Voice에 대한 보안 및 구성 필수 구성 요소
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
ms.openlocfilehash: 6530e00a942e2e839eaf4bc2d069212b746e2504
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="fef39-102">Lync Server 2013의 엔터프라이즈 음성에 대 한 보안 및 구성 선행 조건</span><span class="sxs-lookup"><span data-stu-id="fef39-102">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fef39-103">_**마지막으로 수정한 주제:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="fef39-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="fef39-104">인프라가 다음 보안, 사용자 구성 및 시나리오 관련 하드웨어 필수 구성 요소를 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef39-104">Verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span>

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="fef39-105">관리 권한 및 인증서 인프라</span><span class="sxs-lookup"><span data-stu-id="fef39-105">Administrative Rights and Certificate Infrastructure</span></span>

<span data-ttu-id="fef39-106">환경이 엔터프라이즈 음성 배포 프로세스 중에 사용할 수 있도록 다음 관리 사용자 그룹 및 인증서 인프라로 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef39-106">Be sure that your environment is configured with the following administrative user groups and certificate infrastructure for use during the Enterprise Voice deployment process.</span></span>

  - <span data-ttu-id="fef39-107">엔터프라이즈 음성을 배포 하는 관리자는 RTCUniversalServerAdmins 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef39-107">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="fef39-108">구성 작업을 수행 하는 관리자에 게 적절 한 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef39-108">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
      - <span data-ttu-id="fef39-109">**CsVoiceAdministrator:** 이 관리자 역할은 음성 구성 작업을 수행 하 고, 음성 응용 프로그램을 관리 하 고, 최종 사용자에 게 음성 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef39-109">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
      - <span data-ttu-id="fef39-110">**Csuseradministrator:** 이 관리자 역할은 사용자의 엔터프라이즈 보이스 사용 등의 사용자 속성을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef39-110">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user.</span></span> <span data-ttu-id="fef39-111">이 관리자 역할은 또한 보관 정책의 예외를 사용 하 여 사용자별 정책을 할당할 수 있습니다. 사용자 이동 공통 영역 전화 및 아날로그 장치를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef39-111">This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
      - <span data-ttu-id="fef39-112">**Csadministrator:** 이 관리자 역할은 CsVoiceAdministrator 및 CsUserAdministrator의 모든 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef39-112">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="fef39-113">위임을 사용 하면 더 많은 관리자가 리소스에 대 한 불필요 한 액세스를 열지 않고도 Lync Server 배포에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef39-113">Delegation enables more administrators to participate in your Lync Server deployment without opening up unnecessary access to resources.</span></span>

    
    </div>

  - <span data-ttu-id="fef39-114">Microsoft 또는 타사 CA (인증 기관) 인프라를 사용 하 여 MKI (관리 키 인프라)를 배포 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef39-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="fef39-115">Lync Server의 인증서 요구 사항에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-certificate-infrastructure-requirements.md">Lync server 2013에 대 한 인증서 인프라 요구 사항을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fef39-115">For details about certificate requirements in Lync Server, see <A href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="user-configuration"></a><span data-ttu-id="fef39-116">사용자 구성</span><span class="sxs-lookup"><span data-stu-id="fef39-116">User Configuration</span></span>

<span data-ttu-id="fef39-117">프런트 엔드 배포 중에 각 프런트 엔드 풀 또는 Standard Edition 서버와 중재 서버를 collocated 경우 Enterprise Voice에 필요한 사용자 설정이 해당 서버 역할에 대 한 파일을 설치 하는 동안 자동으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fef39-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>

<span data-ttu-id="fef39-118">지금 엔터프라이즈 음성 작업 부하를 새로 배포 하는 경우 배포 프로세스를 시작 하기 전에 엔터프라이즈 음성을 사용할 수 있도록 계획 하는 각 사용자의 기본 전화 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef39-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="fef39-119">관리자는이 번호가 고유 하다는 것을 책임 집니다.</span><span class="sxs-lookup"><span data-stu-id="fef39-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="fef39-120">구현 하기 전에 모든 주 전화 번호의 형식을 올바르게 지정 하 고 Lync Server 제어판을 사용 하 여 각 사용자의 **줄 URI** 속성에 복사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef39-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user’s **Line URI** property using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="fef39-121">엔터프라이즈 음성 배포에 필요한 기본 전화 번호의 예는 계획 설명서의 <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync server 2013에서 다이얼</A> 플랜 및 정규화 규칙의 <A href="lync-server-2013-dial-plans-and-normalization-rules.md">lync server 2013 섹션에 있는 다이얼 플랜 및 정규화</A> 규칙을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fef39-121">For examples of primary phone numbers required for Enterprise Voice deployment, see the <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> section of <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="fef39-122">다음 단계: 파일 설치 또는 PSTN 연결 구성</span><span class="sxs-lookup"><span data-stu-id="fef39-122">Next Steps: Install Files or Configure PSTN Connectivity</span></span>

<span data-ttu-id="fef39-123">엔터프라이즈 음성에 대 한 소프트웨어 및 환경 선행 조건을 확인 한 후 다음 콘텐츠를 사용 하 여 다음 중 하나를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef39-123">After verifying software and environmental prerequisites for Enterprise Voice, you can use the following content to either:</span></span>

  - <span data-ttu-id="fef39-124">Collocated 때 중재 서버가 프런트 엔드 풀 또는 Standard Edition Server 배포 프로세스의 일부로 설치 되어 있는 경우 [2013](lync-server-2013-install-the-files-for-mediation-server.md)에만 독립 실행형 중재 서버 또는 풀을 배포 하려는 경우에만 조정 서버를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef39-124">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

  - <span data-ttu-id="fef39-125">또는 [Lync Server 2013에서 trunks를 구성](lync-server-2013-configuring-trunks.md)하는 방법에 설명 된 대로 엔터프라이즈 음성 사용자에 대 한 통화를 라우팅하도록 설정 구성을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef39-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


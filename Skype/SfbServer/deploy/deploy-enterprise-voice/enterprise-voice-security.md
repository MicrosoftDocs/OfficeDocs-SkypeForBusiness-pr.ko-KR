---
title: 비즈니스용 Skype 서버의 보안 Enterprise Voice 구성 선행 요구
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: '요약: 비즈니스용 Skype 서버의 보안 및 구성 Enterprise Voice 대해 자세히 알아보습니다.'
ms.openlocfilehash: 77efbf231f83c6d3c31254c9ab742de7e2b226e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830848"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="f16d2-103">비즈니스용 Skype 서버의 보안 Enterprise Voice 구성 선행 요구</span><span class="sxs-lookup"><span data-stu-id="f16d2-103">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="f16d2-104">**요약:** 비즈니스용 Skype 서버의 보안 및 구성 Enterprise Voice 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="f16d2-104">**Summary:** Learn about the security and configuration prerequisites for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="f16d2-105">이 Enterprise Voice 배포하기 전에 인프라가 다음과 같은 보안, 사용자 구성 및 시나리오별 하드웨어 선행 요구 사항을 충족하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f16d2-105">Before deploying Enterprise Voice, verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span> 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="f16d2-106">관리 권한 및 인증서 인프라</span><span class="sxs-lookup"><span data-stu-id="f16d2-106">Administrative rights and certificate infrastructure</span></span>

<span data-ttu-id="f16d2-107">배포하기 전에 다음을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="f16d2-107">Before deploying, check the following:</span></span>
  
- <span data-ttu-id="f16d2-108">Enterprise Voice를 배포하는 관리자는 RTCUniversalServerAdmins 그룹의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f16d2-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>
    
- <span data-ttu-id="f16d2-109">구성 작업을 수행하는 관리자에게는 적절한 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f16d2-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
  - <span data-ttu-id="f16d2-110">**CsVoiceAdministrator:** 이 관리자 역할은 음성 구성 작업을 수행하고, 음성 응용 프로그램을 관리하고, 최종 사용자에게 음성 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f16d2-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
  - <span data-ttu-id="f16d2-p101">**CsUserAdministrator:** 이 관리자 역할은 사용자에 대해 Enterprise Voice를 사용하도록 설정하는 것과 같이 사용자 속성을 관리할 수 있습니다. 또한 이 관리자 역할은 사용자별 정책도 할당할 수 있습니다. 단, 보관 정책/사용자 이동/공통 영역 전화 및 아날로그 장치 관리는 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="f16d2-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
  - <span data-ttu-id="f16d2-113">**CsAdministrator:** 이 관리자 역할은 CsVoiceAdministrator 및 CsUserAdministrator의 모든 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f16d2-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
- <span data-ttu-id="f16d2-114">Microsoft 또는 타사 CA(인증 기관) 인프라를 사용하여 MKI(관리 키 인프라)가 배포 및 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f16d2-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f16d2-115">비즈니스용 Skype 서버의 인증서 요구 사항에 대한 자세한 내용은 비즈니스용 [Skype 서버 2015의](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 환경 요구 사항 또는 비즈니스용 [Skype 서버 2019의](../../../SfBServer2019/plan/system-requirements.md)서버 요구 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f16d2-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
## <a name="user-configuration"></a><span data-ttu-id="f16d2-116">사용자 구성</span><span class="sxs-lookup"><span data-stu-id="f16d2-116">User configuration</span></span>

<span data-ttu-id="f16d2-117">프런트 엔드 배포 중에 중재 서버를 각 프런트 엔드 풀 또는 Standard Edition 서버와 함께 배치한 경우 이러한 서버 역할에 Enterprise Voice 설치하는 동안 중재 서버에 필요한 사용자 설정이 자동으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f16d2-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>
  
<span data-ttu-id="f16d2-118">Enterprise Voice 작업을 새로 배포하는 경우에는 배포 프로세스를 시작하기 전에 Enterprise Voice를 사용하도록 설정할 각 사용자에 대해 기본 전화 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f16d2-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="f16d2-119">관리자는 이 번호가 고유한지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f16d2-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="f16d2-120">구현하기 전에 비즈니스용 Skype 서버 제어판을 사용하여 모든 기본 전화 번호를 정규화하고(올바르게 형식 지정) 각 사용자의 줄 **URI** 속성에 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f16d2-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user's **Line URI** property using Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f16d2-121">배포에 필요한 기본 전화 번호의 예는 Enterprise Voice 정규화 규칙 [예제를 참조합니다.](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules)</span><span class="sxs-lookup"><span data-stu-id="f16d2-121">For examples of primary phone numbers required for Enterprise Voice deployment, see [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span></span> 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="f16d2-122">다음 단계: 파일 설치 또는 PSTN 연결 구성</span><span class="sxs-lookup"><span data-stu-id="f16d2-122">Next Steps: Install files or configure PSTN connectivity</span></span>

<span data-ttu-id="f16d2-123">다음 중 하나에 대한 소프트웨어 및 환경 Enterprise Voice 선행 요구 사항 확인 후 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f16d2-123">After verifying software and environmental prerequisites for Enterprise Voice you can either:</span></span>
  
- <span data-ttu-id="f16d2-124">비즈니스용 [Skype](deploy-a-mediation-server.md)서버의 토폴로지 작성기에서 중재 서버 배포에 설명된 바와 같이 중재 서버를 설치합니다. 단, 중재 서버가 배치될 때 프런트 엔드 풀 또는 Standard Edition Server 배포 프로세스의 일부로 설치되어 독립 실행형 중재 서버 또는 풀을 배포하려는 경우만 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f16d2-124">Install the Mediation Server, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>
    
- <span data-ttu-id="f16d2-125">또는 비즈니스용 Skype 서버의 트렁크 구성에 설명된 Enterprise Voice 사용자에 대한 통화를 라우팅하도록 설정 [구성을 시작하십시오.](configure-trunks.md)</span><span class="sxs-lookup"><span data-stu-id="f16d2-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configure trunks in Skype for Business Server](configure-trunks.md).</span></span>
    


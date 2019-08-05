---
title: 비즈니스용 Skype 서버에서 엔터프라이즈 음성에 대 한 보안 및 구성 선행 조건
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: '요약: 비즈니스용 Skype 서버에서 엔터프라이즈 음성에 대 한 보안 및 구성 선행 조건에 대해 알아봅니다.'
ms.openlocfilehash: b3fced9ecac9020da9601c2ab6831769b34ae00a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196477"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="9d00d-103">비즈니스용 Skype 서버에서 엔터프라이즈 음성에 대 한 보안 및 구성 선행 조건</span><span class="sxs-lookup"><span data-stu-id="9d00d-103">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="9d00d-104">**요약:** 비즈니스용 Skype 서버에서 엔터프라이즈 음성에 대 한 보안 및 구성 선행 조건에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="9d00d-104">**Summary:** Learn about the security and configuration prerequisites for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="9d00d-105">엔터프라이즈 음성을 배포 하기 전에 인프라에서 다음 보안, 사용자 구성, 시나리오 관련 하드웨어 필수 구성 요소를 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d00d-105">Before deploying Enterprise Voice, verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span> 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="9d00d-106">관리 권한 및 인증서 인프라</span><span class="sxs-lookup"><span data-stu-id="9d00d-106">Administrative rights and certificate infrastructure</span></span>

<span data-ttu-id="9d00d-107">배포 하기 전에 다음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d00d-107">Before deploying, check the following:</span></span>
  
- <span data-ttu-id="9d00d-108">엔터프라이즈 음성을 배포 하는 관리자는 RTCUniversalServerAdmins 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d00d-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>
    
- <span data-ttu-id="9d00d-109">구성 작업을 수행 하는 관리자에 게 적절 한 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d00d-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
  - <span data-ttu-id="9d00d-110">**CsVoiceAdministrator:** 이 관리자 역할은 음성 구성 작업을 수행 하 고, 음성 응용 프로그램을 관리 하 고, 최종 사용자에 게 음성 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d00d-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
  - <span data-ttu-id="9d00d-111">**Csuseradministrator:** 이 관리자 역할은 사용자의 엔터프라이즈 보이스 사용 등의 사용자 속성을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d00d-111">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user.</span></span> <span data-ttu-id="9d00d-112">이 관리자 역할은 또한 보관 정책의 예외를 사용 하 여 사용자별 정책을 할당할 수 있습니다. 사용자 이동 공통 영역 전화 및 아날로그 장치를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d00d-112">This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
  - <span data-ttu-id="9d00d-113">**Csadministrator:** 이 관리자 역할은 CsVoiceAdministrator 및 CsUserAdministrator의 모든 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d00d-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
- <span data-ttu-id="9d00d-114">Microsoft 또는 타사 CA (인증 기관) 인프라를 사용 하 여 MKI (관리 키 인프라)를 배포 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d00d-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9d00d-115">비즈니스용 Skype Server의 인증서 요구 사항에 대 한 자세한 내용은 비즈니스용 [Skype server 2015의 환경 요구 사항](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 또는 비즈니스용 [skype server 2019에 대 한 서버 요구](../../../SfBServer2019/plan/system-requirements.md)사항을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9d00d-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
## <a name="user-configuration"></a><span data-ttu-id="9d00d-116">사용자 구성</span><span class="sxs-lookup"><span data-stu-id="9d00d-116">User configuration</span></span>

<span data-ttu-id="9d00d-117">프런트 엔드 배포 중에 각 프런트 엔드 풀 또는 Standard Edition 서버와 중재 서버를 collocated 경우 Enterprise Voice에 필요한 사용자 설정이 해당 서버 역할에 대 한 파일을 설치 하는 동안 자동으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d00d-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>
  
<span data-ttu-id="9d00d-118">지금 엔터프라이즈 음성 작업 부하를 새로 배포 하는 경우 배포 프로세스를 시작 하기 전에 엔터프라이즈 음성을 사용할 수 있도록 계획 하는 각 사용자의 기본 전화 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d00d-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="9d00d-119">관리자는이 번호가 고유 하다는 것을 책임 집니다.</span><span class="sxs-lookup"><span data-stu-id="9d00d-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="9d00d-120">구현 하기 전에 모든 주 전화 번호의 형식이 정규화 되어 비즈니스용 Skype Server 제어판을 사용 하 여 각 사용자의 **줄 URI** 속성에 복사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d00d-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user's **Line URI** property using Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9d00d-121">엔터프라이즈 음성 배포에 필요한 기본 전화 번호 예제는 [예제 정규화 규칙](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9d00d-121">For examples of primary phone numbers required for Enterprise Voice deployment, see [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span></span> 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="9d00d-122">다음 단계: 파일 설치 또는 PSTN 연결 구성</span><span class="sxs-lookup"><span data-stu-id="9d00d-122">Next Steps: Install files or configure PSTN connectivity</span></span>

<span data-ttu-id="9d00d-123">엔터프라이즈 음성에 대 한 소프트웨어 및 환경 필수 구성 요소를 확인 한 후 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d00d-123">After verifying software and environmental prerequisites for Enterprise Voice you can either:</span></span>
  
- <span data-ttu-id="9d00d-124">[비즈니스용 Skype 서버의 토폴로지 작성기에 조정 서버 배포](deploy-a-mediation-server.md)에 설명 된 바와 같이 중재 서버를 설치 하 되, 중재 서버가 프런트 엔드에서 설치 되어 있기 때문에 독립 실행형 중재 서버 또는 풀을 배포 하려는 경우에만 필요 합니다. collocated 때 풀 또는 Standard Edition 서버 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="9d00d-124">Install the Mediation Server, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>
    
- <span data-ttu-id="9d00d-125">또는 [비즈니스용 Skype 서버에서 Trunks 구성](configure-trunks.md)에 설명 된 대로 엔터프라이즈 음성 사용자에 대 한 통화를 라우팅하도록 설정 구성을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d00d-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configure trunks in Skype for Business Server](configure-trunks.md).</span></span>
    


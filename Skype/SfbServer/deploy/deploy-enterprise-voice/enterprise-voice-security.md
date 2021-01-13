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
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 보안 Enterprise Voice 구성 선행 요구
 
**요약:** 비즈니스용 Skype 서버의 보안 및 구성 Enterprise Voice 대해 자세히 알아보습니다.
  
이 Enterprise Voice 배포하기 전에 인프라가 다음과 같은 보안, 사용자 구성 및 시나리오별 하드웨어 선행 요구 사항을 충족하는지 확인해야 합니다. 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>관리 권한 및 인증서 인프라

배포하기 전에 다음을 검사합니다.
  
- Enterprise Voice를 배포하는 관리자는 RTCUniversalServerAdmins 그룹의 구성원이어야 합니다.
    
- 구성 작업을 수행하는 관리자에게는 적절한 권한이 있어야 합니다.
    
  - **CsVoiceAdministrator:** 이 관리자 역할은 음성 구성 작업을 수행하고, 음성 응용 프로그램을 관리하고, 최종 사용자에게 음성 정책을 할당할 수 있습니다.
    
  - **CsUserAdministrator:** 이 관리자 역할은 사용자에 대해 Enterprise Voice를 사용하도록 설정하는 것과 같이 사용자 속성을 관리할 수 있습니다. 또한 이 관리자 역할은 사용자별 정책도 할당할 수 있습니다. 단, 보관 정책/사용자 이동/공통 영역 전화 및 아날로그 장치 관리는 예외입니다.
    
  - **CsAdministrator:** 이 관리자 역할은 CsVoiceAdministrator 및 CsUserAdministrator의 모든 작업을 수행할 수 있습니다.
    
- Microsoft 또는 타사 CA(인증 기관) 인프라를 사용하여 MKI(관리 키 인프라)가 배포 및 구성됩니다.
    
    > [!NOTE]
    > 비즈니스용 Skype 서버의 인증서 요구 사항에 대한 자세한 내용은 비즈니스용 [Skype 서버 2015의](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 환경 요구 사항 또는 비즈니스용 [Skype 서버 2019의](../../../SfBServer2019/plan/system-requirements.md)서버 요구 사항을 참조하세요. 
  
## <a name="user-configuration"></a>사용자 구성

프런트 엔드 배포 중에 중재 서버를 각 프런트 엔드 풀 또는 Standard Edition 서버와 함께 배치한 경우 이러한 서버 역할에 대한 Enterprise Voice 설치하는 동안 중재 서버에 필요한 사용자 설정이 자동으로 구성됩니다.
  
Enterprise Voice 작업을 새로 배포하는 경우에는 배포 프로세스를 시작하기 전에 Enterprise Voice를 사용하도록 설정할 각 사용자에 대해 기본 전화 번호를 지정합니다. 관리자는 이 번호가 고유한지 확인해야 합니다. 구현하기 전에 비즈니스용 Skype 서버 제어판을 사용하여 모든 기본 전화 번호를 정규화하고(올바르게 형식 지정) 각 사용자의 줄 **URI** 속성에 복사해야 합니다.
  
> [!NOTE]
> 배포에 필요한 기본 전화 번호의 예는 Enterprise Voice 정규화 규칙 [예제를 참조합니다.](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules) 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>다음 단계: 파일 설치 또는 PSTN 연결 구성

다음 중 하나에 대한 소프트웨어 및 환경 Enterprise Voice 선행 요구 사항 확인 후 다음을 할 수 있습니다.
  
- 비즈니스용 [Skype](deploy-a-mediation-server.md)서버의 토폴로지 작성기에서 중재 서버 배포에 설명된 바와 같이 중재 서버를 설치합니다. 단, 중재 서버가 배치될 때 프런트 엔드 풀 또는 Standard Edition Server 배포 프로세스의 일부로 설치되어 독립 실행형 중재 서버 또는 풀을 배포하려는 경우만 설치합니다.
    
- 또는 비즈니스용 Skype 서버의 트렁크 구성에 설명된 Enterprise Voice 사용자에 대한 통화를 라우팅하도록 설정 [구성을 시작하십시오.](configure-trunks.md)
    


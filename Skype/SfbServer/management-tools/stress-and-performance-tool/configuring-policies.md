---
title: 비즈니스용 Skype Server 2015 스트레스 및 성능 도구에 맞게 정책 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대 한 정책 구성입니다.
ms.openlocfilehash: bfdf0d9875a37f7f4a1f98aa24cd6fd5c3176a00
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816197"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>비즈니스용 Skype Server 2015 스트레스 및 성능 도구에 맞게 정책 구성
 
비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대 한 정책 구성입니다.
  
스트레스 및 성능 도구를 실행 하기 전에 비즈니스용 Skype Server 2015에서 구성할 수 있는 몇 가지 정책과 기타 영역이 있습니다.
  
- [보관 정책](configuring-policies.md#ArchivingPolicy)
    
- [회의 정책](configuring-policies.md#ConferencingPolicy)
    
- [연락처 정책](configuring-policies.md#ContactsPolicy)
    
- [페더레이션 정책](configuring-policies.md#FederationPolicy)
    
- [통화 허용 제어 정책](configuring-policies.md#CACPolicy)
    
- [음성 라우팅 규칙](configuring-policies.md#VoiceRoutingRules)
    
- [컨퍼런스 전화 교환 응용 프로그램](configuring-policies.md#ConfAttendantApp)
    
- [서버 통화 공원 서비스](configuring-policies.md#ServerCallParkServ)
    
- [비상 전화](configuring-policies.md#EmergencyCalls)
    
- [응답 그룹 응용 프로그램 구성](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>보관 정책
<a name="ArchivingPolicy"> </a>

비즈니스용 Skype 서버 토폴로지에 배포 된 보관 서버가 있는 경우 ArchivingPolicy 스크립트를 볼 수 있습니다. 추가 지원이 필요한 경우 보관 및 웹 회의 cmdlet을 확인 하세요.
  
## <a name="conferencing-policy"></a>회의 정책
<a name="ConferencingPolicy"> </a>

회의의 경우 MeetingPolicy 스크립트가 있습니다. 추가 지원이 필요한 경우 웹 회의 cmdlet을 확인 하세요.
  
## <a name="contacts-policy"></a>연락처 정책
<a name="ContactsPolicy"> </a>

연락처 Spolicy 스크립트는 검토 해야 하는 샘플입니다. 추가 참조가 필요한 경우 메신저 대화 및 현재 상태 cmdlet이 도움이 됩니다.
  
## <a name="federation-policy"></a>페더레이션 정책
<a name="FederationPolicy"> </a>

페더레이션에 대 한 샘플 스크립트는 FederationPolicy입니다. 검토가 필요한 경우에는 Edge 서버, 페더레이션 및 외부 액세스를 확인할 cmdlet입니다.
  
## <a name="call-admission-control-policy"></a>통화 허용 제어 정책
<a name="CACPolicy"> </a>

이 정책에 대해 BandwidthPolicy를 참조할 수 있습니다. 또한 통화 허용 제어 cmdlet에는 추가 정보가 포함 됩니다.
  
## <a name="voice-routing-rules"></a>음성 라우팅 규칙
<a name="VoiceRoutingRules"> </a>

음성 라우팅에 대 한 RoutingRules 샘플 스크립트가 필요 합니다. 이러한 규칙을 구성 하는 경우 사용자를 만들 때 지정할 수 있도록 전화 컨텍스트 (/위치 프로필 또는/SimpleName) 및 내부/외부 지역 코드를 기록해 둡니다. 또한 L Cperf도구 구성 중에도 필요 합니다 (특히 PSTN-UC 및 UC-PSTN 용).
  
예를 들어 RoutingRules의 **새-CsDialPlan 플랜** cmdlet에 대 한 호출의 simplename 매개 변수는 다음 UserProfileGenerator 그림의 locationprofile 값에 사용 해야 합니다.
  
![비즈니스용 Skype 부하 구성 도구, 음성 시나리오 탭, 대화에 대 한 고급 설정.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
자세한 내용은 엔터프라이즈 음성 cmdlet을 검토 하면 됩니다.
  
## <a name="conference-attendant-application"></a>컨퍼런스 전화 교환 응용 프로그램
<a name="ConfAttendantApp"> </a>

먼저 ConferenceAutoAttendantConfiguration 스크립트를 검토 합니다. 다음과 같이 구성 생성을 위한 LConferencingAutoAttendant Cperf도구 구성 도구에 입력할 수 있도록 기본적으로 1121111111 전화 번호를 기록해 야 합니다.
  
![회의 로드 수준 및 전화 번호를 보여주는 음성 시나리오 탭](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
회의 및 전화 접속 회의 cmdlet에서 자세한 내용을 확인할 수 있습니다.
  
## <a name="server-call-park-service"></a>서버 통화 공원 서비스
<a name="ServerCallParkServ"> </a>

기본적으로이 기능은 비활성화 되어 있습니다. 이를 테스트 해야 하는 경우 CallParkConfiguration 샘플 스크립트를 검토할 수 있습니다. 또한 필요에 따라 통화 공원 응용 프로그램 cmdlet을 확인 하세요.
  
## <a name="emergency-calls"></a>비상 전화
<a name="EmergencyCalls"> </a>

비상 전화에 대 한 스트레스 및 성능 테스트를 구성 하려면 다음 단계를 수행 해야 합니다.
  
1. 비상 전화에 대 한 음성 경로를 설정 합니다. RoutingRules 스크립트를 사용 하 고 " **PSTN으로 E911 라우팅** " 설명 아래에서이 음성 경로를 설정 하는 방법에 대 한 예를 확인 합니다.
    
    > [!CAUTION]
    > RoutingRules의 예제 명령에 911이 아닌 숫자 119를 포함 하는 숫자 패턴이 있습니다. 911 (또는 실제 지역 비상 전화 번호)을 사용 하 여 부하 테스트 중에 지역 긴급 운영자에 게 실수로 전화를 하지 않도록 해야 합니다. 이 구성은 시뮬레이션 용도로만 사용 된다는 점에 유의 하세요. 
  
2. 다음 그림과 같이 UserProvisioningTool의 **위치 정보 서비스 구성** 탭에 있는 값을 입력 하 여 주소를 구성 합니다.
    
     ![주소, 서브넷, 스위치 및 포트 수를 보여 주는 사용자 프로비저닝 도구](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. 모든 내용을 UserProvisioningTool에 입력 한 후에는 **LIS Config 파일 생성** 단추를 클릭 합니다.
    
4. 이제 스트레스 및 성능 도구에 대 한 XML 파일은 물론 포트, 서브넷, 스위치 및 WAPs (무선 액세스 지점)에 대 한 CSV 파일도 생성 됩니다. LisConfiguration. ps1 스크립트를 사용 하 여 LIS (위치 정보 서비스)를 구성할 때 입력에 CSV 파일을 사용할 수 있습니다. 이 작업을 수행 하려면 스트레스 및 성능 도구 실행 파일 (L<c13> Cperftool. exe)과 동일한 폴더를 Locations0로 이동 해야 합니다. 이렇게 하면 위치 프로필 (다이얼 플랜) 시나리오를 실행할 수 있습니다.
    
## <a name="configuring-response-group-application"></a>응답 그룹 응용 프로그램 구성
<a name="ConfigResponseGroupApp"> </a>

샘플 스크립트는 ResponseGroupConfiguration. ps1입니다. 추가 구성 세부 정보를 검토 하는 응답 그룹 응용 프로그램 cmdlet도 있습니다. 다음 다이어그램은 몇 가지 구성 세부 정보를 보여 줍니다.
  
![테스트에 대 한 기존 워크플로를 보여 주는 응답 그룹 구성 도구입니다.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  


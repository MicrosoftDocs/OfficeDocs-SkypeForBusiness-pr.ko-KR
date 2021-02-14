---
title: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대한 정책 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대한 정책 구성
ms.openlocfilehash: bb049d5740d74e5ebeacd8a21d00e2644da61a7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815038"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대한 정책 구성
 
비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대한 정책 구성
  
스트레스 및 성능 도구를 실행하기 전에 비즈니스용 Skype 서버 2015에서 구성할 수 있는 몇 가지 정책 및 기타 영역이 있습니다.
  
- [보관 정책](configuring-policies.md#ArchivingPolicy)
    
- [회의 정책](configuring-policies.md#ConferencingPolicy)
    
- [연락처 정책](configuring-policies.md#ContactsPolicy)
    
- [페더전 정책](configuring-policies.md#FederationPolicy)
    
- [통화 제어 정책](configuring-policies.md#CACPolicy)
    
- [음성 라우팅 규칙](configuring-policies.md#VoiceRoutingRules)
    
- [회의 참석자 응용 프로그램](configuring-policies.md#ConfAttendantApp)
    
- [서버 통화 파크 서비스](configuring-policies.md#ServerCallParkServ)
    
- [긴급 통화](configuring-policies.md#EmergencyCalls)
    
- [응답 그룹 응용 프로그램 구성](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>보관 정책
<a name="ArchivingPolicy"> </a>

비즈니스용 Skype 서버 토폴로지에서 보관 서버를 배포한 경우 이 스크립트를 ArchivingPolicy.ps1 있습니다. 추가 지원이 필요한 경우 보관 및 웹 회의 cmdlet을 확인 합니다.
  
## <a name="conferencing-policy"></a>회의 정책
<a name="ConferencingPolicy"> </a>

회의의 경우 이 MeetingPolicy.ps1 있습니다. 추가 지원이 필요한 경우 웹 회의 cmdlet을 확인 합니다.
  
## <a name="contacts-policy"></a>연락처 정책
<a name="ContactsPolicy"> </a>

ContactsPolicy.ps1 스크립트는 검토해야 하는 샘플이 됩니다. 추가 참조가 필요한 경우 IM 및 현재 상태 cmdlet을 사용하면 도움이 됩니다.
  
## <a name="federation-policy"></a>페더전 정책
<a name="FederationPolicy"> </a>

페더링에 대한 샘플 스크립트는 FederationPolicy.ps1. 추가 정보를 파악해야 하는 경우 검토할 cmdlet은 에지 서버, 페더ation 및 외부 액세스가 됩니다.
  
## <a name="call-admission-control-policy"></a>통화 제어 정책
<a name="CACPolicy"> </a>

이 정책에 대한 BandwidthPolicy.ps1 참조할 수 있습니다. 통화 입장 제어 cmdlet에는 추가 정보도 있습니다.
  
## <a name="voice-routing-rules"></a>음성 라우팅 규칙
<a name="VoiceRoutingRules"> </a>

음성 라우팅을 위한 RoutingRules.ps1 스크립트가 필요합니다. 이러한 규칙을 구성할 때 사용자를 만들 때 지정할 수 있도록 전화 컨텍스트(/Location Profile 또는 /SimpleName) 및 내부/외부 영역 코드를 메모합니다. 또한 LyncPerfTool 구성(특히 PSTN-UC 및 UC-PSTN용) 중에도 필요합니다.
  
예를 들어 RoutingRules.ps1 예제에서 **New-CsDialPlan** cmdlet 호출의 SimpleName 매개 변수를 다음 UserProfileGenerator.exe.
  
![비즈니스용 Skype 로드 구성 도구, 음성 시나리오 탭, 대화에 대한 고급 설정](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
자세한 내용은 cmdlet의 Enterprise Voice 수 있습니다.
  
## <a name="conference-attendant-application"></a>회의 참석자 응용 프로그램
<a name="ConfAttendantApp"> </a>

먼저 스크립트를 ConferenceAutoAttendantConfiguration.ps1 검토합니다. 아래와 같은 구성 생성을 위해 LyncPerfTool 구성 도구에 입력할 수 있도록 ConferencingAutoAttendant 전화 번호(기본적으로 11211111111)를 기록해 두는 것이 좋습니다.
  
![회의 부하 수준 및 전화 번호를 보여 주며 음성 시나리오 탭](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
회의 및 전화 접속 회의 cmdlet에서 더 많은 세부 정보를 찾을 수 있습니다.
  
## <a name="server-call-park-service"></a>서버 통화 파크 서비스
<a name="ServerCallParkServ"> </a>

이 설정은 기본적으로 실제로 사용하지 않도록 설정되어 있습니다. 테스트해야 CallParkConfiguration.ps1 스크립트를 검토할 수 있습니다. 또한 필요한 경우 통화 파킹 응용 프로그램 cmdlet을 체크 아웃합니다.
  
## <a name="emergency-calls"></a>긴급 통화
<a name="EmergencyCalls"> </a>

다음 단계를 수행하여 긴급 통화에 대한 스트레스 및 성능 테스트를 구성해야 합니다.
  
1. 긴급 통화에 대한 음성 경로를 설정합니다. 이 음성 RoutingRules.ps1 설정하는 방법의 예는 **"E911에서 PSTN으로** 경로" 설명 아래에서 확인할 수 있습니다.
    
    > [!CAUTION]
    > 예제 명령은 RoutingRules.ps1 911이 아닌 119를 포함하는 숫자 패턴이 있습니다. 부하 테스트 중에 911(또는 실제 로컬 긴급 번호)을 사용하여 로컬 응급 운영자에게 실수로 전화를 걸지 않도록 해야 합니다. 이 구성은 시뮬레이션 목적으로만 사용됩니다. 
  
2. 다음 그림과 같이 UserProvisioningTool의 위치 정보 서비스 구성 탭에 있는 값을 입력하여 주소를 구성합니다. 
    
     ![주소, 서브넷, 스위치 및 포트 수를 표시하는 사용자 프로비전 도구입니다.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. UserProvisioningTool에 모든 것을 입력한 후 **LIS 구성** 파일 생성 단추를 클릭합니다.
    
4. 이제 포트, 서브넷, 스위치 및 WAP(무선 액세스 지점)에 대한 CSV 파일과 스트레스 및 성능 도구용 XML 파일이 생성됩니다. LIS(위치 정보 서비스)를 구성할 때 CSV 파일을 입력에 사용할 LisConfiguration.ps1 있습니다. 이렇게하려면 스트레스 및 성능 도구 실행 파일(Locations0.xml)과 동일한 폴더로 LyncPerfTool.exe. 이렇게 하면 위치 프로필(다이얼 플랜) 시나리오를 실행할 수 있습니다.
    
## <a name="configuring-response-group-application"></a>응답 그룹 응용 프로그램 구성
<a name="ConfigResponseGroupApp"> </a>

샘플 스크립트는 ResponseGroupConfiguration.ps1. 추가 구성 세부 정보를 검토할 응답 그룹 응용 프로그램 cmdlet도 있습니다. 다음 다이어그램에는 몇 가지 구성 세부 정보가 표시됩니다.
  
![테스트할 기존 워크플로를 보여 주며 응답 그룹 구성 도구](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  


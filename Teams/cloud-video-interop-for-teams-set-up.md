---
title: 클라우드용 Cloud Video Interop Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
f1.keywords:
- NOCSH
description: 이 문서에서는 조직의 사용자를 위해 Cloud Video Interop을 계획하고 설정할 수 있는 방법을 설명합니다.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bea2f250e91b8a02cefea70db0b80fcd8cc35cce6ecb079c6417c0a6c31bc55c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322760"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>클라우드용 Cloud Video Interop Microsoft Teams

[Cloud Video Interop](cloud-video-interop.md)파트너를 선택한 후 배포를 계획하고, 프로비전 세부 정보 및 파트너 테넌트 키를 설정하고 조직의 비디오 인터프 앱에 동의해야 합니다. 다음 다이어그램에서는 프로세스를 간략하게 간략하게 설명합니다. 

![조직에서 CVI 배포](media/deploying-cvi.png)

## <a name="plan"></a>계획

조직에서 사용할 파트너 또는 Microsoft Teams 식별에 대한 자세한 내용은 클라우드 비디오 [Interop을](cloud-video-interop.md) 참조하세요. 

사용자 기반/동시/사이트 전체 사용에 대해 계획하려면: 

- 사용에 대한 배포 모델/호스팅 모델 선택
- 조직에 적합한 라이선스 계획을 선택합니다. 
- VM 용량 계획은 비디오 인프라를 호스팅하는 것입니다.

## <a name="configure"></a>구성 

Cloud Video Interop을 구성하기 위해 다음 단계를 수행합니다. 

1. 선택한 파트너/파트너(테넌트 키, appIds...)에서 구성 정보를 얻습니다. 조직에서 하나 이상의 비디오 인터프 파트너를 사용할 수 있습니다. 

2. 네트워크가 올바르게 구성되도록 합니다. 지원할 경계 네트워크 트래버스에 대한 표준 기반 비디오 방화벽을 구성합니다. 예를 들면 다음과 같습니다. 
    - Cisco VCS-e                  
    - Polycom RPAD

3. Exchange 및 OTD를 통해 통합된 회의실을 구성합니다. 대부분의 경우 환경에서 추가 릴레이를 설정하고 구성해야 합니다.


## <a name="provision"></a>프로비전
 
테넌트 키는 파트너 서비스에 대한 전화 접속입니다. 다음 예제에서는 813878896@t.plcm.vc 키입니다. 

![테넌트 키 예제](media/tenant-key-example.png) 

테넌트 키를 프로비전하려면 다음 cmdlet을 실행하고, 선택한 사용자 또는 조직 전체를 사용하여 비디오 인터팝 좌표를 사용하여 모임을 만들 수 있도록 해야 합니다.

 
- **[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft는 클라우드 비디오 Interop에 사용할 파트너를 지정할 수 있도록 지원되는 각 파트너에 대해 미리 생성된 정책을 제공합니다.

    이 cmdlet을 사용하면 조직에서 사용할 수 있는 미리 생성된 정책을 식별할 수 있습니다. cmdlet을 활용하는 하나 이상의 사용자에게 이 정책을 할당할 Grant-CsTeamsVideoInteropServicePolicy 있습니다.
 
- **[Grant-CsTeamsVideoInteropServicePolicy](/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** Grant-CsTeamsVideoInteropServicePolicy cmdlet을 사용하면 조직에서 사용할 미리 생성된 정책을 할당하거나 특정 사용자에게 정책을 할당할 수 있습니다.
 
- **[New-CsVideoInteropServiceProvider:](/powershell/module/skype/new-csvideointeropserviceprovider)** 조직에서 New-CsVideoInteropServiceProvider 지원되는 CVI 파트너에 대한 정보를 지정합니다.
 
- **[Set-CsVideoInteropServiceProvider:](/powershell/module/skype/set-csvideointeropserviceprovider)** 이 Set-CsVideoInteropServiceProvider 사용하여 조직에서 사용하는 지원되는 CVI 파트너에 대한 정보를 업데이트합니다.
 
- **[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider):** 조직 내에서 사용하도록 구성된 모든 공급자를 얻습니다.
 
- **[Remove-CsVideoInteropServiceProvider:](/powershell/module/skype/remove-csvideointeropserviceprovider)** 더 Remove-CsVideoInteropServiceProvider 더 이상 사용하지 않습니다 공급자에 대한 모든 공급자 정보를 제거하려면 이 기능을 사용합니다.  
 
## <a name="consent"></a>동의

파트너 서비스를 통해 조직 모임에 참가하려면 VTC(비디오 원격 회의 디바이스)에 대한 사용 권한 동의를 제공해야 합니다. 이 동의 링크는 파트너가 제공합니다.  
 
이러한 단계가 완료되면 위의 권한 부여 cmdlet을 통해 개별적으로 사용하도록 설정되어 있는 사용자 또는 테넌트가 활성화된 경우 조직의 모든 사용자가 예약하는 모든 Teams VTC 좌표가 표시됩니다. 모든 VTC는 해당 좌표를 통해 이러한 모임에 참가할 수 있습니다.


|이름|애플리케이션 사용 권한 간략한 설명| 설명|
|--|--|---|
|Calls.JoinGroupCall.All|그룹 통화 및 모임에 앱으로 참가(미리 보기)|앱에서 로그인한 사용자 없이 조직에서 그룹 호출 및 예약된 모임에 참가할 수 있습니다.  앱이 테넌트의 모임에 디렉터리 사용자의 권한과 조인됩니다.|
|Calls.JoinGroupCallasGuest.All|게스트 사용자로 그룹 통화 및 모임 참가(미리 보기)|앱에서 로그인한 사용자 없이 조직에서 그룹 통화 및 예약된 모임에 익명으로 참가할 수 있습니다.  앱이 테넌트의 모임에 게스트로 참가됩니다.|
|Calls.AccessMedia.All|앱으로 통화에서 미디어 스트림에 액세스(미리 보기)|앱에서 로그인한 사용자 없이 통화에서 미디어 스트림에 직접 액세스할 수 있습니다.|
|OnlineMeetings.Read.All|온라인 모임 세부 정보 읽기(미리 보기)|앱에서 로그인한 사용자 없이 조직에서 온라인 모임 세부 정보를 읽을 수 있습니다.|

## <a name="schedule"></a>일정

다음으로, Teams 인터프 좌표로 모임을 예약합니다. 사용 가능한 사용자는 다음을 통해 팀 모임을 예약할 수 있습니다.
- [Teams 모임 추가 기능의 Outlook](teams-add-in-for-outlook.md)
- Teams 데스크톱 및 모바일


## <a name="join"></a>조인

다음 방법으로 VTC Teams 모임에 참가할 수 있습니다.
 
- IVR(대화형 음성 응답)
    - 파트너의 IVR에 전화 접속할 수 tenantkey@domain. 
    - 파트너 IVR에 있는 경우 VTC conferenceId에 입력하라는 메시지가 표시되어 모임에 Teams 합니다.
- 직접 다이얼
    - 테넌트키의 Teams 직접 다이얼 기능을 사용하여 파트너의 IVR과 상호 작용하지 않고도 모임에 직접 전화를 걸 수 있습니다. VTC ConferenceId@domain.
- 원터치 다이얼
    - 통합된 Teams 있는 경우 파트너가 제공하는 원터치 다이얼 기능을 사용할 수 있습니다(다이얼 문자열을 입력할 필요 없이).

마지막으로, Teams, 비디오 및 콘텐츠 공유를 사용하여 모임의 사용자와 대화합니다.
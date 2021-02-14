---
title: Microsoft Teams용 클라우드 비디오 Interop 설정
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
description: 이 문서에서는 조직의 사용자를 위해 Cloud Video Interop을 계획하고 설정하는 방법을 설명하고 있습니다.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1f45967b3e2737f6e2df74c505932ea69afe37f
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582635"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Microsoft Teams용 클라우드 비디오 Interop 설정

[Cloud Video Interop](cloud-video-interop.md)파트너를 선택한 후 배포를 계획하고, 프로비전 세부 정보 및 파트너 테넌트 키를 설정하고, 조직의 Video Interop 앱에 동의해야 합니다. 다음 다이어그램에서는 프로세스를 간략하게 설명하고 있습니다. 

![조직에서 CVI 배포](media/deploying-cvi.png)

## <a name="plan"></a>계획

조직에서 사용할 파트너 또는 파트너를 식별하는 데 대한 자세한 내용은 Microsoft Teams용 클라우드 비디오 [Interop을](cloud-video-interop.md) 참조하세요. 

사용자 기반/동시/사이트 전체 사용에 대해 계획하려면: 

- 사용할 배포 모델/호스트된 모델 선택
- 조직에 적합한 라이선스 계획을 선택합니다. 
- VM 용량 계획은 비디오 인프라를 호스팅하는 것입니다.

## <a name="configure"></a>구성 

Cloud Video Interop을 구성하기 위해 다음 단계를 수행합니다. 

1. 선택한 파트너/파트너(테넌트 키, appIds...)에서 구성 정보를 얻습니다. 조직에서 하나 이상의 비디오 Interop 파트너를 사용할 수 있습니다. 

2. 네트워크가 올바르게 구성되어 있는지 확인합니다. 지원할 경계 네트워크 트래버스에 대한 표준 기반 비디오 방화벽을 구성합니다. 예를 들면 다음과 같습니다. 
    - Cisco VCS-e                  
    - Polycom RPAD

3. Exchange 및 OTD를 통해 통합된 회의실을 구성합니다. 대부분의 경우 사용자 환경에서 추가 릴레이를 설정하고 구성해야 합니다.


## <a name="provision"></a>프로비전
 
테넌트 키는 파트너 서비스에 대한 전화 접속입니다. 다음 예제에서는 813878896@t.plcm.vc 키입니다. 

![테넌트 키 예제](media/tenant-key-example.png) 

테넌트 키를 프로비전하려면 다음 cmdlet을 실행하고, 선택된 사용자 또는 전체 조직이 비디오 interop 좌표를 사용하여 모임을 만들 수 있도록 해야 합니다.

 
- **[Get-CsTeamsVideoInteropServicepolicy:](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy)** Microsoft는 지원되는 각 파트너에 대해 클라우드 비디오 interop에 사용할 파트너를 지정하는 미리 구성된 정책을 제공합니다.

    이 cmdlet을 사용하면 조직에서 사용할 수 있는 미리 생성된 정책을 식별할 수 있습니다. 이 정책은 cmdlet을 활용하는 하나 이상의 사용자에게 Grant-CsTeamsVideoInteropServicePolicy 있습니다.
 
- **[Grant-CsTeamsVideoInteropServicePolicy:](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy)** Grant-CsTeamsVideoInteropServicePolicy cmdlet을 사용하면 조직에서 사용할 미리 생성된 정책을 할당하거나 특정 사용자에게 정책을 할당할 수 있습니다.
 
- **[New-CsVideoInteropServiceProvider:](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider)** 이 New-CsVideoInteropServiceProvider 사용하여 조직에서 사용할 지원되는 CVI 파트너에 대한 정보를 지정합니다.
 
- **[Set-CsVideoInteropServiceProvider:](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider)** 이 Set-CsVideoInteropServiceProvider 사용하여 조직에서 사용하는 지원되는 CVI 파트너에 대한 정보를 업데이트합니다.
 
- **[Get-CsVideoInteropServiceProvider:](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider)** 조직 내에서 사용하도록 구성된 모든 공급자를 얻습니다.
 
- **[Remove-CsVideoInteropServiceProvider:](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider)** 조직에서 Remove-CsVideoInteropServiceProvider 공급자에 대한 모든 공급자 정보를 제거하려면 다음을 사용합니다.  
 
## <a name="consent"></a>동의

파트너 서비스를 통해 조직 모임에 참가하려면 VTC(비디오 원격 회의 디바이스)에 대한 사용 권한 동의를 제공해야 합니다. 이 동의 링크는 파트너가 제공합니다.  
 
이러한 단계가 완료되면 위의 권한 부여 cmdlet을 통해 개별적으로 활성화된 사용자 또는 테넌트가 활성화된 경우 조직의 모든 사용자가 예약하는 모든 Teams 모임에서 VTC를 조정합니다. 모든 VTC는 해당 좌표를 통해 이러한 모임에 참가할 수 있습니다.


|이름|애플리케이션 사용 권한 간략한 설명| 설명|
|--|--|---|
|Calls.JoinGroupCall.All|그룹 통화 및 모임을 앱으로 참가(미리 보기)|앱이 로그인한 사용자 없이 조직에서 그룹 통화 및 예약된 모임에 참가할 수 있도록 허용합니다.  앱이 테넌트의 모임에 디렉터리 사용자의 권한과 조인됩니다.|
|Calls.JoinGroupCallasGuest.All|게스트 사용자로 그룹 통화 및 모임 참가(미리 보기)|앱이 로그인한 사용자 없이 조직에서 그룹 통화 및 예약된 모임에 익명으로 참가할 수 있도록 허용합니다.  앱이 테넌트의 모임에 게스트로 참가됩니다.|
|Calls.AccessMedia.All|앱으로 통화에서 미디어 스트림 액세스(미리 보기)|앱에서 로그인한 사용자 없이 통화 중 미디어 스트림에 직접 액세스할 수 있습니다.|
|OnlineMeetings.Read.All|온라인 모임 세부 정보 읽기(미리 보기)|앱에서 로그인한 사용자 없이 조직의 온라인 모임 세부 정보를 읽을 수 있습니다.|

## <a name="schedule"></a>일정

다음으로, 비디오 interop 좌표를 통해 Teams 모임을 예약합니다. 활성화된 사용자는 다음을 통해 팀 모임을 예약할 수 있습니다.
- [Outlook용 Teams 모임 추가 기능](teams-add-in-for-outlook.md)
- Teams 클라이언트 데스크톱 및 모바일


## <a name="join"></a>조인

다음과 같은 방법으로 VTC 디바이스로 Teams 모임에 참가할 수 있습니다.
 
- IVR(대화형 음성 응답)
    - 다음을 사용하여 파트너의 IVR에 tenantkey@domain. 
    - 파트너 IVR에 있는 경우 VTC conferenceId를 입력하라는 메시지가 표시될 수 있습니다. 그러면 Teams 모임에 연결됩니다.
- 직접 전화 걸기
    - Tenantkey의 전체 문자열을 사용하여 직접 전화 걸기 기능을 사용하여 파트너의 IVR과 상호 작용하지 않고 Teams 모임에 직접 전화를 걸 수 있습니다. VTC ConferenceId@domain.
- 원터치 다이얼
    - 통합 Teams 방이 있는 경우 전화 문자열을 입력할 필요 없이 파트너가 제공하는 원터치 다이얼 기능을 사용할 수 있습니다.

마지막으로 오디오, 비디오 및 콘텐츠 공유를 사용하여 모임에 Teams 사용자와 참여합니다. 

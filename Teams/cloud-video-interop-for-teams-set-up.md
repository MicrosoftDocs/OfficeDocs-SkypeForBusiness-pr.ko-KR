---
title: Microsoft 팀을 위한 클라우드 비디오 Interop 설정
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
description: 이 문서에서는 조직의 사용자를 위해 클라우드 비디오 Interop를 계획 하 고 설정 하는 방법에 대해 설명 합니다.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a94292719f8f93b818cbc52dd312859611940e3b
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516664"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Microsoft 팀을 위한 클라우드 비디오 Interop 설정

[클라우드 비디오 Interop 파트너를 선택한](cloud-video-interop.md)후에는 배포를 계획 하 고, 프로 비전 세부 정보 및 파트너 테 넌 트 키를 사용 하 여 설정 하 고, 조직의 비디오 Interop 앱에 대 한 동의를 받아야 합니다. 다음 다이어그램은 프로세스를 대략적으로 보여 줍니다. 

![조직에 CVI 배포](media/deploying-cvi.png)

## <a name="plan"></a>계획

조직에서 사용할 파트너 또는 파트너를 식별 하는 방법에 대 한 자세한 내용은 [Microsoft 팀의 클라우드 비디오 Interop](cloud-video-interop.md) 를 참조 하세요. 

사용자 기반/동시/사이트 전체 사용을 계획 하려면 다음을 수행 합니다. 

- 사용할 배포 모델/호스팅 모델 선택
- 조직에 가장 적합 한 라이선스 계획을 선택 합니다. 
- Vm 용량에 대 한 계획은 비디오 인프라를 호스트 하는 것입니다.

## <a name="configure"></a>구성할 

클라우드 비디오 Interop를 구성 하려면 다음 단계를 따릅니다. 

1. 선택한 파트너/파트너 (테 넌 트 키, appIds)에서 구성 정보를 가져옵니다. 조직에서 하나 이상의 비디오 interop 파트너를 사용할 수 있습니다. 

2. 네트워크가 올바르게 구성 되어 있는지 확인 합니다. 경계 네트워크 순회 지원에 맞게 표준 기반 비디오 방화벽을 구성 합니다. 예를 들면 다음과 같습니다. 
    - Cisco VCS-e                  
    - Polycom RPAD

3. Exchange 및 기타 d를 사용 하 여 통합 채팅방을 구성 합니다. 대부분의 경우에는 환경에서 추가 릴레이가 설정 및 구성 되어야 합니다.


## <a name="provision"></a>공급
 
테 넌 트 키는 파트너 서비스에 대 한 전화 접속으로 보내집니다. 다음 예제에서 813878896@t.plcm.vc는 테 넌 트 키입니다. 

![테 넌 트 키 예제](media/tenant-key-example.png) 

테 넌 트 키를 프로 비전 하려면 다음 cmdlet을 실행 해야 하며 사용자 또는 전체 조직을 선택 하 여 비디오 interop 좌표가 있는 모임을 만들 수도 있습니다.

 
- ** [Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft는 지원 되는 각 파트너에 대해 미리 구성 된 정책을 제공 하 여 클라우드 비디오 interop에 사용할 파트너를 지정할 수 있도록 합니다.

    이 cmdlet을 사용 하 여 조직에서 사용할 수 있는 미리 구성 된 정책을 식별할 수 있습니다. CsTeamsVideoInteropServicePolicy cmdlet을 활용 하는 하나 이상의 사용자에 게이 정책을 할당할 수 있습니다.
 
- ** [허가-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** CsTeamsVideoInteropServicePolicy cmdlet을 사용 하 여 조직에서 사용할 미리 생성 된 정책을 할당 하거나 특정 사용자에 게 정책을 할당할 수 있습니다.
 
- ** [New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** CsVideoInteropServiceProvider를 사용 하 여 조직에서 사용 하려는 지원 되는 CVI 파트너에 대 한 정보를 지정 합니다.
 
- ** [Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** CsVideoInteropServiceProvider를 사용 하 여 조직에서 사용 하는 지원 되는 CVI 파트너에 대 한 정보를 업데이트 합니다.
 
- ** [Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** 조직 내에서 사용 하도록 구성 된 모든 공급자를 가져옵니다.
 
- ** [제거-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** CsVideoInteropServiceProvider를 사용 하 여 조직에서 더 이상 사용 하지 않는 공급자에 대 한 모든 공급자 정보를 제거 합니다.  
 
## <a name="consent"></a>서명

파트너 서비스를 통해 조직 모임에 참가 하려면 VTCs (비디오 teleconferencing 장치)에 대 한 사용 권한 동의를 제공 해야 합니다. 이 동의 링크는 파트너도 제공 합니다.  
 
이러한 단계가 완료 되 면 위의 부여 cmdlet을 통해 개별적으로 사용 하도록 설정 된 사용자 또는 테 넌 트가 설정 된 경우 조직의 모든 사용자가 예약 하는 모든 팀 모임에서 VTC 좌표를 갖게 됩니다. 모든 VTC는 이러한 좌표를 통해 이러한 모임에 참가할 수 있습니다.


|이름|응용 프로그램 권한 간단한 설명| 설명|
|--|--|---|
|-JoinGroupCall을 호출 합니다. 모든|그룹 통화 및 모임을 앱으로 참가 (미리 보기)|앱이 로그인 한 사용자 없이 조직의 그룹 통화 및 예약 된 모임을 참가할 수 있도록 허용 합니다.  앱이 테 넌 트에서 모임에 대 한 디렉터리 사용자의 권한과 연결 됩니다.|
|JoinGroupCallasGuest를 호출 합니다. 모든|게스트 사용자로 그룹 통화 및 모임 참가 (미리 보기)|앱이 로그인 한 사용자 없이 조직의 그룹 통화 및 예약 된 모임을 익명으로 참가할 수 있도록 허용 합니다.  앱이 테 넌 트에서 모임에 게스트로 참가 합니다.|
|AccessMedia를 호출 합니다. 모든|앱으로 호출에서 미디어 스트림 액세스 (미리 보기)|앱에서 로그인 한 사용자 없이 호출의 미디어 스트림에 직접 액세스할 수 있도록 허용 합니다.|
|OnlineMeetings를 참조 하세요. 모든|온라인 모임 세부 정보 읽기 (미리 보기)|앱에서 로그인 한 사용자 없이 조직의 온라인 모임 세부 정보를 읽을 수 있도록 허용 합니다.|

## <a name="schedule"></a>따라

다음으로, 비디오 interop 좌표로 팀 모임을 예약 합니다. 사용 하도록 설정 된 사용자는 다음을 통해 팀의 모임을 예약할 수 있습니다.
- [Outlook 용 팀 모임 추가 기능](teams-add-in-for-outlook.md)
- 팀 클라이언트 데스크톱 및 모바일


## <a name="join"></a>합류

다음과 같은 방법으로 팀 모임에 VTC 장치를 사용 하 여 참가할 수 있습니다.
 
- IVR (대화형 음성 응답)
    - Tenantkey @ domain을 사용 하 여 파트너의 IVR에 전화를 걸 수 있습니다. 
    - 파트너 IVR에 속한 경우 VTC conferenceId을 입력 하 라는 메시지가 표시 되 고 팀 회의에 연결 됩니다.
- 다이렉트 전화 접속
    - Tenantkey의 전체 문자열을 사용 하 여 직접 전화 접속 기능을 사용 하 여 파트너의 IVR과 상호 작용 하지 않고 팀 모임에 직접 전화를 걸 수 있습니다. VTC ConferenceId @ domain.
- 한 번 터치 다이얼
    - 통합 된 팀 객실이 있는 경우에는 해당 파트너가 제공 하는 원터치 전화 접속 기능을 사용할 수 있습니다 (다이얼 문자열을 입력할 필요는 없음).

마지막으로, 오디오, 비디오, 콘텐츠 공유를 사용 하 여 모임에서 팀 사용자에 게 참여 합니다. 

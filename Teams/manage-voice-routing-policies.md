---
title: Microsoft 팀에서 음성 라우팅 정책 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords: ''
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 음성 라우팅 정책을 만들고 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: e3dc656043776d3a2f0e5b37a0c35ab98b7c03f7
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938129"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a>Microsoft 팀에서 음성 라우팅 정책 관리

조직에 [직접 전화 시스템 라우팅을](direct-routing-landing-page.md) 배포한 경우 비즈니스용 Skype Online 사용자가 온-프레미스 전화 통신 인프라를 사용 하 여 PSTN (공개 교환 전화 네트워크)에 전화를 걸거나 받을 수 있도록 음성 라우팅 정책을 사용 합니다.

음성 라우팅 정책은 PSTN 사용 레코드에 대 한 컨테이너입니다. **Voice**  >  Microsoft 팀 관리 센터에서 음성**음성 라우팅 정책** 으로 가거나 Windows PowerShell을 사용 하 여 음성 라우팅 정책을 만들고 관리 합니다.

전역 (조직 차원의 기본) 정책을 사용 하거나 사용자 지정 정책을 만들고 할당할 수 있습니다. 사용자 지정 정책을 만들고 지정 하지 않으면 사용자가 자동으로 전역 정책을 가져옵니다. 전역 정책의 설정은 편집할 수 있지만 이름을 바꾸거나 삭제할 수 없다는 점에 유의 하세요.

사용자에 게 음성 라우팅 정책을 할당 하 여 팀에서 PSTN 통화를 할 수는 없다는 것이 중요 합니다. 또한 사용자가 전화 시스템 다이렉트 라우팅과 다른 구성 단계를 완료 하도록 설정 해야 합니다. 자세히 알아보려면 [직접 라우팅 구성을](direct-routing-configure.md)참조 하세요.

## <a name="create-a-custom-voice-routing-policy"></a>사용자 지정 음성 라우팅 정책 만들기

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **음성 라우팅 정책**으로 이동한 다음 **추가**를 클릭 합니다.<br>
    ![Microsoft 팀 관리 센터의 음성 라우팅 정책 추가 페이지 스크린샷](media/manage-voice-routing-policies.png) 
2. 정책의 이름과 설명을 입력합니다.
3. **Pstn 사용 레코드**에서 **pstn 사용량 추가**를 클릭 한 다음 추가 하려는 레코드를 선택 합니다. 새 PSTN 사용 레코드를 만들어야 할 경우 **추가**를 클릭 합니다.
4. 여러 PSTN 사용 레코드를 추가한 경우 원하는 순서 대로 정렬 합니다.
5. 작업을 마치면 **적용**을 클릭 합니다.
6. **저장**을 클릭합니다.

### <a name="using-powershell"></a>PowerShell 사용

[새로운 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)을 참조 하세요.

## <a name="edit-a-voice-routing-policy"></a>음성 라우팅 정책 편집

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

만든 전역 정책 또는 사용자 지정 정책을 편집할 수 있습니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **음성 라우팅 정책**으로 이동 합니다.
2. 정책 이름 왼쪽을 클릭 하 여 정책을 선택한 다음 **편집**을 클릭 합니다.
3. **PSTN 사용 레코드 추가/제거**를 클릭 하 고 원하는 대로 변경한 다음 **저장**을 클릭 합니다.

### <a name="using-powershell"></a>PowerShell 사용

[Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy)를 참조 하세요.

## <a name="assign-a-custom-voice-routing-policy-to-users"></a>사용자에 게 사용자 지정 음성 라우팅 정책 지정

[!INCLUDE [assign-policy](includes/assign-policy.md)]

[허용-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)을 참조 하세요.

## <a name="related-topics"></a>관련 항목

[Teams PowerShell 개요](teams-powershell-overview.md)

[다이렉트 라우팅에 대 한 음성 라우팅 구성](direct-routing-voice-routing.md)

[직접 라우팅에 위치 기반 라우팅 사용](location-based-routing-enable.md)

[팀에서 사용자에 게 정책 할당](assign-policies.md)

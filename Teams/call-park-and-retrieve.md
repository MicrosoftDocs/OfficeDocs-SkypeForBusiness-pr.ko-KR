---
title: 통화 공원 및 Microsoft 팀에서 검색
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 04/12/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: 통화 공원을 사용 하 고 클라우드의 팀 서비스에서 통화를 보류 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 2420652fc908a943e798ac1acade53eca4c5b55f
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905040"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>통화 공원 및 Microsoft 팀에서 검색

통화 공원 및 검색은 사용자가 클라우드의 팀 서비스에서 통화를 대기 상태로 설정할 수 있는 기능입니다. 통화가 파킹 되 면 서비스에서 호출 검색에 대 한 고유 코드를 생성 합니다. 통화를 대기 하거나 다른 사용자가 해당 코드와 지원 되는 앱 또는 장치를 사용 하 여 통화를 검색할 수 있습니다. 

통화 공원 사용에 대 한 일반적인 시나리오는 다음과 같습니다. 

- Receptionist는 공장에서 작업 하는 사람에 게 전화를 공원 합니다. 그런 다음 receptionist는 공용 주소 시스템을 통해 통화와 코드 번호를 알립니다. 전화를 받은 사용자는 공장 바닥에서 팀 전화를 선택 하 고 통화를 검색 하는 코드를 입력할 수 있습니다.
- 디바이스 배터리의 전원이 부족 하 여 모바일 장치에서 통화를 공원. 그러면 사용자는 팀의 일반 전화기에서 통화를 검색 하는 코드를 입력할 수 있습니다.
- 지원 담당자는 고객에 게 전화를 걸고 전문가를 위해 팀 채널에 알림을 보내 고객에 게 도움을 줍니다. 전문가는 전화를 검색 하기 위해 팀 클라이언트에 코드를 입력 합니다.

> [!IMPORTANT]
> 이 기능은 팀 전용 배포 모드 에서만 사용할 수 있습니다. 팀 배포 모드에 대 한 자세한 내용은 [Microsoft 팀 및 비즈니스용 Skype 공존 및 상호 운용성 이해](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 를 참조 하세요.

## <a name="license-required"></a>라이선스 필요

통화를 대기 하 고 검색 하려면 사용자가 엔터프라이즈 음성 사용자 여야 하 고 관리자가 사용자에 게 통화 공원 정책을 부여 해야 합니다. 라이선스 모델에 대 한 자세한 내용은 [Microsoft 팀 용 Office 365 라이선스](office-365-licensing.md)를 참조 하세요.

## <a name="call-park-and-retrieve-feature-availability"></a>통화 대기 및 기능 가용성 검색

통화 공원 및 검색은 현재 다음 클라이언트 및 장치에서 지원 됩니다. (팀 전용 모드에서는 PSTN 연결 여부에 관계 없이 지원 됩니다.)

| 기능 | 팀 데스크톱 | 팀 Mac 앱 | 팀 웹 앱 (Edge) |팀 모바일 iOS/Android 앱 | 팀 IP 전화 | 비즈니스용 Skype IP 전화 |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| 통화 파킹 | 예 | 예 | 예 | 예 | 개봉박두| 아니요 |
| 파킹 된 통화 검색 | 예 | 예 | 예 | 예 | 개봉박두| 아니요 |
| 통화 링 뒤로 검색 | 예 | 예 | 예 | 예 | 개봉박두| 아니요 |

## <a name="configuring-call-park-and-retrieve"></a>통화 공원 구성 및 검색

관리자만 통화 대기를 구성 하 고 검색을 할 수 있으며 기본적으로이 기능은 비활성화 되어 있습니다. 사용자에 대해이 기능을 사용 하도록 설정 하 고 통화 공원 정책을 사용 하 여 사용자 그룹을 만들 수 있습니다. 사용자 집합에 같은 정책을 적용 하는 경우에는 서로 간에 전화를 걸고 검색할 수 있습니다. 사용자에 대 한 통화 공원를 구성 하 고 통화 공원 사용자 그룹을 만들려면 아래 [통화 공원 할당 정책](#assign-a-call-park-policy) 절차를 따르세요.

통화 공원 및 검색 기능을 사용 하는 방법에 대 한 자세한 내용은 [팀에서 통화](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)대기를 참조 하세요.

### <a name="enable-a-call-park-policy"></a>통화 공원 정책 사용

통화 공원 정책을 사용 하도록 설정 하려면 다음 단계를 따르세요.

1. **Microsoft 팀 관리 센터** > **음성** > **통화 공원 정책**으로 이동 합니다.
2. **새 정책을**선택 합니다.
3. 정책 이름을 지정한 다음 **통화 대기 허용** 을 **설정**으로 전환 합니다.
4. **저장**을 선택 합니다.

### <a name="assign-a-call-park-policy"></a>통화 공원 정책 할당

한 명 이상의 사용자에 게 통화 공원 정책을 할당 하려면 다음 단계를 따르세요.

1. **Microsoft 팀 관리 센터** > **음성** > **통화 공원 정책**으로 이동 합니다.
2. 정책 이름의 왼쪽을 클릭하여 정책을 선택합니다.
3. **사용자 관리**를 선택합니다.
4. **사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 다음, **추가**를 선택하세요. 추가할 각 사용자에 대해 이 단계를 반복합니다.
5. 사용자 추가를 마쳤으면 **저장**을 선택합니다.
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a>호출 공원 구성 및 PowerShell을 사용 하 여 검색

[새 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet을 사용 하 여 통화 공원 정책을 만듭니다.

[CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet을 사용 하 여 통화 공원 정책을 부여 합니다.

다음과 같이 [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) 를 사용 하 여 기본 설정을 변경할 수 있습니다.

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a>문제 해결

사용자가 공원 또는 검색 단추를 볼 수 없는 경우: 

- 사용자가 통화 공원 정책을 사용 하도록 설정 했는지 확인 합니다. 

사용자가 전화를 검색 하 려 할 때 실패 하는 경우 다음을 확인 하세요.

- 사용자가 팀 클라이언트 또는 팀 사용 가능 장치/전화를 사용 하 고 있는지 확인
- 그룹화 – 사용자가 통화 공원 그룹의 구성원이 며,이는 같은 팀 통화 공원 정책이 할당 된 것을 기반으로 합니다. 
- 섬 모드 – 팀 섬 모드에서는 통화 공원 및 읽어들이기를 사용할 수 없습니다.
- 통화가 이미 검색 되었거나 종료 되었습니다.

## <a name="more-information"></a>추가 정보

[팀에서 통화를 파킹](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)합니다.

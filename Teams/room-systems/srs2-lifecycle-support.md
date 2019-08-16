---
title: 버전 지원
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection: M365-voice
localization_priority: Normal
description: 이 문서에서는 Microsoft 팀 대화방에 대 한 수명 지원에 대해 설명 합니다.
ms.openlocfilehash: dc4f8c0997ee64f4011aed6056be506738012639
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "36427690"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft 팀 대화방 앱 버전 지원
 
Microsoft 팀의 회의실에 대 한 업데이트를 연간 몇 회 (일반 가용성) 릴리스 날짜에서 12 개월 동안 지원 되는 상태로 릴리스할 예정입니다. 전체 12 개월 동안 기술 지원이 제공 됩니다. 그러나 지원 구조는 이제 최신 버전의 가용성에 따라 달라 지는 두 가지 개별 서비스 단계로 발전 하 고 있습니다.

**서비스 및 중요 업데이트 서비스 단계** \- 최신 버전의 Microsoft 팀 대화방을 실행할 때 보안 및 서비스 업데이트를 포함 하는 정기 업데이트를 받게 됩니다.

**보안 업데이트 (전용) 서비스 단계** \- 새 버전이 출시 된 후에는 이전 분기에 대 한 지원은 12 개월 동안의 업데이트 지원 주기 기간에 있는 나머지 12 개에 대 한 보안 업데이트만 감소 합니다.

> [!NOTE]
> 최신 버전은 항상 서비스 및 중요 업데이트 서비스 단계에 있습니다. 이는 중요 업데이트를 지 원하는 코드 오류가 발생 하는 경우 픽스를 받기 위해 최신 버전이 설치 되어 있어야 한다는 것을 의미 합니다. 지원 되는 다른 모든 버전은 보안 업데이트를 받을 수만 있습니다.

이후 버전에 대 한 12 개월 수명 주기가 만료 되거나 두 개 이상의 업데이트가 끝난 후에는 모든 지원이 종료 됩니다. 고객은 지원 되는 버전으로 업데이트 해야 합니다.

모든 릴리스는 [Microsoft 팀 대화방 릴리스 노트](srs2-release-note.md)에 나열 되어 있습니다.

# <a name="os-version-support"></a>OS 버전 지원
Microsoft 팀 대화방을 실행 하는 디바이스에 대 한 windows 10 기능 업데이트는 Windows가 릴리스를 업데이트 하는 시점부터 6 개월 동안 제공 되지 않습니다. 이 작업은 비즈니스용 Windows 업데이트 (즉, 반기 채널)와 앱 설정을 통해 Microsoft 팀 공간 장치에 대 한 특수 블록을 추가 하 여 수행 됩니다. 이 기간 동안 Microsoft는 사내와 장치 OEM 파트너를 통해 Microsoft 팀 대화방 앱 및 주변 기기와 연결 된 상태에서 새 Windows 10 기능 릴리스가 작동 하는지 확인 하는 다양 한 테스트를 수행 합니다. 이는 장치 보안, 일관 된 사용자 경험을 보장 하 고 Microsoft 팀 공간 앱을 통해 제공 되는 경험의 품질을 확인 하는 데 중요 합니다. 

이 장치에서 다운로드 하기 위해 Windows 10 기능 업데이트가 제공 되는 시간 블록에서 Microsoft 팀 대화방은 앱 지원 정책에 있는 12 개월 기간에 대 한 특정 Windows 10 기능 릴리스를 지원 합니다. Windows 10의 기능 업데이트는 6 개월 마다 제공 되므로 Microsoft 팀에는 현재 버전에 대 한 지원이 종료 되는 시간을 테스트 하기 위해 두 개 이상의 릴리스가 있음을 의미 하기도 합니다. 이는 또한 Windows 10 버전이 모든 Microsoft 팀 회의실 고객에 게 6 개월 마다 차단 해제 됨을 의미 합니다. 앱이 지속적으로 변경 되 고 차단 되지 않은 마지막 Windows 릴리스에 대해 개발 됩니다. Microsoft 팀 회의실 장치에서 발생 하는 문제에 대 한 앱 수정을 제공 하기 위해 모든 고객에 게 이러한 장치를 지원 되는 windows 버전 지침 내에서 유지 되는 최신 Windows 10 기능 업데이트로 업그레이드할 수 있도록 합니다.

따라서 Microsoft 팀 회의실 장치에는 지원 되는 최소 버전으로 시작 하는 Windows 10 버전 1709이 2019으로 필요 합니다. Windows 10 버전 1703 또는 그 이하의 시스템에는 새로운 앱 릴리스가 제공 되지 않습니다.

> [!NOTE]
> Microsoft 팀 대화방 장치가 Windows 10 OS의 다음 버전과 호환 되는 경우이 장치는 자동으로 Windows Update를 통해 다음 버전으로 업데이트 됩니다. Microsoft 팀 대화방 장치는 "받을 업데이트에 대 한 Windows 준비 수준 선택" 및 "시기 선택"을 사용 하 여 windows 10의 다음 릴리스로 수동 또는 WUFB (비즈니스용 Windows 업데이트) 그룹 정책을 업그레이드할 수 없습니다. GPO를 통해 Preview 빌드 및 기능 업데이트 수신 "옵션 이러한 그룹 정책을 사용 하도록 설정 하는 것이 Windows 10 OS 업데이트와 Microsoft 팀 대화방 앱 간의 문제를 야기할 수 있는 것으로 알려져 있습니다. 
 
<a name="See"> </a> 
## <a name="see-also"></a>참고 항목

[Microsoft 팀 대화방 도움말](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft 팀 대화방 릴리스 정보](srs2-release-note.md)

[Microsoft 팀 회의실 계획](skype-room-systems-v2-0.md)

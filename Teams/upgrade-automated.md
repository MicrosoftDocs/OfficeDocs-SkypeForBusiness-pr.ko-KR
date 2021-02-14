---
title: 자동화된 업그레이드| Skype에서 Teams로 업그레이드
author: serdarsoysal
ms.author: billkau
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: 비즈니스용 Skype에서 Teams로의 자동화된 업그레이드 개요
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b42785d4f8d765e7d9600c2e195e48d7ec60d8ba
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780657"
---
# <a name="automated-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>비즈니스용 Skype Online에서 Microsoft Teams로 자동 업그레이드

Microsoft는 중소기업이 2021년 7월 31일 서비스 사용 중지 이전에 비즈니스용 Skype Online에서 성공적으로 전환할 수 있도록 Teams에 자동 업그레이드를 제공합니다. 자동화된 업그레이드는 고객의 기술 작업 수를 줄이고 조직 준비, 사용자 인식 및 Teams 교육에 더 집중할 수 있도록 합니다.

비즈니스용 Skype에서 Microsoft Teams로 성공적으로 업그레이드하려면 기술 및 사용자 준비를 계획해야 합니다. 시작할 준비가 됐을 때 Microsoft는 [](upgrade-basic.md) 비즈니스용 Skype에서 Teams로의 성공적인 이동을 구현하기 위한 핵심 권장 활동 및 관련 리소스를 제공하는 업그레이드 작업 계획을 제공합니다.

## <a name="notifications-for-scheduled-customers"></a>예약된 고객에 대한 알림

Teams로 자동 업그레이드할 수 있는 비즈니스용 Skype Online 고객은 예약된 업그레이드 날짜 30일 전에 일련의 업그레이드 알림을 받게 됩니다. 이러한 알림은 관리  메시지 센터에서 변경 게시물에 대한 계획으로 전달되고, 전자 메일을 전역 관리자로 업그레이드하고, 앱 내 플래그를 최종 사용자에게 제공합니다.

이러한 알림은 자동화된 업그레이드의 예약된 날짜를 전달하고, Teams의 채택 및 사용을 도우기 위해 리소스 및 교육에 연결하며, 고객에게 예정된 날짜까지 업그레이드할 준비가 되지 않은 경우 자동화된 업그레이드를 30일 더 연기할 수 있는 옵션을 제공합니다.

## <a name="the-automated-upgrade-experience"></a>자동화된 업그레이드 환경

자동 업그레이드는 알림 전자 메일, 메시지 센터 및 Teams 관리 포털에서 전달되는 예약된 업그레이드 날짜에 실행됩니다. 업그레이드하는 데 약 15분이 소요되는 동안 최종 사용자가 비즈니스용 Skype Online 기능에 계속 액세스할 수 있습니다. 업그레이드가 완료된 후 비즈니스용 Skype Online의 사용자 로그아웃이 완료되면 사용자는 메시징, 모임 및 통화에 Teams만 사용할 수 있습니다.

## <a name="the-post-upgrade-experience"></a>업그레이드 후 환경

자동화된 업그레이드가 완료되면 공존 모드는 Teams로만 설정되고 Microsoft에서 다른 공존 모드로만 변경할 수 있습니다.  관리자는 업그레이드하기 전에 [Teams 전용 모드 고려](teams-only-mode-considerations.md) 사항을 검토해야 합니다. 아래 표에서는 Teams 전용 사용자 환경의 개략적인 개요를 제공합니다.


|  |  |
|---------|---------|
|**채팅 및 통화**     | <UL><LI>Teams에서 모든 통화 및 채팅이 시작 및 수신됩니다.<LI>사용자는 비즈니스용 Skype 사용자와 상호 연결(채팅/통화)할 수 있습니다.<LI>사용자는 소비자용 Skype를 사용하는 사용자와 통신할 수 없습니다.<LI>사용자가 비즈니스용 Skype에 로그인하려고 할 때 Teams로 리디렉션됩니다.      </UL>  |
|**모임**     |  <UL><LI>사용자가 Teams에서 모든 새 모임 예약(플러그 인 대체)    </UL>   |
|**마이그레이션된 데이터**     |<UL><LI>페더러드를 포함한 비즈니스용 Skype의 기존 연락처(메일 목록 없음)<LI>기존 비즈니스용 Skype 모임(프레미스 및 온라인 모두)이 Teams 모임으로 변환됩니다.</UL>         |

## <a name="postponing-your-automated-upgrade"></a>자동화된 업그레이드 연기

비즈니스용 Skype Online에서 Microsoft Teams로 성공적으로 전환하려면 조직이 Teams의 확장된 기능 및 성능을 활용할 준비가 되도록 기술 계획 및 사용자 준비가 요구됩니다. 그러나 업그레이드를 계획할 때 조직이 아직 Teams로 업그레이드할 준비가 되지 않았을 수 있습니다.

예약된 자동 Teams 업그레이드에 대한 알림을 받고 나중에 연기하려면 전역 관리자가 Teams 관리 포털에 로그인하여 연기 단추를 클릭할 수 *있습니다.* 이렇게 하면 자동화된 업그레이드 날짜 30일이 푸시됩니다. 연기 후 Teams 관리 포털을 새로 고치면 새 자동화된 업그레이드 날짜가 포함된 알림이 표시됩니다.

## <a name="requests-to-downgrade-to-skype-for-business"></a>비즈니스용 Skype로 다운그레이드 요청

테넌트가 Teams로의 업그레이드를 추가로 준비할 수 있도록 Teams에서 SfBO로의 일회성 다운그레드를 허용합니다. 다운그레이드된 테넌트는 다운그레이드 날짜로부터 60일 동안 자동 업그레이드에 다시 참여합니다.

## <a name="related-content"></a>관련 콘텐츠

- [Microsoft Teams 업그레이드 시작하기](upgrade-start-here.md)
- [비즈니스용 Skype Online 단종](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps)
- [Teams 전용 모드 고려 사항](teams-only-mode-considerations.md)


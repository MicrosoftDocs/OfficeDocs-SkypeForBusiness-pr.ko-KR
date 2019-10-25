---
title: 자동화 된 업그레이드 | Skype 비즈니스에서 팀으로 업그레이드
author: serdarsoysal
ms.author: billkau
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: 비즈니스용 Skype에서 팀으로의 자동화 된 업그레이드 개요
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4f6e994f41f44c2895d394b432b37bed617ad2eb
ms.sourcegitcommit: 70323d648e9ae3b20a710120b9dcdc452afc462b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "37698058"
---
# <a name="automated-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>비즈니스용 Skype Online에서 Microsoft 팀으로 자동 업그레이드

Microsoft는 소규모 기업을 지원 하기 위해 팀에 게 자동화 된 업그레이드를 제공 하 여 서비스의 2021 년 7 월 31 일 이전에 비즈니스용 Skype Online에서 성공적으로 전환 하도록 합니다. 자동화 된 업그레이드는 고객에 게 필요한 기술 작업 수를 줄여 주며 조직 준비, 사용자 인식, 팀 교육에 더 많은 중점을 둘 수 있도록 합니다.

비즈니스용 Skype에서 Microsoft 팀으로 성공적으로 업그레이드 하려면 기술 및 사용자 준비에 대 한 계획이 필요 합니다. 시작할 준비가 되 면 Microsoft는 비즈니스용 Skype에서 팀으로 성공적으로 이동 하는 데 도움이 되는 핵심 활동과 관련 리소스를 제공 하는 [업그레이드 작업 계획](upgrade-basic.md) 을 제시 합니다.

## <a name="notifications-for-scheduled-customers"></a>예약 된 고객에 대 한 알림

팀에 게 자동으로 업그레이드할 수 있는 비즈니스용 Skype Online 고객은 예약 된 업그레이드 날짜 이전 30 일 전에 시작 되는 일련의 업그레이드 알림을 받습니다. 이러한 알림은 관리 메시지 센터의 *변경 게시물에 대 한 계획* 으로 제공 되며, 전자 메일을 전역 관리자에 게 업그레이드 하 고, 앱에서 바로 플래그를 최종 사용자에 게 전달 합니다.

이러한 알림은 자동화 된 업그레이드의 예정 된 날짜를 전달 하 고, 팀의 채택 및 사용을 가능 하 게 하는 데 도움이 되도록 업그레이드 리소스 및 교육에 연결 되며, 고객에 게 자동 업그레이드를 연기할 수 있는 옵션을 제공 합니다 (추가 30 일). 예약 된 날짜를 기준으로 업그레이드할 준비가 되지 않은 이벤트입니다.

## <a name="the-automated-upgrade-experience"></a>자동화 된 업그레이드 환경

자동 업그레이드는 알림 전자 메일, 메시지 센터, 팀 관리자 포털 등에서 통신 하는 예약 된 업그레이드 날짜에서 실행 됩니다. 업그레이드에는 약 15 분이 소요 되며,이 경우 최종 사용자가 비즈니스용 Skype Online 기능에 계속 액세스할 수 있습니다. 업그레이드가 완료 되 고 사용자가 비즈니스용 Skype Online을 로그 아웃 한 경우 사용자는 메시징, 모임, 통화에 대해서만 팀을 사용할 수 있습니다.

## <a name="the-post-upgrade-experience"></a>업그레이드 후 환경

자동화 된 업그레이드가 완료 되 면 **공존 모드** 는 팀에만 설정 되며 Microsoft에서 다른 공존 모드로만 변경할 수 있습니다. 관리자는 업그레이드 하기 전에 [팀 전용 모드 고려 사항을](teams-only-mode-considerations.md) 검토 해야 합니다. 아래 표에는 팀 전용 사용자 환경에 대 한 개략적인 수준의 개요가 나와 있습니다.


|  |  |
|---------|---------|
|**채팅 및 통화**     | <UL><LI>팀에서 모든 통화 및 채팅을 시작 하 고 받을 수 있습니다.<LI>사용자는 비즈니스용 Skype 사용자와 상호 운용 (채팅/통화) 할 수 있습니다.<LI>사용자가 소비자 용 Skype를 사용 하는 사용자와 통신할 수 없음<LI>비즈니스용 Skype에 로그인 하려고 하면 사용자가 팀으로 리디렉션 됨      </UL>  |
|**Meeting**     |  <UL><LI>사용자가 팀에서 모든 새 모임을 예약 (플러그인이 교체 됨)    </UL>   |
|**마이그레이션된 데이터**     |<UL><LI>페더레이션 (메일 그룹 없음)이 포함 된 비즈니스용 Skype의 기존 연락처<LI>기존 비즈니스용 Skype 모임 (온-프레미스 및 online 모두)이 팀 모임으로 변환 됩니다.</UL>         |

## <a name="postponing-your-automated-upgrade"></a>자동화 된 업그레이드 연기

비즈니스용 Skype Online에서 Microsoft 팀으로 전환 하는 경우 조직에서 팀의 확장 된 기능 및 성능을 활용할 수 있도록 기술 계획과 사용자 준비가 필요 합니다. 그러나 업그레이드를 계획할 때 아직 팀으로 업그레이드할 준비가 되지 않은 조직이 있을 수 있습니다.

팀에 예정 된 자동 업그레이드에 대 한 알림을 받은 경우 이후 날짜를 연기 하려면 Office 365 전역 관리자가 팀 관리자 포털에 로그인 하 고 *연기* 단추를 클릭 합니다. 이렇게 하면 자동화 된 업그레이드 날짜 30 일이 없어집니다. 연기 후 팀 관리 포털을 새로 고치면 새 자동화 된 업그레이드 날짜를 포함 하는 알림이 표시 됩니다.

## <a name="requests-to-downgrade-to-skype-for-business"></a>비즈니스용 Skype로 다운 그레이드 요청

팀에서 SfBO으로 일회성 downgrades을 허용 하 여 테 넌 트가 팀의 업그레이드를 더 준비할 수 있도록 합니다. 다운 그레이드 된 테 넌 트가 다운 그레이드 날짜 로부터 60 일 동안 자동으로 업그레이드 되도록 다시 사용 됩니다.

## <a name="related-content"></a>관련 콘텐츠

- [Microsoft 팀 업그레이드 시작 하기](upgrade-start-here.md)
- [비즈니스용 Skype Online 만료](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps)
- [팀 전용 모드 고려 사항](teams-only-mode-considerations.md)


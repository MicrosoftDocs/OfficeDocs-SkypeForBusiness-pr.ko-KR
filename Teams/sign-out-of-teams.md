---
title: Microsoft Teams에서 로그아웃
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: sbhatta
description: Microsoft Teams에서 로그아웃하는 방법을 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.localizationpriority: high
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: ba5789dac9d54de153c6d4c712a2d68367ad79c0
ms.sourcegitcommit: 8d728ca42dc917a28b94e2de84ce4f5b2515d485
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/15/2021
ms.locfileid: "61513599"
---
# <a name="sign-out-of-microsoft-teams"></a>Microsoft Teams에서 로그아웃

채팅, 수신 전화 및 기타 활동을 계속 수신하려면 사용자가 Microsoft Teams 앱에 로그인된 상태를 유지하는 것이 좋습니다. 사용자가 다음과 같은 몇 가지 이유로 Teams 애플리케이션에서 로그아웃하려는 경우가 있음을 이해합니다.

- 하루 동안 Teams 사용을 마쳤기 때문에
- 다른 계정을 사용하려고 함
- 다른 사람과 공유하는 장치를 사용하고 있기 때문에

이러한 이유로 Teams에서는 앱에서 로그아웃하고 세션을 종료할 수 있습니다.

## <a name="account-sharing-between-apps"></a>앱 간 계정 공유

최신 운영 체제를 사용하면 장치의 여러 앱 간에 계정을 공유할 수 있습니다. 이 SSO(Single Sign-On) 디자인을 통해 사용자는 모든 단일 앱에 로그인하지 않고도 장치에서 여러 앱을 사용할 수 있습니다. Teams는 이 동작을 제어하지 않지만 이 디자인이 최종 사용자 환경에 제공하는 편리함을 활용합니다.

SSO는 로그아웃에 중요한 영향을 미칩니다. 사용자가 Teams에서 로그아웃하면 계정과 연결된 데이터가 Teams 앱에서 제거되지만 장치의 다른 앱은 계속해서 계정에 액세스할 수 있습니다. 이는 또한 사용자가 동일한 계정으로 Teams에 다시 로그인하도록 선택하는 경우 자격 증명을 다시 입력하라는 메시지가 표시되지 않을 수 있음을 의미합니다.

## <a name="sign-out-of-teams-on-desktop"></a>데스크톱의 Teams에서 로그아웃

Teams 데스크톱 클라이언트나 브라우저에서 로그아웃하려면 앱 상단에서 프로필 사진을 선택한 다음 **로그아웃** 을 선택합니다.

데스크톱 앱의 경우 작업 표시줄에서 앱 아이콘을 마우스 오른쪽 버튼으로 클릭한 다음 **로그아웃** 을 선택할 수도 있습니다.

여러 계정을 추가한 경우 각 개별 계정에서 로그아웃해야 합니다. Teams의 계정에서 로그아웃한 후 계정에 액세스하려면 다음에 앱을 실행할 때 자격 증명을 다시 입력해야 할 수 있습니다.

## <a name="sign-out-of-teams-on-mobile-devices"></a>모바일 장치에서 Teams에서 로그아웃

모바일에서는 메뉴로 이동하여 **더 보기** 메뉴를 선택한 다음 **로그아웃** 을 선택하여 Teams에서 로그아웃할 수 있습니다. 로그아웃하면 다음에 앱을 실행할 때 자격 증명을 다시 입력해야 합니다.

### <a name="global-sign-in-and-sign-out-for-frontline-workers"></a>일선 근로자를 위한 전체 로그인 및 로그아웃

Teams Android 앱은 이제 전역 로그인 및 로그아웃을 지원하여 최전방 직원에게 번거로움이 없는 로그인 및 로그아웃 환경을 제공합니다. 직원들은 공유 장치 풀에서 장치를 선택하고 근무 시간 동안 단일 로그인을 통해 "내 것으로 만들기"를 수행할 수 있습니다. 교대 근무가 끝나면 장치에서 전역 로그아웃을 수행할 수 있습니다. 이렇게 하면 장치에서 장치의 개인 정보 및 회사 정보를 모두 제거하여 장치 풀에 장치를 반환할 수 있습니다. 이 기능을 사용하려면 장치가 공유 모드에 있어야 합니다. 공유 디바이스 설정 방법에 대한 자세한 내용은 [Android](/azure/active-directory/develop/tutorial-v2-shared-device-mode#set-up-an-android-device-in-shared-mode)에서 공유 디바이스 모드를 사용하는 방법을 참조하세요.

## <a name="manual-cleanup"></a>수동 정리

드물기는 하지만 Teams가 로그아웃할 때 자체적으로 완전히 정리하지 못할 수도 있습니다. 사용자 보고서에 따르면 일반적인 원인에는 시스템에서 실행 중인 서비스에 의해 파일이 잠기는 경우가 있지만 개인의 장치 구성이나 정책 및 장치에 적용된 사용자 권한에 따라 다른 이유가 있을 수 있습니다.

이 문제의 일반적인 형태 중 하나는 Teams가 사용자 로그인을 위해 기존 계정을 자동으로 선택하려고 시도한다는 것입니다. 이와 같은 상황에서 사용자는 Teams의 로컬 캐시를 수동으로 정리할 수 있습니다. [Teams에서 로그인 또는 계정 제거](https://support.microsoft.com/office/sign-out-or-remove-an-account-from-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487?ui=en-US&rs=en-US&ad=US)에서 자세히 알아보세요.

## <a name="related-topics"></a>관련 항목

[Teams에서 로그인 또는 계정 제거](https://support.microsoft.com/office/sign-out-or-remove-an-account-from-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487?ui=en-US&rs=en-US&ad=US)

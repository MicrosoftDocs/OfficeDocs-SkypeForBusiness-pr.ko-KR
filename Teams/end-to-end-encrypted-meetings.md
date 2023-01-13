---
title: 중요한 Teams 모임에 종단 간 암호화 필요
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: Teams 모임에 엔드 투 엔드 암호화를 사용하도록 설정하는 방법을 알아봅니다.
ms.openlocfilehash: 091da268e8042707dd7e27094fde33d957a52d79
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800145"
---
# <a name="require-end-to-end-encryption-for-sensitive-teams-meetings"></a>중요한 Teams 모임에 종단 간 암호화 필요

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

엔드 투 엔드 암호화는 중간 노드의 암호 해독 기능 없이 의도한 대상에서 원본 및 암호 해독에 대한 정보 암호화입니다. Teams의 모임이 엔드 투 엔드 암호화된 경우 모임 참가자를 제외한 누구도 통신을 듣거나 볼 수 없습니다. Microsoft를 포함한 다른 당사자는 암호가 해독된 대화에 액세스할 수 없습니다.

두 당사자 간에 엔드 투 엔드 암호화 모임을 만들 수 있습니다. 당사자는 Windows 또는 Mac용 Teams 데스크톱 클라이언트의 최신 버전을 사용하거나, iOS 및 Android용 최신 업데이트를 사용하는 모바일 디바이스에 있거나, 최신 업데이트를 사용하여 Windows 디바이스의 Teams 룸 있습니다. 브라우저를 통해 참석한 모임에 대한 엔드 투 엔드 암호화는 지원되지 않습니다.

> [!Note]
> 엔드 투 엔드 모임 암호화에는 Teams Premium 필요합니다.

엔드 투 엔드 암호화를 사용하도록 설정하지 않으면 Teams는 여전히 업계 표준에 따라 암호화를 사용하여 모임을 보호합니다. 모임 중에 교환되는 데이터는 전송 중 및 휴지 상태일 때 항상 안전합니다. 자세한 내용은 [Teams에 대한 미디어 암호화](teams-security-guide.md#media-encryption)를 참조하세요.

엔드 투 엔드 암호화 모임 중에 Teams는 다음 기능을 보호합니다.

- 오디오

- 비디오

- 화면 공유.

[Microsoft 365의 암호화](/microsoft-365/compliance/encryption) 는 모임의 채팅, 파일 공유, 현재 상태 및 기타 콘텐츠를 보호합니다. 앱, 아바타, 반응, 채팅 및 Q&A는 엔드 투 엔드 암호화되지 않습니다.

엔드 투 엔드 암호화 모임 중에는 다음 기능을 사용할 수 없습니다.

- 라이브 캡션 및 전사

- 녹음/녹화

- 함께 모드, 도우미 모드, 대형 갤러리

- 소규모 회의실

조직에서 규정 준수 기록을 사용하는 경우 엔드 투 엔드 암호화를 사용할 수 없습니다. Teams에서 규정 준수 녹음을 지원하는 방법에 대한 자세한 내용은 [통화 및 모임에 대한 Teams 정책 기반 녹음 소개](teams-recording-policy.md)를 참조하세요.

## <a name="enable-end-to-end-encryption-for-meetings"></a>모임에 엔드 투 엔드 암호화 사용

기본적으로 모임에 대한 엔드 투 엔드 암호화는 사용하도록 설정되지 않습니다. Teams 관리자 향상된 암호화 정책을 사용하여 사용하도록 설정할 수 있습니다.

엔드 투 엔드 암호화를 사용하도록 설정하면 모임 이끌이는 엔드 투 엔드 암호화를 선택한 다음 모임을 만들 수 있습니다. 모임 템플릿 또는 민감도 레이블을 사용하여 엔드 투 엔드 암호화를 적용할 수도 있습니다.

모임에 엔드 투 엔드 암호화를 사용하도록 설정하려면

1. Teams 관리 센터에서 **향상된 암호화 정책을** 선택합니다.

1. 업데이트하려는 정책을 선택합니다.

1. **엔드 투 엔드 모임 암호화** 를 사용 안 됨으로 설정 **하지만 사용자는 재정의할 수 있습니다**.

1. **저장** 을 선택합니다.

## <a name="related-topics"></a>관련 주제

[세 가지 보호 계층으로 Teams 모임 구성](configure-meetings-three-tiers-protection.md)

[일대일 Microsoft Teams 통화에 엔드투엔드 암호화 사용](teams-end-to-end-encryption.md)

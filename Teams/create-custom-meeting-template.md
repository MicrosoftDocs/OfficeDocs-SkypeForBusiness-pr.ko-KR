---
title: Microsoft Teams에서 사용자 지정 모임 템플릿 만들기
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ralphmaamari
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
description: Microsoft Teams 관리자가 향상된 모임 보안 및 규정 준수를 위해 모임 이끌이 설정을 설정하거나 적용하는 사용자 지정 모임 템플릿을 만드는 방법을 알아봅니다.
ms.openlocfilehash: ec9e836474032d5bb9fde0aed6c81a231788d1bf
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800275"
---
# <a name="create-a-custom-meeting-template-in-microsoft-teams"></a>Microsoft Teams에서 사용자 지정 모임 템플릿 만들기

[!INCLUDE[Teams Premium](includes/teams-premium-ecm.md)]

Microsoft Teams 사용자 지정 모임 템플릿(Teams Premium 기능)을 사용하면 모임 이끌이가 사용할 수 있는 많은 모임 설정에 대한 값을 지정할 수 있습니다. 템플릿은 모임 이끌이가 변경할 수 있는 설정을 구성하거나 모임 이끌이가 설정을 변경할 수 없도록 설정을 잠글 수 있습니다. 사용자 지정 모임 템플릿에 대한 자세한 내용은 [Microsoft Teams의 사용자 지정 모임 템플릿 개요를 참조하세요](custom-meeting-templates-overview.md).

최대 50개의 사용자 지정 템플릿을 만들 수 있습니다. 사용자가 사용할 수 있는 템플릿을 관리하는 방법에 대한 자세한 내용은 [Microsoft Teams에서 모임](manage-meeting-templates.md) 템플릿 관리를 참조하세요.

템플릿의 각 옵션에 대해 다음을 정의할 수 있습니다.

- **기본값** - 템플릿을 사용할 때 모임에 적용되는 값입니다.
- **표시** - 모임 이끌이가 모임 옵션에서 이 설정을 볼 수 있는지 여부를 결정합니다. 
- **잠금 상태** - 모임 이끌이가 템플릿에서 설정한 설정을 변경할 수 있는지 여부를 결정합니다. 설정이 잠겨 있으면 모임 이끌이가 변경할 수 없습니다.

사용자 지정 모임 템플릿을 만들려면

1. Teams 관리 센터에서 **모임을** 확장하고 **모임 템플릿을** 선택합니다.
1. **추가** 선택
1. 템플릿의 이름과 설명을 입력합니다.
1. 이 템플릿에 사용할 설정을 선택합니다. 각 설정에 대한 설명은 아래 섹션을 참조하세요.
1. 모임 이끌이가 설정을 변경하지 못하도록 하려면 설정을 선택한 다음 **잠금** 을 선택합니다.
1. 모임 이끌이가 설정을 볼 수 없도록 하려면 설정을 선택한 다음 **숨기기** 를 선택합니다.
1. **저장** 을 선택합니다.

템플릿이 만들어지면 사용자가 사용할 수 있는 데 최대 24시간이 걸릴 수 있습니다.

#### <a name="security"></a>보안

|설정|설명|
|:------|:----------|
|민감도 레이블|모임에 사용할 모임 민감도 레이블을 지정합니다. 민감도 레이블은 템플릿의 특정 설정을 재정의할 수 있습니다.|
|누가 로비를 우회 할 수 있습니까?|로비를 우회하고 모임에 직접 참가할 수 있는 사용자를 지정합니다.|
|사람 전화 접속은 로비를 우회할 수 있습니다.|전화로 전화를 걸어 대기실을 우회하고 모임에 직접 참가할 수 있는지를 지정합니다.|
|발신자가 가입하고 나갈 때 알림|전화로 전화를 걸 때 소리를 재생하거나 모임을 나갈지 여부를 지정합니다.|
|모임 엔드 투 엔드 암호화 사용|모임에서 엔드 투 엔드 암호화를 사용할지 지정합니다. 녹음/녹화가 켜진 경우 작동하지 않습니다.|
|공유 콘텐츠에 워터마크 적용|모임의 화면에서 공유되는 콘텐츠에 워터마크가 겹쳐지는지 지정합니다.|
|모든 사용자의 비디오 피드에 워터마크 적용|모임의 참석자 비디오 피드에 워터마크가 오버레이되는지를 지정합니다.|

#### <a name="audio-and-video"></a>오디오 및 비디오

|설정|설명|
|:------|:----------|
|참석자에 대한 마이크 허용|**켜** 면 참석자가 음소거를 해제할 수 있습니다.|
|참석자를 위한 카메라 허용|**켜** 면 참석자가 카메라를 켤 수 있습니다.|

#### <a name="recording-and-transcription"></a>기록 및 전사

|설정|설명|
|:------|:----------|
|자동으로 모임 녹음/녹화|**모임이** 자동으로 기록되는 경우.|
|누가 모임을 녹음할 수 있나요?|이끌이만 또는 이끌이 및 발표자가 모임을 기록할 수 있는지 여부를 지정합니다.|

#### <a name="meeting-engagement"></a>모임 참여

|설정|설명|
|:------|:----------|
|참석자가 채팅할 수 있습니다.|모임 채팅을 사용할 수 있는지를 지정합니다. 모임 전후에 채팅을 방지하는 데 사용할 수도 있습니다.|
|참석자는 반응을 사용할 수 있습니다.|참석자가 모임에서 반응을 사용할 수 있는지를 지정합니다. 손 올리기 기능이 작동하려면 **On** 이어야 합니다.|
|Q&A 사용|참석자가 Q&A 기능을 사용하여 모임 중에 질문을 할 수 있는지를 지정합니다.|
|참석자가 보는 내용 관리|**켜** 기일 때 모임 이끌이는 다른 모임 참가자가 볼 수 있기 전에 화면에서 공유되는 콘텐츠를 미리 보고 승인할 수 있습니다.|

## <a name="related-topics"></a>관련 주제

[Microsoft Teams의 사용자 지정 모임 템플릿 개요](custom-meeting-templates-overview.md)

[Teams 모임 템플릿, 민감도 레이블 및 관리자 정책을 함께 사용](meeting-templates-sensitivity-labels-policies.md)

[세 가지 보호 계층으로 Teams 모임 구성](configure-meetings-three-tiers-protection.md)

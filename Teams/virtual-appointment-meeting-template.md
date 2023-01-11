---
title: Microsoft Teams의 가상 약속 모임 템플릿
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
searchScope:
- Microsoft Teams
audience: admin
description: 조직의 Teams 사용자에 대한 가상 약속 모임 템플릿을 관리하는 방법을 알아봅니다.
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f0d93bb05a6456499ab1c0c16070149d8cdfd949
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767629"
---
# <a name="virtual-appointment-meeting-template-in-microsoft-teams"></a>Microsoft Teams의 가상 약속 모임 템플릿

![정보 아이콘](media/info.png) **이 문서에 설명된 일부 기능에는 [Teams Premium](teams-add-on-licensing/licensing-enhance-teams.md)(미리 보기)가 필요합니다**.

## <a name="overview"></a>개요

가상 약속 템플릿은 사용자가 고객, 클라이언트 및 조직 외부의 다른 사용자와 가상 약속을 예약하는 데 사용할 수 있는 Microsoft Teams의 기본 모임 템플릿입니다. 예를 들어 이를 사용하여 인터뷰, 멘토링 세션, 재무 상담, 가상 쇼핑 경험 등을 예약하고 수행합니다.

템플릿을 사용하면 모임 이끌이가 일반적으로 제어하는 모임 설정의 값을 지정할 수 있습니다. 기본 설정을 적용하고 설정을 적용할 수 있는 유연성을 제공합니다. 모임 이끌이가 템플릿을 사용할 때 설정을 변경할 수 없도록 설정을 잠그도록 선택할 수 있습니다.

이 템플릿을 사용하면 Teams 내에서 예약된 가상 약속에 대해 조직 전체에서 일관된 환경을 사용하도록 설정하고 규정 준수 요구 사항을 적용할 수 있습니다.

이 문서에서는 Teams 관리 센터에서 가상 약속 모임 템플릿을 보고 관리하는 방법에 대한 개요를 제공합니다.

## <a name="view-or-change-virtual-appointment-meeting-template-settings"></a>가상 약속 모임 템플릿 설정 보기 또는 변경

1. Teams 관리 센터의 왼쪽 탐색 영역에서 **모임 모임** > **템플릿** 으로 이동합니다.
1. **가상 약속을** 선택한 다음 **편집** 을 선택합니다.
1. 변경하려면 옵션을 선택한 다음 원하는 설정을 구성합니다. 각 옵션에 대해 다음 설정을 정의할 수 있습니다.
    - **기본값**: 템플릿을 사용할 때 가상 약속에 적용되는 값입니다.
    - **표시 유형**: **숨기기** 또는 **표시** 를 선택하여 Teams 모임 옵션에서 모임 이끌이에게 옵션이 표시되는지 여부를 지정합니다.
    - **잠금 상태**: 모임 이끌이가 설정한 값을 변경하지 못하도록 하려면 **잠금** 을 선택합니다. 모임 이끌이가 설정한 값을 변경할 수 있도록 하려면 **잠금 해제** 를 선택합니다.
1. 변경 내용을 검토한 다음 **저장** 을 선택합니다.

## <a name="manage-the-virtual-appointment-meeting-template"></a>가상 약속 모임 템플릿 관리

Teams 관리 센터에서 모임 템플릿 정책을 사용하여 조직의 사용자가 사용할 수 있는 모임 템플릿을 제어합니다. 기본적으로 전역 정책을 사용하면 사용자가 가상 약속 템플릿 및 만든 사용자 지정 템플릿을 비롯한 모든 모임 템플릿을 보고 사용할 수 있습니다.

조직의 특정 사용자 또는 사용자 그룹에서 가상 약속 템플릿을 사용할 수 있도록 하려면 사용자 지정 모임 템플릿 정책을 만든 다음 해당 사용자 또는 그룹에 할당할 수 있습니다.

자세한 내용은 [Teams에서 모임 템플릿 관리를 참조하세요](manage-meeting-templates.md).

## <a name="user-experience"></a>사용자 환경

조직의 사용자가 모임 템플릿을 사용하여 가상 약속을 예약하는 경우 조직 외부 사용자(외부 게스트)는 **게스트로 약속 참가** 단추 및 기타 약속 세부 정보를 포함하는 맞춤형 모임 초대를 받습니다. Teams를 다운로드하고 설치할 필요 없이 이 단추를 사용하여 모든 장치에서 쉽게 조인할 수 있습니다.

일부 Teams 모임 옵션은 외부 게스트 또는 게스트 **로 약속 참가** 단추를 사용하여 참가하는 사람에게는 적용되지 않을 수 있습니다. 게스트 참가에 대해 지원되는 모임 옵션은 다음과 같습니다.

- **로비를 우회할 수 있는 사용자**: **모든 사용자** 설정을 사용하면 외부 게스트가 로비를 우회할 수 있습니다.
- **공동 이끌이 선택**
- **자동으로 기록**
- **모임 채팅 허용: 모임** 전, 도중 및 후에 모임 채팅을 방지하려면 **사용 안** 함으로 설정합니다.

조직 내의 사람 모임 초대를 받고 약속이 Teams 및 Outlook 일정에 표시되며 다른 Teams 모임과 마찬가지로 쉽게 참가할 수 있습니다. 모든 Teams 모임 옵션은 모임 초대 또는 Teams 또는 Outlook 일정에서 Teams 모임 링크를 사용하여 참가하는 참석자에게 적용됩니다.

가상 약속 모임 템플릿 및 사용자 환경을 사용하는 방법에 대한 자세한 내용은 [Teams 모임 템플릿을 사용하여 가상 약속 만들기를 참조하세요](https://support.microsoft.com/office/6a9e8cbb-c0ed-4598-851e-3b1750a4a747).

## <a name="related-articles"></a>관련 기사

- [Teams의 사용자 지정 모임 템플릿 개요](custom-meeting-templates-overview.md)

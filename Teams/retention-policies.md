---
title: Microsoft Teams에 대한 보존 정책 관리
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Microsoft Teams의 보존 정책을 사용하여 내부 정책, 산업 규정 또는 법적 요구 사항을 준수하고 책임으로 간주되거나 법적 비즈니스 가치가 없는 메시지를 삭제하는 데 필요한 메시지를 보관합니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9422fd2b47ac3d460ee10e8933c45964d78282c1
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460658"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>Microsoft Teams에 대한 보존 정책 관리

> [!NOTE]
> 보존 정책에 의해 채팅 또는 메시지가 삭제된 메시지가 Teams에 표시되면 보존 정책에 대한 Teams 메시지를 [참조하세요.](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)
> 
> 이 페이지의 정보는 이러한 보존 정책을 관리하는 IT 관리자를 위한 정보입니다.

Microsoft 365의 보존 정책 및 보존 레이블을 사용하면 조직의 정보를 보다 효과적으로 관리할 수 있습니다. 조직의 내부 정책, 산업 규정 또는 법적 요구 사항을 준수하는 데 필요한 데이터를 유지하도록 보존 설정을 구성할 수 있습니다. 책임으로 간주되는 데이터, 더 이상 보관할 필요 없음 또는 법적 또는 비즈니스 가치가 없는 데이터를 삭제하도록 보존 설정을 구성할 수도 있습니다.

Teams는 채팅 및 채널 메시지에 대한 보존 정책을 지원하기 때문에 관리자는 이 데이터를 보존하거나 삭제하거나 특정 기간 동안 보존할지 여부를 사전적으로 결정할 수 있습니다. Teams 보존 정책을 전체 조직 또는 특정 사용자 및 팀에 적용할 수 있습니다. 보존 레이블은 Teams에 지원되지 않습니다.

보존에 대해 자세히 알아보고 Microsoft 365의 다른 워크로드에 보존 정책 또는 보존 레이블을 사용하여 보존 설정을 적용할 수 있는 방법에 대한 자세한 내용은 보존 정책 및 보존 레이블에 대한 자세한 내용을 [참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/retention)

Teams에 대한 보존 정책에 대한 최소 라이선스 요구 사항은 Microsoft 365 E3입니다. 라이선스에 대한 자세한 내용은 [Microsoft Teams 서비스 설명 을 참조하세요.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="how-teams-retentiondeletion-policies-work"></a>Teams 보존/삭제 정책 작동 방식

Teams 채팅 메시지는 두 위치에 저장됩니다. 기본 복사본은 컴파일 정책에 사용되는 보조 복사본인 Azure에 저장되고 채팅에 포함된 각 사용자의 Exchange 온라인 사서함에 숨겨진 폴더에 저장되고 Teams 채널 메시지는 팀의 그룹 사서함의 유사한 숨겨진 폴더에 저장됩니다. 채팅 메시지 삭제 정책이 사용자 또는 팀에 적용되면 보조 복사본이 먼저 삭제되고 기본 복사본이 뒤따라 삭제됩니다. eDiscovery 또는 Teams 검색은 보조 복사본에 저장된 메시지를 기반으로 하여 보조 복사본을 삭제하면 메시지를 검색할 수 없습니다. 

채팅 메시지 보존 포일시가 사용자 또는 팀에 적용되고 메시지가 삭제된 경우(다른 삭제 정책 또는 사용자 자체로 인해) 주 복사본이 삭제되면 Teams 클라이언트가 메시지가 사라지는 것을 볼 수 있지만 보조 복사본은 **Exchange** 복구 가능한 항목 폴더의 하위 폴더인 **기재홀드라는** 숨겨진 폴더로 자동으로 이동됩니다. 이러한 메시지가 기재 홀드 폴더에서 영구적으로 삭제될 때까지 eDiscovery 도구로 검색할 수 있습니다.

Teams 보존 정책에 포함 및 제외되는 내용 및 정책 구성에 따라 이러한 정책이 작동하는 방법에 대한 자세한 내용은 Microsoft Teams 보존에 대한 자세한 내용을 [참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)

> [!NOTE]
> 이 페이지에서는 보존 정책이 메시지를 삭제하는 경우 지연이 표시될 수 있는 이유를 설명합니다. 예를 들어 보존 정책에서 구성한 만료 기간이 지난 후 최대 7일 후에 메시지가 표시될 수 있습니다.

보존 설정이 다른 여러 Teams 보존 정책을 설정한 경우 보존 원칙은 충돌을 해결합니다. 예를 들면 다음과 같습니다.
- 동일한 콘텐츠를 유지하거나 삭제하는 사이에 충돌이 있는 경우 콘텐츠는 항상 유지됩니다.
- 동일한 콘텐츠를 유지하는 기간에 충돌이 있는 경우 가장 긴 보존 기간 동안 유지됩니다.

이러한 보존 원칙은 Teams에 대한 여러 보존 정책이 있을 때 발생할 수 있는 대부분의 충돌을 해결하지만 자세한 내용은 보존 원칙 또는 우선 순위를 [참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>Teams에 보존 정책을 사용하는 시기

대부분의 경우 조직은 비공개 채팅 데이터를 일반적으로 프로젝트 관련 대화가 주를 이루는 채널 메시지보다 더 많은 책임으로 간주합니다.

비공개 채팅(1:1 또는 1:다수 채팅) 및 채널 메시지에 대해 별도의 보존 정책을 설정할 수 있습니다. 조직의 특정 사용자 또는 팀에 적용되는 고유한 정책을 구성할 수도 있습니다. Teams 채팅의 경우 정책을 적용할 사용자를 선택할 수 있습니다. Teams 채널 메시지의 경우 정책을 적용할 팀을 선택할 수 있습니다.

예를 들어 채널 메시지의 경우 조직의 특정 팀에는 1년 삭제 정책을 적용하고 다른 모든 팀에는 3년 삭제 정책을 적용할 수 있습니다.

## <a name="create-and-manage-retention-policies-for-teams"></a>Teams에 대한 보존 정책 만들기 및 관리

Teams 채팅 및 채널 메시지에 대한 보존 정책을 만들 경우 Teams 위치 보존 정책의 [지침을 사용합니다.](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)

이 페이지에는 Microsoft 365의 다른 워크로드에 대한 보존 정책을 만들고 관리하는 데 대한 추가 정보가 있습니다. 예를 들어 Teams에 액세스하고 OneDrive 또는 SharePoint에 저장된 파일을 보존하고 삭제하기 위해 Microsoft 365 그룹에 대한 보존 정책을 만들 수도 있습니다.  

## <a name="end-user-experience"></a>최종 사용자 환경

비공개 채팅(1:1 채팅) 또는 그룹 채팅의 경우 사용자는 보존 정책 구성보다 오래된 채팅이 삭제되고 "오그의 보존 정책으로 인해 이전 메시지를 삭제했습니다"라는 메시지가 아직 삭제되지 않은 메시지 위에 표시됩니다. 예를 들면 다음과 같습니다.

:::image type="content" source="media/retention-policies-image1.png" alt-text="Teams 보존 정책으로 채팅 메시지가 삭제된다고 팀에 알리는 사용자":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Teams의 사용자 설명 메시지는 Teams 보존 정책의 결과로 삭제됩니다.":::

채널 메시지의 경우 사용자(채널 구성원)는 메시지가 만료되면 삭제된 메시지가 보기에서 사라지는 것을 볼 수 있습니다. 삭제된 메시지가 스레드 대화의 부모 메시지인 경우 부모 메시지 대신 "보존 정책 때문에 이 메시지가 삭제되었습니다"라는 메시지가 표시됩니다. 예를 들면 다음과 같습니다.

:::image type="content" source="media/retention-policies-image3.png" alt-text="보존 전 채널 스크린샷":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="보존 후 채널 스크린샷":::

> [!NOTE]
> 사용자가 삭제된 메시지의 결과로 표시되는 표시된 메시지는 현재 구성할 수 없습니다.

이러한 표시된 메시지의 링크는 보존 정책에 [대한 Teams 메시지로 이동됩니다.](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b) 최종 사용자에 대한 이 설명서는 메시지를 삭제한 이유에 대한 기본 질문에 답변하는 데 도움이 됩니다. 그러나 보존 정책 배포의 일부로 사용자 및 지원 센터에 구성된 설정의 영향을 전달해야 합니다.

## <a name="related-topics"></a>관련 항목

- [보존 정책 및 보존 레이블 시작](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-retention)
- [Microsoft Teams 보존에 대해 자세히 알아보기](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)
- [보존 정책 만들기 및 구성](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies)

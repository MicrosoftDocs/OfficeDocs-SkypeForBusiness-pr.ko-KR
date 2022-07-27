---
title: Microsoft Teams를 위한 보존 정책 만들기 및 관리
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Microsoft Teams에 대한 보존 정책을 사용하여 조직이 내부 정책, 업계 규정 또는 법적 요구 사항을 준수하는 데 필요한 메시지를 유지하고 책임으로 간주되거나 법적 비즈니스 가치가 없는 메시지를 삭제합니다.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 508f10c07a25bb2dc3cef7af84d7dacc62989f28
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2022
ms.locfileid: "67023689"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>Microsoft Teams를 위한 보존 정책 만들기 및 관리

> [!NOTE]
> Teams에서 보존 규정에 따라 채팅이나 메시지가 삭제되었다는 메시지를 본 적이 있다면 [보존 정책 관련 Teams 메시지](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)를 확인하세요.
> 
> 이 페이지는 해당 보존 정책을 관리하는 IT 관리자를 위한 정보를 담고 있습니다.

Microsoft 365의 보존 정책 및 보존 레이블은 조직에서 정보를 더 효과적으로 관리하는 데 도움이 됩니다. 조직의 내부 정책, 산업 규정 또는 법적 요구 사항을 준수하는 데 필요한 데이터를 유지하도록 보존 설정을 구성할 수 있습니다. 또한 보존 정책은 책임으로 간주되거나 더 이상 보관할 필요가 없거나 법적 또는 비즈니스 가치가 없는 데이터를 삭제하도록 보존 설정을 구성할 수도 있습니다.

Teams는 채팅 및 채널 메시지에 대한 보존 정책을 지원하므로 관리자는 이 데이터를 보존할지, 삭제할지 또는 특정 기간 동안 보존할지 여부를 사전에 결정한 다음 삭제할 수 있습니다. 이러한 작업에 대한 보존 기간의 시작은 항상 메시지가 생성되는 시기를 기반으로 합니다. Teams 보존 정책을 전체 조직 또는 특정 사용자 및 Teams에 적용할 수 있습니다. 보존 레이블은 Teams에서 지원되지 않습니다.

> [!NOTE]
> [공유 채널은](shared-channels.md) 보존 정책에서 지원됩니다.

Microsoft 365의 보존 솔루션에 대해 자세히 알아보려면 [보존 정책 및 보존 레이블에 대한 자세한 내용](/microsoft-365/compliance/retention)을 참조하세요.

Teams에 대한 보존 정책이 적용되는 사용자는 Office 365 E3 또는 Office 365 A3과 같은 적절한 라이선스가 있어야 합니다. 이러한 보존 정책에 대한 기타 라이선스 옵션은 [보안 및 규정 준수 대한 Microsoft 365 라이선싱 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance)의 [정보 거버넌스](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) 섹션을 참조하세요. Teams를 위한 라이선싱에 대한 자세한 내용은 [Microsoft Teams 서비스 설명](/office365/servicedescriptions/teams-service-description)을 참조하세요.

## <a name="how-teams-retention-policies-support-retain-and-delete-actions"></a>Teams 보존 정책이 보존 및 삭제 작업을 지원하는 방법

채팅 또는 채널 메시지를 보존하도록 Teams 보존 정책을 구성하는 경우 사용자는 Teams 앱에서 메시지를 편집하고 삭제할 수 있습니다. 사용자는 Teams에서 미리 편집되거나 삭제된 메시지를 더 이상 볼 수 없지만, 이러한 메시지의 데이터는 규정 준수 관리자가 eDiscovery 검색을 위해 설계한 보안 위치에 저장됩니다. 이 데이터의 영구 삭제는 구성된 보존 기간이 끝나기 전에 또는 다른 보존 정책이 이 데이터를 보존하도록 구성되어 있거나 [eDiscovery 보류](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds)의 적용을 받는 경우 발생하지 않습니다.

채팅 및 채널 메시지를 삭제하도록 보존 정책을 구성하면 이러한 메시지가 자동 삭제될 수 있습니다. 메시지가 Teams 앱에 계속 표시되면 해당 메시지들이 사라지며 [사용자는 보존 정책이 이러한 메시지를 삭제했음](#end-user-experience)을 알 수 있습니다. 이전에 메시지가 보존 작업의 적용을 받고 사용자가 편집하거나 삭제한 경우 이러한 메시지는 이제 보안 위치에서 삭제되고 eDiscovery 검색에서 더 이상 반환되지 않습니다.

정책 구성 및 사용자 작업에 따라 이러한 정책이 작동하는 방식과 Teams 보존 정책에 포함 및 제외되는 메시지 데이터에 대한 자세한 내용은 [Microsoft Teams용 보존](/microsoft-365/compliance/retention-policies-teams)에 대한 자세한 내용을 참조하세요. 이 페이지에서는 보존 정책이 메시지를 삭제할 때 때때로 지연이 발생할 수 있는 이유를 설명합니다. 예를 들어 보존 정책에서 구성한 만료 기간 이후 최대 7일 후에 Teams 앱의 사용자에게 메시지를 표시할 수 있습니다.

보존 설정이 다양한 여러 개의 Teams 보존 정책을 설정하는 경우 보존 원칙은 충돌을 해결합니다. 예제:

- 동일한 콘텐츠를 보존하거나 삭제하는 사이에 충돌이 있는 경우 콘텐츠는 항상 보안 위치에 유지되므로 eDiscovery를 통해 준수 관리자를 검색할 수 있습니다.
    
    이 원칙은 법적 또는 조사적 이유로 eDiscovery 보류 중인 메시지에도 적용됩니다.

- 동일한 콘텐츠를 보존하는 기간에 충돌이 있는 경우 해당 콘텐츠는 가장 긴 보존 기간 동안 보안 위치에 보존됩니다.

이러한 보존 원칙은 Teams에 대한 보존 정책이 여러 개 있을 때 발생할 수 있는 대부분의 충돌을 해결하지만, 자세한 내용은 [보존 원칙 또는 우선 순위](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)를 참조하세요.

## <a name="when-to-use-retention-policies-for-teams"></a>Teams에 보존 정책을 사용하는 시기

대부분의 경우 조직은 비공개 채팅 데이터를 일반적으로 프로젝트 관련 대화가 주를 이루는 채널 메시지보다 더 많은 책임으로 간주합니다.

모든 Teams 메시지에 대해 단일 보존 정책을 매우 효율적으로 구성할 수 있습니다. 또는 보다 세분화된 제어를 위해 다음을 수행할 수 있습니다.

- 비공개 채팅(1:1 또는 1:다 채팅), 표준 채널의 메시지 또는 비공개 채널의 메시지에 대해 별도의 보존 정책을 사용합니다.

- 조직의 특정 사용자 또는 팀에만 정책을 적용합니다. Teams 채팅 및 비공개 채널의 경우 정책이 적용되는 사용자를 선택할 수 있습니다. Teams 채널 메시지의 경우 정책을 적용할 팀을 선택할 수 있습니다.

예를 들어 표준 채널 메시지의 경우: 조직의 특정 팀에 대한 보존 정책을 만들고 1년 후에 삭제 작업을 사용하여 해당 정책을 구성합니다. 그런 다음 다른 모든 팀에 대한 표준 채널 메시지에 대한 또 다른 보존 정책을 만들고 3년 후에 삭제 작업을 사용하여 해당 정책을 구성합니다.

## <a name="create-and-manage-retention-policies-for-teams"></a>Teams에 대한 보존 정책 만들기 및 관리

Teams 메시지에 대한 보존 정책을 만들거나 편집하려면 Teams [위치에 대한 보존 정책](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)의 지침을 사용합니다.

해당 페이지에는 Microsoft 365의 다른 워크로드에 대한 보존 정책을 만들고 관리하는 방법에 대한 추가 정보가 있습니다. 예를 들어 Microsoft 365 그룹에 대한 보존 정책을 만들어 Teams에서 액세스하고 OneDrive 또는 SharePoint에 저장된 파일을 유지하고 삭제할 수도 있습니다.  

## <a name="end-user-experience"></a>최종 사용자 환경

비공개 채팅(1:1 채팅) 또는 그룹 채팅의 경우 사용자는 보존 정책 구성보다 오래된 채팅이 삭제되고 "조직의 보존 정책으로 인해 이전 메시지를 삭제했습니다"라는 자동 생성 메시지가 아직 삭제되지 않은 메시지의 맨 위에 표시된 것을 보게 됩니다. 예제:

:::image type="content" source="media/retention-policies-image1.png" alt-text="Teams에서 Teams 보존 정책으로 인해 채팅 메시지가 삭제되었음을 사용자에게 알렸습니다.":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="메시지를 설명하는 Teams의 사용자는 Teams 보존 정책의 결과로 삭제됩니다.":::

채널 메시지의 경우 사용자(채널 구성원)는 메시지가 만료된 후 삭제된 메시지가 보기에서 사라지는 것을 볼 수 있습니다. 삭제된 메시지가 스레드된 대화의 상위 메시지인 경우 상위 메시지 대신 "보존 정책으로 인해 이 메시지가 삭제되었습니다"라는 메시지가 표시됩니다. 예제:

:::image type="content" source="media/retention-policies-image3.png" alt-text="보존 전 채널의 스크린샷.":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="보존 후 채널의 스크린샷.":::

> [!NOTE]
> 사용자가 삭제된 메시지의 결과로 표시되는 표시된 메시지는 현재 구성할 수 없습니다.

이런 표시된 메시지의 링크를 누르면 [보존 정책에 대한 Teams 메시지](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)로 이동합니다. 최종 사용자를 위한 이 설명서는 메시지가 삭제된 이유에 대한 기본적인 질문에 답변하는 데 도움이 됩니다. 그러나 보존 정책 배포의 일부로 구성된 설정의 영향을 사용자 및 지원 센터에 전달해야 합니다.

## <a name="related-topics"></a>관련 항목

- [보존 정책 및 보존 레이블 시작하기](/microsoft-365/compliance/get-started-with-retention)
- [Microsoft Teams의 보존에 대해 자세히 알아보기](/microsoft-365/compliance/retention-policies-teams)
- [보존 정책 만들기 및 구성하기](/microsoft-365/compliance/create-retention-policies)
- 문제 해결: [Teams 및 Yammer 앱의 메시지가 보존 정책에 의해 예기치 않게 삭제됨](/microsoftteams/troubleshoot/teams-im-presence/messages-unexpectedly-deleted-retention-policy)

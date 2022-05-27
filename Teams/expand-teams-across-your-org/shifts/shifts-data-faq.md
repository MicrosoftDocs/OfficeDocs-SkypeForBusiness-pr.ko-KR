---
title: 데이터 FAQ 이동
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Shifts 데이터가 저장되는 위치, 데이터 보존, 검색 및 암호화를 포함하여 Shifts 데이터에 대한 질문과 대답을 가져옵니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 35447b432118737821f578ddaee364e780f18e0d
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675350"
---
# <a name="shifts-data-faq"></a>데이터 FAQ 이동

이 문서에서는 Shifts 데이터가 저장되는 위치, 데이터 보존, 검색 및 암호화를 포함하여 Shifts 데이터에 대한 질문과 대답을 다룹니다.

## <a name="where-is-shifts-data-stored"></a>Shifts 데이터는 어디에 저장되어 있나요?

Shifts 데이터는 아시아 태평양(APAC), 유럽 연합(EU) 또는 미국 세 지역 중 하나에 저장됩니다. 각 지역에서는 HA(고가용성) 및 DR(재해 복구)을 위해 둘 이상의 Azure 데이터 센터 지역에 데이터를 저장합니다. 현재 미국/북아메리카 지역은 미국 중북부 및 중남부의 데이터 센터를 사용합니다. 자세한 내용은 [저장된 고객 데이터를 Microsoft 365 위치를 참조하세요](/microsoft-365/enterprise/o365-data-locations).

현재 Shifts는 오스트레일리아, 캐나다, 프랑스, 일본 및 영국에서 데이터 상주를 제공합니다. 더 많은 위치로 지원을 확장하기 위해 적극적으로 노력하고 있습니다.

## <a name="can-i-choose-where-shifts-data-is-stored"></a>Shifts 데이터가 저장되는 위치를 선택할 수 있나요?

Teams 처음 설정할 때 구독 수준에서 설정된 국가 또는 지역을 선택합니다. Shifts는 이 선택을 적용하고 해당 지역을 지원하는 경우 Teams 설정된 로캘 및 지역을 사용합니다. 해당 지역에 아직 없는 경우 지원되는 인근 지역에 데이터를 저장합니다. 나중에 인근 지역에 저장된 기존 데이터를 Teams 프로비전된 지역으로 마이그레이션할 계획입니다.

## <a name="can-i-access-and-export-or-delete-a-users-personal-data-in-shifts"></a>Shifts에서 사용자의 개인 데이터에 액세스하고 내보내거나 삭제할 수 있나요?

교대 근무는 GDPR(일반 데이터 보호 규정)을 준수합니다. 개인 데이터에 대한 작업을 수행하는 사람(데이터 주체라고 함)의 공식적인 요청을 DSR(데이터 주체 요청)이라고 합니다. DSR에 대한 응답으로 Shifts에서 개인 데이터를 찾아서 작업할 수 있습니다.

Microsoft Purview 규정 준수 포털 Content Search eDiscovery 도구를 사용하여 일정 및 시간 시계 데이터를 검색하고 내보내서 Excel 수 있습니다. 다른 모든 Shifts 데이터의 경우 데이터의 스크린샷을 만들 수 있습니다.

자세한 내용은 [GDPR 및 CCPA에 대한 Office 365 데이터 주체 요청을](/microsoft-365/compliance/gdpr-dsr-office365) 참조하세요.

## <a name="what-happens-to-shifts-data-if-i-turn-off-shifts-for-my-organization"></a>조직에서 교대 근무를 해제하면 Shifts 데이터는 어떻게 됩니까?

조직에서 교대 근무를 해제해도 데이터가 삭제 *되지 않습니다* . 교대 근무를 끈 다음 나중에 Shifts를 켜면 Shifts 데이터를 계속 사용할 수 있습니다.

테넌트가 삭제되면 보존 기간이 종료된 후 모든 Shifts 데이터가 삭제됩니다.

Shifts 데이터만 삭제하는 옵션은 없습니다. Teams 팀을 삭제하면 보존 기간이 종료된 후 해당 팀과 연결된 Shifts 일정 데이터가 삭제됩니다. 자세한 내용은 [Microsoft 365 데이터 보존, 삭제 및 소멸을](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview) 참조하세요.

## <a name="can-i-recover-a-shifts-schedule-that-was-deleted"></a>삭제된 Shifts 일정을 복구할 수 있나요?

삭제된 일정을 백업하는 Microsoft 365 그룹(또는 Teams 팀)이 복원된 경우 삭제된 일정을 복구할 수 있습니다.

기본적으로 삭제된 Microsoft 365 그룹은 30일 동안 유지됩니다. 이 30일 기간은 그룹을 복원할 수 있으므로 "일시 삭제"라고 합니다. 자세한 내용은 [삭제된 Microsoft 365 그룹 복원을](/microsoft-365/admin/create-groups/restore-deleted-group?tabs=admin-center) 참조하세요.

## <a name="can-i-use-custom-retention-policies-for-shifts-data"></a>Shifts 데이터에 사용자 지정 보존 정책을 사용할 수 있나요?

현재 Shifts는 사용자 지정 보존 정책을 지원하지 않습니다.

Teams 보존 정책에 대한 자세한 내용은 Teams 보존 및 Teams [대한 보존 정책 관리에](../../retention-policies.md) [대해 알아보세요](/microsoft-365/compliance/retention-policies-teams).

## <a name="can-i-retrieve-shifts-data-for-a-user-whose-license-was-revoked"></a>라이선스가 해지된 사용자의 Shifts 데이터를 검색할 수 있나요?

현재는 라이선스가 해지된 사용자의 데이터를 검색하는 기능을 제공하지 않습니다. 이 기능은 현재 진행 중인 기능입니다.

## <a name="what-type-of-encryption-does-shifts-use-for-data-at-rest-and-in-transit"></a>Shifts는 미사용 데이터 및 전송 중인 데이터에 어떤 유형의 암호화를 사용하나요?

Shifts 데이터는 Azure Cosmos DB 및 Azure Storage 의해 미사용 시 암호화됩니다. 자세한 내용은 [미사용 Azure 데이터 암호화](/azure/security/fundamentals/encryption-atrest) 및 [Azure Cosmos DB의 데이터 암호화를 참조하세요](/azure/cosmos-db/database-encryption-at-rest).

교대 근무는 전송 중인 데이터 암호화에 대한 Microsoft 365 지침을 따릅니다. 자세한 내용은 [전송 중인 데이터에 대한 암호화를](/compliance/assurance/assurance-encryption-in-transit) 참조하세요.

미사용 데이터 및 전송 중인 데이터의 시프트 암호화는 SOC2 규정 준수 감사에 의해 매년 확인됩니다.

## <a name="can-i-access-immutable-copies-of-shifts-data"></a>변경할 수 없는 Shifts 데이터 복사본에 액세스할 수 있나요?

변경 불가능한 Shifts 데이터 복사본은 저장하지 않습니다. 예를 들어 관리자는 메모 추가, 교대 근무 시간 변경, 작업 할당 등과 같은 일정을 변경할 수 있습니다.

## <a name="can-shifts-data-be-edited"></a>Shifts 데이터를 편집할 수 있나요?

변경할 수 없는 Shifts의 특정 측면과 변경할 수 있는 특정 측면이 있습니다. 예를 들어 Shifts 앱에서 변경할 수 있는 방법과 비슷하게 메모 및 색과 같은 교대 근무 세부 정보를 편집할 수 있습니다. 요청이 철회되지 않으면 Shift 요청을 편집할 수 없습니다.

변경된 필드를 확인하려면 Microsoft 365 감사 로그에서 Shifts 이벤트를 검색할 수 있습니다. Microsoft 365 감사 로그에서 Shifts 활동에 대해 기록되는 이벤트에 대한 자세한 내용은 [Teams 작업의 Shifts](../../audit-log-events.md#shifts-in-teams-activities)를 참조하세요.

## <a name="my-organization-uses-a-workforce-management-system-for-scheduling-can-we-integrate-with-and-access-shifts-data"></a>조직에서는 예약을 위해 인력 관리 시스템을 사용합니다. Shifts 데이터와 통합하고 액세스할 수 있나요?

Shifts Graph API를 사용하면 Shifts 데이터를 WFM(외부 인력 관리) 시스템과 통합할 수 있습니다. 자세한 내용은 [Shifts Graph API](/graph/api/resources/shift)를 참조하세요.

또한 관리형 Shifts 커넥터 및 오픈 소스 Shifts 커넥터도 제공합니다. 이러한 커넥터를 사용하면 WFM 시스템을 Shifts와 직접 통합할 수 있습니다. Shifts 커넥터 및 지원되는 WFM 시스템에 대한 자세한 내용은 [Shifts 커넥터를 참조하세요](shifts-connectors.md).

## <a name="can-shifts-data-be-deleted-permanently-after-a-specified-period-of-time"></a>지정된 기간 후에 Shifts 데이터를 영구적으로 삭제할 수 있나요?

현재는 Shifts 데이터를 전혀 삭제하지 않습니다. [Shifts Graph API](/graph/api/resources/shift)를 사용하면 Power Apps 사용하여 지정된 기간 동안 데이터를 보존하는 [앱을 만들](/powerapps/maker/) 수 있습니다. 그러나, 우리는 이것을 기본적으로 지원하지 않습니다.

## <a name="can-shifts-data-be-moved-in-a-tenant-to-tenant-migration"></a>테넌트-테넌트 마이그레이션에서 Shifts 데이터를 이동할 수 있나요?

특정 요청에 따라 한 테넌트에서 다른 테넌트로 데이터를 마이그레이션할 수 있습니다. 테넌트-테넌트 마이그레이션은 즉시 지원되지 않지만 고객 요청으로 발생할 수 있습니다.

## <a name="related-articles"></a>관련 기사

- [Teams의 교대 근무](../shifts-for-teams-landing-page.md)
- [Shifts 앱 관리](manage-the-shifts-app-for-your-organization-in-teams.md)

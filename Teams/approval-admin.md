---
title: Microsoft Teams에서 승인 앱 관리
author: LanaChin
ms.author: v-lanachin
ms.reviewer: farhazk
manager: samanro
ms.topic: how-to
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Microsoft Teams에서 조직의 승인 앱을 관리하는 방법을 알아봅니다.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
appliesto:
- Microsoft Teams
ms.openlocfilehash: cbedcfb7215adbde9ee8b8dd2afb3e88422e28c2
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131187"
---
# <a name="manage-the-approvals-app-in-microsoft-teams"></a>Microsoft Teams에서 승인 앱 관리

승인 앱은 모든 Microsoft Teams 사용자를 위한 개인 앱으로 사용할 수 있습니다.
승인 앱은 감사, 규정 준수, 책임 및 워크플로를 Teams의 정형 및 비정형 승인에 모두 적용할 수 있는 간단한 방법을 제공합니다.

 ![승인 앱을 표시합니다.](media/approvals-selection.png)

승인 앱을 고정하여 메뉴 모음에 저장할 수 있습니다.

 ![는 pin 옵션이 있는 승인 앱을 표시합니다.](media/approvalApp-pin.png)

승인 앱에서 만든 첫 번째 승인은 기본 Microsoft Dataverse 환경에서 승인 솔루션의 프로비저닝을 트리거합니다. 승인 앱에서 만든 승인은 기본 Microsoft Dataverse 환경에 저장됩니다.

이 자료에서는 승인 앱 요구 사항 및 역할에 대해 설명합니다.

> [!NOTE]
> 이 기능은 정부 GCCH(Community Cloud High) 및 국방부(DOD) 사용자에게 아직 릴리스되지 않았습니다.

## <a name="required-permissions-and-licenses"></a>필요한 권한 및 라이선스

승인 앱을 배포하려면 다음 항목에 대한 권한이 필요합니다.

- Microsoft Dataverse 데이터베이스를 만들 수 있는 권한입니다.

- [powerautomate.microsoft.com](https://powerautomate.microsoft.com/) 계정

- 대상 환경의 관리자 역할

- [Power Automate](/power-automate/get-started-approvals), Office 365 또는 Dynamics 365에 대한 라이선스입니다.

- 사용자가 새 승인 템플릿을 설정하려면 Microsoft Forms 대한 라이선스가 필요합니다.

승인 앱을 사용하려면 Power Automate에 대한 라이선스가 필요하며, 첫 번째 승인 할당에서 계정이 대상 환경의 승인 사용자 역할에 자동으로 추가됩니다.

## <a name="storage-with-microsoft-dataverse"></a>Microsoft Dataverse를 사용하는 스토리지

CDM(Common Data Model)은 Microsoft Dataverse의 비즈니스 및 분석 애플리케이션에서 사용하는 공유 데이터 언어입니다. Microsoft와 파트너가 게시한 표준화되고 확장 가능한 데이터 스키마 집합으로 구성되며, 이를 통해 애플리케이션 및 비즈니스 프로세스에서 데이터의 일관성과 의미를 구현할 수 있습니다. [Microsoft Power Platform의 일반 데이터 모델](/power-automate/get-started-approvals)에 대해 자세히 알아보세요.

[승인 워크플로](/power-automate/modern-approvals)에 대해 자세히 알아보세요.

템플릿에서 만든 승인은 제목, 세부 정보, 템플릿 ID 등과 같은 데이터를 Microsoft Dataverse에 계속 저장합니다. 승인 요청에 제출된 응답은 Forms에 저장됩니다. [Microsoft Forms 위한 데이터 스토리지에](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe) 대해 자세히 알아봅니다.

>[!Note]
>Microsoft Forms 사이트에서 양식 서식 파일을 삭제하면 승인 템플릿이 중단되고 사용자가 요청을 시작할 수 없습니다. 사용자는 Microsoft Forms 삭제된 승인 템플릿을 열려고 할 때 "CDB TableNotFound" 오류가 발생합니다.

조직 범위 템플릿은 테넌트와 동일한 수명을 공유하고 팀 범위 템플릿은 팀의 동일한 수명을 공유합니다. 따라서 팀을 영구적으로 삭제하면 관련 템플릿이 삭제됩니다.

## <a name="approvals-teams-app-permissions"></a>승인 Teams 앱 사용 권한

승인 Teams 앱을 통해 다음 기능에 액세스할 수 있습니다.

- 메시지에 제공하는 메시지 및 데이터를 수신합니다.

- 메시지 및 알림을 보냅니다.

- Teams이 제공한 헤더 없이 개인 앱 및 대화 상자를 렌더링합니다.

- 이름, 전자 메일 주소, 회사 이름 및 기본 설정 언어와 같은 프로필 정보에 액세스합니다.

- Teams 구성원이 채널에 제공하는 메시지 및 데이터를 수신합니다.

- 채널에서 메시지 및 알림을 보냅니다.

- 다음과 같은 Teams 정보에 액세스합니다.
  - 팀 이름
  - 채널 목록
  - 명단(팀 구성원의 이름 및 전자 메일 주소)

- 팀의 정보를 사용하여 팀에 연락하세요.

승인 템플릿 권한

- 모든 팀 소유자는 자신이 소유한 팀에 대한 승인 템플릿을 만들 수 있습니다.

- 관리자가 처음으로 전체 조직에 대한 템플릿을 만들면 전역 및 Teams 서비스 관리자를 포함하여 테넌트 모든 관리자에 대한 새 AAD(Azure Active Directory) 그룹이 자동으로 만들어집니다. 이러한 관리자는 그룹의 소유자로 추가되므로 조직 템플릿을 공동 관리할 수 있습니다. 팀을 만든 후 조직에 익숙하지 않은 관리자는 조직 전체 템플릿을 관리할 수 있는 동일한 권한을 갖도록 그룹 소유자로 수동으로 추가해야 합니다.

> [!Note]
> 관리자가 그룹을 삭제하는 경우 AAD(Azure Active Directory) 포털 내에서 해당 그룹을 복원하여 모든 관련 데이터를 복원해야 합니다. 1개월 후 또는 관리자가 휴지통 내에서 이 그룹을 삭제하면 관련된 모든 데이터가 손실됩니다.

## <a name="disable-the-approvals-app"></a>승인 앱 사용 해제

기본적으로 승인 앱은 사용할 수 있습니다. Teams 관리 센터에서 앱을 비활성화할 수 있습니다.

  1. Teams 관리 센터에 로그인합니다.

  2. **Teams 앱** > **앱 관리** 로 이동합니다.

  3. 승인 앱을 검색합니다.

     ![Teams 앱 > 앱 관리가 강조 표시된 관리 가운데 탐색을 표시합니다.](media/manage-approval-apps.png)

  4. **승인을** 선택합니다.

  5. 조직에 대한 앱을 비활성화하려면 토글을 선택합니다.

     :::image type="content" alt-text="는 승인 앱에 대한 세부 정보를 표시합니다." source="media/approvals-details-new.png" lightbox="media/approvals-details-new.png":::

## <a name="pin-approvals-to-teams"></a>Teams에 승인 고정

### <a name="use-the-tailored-frontline-app-experience-to-pin-approvals-and-other-apps-to-teams"></a>맞춤형 최전방 앱 환경을 사용하여 승인 및 기타 앱을 Teams에 고정

Teams의 맞춤형 최전방 앱 환경은 [F 라이선스](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)가 있는 사용자를 위해 Teams에서 가장 관련성이 큰 앱을 고정합니다. 고정된 앱에는 승인, 워키 토키, 작업 및 교대 근무가 포함됩니다. 기본적으로 이 기능은 사용 중이므로 최전방 작업자에게 요구 사항에 맞는 기본 제공 환경을 제공합니다.

앱은 사용자가 빠르고 쉽게 액세스할 수 있는 Teams 데스크톱 클라이언트의 측면과 Teams 모바일 클라이언트 아래쪽에 있는 바인 앱 바에 고정됩니다.

설정한 앱 정책의 작동 방식을 포함하여 자세한 내용은 [최전방 직원을 위한 Teams 앱 조정](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)을 참조하세요.

### <a name="use-an-app-setup-policy-to-pin-approvals-to-teams"></a>앱 설정 정책을 사용하여 Teams에 승인 고정

앱 설정 정책을 사용하면 Teams를 사용자 지정하여 사용자의 사용자에게 가장 중요한 앱을 고정할 수 있습니다.

사용자에 대한 승인 앱을 고정하려면 전역(조직 전체 기본값) 정책을 편집하거나 앱 설정 정책에서 사용자 지정 정책을 만들고 할당할 수 있습니다. 자세한 내용은 [Teams에서 앱 설정 정책 관리](teams-app-setup-policies.md)를 참조하세요.

## <a name="retention-policy"></a>보존 정책

승인 앱에서 만든 승인은 현재 백업을 지원하지 않는 기본 Microsoft Dataverse 환경에 저장됩니다. [환경을 백업 및 복원하는 방법에 대해 자세히 알아보세요. PowerPlatform \|Microsoft Docs](/power-platform/admin/backup-restore-environments).

양식에 저장된 데이터는 팀 소유자가 Microsoft Forms 웹앱의 **삭제된 양식** 탭에서 정리할 때까지 삭제되지 않습니다.

## <a name="conditional-access-policies"></a>조건부 액세스 정책

현재 Teams의 승인 앱은 Microsoft Teams에 대해 설정된 조건부 액세스 정책을 지원하지 않습니다.

## <a name="data-limitations"></a>데이터 제한 사항

각 팀은 최대 400개의 승인 템플릿을 포함할 수 있으며 각 템플릿은 Microsoft Forms 현재 기능에 따라 최대 50,000개의 요청을 수집할 수 있습니다.

## <a name="auditing"></a>감사

승인 앱은 Microsoft 365 보안 및 규정 준수 센터 내에서 감사 이벤트를 기록합니다. 감사 로그를 볼 수 있습니다.

1. Microsoft 365 규정 준수 사이트로 이동합니다.

2. **감사** 섹션을 선택합니다.

3. **Microsoft Teams 승인 작업** 에서 활동을 검색합니다.

다음 활동을 검색할 수 있습니다.

- 새 승인 요청 만들기

- 승인 요청 세부 정보 보기

- 승인된 승인 요청

- 승인 요청 거부

- 승인 요청 취소

- 공유 승인 요청

- 승인 요청에 첨부된 파일

- 재할당된 승인 요청

- 승인 요청에 전자 서명 추가

- 전자 서명 요청 세부 정보 보기

- 검토된 전자 서명 요청

- 취소된 전자 서명 요청

- 새 템플릿 만들기

- 기존 템플릿 편집

- 템플릿 사용/사용 안 함

- 표시된 템플릿

Power Automate 내에서 더 많은 감사 승인에 액세스하려면 기본 승인 엔터티 승인, 승인 요청 및 승인 응답에 대한 기본 환경에서 감사를 사용하도록 설정하고 구성합니다. 생성, 업데이트 및 삭제 작업은 승인 레코드에 대해 감사할 수 있는 이벤트입니다. [보안 및 규정 준수를 위한 감사 데이터 및 사용자 활동 - Power Platform \|Microsoft Docs](/power-platform/admin/audit-data-user-activity)에 대해 자세히 알아보세요.

감사는 [Microsoft 365 보안 및 규정 준수 센터](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)에서 추가로 사용자 지정할 수 있습니다.

1. 미리 구성된 보고서를 사용하려면 Microsoft 365 보안 및 규정 준수에 로그인합니다.

2. **검색 및 조사** 를 선택하세요.

3. 감사 로그를 검색하고 **Dynamics 365 활동** 탭을 선택하세요.

[Microsoft Dataverse 및 모델 기반 앱 활동 로깅-Power Platform](/power-platform/admin/enable-use-comprehensive-auditing)에 대해 자세히 알아보세요.

## <a name="security"></a>보안

Teams 승인 앱에서 사용자는 새 승인을 만들고 보내고 받은 승인을 볼 수 있습니다. 사용자는 요청의 응답자 또는 뷰어가 아니면 다른 사용자가 만든 승인에 액세스할 수 없습니다.

>[!Note]
> 승인이 만들어진 채팅 또는 채널의 일부인 경우 사용자에게 요청의 뷰어 역할이 부여됩니다. 승인이 생성되었을 때 해당 역할이 부여되지 않은 경우 요청에 대한 조치를 취할 수 없습니다.

## <a name="approvals-e-signature-integration"></a>승인 전자 서명 통합

승인 앱 전자 서명 기능을 사용하려면 사용하려는 특정 전자 서명 공급자에 대한 라이선스가 필요합니다. 조직에 대한 라이선스를 얻으려면 공급자의 사이트로 이동해야 합니다.

### <a name="enable-or-disable-e-signature-providers"></a>전자 서명 공급자 사용 또는 사용 안 함

Teams 관리 센터를 사용하여 승인 앱에서 사용자가 사용할 수 있는 타사 전자 서명 공급자를 제어할 수 있습니다. 기본적으로 전자 서명 공급자는 승인 앱에서 사용하도록 설정됩니다. 전자 서명 공급자를 사용하지 않도록 설정하면 사용자가 승인을 만들 때 해당 공급자에 액세스할 수 없습니다. 또한 사용자는 해당 공급자를 사용하여 만든 전자 서명 요청을 볼 수 없습니다.

1. Teams 관리 센터의 왼쪽 창에서 **Teams 앱 앱** > **관리** 로 이동합니다.
2. 승인 앱을 검색한 다음 선택합니다.
3. **설정** 탭으로 이동한 다음 다음 중 하나 이상을 수행합니다.

    - Adobe Sign을 사용하거나 사용하지 않도록 설정하려면 토글을 **켜** 기 또는 끄기로 전환 **합니다**.
    - DocuSign을 사용하거나 사용하지 않도록 설정하려면 토글을 **켜** 기 또는 끄기로 전환 **합니다**.
4. **제출** 을 선택합니다.

승인 앱에서 만든 전자 서명 승인은 선택한 공급자의 클라우드 환경에 저장됩니다. 전자 서명에 대한 데이터를 내보내려면 공급자의 사이트로 이동해야 합니다. 전자 서명 계약의 스토리지, 내보내기 및 보존에 대한 자세한 내용은 공급자의 설명서를 참조하세요.

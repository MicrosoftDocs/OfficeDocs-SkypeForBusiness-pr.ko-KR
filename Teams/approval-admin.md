---
title: Teams의 승인 응용 프로그램 가용성
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Microsoft Teams의 승인 응용 프로그램 가용성에 대해 알아보세요.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f916b4e794c862a05a42f075ca2f210a079ff42a
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909522"
---
# <a name="teams-approvals-app-availability"></a>Teams 승인 앱 가용성

승인 앱은 모든 Microsoft Teams 사용자를 위한 개인 앱으로 사용할 수 있습니다.
승인 앱은 감사, 규정 준수, 책임 및 워크플로를 Teams의 정형 및 비정형 승인에 모두 적용할 수 있는 간단한 방법을 제공합니다.

 ![승인 앱을 표시합니다.](media/approvals-selection.png)

승인 앱을 고정하여 메뉴 모음에 저장할 수 있습니다.

 ![승인 앱에 고정 옵션을 표시합니다.](media/approvalApp-pin.png)

승인 앱에서 생성된 첫 번째 승인이은 기본 CDS(일반 데이터 서비스) 환경에서 승인 솔루션의 프로비저닝을 트리거합니다. 승인 앱에서 생성된 승인은 기본 CDS 환경에 저장됩니다.

이 자료에서는 승인 앱 요구 사항 및 역할에 대해 설명합니다.

## <a name="required-permissions-and-licenses"></a>필요한 권한 및 라이선스

승인 앱을 사용하려면 다음 항목에 대한 권한이 있어야 합니다.

- Microsoft CDS 데이터베이스를 만들 수 있는 사용 권한입니다.

- [flow.microsoft.com](https://flow.microsoft.com/)의 계정

- 대상 환경의 관리자 역할

- [Power Automatic](https://docs.microsoft.com/power-automate/get-started-approvals), Office 365 또는 Dynamics 365에 대한 라이선스

## <a name="storage-with-cds"></a>CDS가 포함된 저장소

일반 데이터 모델(CDM)은 CDS의 비즈니스 및 분석 응용 프로그램에서 사용되는 공유 데이터 언어입니다. Microsoft 및 파트너가 게시한 표준화된 확장 가능한 데이터 스키마 세트로 구성되어 응용 프로그램 및 비즈니스 프로세스에서 데이터와 데이터 의미의 일관성을 유지합니다. [Microsoft Power Platform의 일반 데이터 모델](https://docs.microsoft.com/power-automate/get-started-approvals)에 대해 자세히 알아보세요.

[승인 워크플로](https://docs.microsoft.com/power-automate/modern-approvals)에 대해 자세히 알아보세요.

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

## <a name="disable-the-approvals-app"></a>승인 앱 사용 해제

기본적으로 승인 앱은 사용할 수 있습니다. Teams 관리 센터에서 앱을 비활성화할 수 있습니다.

  1. Teams 관리 센터에 로그인합니다.

  2. **Teams 앱** 을 확장하고 **앱 관리** 를 선택합니다.

  3. 승인 앱을 검색합니다.

![팀 앱 > 앱 관리가 강조 표시된 관리 센터 탐색이 나타납니다.](media/manage-approval-apps.png)

  4. 승인을 선택합니다.

  5. 조직에 대한 앱을 비활성화하려면 토글을 선택합니다.

![승인 앱의 세부 정보 표시](media/approvals-details.png)

## <a name="retention-policy"></a>보존 정책

승인 앱에서 생성된 승인은 현재 백업을 지원하지 않는 기본 CDS 환경에 저장됩니다. [환경을 백업 및 복원하는 방법에 대해 자세히 알아보세요. PowerPlatform \|Microsoft Docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).

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

Flow 내에서 더 많은 감사 승인에 액세스하려면 기본 승인 엔터티 승인, 승인 요청 및 승인 응답에 대한 기본 환경에서 감사를 사용하도록 설정하고 구성합니다. 생성, 업데이트 및 삭제 작업은 승인 레코드에 대해 감사할 수 있는 이벤트입니다. [보안 및 규정 준수를 위한 감사 데이터 및 사용자 활동 - Power Platform \|Microsoft Docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity)에 대해 자세히 알아보세요.

감사는 [Microsoft 365 보안 및 규정 준수 센터](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)에서 추가로 사용자 지정할 수 있습니다.

1. 미리 구성된 보고서를 사용하려면 Microsoft 365 보안 및 규정 준수에 로그인합니다.

2. **검색 및 조사** 를 선택하세요.

3. 감사 로그를 검색하고 **Dynamics 365 활동** 탭을 선택하세요.

[Microsoft Dataverse 및 모델 기반 앱 활동 로깅-Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing)에 대해 자세히 알아보세요.

## <a name="security"></a>보안

Teams 승인 앱에서 사용자는 새 승인을 만들고 보내고 받은 승인을 볼 수 있습니다. 사용자는 요청의 응답자 또는 뷰어가 아니면 다른 사용자가 만든 승인에 액세스할 수 없습니다.

> [!Note]
> 사용자가 승인이 만들어진 채팅 또는 채널의 일부인 경우 요청의 뷰어 역할이 제공됩니다. 승인이 생성되었을 때 해당 역할이 부여되지 않은 경우 요청에 대한 조치를 취할 수 없습니다.

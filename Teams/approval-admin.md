---
title: Teams의 승인 애플리케이션 가용성
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
description: Microsoft Teams의 승인 애플리케이션 가용성에 대해 자세히 배워야 합니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f916b4e794c862a05a42f075ca2f210a079ff42a
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909522"
---
# <a name="teams-approvals-app-availability"></a>Teams 승인 앱 가용성

승인 앱은 모든 Microsoft Teams 사용자의 개인 앱으로 사용할 수 있습니다.
승인 앱은 Teams에서 구조적 및 비구조적 승인에 감사, 규정 준수, 책임 및 워크플로를 가져오는 간단한 방법을 제공합니다.

 ![승인 앱 표시](media/approvals-selection.png)

사용자는 승인 앱을 고정하여 메뉴 표시줄에 저장할 수 있습니다.

 ![고정 옵션으로 승인 앱 표시](media/approvalApp-pin.png)

승인 앱에서 만든 첫 번째 승인은 기본 CDS(Common Data Service) 환경에서 승인 솔루션의 프로비전을 트리거합니다. 승인 앱에서 만든 승인은 기본 CDS 환경에 저장됩니다.

이 문서에서는 승인 앱 요구 사항 및 역할에 대해 설명하고 있습니다.

## <a name="required-permissions-and-licenses"></a>필요한 사용 권한 및 라이선스

승인 앱을 사용하려면 다음 항목에 대한 권한이 필요합니다.

- Microsoft CDS 데이터베이스를 만들 수 있는 권한.

- 계정의 [flow.microsoft.com](https://flow.microsoft.com/)

- 대상 환경에서 관리자 역할입니다.

- [Power Automate,](https://docs.microsoft.com/power-automate/get-started-approvals)Office 365 또는 Dynamics 365에 대한 라이선스입니다.

## <a name="storage-with-cds"></a>CDS를 사용하여 저장소

CDM(공통 데이터 모델)은 CDS의 비즈니스 및 분석 애플리케이션에서 사용하는 공유 데이터 언어입니다. Microsoft 및 파트너가 게시한 표준화된, 전개할 수 있는 데이터 스마마 집합으로 구성됩니다. 이 집합은 애플리케이션 및 비즈니스 프로세스에서 데이터의 일관성과 의미를 사용할 수 있도록 합니다. Microsoft Power [Platform의 일반](https://docs.microsoft.com/power-automate/get-started-approvals)데이터 모델에 대해 자세히 알아보고

승인 워크플로에 [대해 자세히 배워야 합니다.](https://docs.microsoft.com/power-automate/modern-approvals)

## <a name="approvals-teams-app-permissions"></a>승인 Teams 앱 사용 권한

승인 팀 앱을 사용하면 다음 기능에 액세스할 수 있습니다.

- 사용자에게 제공하는 메시지 및 데이터를 수신합니다.

- 메시지 및 알림을 전송합니다.

- Teams에서 제공하는 헤더 없이 개인 앱 및 대화 상자를 렌더링합니다.

- 이름, 전자 메일 주소, 회사 이름 및 기본 설정 언어와 같은 프로필 정보에 액세스합니다.

- 팀 구성원이 채널에서 제공하는 메시지 및 데이터를 수신합니다.

- 채널에서 메시지 및 알림을 전송합니다.

- 팀의 정보에 액세스합니다.
  - 팀 이름
  - 채널 목록
  - 명단(팀 구성원 이름 및 전자 메일 주소)

- 팀의 정보를 사용하여 연락합니다.

## <a name="disable-the-approvals-app"></a>승인 앱 사용 안

승인 앱은 기본적으로 사용할 수 있습니다. Teams 관리 센터에서 앱을 사용하지 않도록 설정할 수 있습니다.

  1. Teams 관리 센터에 로그인합니다.

  2. **Teams 앱을 확장하고** 앱 **관리를 선택합니다.**

  3. 승인 앱을 검색합니다.

![Teams Apps가 강조 표시된 관리 센터 탐색을 > 앱 관리](media/manage-approval-apps.png)

  4. 승인을 선택합니다.

  5. 조직의 앱을 사용하지 않도록 설정하려면 토글을 선택합니다.

![승인 앱에 대한 세부 정보를 보여줍니다.](media/approvals-details.png)

## <a name="retention-policy"></a>보존 정책

승인 앱에서 만든 승인은 현재 백업을 지원하지 않는 기본 CDS 환경에 저장됩니다. 환경을 백업 및 복원하는 방법에 대해 자세히 [알아보십시오. Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments)

## <a name="auditing"></a>감사

승인 앱은 Microsoft 365 보안 및 규정 준수 센터 내에서 감사 이벤트를 기록합니다. 감사 로그를 볼 수 있습니다.

1. Microsoft 365 규정 준수 사이트로 이동하세요.

2. 감사 **섹션을** 선택합니다.

3. Microsoft Teams 승인 **활동에서 활동을 검색합니다.**

다음 활동을 검색할 수 있습니다.

- 새 승인 요청 만들기

- 승인 요청 세부 정보 보기

- 승인된 승인 요청

- 승인 요청 거부

- 승인 요청 취소

- 공유 승인 요청

- 승인 요청에 첨부된 파일

- 재할당 승인 요청

- 승인 요청에 전자 서명 추가

Flow 내에서 더 많은 감사 승인에 액세스하려면 기본 승인 엔터티 승인, 승인 요청 및 승인 응답에 대한 기본 환경에서 감사를 사용하도록 설정하고 구성합니다. 만들기, 업데이트 및 삭제 작업은 승인 레코드에 대해 감사할 수 있는 이벤트입니다. 보안 및 규정 준수를 위한 데이터 및 사용자 활동 감사에 대해 자세히 [알아보기 - Power Platform \| Microsoft Docs.](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity)

[Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)보안 및 규정 준수 센터에서 감사를 추가로 사용자 지정할 수 있습니다.

1. 미리 구성한 보고서를 사용 하도록 Microsoft 365 보안 및 규정 준수에 로그인합니다.

2. 검색 **& 선택합니다.**

3. 감사 로그를 검색하고 **Dynamics 365** 활동 탭을 선택합니다.

[Microsoft Dataverse](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing)및 모델 기반 앱 활동 로깅에 대한 자세한 정보 - Power Platform.

## <a name="security"></a>보안

Teams 승인 앱에서 사용자는 새 승인을 만들고 보내고 받은 승인을 볼 수 있습니다. 사용자가 요청의 응답자 또는 뷰어가 아니면 다른 사용자가 만든 승인에 액세스할 수 없습니다.

> [!Note]
> 사용자가 승인이 만들어진 채팅 또는 채널의 일부인 경우 요청의 뷰어 역할을 부여합니다. 승인을 만들 때 해당 역할을 부여하지 않은 경우 요청에 대해 조치를 취할 수 없습니다.

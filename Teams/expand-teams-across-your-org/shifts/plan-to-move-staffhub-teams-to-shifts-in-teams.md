---
title: StaffHub 팀이 이동 하도록 계획
author: LanaChin
ms.author: v-lanac
ms.reviewer: gumariam,aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 이 시간 표시 막대를 사용 하 여 StaffHub 팀에서 Microsoft 팀의 변화에 이르기까지 조직의 전환을 지원할 수 있습니다.
ms.custom: seo-marvel-mar2020
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: d38b3d7c67fd546fe73106413cd3505ea792b407
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350292"
---
# <a name="plan-to-move-your-staffhub-teams-to-shifts-in-microsoft-teams"></a>Microsoft 팀에서 StaffHub 팀을 교대으로 이동 하는 계획

> [!IMPORTANT]
> 유효 2020 년 6 월 30 일에 Microsoft StaffHub 사용이 중지 됩니다. Microsoft 팀에 StaffHub 접근 권한 값을 구축 하 고 있습니다. 현재 팀에는 일정 관리를 위해 교대 근무 앱이 포함 되어 있으며 추가 기능이 시간에 따라 롤아웃 됩니다. StaffHub은 2020 년 6 월 30 일에 모든 사용자의 작업을 중지 합니다. StaffHub를 열려고 하는 모든 사용자에 게 팀을 다운로드 하도록 지시 하는 메시지가 표시 됩니다. 자세한 내용은 [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md)을 사용 중지 하세요. 

변경 계획을 시작할 때 StaffHub에서 팀으로 전환 하는 것이 시작 됩니다. 팀으로 이동 하는 데 도움이 되도록 일반적인 전환 계획을 보여 주는 샘플 시간 표시 막대를 만들었습니다. 샘플 시간 표시 막대는 이동 준비를 위해 계획 활동을 개략적으로 설명 하 고 조직의 StaffHub 팀을 팀으로 이동 하는 과정을 안내 합니다.

시간 표시 막대를 지침으로 사용 하 여 StaffHub에서 팀으로 이동 하 고 조직의 요구 사항에 따라 사용자 지정 합니다. 시간 표시 막대의 단계에 연결 된 리소스를 검토 하세요.

## <a name="prepare-to-move-your-staffhub-teams-to-teams"></a>팀으로 StaffHub 팀 이동 준비

|단계만 |지침  |자원별 |
|---------|---------|---------|
|1    |관련자 준비 및 식별         |         |
|2     |StaffHub에서 팀으로 전환 및 팀 온 보 딩에 대 한 설명서를 검토 합니다.         |[사용 중지 StaffHub](microsoft-staffhub-to-be-retired.md)<br><br>[팀에서 StaffHub 팀을 교대으로 이동](move-staffhub-teams-to-shifts-in-teams.md)<br><br>[Teams 시작하기](../../get-started-with-teams-quick-start.md)         |
|3    |조직에서 Microsoft 365 그룹을 사용 하도록 설정        |[Microsoft 365 그룹 및 팀](../../Office-365-groups.md)      |
|4(tcp/ipv4)    |필수 조건을 충족 하는지 확인         |[전제 조건이 충족 되는지 확인](move-staffhub-teams-to-shifts-in-teams.md#check-that-prerequisites-are-met)       |
|5mb   |조직의 StaffHub 사용자에 게 팀 라이선스 할당|[Teams 라이선스 할당](move-staffhub-teams-to-shifts-in-teams.md#assign-teams-licenses)<br><br>[Teams에 대한 사용자 액세스 관리](../../user-access.md)      |
|26    |StaffHub PowerShell 모듈 설치        |[StaffHub PowerShell 모듈 설치](install-the-staffhub-powershell-module.md)        |
|7     |팀으로 이동 StaffHub 사용자 확인 및 시간 표시 막대 결정       |[보고서를 실행하여 활성 StaffHub 사용 현황 표시](run-report-to-show-staffhub-usage.md) |
|20cm(8     |Azure AD 계정이 없는 StaffHub 사용자 확인 (StaffHub에 "비활성"으로 표시) 하 고 계정에 연결     |[StaffHub 팀 구성원에 대 한 Azure AD 계정 연결](move-staffhub-teams-to-shifts-in-teams.md#link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one)        |
|되었는지    |조직에 맞게 조정 된 사용자를 위한 교육 콘텐츠 만들기         |[팀에 대 한 사용자 준비 계획 준비](../../upgrade-user-readiness.md)     |
|1천만    |팀에서 변화 하는 전환에 대해 StaffHub 사용자에 게 전달         |[팀 StaffHub 사용자에 게 전자 메일 통신 샘플](staffhub-to-teams-email-template.md)         |
|mb     |팀 클라이언트 설치         |[Teams용 클라이언트 가져오기](../../get-clients.md) |
|까지    |사용자에 게 FirstLineWorker 앱 설정 정책을 할당 (또는 사용자 지정 앱 설정 정책 만들기 및 할당) 하 여 이동 하는 앱을 팀 클라이언트에 고정  |[사용자에 게 FirstlineWorker 앱 설정 정책 할당](move-staffhub-teams-to-shifts-in-teams.md#assign-the-firstlineworker-app-setup-policy-to-users)         |
|일자     |교대 근무와 팀을 사용 하는 방법에 대 한 사용자 교육         |[팀에 대 한 온보드 사용자](move-staffhub-teams-to-shifts-in-teams.md#onboard-users-to-teams)<br><br>[도움말 문서 이동](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)<br><br>[Teams 도움말 문서](https://support.office.com/teams)<br><br>[Teams 교육 비디오](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)       |
|13     |StaffHub 팀 목록을 검토 하 여 해당 팀의 모든 사용자를 팀으로 이동 해야 합니다. 일정에 없는 사용자를 제거 합니다. |         |

## <a name="move-your-organizations-staffhub-teams-to-teams"></a>조직의 StaffHub 팀을 팀으로 이동

|단계만 |지침 |자원별  |
|---------|---------|---------|
|1  |파일럿 팀 식별 및 한 팀 이동          |[StaffHub 팀 이동](move-staffhub-teams-to-shifts-in-teams.md#move-a-staffhub-team)          |
|2    |파일럿 팀의 유효성을 검사 하 고 이동 문제를 식별 합니다. 필요에 따라 교육 문서를 업데이트 합니다.         |         |
|3     |추가 파일럿 팀을 식별 하 고 5 ~ 10 개 팀 이동         |[StaffHub 팀 이동](move-staffhub-teams-to-shifts-in-teams.md#go-beyond-your-pilot-and-move-all-staffhub-teams)         |
|4(tcp/ipv4)     |나머지 StaffHub 팀을 식별 하 고 단계적인 방법으로 이동         |[StaffHub 팀 이동](move-staffhub-teams-to-shifts-in-teams.md#go-beyond-your-pilot-and-move-all-staffhub-teams)         |
|5mb     |교대 근무 및 팀에 대 한 지원을 계속 제공         |         |
|26     |셀프 서비스 암호 재설정을 사용 하도록 설정한 경우 팀에서 로그온 문제를 지원 하기 위해 보고서를 실행 합니다.       |[셀프 서비스 암호 재설정 설정에 대 한 보고서 실행](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-reporting)        |

---
title: Microsoft Teams의 게스트 액세스에 대한 문제 해결
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: corbinm
search.appverid: MET150
description: Microsoft Teams에서 게스트 액세스에 대한 도움말을 참조하여 문제를 해결하세요.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 35598c38ad80e7d1ed75c7aedce021d0d03d2765
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326715"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Microsoft Teams의 게스트 액세스에 대한 문제 해결
======================================================

- 문제에 대해 알고 있는지 확인 하려면 [조직의 지원 팀](Known-issues.md)을 확인 하세요.
- Teams에서 게스트 액세스에 대한 현재 지원 문제를 확인하려면 [ 문제 해결](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)로 이동합니다.
- 게스트는 조직 외부의 사용자입니다. 사용자가 조직 내부에 속해 있는 경우(직원, 출장 하청 업체 또는 출장 담당자를 포함하여) 해당 사용자를 게스트로 추가할 수 없습니다. 이는 계열사에도 적용됩니다.
- [ 로드맵](https://aka.ms/teamsroadmap)에서 예정된 새 게스트 액세스 기능에 대해 알아보세요.
- [ UserVoice](https://aka.ms/TeamsUserVoice)에서 원하는 내용을 알려주세요.

## <a name="if-your-guests-are-seeing-license-errors"></a>게스트에 라이선스 오류가 표시되는 경우

팀의 게스트 액세스 권한은 Azure AD(Azure Active Directory) B2B 및 해당 라이센싱 모델을 사용합니다. 게스트 액세스는 모든 Microsoft 365 Business Standard, Office 365 Enterprise 및 Office 365 Education 구독에 포함되어 있습니다. 추가 Office 365 라이선스가 필요하지 않습니다.

> [!NOTE]
> 게스트가 다른 (리소스) 테 넌 트에 로그인 하 여 팀을 게스트로 사용할 수 있도록 하려면 게스트의 홈 테 넌 트에서 팀을 활성화 해야 합니다.

라이선스 오류가 표시 되는 경우에는 [Azure Active DIRECTORY B2B 라이선스 지침](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) 을 참조 하 여 조직에서 게스트 액세스에 대 한 요구 사항에 맞는 라이선스 요구 사항을 결정 해야 합니다.


- 초대하는 조직에 대한 게스트 라이선스가 계산됩니다. 필요한 라이선스 수를 계산할 경우 이를 고려합니다.
- 라이선스는 초대 된 게스트가 다른 Office 365 조직에서 보내거나 개인 전자 메일 주소를 사용 하 든 관계 없이 조직에 게 계산 됩니다.

## <a name="support-for-b2b-user-types"></a>B2B 사용자 유형 지원
현재 Teams에는 [Azure B2B에서 정의한](https://docs.microsoft.com/azure/active-directory/b2b/user-properties) 상태 1 및 상태 2 유형의 게스트 사용자만 지원됩니다.

## <a name="related-topics"></a>관련 항목

[Teams의 게스트 액세스](guest-access.md)



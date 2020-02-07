---
title: Microsoft 팀의 게스트 액세스 문제 해결
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
description: Microsoft 팀에서 게스트 액세스 문제 해결을 참조 하 고 문제점을 해결 하세요.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0c0f65f7026e6c083d9230551d689f0dd19d6b0d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837638"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Microsoft 팀의 게스트 액세스 문제 해결
======================================================

> [!IMPORTANT]
> 변경 내용이 적용 되려면 24 시간까지 기다려야 할 수 있습니다. 


- 팀에서 게스트 액세스에 대 한 현재 지원 문제를 확인 하려면 [팀 문제 해결](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)으로 이동 하세요.
- [Microsoft 팀에 대 한 알려진 문제](Known-issues.md)를 확인 하 여 문제에 대해 알고 있는지 확인할 수 있습니다.
- 게스트는 조직 외부의 사용자입니다. 다른 사용자가 조직 내에 있는 경우 (직원, 출장 대리점 또는 출장 업체 포함), 자신을 게스트로 추가할 수 없습니다. 계열사에도 마찬가지입니다.
- [팀 로드맵](https://aka.ms/teamsroadmap)에서 예정 된 새로운 게스트 액세스 기능에 대해 알아보세요.
- [팀 UserVoice](https://aka.ms/TeamsUserVoice)에서 원하는 내용을 알려주십시오.

## <a name="if-your-guests-are-seeing-license-errors"></a>게스트가 라이센스 오류를 보고 있는 경우

팀의 게스트 액세스는 Azure AD (Active Directory) Business to Business (B2B) 및 해당 라이선스 모델을 사용 합니다. 게스트 액세스는 모든 Office 365 Business Premium, Office 365 Enterprise 및 Office 365 Education 구독에 포함되어 있습니다. 추가 Office 365 라이선스가 필요하지 않습니다.

라이선스 오류가 표시 되는 경우에는 [Azure Active DIRECTORY B2B 라이선스 지침](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) 을 참조 하 여 조직에서 게스트 액세스에 대 한 요구 사항에 맞는 라이선스 요구 사항을 결정 해야 합니다.


- 초청 기관에 대해 게스트 라이선스가 계산 됩니다. 필요한 라이선스 수를 계산할 때이를 고려 합니다.
- 라이선스는 초대 된 게스트가 다른 Office 365 테 넌 트에서 온 것인지 또는 개인 전자 메일 주소를 사용 하는 조직에 게 계산 됩니다.

## <a name="support-for-b2b-user-types"></a>B2B 사용자 유형 지원
현재 팀은 [AZURE B2B에 정의 된 대로](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)게스트 사용자의 상태 1 및 상태 2 유형만 지원 합니다.

## <a name="related-topics"></a>관련 항목

[Teams의 게스트 액세스](guest-access.md)



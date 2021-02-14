---
title: Teams 음성 Contoso 사례 연구
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 다국적 기업에 대한 Teams 음성 사례 연구
appliesto:
- Microsoft Teams
ms.openlocfilehash: f58f3518202fd836ff962374e8f3b3a00ab71817
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786115"
---
# <a name="contoso-case-study-audio-conferencing"></a>Contoso 사례 연구: 오디오 회의

오디오 회의의 기능, 비용, 가용성 및 작동 방식에 대해 이해하기 위해 &mdash; &mdash; Contoso에서 [Office 365에서](deploy-audio-conferencing-teams-landing-page.md)오디오 회의를 검토했습니다. 

## <a name="overview"></a>개요 

오디오 회의의 경우 Contoso는 외부뿐만 아니라 조직 내에서 잘 알려진 전화 번호를 사용했습니다. Contoso는 가능한 경우 이러한 번호를 유지 관리하기를 원하기 때문에 전용 및 공유 전화 번호를 오디오 회의 브리지에 할당하는 정보를 검토했습니다. 

Contoso는 조사에 따라 다음과 같은 결정을 내렸다. 

- 정기적으로 오디오 회의 통화를 호스트하는 인구의 세그먼트만 오디오 회의 라이선스를 받게 됩니다. 

- Contoso는 전용 전화 번호를 사용하며 오디오 회의에 사용할 기존 번호를 포터링합니다.   

Contoso 사용자가 비즈니스용 Skype를 사용 중이기 때문에 모든 사용자의 사서함이 온라인에 있기 때문에 많은 사용자가 기존 모임을 예약했습니다. Contoso는 [MMS(모임](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) 마이그레이션 서비스)를 사용하여 최종 사용자를 TeamsOnly 모드로 변경하면 Contoso에 대해 기존 모임이 자동으로 업데이트되는 것을 읽습니다.  


## <a name="configuration"></a>구성

오디오 회의와 연결된 전화 번호를 전화 시스템 내에서 서비스 번호라고 합니다. 

- 통화 플랜을 사용하는 위치의 경우 기존 전화 번호를 통신사에서 Office 365로 포터링하기 위해 Contoso는 서비스 전화 번호로 이동하는 단계를 [따릅니다.](getting-service-phone-numbers.md)

- Contoso 관리자는 기술 파일럿에서 오디오 회의 라이선스를 최종 사용자에게 할당하기 위해 조직의 오디오 회의 설정 관리 단계를 [따릅니다.](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md) 

- 비즈니스 파일럿 및 마이그레이션을 위해 Contoso는 Azure Active Directory의 그룹 멤버 자격에 따라 사용자에게 라이선스 할당의 단계에 따라 그룹 기반 [라이선스를 사용했습니다.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)  

 

 
---
title: 통화에 대한 호출 분석 Microsoft Teams
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
description: 사용자당 통화 분석을 설정하여 통화 품질 문제를 식별하고 Microsoft Teams 해결합니다.
ms.openlocfilehash: be93a24f7d18e5b347c6375622ca47c3bdaeae26
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556479"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>통화에 대한 호출 분석 Microsoft Teams

관리자 Microsoft Teams 사용자별 통화 분석을 사용하여 개별 사용자의 통화 품질 및 연결 Teams 문제를 해결할 **수 있습니다**. 호출 분석을 활용하기 위해 다음을 설정합니다.
  
- 사용자에 대한 호출 분석을 볼 수 있도록 헬프데스크 에이전트와 같은 사용자에게 특수한 지원 역할을 할당합니다. 이러한 지원 역할은 관리 센터의 나머지 Teams 수 없습니다. 
    
- .tsv 또는 데이터 파일을 업로드하여 사용자당 호출 분석에 건물, 사이트 및 .csv 추가합니다.
    
사용자당 통화 분석을 사용할 준비가 됐을 때 사용자당 통화 분석을 사용하여 통화 품질이 좋지 않은 문제를 [해결하세요](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>지원 및 헬프데스크 직원에게 권한을 부여합니다.

관리자 Teams 모든 사용자에 대한 분석 정보를 호출할 수 있는 모든 액세스 권한이 있습니다. 지원 직원 및 지원 Azure Active Directory 할당할 수 있는 몇 가지 특수한 Teams 역할이 만들어졌습니다( 나머지 관리자 센터에 액세스하지 않고도 사용자당 통화 분석에 액세스할 Teams 있습니다. 사용자 **Teams** 호출 분석의 제한된 보기가 있는 사용자에게 통신 지원 전문가 역할을 할당합니다(계층 1 지원). 사용자 **Teams** 호출 분석에 대한 전체 액세스가 필요한 사용자에게 통신 지원 엔지니어 역할을 할당합니다(계층 2 지원). 두 역할 모두 관리자 센터의 나머지 Teams 없습니다.

이러한 각 역할의 역할에 대해 알아보고 각 지원 역할이 Teams [내용을 읽어보세요](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do).

관리자 역할에 대한 Teams 자세한 [내용은 관리자 Teams](using-admin-roles.md) 관리자 역할 사용을 Teams. 관리 팀에서 관리자 역할을 할당하는 Azure Active Directory 자세한 내용은 해당 팀에서 역할 보기 및 [할당을 Azure Active Directory](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).

관리 역할에 관리 역할을 할당하는 방법을 알아보 Azure Active Directory 에서 역할 보기 [및 할당을 Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>업로드.tsv 또는 .csv 파일로 저장하여 건물, 사이트 및 테넌트 정보를 추가합니다.

파일 또는 .tsv 파일을 업로드하여 사용자당 호출 분석에 건물, 사이트 및 테넌트 정보를 .csv 수 있습니다. 이 모든 정보를 사용하여 호출 분석은 IP 주소를 물리적 위치에 매핑할 수 있습니다. 관리자 및 헬프데스크 에이전트는 이 정보를 사용하여 통화 문제의 추세를 파악하는 데 도움을 줄 수 있습니다. 예를 들어 같은 건물에 있는 사용자가 비슷한 통화 품질 문제가 있는 이유는 무엇입니까? 

관리자 또는 Teams 비즈니스용 Skype CQD(전화 품질 대시보드)에서 기존 테넌트 및 Teams 비즈니스용 Skype 사용할 수 있습니다. 먼저 CQD에서 파일을 다운로드한 다음, 업로드하여 분석을 호출합니다. 

- 기존 데이터 파일을 다운로드하려면 Microsoft Teams **관리** >  센터 **Analytics** >  & **보고서Call** >  품질 대시보드로 이동 **하세요업로드.** 내 **업로드 목록에서** 원하는 **파일 옆에 있는** 다운로드를 클릭합니다. 

- 새 파일을 업로드하려면 보고 레이블 추가 및 [업데이트를 참조합니다](/microsoftteams/learn-more-about-site-upload).
  
.tsv 또는 .csv 파일을 처음부터 만드는 경우 테넌트 및 업로드 참조[합니다](CQD-upload-tenant-building-data.md).
  
## <a name="related-topics"></a>관련 항목

[사용자당 통화 분석을 사용하여 통화 품질이 좋지 않은 문제를 해결합니다.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams)

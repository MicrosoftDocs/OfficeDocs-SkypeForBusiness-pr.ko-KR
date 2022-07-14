---
title: Microsoft Teams에 대한 통화 분석 설정
author: CarolynRowe
ms.author: crowe
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
description: 사용자별 통화 분석을 설정하여 Microsoft Teams 통화 품질 문제를 식별하고 해결합니다.
ms.openlocfilehash: bcfe39ccdd9a1a751b49cdc8d0f433e3707635e3
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789943"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Microsoft Teams에 대한 통화 분석 설정

Microsoft Teams 관리자는 사용자별 통화 분석을 사용하여 **개별 사용자의** Teams 통화 품질 및 연결 문제를 해결할 수 있습니다. 통화 분석을 최대한 활용하려면 다음을 설정합니다.
  
- 기술 지원팀 에이전트와 같은 전문 지원 역할을 할당하여 사용자에 대한 통화 분석을 볼 수 있도록 합니다. 이러한 지원 역할은 Teams 관리 센터의 나머지 부분에 액세스할 수 없습니다. 
    
- .tsv 또는 .csv 데이터 파일을 업로드하여 사용자별 통화 분석에 건물, 사이트 및 테넌트 정보를 추가합니다.
    
사용자 단위 통화 분석을 사용할 준비가 되면 [사용자별 통화 분석 사용을 읽어 통화 품질 저하 문제를 해결합니다](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>지원 및 기술 지원팀 직원에게 사용 권한 부여

Teams 관리자는 모든 사용자에 대한 통화 분석 정보에 대한 모든 권한을 가집니다. Teams 관리 센터의 나머지 부분에 액세스하지 않고도 사용자별 통화 분석에 액세스할 수 있도록 직원 및 기술 지원팀 에이전트를 지원하기 위해 할당할 수 있는 몇 가지 특수한 Azure Active Directory 역할을 만들었습니다. 사용자별 통화 분석(계층 1 지원)을 제한된 보기로 볼 수 있어야 하는 사용자에게 **Teams 커뮤니케이션 지원 전문가** 역할을 할당합니다. 사용자별 통화 분석에 대한 모든 권한이 필요한 사용자에게 **Teams 통신 지원 엔지니어** 역할을 할당합니다(계층 2 지원). 두 역할 모두 Teams 관리 센터의 나머지 부분에 액세스할 수 없습니다.

이러한 각 역할이 수행하는 작업을 알아보려면 [각 Teams 지원 역할이 수행하는 작업을](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do) 읽어보세요.

Teams 관리자 역할에 대한 자세한 내용은 [Teams 관리자 역할을 사용하여 Teams를 관리하세요](using-admin-roles.md). Azure Active Directory에서 관리자 역할을 할당하는 방법을 알아보려면 [Azure Active Directory에서 역할 보기 및 할당을 참조하세요](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).

Azure Active Directory에서 관리 역할을 할당하는 방법을 알아보려면 [Azure Active Directory에서 역할 보기 및 할당을 참조하세요](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>.tsv 또는 .csv 파일을 업로드하여 건물, 사이트 및 테넌트 정보 추가

.csv 또는 .tsv 파일을 업로드하여 사용자별 통화 분석에 건물, 사이트 및 테넌트 정보를 추가할 수 있습니다. 이 모든 정보를 통해 호출 분석은 IP 주소를 실제 위치에 매핑할 수 있습니다. 관리자 및 기술 지원팀 에이전트는 이 정보를 사용하여 통화 문제의 추세를 파악할 수 있습니다. 예를 들어 동일한 건물의 사용자가 통화 품질 문제가 비슷한 이유는 무엇인가요? 

Teams 또는 비즈니스용 Skype 관리자인 경우 Teams 또는 비즈니스용 Skype CQD(통화 품질 대시보드)에서 기존 테넌트를 사용하고 데이터 파일을 빌드할 수 있습니다. 먼저 CQD에서 파일을 다운로드한 다음, 분석을 호출하도록 업로드합니다. 

- 기존 데이터 파일을 다운로드하려면 **Microsoft Teams 관리 센터** > **분석 & 보고서** > **통화 품질 대시보드** > **업로드로** 이동합니다. **내 업로드** 목록에서 원하는 파일 옆에 있는 **다운로드** 를 클릭합니다. 

- 새 파일을 업로드하려면 [보고 레이블 추가 및 업데이트를 참조하세요](/microsoftteams/learn-more-about-site-upload).
  
.tsv 또는 .csv 파일을 처음부터 만드는 경우 [테넌트 업로드 및 데이터 빌드](CQD-upload-tenant-building-data.md)를 참조하세요.
  
## <a name="related-topics"></a>관련 주제

[사용자별 통화 분석을 사용하여 통화 품질 저하 문제 해결](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams)

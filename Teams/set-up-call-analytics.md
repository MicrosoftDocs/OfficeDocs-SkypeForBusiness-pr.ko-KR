---
title: Microsoft Teams에 대한 호출 분석 설정
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Microsoft Teams 호출 품질 문제를 식별하고 문제를 해결하기 위해 사용자당 통화 분석을 설정합니다.
ms.openlocfilehash: 209fcad851f5ba7b0183a9988372e249f99cc4fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117136"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Microsoft Teams에 대한 호출 분석 설정

Microsoft Teams 관리자는 사용자별 통화 분석을 사용하여 개별 사용자에 대한 Teams 호출 품질 및 연결 문제를 **해결할 수 있습니다.** 호출 분석을 활용하기 위해 다음을 설정합니다.
  
- 사용자에 대한 호출 분석을 볼 수 있도록 헬프데스크 에이전트와 같은 사용자에게 특수한 지원 역할을 할당합니다. 이러한 지원 역할은 Teams 관리 센터의 나머지에 액세스할 수 없습니다. 
    
- .tsv 또는 .csv 데이터 파일을 업로드하여 사용자당 호출 분석에 건물, 사이트 및 테넌트 정보를 추가합니다.
    
사용자당 통화 분석을 사용할 준비가 됐을 때 사용자당 통화 분석을 사용하여 통화 품질이 좋지 않은 문제를 [해결하세요.](use-call-analytics-to-troubleshoot-poor-call-quality.md)
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>지원 및 헬프데스크 직원에게 권한을 부여합니다.

Teams 관리자로 모든 사용자에 대한 분석 정보를 호출할 수 있는 모든 액세스 권한이 있습니다. 지원 직원 및 헬프데스크 에이전트에 할당할 수 있는 몇 가지 특수한 Azure Active Directory 역할을 만들어 사용자당 통화 분석에 액세스할 수도 있습니다(Teams 관리 센터의 나머지 센터에 대한 액세스 권한이 없습니다). 사용자당 통화 분석의 제한된 보기가 있는 사용자에게 **Teams** 통신 지원 전문가 역할을 할당합니다(계층 1 지원). 사용자당  통화 분석(계층 2 지원)에 대한 전체 액세스가 필요한 사용자에게 Teams 통신 지원 엔지니어 역할을 할당합니다. 두 역할 모두 Teams 관리 센터의 나머지에 액세스할 수 없습니다.

이러한 각 역할의 역할에 대해 알아보고자 하는 각 Teams 지원 역할의 [역할은](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)무엇입니까?

Teams 관리자 역할에 대한 자세한 내용은 Teams 관리자 역할 사용을 참조하여 [Teams를 관리합니다.](using-admin-roles.md) Azure Active Directory에서 관리자 역할을 할당하는 방법에 대한 자세한 내용은 Azure Active Directory에서 역할 보기 및 [할당을 참조하세요.](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)

Azure Active Directory에서 관리 역할을 할당하는 방법에 대한 자세한 내용은 Azure Active Directory에서 역할 보기 및 [할당을 참조하세요.](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>.tsv 또는 .csv 파일을 업로드하여 건물, 사이트 및 테넌트 정보를 추가합니다.

.csv 또는 .tsv 파일을 업로드하여 사용자당 호출 분석에 건물, 사이트 및 테넌트 정보를 추가할 수 있습니다. 이 모든 정보를 사용하여 호출 분석은 IP 주소를 물리적 위치에 매핑할 수 있습니다. 관리자 및 헬프데스크 에이전트는 이 정보를 사용하여 통화 문제의 추세를 파악하는 데 도움을 줄 수 있습니다. 예를 들어 같은 건물에 있는 사용자가 비슷한 통화 품질 문제가 있는 이유는 무엇입니까? 

Teams 또는 비즈니스용 Skype 관리자인 경우 Teams 또는 비즈니스용 Skype 통화 품질 대시보드(CQD)에서 기존 테넌트 및 건물 데이터 파일을 사용할 수 있습니다. 먼저 CQD에서 파일을 다운로드한 다음, 업로드하여 분석을 호출합니다. 

- 기존 데이터 파일을 다운로드하려면 **지금 Microsoft Teams 관리 센터** 통화 품질 대시보드  >    >  **업로드로 이동하세요.** 내 **업로드 목록에서** 원하는 파일 **옆에** 있는 다운로드를 클릭합니다. 

- 새 파일을 업로드하려면 **Microsoft Teams** 관리 센터 위치로 이동한 다음 위치 데이터 업로드 또는 위치 데이터  >   **바꾸기 를 선택합니다.** 
  
.tsv 또는 .csv 파일을 처음부터 만드는 경우 테넌트 업로드 및 데이터 [작성을 참조합니다.](CQD-upload-tenant-building-data.md)
  
## <a name="related-topics"></a>관련 항목

[사용자당 통화 분석을 사용하여 통화 품질이 좋지 않은 문제를 해결합니다.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams)
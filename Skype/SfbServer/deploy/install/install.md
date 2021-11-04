---
title: 비즈니스용 Skype 서버 설치
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: '요약: 사용자 환경의 설치를 준비하는 방법을 비즈니스용 Skype 서버. Microsoft 평가판 센터에서 비즈니스용 Skype 서버 평가판을 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 다운로드합니다.'
ms.openlocfilehash: acbe9f23c2158966200600caa92d33d0aafc6b1a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773208"
---
# <a name="install-skype-for-business-server"></a>비즈니스용 Skype 서버 설치
 
**요약:** 사용자 환경 설치를 준비하는 방법을 비즈니스용 Skype 서버. Microsoft 평가판 센터에서 비즈니스용 Skype 서버 평가판을 [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 다운로드합니다.
  
이 문서에서는 예제 설치를 비즈니스용 Skype 서버. 이 문서에서는 전체 설치를 수행하는 데 필요한 모든 절차를 비즈니스용 Skype 서버 않습니다. 목표는 기본적인 meet-and-share 기능을 포함하는 좁은 정의 토폴로지의 예제 절차를 제공하는 것입니다.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>설치 프로세스 개요 비즈니스용 Skype 서버

설치 비즈니스용 Skype 서버 다양한 절차가 포함됩니다. 환경에서 실행되는 비즈니스용 Skype 서버 절차는 환경의 특정 구성에 따라 다를 수 있습니다. 예를 들어 DNS에 Windows Server를 사용하는 경우 DNS 항목을 추가하는 예제 절차의 이점을 누리게 됩니다. DNS에 다른 시스템을 사용하는 경우 특정 DNS 시스템에 대한 절차를 따라야 합니다. 이 섹션의 많은 절차에 해당합니다.
  
비즈니스용 Skype 서버 및 Standard Edition 사용할 Enterprise Edition. 주요 차이점은 Standard Edition 포함된 고가용성 기능을 지원하지 않는다는 Enterprise Edition. 
  
비즈니스용 Skype 서버 제품으로, 정확한 설치 프로세스는 특정 상황에 따라 매우 많은 수의 의존합니다. 이 섹션에서는 제품을 설치하는 일반적인 단계를 설명합니다. 그러나 환경 및 계획 결정에 따라 각 절차가 다를 수 있습니다. 예를 들어 소규모 조직의 경우 단일 서버를 실행하는 것이 비즈니스용 Skype 서버 Standard Edition 적합할 수 있는 반면, 대규모 다국적 조직에는 전 세계 50대의 서버가 제품 전용으로 있을 수 있습니다.
  
> [!NOTE]
> 최신 누적 업데이트에 대한 자세한 내용은 에 대한 업데이트를 [비즈니스용 Skype 서버.](https://support.microsoft.com/kb/3061064) CU1 패치를 설치한 후 관리자는  `Update-CsAdminRole` cmdlet을 실행해야 합니다. 원격 PowerShell을 통해 새 GCP cmdlet에 액세스하려면 이 cmdlet이 필요합니다.
  
> [!IMPORTANT]
> 이 섹션의 절차는 좁게 정의된 요구 사항 집합을 사용하는 예제로 사용하며 특정 결정이 이미 수행된 것으로 가정합니다. 설치해야 하는 실제 절차는 비즈니스용 Skype 서버 매우 다를 수 있습니다. 이 섹션의 절차는 모든 환경에 설치하기 위한 단계별 가이드가 아니라 예제로만 비즈니스용 Skype 서버 참조하세요. 
  
처음 비즈니스용 Skype 서버 시작 및 실행에는 8개의 기본 단계가 필요합니다. 이 섹션의 예제 절차만 설치하는 데 필요한 절차는 비즈니스용 Skype 서버. 다음 8단계는 전체 프로세스를 더 잘 이해하고 기본 작업 환경을 작동 및 실행하는 데 도움이 되는 예제입니다. 1~5단계는 순서에 따라 수행하면 됩니다. 그러나 다이어그램에 설명된대로 1~5단계를 순서대로 6, 7, 8단계를 순서대로 수행해야 합니다. 8단계는 다음을 수행합니다.
  
![설치 프로세스 개요.](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [비즈니스용 Skype 서버](install-prerequisites.md) 설치: 비즈니스용 Skype 서버 토폴로지로 이 토폴로지가 있는 모든 서버에 비즈니스용 Skype 서버 설치합니다. 모든 역할에 대해 전제가 동일하지는 않습니다. 예를 들어 프런트 엔드 역할을 제공하는 서버에는 여러 가지 선행 조인이 있으며, 감독 역할을 제공하는 서버는 서로 다른 선행 준비를 합니다. 자세한 내용은 선행 계획 설명서를 참조하세요.
    
- [비즈니스용 Skype 서버 파일](create-a-file-share.md) 공유 만들기 : 비즈니스용 Skype 서버 토폴로지 전체에서 서버에서 사용할 파일 공유를 비즈니스용 Skype 서버.
    
- [관리 도구 설치 비즈니스용 Skype 서버](install-administrative-tools.md) 관리 도구에는 토폴로지 작성기 및 제어판이 포함됩니다. 토폴로지의 하나 이상의 서버에 관리 도구를 설치하거나 해당 서버에서 지원되는 Windows OS 버전을 실행하는 64비트 관리 비즈니스용 Skype 서버.
    
- [Active Directory 준비 비즈니스용 Skype 서버](prepare-active-directory.md) : 비즈니스용 Skype 서버 Active Directory와 긴밀하게 작동합니다. Active Directory 도메인에서 작업할 수 있는 Active Directory 도메인을 준비해야 비즈니스용 Skype 서버. 배포 마법사를 통해 이 작업을 수행하면 도메인에 대해 한 번만 수행됩니다. 이는 프로세스에서 그룹을 만들고 도메인을 수정하기 때문에 이 작업을 한 번만 해야 합니다.
    
- 비즈니스용 Skype 서버 DNS 레코드 [만들기:](create-dns-records.md) 비즈니스용 Skype 서버 제대로 작동하려면 여러 DNS 설정이 있어야 합니다. 따라서 클라이언트가 서비스에 액세스하는 방법을 알 수 있으며 서버가 서로에 대해 알고 있습니다. DNS 항목을 할당하면 도메인 전체에서 사용할 수 있기 때문에 이러한 설정은 배포당 한 번만 완료하면 됩니다.
    
- 비즈니스용 Skype 서버 새 토폴로지 만들기 및 [게시:](create-and-publish-new-topology.md) 토폴로지의 각 서버에 비즈니스용 Skype 서버 시스템을 설치하려면 먼저 토폴로지 만들기 및 게시해야 합니다. 토폴로지 게시 시 토폴로지 정보를 중앙 관리 저장소 데이터베이스에 로드합니다. 이 풀이 Enterprise Edition 경우 새 토폴로지가 처음 게시될 때 중앙 관리 저장소 데이터베이스를 만듭니다. 이 Standard Edition 배포 마법사에서 첫 번째 Standard Edition 서버 준비 프로세스를 실행해야 토폴로지가 게시됩니다. 이렇게 하여 Standard Edition Edition 인스턴스를 설치하고 SQL Server Express 관리 저장소를 만들어 사용자 환경을 준비합니다.
    
- [토폴로지의](install-skype-for-business-server.md) 서버에 비즈니스용 Skype 서버 설치: 토폴로지가 중앙 관리 저장소에 로드되어 Active Directory에서 어떤 서버가 어떤 역할을 수행할지 알고 있는 경우 토폴로지의 각 서버에 비즈니스용 Skype 서버 시스템을 설치해야 합니다.
    
- [비즈니스용 Skype 서버](verify-the-topology.md) : 토폴로지와 비즈니스용 Skype 서버 시스템 구성 요소를 토폴로지의 각 서버에 설치한 후 토폴로지가 예상대로 작동하고 있는지 확인할 준비가 된 것입니다. 여기에는 구성이 모든 Active Directory 서버로 전파되어 전체 도메인이 도메인에서 사용할 수 비즈니스용 Skype 수 있는지 확인하는 것이 포함됩니다.
    


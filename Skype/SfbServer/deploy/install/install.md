---
title: 비즈니스용 Skype 서버 설치
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
description: '요약: 비즈니스용 Skype 서버 설치할 환경을 준비하는 방법을 알아봅니다.'
ms.openlocfilehash: 32003fc1c269a0bf1b59afc965099851b6406ed6
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860589"
---
# <a name="install-skype-for-business-server"></a>비즈니스용 Skype 서버 설치
 
**요약:** 비즈니스용 Skype 서버 설치할 환경을 준비하는 방법을 알아봅니다.
  
이 문서에서는 비즈니스용 Skype 서버 설치 예제를 안내합니다. 이 문서에서는 전체 비즈니스용 Skype 서버 설치를 수행하는 데 필요한 모든 절차를 다루지 않습니다. 목표는 기본 모임 및 공유 기능을 포함하는 좁게 정의된 토폴로지에서 예제 프로시저를 제공하는 것입니다.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>비즈니스용 Skype 서버 설치 프로세스 개요

비즈니스용 Skype 서버 설치에는 다양한 절차가 포함되어 있습니다. 환경에서 비즈니스용 Skype 서버 실행하는 데 필요한 절차는 환경의 세부 사항에 따라 달라집니다. 예를 들어 DNS에 Windows Server를 사용하는 경우 DNS 항목을 추가하는 예제 절차의 이점을 얻을 수 있습니다. DNS에 다른 시스템을 사용하는 경우 특정 DNS 시스템에 대한 절차를 따라야 합니다. 이 섹션의 많은 절차에서 마찬가지입니다.
  
비즈니스용 Skype 서버 Standard Edition 및 Enterprise Edition 사용할 수 있습니다. 주요 차이점은 Standard Edition Enterprise Edition 포함된 고가용성 기능을 지원하지 않는다는 것입니다. 
  
비즈니스용 Skype 서버 고급 제품이며 정확한 설치 프로세스는 특정 상황에 따라 크게 달라집니다. 이 섹션에서는 제품을 설치하는 일반적인 단계를 안내합니다. 그러나 각 절차는 환경 및 계획 결정에 따라 다를 수 있습니다. 예를 들어 소규모 조직의 경우 단일 서버에서 비즈니스용 Skype 서버 Standard Edition 실행하는 것이 적절할 수 있지만 대규모 다국적 조직에는 전 세계 제품 전용 위치에 50개의 서버가 있을 수 있습니다.
  
> [!NOTE]
> 최신 누적 업데이트에 대한 자세한 내용은 [비즈니스용 Skype 서버 대한 업데이트를](https://support.microsoft.com/kb/3061064) 참조하세요. CU1 패치를 설치한 후 관리자는 cmdlet을  `Update-CsAdminRole` 실행해야 합니다. 이 cmdlet은 원격 PowerShell을 통해 새 GCP cmdlet에 액세스하는 데 필요합니다.
  
> [!IMPORTANT]
> 이 섹션의 절차는 좁게 정의된 요구 사항 집합을 사용하는 예제로 사용되며 특정 결정이 이미 이루어졌다고 가정합니다. 비즈니스용 Skype 서버 설치해야 하는 실제 절차는 매우 다를 수 있습니다. 이 섹션의 절차는 모든 환경에 비즈니스용 Skype 서버 설치하기 위한 단계별 가이드가 아니라 예제로만 사용합니다. 
  
비즈니스용 Skype 서버 처음으로 시작하고 실행하려면 8개의 기본 단계가 포함됩니다. 이 섹션의 예제 프로시저는 비즈니스용 Skype 서버 설치하는 데 필요한 유일한 절차는 아니라는 것을 이해해야 합니다. 다음 8단계는 전체 프로세스를 더 잘 이해하고 기본 작업 환경을 시작하고 실행하는 데 도움이 되는 예제입니다. 1~5단계는 순서대로 수행할 수 있습니다. 그러나 다이어그램에 설명된 대로 6단계, 7, 8단계를 순서대로, 1~5단계 후에 수행해야 합니다. 8단계는 다음과 같습니다.
  
![설치 프로세스 개요입니다.](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [비즈니스용 Skype 서버 위한 필수 구성 요소 설치: 비즈니스용 Skype 서버](install-prerequisites.md) 토폴로지의 모든 서버에 필수 구성 요소를 설치합니다. 필수 구성 요소는 모든 역할에 대해 동일하지 않습니다. 예를 들어 프런트 엔드 역할을 제공하는 서버에는 일련의 필수 구성 요소가 있고, 디렉터 역할을 제공하는 서버에는 다른 필수 구성 요소 집합이 있습니다. 자세한 내용은 필수 구성 요소 계획 설명서를 참조하세요.
    
- [비즈니스용 Skype 서버 파일 공유 만들기: 비즈니스용 Skype 서버](create-a-file-share.md) 토폴로지 전체에서 서버에서 사용할 파일 공유를 만듭니다.
    
- [비즈니스용 Skype 서버 관리 도구 설치](install-administrative-tools.md): 관리 도구에는 토폴로지 작성기 및 제어판 포함됩니다. 비즈니스용 Skype 서버 지원되는 Windows OS 버전을 실행하는 토폴로지 또는 64비트 관리 워크스테이션에 하나 이상의 서버에 관리 도구를 설치해야 합니다.
    
- [비즈니스용 Skype 서버 Active Directory 준비](prepare-active-directory.md): 비즈니스용 Skype 서버 Active Directory와 긴밀하게 작동합니다. 비즈니스용 Skype 서버 사용할 Active Directory 도메인을 준비해야 합니다. 배포 마법사를 통해 이 작업을 수행할 수 있으며 도메인에 대해 한 번만 수행합니다. 이는 프로세스가 그룹을 만들고 도메인을 수정하기 때문에 한 번만 수행해야 하기 때문입니다.
    
- [비즈니스용 Skype 서버 대한 DNS 레코드 만들기](create-dns-records.md): 비즈니스용 Skype 서버 제대로 작동하려면 여러 DNS 설정이 있어야 합니다. 이는 클라이언트가 서비스에 액세스하는 방법을 알고 서버가 서로에 대해 알 수 있도록 하기 위한 것입니다. DNS 항목을 할당한 후에는 도메인 전체에서 사용할 수 있으므로 이러한 설정은 배포당 한 번만 완료해야 합니다.
    
- [비즈니스용 Skype 서버 새 토폴로지 만들기 및 게시: 토폴로](create-and-publish-new-topology.md)지의 각 서버에 비즈니스용 Skype 서버 시스템을 설치하려면 먼저 토폴로지와 게시해야 합니다. 토폴로지 게시 시 중앙 관리 Microsoft Store 데이터베이스에 토폴로지 정보를 로드합니다. Enterprise Edition 풀인 경우 새 토폴로지 처음 게시할 때 중앙 관리 Microsoft Store 데이터베이스를 만듭니다. Standard Edition 경우 토폴로지 게시하기 전에 배포 마법사에서 첫 번째 Standard Edition 서버 준비 프로세스를 실행해야 합니다. 이렇게 하면 SQL Server Express Edition 인스턴스를 설치하고 중앙 관리 Microsoft Store 만들어 Standard Edition 준비합니다.
    
- [토폴로지의 서버에 비즈니스용 Skype 서버 설치](install-skype-for-business-server.md): 토폴로지가 중앙 관리 Microsoft Store 로드되고 Active Directory에서 어떤 역할을 수행할 서버를 알고 있으면 토폴로지의 각 서버에 비즈니스용 Skype 서버 시스템을 설치해야 합니다.
    
- [비즈니스용 Skype 서버 토폴로지 확인](verify-the-topology.md): 토폴로지와 토폴로지의 각 서버에 비즈니스용 Skype 서버 시스템 구성 요소가 설치되면 토폴로지가 예상대로 작동하는지 확인할 준비가 된 것입니다. 여기에는 전체 도메인이 도메인에서 비즈니스용 Skype 사용할 수 있음을 알 수 있도록 구성이 모든 Active Directory 서버로 전파되었는지 확인하는 작업이 포함됩니다.
    


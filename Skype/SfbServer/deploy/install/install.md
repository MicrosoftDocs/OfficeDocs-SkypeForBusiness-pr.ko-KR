---
title: 비즈니스용 Skype 서버 설치
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: '요약: 비즈니스용 Skype 서버를 설치 하기 위해 환경을 준비 하는 방법을 알아봅니다. Microsoft 평가 센터에서 비즈니스용 Skype 서버의 무료 평가판을 다운로드 하세요. https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server'
ms.openlocfilehash: e33e773abf25be92c163de259af0c3f47e0b1783
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042385"
---
# <a name="install-skype-for-business-server"></a>비즈니스용 Skype 서버 설치
 
**요약:** 비즈니스용 Skype 서버를 설치 하기 위해 환경을 준비 하는 방법을 알아봅니다. Microsoft 평가 센터에서 비즈니스용 Skype 서버의 무료 평가판을 다운로드 하세요.[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)
  
이 문서에서는 비즈니스용 Skype 서버 설치의 예를 안내 합니다. 이 문서에서는 전체 비즈니스용 Skype 서버 설치를 수행 하는 데 필요한 모든 절차를 다루지는 않습니다. 여기서는 기본 모임 및 공유 기능을 포함 하는 정의 되지 않은 토폴로지에 예제 프로시저를 제공 하는 것이 목표입니다.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>비즈니스용 Skype 서버 설치 프로세스 개요

비즈니스용 Skype 서버를 설치 하는 경우 여러 가지 절차가 포함 됩니다. 환경에서 실행 되는 비즈니스용 Skype 서버를 확보 해야 하는 절차는 해당 환경의 구체적인 사항에 따라 달라 집니다. 예를 들어 Windows Server for DNS를 사용 하는 경우 DNS 항목을 추가 하는 절차를 예로 들 수 있습니다. 다른 시스템에 DNS를 사용 하는 경우에는 특정 DNS 시스템에 대 한 절차를 수행 해야 합니다. 이 섹션의 여러 절차에 적용 됩니다.
  
비즈니스용 Skype 서버는 Standard Edition 및 Enterprise Edition에서 사용할 수 있습니다. 주요 차이점은 Standard Edition이 Enterprise Edition에 포함 된 고가용성 기능을 지원 하지 않는다는 것입니다. 
  
비즈니스용 Skype 서버는 고급 제품 이며, 정확한 설치 프로세스는 구체적인 상황을 크게 좌우 합니다. 이 섹션에서는 제품을 설치 하는 일반적인 단계를 안내 합니다. 그러나 각 절차는 사용자 환경 및 계획 결정 사항에 따라 다를 수 있습니다. 예를 들어 소규모 조직의 경우 비즈니스용 Skype 서버 Standard Edition을 실행 하는 것이 적합할 수도 있지만 대규모 다국적 조직의 경우 제품 전용 지역에 50 서버가 있을 수 있습니다.
  
> [!NOTE]
> 최신 누적 업데이트에 대 한 자세한 내용은 [비즈니스용 Skype 서버에 대 한 업데이트](https://support.microsoft.com/kb/3061064)를 참조 하세요. C U 1 패치를 설치한 후에는 관리자가 `Update-CsAdminRole` cmdlet을 실행 해야 합니다. 이 cmdlet은 원격 PowerShell을 통해 새 GCP cmdlet에 액세스 하는 데 필요 합니다.
  
> [!IMPORTANT]
> 이 섹션의 절차는 정의 된 좁은 요구 사항을 사용 하는 예로, 특정 결정을 이미 수행한 적이 있다고 가정 합니다. 비즈니스용 Skype 서버를 설치 하는 데 필요한 실제 절차는 크게 다를 수 있습니다. 이 섹션의 절차는 모든 환경에서 비즈니스용 Skype 서버를 설치 하는 단계별 가이드가 아닌 한 예로 사용 하십시오. 
  
처음에 비즈니스용 Skype 서버를 설치 및 실행 하려면 8 가지 기본 단계를 수행 해야 합니다. 이 섹션의 예제 절차는 비즈니스용 Skype 서버를 설치 하는 데 필요한 유일한 절차도 이해 해야 합니다. 다음 여덟 가지 단계는 전체 프로세스를 보다 잘 이해 하 고 기본적인 작동 환경을 준비 하 고 실행 하는 데 도움이 되는 간단한 예입니다. 순서에 관계 없이 1 ~ 5 단계를 수행할 수 있습니다. 그러나 다이어그램에 나와 있는 것 처럼, 1 ~ 5 단계를 순서 대로 수행 해야 합니다. 여덟 가지 단계는 다음과 같습니다.
  
![설치 프로세스의 개요입니다.](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- 비즈니스용 Skype 서버에 [대 한 필수 구성 요소 설치](install-prerequisites.md) : 비즈니스용 skype 서버 토폴로지를 구성 하는 모든 서버에 필수 구성 요소를 설치 합니다. 필수 구성 요소는 모든 역할에서 동일 하지 않습니다. 예를 들어 프런트 엔드 역할을 제공 하는 서버에는 필수 구성 요소 집합이 있으며 디렉터 역할을 제공 하는 서버에는 서로 다른 필수 구성 요소 집합이 있습니다. 자세한 내용은 필수 구성 요소 계획 설명서를 참조 하세요.
    
- 비즈니스용 [skype 서버의 파일 공유 만들기](create-a-file-share.md) : 비즈니스용 skype 서버 토폴로지의 서버에서 사용할 파일 공유를 만듭니다.
    
- [비즈니스용 Skype 서버에서 관리 도구 설치](install-administrative-tools.md) : 관리 도구에는 토폴로지 작성기와 제어판이 포함 됩니다. 토폴로지에서 비즈니스용 Skype 서버에 대해 지원 되는 Windows OS 버전을 실행 하는 하나 이상의 서버 또는 64 비트 관리 워크스테이션에 관리 도구를 설치 해야 합니다.
    
- [비즈니스용 skype 서버에 대 한 Active Directory 준비](prepare-active-directory.md) : 비즈니스용 Skype 서버가 Active directory와 긴밀 하 게 작동 합니다. 비즈니스용 Skype 서버에서 작동 하도록 Active Directory 도메인을 준비 해야 합니다. 배포 마법사를 통해이 작업을 수행할 수 있으며, 도메인에 대해 한 번만 수행 됩니다. 이 프로세스는 그룹을 만들고 도메인을 수정 하며 한 번만 수행 하면 되기 때문입니다.
    
- [비즈니스용 skype 서버에 대 한 DNS 레코드 만들기](create-dns-records.md) : 비즈니스용 skype 서버가 제대로 작동 하려면 여러 DNS 설정이 적절 하 게 설정 되어 있어야 합니다. 따라서 클라이언트는 서비스에 액세스 하는 방법과 서버에 대 한 정보를 서로 파악 하는 방법을 알게 됩니다. 이러한 설정은 DNS 항목을 할당 한 후 도메인 전체에서 사용할 수 있으므로 배포 당 한 번만 완료 하면 됩니다.
    
- [비즈니스용 Skype 서버에서 새 토폴로지 만들기 및 게시](create-and-publish-new-topology.md) : 토폴로지의 각 서버에 비즈니스용 skype 서버 시스템을 설치 하기 전에 토폴로지를 만들고 게시 해야 합니다. 토폴로지를 게시 하면 중앙 관리 저장소 데이터베이스에 토폴로지 정보를 로드 하 게 됩니다. Enterprise Edition 풀 인 경우 새 토폴로지를 처음으로 게시할 때 중앙 관리 저장소 데이터베이스를 만듭니다. Standard Edition 이면 토폴로지를 게시 하기 전에 배포 마법사에서 최초 Standard Edition Server 준비 프로세스를 실행 해야 합니다. 이렇게 하면 SQL Server Express Edition 인스턴스를 설치 하 고 중앙 관리 저장소를 만들어 Standard Edition을 준비할 때
    
- [토폴로지의 서버에 비즈니스용 Skype 서버 설치](install-skype-for-business-server.md) : 토폴로지가 중앙 관리 저장소에 로드 되 고 Active Directory가 어떤 서버가 어떤 역할을 수행 하는지 알고 있으면 토폴로지의 각 서버에 비즈니스용 skype 서버 시스템을 설치 해야 합니다.
    
- [비즈니스용 Skype 서버에서 토폴로지 확인](verify-the-topology.md) : 토폴로지가 게시 되 고 토폴로지의 각 서버에 비즈니스용 Skype 서버 시스템 구성 요소가 설치 된 후 토폴로지가 정상적으로 작동 하는지 확인할 수 있습니다. 여기에는 전체 도메인에서 비즈니스용 Skype가 도메인에서 사용 가능한 것으로 인식할 수 있도록 구성이 모든 Active Directory 서버에 전파 되었는지 확인 하는 작업이 포함 됩니다.
    


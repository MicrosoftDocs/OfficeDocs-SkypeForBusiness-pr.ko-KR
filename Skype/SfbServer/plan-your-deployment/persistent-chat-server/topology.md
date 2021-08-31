---
title: 영구 채팅 서버 토폴로지 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: '요약: 이 항목을 통해 2015년 8월의 영구 채팅 서버 구성 요소 및 토폴로지 비즈니스용 Skype 서버 있습니다.'
ms.openlocfilehash: 63c82eee1a640616aaf8f390a66b2d67678b36ff
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58725947"
---
# <a name="plan-persistent-chat-server-topology"></a>영구 채팅 서버 토폴로지 계획
 
**요약:** 이 항목을 통해 2015년 8월의 영구 채팅 서버 구성 요소 및 토폴로지에 비즈니스용 Skype 서버 있습니다.
  
영구 채팅 서버는 단일 서버 및 다중 서버 구성을 모두 지원합니다. 영구 채팅 서버는 비즈니스용 Skype 서버 2015 또는 Enterprise Edition Standard Edition 있습니다. 

> [!NOTE] 
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 2019년 8월에는 더 이상 비즈니스용 Skype 서버 없습니다. 동일한 기능을 사용할 수 Teams. 자세한 내용은 업그레이드 시작을 [Microsoft Teams 참조하세요.](/microsoftteams/upgrade-start-here) 영구 채팅을 사용해야 하는 경우 이 기능이 필요한 사용자를 Teams 또는 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다. 
  
## <a name="persistent-chat-server-components"></a>영구 채팅 서버 구성 요소

영구 채팅 서버는 다음 구성 요소로 구성됩니다.
  
- 영구 채팅 서버를 실행하고 다음 서비스를 제공하는 하나 이상의 컴퓨터:
    
  - 영구 채팅 서비스
    
  - 준수를 사용하도록 설정한 경우 켜진 준수 서비스
    
- 채팅방 콘텐츠, 채팅방 및 범주가 저장되는 영구 채팅 콘텐츠 데이터베이스를 호스팅하기 위한 SQL Server 데이터베이스를 실행하는 하나 이상의 서버(미러링이 사용되는 경우 두 개 이상)
    
    > [!NOTE]
    > 백 엔드 데이터베이스는 만들어진 범주 및 영구 채팅방에 대한 정보를 포함하여 채팅 기록 데이터를 저장합니다. 
  
- 준수를 사용하도록 설정하면 준수를 위해 준수 이벤트 및 채팅 콘텐츠가 저장되는 영구 채팅 준수 데이터베이스를 호스팅하기 위해 SQL Server 백 엔드 데이터베이스를 실행하는 하나 이상의 서버(미러링을 사용하는 경우 하나 이상)가 실행됩니다.
    
영구 채팅 서버의 하드웨어 및 소프트웨어 요구 사항에 대한 자세한 내용은 비즈니스용 Skype 서버 [2015의](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) 서버 요구 사항 및 비즈니스용 Skype 서버 [2015의](hardware-and-software-requirements.md)영구 채팅 서버에 대한 하드웨어 및 소프트웨어 요구 사항을 참조하세요. 
  
## <a name="persistent-chat-server-topologies"></a>영구 채팅 서버 토폴로지

단일 서버 또는 다중 서버 풀 및 단일 풀 또는 다중 풀 토폴로지로 영구 채팅 서버를 배포할 수 있습니다. 영구 채팅 서버는 다음 토폴로지가 지원됩니다.
  
-  Standard Edition 프런트 엔드 서버에 영구 채팅 서버가 함께 있는 서버
    
-  Standard Edition 영구 채팅 서버가 별도의 서버에 있는 서버
    
-  Enterprise Edition 개별 서버에 단일 영구 채팅 서버가 있는 서버
    
-  Enterprise Edition 별도의 서버에 영구 채팅 서버가 두 개 이상 있는 서버
    
영구 채팅 서버는 Standard Edition 서버에 배포할 수 있습니다. 성능 및 확장은 영향을 받을 수 있으며 고가용성은 옵션이 아닙니다. 따라서 개념 증명 및 평가를 위해 Standard Edition 서버에 영구 채팅을 배포하는 것이 좋습니다. 
  
비즈니스용 Skype 서버 2015에서는 다양한 함께 사용 시나리오를 지원하여 단일 서버에서 여러 구성 요소를 실행하거나(소규모 조직인 경우) 여러 다른 서버에서 개별 구성 요소를 실행하여 하드웨어 비용을 절약할 수 있는 유연성을 제공합니다(확장성 및 성능이 필요한 대규모 조직인 경우). 구성 요소를 함께 배정할지 여부를 결정하기 전에 확장성 요인을 고려해야 합니다. 2015 및 비즈니스용 Skype 서버 서버의 Enterprise Edition Standard Edition 시나리오가 다릅니다. 
  
다음 섹션에서는 백 엔드 데이터베이스 서버에 대한 옵션과 함께 토폴로지의 설명을 보다 자세히 설명합니다. 모든 서버 역할 및 데이터베이스의 함께 사용에 대한 자세한 내용은 [Topology Basics for 비즈니스용 Skype 서버 2015을 참조합니다.](../../plan-your-deployment/topology-basics/topology-basics.md)
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>Standard Edition 프런트 엔드 서버에 영구 채팅 서버가 함께 있는 서버

이 Standard Edition 프런트 엔드 서버에 영구 채팅을 함께 사용할 수 있습니다. 가장 간단하고 기본적인 구성입니다. CPU, 메모리, 디스크 공간 등 실제 리소스 측면에서 기존 프런트 엔드 서버에 충분한 용량이 있는지 확인해야 합니다.
  
또한 영구 채팅 서버 백 엔드 서버와 영구 채팅 준수 데이터베이스(사용하도록 설정된 경우)를 로컬 SQL Server Express 수 있습니다. 전용 인스턴스와 함께 별도의 SQL Server 선택할 수도 있습니다. 
  
> [!IMPORTANT]
> 첫 번째 영구 채팅 서버가 프런트 엔드 서버와 함께 함께 있는 경우 영구 채팅 서버 풀에 서버를 Standard Edition 수 없습니다. 필요한 경우 나중에 서버를 더 추가할 수 있도록 첫 번째 서버를 독립 실행형 인스턴스로 설치하는 것이 좋습니다. 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>Standard Edition 영구 채팅 서버가 별도의 서버에 설치된 서버

이 Standard Edition 영구 채팅 서버를 독립 실행형 인스턴스로 설치하고 필요한 경우 나중에 서버를 더 추가할 수 있습니다. 
  
영구 채팅 서버 백 엔드 서버와 영구 채팅 준수 데이터베이스(사용하도록 설정된 경우)를 로컬 SQL Server Express 수 있습니다. 전용 인스턴스와 함께 별도의 SQL Server 선택할 수도 있습니다. 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>Enterprise Edition 단일 영구 채팅 서버가 있는 서버

이 Enterprise Edition 영구 채팅 서버를 별도의 컴퓨터에 설치해야 합니다. 즉, 영구 채팅 서버를 프런트 엔드 서버에 Enterprise Edition 수 없습니다. 이 배포를 사용하려면 영구 채팅 서버 및 준수 서비스를 실행하는 별도의 서버가 필요합니다(사용하도록 설정된 경우).
  
그러나 영구 채팅 서버용 SQL Server 데이터베이스를 프런트 엔드 풀의 백 엔드 데이터베이스에 Enterprise Edition 수 있습니다.
  
> [!NOTE]
> HA DR에 대해 SQL AlwaysOn 가용성 그룹을 사용하려면 영구 채팅 서버 데이터베이스에 대해 지원되지 않습니다. 
  
영구 채팅 데이터베이스를 백 엔드 데이터베이스와 함께 두는 경우 모든 데이터베이스에 대해 단일 SQL Server 인스턴스를 사용할 수도 있습니다. 또는 각 데이터베이스에 대해 별도의 SQL Server 인스턴스를 사용할 수 있습니다.
  
> [!IMPORTANT]
> 영구 채팅 데이터베이스를 호스팅하는 서버는 다른 데이터베이스를 호스팅할 수 있습니다. 그러나 영구 채팅 데이터베이스를 다른 데이터베이스와 함께 사용할 경우 여러 사용자의 메시지를 저장하는 경우 영구 채팅 데이터베이스에 필요한 디스크 공간이 매우 커질 수 있습니다. 따라서 영구 채팅 데이터베이스를 백 엔드 데이터베이스와 함께 두지 않는 것이 좋습니다. 
  
다음 그림에서는 준수가 사용하도록 설정된 단일 영구 채팅 서버에 대한 토폴로지의 모든 구성 요소를 보여 주며 선택 사항입니다.
  
**단일 서버 토폴로지**

![영구 채팅 서버 - 단일 서버 토폴로지.](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>Enterprise Edition 여러 영구 채팅 서버가 있는 서버

이 Enterprise Edition 사용하면 용량과 안정성을 향상하기 위해 다중 서버 토폴로지 배포를 할 수 있습니다. 다중 서버 토폴로지는 단일 서버 토폴로지와 동일합니다. 단, 여러 서버가 영구 채팅 서버를 호스팅하고 더 높은 수준으로 확장할 수 있는 경우를 제외하고는 동일합니다. 다중 서버 토폴로지에는 영구 채팅 서버를 실행하는 최대 4대의 활성 컴퓨터가 포함되어 있을 수 있습니다. 고가용성 및 재해 복구 구성에서는 최대 8대를 사용할 수 있지만 활성 상태인 컴퓨터는 4대만 활성화되고 나머지 4대는 대기 상태일 수 있습니다. 각 서버는 20,000명까지 동시 사용자를 지원할 수 있으며, 총 80,000명의 동시 사용자를 4대의 서버가 있는 영구 채팅 서버 풀에 연결할 수 있습니다. 영구 채팅 서버를 실행하는 여러 컴퓨터가 동일한 Active Directory 도메인 서비스 도메인에 비즈니스용 Skype 서버 준수 서비스에 상주해야 합니다.
  
다음 그림에서는 영구 채팅 서버를 실행하는 여러 컴퓨터, 선택적 준수 서비스 및 별도의 준수 데이터베이스를 실행하는 다중 서버 토폴로지의 모든 구성 요소를 보여줍니다.
  
**다중 서버 토폴로지**

![영구 채팅 서버 - 여러 서버 토폴로지.](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
다중 서버 토폴로지에서는 서버 기능 풀링을 제공합니다. 서버 풀에서 영구 채팅 서비스는 데이터를 통신하고 공유합니다. 예를 들어 원래 영구 채팅 서비스에 게시된 채팅 기록은 시스템의 모든 영구 채팅 서비스에서 사용할 수 있습니다. 하나의 영구 채팅 서비스를 통해 업로드된 파일에는 영구 채팅 서비스에서 액세스할 수 있습니다. 사용자는 서로 다른 영구 채팅 서버 프런트 엔드 서버에 연결할 수 있으며 서로 통신할 수 있습니다. TCP 8011의 기본 포트는 서버를 서버 풀에 연결하며, 영구 채팅 서비스에서 자체 또는 관리 목적으로 통신하는 데 사용됩니다.
  
예를 들어 80,000명이 동시에 영구 채팅에 로그인할 수 있는 4 서버 영구 채팅 서버 배포에서는 서버당 사용자 20,000명으로 부하가 고리적으로 분산됩니다. 한 서버를 사용할 수 없게 되는 경우 해당 서버에 연결된 사용자는 영구 채팅 서버에 액세스할 수 없게 됩니다. 연결이 끊긴 사용자는 해당 서버가 복원될 때까지 나머지 서버로 자동으로 전송됩니다. 
  


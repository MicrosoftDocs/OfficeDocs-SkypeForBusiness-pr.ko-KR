---
title: 비즈니스용 Skype 클라우드 커넥터 버전 구성 및 관리
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ce323f4b-24e4-4ddf-84a3-67da82bb0c87
description: 비즈니스용 Skype Online의 전화 시스템(클라우드 PBX) 음성 서비스와의 통합을 가능하게 하는 최소의 사내 토폴로지인 비즈니스용 Skype 클라우드 커넥터 Edition을 구성하는 방법을 학습합니다.
ms.openlocfilehash: 4d24e5a312275158f276856aa78396ad63dff615
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094876"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a>비즈니스용 Skype 클라우드 커넥터 버전 구성 및 관리
 
> [!Important]
> Cloud Connector Edition은 비즈니스용 Skype Online과 함께 2021년 7월 31일부터 사용이 중지됩니다. 조직이 Teams로 업그레이드한 후 직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 배워야 합니다.](/MicrosoftTeams/direct-routing-landing-page)

비즈니스용 Skype Online의 전화 시스템(클라우드 PBX) 음성 서비스와의 통합을 가능하게 하는 최소의 사내 토폴로지인 비즈니스용 Skype 클라우드 커넥터 Edition을 구성하는 방법을 학습합니다. 
  
시작하기 전에 Plan for Skype for Business Cloud Connector Edition 의 선행 [준비를 검토해야 합니다.](plan-skype-for-business-cloud-connector-edition.md)
  
> [!IMPORTANT]
> 이 항목의 단계는 Cloud Connector Edition 1.4.1 이상에만 적용됩니다. 아직 Cloud Connector Edition 2.1로 업그레이드하지 않은 경우 새 버전의 클라우드 커넥터로 [업그레이드를 참조합니다.](upgrade-to-a-new-version-of-cloud-connector.md) 에서 설치 파일을 다운로드할 수 [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 있습니다. 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a>비즈니스용 Skype 클라우드 커넥터 버전 구성 단계

다음 표에는 Cloud Connector Edition을 설치 및 구성하는 데 필요한 단계가 나열됩니다.
  
|**단계**|**설명**|
|:-----|:-----|
|[클라우드 커넥터 어플라이언스 준비](prepare-your-cloud-connector-appliance.md) <br/> |설치 파일을 다운로드하고, 인증서를 준비하고, Hyper-V, 클라우드 커넥터 배포를 위한 환경을 준비합니다.  <br/> |
|[클라우드 커넥터에서 단일 사이트 배포](deploy-a-single-site-in-cloud-connector.md) <br/> |클라우드 커넥터 배포에서 사이트를 만들 수 있습니다.  <br/> |
|[클라우드 커넥터에서 여러 사이트 배포](deploy-multiple-sites-in-cloud-connector.md) <br/> |배포에 사이트를 추가하고 단일 사이트 배포와 다중 사이트 배포 간의 차이점에 대해 설명합니다.  <br/> |
|[Microsoft 365 또는 Office 365 조직과 클라우드 커넥터 통합 구성](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |DNS 레코드를 추가하고, 하이브리드를 구성하고, PSTN 게이트웨이를 설정하고, 사용자가 전화 시스템 음성 메일을 사용할 수 있도록 합니다.  <br/> |
|[클라우드 커넥터 배포 확인](validate-your-cloud-connector-deployment.md) <br/> |배포가 올바르게 작동하고 있는지 확인합니다.  <br/> |
|[클라우드 커넥터의 새 버전으로 업그레이드](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |기존 클라우드 커넥터 배포를 버전 2.1로 업그레이드합니다.  <br/> |
|[기존 클라우드 커넥터 배포의 구성 수정](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |클라우드 커넥터가 이미 배포된 후 설정을 변경합니다.  <br/> |
|[클라우드 커넥터 버전에서 미디어 우회 배포](deploy-media-bypass-in-cloud-connector.md) <br/> |클라우드 커넥터에서 미디어 우회를 배포하는 방법을 배워야 합니다.  <br/> |
|[클라우드 커넥터 cmdlet 참조](cloud-connector-cmdlet-reference.md) <br/> |클라우드 커넥터에서 사용되는 PowerShell cmdlet에 대해 자세히 알아보습니다.  <br/> |
|[클라우드 커넥터 배포 문제 해결](troubleshoot-your-cloud-connector-deployment.md) <br/> |클라우드 커넥터 배포에서 발생하는 일반적인 문제에 대한 해결 방법  <br/> |

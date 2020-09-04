---
title: 비즈니스용 Skype 클라우드 커넥터 에디션 구성 및 관리
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
description: 비즈니스용 skype Online에서 온-프레미스 음성 인프라와 전화 시스템 (클라우드 PBX) 음성 서비스의 통합을 사용 하도록 설정 하는 데 필요한 비즈니스용 Skype 클라우드 커넥터 버전을 구성 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: e30fcb4cad44bffed495f1191e5e5cae73bb18cc
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358794"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a>비즈니스용 Skype 클라우드 커넥터 에디션 구성 및 관리
 
> [!Important]
> 클라우드 커넥터 버전은 비즈니스용 Skype Online과 함께 2021 년 7 월 31 일에 사용 중지 됩니다. 조직이 팀으로 업그레이드 된 후에는 [직접 라우팅을](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)사용 하 여 팀에 온-프레미스 전화 통신 네트워크를 연결 하는 방법을 알아보세요.

비즈니스용 skype Online에서 온-프레미스 음성 인프라와 전화 시스템 (클라우드 PBX) 음성 서비스의 통합을 사용 하도록 설정 하는 데 필요한 비즈니스용 Skype 클라우드 커넥터 버전을 구성 하는 방법에 대해 알아봅니다. 
  
시작 하기 전에 [비즈니스용 Skype 클라우드 Connector Edition 계획](plan-skype-for-business-cloud-connector-edition.md)의 필수 구성 요소를 검토 해야 합니다.
  
> [!IMPORTANT]
> 이 항목의 단계는 Cloud Connector Edition 1.4.1 이상에만 적용 됩니다. 클라우드 Connector Edition 2.1로 아직 업그레이드 하지 않은 경우 [새 버전의 클라우드 커넥터로 업그레이드를](upgrade-to-a-new-version-of-cloud-connector.md)참조 하세요. 에서 설치 파일을 다운로드할 수 있습니다 [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) . 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a>비즈니스용 Skype 클라우드 커넥터 버전을 구성 하는 단계

다음 표에는 클라우드 커넥터 Edition을 설치 하 고 구성 하는 데 필요한 단계가 나와 있습니다.
  
|**단계**|**설명**|
|:-----|:-----|
|[클라우드 커넥터 어플라이언스 준비](prepare-your-cloud-connector-appliance.md) <br/> |설치 파일을 다운로드 하 고 인증서를 준비 하며 Hyper-v를 구성 하 고 클라우드 커넥터 배포를 위한 환경을 준비 합니다.  <br/> |
|[클라우드 커넥터에서 단일 사이트 배포](deploy-a-single-site-in-cloud-connector.md) <br/> |클라우드 커넥터 배포에 사이트를 만듭니다.  <br/> |
|[클라우드 커넥터에서 여러 사이트 배포](deploy-multiple-sites-in-cloud-connector.md) <br/> |배포에 사이트를 추가 하 고 단일 및 다중 사이트 배포 간의 차이점에 대해 알아봅니다.  <br/> |
|[Microsoft 365 또는 Office 365 조직과의 클라우드 커넥터 통합 구성](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |DNS 레코드 추가, 하이브리드 구성, PSTN 게이트웨이 설정 및 전화 시스템 음성 메일에 대해 사용자를 사용 하도록 설정  <br/> |
|[클라우드 커넥터 배포 확인](validate-your-cloud-connector-deployment.md) <br/> |배포가 제대로 작동 하는지 확인 합니다.  <br/> |
|[클라우드 커넥터의 새 버전으로 업그레이드](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |기존 클라우드 커넥터 배포를 버전 2.1으로 업그레이드 합니다.  <br/> |
|[기존 클라우드 커넥터 배포의 구성 수정](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |클라우드 커넥터를 이미 배포한 후에 설정을 변경 합니다.  <br/> |
|[클라우드 커넥터 Edition에 미디어 바이패스 배포](deploy-media-bypass-in-cloud-connector.md) <br/> |클라우드 커넥터에 미디어 바이패스를 배포 하는 방법을 알아봅니다.  <br/> |
|[클라우드 커넥터 cmdlet 참조](cloud-connector-cmdlet-reference.md) <br/> |클라우드 커넥터에 사용 되는 PowerShell cmdlet에 대해 알아봅니다.  <br/> |
|[클라우드 커넥터 배포 문제 해결](troubleshoot-your-cloud-connector-deployment.md) <br/> |클라우드 커넥터 배포 시 발생 하는 일반적인 문제에 대 한 해결 방법입니다.  <br/> |
   


---
title: Microsoft Teams 룸
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: 이 항목에서 Microsoft Teams 룸(Microsoft Teams 룸 포함) 및 공용 영역 Surface Hub 계정 구성에 대해 자세히 알아보는 방법을 참조하세요.
ms.openlocfilehash: 4ecac71ef862fda003523bbcefe3c333daefaa23
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514733"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Microsoft Teams 룸
 
이 항목에서는 계정에서 사용하는 계정을 만드는 Microsoft Teams 룸. 인프라는 다음 구성 중 하나에 빠질 수 있습니다.
  
- 온라인 배포: 조직의 환경은 전체적으로 Microsoft 365 또는 Office 365.
    
- 프레미스 배포: 조직에 제어하는 서버가 있으며 Active Directory, Exchange 및 비즈니스용 Skype 서버 있습니다. 자세한 내용은 Microsoft Teams 룸 배포를 [비즈니스용 Skype 서버](with-skype-for-business-server-2015.md)
    
- 하이브리드 배포: 조직에는 여러 서비스가 있으며, 일부 호스팅된 일부 프레미스 및 일부 온라인 호스팅은 Microsoft 365 Office 365. 이 Microsoft Teams 룸 하이브리드 시나리오가 지원됩니다.
    
  - Exchange Online 비즈니스용 Skype 서버 사용할 수 있습니다.
    
  - Exchange 프레미스에서 Microsoft Teams.
    
디바이스 설정을 준비하는 방법에 영향을 줄 구성입니다.
  
Microsoft Teams 룸 Active Directory, Exchange 및(필요한 경우) "리소스 계정"이 비즈니스용 Skype. 이 계정은 모임 일정에 액세스하고 연결 Microsoft Teams 및/또는 비즈니스용 Skype 설정하는 데 사용됩니다. 사용자와 함께 모임을 예약하여 이 계정을 예약할 수 있습니다. Microsoft Teams 룸 모임에 참가하고 모임 참석자들에게 다양한 기능을 제공할 수 있습니다.
  
> [!IMPORTANT]
> 리소스 계정이 없는 경우 이러한 기능 중 어느 것도 작동하지 않습니다.
  
모든 리소스 계정은 단일 설치에 Microsoft Teams 룸 있습니다.
  
- 리소스 계정을 올바르게 구성해야 합니다.
    
- 리소스 계정의 유효성을 검사하고 Microsoft Teams 룸 도달할 수 있도록 인프라를 구성해야 Microsoft 서비스.

> [!NOTE] 
> Microsoft Teams 패널을 사용하는 경우 Teams 룸 리소스 계정이 Teams 룸 및 연결된 Teams 로그인합니다.
    
> [!IMPORTANT]
> 실제 하드웨어 설치에 앞서 계정 만들기를 잘하는 것이 좋습니다. 이상적으로 계정 준비는 설치 2~3주 전에 시작됩니다.
> 
계정을 사용하지 않는 하이브리드 환경에서는 비즈니스용 Skype 계정을 기본적으로 만드는 것이 Azure Active Directory. 계정이 프레미스 Active Directory를 사용하여 만들어야 하는 경우 Azure Active Directory(AAD) 커넥트 인증에서 Microsoft Teams 룸 인증을 Microsoft 365 Office 365 있어야 합니다. 계정을 설정할 때 계정의 전자 메일 주소가 계정의 사용자 주체 이름(UPN)과 일치하는지 AAD. 
  
리소스 계정을 사람들이 회의실의 이름 또는 공유 공간의 이름으로 인식하는 계정으로 생각할 수 있습니다. 해당 공간을 사용하여 모임을 예약하려는 경우 해당 모임에 리소스 계정을 초대합니다.
  
설치하는 공간에 Exchange 리소스 사서함 계정이 이미 Microsoft Teams 룸 있는 경우 해당 계정을 Teams 룸 수 있습니다. 이 작업을 완료하면 해당 계정으로 로그인하기 위해 Microsoft Teams 룸 합니다.
  
## <a name="basic-configuration"></a>기본 구성

이러한 속성은 리소스 계정에서 작업할 최소 구성을 Microsoft Teams 룸. 리소스 계정에 추가 설정이 필요할 수 있습니다.
  
|**속성**|**목적**|
|:-----|:-----|
|Exchange 사서함(Exchange SP1 이상 또는 Exchange Online)  <br/> |Exchange 사서함은 리소스 계정에 메일 및 모임 요청을 받고 보내고 모임 일정을 표시하는 기능을 Microsoft Teams 룸. Microsoft Teams 룸 사서함은 "room"형식의 리소스 사서함이 되어야 합니다.  <br/> |
|비즈니스용 Skype 사용  <br/> |비즈니스용 Skype 화상 통화, IM 및 화면 공유와 같은 다양한 회의 비즈니스용 Skype 사용할 수 있습니다.  <br/> |
|암호 사용  <br/> |리소스 계정을 암호로 사용하도록 설정해야 합니다. 또는 암호, Microsoft Teams 또는 Exchange 인증할 수 비즈니스용 Skype 서버. 모든 리소스 계정에서 암호 만료를 Teams 룸 해야 합니다.   <br/> |
   
## <a name="advanced-configuration"></a>고급 구성

기본 구성에 대한 속성은 리소스 계정을 간단한 환경에서 설정할 수 있도록 허용하지만 리소스 계정을 성공적으로 사용하려면 환경에 충족해야 하는 계정에 대한 Microsoft Teams 룸 수 있습니다.
  
|**속성**|**목적**|
|:-----|:-----|
|인증서 기반 인증  <br/> |인증서는 Exchange 및 비즈니스용 Skype 서버. 인증서를 배포하려면 관리자로 로그인할 때 인증서를 로드할 수 있습니다.  <br/> |

## <a name="see-also"></a>참고 항목

[Microsoft Teams 룸 계획](rooms-plan.md)
  
[Microsoft Teams 룸 콘솔 구성](console.md)
  
[Microsoft Teams 룸 관리](rooms-manage.md)

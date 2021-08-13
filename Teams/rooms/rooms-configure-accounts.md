---
title: Microsoft Teams 룸
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: 이 항목에서 계정 및 Microsoft Teams 룸 계정 구성에 대해 Exchange 비즈니스용 Skype.
ms.openlocfilehash: d66e495fd4e1e75227b162974891cda9876fef28c9f809dead001af1a95b099a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54348803"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Microsoft Teams 룸
 
이 항목을 읽고 Microsoft Teams 룸 및 이 항목과 통합하는 방법에 Exchange 비즈니스용 Skype.
  
이 항목에서는 Microsoft Microsoft Teams 룸 계정에서 사용하는 계정을 만드는 Exchange 비즈니스용 Skype. Microsoft Teams 룸 디바이스에 대한 배포 지침은 Microsoft Teams 룸 [구성에 설명되어 있습니다.](console.md) 인프라는 다음 구성 중 하나에 빠질 수 있습니다.
  
- 온라인 배포: 조직의 환경은 전체적으로 Microsoft 365 또는 Office 365. 자세한 내용은 Microsoft Teams 룸 또는 Microsoft 365 [Office 365.](with-office-365.md)
    
- 프레미스 배포: 조직에는 Active Directory, Exchange 및 비즈니스용 Skype 서버 서버가 있습니다. 자세한 내용은 Microsoft Teams 룸 배포를 [비즈니스용 Skype 서버](with-skype-for-business-server-2015.md)
    
- 하이브리드 배포: 조직에는 여러 서비스가 있으며, 일부 호스팅된 일부 프레미스 및 일부 온라인 호스트는 Microsoft 365 또는 Office 365. 다음 Microsoft Teams 룸 하이브리드 시나리오가 지원됩니다.
    
  - Exchange Online 비즈니스용 Skype 서버 사용할 수 있습니다. 자세한 내용은 [하이브리드(Microsoft Teams 룸)를 Exchange Online 배포를 참조하세요.](with-exchange-online.md)
    
  - Exchange 온라인을 통해 Microsoft Teams 비즈니스용 Skype 있습니다. 자세한 내용은 Microsoft Teams 룸(하이브리드) Exchange 배포를 [참조하세요.](with-exchange-on-premises.md)
    
디바이스 설정을 준비하는 방법에 영향을 줄 구성입니다.
  
Microsoft Teams 룸 디렉터리에서 "디바이스 계정"을 할당해야 합니다. Exchange 및 비즈니스용 Skype. 이 계정은 모임 일정에 액세스하고 연결 또는 연결 Microsoft Teams 비즈니스용 Skype 사용됩니다. 사용자와 함께 모임을 예약하여 이 계정을 예약할 수 있습니다. Microsoft Teams 룸 모임에 참가하고 모임 참석자들에게 다양한 기능을 제공할 수 있습니다.
  
> [!IMPORTANT]
> 디바이스 계정이 없는 경우 이러한 기능은 작동하지 않습니다. 
  
모든 디바이스 계정은 단일 디바이스에 고유하며 Microsoft Teams 룸 설정이 필요합니다.
  
- 디바이스 계정을 올바르게 구성해야 합니다.
    
- 디바이스 계정의 유효성을 검사하고 적절한 Microsoft Teams 룸 도달할 수 있도록 인프라를 구성해야 Microsoft 서비스.
    
> [!IMPORTANT]
> 실제 하드웨어 설치에 앞서 계정 만들기를 잘하는 것이 좋습니다. 이상적으로 계정 준비는 설치 2~3주 전에 시작됩니다. 

하이브리드 환경에서는 인증에 Microsoft Teams 룸 인증이 필요하기 때문에 Azure Active Directory(AAD) 동기화에서 Microsoft Teams 룸 암호 동기화가 Microsoft 365 Office 365 있어야 합니다. 계정을 설정할 때 계정의 SIP 주소가 AAD의 사용자 주체 이름(UPN)과 일치하는지 확인하세요. 
  
디바이스 계정을 사람들이 회의실 또는 모임 공간의 계정으로 인식하는 리소스 계정으로 생각할 수 있습니다. 해당 회의실을 사용하여 모임을 예약하려는 경우 해당 모임에 계정을 초대합니다. 가장 효율적으로 Microsoft Teams 룸 위해 각 계정에 할당된 디바이스 계정과 동일한 작업을 합니다.
  
설치하는 모임 공간에 대해 리소스 사서함 계정이 이미 설정되어 있는 Microsoft Teams 룸 해당 리소스 계정을 디바이스 계정으로 변경할 수 있습니다. 완료되면 디바이스 계정을 디바이스에 추가하기만 Microsoft Teams 룸 있습니다. 아래 제공된 디바이스 계정 설정 예제를 참조하세요.
  
추가 구성을 통해 [Azure Monitor를](azure-monitor-plan.md)사용하여 계획 Microsoft Azure 모니터링에서 설명한 Microsoft Teams 룸 Azure Monitor를 사용하여 Microsoft Teams 룸 관리 배포 및 Azure [Monitor를](azure-monitor-deploy.md)사용하여 디바이스 Microsoft Teams 룸 원격 [관리가](azure-monitor-manage.md)가능합니다. 
  
## <a name="basic-configuration"></a>기본 구성

이러한 속성은 디바이스 계정에서 작동하기 위한 최소 구성을 Microsoft Teams 룸. 디바이스 계정에 추가 설정이 필요할 수 있습니다.
  
|**속성**|**목적**|
|:-----|:-----|
|Exchange 사서함(Exchange SP1 이상 또는 Exchange Online)  <br/> |사서함이 있는 Exchange 사용하도록 설정하면 디바이스 계정에 메일 및 모임 요청을 모두 수신하고 보내고 모임 일정을 Microsoft Teams 룸 있습니다. Microsoft Teams 룸 사서함은 룸 사서함이 되어야 합니다.  <br/> |
|비즈니스용 Skype 사용  <br/> |비즈니스용 Skype 화상 통화, IM 및 화면 공유와 같은 다양한 회의 기능을 사용하려면 이 기능을 사용하도록 설정해야 합니다. 온라인 비즈니스용 Skype 및 비즈니스용 Skype 서버 모두 지원됩니다.  <br/> |
|암호 사용  <br/> |디바이스 계정을 암호로 사용하도록 설정해야 합니다. 또는 디바이스 계정 또는 암호로 인증할 Exchange 비즈니스용 Skype 서버.  <br/> |
   
## <a name="advanced-configuration"></a>고급 구성

기본 구성에 대한 속성은 디바이스 계정을 간단한 환경에서 설정할 수 있도록 허용하지만, 디바이스 계정을 성공적으로 사용하려면 환경에 충족해야 하는 디렉터리 계정에 대한 Microsoft Teams 룸 수 있습니다.
  
|**속성**|**목적**|
|:-----|:-----|
|인증서 기반 인증  <br/> |인증서는 Exchange 및 비즈니스용 Skype 서버. 인증서를 배포하려면 관리자로 로그인할 때 인증서를 로드할 수 있습니다.  <br/> |
   
디바이스 계정을 설정하는 가장 쉬운 방법은 원격 계정을 사용하여 Windows PowerShell. Microsoft는 [ ](https://go.microsoft.com/fwlink/?linkid=870105)SkypeRoomProvisioningScript.ps1디바이스 계정으로 전환할 수 있도록 새 디바이스 계정을 만들거나 기존 리소스 계정의 유효성을 검사하는 데 도움이 되는 Microsoft Teams 룸 제공합니다.
  
cmdlet을 통해 Microsoft 365 Office 365 UI를 Windows PowerShell 일부 단계를 수동으로 수행할 수 있습니다. 를 사용하여 디바이스 계정 만들기를 Microsoft 365 [Office 365.](/surface-hub/create-a-device-account-using-office-365)
  
## <a name="see-also"></a>참고 항목

[Microsoft Teams 룸 계획](rooms-plan.md)
  
[Microsoft Teams 룸 콘솔 구성](console.md)
  
[Microsoft Teams 룸 관리](rooms-manage.md)
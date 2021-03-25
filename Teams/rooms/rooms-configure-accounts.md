---
title: Microsoft Teams Rooms에 대한 계정 구성
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
description: Exchange 및 비즈니스용 Skype에서 Microsoft Teams Rooms에 대한 계정을 구성하는 방법을 알아보고 이 항목을 참조하세요.
ms.openlocfilehash: 26879b2c07b859e65255ed84bedd4897b75d5caa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117476"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Microsoft Teams Rooms에 대한 계정 구성
 
이 항목에서 Microsoft Teams Rooms 및 Exchange 및 비즈니스용 Skype와 통합하는 방법에 대해 알아보고자 합니다.
  
이 항목에서는 Microsoft Exchange 및 비즈니스용 Skype에서 Microsoft Teams Rooms에서 사용하는 계정을 만드는 방법을 소개합니다. Microsoft Teams Rooms 디바이스에 대한 배포 지침은 Microsoft Teams Rooms 구성 [콘솔에 설명됩니다.](console.md) 인프라는 다음 구성 중 하나에 빠질 수 있습니다.
  
- 온라인 배포: 조직의 환경은 Microsoft 365 또는 Office 365에 전적으로 배포됩니다. 자세한 내용은 [Microsoft 365 또는 Office 365를 통해 Microsoft Teams Rooms 배포를 참조하세요.](with-office-365.md)
    
- 프레미스 배포: 조직에는 Active Directory, Exchange 및 비즈니스용 Skype 서버가 호스팅되는 제어하는 서버가 있습니다. 자세한 내용은 비즈니스용 [Skype 서버를 통해 Microsoft Teams Rooms 배포를 참조하세요.](with-skype-for-business-server-2015.md)
    
- 하이브리드 배포: 조직에는 Microsoft 365 또는 Office 365를 통해 호스팅된 일부 프레미스 및 일부 온라인 호스팅 서비스가 혼합되어 있습니다. Microsoft Teams Rooms에서는 다음 하이브리드 시나리오가 지원됩니다.
    
  - 비즈니스용 Skype 서버온-프레미스와 Exchange Online 자세한 내용은 [Exchange Online(하이브리드)을 통해 Microsoft Teams Rooms 배포를 참조하세요.](with-exchange-online.md)
    
  - Microsoft Teams 또는 비즈니스용 Skype Online과 프레미스에서 교환합니다. 자세한 내용은 [Exchange on-프레미스(하이브리드)를 통해 Microsoft Teams Rooms 배포를 참조하세요.](with-exchange-on-premises.md)
    
디바이스 설정을 준비하는 방법에 영향을 줄 구성입니다.
  
Microsoft Teams Rooms는 Active Directory, Exchange 및 비즈니스용 Skype에서 "디바이스 계정"을 할당해야 합니다. 이 계정은 모임 일정에 액세스하고 Microsoft Teams 또는 비즈니스용 Skype 연결을 설정하는 데 사용됩니다. 사용자와 함께 모임을 예약하여 이 계정을 예약할 수 있습니다. Microsoft Teams Rooms는 모임에 참가하고 모임 참석자들에게 다양한 기능을 제공할 수 있습니다.
  
> [!IMPORTANT]
> 디바이스 계정이 없는 경우 이러한 기능은 작동하지 않습니다. 
  
모든 디바이스 계정은 단일 Microsoft Teams Rooms 디바이스에 고유하며 몇 가지 설정이 필요합니다.
  
- 디바이스 계정을 올바르게 구성해야 합니다.
    
- Microsoft Teams Rooms가 디바이스 계정의 유효성을 검사하고 적절한 Microsoft 서비스에 도달할 수 있도록 인프라를 구성해야 합니다.
    
> [!IMPORTANT]
> 실제 하드웨어 설치에 앞서 계정 만들기를 잘하는 것이 좋습니다. 이상적으로 계정 준비는 설치 2~3주 전에 시작됩니다. 

Microsoft Teams Rooms에 사용되는 계정은 Microsoft Teams Rooms 인증에 Microsoft 365 또는 Office 365 인증이 필요하기 때문에 AAD(Azure Active Directory) 동기화에서 암호 동기화를 사용하도록 설정해야 합니다. 계정을 설정할 때 계정의 SIP 주소가 AAD의 사용자 주체 이름(UPN)과 일치하는지 확인하세요. 
  
디바이스 계정을 사람들이 회의실 또는 모임 공간의 계정으로 인식하는 리소스 계정으로 생각할 수 있습니다. 해당 회의실을 사용하여 모임을 예약하려는 경우 해당 모임에 계정을 초대합니다. Microsoft Teams Rooms를 가장 효과적으로 사용하려면 각각에 할당된 디바이스 계정과 동일한 작업을 합니다.
  
Microsoft Teams Rooms를 설치하는 모임 공간에 대해 리소스 사서함 계정이 이미 설정되어 있는 경우 해당 리소스 계정을 디바이스 계정으로 변경할 수 있습니다. 완료되면 Microsoft Teams Rooms 디바이스에 디바이스 계정을 추가하기만하면 됩니다. 아래 제공된 디바이스 계정 설정 예제를 참조하세요.
  
추가 구성을 통해 Azure Monitor를 사용하여 Microsoft Teams Rooms 관리 계획, [Azure Monitor를](azure-monitor-plan.md)사용하여 [Microsoft Teams Rooms](azure-monitor-deploy.md)관리 배포 및 Azure [Monitor를](azure-monitor-manage.md)사용하여 Microsoft Teams Rooms 디바이스 관리에 설명된 바와 같이 Microsoft Azure Monitor를 사용하여 원격 관리가 가능합니다. 
  
## <a name="basic-configuration"></a>기본 구성

이러한 속성은 디바이스 계정이 Microsoft Teams Rooms와 함께 작동하기 위한 최소 구성을 나타내고 있습니다. 디바이스 계정에 추가 설정이 필요할 수 있습니다.
  
|**속성**|**목적**|
|:-----|:-----|
|Exchange 사서함(Exchange 2013 SP1 이상 또는 Exchange Online)  <br/> |Exchange 사서함을 사용하여 계정을 사용하도록 설정하면 디바이스 계정에 메일 및 모임 요청을 모두 수신하고 보내고 Microsoft Teams Rooms 디바이스에 모임 일정을 표시할 수 있습니다. Microsoft Teams Room 사서함은 회의실 사서함이 되어야 합니다.  <br/> |
|비즈니스용 Skype가 사용하도록 설정되어 있습니다.  <br/> |화상 통화, IM 및 화면 공유와 같은 다양한 회의 기능을 사용하려면 비즈니스용 Skype를 사용하도록 설정해야 합니다. 비즈니스용 Skype Online 및 비즈니스용 Skype 서버가 모두 지원됩니다.  <br/> |
|암호 사용  <br/> |디바이스 계정을 암호로 사용하도록 설정해야 합니다. 또는 Exchange 또는 비즈니스용 Skype 서버로 인증할 수 없습니다.  <br/> |
   
## <a name="advanced-configuration"></a>고급 구성

기본 구성에 대한 속성은 디바이스 계정을 간단한 환경에서 설정할 수 있도록 허용하지만 Microsoft Teams Rooms가 디바이스 계정을 성공적으로 사용하려면 사용자 환경에 충족해야 하는 디렉터리 계정에 대한 다른 제한 사항이 있을 수 있습니다.
  
|**속성**|**목적**|
|:-----|:-----|
|인증서 기반 인증  <br/> |Exchange 및 비즈니스용 Skype 서버에 인증서가 모두 필요합니다. 인증서를 배포하려면 관리자로 로그인할 때 인증서를 로드할 수 있습니다.  <br/> |
   
디바이스 계정을 설정하는 가장 쉬운 방법은 원격 계정을 사용하여 구성하는 Windows PowerShell. Microsoft는 [ ](https://go.microsoft.com/fwlink/?linkid=870105)SkypeRoomProvisioningScript.ps1디바이스 계정을 만들거나 호환되는 Microsoft Teams Rooms 디바이스 계정으로 전환하는 데 도움이 되는 기존 리소스 계정의 유효성을 검사하는 데 도움이 되는 스크립트인 스크립트를 제공합니다.
  
Microsoft 365 또는 Office 365 UI를 Windows PowerShell cmdlet을 통해 사용하려면 일부 단계를 수동으로 수행할 수 있습니다. [Microsoft 365 또는 Office 365를](/surface-hub/create-a-device-account-using-office-365)사용하여 디바이스 계정 만들기를 참조하세요.
  
## <a name="see-also"></a>참고 항목

[Microsoft Teams 룸 계획](rooms-plan.md)
  
[Microsoft Teams 룸 콘솔 구성](console.md)
  
[Microsoft Teams 룸 관리](rooms-manage.md)
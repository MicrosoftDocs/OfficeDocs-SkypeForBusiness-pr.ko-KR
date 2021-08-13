---
title: Windows 요구 사항 및 소프트웨어 지원
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: '요약: 클라이언트 Windows 계획하는 동안 클라이언트 지원 요구 사항을 비즈니스용 Skype 서버.'
ms.openlocfilehash: e26390920334db03fe1d9f9652759f2018d8306f2d57fce50a32165c4d20bb28
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54317473"
---
# <a name="windows-client-requirements-and-software-support"></a>Windows 요구 사항 및 소프트웨어 지원
 
**요약:** 클라이언트 Windows 계획하는 동안 클라이언트 지원 요구 사항을 비즈니스용 Skype 서버.
  
이 섹션에서는 클라이언트를 지원하는 데 필요한 소프트웨어를 비즈니스용 Skype Windows 설명합니다. 이러한 클라이언트는 설치 또는 Microsoft 365 Office 365 설치될 때 설치될 수 있으며 모든 디바이스에서 비즈니스용 Skype 다운로드에서도 [사용할 수 있습니다.](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
> [!NOTE]
> 비즈니스용 Skype 메시징 및 공동 작업 클라이언트 내에서 모임 관리를 지원하는 Outlook 온라인 모임 추가 비즈니스용 Skype. 
  
**비즈니스용 Skype 및 온라인 모임 추가 기능을 위해 필요한 소프트웨어**

|**시스템 구성 요소**|**지원되는 버전**|
|:-----|:-----|
|Windows 운영 체제  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> Windows 최신 서비스 팩이 있는 Server 2008 R2 이상  <br/> **참고:** 비즈니스용 Skype 및 온라인 모임 추가 비즈니스용 Skype Windows Vista 또는 Windows XP(모든 버전)에서는 지원되지 않습니다. <br/> |
|설치 및 업데이트  <br/> |관리자 권한 및 사용 권한  <br/> |
|브라우저  <br/> |Microsoft Edge  <br/> Internet Explorer 11 인터넷 브라우저  <br/>  Internet Explorer 10 인터넷 브라우저 <br/> Internet Explorer 9 브라우저  <br/> Internet Explorer 8 브라우저  <br/> Internet Explorer 7 브라우저  <br/> Mozilla Firefox 웹 브라우저  <br/>  Google Chrome 웹 브라우저  <br/>**참고:** 조직에서 비즈니스용 SKYPE 사용하여 Microsoft Exchange Online 인증 HTTP 프록시를 배포한 경우 Internet Explorer 8 이상이 필요합니다.           |
|Microsoft Office 통합  <br/> | Outlook 2010 이상 |
|Microsoft Exchange 통합  <br/> | Microsoft Exchange Server 2010 이상  | 
   
## <a name="hardware"></a>하드웨어

클라이언트를 Microsoft 365 Office 하드웨어에 대한 [](https://products.office.com/office-system-requirements) 시스템 요구 사항 및 비즈니스용 Skype 참조하세요.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Skype 모임 앱 및 비즈니스용 Skype Web App 

Skype 앱 및 비즈니스용 Skype Web App 운영 체제 및 브라우저 조합을 지원합니다. 자세한 내용은 [Plan for Meetings clients (Web App and Meetings App)을 참조하세요.](meetings-clients.md) 
  
## <a name="using-mandatory-profiles"></a>필수 프로필 사용

비즈니스용 Skype 기능을 사용하려면 Active Directory 도메인 서비스 필수 프로필을 사용하여 비즈니스용 Skype 합니다. 필수 프로필은 읽기 전용 사용자 프로필이기 때문에 비즈니스용 Skype 회의에 필요한 PKI(공개 키 인프라) 키를 프로필에 저장할 수 없습니다. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>관리에 대한 시스템 비즈니스용 Skype for Windows Phone
 
 
Microsoft 비즈니스용 Skype for Windows Phone 스마트폰 또는 모바일 장치에서 연결하는 조직의 사용자를 위해 IM(인스턴트 메시징), 현재 상태 향상 및 전화 통신을 Windows Professional 있습니다. 모바일 장치를 사용하면 사용자가 모바일 장치의 사용 비즈니스용 Skype. 이 항목에서는 필수 구성 요소와 기술 요구 비즈니스용 Skype for Windows Phone, 필수 구성 요소 및 배포 지침을 식별하는 방법에 대한 계획 고려 사항에 대해 설명합니다.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>비즈니스용 Skype for Windows Phone 선행 준비

다음은 다음과 같은 비즈니스용 Skype for Windows Phone 선행 코드입니다.
  
- Windows Phone 8.1 이상입니다.
    
- 장치 Windows Phone Microsoft에서 사용할 수 있는 최신 업데이트가 있어야 합니다. 자세한 내용은 Windows Phone 8.1 섹션(Windows Phone [업데이트 기록)을 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkID=281961)
    
- 장치에 22MB의 사용 가능한 디스크 공간이 있어야 합니다.
    
- 사용자가 통신사의 음성 및 데이터 요금제에 가입한 상태여야 합니다.


## <a name="see-also"></a>참고 항목

[모임 클라이언트 계획(Web App 및 모임 앱)](meetings-clients.md)
  
[비즈니스용 Skype 클라이언트 요구 사항](mac-requirements.md)

[모든 비즈니스용 Skype 다운로드](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Microsoft 365 Office 요구 사항](https://products.office.com/office-system-requirements)

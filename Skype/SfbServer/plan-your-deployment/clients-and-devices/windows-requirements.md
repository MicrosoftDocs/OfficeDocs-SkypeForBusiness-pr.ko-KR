---
title: Windows 클라이언트 요구 사항 및 소프트웨어 지원
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
description: '요약: 비즈니스용 Skype 서버를 계획하는 동안 Windows 클라이언트 지원 요구 사항을 검토합니다.'
ms.openlocfilehash: 105c4ec8824b2b6f5f7a68349659ca10bb82c737
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816068"
---
# <a name="windows-client-requirements-and-software-support"></a>Windows 클라이언트 요구 사항 및 소프트웨어 지원
 
**요약:** 비즈니스용 Skype 서버를 계획하는 동안 Windows 클라이언트 지원 요구 사항을 검토합니다.
  
이 섹션에서는 비즈니스용 Skype Windows 클라이언트를 지원하는 데 필요한 소프트웨어를 요약합니다. 이러한 클라이언트는 Microsoft 365 또는 Office 365를 설치할 때 설치하며 모든 장치에서 비즈니스용 Skype 다운로드에서도 사용할 [수 있습니다.](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
> [!NOTE]
> Outlook 메시징 및 공동 작업 클라이언트 내에서 모임 관리를 지원하는 비즈니스용 Skype의 온라인 모임 추가 기능을 비즈니스용 Skype와 함께 자동으로 설치합니다. 
  
**비즈니스용 Skype 클라이언트 및 온라인 모임 추가 기능에 필요한 소프트웨어**

|**시스템 구성 요소**|**지원되는 버전**|
|:-----|:-----|
|Windows 운영 체제  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> 최신 서비스 팩이 있는 Windows Server 2008 R2 이상  <br/> **참고:** 비즈니스용 Skype 및 비즈니스용 Skype용 온라인 모임 추가 기능은 Windows Vista 또는 Windows XP(모든 버전)에서 지원되지 않습니다. <br/> |
|설치 및 업데이트  <br/> |관리자 권한 및 사용 권한  <br/> |
|브라우저  <br/> |Microsoft Edge  <br/> Internet Explorer 11 인터넷 브라우저  <br/>  Internet Explorer 10 인터넷 브라우저 <br/> Internet Explorer 9 브라우저  <br/> Internet Explorer 8 브라우저  <br/> Internet Explorer 7 브라우저  <br/> Mozilla Firefox 웹 브라우저  <br/>  Google Chrome 웹 브라우저  <br/>**참고:** 조직에서 인증 HTTP 프록시를 Microsoft Exchange Online 비즈니스용 Skype를 사용하는 경우 Internet Explorer 8 이상이 필요합니다.           |
|Microsoft Office 통합  <br/> | Outlook 2010 이상 |
|Microsoft Exchange 통합  <br/> | Microsoft Exchange Server 2010 이상  | 
   
## <a name="hardware"></a>하드웨어

비즈니스용 Skype 클라이언트를 실행하기 위해 필요한 하드웨어에 대한 Microsoft 365 및 Office [System](https://products.office.com/office-system-requirements) 요구 사항을 참조하세요.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Skype 모임 앱 및 비즈니스용 Skype Web App 

Skype 모임 앱 및 비즈니스용 Skype Web App은 특정 운영 체제 및 브라우저 조합을 지원합니다. 자세한 내용은 모임 클라이언트 [계획(Web App 및 Meetings App)을 참조하세요.](meetings-clients.md) 
  
## <a name="using-mandatory-profiles"></a>필수 프로필 사용

비즈니스용 Skype 회의 기능을 사용하려면 Active Directory 도메인 서비스 필수 프로필을 사용하여 비즈니스용 Skype 클라이언트에 로그인하지 않도록 합니다. 필수 프로필은 읽기 전용 사용자 프로필이기 때문에 비즈니스용 Skype 회의에 필요한 PKI(공개 키 인프라) 키를 프로필에 저장할 수 없습니다. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Windows Phone용 비즈니스용 Skype에 대한 시스템 요구 사항
 
 
Windows Phone용 Microsoft 비즈니스용 Skype는 스마트폰 또는 Windows Professional 모바일 장치에서 연결하는 조직의 사용자를 위해 IM(인스턴트 메시징), 현재 상태 및 전화 통신을 제공합니다. 모바일 장치를 통해 사용자는 비즈니스용 Skype의 도달을 확장할 수 있습니다. 이 항목에서는 필수 구성 요소 및 기술 요구 사항, 필수 구성 요소 및 배포 지침을 식별하는 등 Windows Phone용 비즈니스용 Skype에 대한 계획 고려 사항에 대해 설명합니다.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Windows Phone용 비즈니스용 Skype 사전 준비

다음은 비즈니스용 Skype for Windows Phone의 선행 코드입니다.
  
- Windows Phone 8.1 이상
    
- Windows Phone 장치에는 Microsoft에서 사용할 수 있는 최신 업데이트가 있어야 합니다. 자세한 내용은 Windows Phone 8 업데이트 기록의 [Windows Phone 8.1 섹션을 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkID=281961)
    
- 디바이스에 22MB의 사용 가능한 디스크 공간이 있어야 합니다.
    
- 사용자가 통신사의 음성 및 데이터 요금제에 가입한 상태여야 합니다.


## <a name="see-also"></a>참고 항목

[모임 클라이언트 계획(Web App 및 모임 앱)](meetings-clients.md)
  
[Mac의 비즈니스용 Skype 클라이언트 요구 사항](mac-requirements.md)

[모든 장치에서 비즈니스용 Skype 다운로드](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Microsoft 365 및 Office 시스템 요구 사항](https://products.office.com/office-system-requirements)

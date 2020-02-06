---
title: Windows 클라이언트 요구 사항 및 소프트웨어 지원
ms.author: v-lanac
author: lanachin
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
description: '요약: 비즈니스용 Skype 서버를 계획 하는 동안 Windows 클라이언트 지원 요구 사항을 검토 합니다.'
ms.openlocfilehash: a66887b616461a40c6326a66d982a8bfbe8e9605
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803488"
---
# <a name="windows-client-requirements-and-software-support"></a>Windows 클라이언트 요구 사항 및 소프트웨어 지원
 
**요약:** 비즈니스용 Skype 서버를 계획 하는 동안 Windows 클라이언트 지원 요구 사항을 검토 합니다.
  
이 섹션에서는 비즈니스용 Skype Windows 클라이언트를 지 원하는 데 필요한 소프트웨어에 대해 간략하게 설명 합니다.  이러한 클라이언트는 Office 365가 설치 될 때 설치 되며, [모든 장치에서 비즈니스용 Skype를 다운로드할](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)수도 있습니다.
  
> [!NOTE]
> Outlook messaging 및 공동 작업 클라이언트 내에서 모임 관리를 지 원하는 비즈니스용 Skype 용 온라인 모임 추가 기능이 비즈니스용 Skype를 사용 하 여 자동으로 설치 됩니다. 
  
**비즈니스용 Skype 클라이언트 및 온라인 모임 추가 기능에 필요한 소프트웨어**

|**시스템 구성 요소**|**지원 되는 버전**|
|:-----|:-----|
|Windows 운영 체제  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8  <br/> Windows 7 운영 체제  <br/> Windows Server 2008 R2 이상 최신 서비스 팩  <br/> **참고:** 비즈니스용 skype 및 비즈니스용 skype 용 온라인 모임 추가 기능은 Windows Vista 또는 Windows XP (모든 버전)에서 지원 되지 않습니다. <br/> |
|설치 및 업데이트  <br/> |관리자 권한 및 사용 권한  <br/> |
|브라우저  <br/> |Microsoft Edge  <br/> Internet Explorer 11 인터넷 브라우저  <br/>  Internet Explorer 10 인터넷 브라우저 <br/> Internet Explorer 9 인터넷 브라우저  <br/> Internet Explorer 8 인터넷 브라우저  <br/> Internet Explorer 7 인터넷 브라우저  <br/> Mozilla Firefox 웹 브라우저  <br/>  Google Chrome 웹 브라우저  <br/>**참고:** Microsoft Exchange Online에서 비즈니스용 Skype를 사용 하는 경우 조직이 인증 HTTP 프록시를 배포한 경우 Internet Explorer 8 이상이 필요 합니다.           |
|Microsoft Office 통합  <br/> | Outlook 2010 이상 |
|Microsoft Exchange 통합  <br/> | Microsoft Exchange Server 2010 이상  | 
   
## <a name="hardware"></a>하드웨어

비즈니스용 Skype 클라이언트를 실행 하는 데 필요한 하드웨어에 대 한 Office 365 [시스템 요구 사항을](https://products.office.com/en-us/office-system-requirements) 참조 하세요.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Skype 모임 앱 및 비즈니스용 Skype Web App 

Skype 모임 앱과 비즈니스용 Skype Web App은 운영 체제 및 브라우저의 특정 조합을 지원 합니다. 자세한 내용은 [모임 클라이언트 (웹 앱 및 모임 앱) 계획](meetings-clients.md)을 참조 하세요. 
  
## <a name="using-mandatory-profiles"></a>필수 프로필 사용

비즈니스용 Skype 회의 기능을 사용 하려는 경우 Active Directory 도메인 서비스 필수 프로필을 사용 하 여 비즈니스용 Skype 클라이언트에 로그인 하지 않도록 합니다. 필수 프로필은 읽기 전용 사용자 프로필 이기 때문에 비즈니스용 Skype 회의에 필요한 PKI (공개 키 인프라) 키를 프로필에 저장할 수 없습니다. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Windows Phone 용 비즈니스용 Skype의 시스템 요구 사항
 
 
Windows Phone 용 비즈니스용 Skype는 스마트폰 또는 Windows Professional 모바일 장치에서 연결 하는 조직의 사용자에 게 인스턴트 메시지 (IM), 향상 된 현재 상태 및 전화 접속 기능을 제공 합니다. 모바일 장치를 통해 사용자는 비즈니스용 Skype의 범위를 확장할 수 있습니다. 이 항목에서는 필수 구성 요소와 기술 요구 사항, 필수 구성 요소, 배포 지침을 비롯 하 여 Windows Phone 용 비즈니스용 Skype에 대 한 계획 고려 사항을 설명 합니다.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Windows Phone 필수 조건인 비즈니스용 Skype

다음은 Windows Phone 필수 구성 요소에 대 한 비즈니스용 Skype입니다.
  
- Windows Phone 8.1 이상
    
- Windows Phone 장치에는 Microsoft에서 제공 하는 최신 업데이트가 있어야 합니다. 자세한 내용은 [windows phone 8 업데이트 기록](https://go.microsoft.com/fwlink/p/?LinkID=281961)의 windows phone 8.1 섹션을 참조 하세요.
    
- 장치에는 22mb의 사용 가능한 디스크 공간이 있어야 합니다.
    
- 사용자는 통신 회사의 음성 및 데이터 요금제를 보유 하 고 있어야 합니다.


## <a name="see-also"></a>참고 항목

[모임 클라이언트 계획 (웹 앱 및 모임 앱)](meetings-clients.md)
  
[비즈니스용 Skype for Mac 클라이언트 요구 사항](mac-requirements.md)

[모든 장치에서 비즈니스용 Skype 다운로드](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)
  
[Office 365 시스템 요구 사항](https://products.office.com/en-us/office-system-requirements)

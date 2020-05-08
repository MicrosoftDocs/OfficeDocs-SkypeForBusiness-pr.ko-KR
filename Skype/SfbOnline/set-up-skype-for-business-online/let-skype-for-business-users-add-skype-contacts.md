---
title: 비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
- LIL_Placement
description: '비즈니스용 Skype를 사용 하는 사용자에 게 조직 외부의 비즈니스용 Skype 사용자에 게 연락 하 여 연락처 목록에 추가 하는 방법을 알아봅니다. '
ms.openlocfilehash: 71282fe105c85cadca9aab341fc1b5e6ffbe47d2
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164477"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a>비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용

비즈니스용 Skype를 사용 하는 경우 사용자는 Skype를 사용 하는 모든 사용자와 무료 앱을 검색 하 고 메신저 대화를 할 수 있습니다. 이 문서에서는 Skype 연락처를 추가할 수 있도록 하기 위해 수행 해야 할 작업에 대해 설명 합니다. 
  
이 작업을 수행 하려면 Microsoft 365 또는 Office 365에 [관리자 권한이](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) 있어야 합니다.

![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**
  
1. Microsoft 365 또는 Office 365 관리자 계정으로 로그인 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage)합니다.
    
2. 관리 센터에서 **관리 센터** > **비즈니스용 Skype**로 이동 합니다. 
    
    ![비즈니스용 Skype 관리 센터를 선택 합니다.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. **비즈니스용 Skype 관리 센터**에서 **조직** > **외부 통신**을 선택합니다. 
    
4. 기본적으로 사용자는 비즈니스용 Skype를 사용 하는 전세계의 모든 사용자와 통신할 수 있습니다 (방화벽이이를 허용 하도록 구성 된 경우). 
    
    ![다른 사용자가 비즈니스용 Skype를 사용 하 여 Skype와 통신 하도록 허용을 선택 합니다.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    사용자 들이 Skype 사용자와 채팅 하 고 비즈니스용 Skype를 사용 하는 다른 사람과 채팅을 할 수 없도록 하려면 **허용 된 도메인에 대해서만**을 선택 합니다. Skype 사용자와 접촉을 사용 하도록 설정 하면 skype.com가 백그라운드에서 허용 된 도메인으로 자동으로 추가 됩니다. 
    
    특정 사용자를 제외한 비즈니스용 Skype를 사용 하 여 전세계 다른 모든 회사의 연락처를 허용 하려면 차단 된 도메인을 **제외한**모든 사용자를 선택 하 고 해당 **+** 도메인 추가를 선택 합니다. 모든 사용자는 해당 도메인에 속해 있는 사람을 제외한 사용자에 게 연락할 수 있게 됩니다. (일부 기업은이 옵션을 선택 하는 경우 (예: 소송 내에 있는 경우) 다른 비즈니스에 대 한 연락처가 없는지 확인 해야 합니다.)
    
5. **사용자가 비즈니스용 skype를 사용 하 여 조직 외부의 skype 사용자와 통신 하도록 허용을**선택 합니다. 
    
6.  Windows 방화벽을 사용 중인 경우 비즈니스용 Skype는 필요한 포트를 자동으로 엽니다.
    
    조직에서 다른 솔루션을 사용 하 여 네트워크의 컴퓨터를 인터넷에 연결 하지 못하도록 제한 하는 경우 클라이언트 컴퓨터가 Skype 연결 및 Skype 디렉터리 검색을 위해 모든 [IP 주소 및 url](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) 에 액세스할 수 있는지 확인 합니다. 방화벽 또는 프록시 인프라 구성의 아웃 바운드 허용 목록에 추가 해야 할 수 있습니다.
    
7. **테스트 하는 데 최대 24 시간까지 기다립니다**. 외부 통신 설정을 변경할 때마다 변경 내용이 모든 데이터 센터에 걸친 24 시간이 소요 될 수 있습니다.
    
8. 비즈니스용 Skype 연락처 목록에 Skype 연락처를 찾고 추가 하는 방법을 사용자에 게 보여 줍니다. [비즈니스용 Skype에서 사용자를 검색](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19)하려면이를 가리킵니다.
    
## <a name="test-and-troubleshoot"></a>테스트 및 문제 해결

설정을 테스트 하려면 회사 방화벽 뒤에 있지 않은 Skype에 대 한 연락처가 필요 합니다. Gmail 계정, Outlook.com account 또는 기타 유형의 전자 메일 계정을 사용 하 여 Skype에 로그인 할 수 있습니다.
  
1. 외부 통신 설정을 변경한 후에는 **24 시간까지 테스트를 기다립니다**.
    
2. 비즈니스용 Skype에서 로그 아웃 한 다음 다시 로그인 하 여 Skype 디렉터리를 검색 하는 옵션이 표시 되도록 합니다. 
    
    ![Skype 디렉터리가 강조 표시 되 면 Skype 계정이 있는 사람을 검색할 수 있습니다.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. 비즈니스용 Skype에서 Skype에서 대화 상대를 검색 하 고 채팅 요청을 보냅니다. 
    
    회사 정책 때문에 메시지를 보낼 수 없는 경우에는 [방화벽 설정을](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)다시 확인 해야 합니다. 
    
4. 문제가 방화벽에 해당 하는지 여부를 테스트 하는 또 다른 방법은 커피숍과 같이 방화벽 뒤에 있지 않은 wifi 위치로 이동 하 고 비즈니스용 Skype를 사용 하 여 Skype 연락처에 게 채팅에 대 한 요청을 보내는 것입니다. 
    
   - **Skype 님에 게 요청을 전송 하 고이를 수신 하지 않은 경우**, 채팅에 대 한 요청을 보내 달라고 부탁 하세요. 문제가 Skype와 비즈니스용 Skype 간에 연결을 설정한 경우 종종 해결 됩니다.
    
   - 이제 메시지가 커피숍을 통과 하지만 작업 중이 아닌 경우에는 방화벽이 문제가 되는 것을 알 수 있습니다. 
    
## <a name="what-you-can-and-cant-do"></a>할 수 있는 작업과 수행할 수 없는 작업

- **Mac의 비즈니스용 skype** 에는 skype 연락처를 검색 하 고 통신 하는 기능이 없습니다.
    
- 디렉터리 검색을 사용 하도록 설정 하면 Skype 및 비즈니스용 Skype 사용자를 검색 하 고 찾을 수 있습니다. 일부 이유 때문에 디렉터리를 검색 하 여 해당 파일을 찾지 못한 경우에는 연락처 요청을 보낸 다음 Skype에 로그인 하 여 수락할 수 있으므로 메신저 대화를 할 수 있습니다. 
    
- Google 또는 Facebook과 같은 다른 메신저 공급자와 IM 연결을 허용 하는 것은 불가능 합니다. 비즈니스용 Skype를 사용 하 여 휴대 전화 문자 메시지를 보낼 수 없습니다.

- Skype 연락처와 비즈니스용 Skype 연락처 간에는 음성 또는 영상 통화를 녹화할 수 없습니다.
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a>Skype 연락처를 추가할 때 어떤 기능을 사용할 수 있나요?

Microsoft 계정 (이전의 Windows Live ID)으로 로그인 한 skype 연락처는 비즈니스용 Skype 사용자에 게 말을 할 때 일부 기능이 아닌 일부 기능을 사용할 수 있습니다.
  
|**Skype 연락처에서 이용 가능**|**Skype 연락처에서 사용할 수 없음**|
|:-----|:-----|
| 화상 대화 <br/>  개인 간 인스턴트 메시지 <br/>  현재 상태 <br/> | 여러 파티 메신저 대화 <br/>  세 명 이상에 게 오디오 및 비디오 대화 <br/>  데스크톱 및 프로그램 공유 <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>관련 항목

[사용자가 외부 비즈니스용 Skype 사용자와 연락하도록 허용](allow-users-to-contact-external-skype-for-business-users.md)
  
[비즈니스용 Skype 온라인 설정](set-up-skype-for-business-online.md)

  
 

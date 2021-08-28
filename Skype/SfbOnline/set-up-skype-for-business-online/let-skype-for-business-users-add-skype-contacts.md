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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
- LIL_Placement
description: '조직 외부의 비즈니스용 Skype 사용자가 비즈니스용 Skype 연락처 목록에 추가하는 방법을 참조하세요. '
ms.openlocfilehash: 77fb8098e7adeebd4267aed7f21153b20abd661b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594842"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a>비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

사용자가 비즈니스용 Skype 앱을 사용하는 모든 사용자와 함께 검색하고 IM을 Skype 수 있습니다. 이 문서에서는 연락처를 추가할 수 있도록 해야 하는 Skype 설명합니다. 
  
이 작업을 [위해](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) Microsoft 365 또는 Office 365 권한이 있어야 합니다.

![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**
  
1. 에서 Microsoft 365 또는 Office 365 계정으로 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage) 로그인합니다.
    
2. 관리 센터에서 관리 센터  >  비즈니스용 Skype. 
    
    ![관리 비즈니스용 Skype 선택하세요.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. **비즈니스용 Skype 관리 센터** 에서 **조직** > **외부 통신** 을 선택합니다. 
    
4. 기본적으로 사용자는 방화벽이 허용하도록 구성된 것으로 비즈니스용 Skype 전 세계의 모든 다른 사용자와 통신할 수 있습니다. 
    
    ![다른 사용자와 통신하기 위해 비즈니스용 Skype 수 있도록 Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    사용자가 다른 사용자와 채팅을 Skype 싶지만 다른 사용자와 채팅하지 비즈니스용 Skype 허용된 도메인에만 On을 **선택하세요.** 사용자와의 Skype 사용하도록 설정하면 skype.com 장면 뒤에서 허용되는 도메인으로 자동으로 추가됩니다. 
    
    특정 도메인을 제외한 전 세계의 모든 다른 기업에서 연락처를 비즈니스용 Skype 차단된 도메인을 제외하고 On을 선택하고 해당 도메인을 추가하도록 **+** 선택해야 합니다. 해당 특정 도메인에 있는 사람을 제외한 모든 사용자가 연락할 수 있습니다. (소송 중이기 때문에 다른 비즈니스와의 연락이 없는지 확인해야 하는 경우와 같은 일부 기업에서는 이 옵션을 선택할 수 있습니다.)
    
5. 조직 외부의 비즈니스용 Skype 사용자와 통신할 Skype **를 선택하십시오.** 
    
6.  방화벽을 Windows 경우 비즈니스용 Skype 포트가 자동으로 열립니다.
    
    조직에서 다른 솔루션을 사용하여 네트워크의 컴퓨터를 인터넷에 연결하지 못하도록 제한하는 경우 클라이언트 컴퓨터가 모든 [IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) 주소 및 URL에 액세스하여 Skype 디렉터리 검색을 Skype 수 있습니다. 이 경우 방화벽 또는 프록시 인프라 구성의 아웃바운드 허용 목록에 추가해야 할 수 있습니다.
    
7. **테스트할 때까지 최대 24시간을 기다릴 수 있습니다.** 외부 통신 설정을 변경할 때 변경 내용이 모든 데이터 센터에 채워지는 데 최대 24시간이 걸릴 수 있습니다.
    
8. 사용자에게 연락처를 Skype 연락처 목록에 추가하는 방법을 비즈니스용 Skype 표시됩니다. 를 사용하여 에서 사람 [검색을 비즈니스용 Skype.](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19)
    
## <a name="test-and-troubleshoot"></a>테스트 및 문제 해결

설정을 테스트하려면 회사 방화벽에 Skype 사용자에 대한 연락처가 필요합니다. Gmail 계정, Skype.com 계정 또는 기타 유형의 전자 메일 Outlook 사용하여 로그인할 수 있습니다.
  
1. 외부 통신 설정을 변경한 후 최대 **24시간 대기하여 테스트합니다.**
    
2. 비즈니스용 Skype 로그인한 다음 다시 로그인하여 디렉터리를 검색하는 Skype 있습니다. 
    
    ![디렉터리가 Skype 강조 표시될 때 계정이 있는 Skype 있습니다.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. 비즈니스용 Skype 대화에서 연락처를 검색하고 Skype 요청을 보내 채팅합니다. 
    
    회사 정책으로 인해 보낼 수 없는 메시지가 표시될 경우 방화벽 설정을 다시 [확인해야 합니다.](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) 
    
4. 방화벽이 문제가 있는지 여부를 테스트하는 또 다른 방법은 커피숍과 같은 방화벽 뒤에 있지 않은 wifi 위치로 이동하고, 비즈니스용 Skype 사용하여 채팅을 위해 Skype 요청을 보내는 것입니다. 
    
   - **요청에 Skype** 받은 적이 없는 경우 채팅 요청을 보내달라고 요청합니다. 문제가 해결되는 Skype 비즈니스용 Skype 연결합니다.
    
   - 이제 메시지가 커피숍에서 전달되지만 직장에 있는 경우가 아니라면 문제가 방화벽인 것을 알 수 있습니다. 
    
## <a name="what-you-can-and-cant-do"></a>할 수 있는 일과 할 수 없는 일

- **비즈니스용 Skype Mac에서** 연락처를 검색하고 통신할 수 Skype 없습니다.
    
- 디렉터리 검색을 사용하도록 설정하면 사용자를 검색하고 Skype 비즈니스용 Skype 있습니다. 어떤 이유로 디렉터리를 검색하여 찾을 수 없는 경우 연락처 요청을 보낸 다음 로그인하여 Skype 수락할 수 있으므로 해당 디렉터리와 함께 IM할 수 있습니다. 
    
- Google 또는 Facebook과 같은 다른 IM 공급자와 IM 연결을 허용할 수 없습니다. 휴대폰 문자 메시지를 보내기 위해 비즈니스용 Skype 수 없습니다.

- 연락처와 연락처 간에 오디오 또는 화상 통화를 Skype 수 비즈니스용 Skype 없습니다.
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a>연락처를 추가할 때 어떤 Skype 있나요?

Skype Microsoft 계정으로 로그인한 연락처(이전 Windows 라이브 ID)는 사용자와 대화할 때 일부 기능을 얻을 수 비즈니스용 Skype 있습니다.
  
|**연락처에서 Skype 사용할 수 있습니다.**|**연락처에서 사용할 Skype 없습니다.**|
|:-----|:-----|
| 비디오 대화 <br/>  사람 대 사람 인스턴트 메시징 <br/>  현재 상태 <br/> | 다자 IM 대화 <br/>  3명 이상과 오디오 및 비디오 대화 <br/>  데스크톱 및 프로그램 공유 <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>관련 주제

[사용자가 외부 비즈니스용 Skype 사용자와 연락하도록 허용](allow-users-to-contact-external-skype-for-business-users.md)
  
[비즈니스용 Skype 온라인 설정](set-up-skype-for-business-online.md)

  
 

---
title: 비즈니스용 Skype 서버에서 Office Web Apps 서버와의 통합 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: '요약: 웹 회의에 PowerPoint 프레젠테이션을 사용하도록 Office Web Apps 서버와 비즈니스용 Skype 서버 간의 통합을 구성하는 방법을 알아보는 이 항목을 참조하세요.'
ms.openlocfilehash: 005bd9fe7d7fece7d488935002e7146fc5a9ffe4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820468"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 Office Web Apps 서버와의 통합 구성
 
**요약:** 웹 회의에 PowerPoint 프레젠테이션을 사용하도록 Office Web Apps 서버와 비즈니스용 Skype 서버 간의 통합을 구성하는 방법을 알아보는 이 항목을 참조하세요.
  
비즈니스용 Skype 서버는 Office Web Apps 서버를 사용하여 웹 회의에 대한 PowerPoint 프레젠테이션을 처리합니다. 이 방법의 이점에 대한 자세한 내용은 비즈니스용 Skype 서버의 회의 [계획(Plan for conferencing)을 참조하십시오.](../../plan-your-deployment/conferencing/conferencing.md)
  
Office Web Apps 서버를 사용하도록 비즈니스용 Skype 서버를 구성하려면 먼저 Office Web Apps 서버가 이미 배포 및 구성되어 있는지 확인해야 합니다. Office Web Apps 서버에 대한 자세한 내용은 인프라 [배포: Office Online Server 문서를 참조하십시오.](https://go.microsoft.com/fwlink/p/?linkid=257525) 
  
Office Web Apps 서버를 성공적으로 설치하고 웹 팜을 올바르게 구성한 후 비즈니스용 Skype 서버 토폴로지에서 Office Web Apps 서버 검색 URL을 비즈니스용 Skype 서버 토폴로지에 추가하여 새 서버와 통신하도록 비즈니스용 Skype 서버를 구성해야 합니다. 
  
> [!NOTE]
> Office Web Apps 서버의 최신 이니션은 비즈니스용 Skype 서버에서 지원되는 Office Online Server입니다. 자세한 내용은 [Office Online Server 설명서를 참조하십시오.](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx) 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Office Web Apps 서버와 통신하도록 비즈니스용 Skype 서버 구성

토폴로지에 Office Web Apps 서버를 추가하기 위해 다음 단계를 완료합니다.
  
1. 비즈니스용 Skype 서버 토폴로지 작성기 열기.
    
2. **토폴로지 작성기** 대화 상자에서 **기존 배포에서 토폴로지 다운로드** 를 선택한 후 **확인** 을 클릭합니다.
    
3. **토폴로지를 다른 이름으로 저장** 대화 상자에서 **파일 이름** 상자에 토폴로지 문서 이름(예: **PreWebAppsServerTopology**)을 입력한 후 **저장** 을 클릭합니다. 이 토폴로지는 나중에 새 토폴로지에 문제가 발생한 경우 검색하고 다시 게시할 수 있습니다.
    
4. 토폴로지 작성기에서 비즈니스용 **Skype** 서버를 확장하고, 사이트의 이름을 확장하고, **Enterprise Edition 프런트** 엔드 풀을 확장하고, 풀 중 하나의 이름을 마우스 오른쪽 단추로 클릭한 다음 속성 편집을 클릭합니다. 
    
5. **속성 편집** 대화 상자의 **일반** 탭에서 **Office Web Apps Server 연결** 제목을 찾아서 **새로 만들기** 를 클릭합니다(또는 드롭다운 목록에서 기존 Office Web Apps Server 선택).
    
6. **새 Office Web Apps Server 정의** 대화 상자에서 **Office Web Apps Server FQDN** 상자에 Office Web Apps Server 컴퓨터의 FQDN(정규화된 도메인 이름)을 입력합니다. 이렇게 하면 Office Web Apps Server 검색 URL이 **Office Web Apps Server 검색 URL** 상자에 자동으로 입력됩니다.
    
   - Office Web Apps 서버가 비즈니스용 Skype 서버와 같은 네트워크 영역과 모든 프레미스에 설치되어 있는 경우 **Office Web Apps 서버가** 외부 네트워크(경계/인터넷)에 배포되는 옵션을 선택하지 않습니다.
    
   - Office Web Apps Server가 내부 방화벽 외부에 배포된 경우 **Office Web Apps Server가 외부 네트워크에 배포되어 있습니다(경계/인터넷).** 옵션을 선택합니다.
    
7. **새 Office Web Apps Server 정의** 대화 상자에서 **확인** 을 클릭한 후 **속성 편집** 대화 상자에서 **확인** 을 클릭합니다. 그러면 검색 URL이 풀의 연결 중 하나로 나열됩니다.
    
Office Web Apps Server와 연결해야 하는 각 풀에 대해 이 프로세스를 반복해야 합니다.
  
토폴로지에 검색 URL을 추가한 후 업데이트된 토폴로지가 게시되어야 합니다. 이렇게 하려면 토폴로지 작성기에서 다음을 수행합니다.
  
1. **동작** 을 클릭하고, **토폴로지 게시** 를 클릭합니다.
    
2. 토폴로지 게시 마법사의 **토폴로지 게시** 페이지에서 **다음** 을 클릭합니다.
    
3. **게시 마법사 완료** 페이지에서 **마침** 을 클릭합니다.
    
4. 토폴로지 작성기를 닫습니다.
    
## <a name="configure-access-for-external-users"></a>외부 사용자에 대한 액세스 구성

외부 사용자(즉, 조직의 방화벽 외부에서 로그온하는 사용자)가 Office Web Apps 서버 PowerPoint 프레젠테이션에 액세스할 수 있도록 하려는 경우 Office Web Apps 서버 및 역방향 프록시 서버를 사용해야 합니다. 또한 사용자가 서버에 연결할 수 있도록 하는 웹 사이트 게시 규칙을 만들고 구성해야 합니다. 
  
## <a name="validate-the-configuration"></a>구성 유효성 검사

Office Web Apps 서버가 토폴로지에 추가되고 해당 토폴로지가 게시된 후 비즈니스용 Skype 서버 이벤트 로그에 두 개의 새 이벤트 로그 이벤트가 표시됩니다. 먼저 LS 데이터 MCU 이벤트(이벤트 ID 41034)를 추가해야 합니다. 이 이벤트는 Office Web Apps 서버가 검색된 것으로 보고됩니다.
  
 **웹 회의 서버 Office Web Apps 서버가 검색되어 PowerPoint 콘텐츠가 사용하도록 설정됩니다.**
  
또한 백 오피스 Office Web Apps 서버 URL을 보고하는 또 다른 LS 데이터 MCU 이벤트(이벤트 ID 41032)도 표시되어야 합니다. 예를 들면 다음과 같은 로그가 표시되어야 합니다.
  
 **웹 회의 서버 Office Web Apps 서버 검색이 성공했습니다.**
  
 **Office Web Apps 서버 내부 발표자 페이지: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ;embed=**
  
 **Office Web Apps 서버 내부 참석자 페이지: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp ;embed=true&amp;=**
  
외부 사용자에 대한 액세스를 구성한 경우 다음 사항도 볼 수 있습니다.
  
 **Office Web Apps 서버 외부 발표자 페이지: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ;embed**
  
 **Office Web Apps 서버 내부 참석자 <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp> 페이지:**
  
이벤트 ID가 41033인 LS 데이터 MCU 이벤트가 표시되는 경우 이는 Office Web Apps 서버가 검색되지 않았음을 의미합니다. 이 경우 비즈니스용 Skype 서버는 새로 구성된 Office Web Apps 서버를 검색하는 데 필요한 수만큼 시도합니다. 검색 프로세스가 계속 실패할 경우에는 Office Web Apps 서버를 토폴로지 문서에서 제거하고 업데이트된 토폴로지를 게시한 다음 연결 문제가 해결된 후에 Office Web Apps 서버를 토폴로지에 다시 추가해 봅니다.
  
Office Web Apps 서버가 올바르게 구성되고 검색 프로세스에서 인식된 경우 비즈니스용 Skype 클라이언트 쌍 간에 PowerPoint 프레젠테이션을 공유하여 Office Web Apps 서버가 예상대로 작동하고 있는지 확인할 수 있습니다. 사용자 A가 PowerPoint 프레젠테이션을 로드하고 표시할 수 있으며 사용자 B가 모임에 참가하고 해당 프레젠테이션을 볼 수 있는 경우에는 Office Web Apps 서버가 작동 중인 것입니다.
  
Office Web Apps 서버가 올바르게 구성된 것으로 나타나도 PowerPoint 프레젠테이션을 공유하려고 할 때 "서버 연결 문제로 인해 일부 공유 기능을 사용할 수 없습니다."라는 오류 메시지가 표시될 수 있습니다. 이러한 오류 메시지가 나타나면 새 Office Web Apps 서버와 연결된 프런트 엔드 서버를 다시 시작해야 합니다.
  


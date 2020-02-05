---
title: 비즈니스용 Skype 서버에서 Office Web Apps 서버와 통합 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: '요약: Office Web Apps 서버와 비즈니스용 Skype 서버 간 통합을 구성 하 여 PowerPoint 프레젠테이션을 웹 회의로 설정 하는 방법을 알아보려면이 항목을 읽으십시오.'
ms.openlocfilehash: b20646f31a7925ca66180c1580751574152047e5
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768351"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 Office Web Apps 서버와 통합 구성
 
**요약:** 이 항목에서는 Office Web Apps 서버와 비즈니스용 Skype Server의 통합을 구성 하 여 PowerPoint 프레젠테이션 웹 회의를 사용 하는 방법에 대해 알아봅니다.
  
비즈니스용 Skype Server는 Office Web Apps Server를 통해 웹 회의를 위한 PowerPoint 프레젠테이션을 처리 합니다. 이 접근 방법의 이점에 대 한 자세한 내용은 비즈니스용 [Skype 서버의 회의 계획](../../plan-your-deployment/conferencing/conferencing.md)을 참조 하세요.
  
Office Web Apps server를 사용 하도록 비즈니스용 Skype 서버를 구성 하려면 먼저 Office Web Apps 서버가 이미 배포 및 구성 되어 있는지 확인 해야 합니다. Office Web Apps 서버에 대 한 자세한 내용은 [인프라 배포 문서 Office Online Server](https://go.microsoft.com/fwlink/p/?linkid=257525)를 참조 하세요. 
  
Office Web Apps Server를 성공적으로 설치 하 고 웹 팜을 올바르게 구성한 후에는 Office Web Apps 서버 검색 URL을 비즈니스용 Skype에 추가 하 여 비즈니스용 Skype 서버가 새 서버와 통신 하도록 구성 해야 합니다. 서버 토폴로지. 
  
> [!NOTE]
> Office Web Apps Server의 최신 이터레이션을 비즈니스용 Skype 서버에서 지 원하는 Office Online Server 라고 합니다. 자세한 내용은 [Office Online 서버 설명서](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx)를 참조 하세요. 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>비즈니스용 Skype 서버에서 Office Web Apps 서버와 통신 하도록 구성

토폴로지에 Office Web Apps 서버를 추가 하려면 다음 단계를 완료 하세요.
  
1. 비즈니스용 Skype 서버 토폴로지 작성기를 엽니다.
    
2. **토폴로지 작성기** 대화 상자에서 **기존 배포의 토폴로지 다운로드** 를 선택한 다음 **확인**을 클릭 합니다.
    
3. 다른 이름 **으로 토폴로지 저장** 대화 상자에서 **파일 이름** 상자에 토폴로지 문서의 이름 (예: **PreWebAppsServerTopology**)을 입력 한 다음 **저장**을 클릭 합니다. 새 토폴로지에서 문제가 발생 하는 경우 나중에이 토폴로지를 검색 하 고 다시 게시할 수 있습니다.
    
4. 토폴로지 작성기에서 **비즈니스용 Skype 서버**를 확장 하 고, 사이트 이름을 확장 하 고, **Enterprise Edition 프런트 엔드 풀**을 확장 하 고, 풀 중 하나의 이름을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.
    
5. **속성 편집** 대화 상자의 **일반** 탭에서 **Office Web apps 서버 연결** 제목을 찾은 다음 **새로 만들기** (또는 드롭다운 목록에서 기존 Office Web apps 서버 선택)를 클릭 합니다.
    
6. **새 Office Web Apps 서버 정의** 대화 상자에서 office web APPS 서버 **Fqdn** 상자에 office ONLINE server 컴퓨터의 fqdn (정규화 된 도메인 이름)을 입력 합니다. 이렇게 하면 office Web Apps 서버 검색 URL이 **Office Web Apps server 검색 url** 상자에 자동으로 입력 됩니다.
    
   - Office Web Apps 서버가 비즈니스용 Skype 서버와 같은 네트워크 영역에 설치 되어 있는 경우 **외부 네트워크 (즉, 경계/인터넷)에 Office Web Apps 서버를 배포** 하는 옵션을 선택 하지 않아야 합니다.
    
   - Office Web Apps 서버가 내부 방화벽 외부에 배포 된 경우 **Office Web Apps 서버를 외부 네트워크 (즉, 외곽/인터넷)에 배포**하는 옵션을 선택 합니다.
    
7. **새 Office Web Apps 서버 정의** 대화 상자에서 **확인**을 클릭 한 다음 **속성 편집** 대화 상자에서 **확인** 을 클릭 합니다. 그러면 검색 URL이 풀의 연결 중 하나로 나열 됩니다.
    
Office Web Apps 서버와 연결 되어야 하는 각 풀에 대해이 프로세스를 반복 해야 합니다.
  
검색 URL을 토폴로지에 추가한 후에는 업데이트 된 토폴로지를 게시 해야 합니다. 토폴로지 작성기에서 다음을 수행 합니다.
  
1. **작업** 을 클릭 한 다음 **토폴로지 게시**를 클릭 합니다.
    
2. 토폴로지 게시 마법사의 **토폴로지 게시** 페이지에서 **다음**을 클릭 합니다.
    
3. **게시 마법사 완료** 페이지에서 **마침을**클릭 합니다.
    
4. 토폴로지 작성기를 닫습니다.
    
## <a name="configure-access-for-external-users"></a>외부 사용자에 대 한 액세스 권한 구성

외부 사용자 (즉, 조직의 방화벽 외부에서 로그온 하는 사용자)가 Office Web Apps Server PowerPoint 프레젠테이션에 액세스할 수 있도록 하려면 Office Web Apps 서버와 리버스 프록시 서버를 사용 해야 합니다. 또한 사용자가 서버에 연결할 수 있게 해 주는 웹 사이트 게시 규칙을 만들고 구성 해야 합니다. 
  
## <a name="validate-the-configuration"></a>구성 유효성 검사

Office Web Apps 서버를 토폴로지에 추가 하 고 해당 토폴로지가 게시 된 후에는 비즈니스용 Skype 서버 이벤트 로그에 새 이벤트 로그 이벤트가 두 개 표시 되어야 합니다. 첫째, LS 데이터 MCU 이벤트 (이벤트 ID 41034)를 추가 해야 합니다. 이 이벤트는 Office Web Apps 서버가 검색 되었음을 보고 합니다.
  
 **웹 회의 서버 Office Web Apps 서버가 검색 되었으며, PowerPoint 콘텐츠를 사용할 수 있습니다.**
  
이 외에도, Office Web Apps 서버 Url을 보고 하는 다른 LS 데이터 MCU 이벤트 (이벤트 ID 41032)가 표시 되어야 합니다. 예를 들어 다음과 같은 항목이 표시 됩니다.
  
 **웹 회의 서버 Office Web Apps 서버 검색에 성공 했습니다.**
  
 **Office Web Apps Server 내부 발표자 페이지: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp; embed =**
  
 **Office Web Apps Server 내부 참석자 페이지: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp; embed = true&amp;=**
  
외부 사용자에 대 한 액세스를 구성한 경우 다음과 비슷한 항목이 표시 됩니다.
  
 **Office Web Apps 서버 외부 발표자 페이지: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp; embed**
  
 **Office Web Apps Server 내부 참석자 페이지: <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>;**
  
이벤트 ID가 41033 인 LS 데이터 MCU 이벤트가 표시 되는 경우 Office Web Apps 서버 검색에 실패 했음을 의미 합니다. 이 경우 비즈니스용 Skype 서버는 새로 구성 된 Office Web Apps 서버를 검색 하는 데 필요한 횟수 만큼 시도해 봅니다. 검색 프로세스가 반복적으로 실행 되지 않는 경우 토폴로지 문서에서 Office Web Apps 서버를 제거 하 고 업데이트 된 토폴로지를 게시 한 다음 연결 문제가 해결 된 후에 Office Web Apps 서버를 토폴로지에 다시 추가 해 보세요.
  
Office Web Apps 서버가 올바르게 구성 되어 있고 검색 프로세스에서 인식 되는 경우 비즈니스용 Skype 클라이언트 쌍 간에 PowerPoint 프레젠테이션을 공유 하 여 Office Web Apps 서버가 예상 대로 작동 하는지 확인할 수 있습니다. 사용자 A가 PowerPoint 프레젠테이션을 로드 하 고 표시할 수 있으며, 사용자 B가 모임에 참가 하 여 해당 프레젠테이션을 볼 수 있으면 Office Web Apps 서버가 작동 하는 것입니다.
  
Office Web Apps Server가 올바르게 구성 되어 있더라도 PowerPoint 프레젠테이션을 공유 하려고 하면 "서버 연결 문제로 인해 일부 공유 기능을 사용할 수 없습니다." 오류 메시지가 나타날 수 있습니다. 해당 오류 메시지가 나타나면 새 Office Web Apps 서버와 연결 된 프런트 엔드 서버 (또는 서버)를 다시 시작 해야 합니다.
  


---
title: 모니터링할 비즈니스용 Skype 서버 컴퓨터 구성
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: '요약: 모니터링할 비즈니스용 Skype 서버 2019 컴퓨터에 Operations Manager 에이전트 파일을 설치 하 고 System Center 프록시로 작동 하도록 컴퓨터를 구성 합니다.'
ms.openlocfilehash: ae5e1c2ab3d8eb17449c391ea321cfb44272368f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189759"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>모니터링할 비즈니스용 Skype 서버 컴퓨터 구성

**요약:** 비즈니스용 Skype Server 2019 컴퓨터에 Operations Manager 에이전트 파일을 설치 하 고 시스템 센터 프록시로 작동 하도록 컴퓨터를 구성 합니다.

모니터링할 각 비즈니스용 Skype Server 2019 컴퓨터는 관리 서버에 대 한 존재를 자체 보고할 수 있어야 합니다. 이 프로세스를 사용 하도록 설정 하려면 모니터링할 각 컴퓨터에 Operations Manager 에이전트 파일을 설치 해야 합니다. 에이전트 파일을 설치한 후에는 컴퓨터를 System Center 프록시로 작동 하도록 구성 해야 합니다. 이러한 절차를 수행 하기 전에 먼저이 컴퓨터에 비즈니스용 Skype 서버를 설치 하 고 구성 해야 합니다.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>경계 네트워크 외부에 있는 감시자 노드에 인증서 설치
<a name="watcher_node_outside"> </a>

경계 네트워크 (예: 비즈니스용 Skype Server Edge Server)에서 실행 되는 System Center Operations Manager 에이전트 (예: 외부 가상 트랜잭션 감시자 노드 등) 또는 Active Directory 신뢰 경계를 넘어 서 작업을 수행 해야 할 수 있습니다. System Center Operations Manager 게이트웨이 서버의 구성입니다. 이 서버 역할은 루트 관리 서버와 신뢰 관계가 없는 에이전트를 사용 하도록 설정 하 여 알림을 발생 시킵니다. 자세한 내용은 [Operations Manager 2012에서 게이트웨이 서버 관리](https://technet.microsoft.com/en-us/library/hh212823.aspx)를 참조 하세요.

이러한 위치 중 하나에 에이전트를 배포 하는 경우에는 감시자 노드가 System Center Operations Manager에 알림을 보낼 수 있도록 하는 인증서도 요청 하 고 구성 해야 합니다. 이 프로세스를 간소화 하기 위해 Operations Manager 팀은 감시자 노드 컴퓨터에서 올바른 형식의 인증서를 요청 하 고 설치할 수 있는 유틸리티 집합을 만들었습니다. 이 유틸리티를 다운로드 하는 방법에 대 한 자세한 내용은 [인증서 생성 마법사로 쉽게 만들 수 있는 비도메인 가입 에이전트에 대 한 인증서 가져오기를](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)참조 하세요.

### <a name="installing-the-operation-manager-agent-files"></a>Operation Manager 에이전트 파일 설치

1. System Center 설정 미디어에서 Setup.exe를 두 번 클릭 **합니다**.

2. System Center operations Manager 설치 마법사의 설치 에이전트에서 **Operations Manager 에이전트 설치**(선택적 설치의 경우)를 클릭 합니다.

3. System Center 설정 마법사의 System Center Operations Manager 설치 마법사 시작 페이지에서 **다음**을 클릭 합니다.

4. 대상 폴더 페이지에서 Operations Manager 에이전트 파일을 설치할 폴더를 선택 하 고 **다음**을 클릭 합니다.

5. 관리 그룹 구성 페이지에서 **관리 그룹 정보 지정** 을 선택 하 고 **다음**을 클릭 합니다.

6. 관리 그룹 구성 페이지의 **관리 그룹 이름** 상자에 Operations Manager 관리 그룹의 이름을 입력 한 다음 관리 서버에 operations manager 서버의 호스트 이름 (예: atl-scom-001)을 입력 합니다. ** **상자입니다. Operations Manager에 사용 되는 포트 번호를 변경한 경우 **관리 서버 포트** 상자에 새 포트 번호를 입력 합니다. 그렇지 않으면 포트를 기본값인 5723으로 두고 **다음**을 클릭 합니다.

7. 에이전트 작업 계정 페이지에서 **로컬 시스템** 을 선택 하 고 **다음**을 클릭 합니다.

8. Microsoft 업데이트 페이지에서 **Microsoft 업데이트 사용 안 함을** 선택 하 고 **다음**을 클릭 합니다.

9. 설치 준비 페이지에서 **설치**를 클릭 합니다.

10. System Center Operations Manager 설치 마법사 완료 페이지에서 **마침을**클릭 합니다.

11. **끝내기**를 클릭 합니다.

System Center 2012의 경우 **시작**을 클릭 하 고 **모든 프로그램**을 클릭 한 다음 **System Center operations manager 2012**을 클릭 하 고 **Operations 2012 Manager Shell**을 클릭 하 여 에이전트가 만들어졌는지 확인할 수 있습니다. Operations Manager 셸에서 다음 Windows PowerShell 명령을 입력 한 다음 enter 키를 누릅니다.
```
Get-SCOMAgent
```

모든 Operations Manager 에이전트 목록이 표시 됩니다.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>System Center Discovery에 참가 하도록 비즈니스용 Skype Server 컴퓨터 구성
<a name="watcher_node_outside"> </a>

새 비즈니스용 Skype 서버 에이전트가 System Center Operations Manager의 검색 프로세스에 참여 하도록 하려면 System Center Operations Manager 콘솔이 설치 된 각 컴퓨터에서 다음 절차를 완료 해야 합니다.

1. 관리 탭에서 **에이전트 관리**를 클릭 합니다.

2. **검색 마법사** 를 클릭 하 고 컴퓨터를 검색할 마법사를 완료 합니다.

3. 상태 에이전트 서비스를 다시 부팅 합니다. 서비스를 다시 부팅 하면 새 컴퓨터를 강제로 검색 합니다. 서비스를 다시 부팅 하지 않으면 시스템 센터 Operations Manager에서 새 컴퓨터를 검색 하기 전에 4 시간 정도 걸릴 수 있습니다.

4. Operations Manager 이벤트 로그에 오류 이벤트가 기록 되지 않았는지 확인 합니다.

5. 에이전트가 성공적으로 푸시된 컴퓨터가 "에이전트 관리" 목록에 표시 되며 수동으로 설치 된 에이전트가 "보류 중인 관리" 아래에 표시 되는 경우 컴퓨터 이름을 클릭 하 고 승인 합니다.

6. 컴퓨터의 이름을 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다. 속성 대화 상자의 보안 탭에서 **이 에이전트가 프록시로 작동할 수 있도록 허용을 선택 하 고 다른 컴퓨터에서 관리 되는 개체를 검색**한 다음 **확인**을 클릭 합니다.



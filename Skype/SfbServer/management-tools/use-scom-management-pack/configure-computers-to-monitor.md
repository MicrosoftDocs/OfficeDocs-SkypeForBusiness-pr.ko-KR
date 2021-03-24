---
title: 모니터링할 비즈니스용 Skype 서버 컴퓨터 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b24ea184-4b3e-4277-a244-157afb4b368b
description: '요약: 모니터링할 비즈니스용 Skype 서버 2015 컴퓨터에 Operations Manager 에이전트 파일을 설치하고 System Center 프록시 역할을 하도록 컴퓨터를 구성합니다.'
ms.openlocfilehash: bb4dc64a1c04bbef1b6cb0e391fc27568edfef43
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111684"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>모니터링할 비즈니스용 Skype 서버 컴퓨터 구성

**요약:** 모니터링할 비즈니스용 Skype 서버 2015 컴퓨터에 Operations Manager 에이전트 파일을 설치하고 System Center 프록시 역할을 하도록 컴퓨터를 구성합니다.

모니터링할 각 비즈니스용 Skype 서버 2015 컴퓨터는 해당 존재를 관리 서버에 자체 보고할 수 있어야 합니다. 이 프로세스를 사용하도록 설정하려면 모니터링할 각 컴퓨터에 Operations Manager 에이전트 파일을 설치해야 합니다. 에이전트 파일을 설치한 후 System Center 프록시 역할을 하도록 컴퓨터를 구성해야 합니다. 이러한 절차를 수행하기 전에 먼저 이러한 컴퓨터에 비즈니스용 Skype 서버를 설치하고 구성해야 합니다.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>경계 네트워크 외부에 위치한 감시자 노드에 인증서 설치
<a name="watcher_node_outside"> </a>

경계 네트워크(예: 비즈니스용 Skype 서버 에지 서버) 또는 엔터프라이즈 외부(예: 외부 가상 트랜잭션 감시자 노드) 또는 Active Directory 트러스트 경계를 통해 실행되는 System Center Operations Manager 에이전트는 System Center Operations Manager 게이트웨이 서버를 구성해야 할 수 있습니다. 이 서버 역할을 사용하면 루트 관리 서버와 트러스트 관계가 없는 에이전트가 경고를 발생할 수 있습니다. 자세한 내용은 [Managing Gateway Servers in Operations Manager 2012를 참조합니다.](/previous-versions/system-center/system-center-2012-R2/hh212823(v=sc.12))

이러한 위치 중 하나에 에이전트를 배포하는 경우 감시자 노드가 System Center Operations Manager로 알림을 보낼 수 있도록 하는 인증서를 요청하고 구성해야 합니다. 이 프로세스를 간소화하기 위해 Operations Manager 팀은 감시자 노드 컴퓨터에 올바른 유형의 인증서를 요청하고 설치할 수 있게 해주는 유틸리티 집합을 만들었습니다. 자세한 내용을 보고 이러한 유틸리티를 다운로드하려면 인증서 생성 마법사를 통해 도메인에 가입되지 않은 에이전트에 대한 인증서 [얻기를 참조합니다.](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)

### <a name="installing-the-operation-manager-agent-files"></a>Operation Manager Agent 파일 설치

1. System Center 설치 미디어에서 를 두 **번Setup.exe.**

2. System Center Operation Manager 설치 마법사에서 Install Agent under Optional Installations에서 **Operations Manager Agent** 설치를 클릭합니다.

3. System Center 설치 마법사의 System Center Operations Manager 설치 시작 마법사 페이지에서 다음 을 **클릭합니다.**

4. 대상 폴더 페이지에서 Operations Manager 에이전트 파일이 설치될 폴더를 선택하고 다음 을 **클릭합니다.**

5. 관리 그룹 구성 페이지에서 관리 그룹 **정보 지정을 선택하고** 다음 을 **클릭합니다.**

6. 관리 그룹 구성 페이지의 **관리 그룹 이름** 상자에 Operations Manager 관리 그룹의 이름을 입력하고 **관리 서버** 상자에 Operations Manager 서버의 이름(예: atl-scom-001)을 입력합니다. Operations Manager에서 사용하는 포트 번호를 변경한 경우 관리 서버 포트 상자에 새 포트 번호를 **입력합니다.** 그렇지 않으면 포트를 기본값인 5723으로 그대로 두고 다음 을 **클릭합니다.**

7. 에이전트 작업 계정 페이지에서 로컬 시스템을 **선택하고** 다음 을 **클릭합니다.**

8. Microsoft 업데이트 페이지에서 Microsoft 업데이트를 사용하지 않습니다.를 선택하고 **다음** 을 **클릭합니다.**

9. 설치 준비 완료 페이지에서 **설치** 를 클릭합니다.

10. System Center Operations Manager 설치 마법사 완료 중(Completing the System Center Operations Manager Setup wizard) 페이지에서 **마침** 을 클릭합니다.

11. **끝내기** 를 클릭합니다.

이 System Center 2012 시작, 모든 프로그램, System Center   **Operations Manager 2012, Operations** **2012** Manager Shell을 클릭하여 에이전트가 만들어졌습니다. Operations Manager 셸에서 다음 Windows PowerShell 입력한 다음 Enter를 누를 수 있습니다.
```PowerShell
Get-SCOMAgent
```

모든 Operations Manager 에이전트의 목록이 표시됩니다.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>System Center 검색에 참여할 비즈니스용 Skype 서버 컴퓨터 구성
<a name="watcher_node_outside"> </a>

새 비즈니스용 Skype 서버 에이전트가 System Center Operations Manager의 검색 프로세스에 참여하는지 확인하려면 System Center Operations Manager 콘솔이 설치된 각 컴퓨터에서 다음 절차를 완료해야 합니다.

1. 관리 탭에서 **에이전트에서 관리** 를 클릭합니다.

2. 검색 **마법사를 클릭하고** 검색할 컴퓨터의 마법사를 완료합니다.

3. 상태 에이전트 서비스를 다시 시작하십시오. 서비스를 다시 시작하면 새 컴퓨터 검색이 강제로 됩니다. 서비스를 다시 시작하지 않는 경우 System Center Operations Manager에서 새 시스템을 검색하기까지 4시간 정도 걸릴 수 있습니다.

4. Operations Manager 이벤트 로그에 기록된 오류 이벤트가 없는지 확인

5. 에이전트가 푸시된 컴퓨터는 "에이전트 관리" 목록에 표시되고 에이전트가 수동으로 설치된 컴퓨터는 "보류 중인 관리"에 표시되고 컴퓨터 이름을 클릭하고 승인합니다.

6. 컴퓨터의 이름을 마우스 오른쪽 단추로 클릭하고 **속성** 을 클릭합니다. 속성 대화 상자의 보안 탭에서 **이 에이전트를 프록시로 허용하고 다른 컴퓨터에서 관리되는 개체 검색** 을 선택하고 **확인** 을 클릭합니다.
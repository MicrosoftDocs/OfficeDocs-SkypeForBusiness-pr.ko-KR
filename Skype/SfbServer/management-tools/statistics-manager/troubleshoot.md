---
title: 비즈니스용 Skype 서버 통계 관리자 문제 해결
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: '요약: 비즈니스용 Skype 서버 대한 Statistics Manager 배포 문제를 해결하려면 이 항목을 읽어보세요.'
ms.openlocfilehash: a7604b15826ee55e127cd24447b0557b24b78548
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675280"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>비즈니스용 Skype 서버 통계 관리자 문제 해결

**요약:** 비즈니스용 Skype 서버 대한 Statistics Manager 배포 문제를 해결하려면 이 항목을 참조하세요.

이 항목에서는 애플리케이션 이벤트 로그에 표시될 수 있는 이벤트와 이벤트를 수정하기 위해 수행할 수 있는 적절한 작업을 설명하여 Statistics Manager 배포 문제를 해결하는 방법을 설명합니다. 이 항목에는 다음 섹션이 포함되어 있습니다.

- [에이전트 이벤트](troubleshoot.md#BKMK_Agent)

- [수신기 이벤트](troubleshoot.md#BKMK_Listener)

- [웹 사이트 문제](troubleshoot.md#BKMK_Website)

## <a name="agent-events"></a>에이전트 이벤트
<a name="BKMK_Agent"> </a>

- **1000** — 프로세서 리미터(작업 개체)를 설정할 수 없음 - 알 수 없는 이유

- **1001** - 프로세스에서 프로세스 제한은 허용되지 않습니다(작업 개체 내에 이미 있음).

    에이전트는 Windows 작업 개체 내에서 실행하여 메모리 공간을 자동으로 제한합니다. 에이전트가 시작되지 않고 이러한 이벤트 항목이 이벤트 로그에 있는 경우 작업 개체를 서버에서 인스턴스화할 수 없습니다. 이 작업을 위해 구성 파일의 값을 변경하여 상한 메모리 제한을 제거할 수 있습니다.

  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    "MaxProcessMemoryMB"를 검색하고 다음과 같이 값을 "0"으로 변경합니다.

  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > 이 변경이 수행되면 에이전트는 일반적으로 100MB의 메모리를 계속 사용 \< 하게 되지만 기본값과 같이 강제로 300MB로 제한되지는 않습니다. 이 변경이 수행되면 에이전트가 호스트 컴퓨터에서 많은 양의 메모리를 사용하지 않도록 메모리 사용량을 면밀히 모니터링하는 것이 좋습니다.

- **2000** - 클라이언트 초기화 실패

- **2001** - 원본 IP에서 서비스에 연결할 수 없음

  에이전트가 수신기 컴퓨터에 연결할 수 없는 경우 다음을 확인합니다.

  1. 수신기 서비스가 수신기 컴퓨터에서 실행되고 있는지 확인합니다. 그렇지 않은 경우 Redis가 해당 서버에서 실행 중인지 확인하고 수신기 서비스를 다시 시작합니다.

     수신기 컴퓨터에서 Statistics Manager 이벤트 로그를 확인하여 Statistics Manager 수신기 서비스 자체에 문제가 없는지 확인합니다.

  2. 텔넷과 같은 연결 도구를 사용하여 에이전트 컴퓨터에서 올바른 포트의 수신기로의 연결을 확인합니다.

     그렇지 않은 경우 수신기 컴퓨터가 연결된 네트워크 유형(프라이빗/퍼블릭/도메인)에 대해 수신기 컴퓨터에서 들어오는 방화벽 규칙이 사용하도록 설정되어 있는지 확인합니다. 수신기 컴퓨터가 도메인에 가입되지 않은 경우 네트워크가 공용으로 나열될 수 있으며, 이 경우 Statistics Manager와 함께 설치된 방화벽 규칙이 기본적으로 적용되지 않습니다.

- **4000** - 수신기에서 서버 정보를 다운로드하지 못했습니다(알 수 없는 이유)

  - **4001** — 수신기 토폴로지에서 서버를 찾을 수 없음

    이 오류는 서버가 수신기에 성공적으로 연결되었지만 서버가 수신기 캐시의 토폴로지에 추가되지 않은 경우에 발생합니다. 해결 옵션:

  - 토폴로지 가져오기에 대한 지침을 따랐는지 확인합니다. [토폴로지 가져오기를 참조하세요](deploy.md#BKMK_ImportTopology).

  - 에이전트가 토폴로지(예: SQL AlwaysOn 클러스터의 노드)에 나열되지 않은 서버에 있는 경우 [토폴로지 가져오기](deploy.md#BKMK_ImportTopology)의 지침에 따라 에이전트를 수동으로 추가해야 합니다.

  - **4002** - 잘못된 수신기 암호

    에이전트가 사용하려는 암호화된 암호가 수신기 자체의 서비스 암호와 일치하지 않습니다. 에이전트를 제거하고 올바른 서비스 암호를 사용하여 다시 설치합니다.

  - **4003** - 인증서 지문 불일치

    설치 시 에이전트에 제공된 인증서 지문이 수신기가 현재 사용 중인 인증서의 지문과 일치하지 않으므로 연결이 거부됩니다. 에이전트를 제거하고 올바른 인증서 지문을 사용하여 다시 설치합니다.

  - **4004** - 잘못된 응답 또는 HttpStatusCode

    수신기가 예상된 상태로 응답하지 않습니다.

  - 연결이 프록시된 경우 프록시 구성을 확인합니다.

  - 수신기 컴퓨터의 StatsMan 로그에서 구성 관련 문제를 확인합니다.

  - **4005** — XML을 직렬화 해제할 수 없습니다.

    수신기 서버의 서버 정보가 손상되었거나 에이전트와 수신기 컴퓨터 간에 버전이 일치하지 않을 수 있습니다. 버전이 일치하는지 확인하고 수신기 이벤트 로그에서 문제가 있는지 확인합니다.

## <a name="listener-events"></a>수신기 이벤트
<a name="BKMK_Listener"> </a>

- **10000** — 시작 실패 알 수 없는 이유(복구할 수 없으며 결과적으로 서비스가 중지/충돌)

  - **10001** — 구성 문제

    일반적으로 이 문제는 [listener_install_location] \PerfAgentListener.exe.config 파일이 수동으로 수정되어 애플리케이션에서 읽을 수 없는 경우에 발생합니다.

  - **10002** - HTTP 수신기 초기화 오류

    이 이벤트는 일반적으로 설치 중에 URL ACL이 제대로 설정되지 않았거나 SSL 인증서가 잘못되었을 때 기록됩니다. 구성의 인증서가 유효한지 확인합니다. 이 경우 [통계 관리자 배포](deploy.md#BKMK_Deploy)의 지침에 따라 수신기를 다시 설치합니다.

  - **10003** — Redis 실패

  - **10004** - 인프라 오류 캐싱

  - **10007** — 설정(redis에 저장됨)

    수신기가 Redis에 연결하거나 캐시에서 올바른 형식의 데이터를 검색할 수 없으며 시작할 수 없습니다. Redis 서비스가 서버에서 제대로 시작되고 구성되었는지 확인합니다.

  - **10005** — 서버 정보 검색/구문 분석

    Redis 캐시의 토폴로지 정보가 잘못되었습니다. 먼저 Redis 및 수신기를 다시 시작합니다. 오류가 계속되면 [토폴로지 가져오기를 참조하여 토폴](deploy.md#BKMK_ImportTopology) 로지 데이터를 다시 만듭니다.

- **10100** — Redis PING 중단

  - **10101** - Redis PING이 계속 중단됨(60초마다)

  - **30100** - Redis PING 중단 복원됨

    수신기가 Redis에 연결할 수 없는 경우 기록됩니다. Redis가 시작되고 수신기와 Redis 간의 네트워크 연결을 사용할 수 있는지 확인합니다.

- **10200** — Redis 쓰기 중단

  - **10201** - Redis 쓰기 중단이 계속됨(60초마다)

  - **30100** - Redis 쓰기 중단 해결됨

    수신기가 Redis 캐시에 쓸 수 없는 경우 기록됩니다. Redis가 시작되고 수신기와 Redis 간의 네트워크 연결을 사용할 수 있는지 확인합니다.

- **30000** — 성공적으로 시작됨

    수신기가 시작될 때마다 기록됩니다.

- **22000** - Statistics Manager 에이전트 초기화에 성공했습니다.

- **23000** — EventLogQueryManager 초기화 성공(처음 또는 실패 후)

- **24000** - serverinfo 초기화 성공(처음 또는 실패 후)

- **25000** — 수신기가 게시에 실패한 후 다시 온라인 상태가 됩니다(또는 처음 성공한 게시물).

- **5000** - 데이터를 게시하기 위해 오프라인으로 수신기 시작

- **5001** - 수신기는 연장된 기간 동안 여전히 오프라인 상태입니다.

    이러한 이벤트는 문제를 모니터링/경고/지우는 데 유용할 수 있습니다.

## <a name="website-issues"></a>웹 사이트 문제
<a name="BKMK_Website"> </a>

- Chrome의 반복적인 로그인 프롬프트 - 버전 1.1에서 해결된 버그입니다. Chrome 브라우저에서 로그인 프롬프트가 반복되는 경우 최신 버전의 Statistics Manager로 업그레이드해야 합니다. 실행 중인 웹 사이트의 버전을 확인하려면 다음을 수행합니다.

  - 파일 탐색기 열기(기본 디렉터리)

  - StatsManHubWebSite.dll 마우스 오른쪽 단추로 클릭하고 해당 속성을 봅니다.

  - KHI 가로 보기 또는 카운터 세부 정보 보기에서 컴퓨터를 찾을 수 없는 경우 사이트 및 풀의 구성원인지 확인합니다. 그렇지 않으면 해당 보기에 표시되지 않습니다. 토폴로지에서 서버에 대한 사이트 및 풀을 정의하는 방법에 대한 자세한 내용은 [토폴로지 가져오기를](deploy.md#BKMK_ImportTopology) 참조하세요.

  - 제품 버전은 설명 세부 정보에 표시됩니다.

## <a name="for-more-information"></a>자세한 내용
<a name="BKMK_Website"> </a>

자세한 내용은 다음 항목을 참조하세요.

- [비즈니스용 Skype 서버 통계 관리자에 대한 계획](plan.md)

- [비즈니스용 Skype 서버 통계 관리자 배포](deploy.md)

- [비즈니스용 Skype 서버 통계 관리자 업그레이드](upgrade.md)

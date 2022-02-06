---
title: 비즈니스용 Skype 서버 통계 관리자에 대한 계획
ms.reviewer: null
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
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: '요약: 이 항목을 통해 통계 관리자를 비즈니스용 Skype 서버.'
---

# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a>비즈니스용 Skype 서버 통계 관리자에 대한 계획

**요약:** 통계 관리자에 대한 자세한 내용은 이 비즈니스용 Skype 서버.

 통계 관리자는 비즈니스용 Skype 서버 상태 및 성능 데이터를 실시간으로 비즈니스용 Skype 서버 수 있는 강력한 도구입니다. 몇 초마다 수백 대의 서버로 성능 데이터를 폴링하고 통계 관리자 웹 사이트에서 결과를 즉시 확인할 수 있습니다.

통계 관리자를 사용하여 지속적인 성능 문제를 식별하고, 환경의 계획된 변경 결과를 확인하고, 정전 해결을 추적하는 등 다양한 정보를 확인할 수 있습니다. 통계 관리자는 KHI(키 상태 표시기) 임계값을 사용하여 구성하며 배포의 고유한 요구 사항에 맞게 사용자 지정될 수 있습니다.

단일 서버가 모든 서버 쪽 Statistics Manager 구성 요소를 호스팅하는 사내 배포에 통계 관리자를 배포할 수 있습니다. 통계 관리자 배포에 대한 자세한 내용은 [Deploy Statistics Manager for 비즈니스용 Skype 서버](deploy.md). 통계 관리자의 기존 배포가 있지만 아직 릴리스 2.0으로 업그레이드하지 않은 경우 릴리스 [2.0](plan.md#BKMK_WhatsNew)의 새로운 버전 및 업그레이드 통계 관리자 [for 비즈니스용 Skype 서버](upgrade.md).

이 항목에는 다음 섹션이 포함되어 있습니다.

- [기능 및 기능](plan.md#BKMK_Features)

- [릴리스 2.0의 새로운](plan.md#BKMK_WhatsNew)

- [구성 요소](plan.md#BKMK_Components)

- [사내 배포](plan.md#BKMK_DeploymentOptions)

- [요구 사항](plan.md#BKMK_Requirements)

- [보안 고려 사항](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a>기능 및 기능
<a name="BKMK_Features"> </a>

통계 관리자를 사용하여 다음을 할 수 있습니다.

- 실시간으로 모든 서버의 원시 데이터를  볼 수 있습니다. (데이터는 매우 높은 속도로 샘플링된 후 1초 미만의 웹 사이트로 전송됩니다.)

- 특정 역할에 대해 집계된 데이터 보기 예를 들어 프런트 엔드 서버, 중재 서버, 에지 서버 등입니다.

- 드릴다운하여 특정 사이트, 사이트 내의 특정 풀 및 풀 내의 특정 서버에 대한 데이터를 볼 수 있습니다.

- 기본적으로 선택한 카운터가 표시  있도록 사용자 지정 차트를 만들 수 있습니다.

- x 축과 y 축을 모두 확대/축소하고 이동하거나 x 축에서만 이동합니다.

- 날짜 범위 또는 포인트를 사용하여 데이터를 필터링합니다.

- KHIS(핵심 상태 표시기)를 기반으로 서버 성능을 볼 수 있습니다. KHIS는 정의된 정상 범위를 나타내는 성능 카운터 모음을 나타내고 있습니다.

- 각 카운터에 대한 자세한 메트릭을  시청합니다.

- 여러 인구 또는 서버의 데이터를 비교합니다.

- 대시보드 서비스에 현재 데이터를 보고하지 않는 에이전트를 식별할 수 있는 카운터 보고서를 볼 수 있습니다.

- 차트 데이터의 특정 인스턴스를 파일에 저장합니다.

- 업데이트를 포함하여 실시간으로 KHIS를 확인합니다. 사용 기록 보기를 사용하도록 설정하면 새 오류만 표시됩니다.

  - 한 번씩 모든 KHIS 보기

  - 서버당 KHIS 보기(가로 보기)

  - KHI 정의 보기

## <a name="whats-new-in-release-20"></a>릴리스 2.0의 새로운
<a name="BKMK_WhatsNew"> </a>

다음은 릴리스 2.0의 새로운 버전에 대해 설명하는 예제입니다. 통계 관리자의 기존 배포가 있는 경우 아직 업그레이드하지 않은 경우 [Upgrade Statistics Manager for 비즈니스용 Skype 서버](upgrade.md).

- 에지 미디어, 패브릭 상태, 풀 장애 조치(Failover) 및 등록 시나리오에 대한 시나리오 보기가 추가되었습니다.

- 여러 새 카운터가 SQL 서버, 비즈니스용 Skype 카운터가 추가되었습니다.

- 통계 관리자 에이전트에 대한 감시자 노드 통합 - 에이전트가 감시자 노드에 설치된 경우 가상 트랜잭션 통계를 통계 관리자에 카운터로 다시 보고합니다.

- 다양한 안정성 및 성능 개선

실행 중인 통계 관리자 웹 사이트의 버전을 확인:

- 파일 탐색기에서 (기본 디렉터리) C:\Program Files\비즈니스용 Skype 서버 StatsMan WebSite\bin을  열습니다.

- 마우스 오른쪽 단추를 StatsManHubWebSite.dll 속성 보기

- 제품 버전이 설명 세부 정보에 표시됩니다.

## <a name="components"></a>구성 요소
<a name="BKMK_Components"> </a>

통계 관리자는 다음 구성 요소로 구성됩니다.

- **에이전트.** 모니터링되는 각 서버에서 실행되는 간단한 에이전트입니다. 에이전트는 로컬 집계를 사용하여 구성 가능한 높은 속도의 성능 카운터 폴링을 허용합니다.

- **수신기.** 모든 에이전트에서 데이터를 수신하고 모집단에서 데이터를 집계하는 서버 쪽 API입니다.

- **허브.** 시스템의 클라이언트 API 역할을 하며, 웹 서버에서 실행되고, 웹 사이트를 통해 연결된 클라이언트에 대한 실시간 데이터 업데이트를 제공합니다. (허브는 웹 사이트 msi의 일부로 자동으로 설치됩니다.)

- **웹 사이트.** 시스템에서 사용할 수 있는 모든 기능을 모아서 사용하는 사용자 인터페이스입니다.

또한 통계 관리자에는 메모리 내 캐싱을 위한 오픈 소스 데이터 구조 서버인 **Redis** 가 필요합니다. Redis 다운로드에 대한 자세한 내용은 [Deploy Statistics Manager를 참조하십시오](deploy.md#BKMK_Deploy) .

## <a name="on-premises-deployment"></a>사내 배포
<a name="BKMK_DeploymentOptions"> </a>

On-premises deployment, a single server hosts all of the server-side Statistics Manager components.

다음 다이어그램은 통계 관리자 웹 사이트, 허브, 수신기 및 Redis 캐싱 시스템이 단일 시스템에서 호스팅되는 사내 배포를 보여줍니다. 통계 관리자는 세 개의 비즈니스용 Skype 모니터링하고 있습니다. 각 서버에는 수신기로 데이터를 전송하는 단일 에이전트가 있습니다. 사용자는 단일 웹 사이트에 연결하여 통계 관리자로 집계된 모든 데이터를 볼 수 있습니다.

![Stats Manager On-premises deployment.](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a>요구 사항
<a name="BKMK_Requirements"> </a>

통계 관리자를 배포하기 전에 다음 소프트웨어, 네트워킹 및 하드웨어 요구 사항을 고려해야 합니다.

### <a name="software-requirements"></a>소프트웨어 요구 사항

- Windows Server 2016 및 2019

- IIS(자동으로 설치)

- Redis

- Statistics Manager 서비스(자동으로 설치)

- PSExec - 원격 에이전트 배포를 위해 필요합니다.

- .NET 4.5(2012 R2에 포함) - 에이전트 및 서버 쪽 구성 요소에 필요
- 통계 [비즈니스용 Skype 서버 Real-Time(64](https://www.microsoft.com/en-in/download/details.aspx?id=57518)비트) 다운로드

### <a name="networking-requirements"></a>네트워킹 요구 사항


|**호스팅 서버**|**Agents**|**수신기**|
|:-----|:-----|:-----|
|최소 기가비트 전체 이면 네트워킹.  <br/> |수신기와 통신하기 위한 아웃바운드 TCP 포트 8443(사용자 지정 가능한 포트 번호)  <br/> |수신기 포트는 모든 서버에서 동일해야 합니다.  <br/> |
|인바운드 TCP 포트 80 또는 443이 열려 웹 사이트를 호스트합니다.  <br/> |||
|에이전트가 통신할 수 있도록 인바운드 TCP 포트 8443(사용자 지정 가능한 포트 번호)입니다.  <br/> |||

설치하는 동안 수신기 및 웹 사이트에 대한 방화벽 포트가 자동으로 만들어집니다. 에이전트의 경우 설치에서는 기본적으로 아웃바운드 TCP 연결이 허용된다고 가정합니다.

### <a name="hardware-requirements"></a>하드웨어 요구 사항

단일 서버가 모든 서버 쪽 Statistics Manager 구성 요소를 호스팅하는 사내 배포에서는 RAM이 16GB, CPU가 4개인 서버는 평균적으로 초당 약 150개의 샘플을 지원할 수 있습니다. 지원할 수 있는 카운터/에이전트 수를 결정하기 위해 다음 계산을 사용합니다.

서버 100 \*개 카운터 80 \* 개 각 에이전트의 분당 샘플 1개/60초 = 초당 샘플 133개

## <a name="security-considerations"></a>보안 고려 사항
<a name="BKMK_Security"> </a>

서버 간의 모든 트래픽이 암호화됩니다.

- 암호화된 HTTPS 트래픽은 에이전트에서 수신기 서버로 포트 8443(기본적으로)을 통해 전송됩니다.

- 에이전트는 서버의 SSL 지문을 확인하여 수신기 서버가 예상되는 받는 사람이 되도록 합니다. 에이전트는 체인 확인 대신 인증서 지문 확인을 사용합니다. 자체 서명된 인증서를 사용할 수 있기 때문에 전체 인증서 유효성 검사를 하지 않습니다.

- 에이전트가 수신기 인증에 만족하면 에이전트가 암호를 제공한 다음 수신기에서 확인됩니다.

- 에이전트는 수신기 연결을 통해 성능 데이터를 전송하기 시작합니다.

## <a name="for-more-information"></a>자세한 내용
<a name="BKMK_Security"> </a>

자세한 내용은 다음 항목을 참조하세요.

- [비즈니스용 Skype 서버 통계 관리자 배포](deploy.md)

- [비즈니스용 Skype 서버 통계 관리자 업그레이드](upgrade.md)

- [비즈니스용 Skype 서버 통계 관리자 문제 해결](troubleshoot.md)

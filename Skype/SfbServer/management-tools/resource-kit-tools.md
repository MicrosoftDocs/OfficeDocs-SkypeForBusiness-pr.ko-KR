---
title: 비즈니스용 Skype 서버 2015 리소스 키트 도구 문서
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: 이 항목에서는 각 도구의 용도와 사용 예를 포함 하 여 비즈니스용 Skype Server 2015 리소스 키트의 도구에 대해 설명 합니다. 비즈니스용 Skype Server 2015 리소스 키트는 비즈니스용 Skype Server 2015를 배포 하 고 관리 하는 IT 관리자를 위한 일상적인 작업을 더욱 쉽게 수행할 수 있도록 지원 합니다. 예를 들어 웹 회의 데이터 도구를 사용 하 여 온라인 모임 중에 사용자가 업로드 한 데이터를 쉽게 제어할 수 있습니다. SEFAUtil 도구를 사용 하 여 사용자에 대 한 대리인 착신 전환 및 응답을 설정할 수 있습니다. IT 관리자가 이러한 도구를 사용 하 여 비즈니스용 Skype 서버 2015을 보다 효율적으로 관리 하도록 하는 것이 좋습니다.
ms.openlocfilehash: c34998cf86de6bc85d384081c0db77f70edb68f9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191214"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a>비즈니스용 Skype 서버 2015 리소스 키트 도구 문서

이 항목에서는 각 도구의 용도와 사용 예를 포함 하 여 비즈니스용 Skype Server 2015 리소스 키트의 도구에 대해 설명 합니다. 비즈니스용 Skype Server 2015 리소스 키트는 비즈니스용 Skype Server 2015를 배포 하 고 관리 하는 IT 관리자를 위한 일상적인 작업을 더욱 쉽게 수행할 수 있도록 지원 합니다. 예를 들어 **웹 회의 데이터** 도구를 사용 하 여 온라인 모임 중에 사용자가 업로드 한 데이터를 쉽게 제어할 수 있습니다. **SEFAUtil** 도구를 사용 하 여 사용자에 대 한 대리인 착신 전환 및 응답을 설정할 수 있습니다. IT 관리자가 이러한 도구를 사용 하 여 비즈니스용 Skype 서버 2015을 보다 효율적으로 관리 하도록 하는 것이 좋습니다.

## <a name="installation-of-the-resource-kit-tools"></a>리소스 키트 도구 설치

비즈니스용 Skype 서버 2015 리소스 키트를 설치 하려면 다운로드 센터에서 [Ocsreskit. msi](https://www.microsoft.com/en-us/download/details.aspx?id=52631) 를 다운로드 하세요.

설치를 수행 하려면 **Ocsreskit. msi** 를 실행 합니다. .Msi는 다음 경로에 있는 모든 도구를 설치 합니다: **비즈니스 서버 2015 용 Files%\Skype% ResKit**. 자체 포함 된 실행 파일의 도구는이 폴더에 있습니다. 지원 파일도 있는 도구는 고유한 하위 폴더에 있습니다.

## <a name="supported-environments"></a>지원 되는 환경

비즈니스용 skype server 2015 리소스 키트는 비즈니스용 skype server 2015에 필요한 사양에 부합 하는 서버에 설치 되어 있어야 하며, 일반적으로 비즈니스용 Skype 서버 2015를 실행 하는 데 사용 됩니다.

## <a name="resource-kit-tools-overview"></a>리소스 키트 도구 개요

다음은 비즈니스용 Skype 서버 2015 리소스 키트에 제공 되는 도구 목록입니다. 요구 사항 및 예제 사용법을 비롯 한 각 도구에 대 한 설명은 다음 섹션에서 다룹니다.

- [ABSConfig](resource-kit-tools.md#ABSConfig)

- [대역폭 정책 서비스 모니터](resource-kit-tools.md#bpsm)

- [대역폭 이용률 분석기](resource-kit-tools.md#bua)

- [전화 Parkometer](resource-kit-tools.md#callpark)

- [DBAnalyze](resource-kit-tools.md#dba)

- [저장소 서비스 데이터 가져오기](resource-kit-tools.md#Issd)

- [LCSSync](resource-kit-tools.md#LCSSync)

- [조회 사용자 콘솔](resource-kit-tools.md#LUC)

- [MsTurnPing](resource-kit-tools.md#MsTurnPing)

- [네트워크 구성 뷰어](resource-kit-tools.md#NCV)

- [응답 그룹 에이전트 라이브](resource-kit-tools.md#RGAL)

- [SEFAUtil](resource-kit-tools.md#SEFAUtil)

- [SYSPrep. ps1](resource-kit-tools.md#SYSPrep)

- [할당 되지 않은 번호 알림 마이그레이션](resource-kit-tools.md#UNAM)

- [웹 회의 데이터](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a>ABSConfig
<a name="ABSConfig"> </a>

ABSConfig (주소록 서비스 구성 도구)는 관리자가 비즈니스용 Skype 서버 2015에서 주소록 서비스 구성을 사용자 지정 하는 데 도움이 되는 관리 도구입니다. 또한이 도구는 비즈니스용 Skype Server 2015 관리자가 기본 주소록 서비스 설정을 복원할 수 있도록 합니다.

### <a name="description"></a>설명

ABSConfig는 관리자가 주소록 서비스와 관련 된 Active Directory 도메인 서비스 특성을 구성할 수 있도록 하는 그래픽 사용자 인터페이스 응용 프로그램입니다.

도구의 주요 시나리오는 다음과 같습니다.

- 관리자가 Active Directory 도메인 서비스의 특성을 비즈니스용 Skype 서버 2015의 특성에 매핑할 수 있도록 합니다.

- 관리자가 주소록 서비스 파일에 포함 하거나 제외할 Active Directory 도메인 서비스 특성을 지정할 수 있도록 설정 합니다.

- 관리자가 기본 주소록 서비스 설정을 복원할 수 있도록 설정 합니다.

ABSConfig 도구는 ABSConfig 파일을 사용 하 여 시작할 수 있습니다. 도구는 **속성 구성** 탭으로 열립니다. 이 표에는 Active Directory 도메인 서비스 특성을 비즈니스용 Skype Server 2015의 특성 필드에 매핑하고 특정 특성 필터에 따라 주소록 서비스 파일에 포함 하거나 제외할 사용자를 지정 하는 옵션이 있습니다. 또한 주소록 파일에 포함할 전화 번호 값을 사용자 지정 하는 옵션도 있습니다. **기본값으로 복원** 옵션을 사용 하면 관리자가 주소록 서비스 설정을 기본값으로 복원할 수 있습니다.

> [!NOTE]
> 광고 특성을 다른 OC 필드 이름으로 다시 매핑하는 방법은 주소록 파일 다운로드에만 적용 되며 주소록 웹 쿼리에서 지원 되지 않습니다.

### <a name="output"></a>결과물

ABSConfig는 데이터베이스에 주소록 서비스 구성을 저장 합니다.

```
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a>것

ABSConfig는 비즈니스용 Skype Server 2015 주소록 서비스를 빠르고 쉽게 사용자 지정할 수 있는 방법을 제공 합니다.

### <a name="requirements"></a>요구 사항

#### <a name="computer"></a>컴퓨터

ABSConfig는 비즈니스용 Skype 서버 2015이 설치 되어 있는 도메인 가입 컴퓨터 에서만 실행할 수 있습니다. 비즈니스용 Skype Server 2015, Enterprise Edition의 경우, 설치 중에 주소록 서비스를 사용 하는 프런트 엔드 서버에서이 도구를 실행할 수 있습니다.

#### <a name="network"></a>사설망

컴퓨터가 프런트 엔드 풀 및 백 엔드 데이터베이스에 연결할 수 있어야 합니다.

#### <a name="software"></a>소프트웨어

ABSConfig 도구를 실행 하기 전에 다음 소프트웨어 구성 요소를 설치 해야 합니다.

- 비즈니스용 Skype 서버 2015

#### <a name="users"></a>사용자

비즈니스용 Skype 서버 2015 배포를 업데이트 하는 데 필요한 권한이 있는 관리자입니다.

### <a name="examples"></a>예제

ABSConfig는 명령 프롬프트에서 **ABSConfig** 를 입력 하 여 시작할 수 있습니다. 아래에는 ABSConfig tool 사용자 인터페이스가 나와 있습니다.

![ABSConfig.exe 도구.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a>요약

ABSConfig 도구는 관리자에 게 비즈니스용 Skype Server 2015 주소록 서비스를 사용자 지정할 수 있는 빠르고 간편한 도구를 제공 합니다.

## <a name="bandwidth-policy-service-monitor"></a>대역폭 정책 서비스 모니터
<a name="bpsm"> </a>

대역폭 정책 서비스 모니터 도구는 관리자가 다음 목록을 볼 수 있도록 고안 되었습니다.

1. 구성 된 모든 비즈니스용 Skype 서버 2015 대역폭 정책 서비스 (인증 및 핵심)가 토폴로지에 있습니다.

2. 각 서비스가 다른 대역폭 정책 서비스 및 Edge 서버에 대해 수행 하는 연결

3. 네트워크 구성 문서에 구성 된 모든 링크와 각 대역폭 정책 서비스에서 보고 하는 실시간 대역폭 사용량이

### <a name="description"></a>설명

대역폭 정책 서비스 모니터 도구는 GUI 기반 응용 프로그램으로 구현 됩니다. 관리자가이 도구를 시작 하 고 있습니다.

도구가 시작 되 면 토폴로지에서 대역폭 정책 서비스 목록을 검색 하려고 시도 합니다. 초기 업데이트를 완료 한 후 창 왼쪽의 창에는 자신이 속한 클러스터 별로 그룹화 된 서비스 목록이 채워집니다.

관리자가 특정 대역폭 정책 서비스를 선택 하면 오른쪽에 있는 창에 특정 서비스에 대 한 정보가 표시 됩니다. 또한이 창에는 정보를 표시 하는 두 개의 기본 탭이 있습니다.

#### <a name="machine-info-tab"></a>컴퓨터 정보 탭

**컴퓨터 정보** 탭에는 선택한 대역폭 정책 서비스에 대 한 세부 정보와 선택한 대역폭 정책 서비스가 다른 서비스에 대해 적용 한 모든 연결의 목록 및 상태가 표시 됩니다.

#### <a name="topology-info-tab"></a>토폴로지 정보 탭

**토폴로지 정보** 탭에는 네트워크 구성 설정에 구성 된 모든 링크 목록이 표시 됩니다. 각 링크에 오디오 및 비디오 대역폭 용량이 표시 됩니다. 또한 현재 사용 되는 대역폭이 Kbps와 용량에 대 한 백분율로 표시 됩니다. 이 도구는 색 코드를 사용 하 여 용량에 가까운 사용률을 가진 링크를 강조 표시 하므로 관리자가 이러한 링크를 빠르게 격리할 수 있습니다.

> [!NOTE]
>  대역폭 정책 서비스 모니터 도구를 구성 된 대역폭 정책 서비스에 연결할 때 오류가 발생 하는 경우 **컴퓨터 정보** 및 **토폴로지 정보** 탭의 정보가 채워지지 않습니다. 그러나 처음에는 도구를 연결할 수 있지만 그 이후에는 서비스 연결이 끊어질 수 있습니다. 이런 경우 관리자는 오래 된 정보를 볼 수도 있습니다. 각 탭에 **마지막으로 업데이트** 된 타임 스탬프가 있으므로 관리자가 특정 대역폭 정책 서비스에 대 한 데이터를 마지막으로 업데이트 한 날짜를 볼 수 있습니다.

### <a name="output"></a>결과물

명령줄 출력은 없습니다. 프로그램 출력은 주 GUI (그래픽 사용자 인터페이스) 내에 포함 되어 있습니다.

### <a name="purpose"></a>것

대역폭 정책 서비스 모니터 도구의 목적은 토폴로지에 정의 된 각 대역폭 정책 서비스의 상태를 관리자가 볼 수 있도록 하는 것입니다. 또한 관리자는 네트워크 구성 문서에 정의 된 모든 링크에 대해 실시간 대역폭 사용량을 볼 수 있습니다.

### <a name="requirements"></a>요구 사항

비즈니스용 Skype 서버 토폴로지에 속한 컴퓨터에서 대역폭 정책 서비스 모니터 도구를 실행 해야 합니다.

### <a name="summary"></a>요약

대역폭 정책 서비스 모니터 도구는 토폴로지에 있는 모든 대역폭 정책 서비스의 상태를 검사할 수 있도록 관리자에 게 유용한 리소스가 될 수 있으며, 더욱 중요 한 이유는 링크에 대 한 실시간 대역폭 활용도를 얻을 수 있다는 것입니다. 네트워크 구성 설정에 정의 되어 있습니다.

## <a name="bandwidth-utilization-analyzer"></a>대역폭 이용률 분석기
<a name="bua"> </a>

대역폭 사용률 분석기는 엔터프라이즈 네트워크의 WAN 링크 간에 UC 끝점을 사용 하 여 다양 한 대역폭 사용량 보기에 대 한 보고서를 만드는 도구입니다. 이러한 보고서를 사용 하 여 현재 대역폭 소비 패턴을 이해 하 고 대역폭 용량 계획을 도울 수 있습니다.

### <a name="description"></a>설명

대역폭 사용률 분석기는 GUI 기반 응용 프로그램으로 구현 됩니다. 이 도구는 네트워크에서 오디오 사용률을 위한 보고서를 생성 하 고 용량 계획에 도움이 됩니다. 또한 다양 한 링크에 할당 된 대역폭 용량을 반복 합니다.

### <a name="output"></a>결과물

대역폭 사용률 분석기는 시스템에 구성 된 모든 WAN 링크에 대 한 오디오 사용량 및 대역폭 용량을 그래픽으로 그립니다.

### <a name="purpose"></a>것

음성 및 영상 배포의 경우 엔터프라이즈 네트워크에서 미디어 소통량의 대역폭 사용률 추세를 모니터링 하 고 이해 하는 것이 중요 합니다. 관리자는 대역폭 사용률 분석기 도구를 사용 하 여이를 구현할 수 있습니다. 이 도구는 다음을 수행 합니다.

- 네트워크에서 오디오 사용률을 위한 특정 보고서를 생성 합니다.

- 다양 한 링크에 할당 된 대역폭 용량에 대 한 보다 효과적인 용량 계획 및 반복을 지원 합니다.

대역폭 사용률 분석기는 대역폭 용량 및 사용률 보고서의 그래픽 플롯을 생성할 수 있습니다. 이러한 작업은 다음과 같습니다.

- 엔터프라이즈 네트워크의 모든 WAN 링크

- 선택한 WAN 링크로 필터링 됨

- 링크 용량을 초과한 WAN 링크로 필터링 됨

- 프로 비전 된 대역폭을 이용 하 고 있는 WAN 링크로 필터링 됨

- 중요 한 수준에 도달한 WAN 링크 (WAN 링크의 대역폭 용량의 90% 보다 큰 대역폭 이용률)를 기준으로 필터링

- WAN 링크 유형 (네트워크 사이트 링크, 상호 지역 링크, 사이트 내의 링크)을 기준으로 필터링

- 네트워크 지역별로 필터링 됨

#### <a name="applications"></a>프로그램도

대역폭 사용률 분석기에는 다음과 같은 두 가지 응용 프로그램이 있습니다 (도구).

- **WanLinkLogCollector** 사용자는이 도구를 사용 하 여 필요한 정보를 입력할 수 있습니다.

- **BandwidthUtilizationAnalyzer** Microsoft Excel 스프레드시트 소프트웨어 보고서는 WanLinkLogCollector에서 자동으로 실행 됩니다. 이 응용 프로그램을 사용 하면이 문서의 뒷부분에 나와 있는 대로 사용자가 보고서에 필터를 적용할 수 있습니다.

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a>대역폭 이용률 분석기 사용 단계

대역폭 이용률 분석기를 사용 하는 두 단계는 다음과 같습니다.

- WanLinkLogCollector를 사용 하 여 수행 되는 로그 수집

- BandwidthUtilizationAnalyzer를 사용 하 여 수행 되는 보고서 사용자 지정

> [!IMPORTANT]
> 최종 사용자가 수동으로 BandwidthUtilizationAnalyzer를 실행 하는 것이 좋습니다.

#### <a name="starting-bandwidth-utilization-analyzer"></a>대역폭 사용률 분석기 시작

명령 프롬프트 또는 Windows 탐색기를 사용 하 여 WanLinkLogCollector를 시작 합니다.

 **WanLinkLogCollector 사용**

WanLinkLogCollector를 사용 하는 세 단계는 다음과 같습니다.

1. **시간 표시 막대 기록** 보고서를 생성 해야 하는 시간 표시 막대를 제공 합니다.

2. **파일 디렉터리 지정** 파일 위치 정보 제공

3. **로그를 수집 하 고 보고서 뷰어를 실행 합니다** . 명령을 실행 하 여 보고서 생성

#### <a name="step-1---log-the-timeline"></a>1 단계-시간 표시 막대 기록

시간 표시 막대를 기록 하면 도구 사용자가 아래 그림에 표시 된 대로 다음을 지정할 수 있습니다.

1. **시작 날짜** 보고서가 생성 되는 시간 표시 막대의 시작 날짜입니다. 예를 들어 2010 년 8 월 1 일입니다.

2. **종료 날짜** 보고서가 생성 되는 시간 표시 막대의 종료 날짜입니다. 예를 들어 2010 년 9 월 30 일.

     ![Bandwidth Utilization Analyzer의 시작 및 종료 날짜](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a>2 단계-파일 디렉터리 지정

다음 파일 디렉터리는 사용자가 표시 된 대로 지정할 수 있습니다.

- **서버 로그 파일 위치** 대역폭 정책 서버 로그가 저장 되는 폴더 위치입니다. 이는 일반적으로 \<FE\> \\ \>\AppServerFiles\PDP. fileserver<선택 사항입니다.

- **임시 파일 저장소 위치** 보고서를 생성 하는 동안 중간 파일이 저장 되는 임시 파일 위치입니다.

![Bandwidth Utilization Analyzer의 파일 디렉터리](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

> [!NOTE]
> 서버 로그에 대 한 파일 액세스 권한 및 임시 파일 저장소 폴더가 도구 사용자에 게 제공 되는지 확인 합니다.

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>3 단계-로그를 수집 하 고 보고서 뷰어를 시작 합니다.

로그를 수집 하 고 보고서 뷰어를 시작 하려면 아래와 같이 **실행** 을 클릭 합니다. 이 단계는 필요한 데이터를 수집 합니다.

![Bandwidth Utilization Analyzer의 데이터 수집](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

입력 유효성 검사에 성공 하면 아래에 표시 된 메시지가 표시 됩니다.

![Bandwidth Utilization Analyzer에 수집된 알림 로그](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

**확인**을 클릭합니다. BandwidthUtilizationAnalyzer 자동으로 시작 됩니다. 메시지 상자의 지침을 따릅니다. 자세한 내용은 다음 섹션의 **BandwidthUtilizationAnalyzer 사용** 을 참조 하세요.


### <a name="using-bandwidthutilizationanalyzerxlsm"></a>BandwidthUtilizationAnalyzer 사용

1. BandwidthUtilizationAnalyzer가 자동으로 시작 되 면 아래와 같이 **새로 고침** 을 클릭 합니다.

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. 파일 폴더를 열 때 아래와 같이 메시지 상자에 지정 된 위치에서 통합 .csv를 선택 합니다. 또한 **C:\Temp**로 위치를 표시 합니다.

     ![BandwidthUtilizationAnalyzer의 폴더 열기.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. **가져오기를**클릭 합니다.

4. 그래픽 플롯이 자동으로 생성 됩니다. 이 기능은 작업 중 배경 포인터가 사라질 때 사용할 수 있습니다.

     ![보고서 보기의 필터 적용.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a>보고서 보기에 필터 적용

아래 표시 된 것 처럼 보고서 보기에 적용할 수 있는 필터에 대 한 설명은 다음과 같습니다.

![보고서 보기의 필터 적용.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. **이름** WAN 링크로 필터링 (필터는 그래프 오른쪽에 있습니다.) 접두사는 다음 링크 형식을 나타냅니다. 세로 (파란색) 상자를 표시 합니다.

   - **S 사이트** 네트워크 사이트에서 네트워크 지역으로의 WAN 연결

   - **사이트 간** 두 네트워크 사이트 간 WAN 링크

   - **R 지역 간** 두 네트워크 지역 간 WAN 링크

2. **제한 초과** 대역폭 사용량이 대역폭 용량 보다 더 많은 WAN 링크를 기준으로 필터링

3. **요주의 수준** 대역폭 사용률이 대역폭 용량 보다 90% 이상에 도달 했을 때의 WAN 링크 필터링

4. **과소 사용** 대역폭 사용률이 대역폭 용량의 25% 미만이 되는 WAN 링크로 필터링

5. **링크 형식** 다음 WAN 링크 형식으로 필터링:

   - **네트워크 사이트** 종류

   - **사이트 간** 종류

   - **지역 간 링크** 형식

6. **지역** 네트워크 지역별로 필터링

다음 그림에는 앞에서 설명한 필터가 나와 있습니다.

**이름**필터링. 그래프에 표시 해야 하는 링크 목록을 선택 합니다.

![BandwidthUtilizationAnalyzer의 이름을 기준으로 필터링.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

**제한을 초과한 값**을 기준으로 필터링 합니다. **True** 를 선택 하 여 필터를 적용 합니다.

![Exceeded Limit(제한 초과)를 기준으로 필터링.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

**위험 수준**으로 필터링 **True** 를 선택 하 여 필터를 적용 합니다.

![Critical Levels(위험 수준)를 기준으로 필터링.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

**과소**필터링을 사용 합니다. **True** 를 선택 하 여 필터를 적용 합니다.

![Under Utilized(낮은 활용도)를 기준으로 필터링.](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

**링크 형식**으로 필터링 표시 해야 하는 유형을 선택 합니다.

![Link Type(링크 유형)을 기준으로 필터링.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

**지역별로**필터링. 링크를 표시 해야 하는 영역 목록을 선택 합니다.

![Region(영역)을 기준으로 필터링.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a>요구 사항

- .NET Framework 3.5

- Microsoft Excel 2010 또는 Excel 2007

### <a name="summary"></a>요약

대역폭 사용률 분석기는 네트워크를 통해 UC 트래픽에 대 한 오디오 대역폭 사용률을 그리는 데 사용 됩니다. 이 도구를 사용 하 여 네트워크의 비디오 대역폭 사용률도 보고할 수 있습니다.

## <a name="call-parkometer"></a>전화 Parkometer
<a name="callpark"> </a>

통화 Parkometer는 통화 공원 궤도 데이터베이스에 쉽게 액세스할 수 있는 명령줄 응용 프로그램입니다.

### <a name="description"></a>설명

Parkometer 통화는 현재 파킹 된 통화를 추적 하는 도구입니다. 또한 orbits 및 CPS (통화 공원 서버) 사용에 대 한 통계도 수집 합니다. 이 명령줄 도구는 로컬 또는 원격으로 연결 된 컴퓨터에서 CPS 궤도 SQL Server 데이터베이스에 대 한 읽기 및 쓰기 액세스를 모두 제공 합니다.

모든 옵션은 동시에 사용할 수 없습니다. 명령줄 구문은 다음과 같습니다.

- **-o** 매개 변수-이 풀에 대해 구성 된 모든 궤도 범위를 나열 합니다.

- **-n** 매개 변수-이 풀에서 현재 사용 된 모든 orbits를 나열 합니다. 표시 되는 정보는 다음과 같습니다.

  - Parkee 및 parker의 SIP URI (Uniform Resource Identifier)입니다.

  - 통화가 파킹 된 CPS의 호스트 이름입니다.

  - 통화가 파킹 되었을 때의 타임 스탬프입니다.

- **-f** 매개 변수-풀에서 현재 사용 가능한 orbits의 수를 나열 합니다.

- **-r \<n\> ** 매개 변수-마지막 \<으로\> 파킹 된 통화 n 개를 나열 합니다. 표시 되는 정보는 다음과 같습니다.

  - Parkee SIP URI.

  - Parker SIP URI.

  - 통화가 파킹 된 CPS의 호스트 이름입니다.

  - 통화를 검색 하거나 삭제 한 시간의 타임 스탬프입니다.

- **-t\<n\> ** 매개 변수-테스트 데이터베이스에서 궤도를 예약 하 여 지정 된 궤도 숫자의 임의성을 표시 합니다.

### <a name="output"></a>결과물

명령 프롬프트에 지정 된 입력 매개 변수에 따라 Parkometer에 다음 출력이 표시 됩니다.

- 이 풀에 대해 구성 된 모든 궤도 범위

- 현재 파킹 통화

- 무료 (사용 가능) orbits 수

- 최근에 파킹 한 통화

- 통일 및 임의 궤도 값을 테스트 하기 위해 예약 된 orbits

### <a name="purpose"></a>것

CPS 도구의 용도는 CPS 데이터베이스에 대 한 명령줄 액세스를 제공 하는 것입니다. 관리자는 CPS 사용량을 보고 풀에 할당 된 orbits 수를 확인할 수 있습니다.

### <a name="requirements"></a>요구 사항

CPS를 실행 하는 컴퓨터에서이 도구를 실행 하는 경우 요구 사항은 없습니다. 원격 컴퓨터에서이 도구를 실행 하는 경우 비즈니스용 Skype 서버 2015에서 사용 하는 SQL Server 데이터베이스를 원격 액세스를 허용 하도록 구성 해야 합니다. 풀의 SQL Server에 연결 하려면 SQL Server 데이터베이스 연결 문자열을 사용 하 여 Parkometer 호출을 구성 해야 합니다. 이 SQL Server 데이터베이스 연결 문자열은 구성 파일 **parkometer**에 정의 되어 있습니다. Parkometer가 있는 디렉터리에 배치 해야 합니다. 다음 XML 파일은 parkometer의 예입니다. 구성 해야 하는 매개 변수는 사용자 이름 (예: mydomain\Administrator), 암호 (예: mypassword) 및 호스트 이름 (예: myserver)입니다.

```
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <appSettings>
   <add key="SQL" value="server=myserver\RTC;
database=cpsdyn;
User Id=mydomain\Administrator;
Password=mypassword.;
Integrated Security=false;"/>
  </appSettings>
</configuration>
```

### <a name="examples"></a>예제

배포 된 궤도 범위:-o 매개 변수는 아래와 같이이 풀에 대해 구성 된 모든 궤도 범위를 나열 합니다.

![Call Parkometer의 통화 번호 범위.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

현재 대기 중인 통화:-n 매개 변수는 표시 된 대로이 풀에서 현재 사용 되는 모든 orbits를 나열 합니다.

![Call Parkometer의 현재 대기 중인 통화.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

무료 orbits 수:-f 매개 변수는 아래와 같이 풀에서 현재 사용 가능한 orbits 수를 나열 합니다.

![Call Parkometer의 사용 가능한 통화 번호.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

최근 파킹 된 통화:-r \<n\> 매개 변수는 \<표시\> 된 것과 같이 n 개의 마지막으로 거는 전화를 나열 합니다.

![Call Parkometer의 최근 대기 통화.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

테스트 궤도 예약:-t \<n\> 매개 변수 테스트에서는 표시 된 대로 데이터베이스에서 궤도를 예약 합니다.

![Call Parkometer의 테스트 통화 번호 예약.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a>요약

Parkometer 통화는 통화 공원 서버에 대 한 자세한 정보를 제공 하는 명령줄 도구입니다.

## <a name="dbanalyze"></a>DBAnalyze
<a name="dba"> </a>

### <a name="description"></a>설명

DBAnalyze는 관리자가 비즈니스용 Skype 서버 2015 데이터베이스에 대 한 분석 보고서를 수집 하는 데 도움이 되는 명령줄 도구입니다. DBAnalyze에는 진단, 사용자 데이터, 회의, MCUs, 디스크 조각화 등의 모드가 있습니다.

- **진단 모드** 테이블에 대 한 정보 (레코드 수, 조각화, 데이터 크기, 인덱스 크기), 데이터 및 로그 파일 크기, 마지막 백업 시간, Microsoft Office Communications Server를 실행 하는 서버 간에 서비스 배포에 대 한 연락처를 포함 하는 보고서를 만듭니다. 평균 사용 권한, 연락처, 컨테이너, 구독, 게시, 사용자 당 끝점, 부적절 한 홈 사용자, 라우팅할 수 없는 사용자, 사용자 당 구성 되는 평균 컨퍼런스, 예약 된 회의, 활성 회의, 데이터베이스 버전.

    > [!NOTE]
    > 진단 모드를 실행 하면 서버 성능이 저하 될 수 있습니다.

- **사용자 데이터 모드** 지정 된 사용자 또는 해당 사용자의 연락처 및 사용 권한 목록에 있는 사용자의 연락처, 컨테이너, 구독, 게시, 사용 권한, 연락처 그룹 데이터를 보고 합니다. 또한이 모드는 사용자가 구성 하거나 초대 하는 회의에 대 한 요약 데이터를 보고 합니다.

- **컨퍼런스 모드** 회의의 모든 일정 시간 세부 정보, 초대 대 상자, 회의에 허용 된 미디어 유형 목록, 활성 MCUs (multipoint 컨트롤 단위), 활성 참가자 목록 등 특정 회의에 대 한 자세한 데이터를 보고 합니다. 참가자의 신호 상태입니다.

- **디코드 모임 ID** **/Pstnid** 스위치로 지정 되지만 백 엔드에 연결 되지 않은 PSTN (공개 전환 전화 네트워크) 모임 ID를 디코딩 하는 방법에 대해 자세히 설명 합니다.

- **컨퍼런스 해결** **/Pstnid** 스위치로 지정 된 PSTN 모임 ID를 디코딩하고 ID로 표시 되는 전화 회의에 대 한 정보를 표시 합니다.

- **MCUs 모드** 풀의 각 MCU에 대 한 ID, 미디어 유형, URL, 하트 비트 상태, 컨퍼런스 부하, 참가자 부하를 보고 합니다.

- **디스크 조각화 모드** 모든 디스크의 조각화 상태를 표시 합니다.

이 도구는 다양 한 문제를 진단 하거나 용량 계획에 관리자를 지원 하기 위해 사용할 수 있습니다. 예를 들어 서버 A에 있는 사용자가 대부분 사용자를 선택 하 여 서버 B에 연결 되어 있는 경우, 관리자는 서버 A의 사용자를 서버 B로 이동 하 여 교차 서버 트래픽을 줄일 수 있습니다.

### <a name="output"></a>결과물

이 도구는 비즈니스용 Skype Server 2015 데이터베이스에 대 한 미리 정의 된 보고서를 출력 합니다. **경로**: 비즈니스용%ProgramFiles%\Skype Server 2015 \ Reskit

### <a name="purpose"></a>것

Dbanalyze .exe를 설치 하려면 로컬 폴더에 복사한 다음 도구를 실행 합니다. 이 도구를 사용 하려면 명령줄에서 다음 명령을 실행 합니다. `dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`명령줄 옵션에 대 한 설명은 다음과 같습니다.

![Dbanalyze.exe의 명령줄 옵션.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a>요구 사항

 **컴퓨터** DBAnalyze는 비즈니스용 Skype 서버 2015이 설치 되어 있는 도메인 가입 컴퓨터 에서만 실행할 수 있습니다.

 **네트워크** 컴퓨터가 백 엔드 데이터베이스에 연결할 수 있어야 합니다.

 **소프트웨어** DBAnalyze를 실행 하기 전에 비즈니스용 Skype 서버 2015 소프트웨어 구성 요소를 설치 해야 합니다.

 **사용자** 아래 표에는 비즈니스용 Skype Server 2015 데이터베이스에 액세스 하는 데 필요한 권한이 있는 관리자가 나와 있습니다.

![Dbanalyze.exe의 사용 권한 테이블.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> **/Creport: disk** mode에는 로컬 관리자 계정이 필요 합니다.

### <a name="examples"></a>예제

다음은 유효한 Dbanalyze 명령의 예입니다.

```
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a>요약

DBAnalyzer는 관리자가 비즈니스용 Skype 서버 2015 데이터베이스를 빠르고 쉽게 분석할 수 있도록 합니다.

## <a name="import-storage-service-data"></a>저장소 서비스 데이터 가져오기
<a name="Issd"> </a>

ImportStorageServiceData resource kit 도구를 사용 하면 저장소 서비스 (LYSS)에서 다시 플러시된 큐 및 끝점 데이터를 저장소 서비스로 다시 가져올 수 있습니다.

### <a name="description"></a>설명

저장소 서비스에서 플러시된 데이터는 큐 항목 상태 또는 데이터베이스 크기에 따라 자동 (정기적)이 될 수 있습니다. 풀 장애 조치 cmdlet 또는 StorageServiceFullFlush cmdlet (풀 장애 조치 cmdlet이 호출 하는)의 수동 호출 때문에 발생 했을 수 있습니다. 프런트 엔드에서 저장소 서비스 (LYSS) 데이터베이스 크기가 표준 수준 보다 위에 있으면 데이터를 다시 가져올 필요가 없으며,이 경우에는 더 많은 데이터를 다시 내보내기만 하면 됩니다. 또한 저장소 서비스 대기열을 증가 시키는 오류에 대 한 문제를 먼저 해결 해야 합니다 (예: Exchange endpoint errors, 네트워크 문제 또는 기타 문제 발생).

 **시나리오 1:** 풀 장애 조치 중에 각 프런트 엔드에서 저장소 서비스에서 파일을 플러시할 수 있습니다. 장애 조치 (failover)가 완료 된 후 데이터를 다시 가져오려면 도구를 실행 해야 합니다.

 **시나리오 2:** 데이터는 매일 자동으로 플러시되고 특정 크기 임계값을 초과 하는 저장소 서비스 데이터베이스 (예: 60%, 80%, 90% full)에 대 한 응답으로 플러시합니다. 자동으로 플러시된이 데이터는 관리자가 정기적으로 다시 가져와야 합니다. 위의 상황에서 모니터링 SCOM pack이 배포 되지 않은 경우 저장소 서비스에서 플러시된 데이터와 관련 된 비즈니스용 Skype 서버 저장소 서비스에 대 한 이벤트가 있습니다. 32075의 이벤트 Id (전체 플러시 작업이 시작 됨), 32076 (전체 플러시 완료), 32082 (유지 관리 수준 플러시 시작), 32083 (유지 관리 수준 강제 완료), 32089 (데이터베이스 채우기 때문에 플러시 발생) 참고 이러한 이벤트 Id는 RTM 릴리스에 해당 합니다. 관리자가 이러한 이벤트를 볼 때 플러시된 파일이 있음을 의미 합니다. 이 도구를 사용 하 여이 데이터를 정기적으로 다시 가져와야 합니다 (예: 일주일에 한 번).

온라인 서비스 릴리스의 경우 비즈니스용 Skype 서버용 상태 모니터링 SCOM pack을 배포 하는 경우 관리자에 게 플러시된 데이터를 저장소 서비스로 다시 가져오도록 요청 하는 새로운 경고가 발생할 수 있습니다. 프런트 엔드 서버의 이벤트 로그에 경고가 트리거된 해당 이벤트가 있습니다. 이 이벤트는 플러시된 데이터 파일이 있는 상위 경로에 대 한 설명과 함께 알림 기준에 맞는 파일 수를 제공 합니다. 알림 기준에는 Y 일 이상 지난 특정 상위 경로 아래에 X와 Y가 StorageService 내에서 사전 설정 되지만 APPCONFIG 파일을 변경 하 여 재정의할 수 있는 파일이 포함 되어 있습니다. 상태 알림을 트리거할 수 있는 이벤트의 두 가지 예는 다음과 같습니다 (부모 경로와 차이). 웹 서비스 파일 공유 아래에는 각 프런트 엔드의 로컬 응용 프로그램 데이터 디렉터리인 한 가지 가능성이 있습니다. (예: 비즈니스용 c:\ProgramData\Microsoft\Skype Server 2015 \ StorageService). 그러면 관리자가이 reskit 도구를 실행 합니다.

이 도구는 해당 도구가 실행 되는 프런트 엔드에서 데이터를 소유 하지 않는 경우에도 실행 중인 프런트 엔드에서 CPU 및 IO 부하를 늘리고, 다른 프런트 엔드는이를 수행 합니다. 프론트 엔드가 과도 한 CPU 및 IO 로드가 아닌 경우 (예: 최대 사용 시간 외)에이 도구를 사용 하는 것이 좋습니다. 둘째,이 도구는 데이터 파일 하나를 가져오는 데 2 ~ 3 분 정도 걸릴 수 있습니다. 도구 실행 시간을 예상할 때이 점에 유의 하세요. 도구에서 생성 된 자세한 로그 파일은 기본적으로 파일 저장소에 표시 됩니다. 로그 파일의 크기가 수십 MB 이상 일 수 있으므로 보고 되는 오류가 없는 경우 삭제 합니다.

![샘플 저장소 서버 이벤트 로그 이벤트.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a>요구 사항

비즈니스용 Skype 서버 2015 리소스 키트 도구를 설치 합니다. 이 도구는 비즈니스용 Skype Server 및 비즈니스용 Skype Server Management 셸이 설치 되어 있는 도메인에 가입 된 컴퓨터에서 실행 됩니다. 이 도구는 관리 셸에서 cmdlet을 사용 하 여 풀의 모든 프런트 엔드 서버를 식별 합니다. 둘째로, **RtcLocal** 데이터베이스가 설치 되어 있는 풀의 컴퓨터에서 도구를 실행 해야 합니다. 이 데이터베이스는 도구에서 풀에 대 한 WEBSERVICE 파일 공유 위치를 검색 하는 데 사용 됩니다. 또한이 도구를 사용 하기 전에 각 프런트 엔드 서버에서 각 프런트 엔드 서버에 대해 **enable-PSRemoting** 을 사용 하 여 Windows PowerShell Remoting을 먼저 사용 하도록 설정 해야 하며,이 도구를 실행 하는 컴퓨터도 필요 합니다. 그렇지 않은 경우에는이 도구의 원격 Windows PowerShell 명령이 실패 합니다. 완료 된 후 풀의 모든 프런트 엔드 서버에서 Windows PowerShell Remoting을 끌 수 있습니다. 마지막으로 도구를 호출 하는 계정 또는 자격 증명에는이 도구를 실행 하는 풀의 webservice 파일 공유에 대 한 읽기/쓰기 권한이 있어야 합니다. 그렇지 않으면 IO 권한 오류와 관련 된 도구가 작동 하지 않습니다.

> [!NOTE]
> Windows Server 2012에서는 windows PowerShell Remoting이 기본적으로 사용 하도록 설정 되어 있지만 Windows Server 2008 운영 체제에서는 사용할 수 없습니다.

### <a name="examples"></a>예제

```
>  C:\StorageService>ImportStorageServiceData.exe
Description:
This tool will re-import Storage Service (LYSS) flushed queue data back in.  For a pool: you are required to run this tool on a machine inside the pool which has the Lync Server Management Shell installed.  Additionally, all front end machines need to have Windows Powershell Remoting enabled before executing this tool by executing Enable-PSRemoting.  Also, please ensure that all Storage Service instance DB Size are at the 'Normal' level (verify this by viewing Eventlog events). Otherwise re-importing may cause data to be flushed out again if any Storage Service instance DB size level goes above 'Normal'.
Usage: Default behavior is to Import data from web service file share as well as any files on all Front End machines in pool.
Additional Options:
-Verbose                    : Turn verbose output on.

-StorageServiceHostName     : Host Name of Storage Service WCF endpoint.  ( Default=localhost netnamedpipe binding. )

-FileSharePath              : Import only all data from just under the UNC path specified.

ActivityID: cc3b62ff-bb66-4e61-a6e2-96cb3626315c. <-- Use this to correlate with StorageService trace logs if troubleshooting.
Type Server name (TCP binding) or press <enter> for localhost (NamePipe binding):
Using NetNamedPipeBinding...
OnTopologyChanged Event received
Web Service File Share: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService

Front Ends:
server.vdomain.com
server2.vdomain.com
server1.vdomain.com
server3.vdomain.com
Looking under directory: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService for exported data.
# Files found: 8
Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
Items deserialized: 20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
Items deserialized: 20

[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml

Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d
3832e4__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c
86684d3832e4__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml

Items deserialized: 20

[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server2.vdom
ain.com, queueItems=20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42
287dd6__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2
b46a42287dd6__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml

Items deserialized: 20

[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=1

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15
d251e6__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759
e08a15d251e6__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml
Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=1
All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346949ff8
17c220__0.xml
All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346
949ff817c220__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml: succeeded: 20, failed: 0
Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml

Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=20
All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be6
6d5317__0.xml
All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876
749be66d5317__0.xml
Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml: succeeded: 20, failed: 0
Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml
Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=20
All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda
86b565__0.xml
All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4
657eda86b565__0.xml
Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml: succeeded: 20, failed: 0
All files have been imported into Storage Service for path: \\dc.vdomain.com\OcsFileStore\co1-WebSer
vices-1\StorageService
Importing files for: server.vdomain.com
No files founds.
Importing files for: server2.vdomain.com
No files founds.
Importing files for: server1.vdomain.com
No files founds.
Importing files for: server3.vdomain.com
No files founds.
Writing log: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\ImportStorageServiceData
Log20120910_1609SS
Tool has finished execution.
>  C:\StorageService>
```

## <a name="lcssync"></a>LCSSync
<a name="LCSSync"> </a>

LCSSync 도구는 다중 포리스트 환경에서 비즈니스용 Skype Server 2015 통신 소프트웨어를 배포 하는 데 도움이 됩니다. 이 도구는 다른 사용자 및 그룹을 Active Directory 도메인 서비스 contact 개체와 사용자 및 그룹과 동기화 하는 데 사용 되며,이는 비즈니스용 Skype 서버 2015이 설치 되어 있는 중앙 포리스트로 작동 합니다.

### <a name="description"></a>설명

 LCSSync는 중앙 포리스트에서 동기화 된 Active Directory 도메인 서비스 연락처 개체를 사용 하 여 비즈니스용 Skype Server의 사용자를 사용 하도록 설정 합니다. Single sign-on을 제공 하려면 비즈니스용 Skype Server 2015의 중앙 포리스트에서 Active Directory 도메인 서비스 연락처 개체에 기본 사용자 계정이 매핑되어야 합니다. 이 도구는 해당 매핑을 수행 하는 데 도움이 됩니다. 이 도구는 Microsoft Id 통합 서버에서 관리 에이전트를 만들기 위한 템플릿을 제공 합니다.

### <a name="summary"></a>요약

LCSSync tool을 사용 하면 다중 포리스트 환경에서 비즈니스용 Skype 서버 2015을 배포할 수 있습니다.

## <a name="lookup-user-console"></a>조회 사용자 콘솔
<a name="LUC"> </a>

LookupUserConsole 도구는 특정 사용자에 대 한 비즈니스용 Skype 서버의 라우팅 정보를 표시 합니다. 이 정보는 배포 및 라우팅 문제를 진단 하는 데 Microsoft 지원 개인에 게 유용할 수 있습니다.

### <a name="description"></a>설명

 LookupUserConsole을 실행 하면 SIP 주소를 수락 하 고 해당 사용자와 관련 된 비즈니스용 Skype 서버 라우팅 정보를 표시 하려고 할 때 명령 프롬프트가 열립니다. **Exit** 를 입력 하 여 LookupUserConsole 도구를 종료 합니다.

### <a name="requirements"></a>요구 사항

비즈니스용 Skype 서버 2015 리소스 키트를 설치 합니다. 이 도구는 비즈니스용 Skype 서버가 설치 되어 있는 도메인에 가입 된 컴퓨터에서 실행 됩니다.

### <a name="examples"></a>예제

Business Server 2015에 대 한 C:\Program Files\Skype\>/ResKit lookupuserconsole. exe

```
> sip:john.doe@vdomain.com

  Execution time (ms):                            171.094
  Exeuction result:                               Success
  SIP URI:                                        sip:john.doe@vdomain.com
  User info:
    SID:                                          S-1-5-21-2831376166-29632525...    Display name:                                     John Doe
    Grouping ID:                                  00000000-0000-0000-0000-...
    Line URI:                                     <null>
    Policy assignment:                            TenantId={00000000--0000-000....
    SIP enabled:                                  True
    UC enabled:                                   False
    Tenant ID:                                    00000000-0000-0000-0000-...  Cluster info:
    Active cluster:                               pool0.vdomain.com
    Backup registrar cluster:                     <null>
    Deployment location:                          <null>
    Home Front-End FQDN:                          SERVER.vdomain.com
    Primary Registrar cluster:                    pool0.vdomain.com
    Remote Director external SIP FQDN:            <null>
    Remote Director internal SIP FQDN:            <null>
    Remote Director Web FQDN:                     <null>
    Routing group ID:                             4501e04e-ae48-5605-9346...
    Service tag ID:                               1266953005
    User Front-End resolved:                      True
    User in local forest:                         True
    User in remote forest:                        False
    User in split domain:                         False
    User-Services cluster:                        pool0.vdomain.com

> sip:nouser@vdomain.com

  Execution time (ms):                            948.7574
  Exeuction result:                               UserDoesNotExist

> exit
```

## <a name="msturnping"></a>MsTurnPing
<a name="MsTurnPing"> </a>

MSTurnPing 도구를 사용 하면 비즈니스용 Skype Server 2015 통신 소프트웨어에서 오디오/비디오에 지 및 오디오/비디오 인증 서비스를 실행 하는 서버의 상태와 대역폭 정책을 실행 하는 서버를 확인할 수 있습니다. 토폴로지의 서비스.

### <a name="description"></a>설명

MSTurnPing 도구를 사용 하면 비즈니스용 Skype Server 2015 통신 소프트웨어에서 오디오/비디오에 지 및 오디오/비디오 인증 서비스를 실행 하는 서버의 상태와 대역폭 정책을 실행 하는 서버를 확인할 수 있습니다. 토폴로지의 서비스.

관리자는이 도구를 사용 하 여 다음과 같은 테스트를 수행할 수 있습니다.

1. A/V Edge 서버 테스트: 도구는 다음을 수행 하 여 토폴로지의 모든 A/V Edge 서버에 대해 테스트를 수행 합니다.

   - 비즈니스용 Skype 서버 오디오/비디오 인증 서비스가 시작 되었으며 적절 한 자격 증명을 발급할 수 있는지 확인 합니다.

   - 비즈니스용 Skype 서버 오디오/비디오에 지 서비스가 시작 되었으며 외부에 지에 대 한 리소스를 성공적으로 할당할 수 있는지 확인 합니다.

2. 대역폭 정책 서비스 테스트: 도구는 다음을 수행 하 여 토폴로지에서 대역폭 정책 서비스를 실행 하는 모든 서버에 대해 테스트를 수행 합니다.

   - 비즈니스용 Skype 서버 대역폭 정책 서비스 (인증)가 시작 되었으며 적절 한 자격 증명을 발급할 수 있는지 확인 합니다.

   - 비즈니스용 Skype Server Core (대역폭 정책 서비스)가 시작 되었는지 확인 하 고 대역폭 검사를 성공적으로 수행할 수 있습니다.

이 도구는 토폴로지에 속해 있고 로컬 저장소가 설치 된 컴퓨터에서 실행 해야 합니다.

### <a name="output"></a>결과물

도구가 각 작업의 결과를 출력 합니다.

- **AudioVideoEdgeServer** 테스트를 수행 하는 경우 도구 출력은 다음과 같습니다.

  - 토폴로지에 비즈니스용 Skype 서버 2015 오디오/비디오 인증 서비스를 제공 하는 컴퓨터의 테스트 결과

  - 토폴로지에 비즈니스용 Skype 서버 2015 오디오/비디오에 지 서비스를 제공 하는 컴퓨터의 테스트 결과

- **BandwidthPolicyServer** 테스트를 수행 하는 경우 도구 출력은 다음과 같습니다.

  - 토폴로지에 비즈니스용 Skype 서버 2015 대역폭 정책 서비스 (인증)를 제공 하는 컴퓨터의 테스트 결과

  - 토폴로지에 비즈니스용 Skype 서버 2015 Core (대역폭 정책 서비스)를 제공 하는 컴퓨터의 테스트 결과

### <a name="requirements"></a>요구 사항

- 이 도구는 토폴로지에 있고 로컬 저장소가 있는 컴퓨터에서 실행 해야 합니다.

- 이 도구는 로컬 저장소에 액세스할 수 있는 관리자 권한으로 실행 해야 합니다.

### <a name="examples"></a>예제

다음은 도구 입력의 예제입니다.

```
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a>요약

이 도구는 오디오/비디오 및 대역폭 정책 서비스를 실행 중인 서버의 상태를 확인 하려는 비즈니스용 Skype 서버 2015 관리자에 게 유용한 리소스 일 수 있습니다.

## <a name="network-configuration-viewer"></a>네트워크 구성 뷰어
<a name="NCV"> </a>

비즈니스용 Skype Server 2015 통신 소프트웨어 관리자는 네트워크 구성 뷰어를 사용 하 여 실시간 통신 세션을 허용 하도록 프로 비전 된 엔터프라이즈에 대 한 CAC (호출 허용 제어) 네트워크 토폴로지를 볼 수 있습니다. 지정 된 대역폭 용량을 기준으로 음성 또는 영상 통화 비즈니스용 skype 서버 2015 관리자는 비즈니스용 Skype Server 2015와 함께 설치 되는 대역폭 정책 서비스에 의해 적용 되는 CAC 정책을 정의 합니다.

### <a name="description"></a>설명

네트워크 구성 뷰어 (NetworkConfigurationViewer)를 사용 하 여 관리자는 다음 작업을 수행할 수 있습니다.

- 그래픽 형식의 비즈니스용 Skype 서버 2015 배포에서 CAC 네트워크 토폴로지를 로드 하 고 확인 합니다.

- 그래픽 형식의 대역폭 정책 서버 로그 파일에서 CAC 네트워크 토폴로지를 로드 하 고 확인 합니다.

- CAC 네트워크 토폴로지를 디스크의 XML 형식으로 저장 하 고 저장 합니다.

- JPG 또는 BMP 형식으로 CAC 네트워크 토폴로지 다이어그램을 저장 하 고 저장 합니다.

- CAC 네트워크 토폴로지 구성 데이터를 봅니다.

- 트리 보기 스타일로 CAC 네트워크 토폴로지를 봅니다.

- CAC 네트워크 토폴로지 링크에 대 한 사용자 지정 커넥터 정의 (예: 사이트 대 지역, 지역/지역, 사이트 간 링크)

- CAC 네트워크 토폴로지 사이트 정보, 지역 정보, 프로 비전 된 대역폭 정책 및 네트워크 링크를 봅니다.

### <a name="purpose"></a>것

그래픽 인터페이스에서 엔터프라이즈 CAC 네트워크 토폴로지 링크를 봅니다.

### <a name="examples"></a>예제

 비즈니스용 skype server **2015 배포에서 cac 네트워크 토폴로지 로드 및 보기 그래픽 형식**: 비즈니스용 skype server 2015 관리자는 비즈니스용 skype server 2015 컴퓨터에서 CAC 네트워크 토폴로지 구성을 로드 하 고 볼 수 있습니다. 아래 그림에 표시 된 것 처럼 **네트워크 구성 다운로드** 옵션을 사용 합니다. 이 도구는 비즈니스용 Skype Server 2015 구성 저장소에 연결 되어 있지 않은 컴퓨터에 배포 된 경우 이러한 구성을 다운로드 하거나 볼 수 없습니다.

![네트워크 구성 다운로드.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 **그래픽 형식의 대역폭 정책 서버 로그 파일에서 CAC 네트워크 토폴로지를 로드 하 고 확인 합니다.** 비즈니스용 skype 서버 2015 대역폭 정책 서버는 비즈니스용 Skype Server 2015 파일 공유 위치 아래에 있는 로깅 메커니즘의 일부로 CAC 네트워크 토폴로지를 저장 합니다. 비즈니스용 Skype Server 2015 관리자는 아래와 같이 **네트워크 구성 열기** 옵션을 사용 하 여 그래픽 형식으로 이러한 파일을 볼 수 있습니다.

![대역폭 정책 서버 로그 파일 열기.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

디스크의 XML 형식으로 CAC 네트워크 토폴로지 저장 및 저장: 비즈니스용 Skype Server 2015 관리자는 아래와 같이 **네트워크 구성 복사본 저장** 옵션을 사용 하 여 cac 네트워크 토폴로지 구성 파일을 xml 형식으로 저장할 수 있습니다. 저장 된 구성 파일은 그래픽 보기 목적으로 오프 라인으로 사용할 수 있습니다.

![네트워크 구성을 XML 파일로 저장.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

다음으로 CAC 네트워크 토폴로지 다이어그램 저장 및 저장: JPG 또는 BMP 형식의 Skype for Business Server 2015 관리자는 **네트워크 구성 다이어그램을 다음으로 저장을 사용 하 여 CAC 네트워크 토폴로지 구성을 그래픽 형식 (JPG 및 BMP 파일 형식)으로 저장할 수 있습니다. **아래 표시 된 그림 옵션

![네트워크 구성을 그림으로 저장.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <strong>CAC 네트워크 토폴로지 구성 데이터 보기:</strong> 비즈니스용 Skype 서버 2015 관리자는 네트워크 영역, 네트워크 사이트, 대역폭 프로필, 사이트 서브넷 IP 주소와 같은 관련 네트워크 구성 데이터를 다음과 같이 볼 수 있습니다. 미만인.

![네트워크 구성 데이터 보기.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 **트리 보기 스타일에서 CAC 네트워크 토폴로지 보기:** 비즈니스용 Skype 서버 2015 관리자는 아래와 같이 도구 창 왼쪽의 제어판을 사용 하 여 그래픽 트리 보기 스타일에서 관련 네트워크 구성 데이터를 볼 수 있습니다.

![네트워크 구성 데이터를 트리 뷰로 보기.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 **CAC 네트워크 토폴로지 링크에 대 한 사용자 지정 커넥터 정의 (예: 사이트 대 지역, 지역/지역 및 사이트 간 링크):** 비즈니스용 Skype 서버 2015 관리자는 아래와 같이 설정 옵션을 사용 하 여 CAC 네트워크 구성 WAN 링크에 대 한 사용자 지정 그래픽 커넥터를 정의할 수 있습니다. 이렇게 하면 네트워크 구성에서 프로 비전 되는 다양 한 종류의 네트워크 링크를 구분 하는 데 도움이 됩니다.

![도구](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 **CAC 네트워크 토폴로지 사이트 정보, 지역 정보 및 프로 비전 된 대역폭 정책 보기:** 비즈니스용 Skype 서버 2015 관리자는 아래 표시 된 옵션을 사용 하 여 관련 CAC 네트워크 지역 정보, 사이트 정보 및 CAC 대역폭 제공 정보를 볼 수 있습니다. (예를 들어, 네트워크 지역 또는 네트워크 사이트 개체에서 **정보** 를 클릭 합니다.)

![네트워크의 사용자 지정 커넥터 정의.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a>요약

이 도구는 그래픽 형식으로 배포에 대 한 CAC 네트워크 토폴로지를 보려는 비즈니스용 Skype 서버 2015 관리자에 게 유용한 리소스 일 수 있습니다.

## <a name="response-group-agent-live"></a>응답 그룹 에이전트 라이브
<a name="RGAL"> </a>

응답 그룹 응용 프로그램을 통해 에이전트는 기본 제공 웹 서비스를 사용 하 여 유용한 실시간 정보에 액세스할 수 있습니다. 아쉽게도이 데이터에 대 한 그래픽 보기는 응용 프로그램 외부에서 사용할 수 없습니다. 응답 그룹 에이전트 라이브 리소스 키트 도구는이 정보에 액세스 하는 간단한 방법으로이 문제를 해결 하며, 다른 에이전트와 같은 비즈니스용 Skype 통신 소프트웨어 정보로 더욱 향상 된 기능을 제공 합니다.

### <a name="description"></a>설명

응답 그룹 에이전트 라이브는 응답 그룹 에이전트에 로그인 및 로그 아웃 기능과 일부 실시간 정보 (예: 그룹 구성원 자격 및 현재 통화 수)를 제공 하는 Windows 응용 프로그램입니다. 이는 비즈니스용 Skype에서 액세스할 수 있는 향상 된 버전의 에이전트 그룹 페이지를 의미 합니다.

### <a name="purpose"></a>것

응답 그룹 응용 프로그램은 수신 전화를 큐에 대기 시키고 에이전트 그룹에 라우팅합니다. 서비스 호출에 대 한 의사 결정을 내릴 수 있도록 상담원은 사용 가능한 다른 에이전트, 각 대기열에서 대기 중인 통화 수 등과 같은 에이전트 그룹에 대 한 실시간 정보에 액세스 합니다. 처음에는 응답 그룹 서비스를 통해서만 액세스할 수 있는이 정보를 사용 하 여 직관적인 방법으로 그룹 에이전트를 실시간으로 사용할 수 있습니다.

#### <a name="features"></a>기능

응답 그룹 에이전트 라이브 도구는 응답 그룹 서비스와 비즈니스용 Skype 서버 2015 SDK를 기반으로 합니다. 응답 그룹 에이전트에는 응답 그룹 서비스에서 사용할 수 있는 정보 및 기능 (그룹 구성원, 다른 에이전트의 현재 상태, 대기 통화 수 등)이 제공 됩니다.

아래 그림은 응답 그룹 에이전트의 주요 인터페이스를 보여줍니다.

![Response Group Agent Live 도구.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

응답 그룹 에이전트 라이브의 상담원은 다음 세 가지 주요 기능을 사용할 수 있습니다.

- **로그인/로그 아웃:** 에이전트 그룹 페이지 (비즈니스용 Skype Server 2015에서 액세스할 수 있음)와는 다르게, 응답 그룹 에이전트 라이브에서는 에이전트만 한 번에 모든 에이전트 그룹에 로그인 하거나 로그 아웃할 수 있습니다. 이 응용 프로그램은 상담원에 게 로그인 하거나 로그 아웃할 수 있는 세 가지 빠른 방법을 제공 합니다.

  - 응용 프로그램 내에서 로그인/출력 (녹색 및 빨간색) 단추를 클릭 합니다.

  - 시스템 트레이 아이콘을 마우스 오른쪽 단추로 클릭 하 고 로그인 또는 로그 아웃을 선택 합니다.

  - 구성 가능한 바로 가기 키 사용

- **그룹 등록:** 에이전트 그룹을 선택한 경우 응답 그룹 에이전트 라이브에는 오른쪽 창에이 그룹의 에이전트 목록이 표시 됩니다. 비즈니스용 Skype 서버 2015이이 응용 프로그램과 동일한 컴퓨터에서 실행 되 고 있는 경우, 현재 상태 정보 및 대화 상대 카드는 응답 그룹 에이전트에 실시간으로 표시 됩니다. 상담원은 IM을 전송 하거나 다른 상담원에 게 직접 전화를 걸 수 있습니다.

- **실시간 통계:** 응답 그룹 에이전트 라이브는 모든 에이전트 그룹에 대 한 실시간 통계를 제공 합니다. 업데이트 주기는 1 분입니다. 응답 그룹에서 전화를 받으면 현재 대기 중인 통화 수를 사용 하 여 그룹 이름 옆에 시각적 표시기가 추가 됩니다. 그룹 위에 포인터를 놓으면 가장 오래 된 대기 시간이 표시 됩니다.

### <a name="requirements"></a>요구 사항

응답 그룹 에이전트 라이브에는 .NET Framework 4.0이 필요 합니다. 또한 현재 상태 및 대화 상대 카드 기능을 활용 하려면 비즈니스용 Skype를 로컬로 설치 하 고 실행 해야 합니다.

#### <a name="configuration"></a>구성

응답 그룹 에이전트 라이브는 응용 프로그램의 옵션 대화 상자를 사용 하 여 개별 기본 설정에 맞게 사용자 지정할 수 있습니다. 또한 관리자는 RGAgentLive 파일의 defaultHostAddress 속성을 직접 편집 하 여 기본 호스트 주소를 정의할 수 있습니다.

아래 그림에서는 에이전트에서 호스트 주소 및 바로 가기 키를 구성 하는 데 사용할 수 있는 옵션 대화 상자를 보여 줍니다. 이 대화 상자는 기본 인터페이스의 오른쪽 위에 있는 옵션 단추를 클릭 하 여 액세스할 수 있습니다.

![Response Group Agent Live 옵션 대화 상자.](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

응답 그룹 에이전트 라이브 구성에서 다음 세 가지 다른 설정을 사용자 지정할 수 있습니다.

- 호스트 주소: 일반적으로 에이전트의 홈 풀에 속한 웹 풀 FQDN입니다. 정확한 응답 그룹 서비스 주소는 호스트 뒤에 올바른 경로를 추가 하 여이 정보의 백그라운드에서 자동으로 파생 됩니다.

- 바로 가기: 로그인/아웃에 대 한 정확한 바로 가기를 사용자 지정할 수 있습니다. 유일한 제한 사항은 두 바로 가기에 "Windows 로고" 키 (최소한 다른 키 외에는)를 포함 해야 한다는 것입니다.

- Windows에서 시작: Windows에서 자동으로 시작 하도록 응용 프로그램을 구성할 수 있습니다.

### <a name="examples"></a>예제

아래 그림은 오른쪽 창에서 대화 상대를 마우스 오른쪽 단추로 클릭 하 여 다른 에이전트로 IM을 호출 하거나 보내는 방법을 보여 줍니다.

![전화 걸기 또는 메신저 대화 보내기.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

아래 그림에서는 응답 그룹 에이전트에 현재 대기 중인 통화 수와 이러한 모든 수신 전화 중 가장 긴 대기 시간을 표시 하는 방법을 보여 줍니다.

![대기열 정보 보기.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a>요약

빠른 로그인 및 로그 아웃, 그룹 구성원, 기본 실시간 통계는 응답 그룹 서비스의 응용 프로그램 외부 에서만 사용할 수 있는 흥미로운 응답 그룹 에이전트 기능입니다. 응답 그룹 에이전트 라이브 리소스 키트 도구를 사용 하 여 비즈니스용 Skype Server 2015 관리자는 사용자가 더 빠르고 그래픽 방식으로 작업을 수행할 수 있도록 하는 Windows 응용 프로그램에 에이전트를 제공할 수 있습니다.

## <a name="sefautil"></a>SEFAUtil
<a name="SEFAUtil"> </a>

SEFAUtil (보조 확장 기능 활성화)는 비즈니스용 Skype Server 2015 통신 소프트웨어 관리자와 헬프데스크 상담원에 게 대리자 링, 착신 전환, 동시 연결을 구성할 수 있는 명령줄 도구입니다. 비즈니스용 Skype Server 2015 사용자 대신 팀 호출 설정 및 그룹 통화 픽업. 또한이 도구를 사용 하면 관리자가 특정 사용자에 대해 게시 된 통화 라우팅 설정을 쿼리할 수 있습니다. SEFAUtil 도구를 사용 하면 관리자가 사용자를 대신해 착신 전환 또는 동시 연결을 설정/해제 하거나 수정할 수 있습니다. 관리자는 SIP URI 형식으로 대상을 지정 하거나 사용자가 이미 게시 한 대상을 사용할 수 있습니다. 또한 관리자는이 도구를 사용 하 여 사용자 대신 대리인 또는 팀 호출 그룹 구성원을 추가 하거나 제거할 수 있습니다. 이 도구는 Microsoft 통합 커뮤니케이션 관리 API (OMMA) 3.0를 기반으로 하며 관리자가 SEFAUtil 용 중앙 관리 저장소에서 신뢰할 수 있는 응용 프로그램을 만들어야 합니다.

SEFAUtil (보조 확장 기능 활성화) 비즈니스용 Skype Server 2015 관리자 및 헬프데스크 상담원은 skype를 대신 하 여 대리인 연결-링, 착신 전환, 동시 연결, 팀 통화 설정 및 그룹 통화 픽업 기능을 구성할 수 있습니다. 비즈니스 서버 2015 사용자. 또한 관리자는이 도구를 사용 하 여 특정 사용자에 대해 게시 된 통화 라우팅 설정을 쿼리할 수 있습니다.

### <a name="description"></a>설명

현재 버전의 SEFAUtil는 명령줄 도구에 불과합니다. 지원 되는 그래픽 사용자 인터페이스가 없습니다. 이 도구는 Microsoft 통합 커뮤니케이션 관리 API (()를 기반으로 합니다. 3.0. 이 도구의 기능을 통해 관리자와 헬프데스크 상담원은 다음을 수행할 수 있습니다.

- 사용자에 대 한 모든 통화 라우팅 설정 보기 (통화 착신 전환, 위임, 동시 연결, 팀 통화 및 그룹 통화 픽업 포함)

- 착신 전환 설정 사용/사용 안 함/수정 (대상 및 응답 없음 타이머 포함)

- 통화 전달/사용 안 함/수정-즉시 구성

- 위임 설정 사용/사용 안 함/수정

- 팀 호출 그룹 설정 사용/사용 안 함/수정

    > [!NOTE]
    > 비즈니스용 Skype Server 2015 SEFAUtil 도구의 새로운 도구

- 동시 링 설정/해제/사용 안 함 또는 수정 (대상 포함)

    > [!NOTE]
    > 비즈니스용 Skype Server 2015 SEFAUtil 도구의 새로운 도구

- 그룹 통화 픽업 설정 사용/사용 안 함/수정

    > [!CAUTION]
    > 비즈니스용 Skype Server 2015 SEFAUtil 도구의 새로운 도구

이 도구에는 다음과 같은 제한 사항이 있습니다.

- 비즈니스용 Skype 서버 풀에 속한 사용자만 지원 됩니다.

- 여러 사용자에 대 한 통화 라우팅 설정의 대량 편집은 지원 되지 않습니다.

### <a name="output"></a>결과물

이 도구의 현재 버전은 명령 프롬프트 창에만 출력을 제공 합니다. 자세한 내용은이 문서의 뒷부분에 나오는 예제 섹션을 참조 하세요.

### <a name="purpose"></a>것

다음은이 도구를 사용할 수 있는 몇 가지 주요 시나리오입니다.

- Bob은 executive 이며 비즈니스용 Skype Server 전화 통신으로 옮겨졌습니다. 그는 기존 PBX 시스템에서 위임을 가집니다. 관리자는 비즈니스용 Skype 서버 2015으로 이동 하는 동안 기존 위임 구성을 반영 하도록 Bob의 라우팅을 구성할 수 있습니다.

- Alice는 여러분의 고객 중 한 명에 게 중요 한 통화를 기대 하 고 있다는 것을 여행. 그러나 호텔에는 있지만 컴퓨터에는 액세스할 수 없습니다. 헬프 데스크에 전화를 걸고 자신의 회사 번호에 대 한 모든 통화를 휴대폰 번호에 전달 하도록 요청 합니다. 헬프 데스크 직원은 자신을 대신해 서 구성을 할 수 있습니다.

- 귀하의 직장 번호에 대 한 Joe의 통화는 직장에서 언제 든 지 모바일 보이스 메일을 이동 합니다. 그러나 대부분의 다른 위치에서 제대로 작동 하는 것 같습니다. 헬프 데스크 기술자는 Joe의 라우팅 구성을 볼 수 있으며, Joe가 자신의 휴대폰으로 동시에 연결을 설정 했음을 알게 되었습니다. 기술자는 자신의 사무실에 있는 모바일 서비스에 대 한 정보를 제공 하며, 동시 연결 상태가 좋지 않은 경우 Joe의 모바일 음성 메일로의 통화를 유발 하는 원인이 되는 것을 확인할 수 있습니다.

- Mike는 Contoso의 새로운 직원이 며, 모든 구성원이 팀 호출을 위해 구성 된 새 팀에 참가 하는 경우, 즉, 비즈니스용 Skype Server 2015을 사용 하도록 설정 하면 관리자가 팀 호출 그룹 설정에 자신의 새 팀 구성원을 포함 하도록 설정할 수 있습니다. 또한 관리자가 Mike를 팀의 각 구성원에 대 한 팀 호출 그룹 구성원으로 추가 합니다.

- Contoso의 인적 자원 부서에 있는 고객 서비스 연습은 첫 번째 통화 이후 모든 호출자에 대해 개인 서비스를 제공 하는 것입니다. 부서의 모든 구성원이 서로 가까이에 있으면 모든 전화가 팀과 동시에 전환 되는 것이 팀에 게 매우 방해가 됩니다. 팀 구성원을 방해 하지 않고 최상의 서비스를 제공 하기 위해 비즈니스용 Skype 서버 2015 관리자는 그룹 통화 픽업 접근 권한 값을 사용 합니다. 관리자가 모든 부서 구성원을 픽업 그룹에 추가 하 고 부서별로 픽업 그룹 번호를 통신 합니다. 책상에서 Samantha가 없는 경우에는 상대방이 전화를 걸고 상대방의 책상 으로부터 통화에 응답 하는 것으로 진행 됩니다.

### <a name="requirements"></a>요구 사항

SEFAUtil 도구는 신뢰할 수 있는 응용 프로그램 풀의 일부인 컴퓨터 에서만 실행 됩니다. 이 컴퓨터에는 버전 MA 3.0가 설치 되어 있어야 합니다. 이 도구를 실행 하려면 SEFAUtil 응용 프로그램 ID를 사용 하는 신뢰할 수 있는 새 응용 프로그램을 해당 풀에 만들어야 합니다.

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a>SEFAUtil 도구에 대해 신뢰할 수 있는 새 응용 프로그램 만들기

1. SEFAUTil 도구는 신뢰할 수 있는 응용 프로그램 풀의 일부인 컴퓨터 에서만 실행 됩니다. 필요한 경우 다음 cmdlet을 사용 하 여 비즈니스용 Skype Server Management Shell을 통해 풀을 새 신뢰할 수 있는 응용 프로그램 풀로 추가 하는 작업을 수행할 수 있습니다.

   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > SEFAUtil 도구를 실행 하는 데 사용할 컴퓨터에는 버전 MA 3.0가 설치 되어 있어야 합니다.

2. 신뢰할 수 있는 응용 프로그램은 SEFAUtil 도구의 토폴로지에서 정의 해야 합니다. SEFAUtil를 새 신뢰할 수 있는 응용 프로그램으로 정의 하려면 비즈니스용 Skype Server Management Shell을 사용 하 여 다음 cmdlet을 실행 합니다.

   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > 필요한 경우 다른 포트를 사용할 수 있습니다.
    
    > [!NOTE]
    > 풀 FQDN: SEFAUtil 응용 프로그램을 호스트할 서버 또는 풀의 FQDN입니다 (일반적으로 비즈니스용 Skype 프런트 엔드 서버 > 또는 풀).
    > 풀 등록자 FQDN:이 응용 프로그램 풀과 연결 된 비즈니스용 Skype 프런트 엔드 서버 또는 풀의 FQDN입니다.
    > 풀 사이트:이 풀이 속한 사이트의 사이트 ID입니다.

3. 토폴로지 변경 내용을 사용할 수 있어야 합니다. 다음 cmdlet을 실행 하 여 비즈니스용 Skype 서버 관리 셸을 통해 토폴로지 변경 사용을 수행할 수 있습니다.

   ```
   Enable-CsToplogy
   ```

4. 필요한 경우 SEFAUtil 도구를 실행 하는 데 사용할 비즈니스용 Skype 서버 2015 리소스 키트 도구를 설치 합니다 (서버가 신뢰할 수 있는 응용 프로그램 풀의 일부 여야 함).

5. SEFAUtil 올바르게 실행 중인지 확인 합니다. 이렇게 하려면 관리자 권한을 사용 하 여 windows 명령 프롬프트에서 도구를 실행 하 여 배포에 있는 사용자의 착신 전환 설정을 표시 합니다. 기본적으로이 도구는 "..\Program Files\Skype for Business Server 2015 \ Reskit"에 위치 합니다. 사용자의 착신 전환 설정을 표시 하려면 다음 명령을 사용 합니다.

   ```
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    사용자의 착신 전환 설정이 표시 되어야 합니다.

#### <a name="group-call-pickup"></a>그룹 통화 픽업

그룹 통화 픽업 기능을 사용 하려면 비즈니스용 Skype 서버 2015에 추가 구성이 필요 합니다. 사용자에 게 픽업 그룹을 할당 하기 전에이 기능의 계획 및 배포 단계에 대 한 그룹 통화 픽업 제품 설명서를 참조 하세요.

### <a name="examples"></a>예제

#### <a name="display-current-call-handling-settings"></a>현재 통화 처리 설정 표시

다음 명령을 사용 하 여 사용자에 대 한 통화 처리를 표시 합니다.  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> 이 예제에서는 **/server** 스위치를 사용 하 여 연결할 비즈니스용 Skype 서버를 지정 합니다.

 **결과물**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a>통화 전달/응답 없음 대상 설정

이 예제에서는 통화 전달/아니요 응답 대상과 링 지연 시간을 설정 합니다. 여기서는/server 스위치가 제공 되지 않습니다. SEFAUtil는 비즈니스용 Skype 서버 2015를 자동 검색 하려고 시도 합니다.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone
```

 **결과물**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a>착신 전환 즉시 사용

이 예제에서는 다른 사용자에 게 착신 전환을 즉시 사용 하도록 설정 합니다.

```
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 **결과물**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a>착신 전환 즉시 사용 안 함

이 예에서는 즉시 착신 전환을 사용 하지 않도록 설정 합니다.

```
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com  /disablefwdimmediate
```

 **결과물**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>대리인으로 사용자 추가 및 대리인의 동시 신호음 설정

이 예제에서는 사용자를 대리인으로 추가 하 고 대리인의 동시 벨 울림을 설정 합니다.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 **결과물**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a>대리인의 동시 신호음 규칙 변경

이 예제에서는 이전 예제에서 설정한 동시 신호음 규칙을 지연 링 규칙으로 변경 합니다.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 **결과물**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a>대리인 제거

이 예제에서는 대리인을 제거 합니다.

> [!NOTE]
> 마지막 대리인이 제거 되 면 대리인의 연결이 자동으로 해제 됩니다.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 **결과물**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>대리인을 추가 하 고 착신 전환 규칙이 대리인에 게 설정 됩니다.

이 예제에서는 대리인을 추가 하 고 착신 전환을 대리인 규칙으로 설정 합니다.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 **결과물**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>동시 신호음 사용 및 대상 번호 설정

이 예제에서는 동시 신호음을 사용 하도록 설정 하 고 동시 벨 울림 대상 번호를 설정 합니다.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> 이미 동시에 신호음을 사용 하도록 설정 된 사용자의 동시 벨 울림 번호를 변경 하려면/enablesimulring 스위치를 사용 하 여 명령을 유지 하 고, 그렇지 않으면 대상 번호가 변경 되지 않습니다.

 **결과물**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a>동시 신호음 해제

이 예제에서는 동시 신호음을 비활성화 합니다.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 **결과물**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>팀 호출을 위해 팀 구성원을 추가 하 고 팀 호출 구성원 그룹에 게 동시 연결을 설정 합니다.

이 예제에서는 팀 구성원을 사용자의 팀 호출 그룹에 추가 하 고 팀 호출 그룹으로 동시 연결을 설정 합니다.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> 사용자의 팀 호출 그룹에 구성원을 추가 하면 해당 사용자의 동시 연결 settigs가 자동으로 전환 되어 팀 호출 그룹을 simulring 수 있습니다.

 **결과물**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a>팀 호출 그룹에서 구성원 제거

이 예제에서는 사용자의 팀 호출 그룹 팀 구성원을 제거 합니다.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> 제거할 구성원이 팀 호출 그룹의 유일한 구성원 인 경우 팀 호출 그룹에 동시에 연결 되는 것은 자동으로 비활성화 됩니다.

 **결과물**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a>지연 된 벨소리를 팀 호출 그룹으로 설정

이 예제에서는 지연 된 링을 팀 호출 그룹 시간 설정으로 변경 합니다.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 **결과물**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a>팀 전화 사용

이 예제에서는 지정 된 사용자에 대해 팀 호출을 사용 하도록 설정 합니다.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> 사용자의 팀 호출 그룹에 구성원이 없는 경우 팀 호출을 사용할 수 없습니다.

 **결과물**

#### <a name="disable-team-call"></a>팀 전화 비활성화

이 예제에서는 지정 된 사용자에 대해 팀 호출을 사용 하지 않도록 설정 합니다.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 **결과물**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>그룹 통화 픽업 기능을 사용 하도록 설정 하 고 사용자에 게 픽업 그룹 지정

이 예제에서는 픽업 그룹을 사용자에 게 할당 하 고 그룹 통화 픽업 기능을 사용 하도록 설정 합니다.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 **결과물**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a>그룹 통화 픽업 사용 안 함

이 예제에서는 지정 된 사용자에 대 한 그룹 통화 픽업을 사용 하지 않도록 설정 합니다.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> 사용자의 그룹 통화 픽업을 사용 하지 않도록 설정 하면 사용자에 게 할당 된 그룹 번호가 보존 되지 않습니다. 나중에 해당 사용자의 그룹 통화 픽업을 다시 사용 하도록 설정 하려면/enablegrouppickup 스위치를 사용 하 여 그룹 번호를 다시 할당 해야 합니다.

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a>SYSPrep. ps1
<a name="SYSPrep"> </a>

### <a name="description"></a>설명

SYSPrep. ps1는 Windows Server 2008 운영 체제 컴퓨터에 다음 비즈니스용 Skype Server 2015 필수 조건을 설치 하는 Windows PowerShell 스크립트입니다.

- Microsoft .Net Framework 4.5

- Microsoft SQL Server Express

- Windows Powershell 버전 3.0

- Visual c + + 2010 재배포 가능 패키지

- 인터넷 정보 서버 업데이트

- Windows Identity Foundation

- 비즈니스용 Skype 서버 2015 Core 파일

  스크립트 이름은 Microsoft Windows 운영 체제의 시스템 준비 도구와 비슷하지만 서로 다릅니다. 이 스크립트는 비즈니스용 Skype 서버 2015에 필요한 필수 구성 요소를 설치 합니다. 이러한 필수 구성 요소를 설치한 후에는 Windows SYSPrep 도구를 사용 하 여 서버의 이미지를 만들 수 있습니다.

### <a name="requirements"></a>요구 사항

Sysprep.inf 스크립트를 실행 하기 전에 필수 구성 요소 파일을 Windows Server 2008 운영 체제 컴퓨터의 로컬 폴더 (예: **D:\setup)** 에 복사 해야 합니다. 또한이 폴더에는 비즈니스용 Skype 서버 2015 파일 (특히 **setup.exe** )의 복사본이 포함 되어 있어야 합니다. 필수 구성 요소 파일은 다음 위치에서 다운로드할 수 있습니다.


| **요소일**                                | **위치**                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| Microsoft .Net Framework 4.5  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| Microsoft SQL Server Express 2008 R2  <br/>     | <https://www.microsoft.com/en-us/download/details.aspx?id=23650>  <br/> |
| Windows Powershell 버전 3.0  <br/>           | <https://www.microsoft.com/en-us/download/details.aspx?id=34595>  <br/> |
| Visual c + + 2010 재배포 가능 패키지  <br/>          | <https://www.microsoft.com/en-us/download/details.aspx?id=5555>  <br/>  |
| 인터넷 정보 서버 업데이트  <br/>      | <https://www.microsoft.com/en-us/download/details.aspx?id=34869>  <br/> |
| Windows Identity Foundation  <br/>              | <https://www.microsoft.com/en-us/download/details.aspx?id=17331>  <br/> |
| 비즈니스용 Skype Server 2015 Setup.exe  <br/> | 비즈니스용 Skype 서버 2015 미디어에서 복사  <br/>                   |

### <a name="parameter"></a>매개 변수

**-Setupfolder** 매개 변수는 필수 구성 요소 파일의 디렉터리 위치를 인수로 받습니다.

### <a name="examples"></a>예제

Sysprep.inf 스크립트를 실행 하 고 비즈니스용 Skype 서버 2015 필수 조건을 설치 하려면 관리자 권한 명령 프롬프트에서 다음 명령을 실행 합니다.

```
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a>할당 되지 않은 번호 알림 마이그레이션
<a name="UNAM"> </a>

지정 하지 않은 번호 알림 마이그레이션 도구를 사용 하면 비즈니스용 Skype Server 2015 관리자가 알림 응용 프로그램에서 제공 하는 할당 되지 않은 번호 구성을 비즈니스용 원본 비즈니스용 Skype 서버 또는 풀로 이동할 수 있습니다. 대상 비즈니스용 Skype 서버 또는 풀

### <a name="description"></a>설명

할당 되지 않은 번호 알림 마이그레이션 도구는 원본 서버 또는 풀의 알림 신청에 의해 서비스 되는 할당 되지 않은 번호 구성을 다른 서버 또는 풀에 이동 하는 Windows PowerShell 스크립트입니다.

이를 실행 하면 할당 되지 않은 번호 알림 마이그레이션 스크립트가 다음 작업을 수행 합니다.

1. 원본 서버 또는 풀에 호스팅되는 알림 응용 프로그램의 할당 되지 않은 번호 알림에서 사용 되는 모든 오디오 파일을 대상 서버 또는 풀의 파일 저장소로 이동 합니다.

    > [!NOTE]
    > 대상 풀에 복사 된 오디오 파일은 원본 풀에서 제거 됩니다.

2. 원본 서버 또는 풀에 호스팅되는 알림 응용 프로그램에 대해 구성 된 모든 할당 되지 않은 번호 알림을 대상 서버 또는 풀에 이동 합니다.

3. 원본 서버 또는 풀에 호스팅되는 알림 응용 프로그램에서 지 원하는 모든 할당 되지 않은 번호 범위를 대상 서버 또는 풀에 다시 할당 합니다.

스크립트를 성공적으로 실행 하면 원본 서버 또는 풀에 호스팅된 알림 응용 프로그램에서 서비스 된 모든 할당 되지 않은 번호 범위가 대상 서버 또는 풀에서 동일한 구성으로 처리 됩니다.

### <a name="output"></a>결과물

**CsAnnouncementConfiguration** 스크립트는 비즈니스용 Skype Server Management Shell 창에서 마이그레이션 작업의 성공 또는 실패를 실행 했음을 나타냅니다.

작업 실행이 오류로 인해 중단 되는 경우 대상으로 성공적으로 이동한 할당 되지 않은 숫자 범위는 작업 폼의 대상에 유지 되 고 마이그레이션할 수 없는 나머지 범위는 유지 됩니다. 원본 및 작업 폼 나머지 구성을 완전히 마이그레이션하려면 오류를 해결 한 후 스크립트를 다시 실행 합니다.

### <a name="purpose"></a>것

지정 되지 않은 번호 공지 사항 마이그레이션 스크립트는 다음 세 가지 시나리오에서 사용할 수 있습니다.

- **새 버전의 비즈니스용 Skype 서버에 구성 설정을 마이그레이션합니다.** Contoso는 비즈니스용 Skype Server 2015으로 마이그레이션하고 마이그레이션 프로세스의 일부로, 비즈니스용 Skype 서버 관리자가 알림 신청 중 할당 되지 않은 번호 구성을 Lync에서 이동 하 고 싶습니다. 새로운 비즈니스용 Skype Server 2015 배포에 대 한 서버 2013 배포. 구성 설정을 이동 하려면 비즈니스용 Skype 서버 관리자가 할당 되지 않은 번호 알림 마이그레이션 도구를 사용 합니다.

- **비즈니스용 Skype 서버 2015에서 Lync server 2013으로 배포 롤백:** 예기치 않은 요인으로 인해 Contoso는 새로운 비즈니스용 Skype Server 2015 배포로 마이그레이션을 롤백해야 합니다. 서비스 중단을 최소화 하기 위해 비즈니스용 Skype 서버 관리자는 할당 되지 않은 번호 알림 마이그레이션 도구를 사용 하 여 비즈니스용 Skype Server 2015 배포에서 Lync Server 2013 배포로 구성을 롤백합니다.

- **배포 간에 데이터 이동:** Contoso는 한 풀의 모든 서버를 최신 서버로 바꾸는 과정을 진행 중입니다. 이 전략은 새로운 비즈니스용 Skype Server 2015 풀을 배포 하 고, 이전 버전의 모든 데이터를 새 풀로 이동한 다음, 이전 풀을 사용 안 함 하는 것입니다. 새 풀이 배포 된 후에는 할당 되지 않은 번호 알림 마이그레이션 도구를 사용 하 여 구성을 이전 풀에서 새 항목으로 이동 합니다.

#### <a name="requirements"></a>요구 사항

다음은 도구를 성공적으로 실행 하는 데 필요한 주요 요구 사항입니다.

1. 이 스크립트는 비즈니스용 Skype 서버 관리 셸이 설치 된 컴퓨터에서 실행 해야 합니다.

2. 알림 응용 프로그램은 원본 및 대상 비즈니스용 Skype 서버 또는 풀에 성공적으로 배포 되어야 합니다.

#### <a name="move-csannouncementconfiguration-script"></a>이동-CsAnnouncementConfiguration 스크립트

CsAnnouncementConfiguration 스크립트는 아래 표에 설명 된 두 가지 매개 변수를 필요로 합니다.

![Move-CsAnnouncementConfiguration 매개 변수.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a>예제

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a>할당 되지 않은 번호 알림 구성을 Lync Server 2013 풀에서 비즈니스용 Skype Server 2015 풀로 이동

이 예제에서는 할당 되지 않은 번호 알림을 원본 풀 (Lync Server 2013)에서 대상 풀 (비즈니스용 Skype Server 2015)으로 이동 합니다.

```
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a>할당 되지 않은 번호 알림 구성을 비즈니스용 Skype 서버 2015 풀에서 Lync Server 2013 풀로 이동

이 예제에서는 원본 풀 (비즈니스용 Skype Server 2015)의 할당 되지 않은 번호 알림을 대상 풀 (Lync Server 2013)로 이동 합니다.

```
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a>웹 회의 데이터
<a name="WebConfData"> </a>

웹 컨퍼런스 데이터 도구를 사용 하 여 비즈니스용 Skype Server 2015 통신 소프트웨어의 관리자는 이끌이의 웹 회의와 관련 된 데이터를 보다 효율적으로 제어할 수 있습니다. 시나리오에는 타임 스탬프 조건을 기반으로 특정 사용자의 모임 데이터를 삭제 하는 기능이 포함 됩니다.

### <a name="description"></a>설명

이 도구는 관리자가 다음 작업을 수행할 수 있도록 합니다.

1. 단일 사용자와 연결 된 모든 웹 회의 데이터를 찾습니다.

2. 단일 사용자와 연결 된 모든 웹 회의 데이터를 삭제 합니다.

3. 특정 날짜 보다 오래 된 단일 사용자와 연결 된 모든 웹 회의 데이터를 삭제 합니다.

4. 단일 사용자와 연결 된 모든 웹 회의 데이터를 다른 풀로 이동할 때 해당 항목을 이동 합니다.

> [!NOTE]
> Lync Server 2010에 대 한 리소스 키트 도구는 사용자가 단일 사용자와 연결 된 모든 웹 회의 데이터를 다른 풀로 이동할 때 지원 합니다. 이 기능은 **MoveConferenceData** 매개 변수를 위해이 도구에서 더 이상 사용 되지 않습니다. 이 매개 변수에 대 한 자세한 내용은 [CsUser Cmdlet 이동을](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) 참조 하세요.

이 도구는 비활성 상태인 모임에 대해서만 모임 데이터를 삭제 합니다. 활성 모임 (또는 세션의 모임)은 삭제할 수 없습니다.

이 도구는 대상 사용자와 같은 풀에 있는 컴퓨터에서 실행 해야 합니다. 이 도구로 모임 콘텐츠 데이터를 관리 하 고 있는 사용자는 같은 사용자 풀에 있어야 합니다.

### <a name="output"></a>결과물

이 도구는 각 작업의 결과를 출력 합니다.

- 쿼리를 수행 하면 도구가 해당 사용자를 이끌이 인 모든 비활성 모임 데이터 폴더의 목록을 출력 합니다.

- Delete를 수행 하면 해당 데이터가 삭제 될 모든 모임 데이터 폴더의 목록이이 도구에 출력 됩니다.

### <a name="requirements"></a>요구 사항

이 도구는 주최자가 현재 홈 상태에 있는 동일한 풀에서 실행 되어야 합니다.

콘텐츠 파일 저장소에 대 한 액세스 권한을 가진 관리자 권한을 사용 하 여 도구를 실행 해야 합니다.

### <a name="examples"></a>예제

다음 표에서는 예제에 사용 되는 매개 변수에 대해 설명 합니다.

![Web Conf Data Tool 매개 변수.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

앞의 예제에서는 쿼리 명령이 작동 하는 방식을 보여 줍니다. 이러한 명령의 출력은이 도구의 영향을 받을 수 있는 모든 모임 콘텐츠 폴더의 목록입니다.

```
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

앞의 예제는 delete 명령에 대 한 예입니다. 삭제 명령을 사용 하면이 사용자의 모든 비활성 모임 폴더가 제거 됩니다.

### <a name="summary"></a>요약

이 도구는 회의 모임 데이터를 보다 세부적으로 제어 해야 하는 관리자에 게 유용한 리소스가 될 수 있습니다.



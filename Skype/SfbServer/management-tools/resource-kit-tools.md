---
title: 비즈니스용 Skype 서버 2015 리소스 키트 도구 설명서
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: 이 항목에서는 각 도구의 용도와 사용 예를 포함 하 여 비즈니스용 Skype 서버 2015 리소스 키트의 도구에 대해 설명 합니다. 비즈니스용 Skype 서버 2015 리소스 키트를 사용 하면 비즈니스용 Skype 서버 2015를 배포 및 관리 하는 IT 관리자가 일상적인 작업을 보다 쉽게 수행할 수 있습니다. 예를 들어 웹 회의 데이터 도구를 사용 하 여 온라인 모임 중에 사용자가 업로드 한 데이터를 쉽게 제어할 수 있습니다. SEFAUtil 도구를 사용 하 여 사용자에 대 한 착신 전환 및 응답을 설정할 수 있습니다. IT 관리자는 이러한 도구를 사용 하 여 비즈니스용 Skype 서버 2015을 보다 효율적으로 관리할 수 있도록 권장 합니다.
ms.openlocfilehash: 7269d7c82736be8e533a0782548a94d14aafcfb5
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42160772"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a>비즈니스용 Skype 서버 2015 리소스 키트 도구 설명서

이 항목에서는 각 도구의 용도와 사용 예를 포함 하 여 비즈니스용 Skype 서버 2015 리소스 키트의 도구에 대해 설명 합니다. 비즈니스용 Skype 서버 2015 리소스 키트를 사용 하면 비즈니스용 Skype 서버 2015를 배포 및 관리 하는 IT 관리자가 일상적인 작업을 보다 쉽게 수행할 수 있습니다. 예를 들어 **웹 회의 데이터** 도구를 사용 하 여 온라인 모임 중에 사용자가 업로드 한 데이터를 쉽게 제어할 수 있습니다. **SEFAUtil** 도구를 사용 하 여 사용자에 대 한 착신 전환 및 응답을 설정할 수 있습니다. IT 관리자는 이러한 도구를 사용 하 여 비즈니스용 Skype 서버 2015을 보다 효율적으로 관리할 수 있도록 권장 합니다.

## <a name="installation-of-the-resource-kit-tools"></a>리소스 키트 도구 설치

비즈니스용 Skype 서버 2015 리소스 키트를 설치 하려면 다운로드 센터에서 [Ocsreskit .msi](https://www.microsoft.com/download/details.aspx?id=52631) 를 다운로드 하세요.

작업을 간단 하 게 설치 하려면 **Ocsreskit** 를 실행 합니다. .Msi는 다음 경로에 있는 모든 도구를 설치 합니다: **% Program Files%\Skype For Business Server 2015 \ ResKit** 자체 포함 된 실행 파일은이 폴더에 있습니다. 지원 파일도 있는 도구는 자체 하위 폴더에 있습니다.

## <a name="supported-environments"></a>지원 되는 환경

비즈니스용 skype 서버 2015에 필요한 사양에 맞는 서버에는 비즈니스용 skype 서버 2015을 실행 하는 데 주로 사용 됩니다. 2015

## <a name="resource-kit-tools-overview"></a>리소스 키트 도구 개요

다음은 비즈니스용 Skype 서버 2015 리소스 키트에 제공 되는 도구 목록입니다. 요구 사항 및 사용 예를 비롯 한 각 도구에 대 한 설명은 다음 섹션에서 다룹니다.

- [ABSConfig](resource-kit-tools.md#ABSConfig)

- [대역폭 정책 서비스 모니터](resource-kit-tools.md#bpsm)

- [대역폭 사용률 분석기](resource-kit-tools.md#bua)

- [통화 Parkometer](resource-kit-tools.md#callpark)

- [Dbanalyze.exe](resource-kit-tools.md#dba)

- [저장소 서비스 데이터 가져오기](resource-kit-tools.md#Issd)

- [Lcssync.dll](resource-kit-tools.md#LCSSync)

- [조회 사용자 콘솔](resource-kit-tools.md#LUC)

- [MsTurnPing](resource-kit-tools.md#MsTurnPing)

- [네트워크 구성 뷰어](resource-kit-tools.md#NCV)

- [응답 그룹 에이전트 라이브](resource-kit-tools.md#RGAL)

- [SEFAUtil](resource-kit-tools.md#SEFAUtil)

- [Sysprep.inf](resource-kit-tools.md#SYSPrep)

- [할당 되지 않은 번호 알림 마이그레이션](resource-kit-tools.md#UNAM)

- [웹 회의 데이터](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a>ABSConfig
<a name="ABSConfig"> </a>

ABSConfig (주소록 서비스 구성 도구)는 관리자가 비즈니스용 Skype 서버 2015에서 주소록 서비스 구성을 사용자 지정 하는 데 사용할 수 있는 관리 도구입니다. 또한이 도구는 비즈니스용 Skype 서버 2015 관리자가 기본 주소록 서비스 설정을 복원할 수 있도록 합니다.

### <a name="description"></a>설명

ABSConfig는 관리자가 주소록 서비스와 관련 된 Active Directory 도메인 서비스 특성을 구성할 수 있도록 하는 그래픽 사용자 인터페이스 응용 프로그램입니다.

도구에 대 한 기본 시나리오는 다음과 같습니다.

- 관리자가 Active Directory 도메인 서비스의 특성을 비즈니스용 Skype 서버 2015의 특성에 매핑할 수 있도록 합니다.

- 관리자가 주소록 서비스 파일에 포함 하거나 제외할 Active Directory 도메인 서비스 특성을 지정할 수 있도록 하려면

- 관리자가 기본 주소록 서비스 설정을 복원 하도록 설정 합니다.

ABSConfig 도구는 ABSConfig 파일을 사용 하 여 시작할 수 있습니다. 도구를 열면 **특성 구성** 탭이 열립니다. 이 테이블에는 Active Directory 도메인 서비스 특성을 비즈니스용 Skype 서버 2015의 특성 필드에 매핑하고, 특정 특성 필터를 기준으로 주소록 서비스 파일에 포함 하거나 제외할 사용자를 지정 하는 옵션이 포함 되어 있습니다. 또한 주소록 파일에 포함할 전화 번호의 값을 사용자 지정 하는 옵션도 있습니다. 관리자는 **기본값 복원** 옵션을 사용 하 여 주소록 서비스 설정을 기본값으로 복원할 수 있습니다.

> [!NOTE]
> AD 특성을 다른 OC 필드 이름에 다시 매핑하는 것은 주소록 파일 다운로드에만 작동 하며, 주소록 웹 쿼리에서는 지원 되지 않습니다.

### <a name="output"></a>출력

ABSConfig는 주소록 서비스 구성을 데이터베이스에 저장 합니다.

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a>용도

ABSConfig에서는 비즈니스용 Skype 서버 2015 주소록 서비스를 빠르고 쉽게 사용자 지정할 수 있는 방법을 제공 합니다.

### <a name="requirements"></a>요구 사항

#### <a name="computer"></a>컴퓨터

ABSConfig는 비즈니스용 Skype 서버 2015이 설치 된 도메인에 가입 된 컴퓨터 에서만 실행할 수 있습니다. 비즈니스용 Skype 서버 2015, Enterprise Edition의 경우 설치 중에 주소록 서비스가 사용 하도록 설정 된 모든 프런트 엔드 서버에서이 도구를 실행할 수 있습니다.

#### <a name="network"></a>네트워크

컴퓨터가 프런트 엔드 풀 및 백 엔드 데이터베이스에 연결할 수 있어야 합니다.

#### <a name="software"></a>소프트웨어

ABSConfig 도구를 실행 하려면 먼저 다음 소프트웨어 구성 요소를 설치 해야 합니다.

- 비즈니스용 Skype 서버 2015

#### <a name="users"></a>사용자

비즈니스용 Skype 서버 2015 배포를 업데이트 하는 데 필요한 사용 권한이 있는 관리자입니다.

### <a name="examples"></a>예제

ABSConfig는 명령 프롬프트에서 **ABSConfig** 를 입력 하 여 시작할 수 있습니다. 아래에는 ABSConfig 도구 사용자 인터페이스가 나와 있습니다.

![ABSConfig 도구](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a>요약

관리자는 ABSConfig 도구를 사용 하 여 비즈니스용 Skype 서버 2015 주소록 서비스를 빠르고 쉽게 사용자 지정할 수 있습니다.

## <a name="bandwidth-policy-service-monitor"></a>대역폭 정책 서비스 모니터
<a name="bpsm"> </a>

대역폭 정책 서비스 모니터 도구는 관리자가 다음 목록을 볼 수 있도록 하기 위한 것입니다.

1. 토폴로지의 모든 구성 된 비즈니스용 Skype 서버 2015 대역폭 정책 서비스 (인증 및 코어)

2. 각 서비스가 다른 대역폭 정책 서비스와에 지 서버에 대해 수행 하는 연결

3. 네트워크 구성 문서에 구성 된 모든 링크 및 각 대역폭 정책 서비스에서 보고 하는 실시간 대역폭 사용

### <a name="description"></a>설명

대역폭 정책 서비스 모니터 도구는 GUI 기반 응용 프로그램으로 구현 됩니다. 관리자가 도구를 시작 합니다.

이 도구는 시작 될 때 토폴로지의 대역폭 정책 서비스 목록을 검색 합니다. 초기 업데이트가 완료 되 면 창 왼쪽의 창에는 자신이 속한 클러스터 별로 그룹화 된 서비스 목록이 채워집니다.

관리자가 특정 대역폭 정책 서비스를 선택 하면 오른쪽의 창에 해당 특정 서비스에 대 한 정보가 표시 됩니다. 또한이 창에는 정보를 표시 하는 두 개의 기본 탭이 있습니다.

#### <a name="machine-info-tab"></a>컴퓨터 정보 탭

**컴퓨터 정보** 탭에는 선택한 대역폭 정책 서비스의 세부 정보 및 선택한 대역폭 정책 서비스에 의해 다른 서비스에 대 한 모든 연결의 목록과 상태가 표시 됩니다.

#### <a name="topology-info-tab"></a>토폴로지 정보 탭

**토폴로지 정보** 탭에는 네트워크 구성 설정에 구성 되어 있는 모든 링크의 목록이 표시 됩니다. 각 링크에 대해 오디오 및 비디오 대역폭 용량이 표시 됩니다. 또한 현재 사용 되는 대역폭이 Kbps 및 용량에 대 한 백분율로 표시 됩니다. 이 도구는 색 구분을 사용 하 여 용량과 근접 한 사용률을 갖는 링크를 강조 표시 하므로 관리자가 이러한 링크를 빠르게 분리할 수 있습니다.

> [!NOTE]
>  대역폭 정책 서비스 모니터 도구에서 구성 된 대역폭 정책 서비스에 연결할 때 오류가 발생 하면 **컴퓨터 정보** 및 **토폴로지 정보** 탭의 정보가 채워지지 않습니다. 그러나이 도구는 처음에는 연결할 수 있지만 이후에는 서비스에 대 한 연결이 끊어질 수 있습니다. 이러한 경우 관리자에 게 오래 된 정보가 표시 될 수 있습니다. 관리자가 특정 대역폭 정책 서비스에 대해 데이터를 마지막으로 업데이트 한 날짜를 볼 수 있도록 허용 하는 각 탭에 **마지막으로 업데이트** 된 타임 스탬프가 있습니다.

### <a name="output"></a>출력

명령줄 출력은 없습니다. 프로그램 출력은 기본 GUI (그래픽 사용자 인터페이스) 내에 포함 됩니다.

### <a name="purpose"></a>용도

대역폭 정책 서비스 모니터 도구의 목적은 관리자가 토폴로지에 정의 된 각 대역폭 정책 서비스의 상태를 볼 수 있도록 하는 것입니다. 또한 관리자는 네트워크 구성 문서에 정의 된 모든 링크에 대 한 실시간 대역폭 사용을 볼 수 있습니다.

### <a name="requirements"></a>요구 사항

비즈니스용 Skype 서버 토폴로지의 일부인 컴퓨터에서 대역폭 정책 서비스 모니터 도구를 실행 해야 합니다.

### <a name="summary"></a>요약

대역폭 정책 서비스 모니터 도구는 토폴로지의 모든 대역폭 정책 서비스 상태를 검사할 수 있도록 관리자에 게 유용한 리소스가 될 수 있으며, 더 중요 한 역할을 하는 링크에 대 한 실시간 대역폭 사용률을 얻을 수 있습니다. 네트워크 구성 설정에 정의 되어 있습니다.

## <a name="bandwidth-utilization-analyzer"></a>대역폭 사용률 분석기
<a name="bua"> </a>

대역폭 사용률 분석기는 엔터프라이즈 네트워크의 WAN 링크에서 UC 끝점에 의해 다양 한 대역폭 소비 보기에 대 한 보고서를 작성 하는 도구입니다. 이러한 보고서를 사용 하 여 현재 대역폭 소비 패턴을 이해 하 고 대역폭 용량 계획에 도움을 받을 수 있습니다.

### <a name="description"></a>설명

대역폭 사용률 분석기는 GUI 기반 응용 프로그램으로 구현 됩니다. 이 도구는 네트워크를 통한 오디오 사용률에 대 한 보고서를 생성 하 고 용량 계획에 도움이 됩니다. 또한 다양 한 링크에 할당 된 대역폭 용량을 반복 합니다.

### <a name="output"></a>출력

대역폭 사용률 분석기는 시스템에 구성 되어 있는 모든 WAN 링크에 대 한 대역폭 용량 및 오디오 사용률을 그래픽으로 플롯 합니다.

### <a name="purpose"></a>용도

음성 및 비디오 배포에서는 엔터프라이즈 네트워크 전체에서의 대역폭 사용률 추세를 모니터링 하 고 이해 하는 것이 중요 합니다. 대역폭 사용률 분석기 도구를 사용 하면 관리자가 해당 항목만 얻을 수 있습니다. 이 도구는 다음을 수행 합니다.

- 네트워크를 통한 오디오 사용률에 대 한 특정 보고서 생성

- 다양 한 링크에 할당 된 대역폭 용량에 대 한 보다 효율적인 용량 계획 및 반복을 지원 합니다.

대역폭 사용률 분석기는 대역폭 용량 및 사용률 보고서의 그래픽 플롯을 생성할 수 있습니다. 이러한 작업은 다음과 같습니다.

- 엔터프라이즈 네트워크의 모든 WAN 링크

- 선택한 WAN 링크로 필터링 됨

- 연결 용량을 초과한 WAN 링크로 필터링 됨

- 프로 비전 된 대역폭을 이용 하 여 온 WAN 링크로 필터링 됨

- 중요 한 수준에 도달한 WAN 링크로 필터링 (WAN 링크의 대역폭 용량을 90% 초과 하는 대역폭 사용률)

- WAN 링크 유형 (네트워크-사이트 링크, 인터 지역별 링크 및 사이트 내의 링크)을 기준으로 필터링 됨

- 네트워크 지역별로 필터링 됨

#### <a name="applications"></a>응용 프로그램

대역폭 사용률 분석기에는 다음과 같은 두 가지 응용 프로그램 (도구)이 있습니다.

- **WanLinkLogCollector** 이 도구는 사용자가 필요한 정보를 입력할 수 있도록 합니다.

- **BandwidthUtilizationAnalyzer** Microsoft Excel 스프레드시트 소프트웨어 보고서는 WanLinkLogCollector를 통해 자동으로 시작 됩니다. 이 응용 프로그램을 통해 사용자는이 문서 뒷부분에 나와 있는 것 처럼 보고서에 필터를 적용할 수 있습니다.

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a>대역폭 사용률 분석기 사용 단계

대역폭 사용률 분석기를 사용 하는 경우 두 가지 단계가 있습니다.

- WanLinkLogCollector을 사용 하 여 수행 되는 로그 수집

- BandwidthUtilizationAnalyzer을 사용 하 여 수행 되는 보고서 사용자 지정

    > [!IMPORTANT]
    > 최종 사용자가 수동으로 BandwidthUtilizationAnalyzer을 실행 하는 것이 좋습니다.

#### <a name="starting-bandwidth-utilization-analyzer"></a>대역폭 사용률 분석기 시작

명령 프롬프트 또는 Windows 탐색기를 사용 하 여 WanLinkLogCollector을 시작 합니다.

 **WanLinkLogCollector 사용**

WanLinkLogCollector를 사용 하는 세 가지 단계는 다음과 같습니다.

1. **시간 표시 막대 기록** 보고서를 생성 해야 하는 시간 표시 막대를 제공 합니다.

2. **파일 디렉터리 지정** 파일 위치 정보 제공

3. **로그 수집 및 보고서 뷰어 실행** 보고서를 생성 하는 명령을 실행 합니다.

#### <a name="step-1---log-the-timeline"></a>1 단계-시간 표시 막대 기록

시간 표시줄 로깅을 사용 하면 도구 사용자가 아래 그림에 나와 있는 것 처럼 다음을 지정할 수 있습니다.

1. **시작 날짜** 보고서를 생성할 시간 표시 막대의 시작 날짜입니다. 예를 들어, 2010 년 8 월 1 일

2. **종료 날짜** 보고서를 생성할 시간 표시 막대의 종료 날짜 이며, 예를 들어, 2010 년 9 월 30 일을 예로 들 있습니다.

     ![대역폭 사용률 A의 시작 및 종료 날짜](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a>2 단계-파일 디렉터리 지정

표시 된 대로 사용자가 다음 파일 디렉터리를 지정할 수 있습니다.

- **서버 로그 파일 위치** 대역폭 정책 서버 로그가 저장 되는 폴더 위치입니다. 일반적으로 op-fileserver \<\> \\<에서 FE\>\AppServerFiles\PDP.을 선택 합니다.

- **임시 파일 저장 위치** 보고서를 생성 하는 동안 중간 파일이 저장 되는 임시 파일 위치입니다.

    ![대역폭 사용률의 파일 디렉터리](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > 서버 로그 및 임시 파일 저장소 폴더에 대 한 충분 한 파일 액세스 권한이 도구 사용자에 게 제공 되는지 확인 합니다.

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>3 단계-로그를 수집 하 고 보고서 뷰어를 시작 합니다.

로그를 수집 하 고 보고서 뷰어를 시작 하려면 아래 표시 된 대로 **실행** 을 클릭 합니다. 이 단계에서는 필요한 데이터를 수집 합니다.

![대역폭 사용률 Utilization에서 데이터 수집](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

입력 유효성 검사가 성공적으로 완료 되 면 아래 표시 된 메시지가 표시 됩니다.

![Utili 대역폭에서 수집 된 알림을 기록 합니다.](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

**확인**을 클릭합니다. BandwidthUtilizationAnalyzer가 자동으로 시작 됩니다. 메시지 상자의 지침을 따릅니다. 자세한 내용은 다음 섹션에서 **BandwidthUtilizationAnalyzer 사용** 을 참조 하십시오.


### <a name="using-bandwidthutilizationanalyzerxlsm"></a>BandwidthUtilizationAnalyzer 사용

1. BandwidthUtilizationAnalyzer가 자동으로 시작 되 면 아래 표시 된 대로 **새로 고침** 을 클릭 합니다.

     ![BandwidthUtilizationAnalyzer. .xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. 파일 폴더가 열리면 아래와 같이 메시지 상자에 지정 된 위치에서 통합 .csv를 선택 합니다. 또한 **C:\Temp**로 위치를 표시 합니다.

     ![BandwidthUtilizationAnalyzer에서 폴더 열기](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. **가져오기**를 클릭합니다.

4. 그래픽 플롯이 자동으로 생성 됩니다. 배경 작업 포인터가 사라지면 서 사용할 수 있습니다.

     ![보고서 보기에 필터를 적용 합니다.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a>보고서 보기에 필터 적용

아래에 표시 된 것 처럼 보고서 보기에 적용할 수 있는 필터는 다음과 같이 설명 됩니다.

![보고서 보기에 필터를 적용 합니다.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. **이름** WAN 링크로 필터링 (그래프 오른쪽에 필터가 있습니다.) 접두사는 다음 링크 형식을 나타냅니다. 세로 (파란색) 상자를 표시 합니다.

   - **S 사이트** 네트워크 사이트에서 네트워크 지역으로의 WAN 연결

   - **사이트 간** 두 네트워크 사이트 간의 WAN 링크

   - **R 지역 간** 두 네트워크 지역 간의 WAN 링크

2. **제한 초과** 대역폭 사용량이 대역폭 용량 보다 많은 WAN 링크로 필터링

3. **중요 수준** 대역폭 사용률이 대역폭 용량 보다 90% 이상에 도달 했을 때의 WAN 링크로 필터링

4. **미달 사용** 대역폭 사용률이 대역폭 용량의 25% 미만인 WAN 링크로 필터링

5. **연결 유형** 다음 WAN 링크 유형으로 필터링:

   - **네트워크 사이트** 유형

   - **사이트 간** 유형

   - **지역 간 링크** 형식

6. **지역** 네트워크 지역별로 필터링

다음 그림에서는 앞에서 설명한 필터를 보여 줍니다.

**이름을**기준으로 필터링 합니다. 그래프에 표시 해야 하는 링크 목록을 선택 합니다.

![BandwidthUtilizationAnalyzer에서 이름을 기준으로 필터링 합니다.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

**제한을 초과**하 여 필터링 합니다. **True** 를 선택 하 여 필터를 적용 합니다.

![제한을 초과한 필터링](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

**중요 수준**으로 필터링 합니다. **True** 를 선택 하 여 필터를 적용 합니다.

![중요 수준별로 필터링](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

**과소**사용으로 필터링 합니다. **True** 를 선택 하 여 필터를 적용 합니다.

![과소 사용을 기준으로 필터링](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

**링크 형식**으로 필터링 합니다. 표시 해야 하는 유형을 선택 합니다.

![링크 형식별 필터링](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

**지역별로**필터링 링크를 표시 해야 하는 지역 목록을 선택 합니다.

![지역별 필터링](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a>요구 사항

- .NET Framework 3.5

- Microsoft Excel 2010 또는 Excel 2007

### <a name="summary"></a>요약

대역폭 사용률 분석기는 네트워크를 통해 UC 트래픽에 대 한 오디오 대역폭 사용률을 그리는 데 사용 됩니다. 이 도구는 네트워크의 비디오 대역폭 사용률을 보고 하는 데에도 사용할 수 있습니다.

## <a name="call-parkometer"></a>통화 Parkometer
<a name="callpark"> </a>

Call Parkometer는 통화 대기 궤도 데이터베이스에 쉽게 액세스할 수 있게 해 주는 명령줄 응용 프로그램입니다.

### <a name="description"></a>설명

Call Parkometer는 현재 대기 중인 통화를 추적 하는 도구입니다. 또한 궤도 및 CPS (통화 대기 서버) 사용에 대 한 통계를 수집 합니다. 이 명령줄 도구는 로컬 또는 원격으로 연결 된 컴퓨터에서 CPS 궤도 SQL Server 데이터베이스에 대 한 읽기 및 쓰기 액세스를 모두 제공 합니다.

모든 옵션은 함께 사용할 수 없습니다. 명령줄 구문은 다음과 같습니다.

- **-o** parameter-이 풀에 대해 구성 된 모든 궤도 범위를 나열 합니다.

- **-n** 매개 변수-이 풀에서 현재 사용 된 모든 궤도를 나열 합니다. 표시 되는 정보는 다음과 같습니다.

  - Parkee 및 parker의 SIP URI (Uniform Resource Identifier)입니다.

  - 통화가 대기 중인 CPS의 호스트 이름입니다.

  - 통화가 대기 되었을 때의 타임 스탬프입니다.

- **-f** 매개 변수-풀에서 현재 사용 가능한 궤도의 수를 나열 합니다.

- **-r \<n\> ** 매개 변수-\> 마지막 \<으로 대기 된 통화를 나열 합니다. 표시 되는 정보는 다음과 같습니다.

  - Parkee SIP URI입니다.

  - Parker SIP URI입니다.

  - 통화가 파킹 된 CPS의 호스트 이름입니다.

  - 통화를 검색 하거나 삭제할 때의 타임 스탬프입니다.

- **-t\<n\> ** 매개 변수-데이터베이스의 궤도를 예약 하 여 지정 된 궤도 번호의 임의성을 표시 하는 테스트입니다.

### <a name="output"></a>출력

명령 프롬프트에서 지정한 입력 매개 변수에 따라 Call Parkometer에는 다음과 같은 출력이 표시 됩니다.

- 이 풀에 대해 구성 된 모든 궤도 범위

- 현재 대기 중인 통화

- 사용할 수 있는 사용 가능한 공간 (사용 가능) 궤도

- 최근 대기 통화

- Uniform 및 random 궤도 값을 테스트 하기 위해 예약 된 궤도

### <a name="purpose"></a>용도

CPS 도구의 용도는 CPS 데이터베이스에 대 한 명령줄 액세스를 제공 하는 것입니다. 관리자는 CPS 사용량을 확인 하 고 풀에 할당 된 궤도 수를 확인할 수 있습니다.

### <a name="requirements"></a>요구 사항

CPS를 실행 하는 동일한 컴퓨터에서이 도구를 실행 하는 경우에는 요구 사항이 없습니다. 이 도구를 원격 컴퓨터에서 실행 하는 경우 비즈니스용 Skype 서버 2015에서 사용 하는 SQL Server 데이터베이스를 원격 액세스를 허용 하도록 구성 해야 합니다. 풀의 SQL Server에 연결 하려면 Call Parkometer를 SQL Server 데이터베이스 연결 문자열로 구성 해야 합니다. 이 SQL Server 데이터베이스 연결 문자열은 구성 파일인 **parkometer**에 정의 되어 있습니다. Parkometer가 있는 디렉터리에 배치 해야 합니다. 다음 XML 파일은 parkometer의 예입니다. 구성 해야 하는 매개 변수는 사용자 이름 (예: mydomain\Administrator), 암호 (예: mypassword) 및 호스트 이름 (예: myserver)입니다.

```xml
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

배포한 궤도 범위:-o 매개 변수는 표시 된 것 처럼이 풀에 대해 구성 된 모든 궤도 범위를 나열 합니다.

![통화 Parkometer의 궤도 범위입니다.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

현재 대기 중인 통화:-n 매개 변수는이 풀에서 현재 사용 되는 모든 궤도를 표시 된 대로 나열 합니다.

![통화 Parkometer에서 현재 대기 중인 통화입니다.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

Free 궤도의 수:-f 매개 변수는 다음과 같이 풀에 현재 사용 가능한 궤도 수를 나열 합니다.

![통화 Parkometer의 무료 궤도입니다.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

최근에 대기 된 통화:-r \<n\> 매개 변수는 \<표시\> 된 대로 마지막으로 대기 중인 통화를 나열 합니다.

![통화 Parkometer의 최근에 파킹 된 통화입니다.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

Test 궤도 예약:-t \<n\> 매개 변수 테스트에서는 다음과 같이 데이터베이스의 궤도를 예약 합니다.

![통화 Parkometer에서 궤도 예약을 테스트 합니다.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a>요약

Call Parkometer는 통화 대기 서버에 대 한 자세한 정보를 제공 하는 명령줄 도구입니다.

## <a name="dbanalyze"></a>Dbanalyze.exe
<a name="dba"> </a>

### <a name="description"></a>설명

DBAnalyze는 관리자가 비즈니스용 Skype 서버 2015 데이터베이스에 대 한 분석 보고서를 수집할 수 있도록 하는 명령줄 도구입니다. DBAnalyze에는 진단, 사용자 데이터, 회의, MCUs 및 디스크 조각화 모드가 있습니다.

- **진단 모드** 테이블에 대 한 정보를 포함 하는 보고서를 만듭니다 (레코드 수, 조각 모음, 데이터 크기 및 인덱스 크기), 데이터 및 로그 파일 크기, 이전 백업 시간, Microsoft Office Communications Server를 실행 하는 서버 간, 최대 사용 권한, 연락처, 컨테이너, 구독, 게시, 사용자 당 작업 수, 잘못 된 홈 사용자, 모든 부적절 한 연결, 사용자 당 구성 된 전화 회의 수, 예약 된 전화 회의, 활성 회의의 평균 횟수 데이터베이스 버전

    > [!NOTE]
    > 진단 모드 실행은 서버 성능에 영향을 줄 수 있습니다.

- **사용자 데이터 모드** 지정 된 사용자 또는 해당 사용자가 대화 상대 및 사용 권한 목록에 있는 사용자에 대 한 연락처, 컨테이너, 구독, 게시, 사용 권한 및 연락처 그룹 데이터를 보고 합니다. 또한이 모드는 사용자가 구성 하거나 초대 하는 전화 회의에 대 한 요약 데이터를 보고 합니다.

- **전화 회의 모드** 회의에 대 한 모든 일정 시간 정보, 초대 대 상자, 회의에 허용 되는 미디어 유형 목록, 활성 참가자 목록 및 각 참가자의 신호 상태를 비롯 하 여 특정 회의에 대 한 자세한 데이터를 보고 합니다.

- **디코드 모임 ID** **/Pstnid** 스위치로 지정 되는 공중 전화망 (PSTN) 모임 ID를 디코딩하고 자세한 정보는 백 엔드에 연결 하지 않습니다.

- **전화 회의 문제 해결** **/Pstnid** 스위치에 지정 된 PSTN 모임 id를 디코딩하고 ID가 나타내는 전화 회의에 대 한 정보를 표시 합니다.

- **MCUs 모드** 풀의 각 MCU에 대 한 ID, 미디어 유형, URL, 하트 비트 상태, 회의 부하 및 참가자 부하를 보고 합니다.

- **디스크 조각화 모드** 모든 디스크의 조각화 상태를 표시 합니다.

이 도구를 사용 하 여 다양 한 문제를 진단 하거나 관리자가 용량 계획을 지원할 수 있습니다. 예를 들어 서버 A에 있는 대부분의 사용자가 자신의 연락처로 서버 B에 있는 사용자를 선택 하는 경우 관리자는 서버 A의 사용자를 서버 B로 이동 하 여 서버 간 트래픽을 줄일 수 있습니다.

### <a name="output"></a>출력

이 도구는 비즈니스용 Skype 서버 2015 데이터베이스에 대 한 미리 정의 된 보고서를 출력 합니다. **경로**:%ProgramFiles%\Skype For Business Server 2015 \ Reskit

### <a name="purpose"></a>용도

Dbanalyze .exe를 설치 하려면 로컬 폴더에 복사한 다음 도구를 실행 합니다. 이 도구를 사용 하려면 명령줄에서 다음 명령을 실행 합니다. `dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`명령줄 옵션에 대 한 설명은 아래와 같습니다.

![Dbanalyze에 대 한 명령줄 옵션입니다.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a>요구 사항

 **컴퓨터** DBAnalyze는 비즈니스용 Skype 서버 2015이 설치 된 도메인에 가입 된 컴퓨터 에서만 실행할 수 있습니다.

 **네트워크** 컴퓨터에서 백 엔드 데이터베이스에 연결할 수 있어야 합니다.

 **소프트웨어** DBAnalyze를 실행 하기 전에 비즈니스용 Skype 서버 2015 소프트웨어 구성 요소를 설치 해야 합니다.

 **사용자** 아래 표에는 비즈니스용 Skype 서버 2015 데이터베이스에 액세스 하는 데 필요한 권한이 있는 관리자가 나와 있습니다.

![Dbanalyze에 대 한 사용 권한 테이블](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> **/Preport: 디스크** 모드에는 로컬 관리자 계정이 필요 합니다.

### <a name="examples"></a>예제

다음은 유효한 Dbanalyze 명령에 대 한 예입니다.

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a>요약

DBAnalyzer를 통해 관리자는 비즈니스용 Skype 서버 2015 데이터베이스를 빠르고 쉽게 분석할 수 있습니다.

## <a name="import-storage-service-data"></a>저장소 서비스 데이터 가져오기
<a name="Issd"> </a>

ImportStorageServiceData resource kit 도구를 사용 하면 저장소 서비스 (LYSS)에서 플러시된 큐 및 끝점 데이터를 저장소 서비스로 다시 가져올 수 있습니다.

### <a name="description"></a>설명

저장소 서비스에서 플러시된 데이터는 큐 항목 상태 또는 데이터베이스 크기에 따라 자동 (주기적)이 될 수 있습니다. 이 문제는 풀 장애 조치 (failover) cmdlet 또는 풀 장애 조치 (failover) cmdlet이 호출 하는 StorageServiceFullFlush cmdlet의 수동 호출로 인해 발생 했을 수 있습니다. 프런트 엔드에서 저장소 서비스 (LYSS) 데이터베이스 크기가 일반 수준 위에 있는 경우에는 데이터를 다시 가져올 필요가 없기 때문에이 작업을 수행 하면 더 많은 데이터를 다시 내보낼 수 있습니다. 또한 저장소 서비스 큐 증가를 일으킨 오류에 대 한 영향을 받을 수 있는 모든 문제 (예: Exchange 끝점 오류, 네트워크 문제 또는 기타 문제)를 먼저 해결 해야 합니다.

 **시나리오 1:** 풀 장애 조치 (failover) 중에 각 프런트 엔드에서 파일을 저장소 서비스에서 플러시할 수 있습니다. 장애 조치 (failover)가 완료 되 면 도구를 실행 하 여 데이터를 다시 가져와야 합니다.

 **시나리오 2:** 데이터를 매일 자동으로 플러시 중이거나 저장소 서비스 데이터베이스에 대 한 응답으로 특정 크기 임계값 (예: 60%, 80%, 90% full)을 초과 하는 경우 자동으로 플러시된 데이터는 관리자가 정기적으로 다시 가져와야 합니다. 위의 상황에서 모니터링 SCOM pack이 배포 되지 않은 경우 저장소 서비스에서 플러시하는 데이터와 관련 된 비즈니스용 Skype 서버 저장소 서비스에 대 한 이벤트가 있습니다. 이벤트 Id 32075 (전체 플러시 작업을 시작 함), 32076 (전체 플러시 완료), 32082 (유지 관리 수준 플러시 시작), 32083 (, 유지 관리 수준 플러시 완료), 32089 (데이터베이스를 채우는 중에 플러시 발생) 참고 이러한 이벤트 Id는 RTM 릴리스에 해당 합니다. 관리자에 게 이러한 이벤트가 표시 되 면 플러시 된 파일이 있음을 의미 합니다. 이 도구를 사용 하 여이 데이터를 정기적으로 다시 가져와야 합니다 (예: 일주일에 한 번).

온라인 서비스 릴리스의 경우 비즈니스용 Skype 서버에 대 한 상태 모니터링 SCOM pack이 배포 되는 경우 관리자에 게 플러시된 데이터를 다시 저장소 서비스에 재할당 하도록 요청 하는 새로운 경고가 발생할 수 있습니다. 프런트 엔드 서버의 이벤트 로그에 경고를 트리거한 해당 이벤트가 발생 합니다. 이 이벤트는 플러시된 데이터 파일이 있는 상위 경로에 대 한 설명과, 경고 조건을 충족 하는 파일 수를 제공 합니다. 경고 기준은 특정 상위 경로 아래에 Y 일이 지난 파일 (X 및 Y는 StorageService 내에서 사전 설정 되지만 APPCONFIG 파일을 변경 하 여 재정의할 수 있음)이 포함 되어 있다는 것입니다. 상태 경고를 트리거할 수 있는 이벤트의 두 가지 예는 다음과 같습니다 (상위 경로). 웹 서비스 파일 공유 아래에는 각 프런트 엔드의 로컬 응용 프로그램 데이터 디렉터리인 한 가지 가능성이 있습니다. (예: c:\ProgramData\Microsoft\Skype for Business Server 2015 \ StorageService). 그러면 관리자가이 reskit 도구를 실행 합니다.

이 도구는 도구를 실행 하는 프런트 엔드에서 데이터를 소유 하지 않는 경우에도 실행 중인 프런트 엔드에서 CPU 및 IO 부하를 증가 시킵니다. 프런트 엔드의 CPU 및 IO 부하가 많지 않은 경우 (예: 사용량이 가장 많은 시간 외에)이 도구를 사용 하는 것이 좋습니다. 그런 다음이 도구는 데이터 파일 하나를 가져오는 데 2 ~ 3 분이 걸릴 수 있습니다. 도구 실행 시간을 추정할 때이 점에 유의 하세요. 도구에서 생성 되는 자세한 로그 파일은 기본적으로 파일 저장소에 표시 됩니다. 로그 파일의 크기가 수십 개이 하 이므로 오류가 보고 되지 않은 경우 삭제 합니다.

![예제 저장소 서버 이벤트 로그 이벤트](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a>요구 사항

비즈니스용 Skype 서버 2015 리소스 키트 도구를 설치 합니다. 이 도구는 비즈니스용 Skype 서버 및 비즈니스용 Skype 서버 관리 셸이 설치 된 도메인에 가입 된 컴퓨터에서 실행 됩니다. 이 도구는 관리 셸에서 cmdlet을 사용 하 여 풀의 모든 프런트 엔드 서버를 식별 합니다. 그런 다음 **RtcLocal** 데이터베이스가 설치 된 풀의 컴퓨터에서 도구를 실행 해야 합니다. 이 데이터베이스는 도구에서 풀에 대 한 WEBSERVICE 파일 공유 위치를 검색 하는 데 사용 됩니다. 또한이 도구를 사용 하기 전에 각 프런트 엔드 서버에서 먼저 각 프런트 엔드 서버에서 **enable-psremoting** 를 사용 하 여 Windows PowerShell Remoting을 사용 하도록 설정 해야 하며,이 도구를 실행 하는 컴퓨터도 필요 합니다. 그렇지 않은 경우에는이 도구의 원격 Windows PowerShell 명령이 실패 합니다. 풀에 있는 모든 프런트 엔드 서버를 완료 한 후에는 Windows PowerShell Remoting을 끌 수 있습니다. 마지막으로 도구를 호출 하는 계정 또는 자격 증명에는이 도구를 실행 하는 풀에 대 한 webservice 파일 공유에 대 한 읽기/쓰기 권한이 있어야 합니다. 그렇지 않으면 도구에서 IO 권한 오류가 발생 하지 않습니다.

> [!NOTE]
> Windows Server 2012에서는 windows PowerShell Remoting이 기본적으로 사용 하도록 설정 되어 있지만 Windows Server 2008 운영 체제에서는 사용할 수 없습니다.

### <a name="examples"></a>예제

```console
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

## <a name="lcssync"></a>Lcssync.dll
<a name="LCSSync"> </a>

LCSSync 도구는 다중 포리스트 환경에서 비즈니스용 Skype 서버 2015 통신 소프트웨어를 배포 하는 데 도움이 됩니다. 이 도구는 다른 사용자 포리스트에서 사용자 및 그룹을 Active Directory 도메인 서비스 연락처 개체로 동기화 하 여 비즈니스용 Skype 서버 2015이 설치 된 중앙 포리스트로 연결 하는 데 사용 됩니다.

### <a name="description"></a>설명

 LCSSync는 중앙 포리스트에서 동기화 된 Active Directory 도메인 서비스 대화 상대 개체를 사용 하 여 비즈니스용 Skype 서버에 대 한 사용자를 사용 하도록 설정 합니다. Single sign-on을 제공 하려면 비즈니스용 Skype 서버 2015에 대 한 중앙 포리스트의 Active Directory 도메인 서비스 대화 상대 개체에 주 사용자 계정을 매핑해야 합니다. 이 도구는 해당 매핑을 수행 하는 데 도움이 됩니다. 이 도구는 Microsoft Identity 통합 서버에서 관리 에이전트를 만들기 위한 템플릿을 제공 합니다.

### <a name="summary"></a>요약

LCSSync 도구는 다중 포리스트 환경에서 비즈니스용 Skype 서버 2015을 배포 하는 데 도움이 됩니다.

## <a name="lookup-user-console"></a>조회 사용자 콘솔
<a name="LUC"> </a>

LookupUserConsole 도구는 특정 사용자에 대 한 내부 비즈니스용 Skype 서버 라우팅 정보를 표시 합니다. 이 정보는 Microsoft에서 배포 및 라우팅 문제를 진단 하는 데 유용할 수 있습니다.

### <a name="description"></a>설명

 LookupUserConsole을 실행 하면 SIP 주소를 허용 하 고 내부 비즈니스용 Skype 서버 라우팅 정보를 표시 하려고 하는 명령 프롬프트가 열립니다. **Exit** 를 입력 하 여 LookupUserConsole 도구를 종료 합니다.

### <a name="requirements"></a>요구 사항

비즈니스용 Skype 서버 2015 리소스 키트를 설치 합니다. 이 도구는 비즈니스용 Skype 서버가 설치 된 도메인에 가입 된 컴퓨터에서 실행 됩니다.

### <a name="examples"></a>예제

Business Server 2015에 대 한 C:\Program Files\Skype\>\ ResKit lookupuserconsole

```console
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

MSTurnPing 도구를 사용 하면 비즈니스용 Skype 서버 2015 통신 소프트웨어에서 오디오/비디오에 지 및 오디오/비디오 인증 서비스를 실행 하는 서버의 상태를 확인 하 고 토폴로지에서 대역폭 정책 서비스를 실행 하는 서버를 확인할 수 있습니다.

### <a name="description"></a>설명

MSTurnPing 도구를 사용 하면 비즈니스용 Skype 서버 2015 통신 소프트웨어에서 오디오/비디오에 지 및 오디오/비디오 인증 서비스를 실행 하는 서버의 상태를 확인 하 고 토폴로지에서 대역폭 정책 서비스를 실행 하는 서버를 확인할 수 있습니다.

이 도구를 사용 하면 관리자가 다음과 같은 테스트를 수행할 수 있습니다.

1. A/V에 지 서버 테스트:이 도구는 다음을 수행 하 여 토폴로지의 모든 A/V에 지 서버에 대해 테스트를 수행 합니다.

   - 비즈니스용 Skype 서버 오디오/비디오 인증 서비스가 시작 되었으며 적절 한 자격 증명을 발행할 수 있는지 확인 합니다.

   - 비즈니스용 Skype 서버 오디오/비디오에 지 서비스가 시작 되었는지 확인 하 고 리소스를 외부에 지에 성공적으로 할당할 수 있습니다.

2. 대역폭 정책 서비스 테스트: 도구는 다음을 수행 하 여 토폴로지에서 대역폭 정책 서비스를 실행 하는 모든 서버에 대해 테스트를 수행 합니다.

   - 비즈니스용 Skype 서버 대역폭 정책 서비스 (인증)가 시작 되었으며 적절 한 자격 증명을 발급할 수 있는지 확인 합니다.

   - 비즈니스용 Skype 서버 코어 (대역폭 정책 서비스)가 시작 되었으며 대역폭 확인을 수행할 수 있는지 확인 합니다.

토폴로지의 일부인 컴퓨터에서이 도구를 실행 하 고 로컬 저장소를 설치 해야 합니다.

### <a name="output"></a>출력

이 도구는 각 작업의 결과를 출력 합니다.

- **AudioVideoEdgeServer** 테스트를 수행 하는 경우에는 다음과 같은 도구가 출력 됩니다.

  - 토폴로지에서 비즈니스용 Skype 서버 2015 오디오/비디오 인증 서비스를 제공 하는 컴퓨터의 테스트 결과

  - 토폴로지에서 비즈니스용 Skype 서버 2015 오디오/비디오에 지 서비스를 제공 하는 컴퓨터의 테스트 결과

- **BandwidthPolicyServer** 테스트를 수행 하는 경우에는 다음과 같은 도구가 출력 됩니다.

  - 토폴로지에서 비즈니스용 Skype 서버 2015 대역폭 정책 서비스 (인증)를 제공 하는 컴퓨터의 테스트 결과

  - 해당 토폴로지에서 비즈니스용 Skype 서버 2015 코어 (대역폭 정책 서비스)를 제공 하는 컴퓨터의 테스트 결과

### <a name="requirements"></a>요구 사항

- 이 도구는 토폴로지에 있고 로컬 저장소가 있는 컴퓨터에서 실행 해야 합니다.

- 이 도구는 로컬 저장소에 대 한 액세스 권한이 있는 관리자 권한으로 실행 해야 합니다.

### <a name="examples"></a>예제

다음은 도구 입력의 예입니다.

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a>요약

이 도구는 오디오/비디오 및 대역폭 정책 서비스를 실행 하는 서버의 상태를 확인 하려는 비즈니스용 Skype 서버 2015 관리자에 게 유용한 리소스 일 수 있습니다.

## <a name="network-configuration-viewer"></a>네트워크 구성 뷰어
<a name="NCV"> </a>

비즈니스용 Skype 서버 2015 통신 소프트웨어 관리자는 네트워크 구성 뷰어를 사용 하 여 프로 비전 된 기업에 대 한 CAC (통화 허용 제어) 네트워크 토폴로지를 볼 수 있습니다 (예: 지정 된 대역폭 용량에 따른 음성 또는 비디오 통화입니다. 비즈니스용 skype 서버 2015 관리자는 비즈니스용 Skype 서버 2015와 함께 설치 되는 대역폭 정책 서비스에 의해 적용 되는 CAC 정책을 정의 합니다.

### <a name="description"></a>설명

네트워크 구성 뷰어 (NetworkConfigurationViewer)를 사용 하면 관리자가 다음 작업을 수행할 수 있습니다.

- CAC 네트워크 토폴로지를 그래픽 형식으로 비즈니스용 Skype 서버 2015 배포에서 로드 하 고 확인 합니다.

- CAC 네트워크 토폴로지를 그래픽 형식으로 대역폭 정책 서버 로그 파일에서 로드 하 고 확인 합니다.

- CAC 네트워크 토폴로지를 디스크의 XML 형식으로 저장 하 고 저장 합니다.

- CAC 네트워크 토폴로지 다이어그램을 JPG 또는 BMP 형식으로 저장 하 고 저장 합니다.

- CAC 네트워크 토폴로지 구성 데이터를 확인 합니다.

- 트리 보기 스타일로 CAC 네트워크 토폴로지를 봅니다.

- CAC 네트워크 토폴로지 링크에 대 한 사용자 지정 커넥터 (예: 사이트 간, 지역 간 및 사이트 간 링크)를 정의 합니다.

- CAC 네트워크 토폴로지 사이트 정보, 지역 정보, 프로 비전 된 대역폭 정책 및 네트워크 링크 보기

### <a name="purpose"></a>용도

그래픽 인터페이스에서 엔터프라이즈 CAC 네트워크 토폴로지 링크를 봅니다.

### <a name="examples"></a>예제

 다음 그림에 표시 된 대로 비즈니스용 skype 서버 **2015 배포에서 cac 네트워크 토폴로지를 로드 하 고 확인**합니다.: 비즈니스용 skype 서버 2015 관리자는 다음 그림과 같이 **네트워크 구성 다운로드** 옵션을 사용 하 여 비즈니스용 skype 서버 2015 컴퓨터에서 cac 네트워크 토폴로지 구성을 로드 하 고 확인할 수 있습니다. 이 도구는 비즈니스용 Skype 서버 2015 구성 저장소에 연결 되지 않은 컴퓨터에 배포할 때 이러한 구성을 다운로드 하거나 볼 수 없습니다.

![네트워크 구성을 다운로드 합니다.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 **그래픽 형식으로 대역폭 정책 서버 로그 파일에서 CAC 네트워크 토폴로지를 로드 하 고 확인 합니다.** 비즈니스용 skype 서버 2015 대역폭 정책 서버는 CAC 네트워크 토폴로지를 비즈니스용 Skype 서버 2015 파일 공유 위치에 있는 로깅 메커니즘의 일부로 저장 합니다. 비즈니스용 Skype 서버 2015 관리자는 아래와 같이 **네트워크 구성 열기** 옵션을 사용 하 여 그래픽 형식으로 이러한 파일을 볼 수 있습니다.

![대역폭 정책 서버 로그 파일 열기](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

디스크의 XML 형식으로 CAC 네트워크 토폴로지 저장 및 저장: 비즈니스용 Skype 서버 2015 관리자는 아래와 같이 **네트워크 구성 복사본 저장** 옵션을 사용 하 여 cac 네트워크 토폴로지 구성 파일을 xml 형식으로 저장할 수 있습니다. 저장 된 구성 파일은 그래픽 보기를 위해 오프 라인으로 사용할 수 있습니다.

![네트워크 구성을 XML 파일로 저장](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

JPG 또는 BMP 형식으로 CAC 네트워크 토폴로지 다이어그램 저장 및 저장: 비즈니스용 Skype 서버 2015 관리자는 아래와 같이 **네트워크 구성 다이어그램을 그림으로 저장** 옵션을 사용 하 여 CAC 네트워크 토폴로지 구성을 그래픽 형식 (JPG 및 BMP 파일 형식)으로 저장할 수 있습니다.

![네트워크 구성을 그림으로 저장](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <strong>CAC 네트워크 토폴로지 구성 데이터 보기:</strong> 비즈니스용 Skype 서버 2015 관리자는 아래와 같이 네트워크 구성 데이터 보기 옵션을 사용 하 여 네트워크 지역, 네트워크 사이트, 대역폭 프로필 및 사이트 서브넷 IP 주소와 같은 관련 네트워크 구성 데이터를 텍스트 형식으로 볼 수 있습니다.

![네트워크 구성 데이터 보기](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 **트리 보기 스타일로 CAC 네트워크 토폴로지 보기:** 비즈니스용 Skype 서버 2015 관리자는 아래와 같이 도구 창의 왼쪽에 있는 제어판을 사용 하 여 관련 네트워크 구성 데이터를 그래픽 트리 보기 스타일로 볼 수 있습니다.

![트리 뷰에서 네트워크 구성 데이터 보기](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 **CAC 네트워크 토폴로지 링크에 대 한 사용자 지정 커넥터 (예: 사이트 간, 지역 간 및 사이트 간 링크)를 정의 합니다.** 비즈니스용 Skype 서버 2015 관리자는 아래와 같이 설정 옵션을 사용 하 여 CAC 네트워크 구성 WAN 링크에 대 한 사용자 지정 그래픽 커넥터를 정의할 수 있습니다. 이렇게 하면 네트워크 구성에서 프로 비전 되는 다양 한 유형의 네트워크 링크를 구분 하는 데 도움이 됩니다.

![도구](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 **CAC 네트워크 토폴로지 사이트 정보, 지역 정보 및 프로 비전 된 대역폭 정책 보기:** 비즈니스용 Skype 서버 2015 관리자는 아래 표시 된 옵션을 사용 하 여 관련 CAC 네트워크 지역 정보, 사이트 정보 및 CAC 대역폭 프로 비전 정보를 볼 수 있습니다. 예를 들어 네트워크 지역 또는 네트워크 사이트 개체에서 **정보** 를 클릭 합니다.

![네트워크에 대 한 사용자 지정 커넥터 정의](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a>요약

이 도구는 해당 배포에 대 한 CAC 네트워크 토폴로지를 그래픽 형식으로 보려는 비즈니스용 Skype 서버 2015 관리자에 게 유용한 리소스가 될 수 있습니다.

## <a name="response-group-agent-live"></a>응답 그룹 에이전트 라이브
<a name="RGAL"> </a>

에이전트에서는 응답 그룹 응용 프로그램을 사용 하 여 기본 제공 웹 서비스를 통해 유용한 실시간 정보에 액세스할 수 있습니다. 아쉽게도이 데이터에 대 한 그래픽 보기는 응용 프로그램 외부에서 사용할 수 없습니다. 응답 그룹 에이전트 라이브 리소스 키트 도구는이 정보에 액세스할 수 있는 간단 하 고 시각적 방법을 제공 하 여이 문제를 해결 하며, 다른 에이전트와 같은 실시간 비즈니스용 Skype 통신 소프트웨어 정보를 사용 하 여 향상 되었습니다.

### <a name="description"></a>설명

응답 그룹 에이전트 라이브는 응답 그룹 에이전트에 로그인 및 로그 아웃 기능과 일부 실시간 정보 (예: 그룹 구성원 자격 및 현재 통화 수)를 제공 하는 Windows 응용 프로그램입니다. 비즈니스용 Skype에서 액세스할 수 있는 향상 된 버전의 에이전트 그룹 페이지를 의미 합니다.

### <a name="purpose"></a>용도

응답 그룹 응용 프로그램은 수신 전화를 큐에 대기 시키고 에이전트 그룹에 라우팅합니다. 서비스에 대 한 호출을 결정 하기 위해, 에이전트는 사용 가능한 다른 에이전트 및 각 큐에서 대기 중인 호출 수와 같은 에이전트 그룹에 대 한 실시간 정보에 액세스할 수 있습니다. 처음에 응답 그룹 서비스를 통해서만 액세스할 수 있는이 정보는 그룹 에이전트 라이브에 대 한 직관적인 방식으로 사용 가능 합니다.

#### <a name="features"></a>기능

응답 그룹 에이전트 라이브 도구는 응답 그룹 서비스와 비즈니스용 Skype 서버 2015 SDK를 기반으로 작성 되었습니다. 응답 그룹 에이전트는 응답 그룹 서비스에서 사용할 수 있는 정보 및 기능 (예: 그룹 구성원, 다른 에이전트의 현재 상태 및 대기 통화 수)을 제공 합니다.

아래 그림에서는 응답 그룹 에이전트 라이브의 주요 인터페이스를 보여 줍니다.

![응답 그룹 에이전트 라이브 도구입니다.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

응답 그룹 에이전트 라이브의 에이전트에는 다음과 같은 세 가지 주요 기능을 사용할 수 있습니다.

- **로그인/출력:** 에이전트 그룹 페이지 (비즈니스용 Skype 서버 2015에서 액세스할 수 있음)와 반대로, 응답 그룹 에이전트를 사용 하는 경우, 한 번에 에이전트 에서만 로그인 하거나 모든 에이전트 그룹을 제거할 수 있습니다. 이 응용 프로그램은 에이전트가 로그인 하거나 로그 아웃할 수 있는 세 가지 빠른 방법을 제공 합니다.

  - 응용 프로그램 내에서 로그인/출력 (녹색 및 빨강) 단추를 클릭 합니다.

  - 시스템 트레이 아이콘을 마우스 오른쪽 단추로 클릭 하 고 로그인 또는 로그 아웃을 선택 합니다.

  - 구성 가능한 바로 가기 키 사용

- **그룹 구성원 자격:** 에이전트 그룹을 선택 하면 응답 그룹 에이전트 Live에 오른쪽 창에서이 그룹의 에이전트 목록을 표시 합니다. 이 응용 프로그램과 동일한 컴퓨터에서 비즈니스용 Skype 서버 2015이 실행 되 고 있는 경우 응답 그룹 에이전트에 현재 상태 정보와 연락처 카드를 표시 합니다. 상담원은 IM을 보내거나 여기에서 다른 에이전트를 직접 호출할 수 있습니다.

- **실시간 통계:** 응답 그룹 에이전트 라이브에서는 모든 에이전트 그룹에 대해 실시간 통계를 제공 합니다. 업데이트 빈도가 1 분입니다. 응답 그룹에서 전화를 받은 경우 현재 대기 중인 통화 수를 사용 하 여 그룹 이름 옆에 시각적 표시기가 추가 됩니다. 그룹 위에 포인터를 일시 중지 하면 가장 오래 된 대기 시간이 표시 됩니다.

### <a name="requirements"></a>요구 사항

응답 그룹 에이전트를 사용 하려면 .NET Framework 4.0이 필요 합니다. 또한 현재 상태 및 대화 상대 카드 기능을 활용 하기 위해 비즈니스용 Skype를 로컬로 설치 하 고 실행 해야 합니다.

#### <a name="configuration"></a>구성

응용 프로그램의 옵션 대화 상자를 사용 하 여 개별 기본 설정에 응답 그룹 에이전트 Live를 사용자 지정할 수 있습니다. 또한 관리자는 RGAgentLive 파일의 defaultHostAddress 속성을 직접 편집 하 여 기본 호스트 주소를 정의할 수 있습니다.

아래 그림에서는 상담원이 호스트 주소 및 바로 가기 키를 구성 하는 데 사용할 수 있는 옵션 대화 상자를 보여 줍니다. 주 인터페이스의 오른쪽 위에 있는 옵션 단추를 클릭 하 여이 대화 상자에 액세스할 수 있습니다.

![응답 그룹 에이전트 라이브 옵션 대화 상자](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

응답 그룹 에이전트 라이브 구성에서는 다음과 같은 세 가지 다른 설정을 사용자 지정할 수 있습니다.

- 호스트 주소:이는 일반적으로 에이전트의 홈 풀에 속하는 웹 풀 FQDN입니다. 정확한 응답 그룹 서비스 주소는 호스트 뒤에 적절 한 경로를 추가 하 여이 정보를 바탕으로 백그라운드에서 자동으로 파생 됩니다.

- 바로 가기: 로그인/출력에 대 한 정확한 바로 가기를 사용자 지정할 수 있습니다. 두 바로 가기에는 모두 "Windows 로고" 키 (하나 이상의 키 추가)가 포함 되어야 한다는 제한이 있습니다.

- Windows에서 시작: 응용 프로그램이 Windows에서 자동으로 시작 되도록 구성할 수 있습니다.

### <a name="examples"></a>예제

아래 그림에서는 오른쪽 창에서 연락처를 마우스 오른쪽 단추로 클릭 하 여 다른 에이전트로 IM을 호출 하거나 보내는 방법을 보여 줍니다.

![통화 만들기 또는 메신저 대화 보내기](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

아래 그림에서는 응답 그룹 에이전트 라이브에 큐의 현재 통화 수와 이러한 모든 수신 전화 간의 대기 시간이 가장 긴 지를 보여 줍니다.

![큐 정보 보기](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a>요약

Fast sign-on 및 로그 아웃, 그룹 구성원 자격 및 기본 실시간 통계는 응답 그룹 서비스의 응용 프로그램 외부 에서만 사용할 수 있는 흥미로운 응답 그룹 에이전트 기능입니다. 응답 그룹 에이전트 라이브 리소스 키트 도구를 사용 하 여 비즈니스용 Skype 서버 2015 관리자는 Windows 응용 프로그램에 에이전트를 제공 하 여 사용자가 더 빠르고 그래픽 방식으로 작업을 수행할 수 있도록 합니다.

## <a name="sefautil"></a>SEFAUtil
<a name="SEFAUtil"> </a>

SEFAUtil (보조 확장 기능 정품 인증)은 비즈니스용 Skype 서버 2015 통신 소프트웨어 관리자 및 지원 센터 에이전트에서 위임-링, 착신 전환, 동시 전화 벨 울림을 구성할 수 있도록 하는 명령줄 도구입니다. 비즈니스용 Skype 서버 2015 사용자를 대신 하 여 팀 호출 설정 및 그룹 통화 픽업을 사용 합니다. 또한이 도구를 사용 하면 관리자가 특정 사용자에 대해 게시 된 통화 라우팅 설정을 쿼리할 수 있습니다. SEFAUtil 도구를 사용 하면 관리자가 사용자를 대신 하 여 착신 전환 또는 동시 신호음 울림을 사용 하거나 사용 하지 않도록 설정할 수 있습니다. 관리자는 대상 (SIP URI 형식)을 지정 하거나 사용자가 이미 게시 한 대상을 사용할 수 있습니다. 또한 관리자는이 도구를 사용 하 여 사용자 대신 대리인 또는 팀 호출 그룹 구성원을 추가 하거나 제거할 수 있습니다. 이 도구는 Microsoft 통합 커뮤니케이션 관리 API (지 수) 3.0를 기반으로 작성 되었으며 관리자가 SEFAUtil에 대 한 중앙 관리 저장소에 트러스트 된 응용 프로그램을 만들어야 합니다.

SEFAUtil (보조 확장 기능 활성화) 비즈니스용 Skype 서버 2015 관리자 및 지원 센터 에이전트에서 Skype를 대신 하 여 위임-링, 착신 전환, 동시 신호음, 팀 호출 설정 및 그룹 통화 픽업을 구성할 수 있도록 합니다. Business Server 2015 사용자에 게 적합 합니다. 또한 관리자는이 도구를 사용 하 여 특정 사용자에 대해 게시 된 통화 라우팅 설정을 쿼리할 수 있습니다.

### <a name="description"></a>설명

현재 버전의 SEFAUtil는 명령줄 도구에 불과합니다. 지원 그래픽 사용자 인터페이스가 없습니다. 이 도구는 Microsoft 통합 커뮤니케이션 관리 API (c) 3.0를 기반으로 합니다. 관리자 및 헬프데스크 에이전트는이 도구의 기능을 사용 하 여 다음 작업을 수행할 수 있습니다.

- 사용자에 대 한 모든 통화 라우팅 설정 보기 (통화 전달, 위임, 동시 신호음, 팀 통화 및 그룹 통화 픽업 포함)

- 사용/사용 안 함/수정 통화 전달 설정 (대상 및 응답 없음 타이머 포함)

- 사용/사용 안 함/수정 전화 착신 전환 즉시 구성

- 위임 설정 사용/사용 안 함/수정

- 팀 호출 그룹 설정 사용/사용 안 함/수정

    > [!NOTE]
    > 비즈니스용 Skype 서버 2015 SEFAUtil 도구에 새로 만들기

- 동시 벨 울림 설정 사용/사용 안 함/수정 (대상 포함)

    > [!NOTE]
    > 비즈니스용 Skype 서버 2015 SEFAUtil 도구에 새로 만들기

- 그룹 통화 픽업 설정 사용/사용 안 함/수정

    > [!CAUTION]
    > 비즈니스용 Skype 서버 2015 SEFAUtil 도구에 새로 만들기

이 도구에는 다음과 같은 제한 사항이 있습니다.

- 비즈니스용 Skype 서버 풀에 있는 사용자에 대해서만 지원 됩니다.

- 여러 사용자에 대 한 통화 라우팅 설정의 대량 편집은 지원 되지 않습니다.

### <a name="output"></a>출력

이 도구의 현재 버전은 명령 프롬프트 창에만 출력을 제공 합니다. 자세한 내용은이 문서 뒷부분의 예 섹션을 참조 하십시오.

### <a name="purpose"></a>용도

이 도구를 사용할 수 있는 몇 가지 주요 시나리오는 다음과 같습니다.

- Bob은 임원 이며 비즈니스용 Skype 서버 전화 통신으로 옮겨졌습니다. 기존 PBX 시스템에 대 한 위임이 있습니다. 비즈니스용 Skype 서버 2015로 이동 하는 동안 관리자는 Bob의 라우팅을 구성 하 여 기존 위임 구성을 반영할 수 있습니다.

- Alice가 모바일 고객 중 한 명에 게 중요 한 전화를 거는 것을 인식 하 고 있습니다. 하지만 호텔에는 해당 컴퓨터에 대 한 액세스 권한이 없습니다. 지원 센터에 전화를 걸고 사용자에 게 회사 번호로 건 모든 통화를 휴대폰으로 전달 하도록 요청 합니다. 지원 센터 직원이 자신을 대신해 서 구성을 수행할 수 있습니다.

- Joe의 직장 번호에 대 한 통화는 직장에서 언제 든 지 모바일 음성 메일로 이동 합니다. 그러나 대부분의 다른 위치에서 제대로 작동 하는 것 처럼 보입니다. 헬프데스크 기술자는 Joe의 라우팅 구성을 볼 수 있으며, Joe가 휴대폰으로 구성 된 동시 연결을 감지 합니다. 기술자는 귀하의 사무실에 있는 모바일 기능에 대 한 정보를 제공 하 고 동시 벨 울림 규칙으로 인해 네트워크에 문제가 있을 경우 Joe의 모바일 음성 메일로 전화가 이동 하도록 하는 것을 확인할 수 있습니다.

- Mike는 Contoso의 새로운 직원 이며, 모든 구성원이 비즈니스용 Skype 서버 2015을 사용할 수 있도록 설정 된 경우 팀 호출에 대해 모든 구성원을 구성 하는 새 팀에 참여 하 게 됩니다. 또한 관리자가 Mike를 팀의 각 구성원에 대 한 팀 호출 그룹 구성원으로 추가 합니다.

- Contoso의 인적 자원 부서에 있는 고객 서비스 연습은 최초 통화 이후 모든 발신자에 게 개인 서비스를 제공 하는 것입니다. 부서의 모든 구성원이 서로 가까이에 있을 것 이므로 모든 전화가 팀과 동시에 모든 전화를 사용 하는 것은 팀에 게 매우 방해가 됩니다. 팀 구성원을 중단시 키 지 않고 최상의 서비스를 제공 하기 위해 비즈니스용 Skype 서버 2015 관리자는 그룹 통화 픽업 기능을 활용 합니다. 관리자가 모든 부서 구성원을 pickup 그룹에 추가 하 고 해당 부서에 pickup 그룹 번호를 전달 합니다. Samantha가 책상에 없으면 Joe가 전화를 걸고 사용자의 책상 으로부터 통화에 응답 하도록 진행 합니다.

### <a name="requirements"></a>요구 사항

SEFAUtil 도구는 트러스트 된 응용 프로그램 풀의 일부인 컴퓨터 에서만 실행할 수 있습니다. 해당 컴퓨터에 c s p 3.0이 설치 되어 있어야 합니다. 이 도구를 실행 하려면 SEFAUtil 응용 프로그램 ID가 있는 새 신뢰할 수 있는 응용 프로그램을 해당 풀에 만들어야 합니다.

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a>SEFAUtil 도구에 대 한 신뢰할 수 있는 응용 프로그램 새로 만들기

1. SEFAUTil 도구는 트러스트 된 응용 프로그램 풀에 속하는 컴퓨터 에서만 실행할 수 있습니다. 필요한 경우 다음 cmdlet을 사용 하 여 비즈니스용 Skype 서버 관리 셸을 통해 풀을 새 신뢰할 수 있는 응용 프로그램 풀로 추가 하는 작업을 수행할 수 있습니다.

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > SEFAUtil 도구를 실행 하는 데 사용 되는 모든 컴퓨터에는 c s p 3.0이 설치 되어 있어야 합니다.

2. 신뢰할 수 있는 응용 프로그램은 SEFAUtil 도구에 대 한 토폴로지에서 정의 해야 합니다. SEFAUtil를 새 신뢰할 수 있는 응용 프로그램으로 정의 하려면 비즈니스용 Skype 서버 관리 셸을 사용 하 여 다음 cmdlet을 실행 합니다.

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > 필요한 경우 다른 포트를 사용할 수 있습니다.
    
    > [!NOTE]
    > 풀 FQDN: SEFAUtil 응용 프로그램을 호스팅할 서버 또는 풀의 FQDN (대개 비즈니스용 Skype 프런트 엔드 서버 > 또는 풀)입니다.
    > 풀 등록자 FQDN:이 응용 프로그램 풀과 연결 된 비즈니스용 Skype 프런트 엔드 서버 또는 풀의 FQDN입니다.
    > 풀 사이트:이 풀이 홈으로 설정 된 사이트의 사이트 ID입니다.

3. 토폴로지 변경 내용을 사용 하도록 설정 해야 합니다. 다음 cmdlet을 실행 하 여 비즈니스용 Skype 서버 관리 셸을 통해 토폴로지 변경을 사용 하도록 설정할 수 있습니다.

   ```powershell
   Enable-CsToplogy
   ```

4. 필요한 경우 SEFAUtil 도구를 실행 하는 데 사용 되는 서버에 비즈니스용 Skype 서버 2015 리소스 키트 도구를 설치 합니다 (서버가 신뢰할 수 있는 응용 프로그램 풀의 일부가 되어야 함).

5. SEFAUtil가 제대로 실행 되 고 있는지 확인 합니다. 이렇게 하려면 관리자 권한으로 windows 명령 프롬프트에서 도구를 실행 하 여 배포에 포함 된 사용자의 착신 전환 설정을 표시 합니다. 기본적으로 도구는 ". ..\Program Files\Skype for Business Server 2015 \ Reskit"에 배치 됩니다. 사용자의 착신 전환 설정을 표시 하려면 다음 명령을 사용 합니다.

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    사용자의 착신 전환 설정이 표시 됩니다.

#### <a name="group-call-pickup"></a>그룹 통화 픽업

그룹 통화 지원 기능을 사용 하려면 비즈니스용 Skype 서버 2015의 추가 구성이 필요 합니다. 사용자에 게 pickup 그룹을 할당 하기 전에이 기능의 계획 및 배포 단계에 대 한 Call Pickup 제품 설명서 그룹을 참조 하십시오.

### <a name="examples"></a>예제

#### <a name="display-current-call-handling-settings"></a>현재 통화 처리 설정 표시

다음 명령은 사용자에 대 한 통화 처리를 표시 합니다.  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> 다음은 **/server** 스위치를 사용 하 여 연결할 비즈니스용 Skype 서버를 지정 하는 예제입니다.

 **출력**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a>착신 전환 대상/응답 없음 설정

이 예에서는 착신 전환/아니요 응답 대상과 링 지연을 설정 합니다. 여기서/server 스위치는 제공 되지 않습니다. SEFAUtil는 비즈니스용 Skype 서버 2015의 자동 검색을 시도 합니다.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+14255550126@contoso.com;user=phone
```

 **출력**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a>착신 전환 즉시 사용

다음은 다른 사용자에 게 즉시 착신 전환 기능을 사용 하도록 설정 하는 예제입니다.

```console
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 **출력**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a>착신 전환 즉시 사용 안 함

이 예에서는 착신 전환을 즉시 사용 하지 않도록 설정 합니다.

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com /disablefwdimmediate
```

 **출력**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>사용자를 대리인으로 추가 하 고 대리인에 게 동시 신호음 울림 설정

다음은 사용자를 대리인으로 추가 하 고 대리인의 동시 신호음을 설정 하는 예제입니다.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 **출력**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a>위임의 동시 벨 울림 규칙 변경

이 예에서는 이전 예제에서 설정한 동시 신호음 규칙을 지연 된 링 규칙으로 변경 합니다.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 **출력**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a>대리인 제거

이 예에서는 대리인을 제거 합니다.

> [!NOTE]
> 마지막 대리인이 제거 되 면 대리인의 벨 울림은 자동으로 사용 하지 않도록 설정 됩니다.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 **출력**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>대리인을 추가 하 고 대리인에 게 착신 전환 규칙을 설정 합니다.

다음은 대리인을 추가 하 고 착신 전환을 대리인 규칙에 설정 하는 예제입니다.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 **출력**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>동시 신호음 사용 및 대상 번호 설정

이 예에서는 동시 신호음을 사용 하도록 설정 하 고 동시 벨 울림 대상 번호를 설정 합니다.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> 이미 동시에 신호음을 사용 하도록 설정 된 사용자의 동시 울림 대상 번호를 변경 하려면/enablesimulring 스위치를 사용 하 여 명령을 유지 하 고, 그렇지 않으면 대상 번호가 변경 되지 않습니다.

 **출력**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a>동시 신호음 사용 안 함

이 예에서는 동시 신호음을 사용 하지 않도록 설정 합니다.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 **출력**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>팀 통화를 위해 팀 구성원을 추가 하 고 팀 호출 구성원 그룹에 게 동시 신호음 울림 설정

이 예에서는 사용자의 팀 호출 그룹에 팀 구성원을 추가 하 고 팀 호출 그룹에 동시에 신호음을 울리는 기능을 사용 하도록 설정 합니다.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> 사용자의 팀 호출 그룹에 구성원을 추가 하면 자동으로 사용자의 동시 연결 해제 settigs가 팀 호출 그룹을 simulring으로 전환 됩니다.

 **출력**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a>팀 호출 그룹에서 구성원 제거

이 예에서는 사용자의 팀 호출 그룹 팀 구성원을 제거 합니다.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> 제거할 구성원이 팀 호출 그룹의 유일한 구성원이 면 팀 호출 그룹에 동시에 연결 하는 것이 자동으로 사용 하지 않도록 설정 됩니다.

 **출력**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a>지연 된 링을 팀 호출 그룹으로 설정

이 예에서는 지연 된 링을 팀 통화 그룹 시간 설정으로 변경 합니다.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 **출력**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a>팀 호출 사용

이 예에서는 지정 된 사용자에 대해 팀 호출을 사용 하도록 설정 합니다.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> 사용자의 팀 호출 그룹에 구성원이 없으면 팀 호출을 사용 하도록 설정 되지 않습니다.

 **출력**

#### <a name="disable-team-call"></a>팀 호출 사용 안 함

이 예에서는 지정 된 사용자에 대해 팀 호출을 사용 하지 않도록 설정 합니다.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 **출력**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>그룹 통화 픽업 사용 및 사용자에 게 Pickup 그룹 할당

이 예에서는 사용자에 게 pickup 그룹을 할당 하 고 그룹 통화 픽업을 사용 하도록 설정 합니다.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 **출력**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a>그룹 통화 픽업 사용 안 함

이 예에서는 지정 된 사용자에 대해 그룹 통화 픽업를 사용 하지 않도록 설정 합니다.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> 사용자에 대해 그룹 통화 픽업를 사용 하지 않도록 설정 하면 사용자에 게 할당 된 그룹 번호가 보존 되지 않습니다. 이후에 해당 사용자에 대 한 그룹 통화 픽업을 다시 사용 하도록 설정 하려면/enablegrouppickup 스위치를 사용 하 여 그룹 번호를 다시 할당 해야 합니다.

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a>Sysprep.inf
<a name="SYSPrep"> </a>

### <a name="description"></a>설명

Sysprep.inf는 Windows Server 2008 운영 체제 시스템에 다음 비즈니스용 Skype 서버 2015 필수 구성 요소를 설치 하는 Windows PowerShell 스크립트입니다.

- Microsoft .Net Framework 4.5

- Microsoft SQL Server Express

- Windows Powershell 버전 3.0

- Visual 2010 재배포 가능 패키지

- 인터넷 정보 서버 업데이트

- Windows Identity Foundation

- 비즈니스용 Skype 서버 2015 코어 파일

  스크립트 이름은 Microsoft Windows 운영 체제에 대 한 시스템 준비 도구와 비슷하지만 서로 다릅니다. 이 스크립트는 비즈니스용 Skype 서버 2015에 대 한 필수 필수 구성 요소만 설치 합니다. 이러한 필수 구성 요소를 설치한 후에는 Windows SYSPrep 도구를 사용 하 여 서버의 이미지를 만들 수 있습니다.

### <a name="requirements"></a>요구 사항

Sysprep.inf 스크립트를 실행 하기 전에 필수 구성 요소 파일을 Windows Server 2008 운영 체제 컴퓨터의 로컬 폴더 (예: **D:\setup)** 에 복사 해야 합니다. 이 폴더에는 비즈니스용 Skype 서버 2015 파일 (특히 **setup.exe** )의 복사본도 포함 해야 합니다. 필수 구성 요소 파일은 다음 위치에서 다운로드할 수 있습니다.


| **충족**                                | **위치**                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| Microsoft .Net Framework 4.5  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| Microsoft SQL Server Express 2008 R2  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| Windows Powershell 버전 3.0  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| Visual 2010 재배포 가능 패키지  <br/>          | <https://www.microsoft.com/download/details.aspx?id=5555>  <br/>  |
| 인터넷 정보 서버 업데이트  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| Windows Identity Foundation  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| 비즈니스용 Skype 서버 2015 Setup.exe  <br/> | 비즈니스용 Skype 서버 2015 미디어에서 복사  <br/>                   |

### <a name="parameter"></a>매개 변수

**-Setupfolder** 매개 변수는 필수 구성 요소 파일의 디렉터리 위치를 인수로 사용 합니다.

### <a name="examples"></a>예제

Sysprep.inf 스크립트를 실행 하 고 비즈니스용 Skype 서버 2015 필수 구성 요소를 설치 하려면 관리자 권한 명령 프롬프트에서 다음 명령을 실행 합니다.

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a>할당 되지 않은 번호 알림 마이그레이션
<a name="UNAM"> </a>

지정 되지 않은 번호 알림 마이그레이션 도구를 사용 하면 비즈니스용 Skype 서버 2015 관리자가 알림 응용 프로그램에서 제공 하는 할당 되지 않은 번호 구성을 원본 비즈니스용 Skype 서버 또는 풀에서 다음으로 이동할 수 있습니다. 대상 비즈니스용 Skype 서버 또는 풀입니다.

### <a name="description"></a>설명

할당 되지 않은 번호 알림 마이그레이션 도구는 원본 서버 또는 풀의 알림 응용 프로그램에서 제공 하는 할당 되지 않은 번호 구성을 다른 서버나 풀로 이동 하는 Windows PowerShell 스크립트입니다.

할당 되지 않은 번호 알림 마이그레이션 스크립트를 실행 하면 다음 작업이 수행 됩니다.

1. 원본 서버 또는 풀에 호스트 된 알림 응용 프로그램의 할당 되지 않은 번호 알림에 사용 되는 모든 오디오 파일을 대상 서버 또는 풀의 파일 저장소로 이동 합니다.

    > [!NOTE]
    > 오디오 파일은 대상 풀로 복사 된 후 원본 풀에서 제거 됩니다.

2. 원본 서버 또는 풀에서 호스트 되는 알림 응용 프로그램에 대해 구성 된 모든 할당 되지 않은 번호 알림을 대상 서버 또는 풀로 이동 합니다.

3. 원본 서버 또는 풀에서 호스트 되는 알림 응용 프로그램에서 지 원하는 모든 할당 되지 않은 번호 범위를 대상 서버 또는 풀에 다시 할당 합니다.

스크립트를 성공적으로 실행 한 후에는 원본 서버 또는 풀에서 호스트 되는 알림 응용 프로그램에 의해 처리 된 모든 할당 되지 않은 번호 범위가 대상 서버 또는 풀에서 동일한 구성으로 처리 됩니다.

### <a name="output"></a>출력

**CsAnnouncementConfiguration** 스크립트는 비즈니스용 Skype 서버 관리 셸 창에서 마이그레이션 작업의 성공 또는 실패를 실행 하는 것을 나타냅니다.

작업 실행이 오류로 인해 중단 되는 경우 대상으로 성공적으로 이동 된 할당 되지 않은 번호 범위는 작업 폼의 대상에 유지 되 고 마이그레이션될 할당 되지 않은 나머지 번호 범위는에 남아 있게 됩니다. 원본 뿐만 아니라 운영 폼에도 해당 합니다. 나머지 구성을 완전히 마이그레이션하려면 오류를 해결 한 후 스크립트를 다시 실행 합니다.

### <a name="purpose"></a>용도

할당 되지 않은 번호 알림 마이그레이션 스크립트는 다음과 같은 세 가지 시나리오에서 사용할 수 있습니다.

- **새 버전의 비즈니스용 Skype 서버에 대 한 구성 설정 마이그레이션:** Contoso는 비즈니스용 Skype 서버 2015로 마이그레이션하는 중 이며, 마이그레이션 프로세스의 일부로 서, 비즈니스용 Skype 서버 관리자가 알림 응용 프로그램에서 서비스를 제공 하는 할당 되지 않은 번호 구성을 Lync Server 2013 배포에서 새 비즈니스용 Skype 서버 2015 배포로 이동 하려고 합니다. 구성 설정을 이동 하기 위해 비즈니스용 Skype 서버 관리자는 할당 되지 않은 번호 알림 마이그레이션 도구를 사용 합니다.

- **비즈니스용 Skype 서버 2015에서 Lync server 2013로의 배포 롤백:** 예기치 않은 요인으로 인해 Contoso는 마이그레이션을 새로운 비즈니스용 Skype 서버 2015 배포로 롤백해야 합니다. 서비스 중단을 최소화 하기 위해 비즈니스용 Skype 서버 관리자는 할당 되지 않은 번호 알림 마이그레이션 도구를 사용 하 여 비즈니스용 Skype 서버 2015 배포의 구성을 Lync Server 2013 배포로 롤백합니다.

- **배포 간 데이터 이동:** Contoso는 한 풀의 모든 서버를 새 서버로 교체 하는 프로세스를 진행 중입니다. 이러한 전략은 새로운 비즈니스용 Skype 서버 2015 풀을 배포 하 고, 이전의 모든 데이터를 새 풀로 이동한 다음, 이전 풀을 사용 중지 하는 것입니다. 새 풀이 배포 되 면 할당 되지 않은 번호 알림 마이그레이션 도구를 사용 하 여 구성을 이전 풀에서 새 그룹으로 이동 합니다.

#### <a name="requirements"></a>요구 사항

도구를 성공적으로 실행 하려면 다음과 같은 주요 요구 사항을 충족 해야 합니다.

1. 비즈니스용 Skype 서버 관리 셸이 설치 된 컴퓨터에서 스크립트를 실행 해야 합니다.

2. 알림 응용 프로그램을 원본 및 대상 비즈니스용 Skype 서버 또는 풀에 배포 해야 합니다.

#### <a name="move-csannouncementconfiguration-script"></a>CsAnnouncementConfiguration 스크립트

CsAnnouncementConfiguration 스크립트를 사용 하려면 아래 표에 설명 된 매개 변수가 두 가지입니다.

![CsAnnouncementConfiguration 매개 변수입니다.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a>예제

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a>지정 되지 않은 번호 알림 구성을 Lync Server 2013 Pool에서 비즈니스용 Skype 서버 2015 풀로 이동

이 예에서는 원본 풀 (Lync Server 2013)에서 지정 되지 않은 번호 알림을 대상 풀 (비즈니스용 Skype 서버 2015)으로 이동 합니다.

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a>할당 되지 않은 번호 알림 구성을 비즈니스용 Skype 서버 2015 풀에서 Lync Server 2013 풀로 이동

이 예에서는 원본 풀 (비즈니스용 Skype 서버 2015)의 지정 되지 않은 번호 알림을 대상 풀 (Lync Server 2013)로 이동 합니다.

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a>웹 회의 데이터
<a name="WebConfData"> </a>

웹 회의 데이터 도구를 사용 하면 비즈니스용 Skype 서버 2015 통신 소프트웨어 관리자가 이끌이의 웹 회의와 관련 된 데이터를 보다 강력 하 게 제어할 수 있습니다. 시나리오에는 타임 스탬프 조건을 기준으로 특정 사용자의 모임 데이터를 삭제 하는 기능이 포함 되어 있습니다.

### <a name="description"></a>설명

이 도구를 사용 하면 관리자가 다음 작업을 수행할 수 있습니다.

1. 단일 사용자와 연결 된 모든 웹 회의 데이터를 찾습니다.

2. 단일 사용자와 연결 된 모든 웹 회의 데이터를 삭제 합니다.

3. 특정 날짜 보다 오래 된 단일 사용자와 연결 된 모든 웹 회의 데이터를 삭제 합니다.

4. 사용자가 풀 간에 이동할 때 단일 사용자와 연결 된 모든 웹 회의 데이터를 이동 합니다.

    > [!NOTE]
    > Lync Server 2010에 대 한 리소스 키트 도구는 단일 사용자와 연결 된 모든 웹 회의 데이터를 풀 간에 이동할 때 지원 합니다. 이 기능은 이제 **MoveConferenceData** 매개 변수로 인해이 도구에서 더 이상 사용 되지 않습니다. 이 매개 변수에 대 한 자세한 내용은 [csuser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) 을 참조 하십시오.

이 도구는 비활성 상태인 모임에 대 한 모임 데이터만 삭제 합니다. 활성 모임 (또는 세션의 모임)은 삭제할 수 없습니다.

이 도구는 대상 사용자와 같은 풀에 있는 컴퓨터에서 실행 해야 합니다. 이 도구를 사용 하 여 해당 모임 콘텐츠 데이터를 관리 하는 사용자는 동일한 사용자 풀에 있어야 합니다.

### <a name="output"></a>출력

이 도구는 각 작업의 결과를 출력 합니다.

- 쿼리가 수행 되 면이 도구는 해당 사용자가 이끌이 인 모든 비활성 모임 데이터 폴더의 목록을 출력 합니다.

- Delete를 수행 하는 경우이 도구는 해당 데이터가 삭제 될 모든 모임 데이터 폴더의 목록을 출력 합니다.

### <a name="requirements"></a>요구 사항

이 도구는 이끌이를 현재 홈에 있는 동일한 풀에서 실행 해야 합니다.

이 도구는 콘텐츠 파일 저장소에 대 한 액세스 권한으로 관리자 권한을 사용 하 여 실행 해야 합니다.

### <a name="examples"></a>예제

다음 표에서는 예제에 사용 된 매개 변수에 대해 설명 합니다.

![웹 회의 데이터 도구 매개 변수](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

위 예제에서는 쿼리 명령이 작동 하는 방식을 보여 줍니다. 이러한 명령의 출력은이 도구의 영향을 받게 되는 모든 모임 콘텐츠 폴더의 목록입니다.

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

위의 예제는 delete 명령의 예입니다. 삭제 명령을 실행 하면 해당 사용자의 모든 비활성 모임 폴더가 제거 됩니다.

### <a name="summary"></a>요약

이 도구는 전화 회의 데이터를 보다 세부적으로 제어 해야 하는 관리자에 게 유용한 리소스가 될 수 있습니다.



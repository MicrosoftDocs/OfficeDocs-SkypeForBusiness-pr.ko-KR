---
title: Lync Server 2013 Resource Kit 도구 설명서
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Resource Kit Tools Documentation
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945604(v=OCS.15)
ms:contentKeyID: 51541429
ms.date: 02/02/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60c2260f5729c45455596f0ab2477f7a190ef520
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509225"
---
# <a name="lync-server-2013-resource-kit-tools-documentation"></a>Lync Server 2013 Resource Kit 도구 설명서

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-01-09_

이 항목에서는 각 도구의 용도와 사용 예를 포함 하 여 Lync Server 2013 Resource Kit에 포함 되는 도구에 대해 설명 합니다. Lync Server 2013, Resource Kit 도구를 통해 Lync Server 2013를 배포 및 관리 하는 IT 관리자가 일상적인 작업을 보다 쉽게 수행할 수 있습니다. 예를 들어 **웹 회의 데이터** 도구를 사용 하 여 온라인 모임 중에 사용자가 업로드 한 데이터를 쉽게 제어할 수 있습니다. **SEFAUtil** 도구를 사용 하 여 사용자에 대 한 착신 전환 및 응답을 설정할 수 있습니다. IT 관리자는 이러한 도구를 사용 하 여 Lync Server 2013을 보다 효율적으로 관리할 수 있도록 권장 합니다.

<div>

## <a name="installation-of-the-resource-kit-tools"></a>리소스 키트 도구 설치

Lync Server 2013, 리소스 키트 도구를 설치 하려면 **OCSReskit.msi**를 다운로드 합니다. 리소스 키트 도구 설치 관리자는의 다운로드 센터에서 다운로드할 수 있습니다 [https://go.microsoft.com/fwlink/p/?LinkID=330429](https://go.microsoft.com/fwlink/p/?linkid=330429) .

단순 설치를 수행 하려면 **OCSResKit.msi** 를 실행 합니다. .Msi는 다음 경로에 있는 모든 도구를 설치 합니다: **% Program Files% \\ Microsoft Lync Server 2013 \\ ResKit**. 자체 포함 된 실행 파일은이 폴더에 있습니다. 파일을 포함 하는 도구는 자체 하위 폴더에 있습니다.

</div>

<div>

## <a name="supported-environments"></a>지원 되는 환경

최적의 성능을 위해서는 lync server 2013, Resource Kit 도구를 동일한 환경 및 Lync Server 2013에 필요한 사양과 동일 하 게 설치 해야 합니다.

</div>

<div>

## <a name="resource-kit-tools-overview"></a>리소스 키트 도구 개요

다음 목록에서는 Lync Server 2013 Resource Kit에서 제공 되는 도구에 대해 설명 합니다. 요구 사항 및 사용 예를 비롯 한 각 도구에 대 한 설명은 다음 섹션에서 다룹니다.

  - ABSConfig

  - 대역폭 정책 서비스 모니터

  - 대역폭 사용률 분석기

  - 통화 Parkometer

  - CleanupStorageServiceData

  - Dbanalyze.exe

  - ImportStorageServiceData

  - Lcssync.dll

  - LookupUserConsole

  - MsTurnPing

  - 네트워크 구성 뷰어

  - 응답 그룹 에이전트 라이브

  - SEFAUtil

  - SYSPrep.ps1

  - 할당 되지 않은 번호 알림 마이그레이션

  - 웹 회의 데이터

</div>

<div>

## <a name="absconfig"></a>ABSConfig

ABSConfig (주소록 서비스 구성 도구)는 관리자가 Lync Server 2013에서 주소록 서비스 구성을 사용자 지정 하는 데 도움이 되는 관리 도구입니다. 또한이 도구를 사용 하면 Lync Server 2013 관리자가 기본 주소록 서비스 설정을 복원할 수 있습니다.

<div>

## <a name="description"></a>설명

ABSConfig는 관리자가 주소록 서비스와 관련 된 Active Directory 도메인 서비스 특성을 구성할 수 있도록 하는 그래픽 사용자 인터페이스 응용 프로그램입니다.

도구에 대 한 기본 시나리오는 다음과 같습니다.

  - 관리자가 Active Directory 도메인 서비스의 특성을 Lync Server 2013의 특성에 매핑할 수 있도록 합니다.

  - 관리자가 주소록 서비스 파일에 포함 하거나 제외할 Active Directory 도메인 서비스 특성을 지정할 수 있도록 하려면

  - 관리자가 기본 주소록 서비스 설정을 복원 하도록 설정 합니다.

ABSConfig 도구는 absConfig.exe 파일을 사용 하 여 시작할 수 있습니다. 도구를 열면 **특성 구성** 탭이 열립니다. 이 테이블에는 Active Directory 도메인 서비스 특성을 Lync Server 2013의 특성 필드에 매핑하고, 특정 특성 필터를 기준으로 주소록 서비스 파일에 포함 하거나 제외할 사용자를 지정 하는 옵션이 있습니다. 또한 주소록 파일에 포함할 전화 번호의 값을 사용자 지정 하는 옵션도 있습니다. 관리자는 **기본값 복원** 옵션을 사용 하 여 주소록 서비스 설정을 기본값으로 복원할 수 있습니다.

</div>

<div>

## <a name="changes-from-lync-server-2010"></a>Lync Server 2010의 변경 내용

Lync Server 2013 ABS 구성 도구에서 특성에 대해 "사용" 확인란을 선택 취소 하 여 특성 (행)을 제거할 수 있습니다. 이는 Lync Server 2010에서 행을 삭제 하는 것과 같은 기능을 합니다.

<div>


> [!NOTE]  
> 사용 확인란은 오른쪽 끝 열에 있습니다. 열을 보려면 오른쪽으로 스크롤해야 할 수도 있습니다.



</div>

</div>

<div>

## <a name="output"></a>출력

ABSConfig는 주소록 서비스 구성을 데이터베이스에 저장 합니다.

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a>용도

ABSConfig에서는 Lync Server 2013 주소록 서비스를 빠르고 쉽게 사용자 지정할 수 있는 방법을 제공 합니다.

</div>

<div>

## <a name="requirements"></a>요구 사항

<div>

## <a name="computer"></a>컴퓨터

ABSConfig은 Lync Server 2013이 설치 된 도메인에 가입 된 컴퓨터 에서만 실행할 수 있습니다. Lync Server 2013, Enterprise Edition의 경우 설치 중에 주소록 서비스가 사용 하도록 설정 된 모든 프런트 엔드 서버에서이 도구를 실행할 수 있습니다.

</div>

<div>

## <a name="network"></a>네트워크

컴퓨터가 프런트 엔드 풀 및 백 엔드 데이터베이스에 연결할 수 있어야 합니다.

</div>

<div>

## <a name="software"></a>소프트웨어

ABSConfig 도구를 실행 하려면 먼저 다음 소프트웨어 구성 요소를 설치 해야 합니다.

  - Microsoft Lync Server 2013

</div>

<div>

## <a name="users"></a>사용자

Lync Server 2013 배포를 업데이트 하는 데 필요한 사용 권한이 있는 관리자

</div>

</div>

<div>

## <a name="examples"></a>예

ABSConfig는 명령 프롬프트에 **ABSConfig.exe** 를 입력 하 여 시작할 수 있습니다. 아래에는 ABSConfig 도구 사용자 인터페이스가 나와 있습니다.

![ABSConfig.exe 도구입니다.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "ABSConfig.exe 도구입니다.")

</div>

<div>

## <a name="summary"></a>요약

관리자는 ABSConfig 도구를 사용 하 여 Lync Server 2013 주소록 서비스를 빠르고 간편 하 게 사용자 지정할 수 있습니다.

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a>대역폭 정책 서비스 모니터

대역폭 정책 서비스 모니터 도구는 관리자가 다음 목록을 볼 수 있도록 하기 위한 것입니다.

1.  토폴로지의 모든 구성 된 Lync Server 2013 대역폭 정책 서비스 (인증 및 코어)

2.  각 서비스가 다른 대역폭 정책 서비스와에 지 서버에 대해 수행 하는 연결

3.  네트워크 구성 문서에 구성 된 모든 링크 및 각 대역폭 정책 서비스에서 보고 하는 실시간 대역폭 사용

<div>

## <a name="description"></a>설명

대역폭 정책 서비스 모니터 도구는 GUI 기반 응용 프로그램으로 구현 됩니다. 관리자는 PDPMonUI.exe를 실행 하 여 도구를 시작 합니다.

이 도구는 시작 될 때 토폴로지의 대역폭 정책 서비스 목록을 검색 합니다. 초기 업데이트가 완료 되 면 창 왼쪽의 창에는 자신이 속한 클러스터 별로 그룹화 된 서비스 목록이 채워집니다.

관리자가 특정 대역폭 정책 서비스를 선택 하면 오른쪽의 창에 해당 특정 서비스에 대 한 정보가 표시 됩니다. 또한이 창에는 정보를 표시 하는 두 개의 기본 탭이 있습니다.

<div>

## <a name="machine-info-tab"></a>컴퓨터 정보 탭

**컴퓨터 정보** 탭에는 선택한 대역폭 정책 서비스의 세부 정보 및 선택한 대역폭 정책 서비스에 의해 다른 서비스에 대 한 모든 연결의 목록과 상태가 표시 됩니다.

</div>

<div>

## <a name="topology-info-tab"></a>토폴로지 정보 탭

**토폴로지 정보** 탭에는 네트워크 구성 설정에 구성 되어 있는 모든 링크의 목록이 표시 됩니다. 각 링크에 대해 오디오 및 비디오 대역폭 용량이 표시 됩니다. 또한 현재 사용 되는 대역폭이 Kbps 및 용량에 대 한 백분율로 표시 됩니다. 이 도구는 색 구분을 사용 하 여 용량과 근접 한 사용률을 갖는 링크를 강조 표시 하므로 관리자가 이러한 링크를 빠르게 분리할 수 있습니다.

<div>


> [!NOTE]  
> 대역폭 정책 서비스 모니터 도구에서 구성 된 대역폭 정책 서비스에 연결할 때 오류가 발생 하면 <STRONG>컴퓨터 정보</STRONG> 및 <STRONG>토폴로지 정보</STRONG> 탭의 정보가 채워지지 않습니다. 그러나이 도구는 처음에는 연결할 수 있지만 이후에는 서비스에 대 한 연결이 끊어질 수 있습니다. 이러한 경우 관리자에 게 오래 된 정보가 표시 될 수 있습니다. 관리자가 특정 대역폭 정책 서비스에 대해 데이터를 마지막으로 업데이트 한 날짜를 볼 수 있도록 허용 하는 각 탭에 <STRONG>마지막으로 업데이트</STRONG> 된 타임 스탬프가 있습니다.



</div>

</div>

</div>

<div>

## <a name="output"></a>출력

명령줄 출력은 없습니다. 프로그램 출력은 기본 GUI (그래픽 사용자 인터페이스) 내에 포함 됩니다.

</div>

<div>

## <a name="purpose"></a>용도

대역폭 정책 서비스 모니터 도구의 목적은 관리자가 토폴로지에 정의 된 각 대역폭 정책 서비스의 상태를 볼 수 있도록 하는 것입니다. 또한 관리자는 네트워크 구성 문서에 정의 된 모든 링크에 대 한 실시간 대역폭 사용을 볼 수 있습니다.

</div>

<div>

## <a name="requirements"></a>요구 사항

Lync Server 토폴로지의 일부인 컴퓨터에서 대역폭 정책 서비스 모니터 도구를 실행 해야 합니다.

</div>

<div>

## <a name="summary"></a>요약

대역폭 정책 서비스 모니터 도구는 토폴로지의 모든 대역폭 정책 서비스의 상태를 조사할 수 있도록 관리자에 게 유용한 리소스 이며, 더 중요 한 이유는 네트워크 구성 설정에 정의 된 링크에 대 한 실시간 대역폭 사용률을 얻을 수 있다는 것입니다.

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a>대역폭 사용률 분석기

대역폭 사용률 분석기는 엔터프라이즈 네트워크의 WAN 링크에서 UC 끝점에 의해 다양 한 대역폭 소비 보기에 대 한 보고서를 작성 하는 도구입니다. 이러한 보고서를 사용 하 여 현재 대역폭 소비 패턴을 이해 하 고 대역폭 용량 계획에 도움을 받을 수 있습니다.

<div>

## <a name="description"></a>설명

대역폭 사용률 분석기는 GUI 기반 응용 프로그램으로 구현 됩니다. 이 도구는 네트워크를 통한 오디오 사용률에 대 한 보고서를 생성 하 고 용량 계획에 도움이 됩니다. 또한 다양 한 링크에 할당 된 대역폭 용량을 반복 합니다.

</div>

<div>

## <a name="output"></a>출력

대역폭 사용률 분석기는 시스템에 구성 되어 있는 모든 WAN 링크에 대 한 대역폭 용량 및 오디오 사용률을 그래픽으로 플롯 합니다.

</div>

<div>

## <a name="purpose"></a>용도

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

<div>

## <a name="applications"></a>응용 프로그램

대역폭 사용률 분석기에는 다음과 같은 두 가지 응용 프로그램 (도구)이 있습니다.

  - **WanLinkLogCollector.exe**     이 도구를 사용 하면 사용자가 필요한 정보를 입력할 수 있습니다.

  - **BandwidthUtilizationAnalyzer.xlsm**    Microsoft Excel 스프레드시트 소프트웨어 보고서는 WanLinkLogCollector.exe에 의해 자동으로 실행 됩니다. 이 응용 프로그램을 통해 사용자는이 문서 뒷부분에 나와 있는 것 처럼 보고서에 필터를 적용할 수 있습니다.

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a>대역폭 사용률 분석기 사용 단계

대역폭 사용률 분석기를 사용 하는 경우 두 가지 단계가 있습니다.

  - WanLinkLogCollector.exe를 사용 하 여 수행 되는 로그 수집

  - BandwidthUtilizationAnalyzer.xlsm을 사용 하 여 수행 하는 보고서 사용자 지정

<div>


> [!IMPORTANT]  
> 최종 사용자가 수동으로 m BandwidthUtilizationAnalyzer.xls를 시작 하지 않는 것이 좋습니다.



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a>대역폭 사용률 분석기 시작

명령 프롬프트 또는 Windows 탐색기를 사용 하 여 WanLinkLogCollector.exe을 시작 합니다.

**WanLinkLogCollector.exe사용 **

WanLinkLogCollector.exe를 사용 하는 세 가지 단계는 다음과 같습니다.

1.  **시간 표시 막대 기록**     보고서를 생성 해야 하는 시간 표시 막대를 제공 합니다.

2.  **파일 디렉터리 지정**     파일 위치 정보 제공

3.  **로그 수집 및 보고서 뷰어 실행**    보고서를 생성 하는 명령을 실행 합니다.

<div>

## <a name="step-1---log-the-timeline"></a>1 단계-시간 표시 막대 기록

시간 표시줄 로깅을 사용 하면 도구 사용자가 아래 그림에 나와 있는 것 처럼 다음을 지정할 수 있습니다.

1.  **시작 날짜** 보고서를 생성할 시간 표시 막대의 시작 날짜입니다. 예를 들어, 2010 년 8 월 1 일

2.  **종료 날짜** 보고서를 생성할 시간 표시 막대의 종료 날짜 이며, 예를 들어, 2010 년 9 월 30 일을 예로 들 있습니다.
    
    ![대역폭 사용률 A의 시작 및 종료 날짜](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "대역폭 사용률 A의 시작 및 종료 날짜")  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a>2 단계-파일 디렉터리 지정

표시 된 대로 사용자가 다음 파일 디렉터리를 지정할 수 있습니다.

  - **서버 로그 파일 위치** 대역폭 정책 서버 로그가 저장 되는 폴더 위치입니다. 이는 일반적으로 \<fileserver\> \\ \<choice of FE\> \\ appserverfiles \\ PDP에 있습니다.

  - **임시 파일 저장 위치** 보고서를 생성 하는 동안 중간 파일이 저장 되는 임시 파일 위치입니다.

![대역폭 사용률의 파일 디렉터리](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "대역폭 사용률의 파일 디렉터리")

<div>


> [!NOTE]  
> 서버 로그 및 임시 파일 저장소 폴더에 대 한 충분 한 파일 액세스 권한이 도구 사용자에 게 제공 되는지 확인 합니다.



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>3 단계-로그를 수집 하 고 보고서 뷰어를 시작 합니다.

로그를 수집 하 고 보고서 뷰어를 시작 하려면 아래 표시 된 대로 **실행** 을 클릭 합니다. 이 단계에서는 필요한 데이터를 수집 합니다.

![대역폭 사용률 Utilization에서 데이터 수집](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "대역폭 사용률 Utilization에서 데이터 수집")

입력 유효성 검사가 성공적으로 완료 되 면 아래 표시 된 메시지가 표시 됩니다.

![Utili 대역폭에서 수집 된 알림을 기록 합니다.](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Utili 대역폭에서 수집 된 알림을 기록 합니다.")

**확인**을 클릭합니다. BandwidthUtilizationAnalyzer.xlsm이 자동으로 시작 됩니다. 메시지 상자의 지침을 따릅니다. 자세한 내용은 다음 섹션에서 **BandwidthUtilizationAnalyzer.xlsm 사용** 을 참조 하십시오.

</div>

<div>


**BandwidthUtilizationAnalyzer.xlsm 사용**

1.  BandwidthUtilizationAnalyzer.xlsm이 자동으로 시작 되 면 아래 표시 된 대로 **새로 고침** 을 클릭 합니다.
    
    ![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")

2.  파일 폴더가 열리면 아래와 같이 메시지 상자에 지정 된 위치에서 consolidated.csv를 선택 합니다. 또한 **C: \\ Temp**로 위치를 표시 합니다.
    
    ![BandwidthUtilizationAnalyzer에서 폴더 열기](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "BandwidthUtilizationAnalyzer에서 폴더 열기")

3.  **가져오기**를 클릭합니다.

4.  그래픽 플롯이 자동으로 생성 됩니다. 배경 작업 포인터가 사라지면 서 사용할 수 있습니다.
    
    ![보고서 보기에 필터를 적용 합니다.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "보고서 보기에 필터를 적용 합니다.")

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a>보고서 보기에 필터 적용

아래에 표시 된 것 처럼 보고서 보기에 적용할 수 있는 필터는 다음과 같이 설명 됩니다.

![보고서 보기에 필터를 적용 합니다.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "보고서 보기에 필터를 적용 합니다.")

1.  **이름** WAN 링크로 필터링 (그래프 오른쪽에 필터가 있습니다.) 접두사는 다음 링크 형식을 나타냅니다. 세로 (파란색) 상자를 표시 합니다.
    
      - **S 사이트** 네트워크 사이트에서 네트워크 지역으로의 WAN 연결
    
      - **사이트 간** 두 네트워크 사이트 간의 WAN 링크
    
      - **R 지역 간** 두 네트워크 지역 간의 WAN 링크

2.  **제한 초과** 대역폭 사용량이 대역폭 용량 보다 많은 WAN 링크로 필터링

3.  **중요 수준** 대역폭 사용률이 대역폭 용량 보다 90% 이상에 도달 했을 때의 WAN 링크로 필터링

4.  **미달 사용** 대역폭 사용률이 대역폭 용량의 25% 미만인 WAN 링크로 필터링

5.  **연결 유형** 다음 WAN 링크 유형으로 필터링:
    
      - **네트워크 사이트** 유형
    
      - **사이트 간** 유형
    
      - **지역 간 링크** 형식

6.  **지역** 네트워크 지역별로 필터링

다음 그림에서는 앞에서 설명한 필터를 보여 줍니다.

**이름을**기준으로 필터링 합니다. 그래프에 표시 해야 하는 링크 목록을 선택 합니다.

![BandwidthUtilizationAnalyzer에서 이름을 기준으로 필터링 합니다.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "BandwidthUtilizationAnalyzer에서 이름을 기준으로 필터링 합니다.")

**제한을 초과**하 여 필터링 합니다. **True** 를 선택 하 여 필터를 적용 합니다.

![제한을 초과한 필터링](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "제한을 초과한 필터링")

**중요 수준**으로 필터링 합니다. **True** 를 선택 하 여 필터를 적용 합니다.

![중요 수준별로 필터링](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "중요 수준별로 필터링")

**과소**사용으로 필터링 합니다. **True** 를 선택 하 여 필터를 적용 합니다.

![과소 사용을 기준으로 필터링](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "과소 사용을 기준으로 필터링")

**링크 형식**으로 필터링 합니다. 표시 해야 하는 유형을 선택 합니다.

![링크 형식별 필터링](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "링크 형식별 필터링")

**지역별로**필터링 링크를 표시 해야 하는 지역 목록을 선택 합니다.

![지역별 필터링](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "지역별 필터링")

</div>

</div>

</div>

<div>

## <a name="requirements"></a>요구 사항

  - .NET Framework 3.5

  - Microsoft Excel 2010 또는 Excel 2007

</div>

<div>

## <a name="summary"></a>요약

대역폭 사용률 분석기는 네트워크를 통해 UC 트래픽에 대 한 오디오 대역폭 사용률을 그리는 데 사용 됩니다. 이 도구는 네트워크의 비디오 대역폭 사용률을 보고 하는 데에도 사용할 수 있습니다.

</div>

</div>

<div>

## <a name="call-parkometer"></a>통화 Parkometer

Call Parkometer는 통화 대기 궤도 데이터베이스에 쉽게 액세스할 수 있게 해 주는 명령줄 응용 프로그램입니다.

<div>

## <a name="description"></a>설명

Call Parkometer는 현재 대기 중인 통화를 추적 하는 도구입니다. 또한 궤도 및 CPS (통화 대기 서버) 사용에 대 한 통계를 수집 합니다. 이 명령줄 도구는 로컬 또는 원격으로 연결 된 컴퓨터에서 CPS 궤도 SQL Server 데이터베이스에 대 한 읽기 및 쓰기 액세스를 모두 제공 합니다.

모든 옵션은 함께 사용할 수 없습니다. 명령줄 구문은 다음과 같습니다.

  - **-o** parameter-이 풀에 대해 구성 된 모든 궤도 범위를 나열 합니다.

  - **– n** 매개 변수-이 풀에서 현재 사용 되는 모든 궤도를 나열 합니다. 표시 되는 정보는 다음과 같습니다.
    
      - Parkee 및 parker의 SIP URI (Uniform Resource Identifier)입니다.
    
      - 통화가 대기 중인 CPS의 호스트 이름입니다.
    
      - 통화가 대기 되었을 때의 타임 스탬프입니다.

  - **– f** 매개 변수-풀에서 현재 사용 가능한 궤도의 수를 나열 합니다.

  - **– r \<n\> ** parameter-마지막으로 대기 된 통화를 나열 합니다 \<n\> . 표시 되는 정보는 다음과 같습니다.
    
      - Parkee SIP URI입니다.
    
      - Parker SIP URI입니다.
    
      - 통화가 파킹 된 CPS의 호스트 이름입니다.
    
      - 통화를 검색 하거나 삭제할 때의 타임 스탬프입니다.

  - **-t \<n\> ** parameter-지정 된 궤도 번호의 임의성을 표시 하기 위해 데이터베이스의 궤도를 예약 하는 테스트입니다.

</div>

<div>

## <a name="output"></a>출력

명령 프롬프트에서 지정한 입력 매개 변수에 따라 Call Parkometer에는 다음과 같은 출력이 표시 됩니다.

  - 이 풀에 대해 구성 된 모든 궤도 범위

  - 현재 대기 중인 통화

  - 사용할 수 있는 사용 가능한 공간 (사용 가능) 궤도

  - 최근 대기 통화

  - Uniform 및 random 궤도 값을 테스트 하기 위해 예약 된 궤도

</div>

<div>

## <a name="purpose"></a>용도

CPS 도구의 용도는 CPS 데이터베이스에 대 한 명령줄 액세스를 제공 하는 것입니다. 관리자는 CPS 사용량을 확인 하 고 풀에 할당 된 궤도 수를 확인할 수 있습니다.

</div>

<div>

## <a name="requirements"></a>요구 사항

CPS를 실행 하는 동일한 컴퓨터에서이 도구를 실행 하는 경우에는 요구 사항이 없습니다. 원격 컴퓨터에서이 도구를 실행 하는 경우 Lync Server 2013에서 사용 하는 SQL Server 데이터베이스를 원격 액세스를 허용 하도록 구성 해야 합니다. 풀의 SQL Server에 연결 하려면 Call Parkometer를 SQL Server 데이터베이스 연결 문자열로 구성 해야 합니다. 이 SQL Server 데이터베이스 연결 문자열은 구성 파일 **parkometer.exe.config**에 정의 되어 있습니다. parkometer.exe가 있는 디렉터리에 배치 해야 합니다. 다음 XML 파일은 parkometer.exe.config의 예입니다. 구성 해야 하는 매개 변수는 사용자 이름 (예: mydomain \\ 관리자), 암호 (예: mypassword) 및 호스트 이름 (예: myserver)입니다.

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

</div>

<div>

## <a name="examples"></a>예

배포한 궤도 범위:-o 매개 변수는 표시 된 것 처럼이 풀에 대해 구성 된 모든 궤도 범위를 나열 합니다.

![통화 Parkometer의 궤도 범위입니다.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "통화 Parkometer의 궤도 범위입니다.")

현재 대기 중인 통화:-n 매개 변수는이 풀에서 현재 사용 되는 모든 궤도를 표시 된 대로 나열 합니다.

![통화 Parkometer에서 현재 대기 중인 통화입니다.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "통화 Parkometer에서 현재 대기 중인 통화입니다.")

Free 궤도의 수: – f 매개 변수는 다음과 같이 풀에 현재 사용 가능한 궤도 수를 나열 합니다.

![통화 Parkometer의 무료 궤도입니다.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "통화 Parkometer의 무료 궤도입니다.")

최근에 대기 된 통화:-r \<n\> 매개 변수는 표시 된 마지막 대기 통화를 나열 합니다. \<n\>

![통화 Parkometer의 최근에 파킹 된 통화입니다.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "통화 Parkometer의 최근에 파킹 된 통화입니다.")

Test 궤도 예약: – t \<n\> 매개 변수 테스트에서는 다음과 같이 데이터베이스의 궤도를 예약 합니다.

![통화 Parkometer에서 궤도 예약을 테스트 합니다.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "통화 Parkometer에서 궤도 예약을 테스트 합니다.")

</div>

<div>

## <a name="summary"></a>요약

Call Parkometer는 통화 대기 서버에 대 한 자세한 정보를 제공 하는 명령줄 도구입니다.

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a>CleanupStorageServiceData

CleanupStorageServiceData resource kit 도구를 사용 하면 Lync Server 저장소 서비스 (LYSS)에서 사용 하는 데이터베이스에서 분리 된 데이터를 삭제할 수 있습니다. 저장소 서비스의 한 가지 기능은 SQL Server 및 Exchange와 같은 다양 한 백 엔드 데이터 저장소 끝점과 Lync Server 간의 통신을 버퍼링 하는 것입니다.

<div>

## <a name="description"></a>설명

높은 가용성을 지원 하기 위해 LYSS는 풀의 여러 프런트 엔드 서버에 있는 데이터의 복사본을 일시적으로 수락 및 저장 하 고, 해당 데이터를 최종 장기 저장소 위치로 배달 한 후에 제거 합니다. 정상적인 작동 중에 발생할 수 있는 비정상적인 상황이 발생 하 고, 서버에 충돌이 있거나, 처리 문제가 발생할 수 있으며, 일부 데이터가 제대로 정리 되지 않을 수 있습니다. 이 데이터는 무해 하지만 제한 된 처리 리소스를 사용 합니다. 대부분의 일반 필수 데이터 유지 관리가 자동화 되지만이 도구를 사용 하면 자동화 된 제거를 수행할 수 없는 경우 이러한 고아 데이터를 안전 하 게 식별 하 고 제거할 수 있습니다. 이 도구의 사용은 관리자가 풀의 로컬 LYSS 데이터베이스에서 불필요 한 데이터를 제거 하도록 요청 하는 SCOM (System Center Operations Manager) 경고가 발생 하는 경우에 표시 됩니다. 경고를 트리거한 프런트 엔드에서 이벤트 로그에 해당 이벤트가 발생 합니다. 이벤트 세부 정보에는 프런트 엔드에 포함 된 분리 된 데이터의 양에 대 한 정보가 포함 되며 해당 데이터가 미리 결정 된 특정 임계값을 초과 하면 발생 합니다.

</div>

<div>

## <a name="requirements"></a>요구 사항

Lync Server 2013, 리소스 키트 도구를 설치 합니다. 이 도구는 Lync Server 및 Lync Server 2013 관리 셸이 설치 된 도메인에 가입 된 컴퓨터에서 실행 됩니다. 이 도구는 관리 셸에서 cmdlet을 사용 하 여 풀의 모든 프런트 엔드 서버를 식별 합니다. 그런 다음 **RtcLocal** 데이터베이스가 설치 된 풀의 컴퓨터에서 도구를 실행 해야 합니다. 이 데이터베이스는 CleanupStorageServiceData 도구에서 Lync Server 라우팅 서비스와 통신 하는 데 필요한 연결 세부 정보를 가져오는 데 사용 됩니다. 마지막으로 도구를 호출 하는 계정 또는 자격 증명에는 출력 로그를 쓸 파일 공유에 대 한 읽기/쓰기 권한이 있어야 합니다. 또한이 도구는 풀이 안정적인 상태임을 따라 달라 집니다. 즉, 모든 프런트 엔드 서버가 가동 되 고 실행 중 이어야 하 고 SQL Server LYNCLOCAL instance 및 LYSS 데이터베이스를 연결할 수 있어야 하며 각 라우팅 그룹에는 1 개의 기본 프런트 엔드 서버와 2 개의 보조 프런트 엔드 서버가 있어야 합니다.

</div>

<div>

## <a name="examples"></a>예

C: \\ 프로그램 파일 \\ Microsoft Lync Server 2013 \\ ResKit \\ StorageService \> ImportStorageServiceData.exe

    Description:
    This tool will remove orphaned data from the Storage Service database
    for a pool. You are required to run this tool on a machine inside the
    pool which has the Lync Server Management Shell installed and has RtcLocal database installed.
    Usage: Default behavior is to clean up orphaned data from the all the 
           Storage Service databases in the current pool.
    Additional Options:
    -Verbose    : Turn verbose output on.
    -LogPath    : The UNC path to which to write the log.
    ------------------------------------------------------------------------------
    Please wait while we initialize...
    Found 4 front end servers
    Replica Instances for LYSS Service
    Address: server2.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server1.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server3.vdomain.com - Primaries: 7 Secondaries: 14
    Primary Total Count = 28, Secondary Total Count = 56
    Finding and removing orphaned data for 28 routing groups
    Removing 1 stale groups from FE server.vdomain.com
    No stale routing groups detected on FE server2.vdomain.com
    No stale routing groups detected on FE server1.vdomain.com
    No stale routing groups detected on FE server3.vdomain.com
    Searching for stale queue items
    Removed 20 stale queue items for routing group 17D5435AE40259F7BBDF1866776386E4
    No stale queue items found for routing group 1975349662315F90B119DACB4F2AE3AD
    No stale queue items found for routing group 1A23E3D58BDB5A458A0B73F34AB7ACBE
    No stale queue items found for routing group 1AC91E3A1029535A80123121989CEADC
    No stale queue items found for routing group 3313935458E35B9B9759E08A15D251E6
    No stale queue items found for routing group 39BB0035B06B5427873FC6099720462A
    No stale queue items found for routing group 40721948E7B55CE893A53E911F76D185
    No stale queue items found for routing group 4501E04EAE4856059346949FF817C220
    No stale queue items found for routing group 4D833C98801F546F8E45E417EE028E2E
    No stale queue items found for routing group 5AD77443AD955A22A876749BE66D5317
    No stale queue items found for routing group 69844A271E6C5633A1F2B46A42287DD6
    No stale queue items found for routing group 69DA3BE407A95C7284EB4B1337718C93
    No stale queue items found for routing group 8437358AB34A5CC8967D5EF39494AB8D
    No stale queue items found for routing group 8ED455B1789655359816E1C5BF4C430F
    No stale queue items found for routing group 904F6C9B8AC951AE8B3C86684D3832E4
    No stale queue items found for routing group 90AAB3AE9A1950E0ADE7809A27021D63
    No stale queue items found for routing group 944F5724C65C5F93900DC1C8C898B102
    No stale queue items found for routing group 9E8A2630250C51769E39F63F0FB552BA
    No stale queue items found for routing group A11E27AE439A582288D4657EDA86B565
    No stale queue items found for routing group A9B10C76E764556FAEA3E47301EDF518
    No stale queue items found for routing group AEA2699E74ED59848ACEA7896699430D
    No stale queue items found for routing group B269961603E75065AFDA4F4F006DA5E4
    No stale queue items found for routing group BB873D9A3DA959DAB2FD743E5AA619F7
    No stale queue items found for routing group BCC6A48FBA2454B79B9EDB276657A404
    No stale queue items found for routing group C8EF4805722B5F6C876EBC0440B420FD
    No stale queue items found for routing group CA38EBDAC4845489ACE208C2240E4056
    No stale queue items found for routing group F5921887DB025C5F908CE42DB7F1AEE8
    No stale queue items found for routing group F9E606A825395422B3BF7A01ECBB7B1F
    Writing log: M:\Dev\Server\ResKit\StorageService\CleanupStorageServiceData.Log_20121009_151040
    Tool has finished execution.  Errors encountered: 0
    C:\Program Files\Microsoft Lync Server 2013\ResKit\StorageService>

</div>

</div>

<div>

## <a name="dbanalyze"></a>Dbanalyze.exe

<div>

## <a name="description"></a>설명

DBAnalyze는 관리자가 Lync Server 2013 데이터베이스에 대 한 분석 보고서를 수집할 수 있도록 하는 명령줄 도구입니다. DBAnalyze에는 진단, 사용자 데이터, 회의, MCUs 및 디스크 조각화 모드가 있습니다.

  - **진단 모드**     테이블 (레코드 수, 조각, 데이터 크기 및 인덱스 크기)에 대 한 정보를 포함 하는 보고서를 만듭니다. 데이터 및 로그 파일 크기, 최근 백업 시간, 마지막 다시 실행 시간은 Microsoft Office Communications Server, 사용자 당 평균 사용 권한, 연락처, 컨테이너, 구독, 게시, 사용자별 끝점, 모든 부적절 한 홈 사용자, 사용자에 게 구성 된 최대 전화 회의 수, 예약 된 전화 회의, 활성 회의 및 데이터베이스 버전 등이 여기에 해당 합니다.
    
    <div>
    

    > [!NOTE]  
    > 진단 모드 실행은 서버 성능에 영향을 줄 수 있습니다.

    
    </div>

  - **사용자 데이터 모드**   지정 된 사용자 또는 해당 사용자가 대화 상대 및 사용 권한 목록에 있는 사용자에 대 한 연락처, 컨테이너, 구독, 게시, 사용 권한 및 연락처 그룹 데이터를 보고 합니다. 또한이 모드는 사용자가 구성 하거나 초대 하는 전화 회의에 대 한 요약 데이터를 보고 합니다.

  - **전화 회의 모드**     회의에 대 한 모든 일정 시간 정보, 초대 대 상자, 회의에 허용 되는 미디어 유형 목록, 활성 참가자 목록 및 각 참가자의 신호 상태를 비롯 하 여 특정 회의에 대 한 자세한 데이터를 보고 합니다.

  - **디코드 모임 ID**    **/Pstnid** 스위치로 지정 되는 공중 전화망 (PSTN) 모임 ID를 디코딩하고 자세한 정보는 백 엔드에 연결 하지 않습니다.

  - **전화 회의**     문제 해결 **/Pstnid** 스위치에 지정 된 PSTN 모임 id를 디코딩하고 ID가 나타내는 전화 회의에 대 한 정보를 표시 합니다.

  - **MCUs 모드**    풀의 각 MCU에 대 한 ID, 미디어 유형, URL, 하트 비트 상태, 회의 부하 및 참가자 부하를 보고 합니다.

  - **디스크 조각화 모드**    모든 디스크의 조각화 상태를 표시 합니다.

이 도구를 사용 하 여 다양 한 문제를 진단 하거나 관리자가 용량 계획을 지원할 수 있습니다. 예를 들어 서버 A에 있는 대부분의 사용자가 자신의 연락처로 서버 B에 있는 사용자를 선택 하는 경우 관리자는 서버 A의 사용자를 서버 B로 이동 하 여 서버 간 트래픽을 줄일 수 있습니다.

</div>

<div>

## <a name="output"></a>출력

이 도구는 Lync Server 2013 데이터베이스에 대 한 미리 정의 된 보고서를 출력 합니다. **경로:** % ProgramFiles% \\ Microsoft Lync Server 2013 \\ Reskit

</div>

<div>

## <a name="purpose"></a>용도

Dbanalyze.exe을 설치 하려면 해당 파일을 로컬 폴더에 복사한 다음 도구를 실행 합니다. 이 도구를 사용 하려면 명령줄에서 다음 명령을 실행 합니다.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` 명령줄 옵션에 대 한 설명은 아래와 같습니다.

![Dbanalyze.exe에 대 한 명령줄 옵션입니다.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Dbanalyze.exe에 대 한 명령줄 옵션입니다.")

</div>

<div>

## <a name="requirements"></a>요구 사항

**컴퓨터** DBAnalyze는 Lync Server 2013이 설치 된 도메인에 가입 된 컴퓨터 에서만 실행할 수 있습니다.

**네트워크** 컴퓨터에서 백 엔드 데이터베이스에 연결할 수 있어야 합니다.

**소프트웨어** DBAnalyze를 실행 하기 전에 Lync Server 2013 소프트웨어 구성 요소를 설치 해야 합니다.

**사용자** 아래 표에는 Lync Server 2013 데이터베이스에 액세스 하는 데 필요한 권한이 있는 관리자가 나와 있습니다.

![Dbanalyze.exe에 대 한 사용 권한 테이블입니다.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Dbanalyze.exe에 대 한 사용 권한 테이블입니다.")

<div>


> [!NOTE]  
> <STRONG>/Preport: 디스크</STRONG> 모드에는 로컬 관리자 계정이 필요 합니다.



</div>

</div>

<div>

## <a name="examples"></a>예

다음은 유효한 Dbanalyze.exe 명령의 예입니다.

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a>요약

DBAnalyzer는 관리자에 게 Lync Server 2013 데이터베이스를 빠르고 쉽게 분석할 수 있도록 합니다.

</div>

</div>

<div>

## <a name="importstorageservicedata"></a>ImportStorageServiceData

ImportStorageServiceData resource kit 도구를 사용 하면 저장소 서비스 (LYSS)에서 플러시된 큐 및 끝점 데이터를 저장소 서비스로 다시 가져올 수 있습니다.

<div>

## <a name="description"></a>설명

저장소 서비스에서 플러시된 데이터는 큐 항목 상태 또는 데이터베이스 크기에 따라 자동 (주기적)이 될 수 있습니다. 이 문제는 풀 장애 조치 (failover) cmdlet 또는 풀 장애 조치 (failover) cmdlet이 호출 하는 StorageServiceFullFlush cmdlet의 수동 호출로 인해 발생 했을 수 있습니다. 프런트 엔드에서 저장소 서비스 (LYSS) 데이터베이스 크기가 일반 수준 위에 있는 경우에는 데이터를 다시 가져올 필요가 없기 때문에이 작업을 수행 하면 더 많은 데이터를 다시 내보낼 수 있습니다. 또한 저장소 서비스 큐 증가를 일으킨 오류에 대 한 영향을 받을 수 있는 모든 문제 (예: Exchange 끝점 오류, 네트워크 문제 또는 기타 문제)를 먼저 해결 해야 합니다.

**시나리오 1:** 풀 장애 조치 (failover) 중에 각 프런트 엔드에서 파일을 저장소 서비스에서 플러시할 수 있습니다. 장애 조치 (failover)가 완료 되 면 도구를 실행 하 여 데이터를 다시 가져와야 합니다.

**시나리오 2:** 데이터를 매일 자동으로 플러시 중이거나 저장소 서비스 데이터베이스에 대 한 응답으로 특정 크기 임계값 (예: 60%, 80%, 90% full)을 초과 하는 경우 자동으로 플러시된 데이터는 관리자가 정기적으로 다시 가져와야 합니다. 위의 상황에서 모니터링 SCOM pack이 배포 되지 않은 경우 저장소 서비스에서 플러시하는 데이터와 관련 된 Lync Server 저장소 서비스에 대 한 이벤트가 있습니다. 이벤트 Id 32075 (전체 플러시 작업을 시작 함), 32076 (전체 플러시 완료), 32082 (유지 관리 수준 플러시 시작), 32083 (, 유지 관리 수준 플러시 완료), 32089 (데이터베이스를 채우는 중에 플러시 발생) 참고 이러한 이벤트 Id는 RTM 릴리스에 해당 합니다. 관리자에 게 이러한 이벤트가 표시 되 면 플러시 된 파일이 있음을 의미 합니다. 이 도구를 사용 하 여이 데이터를 정기적으로 다시 가져와야 합니다 (예: 일주일에 한 번).

온라인 서비스 릴리스의 경우 Lync Server에 대 한 상태 모니터링 SCOM pack이 배포 되는 경우 관리자에 게 플러시된 데이터를 다시 저장소 서비스에 재 가져오도록 요청 하는 새로운 경고가 발생할 수 있습니다. 프런트 엔드 서버의 이벤트 로그에 경고를 트리거한 해당 이벤트가 발생 합니다. 이 이벤트는 플러시된 데이터 파일이 있는 상위 경로에 대 한 설명과, 경고 조건을 충족 하는 파일 수를 제공 합니다. 경고 기준은 특정 상위 경로 아래에 Y 일이 지난 파일 (X 및 Y는 StorageService 내에서 사전 설정 되지만 APPCONFIG 파일을 변경 하 여 재정의할 수 있음)이 포함 되어 있다는 것입니다. 상태 경고를 트리거할 수 있는 이벤트의 두 가지 예는 다음과 같습니다 (상위 경로). 웹 서비스 파일 공유 아래에는 각 프런트 엔드의 로컬 응용 프로그램 데이터 디렉터리인 한 가지 가능성이 있습니다. 예를 들면 c: \\ ProgramData \\ Microsoft \\ Lync Server \\ StorageService). 그러면 관리자가이 reskit 도구를 실행 합니다.

이 도구는 도구를 실행 하는 프런트 엔드에서 데이터를 소유 하지 않는 경우에도 실행 중인 프런트 엔드에서 CPU 및 IO 부하를 증가 시킵니다. 프런트 엔드의 CPU 및 IO 부하가 많지 않은 경우 (예: 사용량이 가장 많은 시간 외에)이 도구를 사용 하는 것이 좋습니다. 그런 다음이 도구는 데이터 파일 하나를 가져오는 데 2 ~ 3 분이 걸릴 수 있습니다. 도구 실행 시간을 추정할 때이 점에 유의 하세요. 도구에서 생성 되는 자세한 로그 파일은 기본적으로 파일 저장소에 표시 됩니다. 로그 파일의 크기가 수십 개이 하 이므로 오류가 보고 되지 않은 경우 삭제 합니다.

![예제 저장소 서버 이벤트 로그 이벤트](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "예제 저장소 서버 이벤트 로그 이벤트")

</div>

<div>

## <a name="requirements"></a>요구 사항

Lync Server 2013, 리소스 키트 도구를 설치 합니다. 이 도구는 Lync Server 및 Lync Server 관리 셸이 설치 된 도메인에 가입 된 컴퓨터에서 실행 됩니다. 이 도구는 관리 셸에서 cmdlet을 사용 하 여 풀의 모든 프런트 엔드 서버를 식별 합니다. 그런 다음 **RtcLocal** 데이터베이스가 설치 된 풀의 컴퓨터에서 도구를 실행 해야 합니다. 이 데이터베이스는 도구에서 풀에 대 한 WEBSERVICE 파일 공유 위치를 검색 하는 데 사용 됩니다. 또한이 도구를 사용 하기 전에 각 프런트 엔드 서버에서 먼저 각 프런트 엔드 서버에서 **enable-psremoting** 를 사용 하 여 Windows PowerShell Remoting을 사용 하도록 설정 해야 하며,이 도구를 실행 하는 컴퓨터도 필요 합니다. 그렇지 않은 경우에는이 도구의 원격 Windows PowerShell 명령이 실패 합니다. 풀에 있는 모든 프런트 엔드 서버를 완료 한 후에는 Windows PowerShell Remoting을 끌 수 있습니다. 마지막으로 도구를 호출 하는 계정 또는 자격 증명에는이 도구를 실행 하는 풀에 대 한 webservice 파일 공유에 대 한 읽기/쓰기 권한이 있어야 합니다. 그렇지 않으면 도구에서 IO 권한 오류가 발생 하지 않습니다.

<div>


> [!NOTE]  
> Windows Server 2012에서는 windows PowerShell Remoting이 기본적으로 사용 하도록 설정 되어 있지만 Windows Server 2008 운영 체제에서는 사용할 수 없습니다.



</div>

</div>

<div>

## <a name="examples"></a>예

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

</div>

</div>

<div>

## <a name="lcssync"></a>Lcssync.dll

LCSSync 도구는 다중 포리스트 환경에서 Lync Server 2013 통신 소프트웨어를 배포 하는 데 도움이 됩니다. 이 도구는 다른 사용자 포리스트에서 사용자 및 그룹을 Active Directory 도메인 서비스 연락처 개체로, Lync Server 2013이 설치 된 중앙 포리스트로 동기화 하는 데 사용 됩니다.

<div>

## <a name="description"></a>설명

LCSSync는 중앙 포리스트에서 동기화 된 Active Directory 도메인 서비스 대화 상대 개체를 사용 하 여 사용자가 Lync Server를 사용할 수 있도록 합니다. Single sign-on을 제공 하려면 기본 사용자 계정을 Lync Server 2013에 대 한 중앙 포리스트의 Active Directory 도메인 서비스 대화 상대 개체에 매핑해야 합니다. 이 도구는 해당 매핑을 수행 하는 데 도움이 됩니다. 이 도구는 Microsoft Identity 통합 서버에서 관리 에이전트를 만들기 위한 템플릿을 제공 합니다.

</div>

<div>

## <a name="summary"></a>요약

LCSSync 도구는 다중 포리스트 환경에서 Lync Server를 배포 하는 데 도움이 됩니다.

</div>

</div>

<div>

## <a name="lookupuserconsole"></a>LookupUserConsole

LookupUserConsole 도구는 특정 사용자에 대 한 내부 Lync Server 라우팅 정보를 표시 합니다. 이 정보는 Microsoft에서 배포 및 라우팅 문제를 진단 하는 데 유용할 수 있습니다.

<div>

## <a name="description"></a>설명

LookupUserConsole.exe를 실행 하면 SIP 주소를 허용 하 고 해당 항목과 관련 된 내부 Lync Server 라우팅 정보를 표시 하려고 하는 명령 프롬프트가 열립니다. **Exit** 를 입력 하 여 LookupUserConsole 도구를 종료 합니다.

</div>

<div>

## <a name="requirements"></a>요구 사항

Lync Server 2013, 리소스 키트 도구를 설치 합니다. 이 도구는 Lync Server가 설치 된 도메인에 가입 된 컴퓨터에서 실행 됩니다.

</div>

<div>

## <a name="examples"></a>예

C: \\ 프로그램 파일 \\ Microsoft Lync Server 2013 \\ ResKit \>LookupUserConsole.exe

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

</div>

</div>

<div>

## <a name="msturnping"></a>MsTurnPing

Microsoft Lync Server 2013 통신 소프트웨어 관리자는 MSTurnPing 도구를 사용 하 여 토폴로지에서 대역폭 정책 서비스를 실행 하는 서버 뿐만 아니라 오디오/비디오에 지 및 오디오/비디오 인증 서비스를 실행 하는 서버의 상태를 확인할 수 있습니다.

<div>

## <a name="description"></a>설명

MSTurnPing 도구를 사용 하면 Lync Server 2013 통신 소프트웨어 관리자가 토폴로지에서 대역폭 정책 서비스를 실행 하는 서버 뿐만 아니라 오디오/비디오에 지 및 오디오/비디오 인증 서비스를 실행 하는 서버의 상태를 확인할 수 있습니다.

이 도구를 사용 하면 관리자가 다음과 같은 테스트를 수행할 수 있습니다.

1.  A/V에 지 서버 테스트:이 도구는 다음을 수행 하 여 토폴로지의 모든 A/V에 지 서버에 대해 테스트를 수행 합니다.
    
      - Lync Server 오디오/비디오 인증 서비스가 시작 되었으며 적절 한 자격 증명을 발급할 수 있는지 확인 합니다.
    
      - Lync Server 오디오/비디오에 지 서비스가 시작 되었는지 확인 하 고 리소스를 외부에 지에 성공적으로 할당할 수 있습니다.

2.  대역폭 정책 서비스 테스트: 도구는 다음을 수행 하 여 토폴로지에서 대역폭 정책 서비스를 실행 하는 모든 서버에 대해 테스트를 수행 합니다.
    
      - Lync Server 대역폭 정책 서비스 (인증)가 시작 되었으며 적절 한 자격 증명을 발급할 수 있는지 확인 합니다.
    
      - Lync Server Core (대역폭 정책 서비스)가 시작 되었으며 대역폭 확인을 정상적으로 수행할 수 있는지 확인 합니다.

토폴로지의 일부인 컴퓨터에서이 도구를 실행 하 고 로컬 저장소를 설치 해야 합니다.

</div>

<div>

## <a name="output"></a>출력

이 도구는 각 작업의 결과를 출력 합니다.

  - **AudioVideoEdgeServer** 테스트를 수행 하는 경우에는 다음과 같은 도구가 출력 됩니다.
    
      - 토폴로지에서 Lync Server 오디오/비디오 인증 서비스를 제공 하는 컴퓨터의 테스트 결과
    
      - 토폴로지에서 Lync Server 오디오/비디오에 지 서비스를 제공 하는 컴퓨터의 테스트 결과

  - **BandwidthPolicyServer** 테스트를 수행 하는 경우에는 다음과 같은 도구가 출력 됩니다.
    
      - 토폴로지에서 Lync Server 대역폭 정책 서비스 (인증)를 제공 하는 컴퓨터의 테스트 결과
    
      - 토폴로지에서 Lync Server Core (대역폭 정책 서비스)를 제공 하는 컴퓨터의 테스트 결과

</div>

<div>

## <a name="requirements"></a>요구 사항

  - 이 도구는 토폴로지에 있고 로컬 저장소가 있는 컴퓨터에서 실행 해야 합니다.

  - 이 도구는 로컬 저장소에 대 한 액세스 권한이 있는 관리자 권한으로 실행 해야 합니다.

</div>

<div>

## <a name="examples"></a>예

다음은 도구 입력의 예입니다.

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a>요약

이 도구는 오디오/비디오 및 대역폭 정책 서비스를 실행 하는 서버의 상태를 확인 하려는 Lync Server 2013 관리자에 게 유용한 리소스 일 수 있습니다.

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a>네트워크 구성 뷰어

Microsoft Lync Server 2013 통신 소프트웨어 관리자는 네트워크 구성 뷰어를 사용 하 여 지정 된 대역폭 용량에 따라 음성 또는 비디오 통화와 같은 실시간 통신 세션을 허용 하도록 프로 비전 된 엔터프라이즈에 대 한 CAC (통화 허용 제어) 네트워크 토폴로지를 볼 수 있습니다. Lync Server 2013 관리자는 Lync Server 2013와 함께 설치 되는 대역폭 정책 서비스에 의해 적용 되는 CAC 정책을 정의 합니다.

<div>

## <a name="description"></a>설명

NetworkConfigurationViewer.exe (Network Configuration Viewer)에서는 관리자가 다음 작업을 수행할 수 있습니다.

  - Lync Server 2013 배포에서 CAC 네트워크 토폴로지를 그래픽 형식으로 로드 하 고 확인 합니다.

  - CAC 네트워크 토폴로지를 그래픽 형식으로 대역폭 정책 서버 로그 파일에서 로드 하 고 확인 합니다.

  - CAC 네트워크 토폴로지를 디스크의 XML 형식으로 저장 하 고 저장 합니다.

  - CAC 네트워크 토폴로지 다이어그램을 JPG 또는 BMP 형식으로 저장 하 고 저장 합니다.

  - CAC 네트워크 토폴로지 구성 데이터를 확인 합니다.

  - 트리 보기 스타일로 CAC 네트워크 토폴로지를 봅니다.

  - CAC 네트워크 토폴로지 링크에 대 한 사용자 지정 커넥터 (예: 사이트 간, 지역 간 및 사이트 간 링크)를 정의 합니다.

  - CAC 네트워크 토폴로지 사이트 정보, 지역 정보, 프로 비전 된 대역폭 정책 및 네트워크 링크 보기

</div>

<div>

## <a name="purpose"></a>용도

그래픽 인터페이스에서 엔터프라이즈 CAC 네트워크 토폴로지 링크를 봅니다.

</div>

<div>

## <a name="examples"></a>예

**다음은 Lync Server 2013 배포에서 CAC 네트워크 토폴로지를 그래픽 형식으로 로드 하 고 확인 하** 는 것입니다. Lync Server 2013 관리자는 아래 그림에 나와 있는 것 처럼 **네트워크 구성 다운로드** 옵션을 사용 하 여 lync server 2013 컴퓨터에서 CAC 네트워크 토폴로지 구성을 로드 하 고 확인할 수 있습니다. 이 도구는 Lync 구성 저장소에 연결 되지 않은 컴퓨터에 배포할 때 이러한 구성을 다운로드 하거나 볼 수 없습니다.

![네트워크 구성을 다운로드 합니다.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "네트워크 구성을 다운로드 합니다.")

**그래픽 형식으로 대역폭 정책 서버 로그 파일에서 CAC 네트워크 토폴로지를 로드 하 고 확인 합니다.** Lync Server 2013 대역폭 정책 서버는 CAC 네트워크 토폴로지를 Lync Server 2013 파일 공유 위치 아래에 있는 로깅 메커니즘의 일부로 저장 합니다. Lync Server 관리자는 아래와 같이 **네트워크 구성 열기** 옵션을 사용 하 여 그래픽 형식으로 이러한 파일을 볼 수 있습니다.

![대역폭 정책 서버 로그 파일 열기](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "대역폭 정책 서버 로그 파일 열기")

CAC 네트워크 토폴로지를 디스크의 XML 형식으로 저장 하 고 저장 합니다. Lync Server 2013 관리자는 아래와 같이 **네트워크 구성 복사본 저장** 옵션을 사용 하 여 cac 네트워크 토폴로지 구성 파일을 xml 형식으로 저장할 수 있습니다. 저장 된 구성 파일은 그래픽 보기를 위해 오프 라인으로 사용할 수 있습니다.

![네트워크 구성을 XML 파일로 저장](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "네트워크 구성을 XML 파일로 저장")

다음에 설명 된 대로 CAC 네트워크 토폴로지 다이어그램을 JPG 또는 BMP 형식으로 저장 및 저장: Lync Server 2013 관리자는 다음과 같이 **네트워크 구성 다이어그램을 그림으로 저장** 옵션을 사용 하 여 cac 네트워크 토폴로지 구성을 그래픽 형식 (JPG 및 BMP 파일 형식)으로 저장할 수 있습니다.

![네트워크 구성을 그림으로 저장](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "네트워크 구성을 그림으로 저장")

**CAC 네트워크 토폴로지 구성 데이터 보기:** Lync Server 2013 관리자는 아래와 같이 네트워크 구성 데이터 보기 옵션을 사용 하 여 네트워크 지역, 네트워크 사이트, 대역폭 프로필 및 사이트 서브넷 IP 주소와 같은 관련 네트워크 구성 데이터를 텍스트 형식으로 볼 수 있습니다.

![네트워크 구성 데이터 보기](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "네트워크 구성 데이터 보기")

**트리 보기 스타일로 CAC 네트워크 토폴로지 보기:** Lync Server 2013 관리자는 아래와 같이 도구 창의 왼쪽에 있는 제어판을 사용 하 여 관련 네트워크 구성 데이터를 그래픽 트리 보기 스타일로 볼 수 있습니다.

![트리 뷰에서 네트워크 구성 데이터 보기](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "트리 뷰에서 네트워크 구성 데이터 보기")

**CAC 네트워크 토폴로지 링크에 대 한 사용자 지정 커넥터 (예: 사이트 간, 지역 간 및 사이트 간 링크)를 정의 합니다.** Lync Server 2013 관리자는 아래와 같이 설정 옵션을 사용 하 여 CAC 네트워크 구성 WAN 링크에 대 한 사용자 지정 그래픽 커넥터를 정의할 수 있습니다. 이렇게 하면 네트워크 구성에서 프로 비전 되는 다양 한 유형의 네트워크 링크를 구분 하는 데 도움이 됩니다.

![CAC 네트워크 토폴로지의 사용자 지정 커넥터 정의](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "CAC 네트워크 토폴로지의 사용자 지정 커넥터 정의")

**CAC 네트워크 토폴로지 사이트 정보, 지역 정보 및 프로 비전 된 대역폭 정책 보기:** Lync Server 2013 관리자는 아래 표시 된 옵션을 사용 하 여 관련 CAC 네트워크 지역 정보, 사이트 정보 및 CAC 대역폭 프로 비전 정보를 볼 수 있습니다. 예를 들어 네트워크 지역 또는 네트워크 사이트 개체에서 **정보** 를 클릭 합니다.

![네트워크에 대 한 사용자 지정 커넥터 정의](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "네트워크에 대 한 사용자 지정 커넥터 정의")

</div>

<div>

## <a name="summary"></a>요약

이 도구는 배포에 대 한 CAC 네트워크 토폴로지를 그래픽 형식으로 보려는 Lync Server 2013 관리자에 게 유용한 리소스 일 수 있습니다.

</div>

</div>

<div>

## <a name="response-group-agent-live"></a>응답 그룹 에이전트 라이브

에이전트에서는 응답 그룹 응용 프로그램을 사용 하 여 기본 제공 웹 서비스를 통해 유용한 실시간 정보에 액세스할 수 있습니다. 아쉽게도이 데이터에 대 한 그래픽 보기는 응용 프로그램 외부에서 사용할 수 없습니다. 응답 그룹 에이전트 라이브 Resource Kit 도구는이 정보에 액세스 하 여 다른 에이전트와 같은 실시간 Microsoft Lync 2013 통신 소프트웨어 정보를 사용 하 여이 문제를 해결 합니다.

<div>

## <a name="description"></a>설명

응답 그룹 에이전트 라이브는 응답 그룹 에이전트에 로그인 및 로그 아웃 기능과 일부 실시간 정보 (예: 그룹 구성원 자격 및 현재 통화 수)를 제공 하는 Windows 응용 프로그램입니다. 이는 Lync 2013에서 액세스할 수 있는 향상 된 버전의 에이전트 그룹 페이지를 의미 합니다.

</div>

<div>

## <a name="purpose"></a>용도

응답 그룹 응용 프로그램은 수신 전화를 큐에 대기 시키고 에이전트 그룹에 라우팅합니다. 서비스에 대 한 호출을 결정 하기 위해, 에이전트는 사용 가능한 다른 에이전트 및 각 큐에서 대기 중인 호출 수와 같은 에이전트 그룹에 대 한 실시간 정보에 액세스할 수 있습니다. 처음에 응답 그룹 서비스를 통해서만 액세스할 수 있는이 정보는 그룹 에이전트 라이브에 대 한 직관적인 방식으로 사용 가능 합니다.

<div>

## <a name="features"></a>기능

응답 그룹 에이전트 라이브 도구는 응답 그룹 서비스 및 Microsoft Lync 2013 SDK를 기반으로 합니다. 응답 그룹 에이전트는 응답 그룹 서비스에서 사용할 수 있는 정보 및 기능 (예: 그룹 구성원, 다른 에이전트의 현재 상태 및 대기 통화 수)을 제공 합니다.

아래 그림에서는 응답 그룹 에이전트 라이브의 주요 인터페이스를 보여 줍니다.

![응답 그룹 에이전트 라이브 도구입니다.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "응답 그룹 에이전트 라이브 도구입니다.")

응답 그룹 에이전트 라이브의 에이전트에는 다음과 같은 세 가지 주요 기능을 사용할 수 있습니다.

  - **로그인/출력:** Lync 2013에서 액세스할 수 있는 에이전트 그룹 페이지와 반대로, 응답 그룹 에이전트를 사용 하는 경우에는 한 번에 에이전트 에서만 로그인 하거나 모든 에이전트 그룹을 제거할 수 있습니다. 이 응용 프로그램은 에이전트가 로그인 하거나 로그 아웃할 수 있는 세 가지 빠른 방법을 제공 합니다.
    
      - 응용 프로그램 내에서 로그인/출력 (녹색 및 빨강) 단추를 클릭 합니다.
    
      - 시스템 트레이 아이콘을 마우스 오른쪽 단추로 클릭 하 고 로그인 또는 로그 아웃을 선택 합니다.
    
      - 구성 가능한 바로 가기 키 사용

  - **그룹 구성원 자격:** 에이전트 그룹을 선택 하면 응답 그룹 에이전트 Live에 오른쪽 창에서이 그룹의 에이전트 목록을 표시 합니다. Lync 2013이이 응용 프로그램과 동일한 컴퓨터에서 실행 되는 경우 현재 상태 정보 및 대화 상대 카드는 응답 그룹 에이전트에 표시 됩니다. 상담원은 IM을 보내거나 여기에서 다른 에이전트를 직접 호출할 수 있습니다.

  - **실시간 통계:** 응답 그룹 에이전트 라이브에서는 모든 에이전트 그룹에 대해 실시간 통계를 제공 합니다. 업데이트 빈도가 1 분입니다. 응답 그룹에서 전화를 받은 경우 현재 대기 중인 통화 수를 사용 하 여 그룹 이름 옆에 시각적 표시기가 추가 됩니다. 그룹 위에 포인터를 일시 중지 하면 가장 오래 된 대기 시간이 표시 됩니다.

</div>

</div>

<div>

## <a name="requirements"></a>요구 사항

응답 그룹 에이전트를 사용 하려면 .NET Framework 4.0이 필요 합니다. 또한 현재 상태 및 대화 상대 카드 기능을 활용 하려면 Lync 2013을 로컬로 설치 하 고 실행 해야 합니다.

<div>

## <a name="configuration"></a>구성

응용 프로그램의 옵션 대화 상자를 사용 하 여 개별 기본 설정에 응답 그룹 에이전트 Live를 사용자 지정할 수 있습니다. 또한 관리자는 RGAgentLive.exe.config 파일의 defaultHostAddress 속성을 직접 편집 하 여 기본 호스트 주소를 정의할 수 있습니다.

아래 그림에서는 상담원이 호스트 주소 및 바로 가기 키를 구성 하는 데 사용할 수 있는 옵션 대화 상자를 보여 줍니다. 주 인터페이스의 오른쪽 위에 있는 옵션 단추를 클릭 하 여이 대화 상자에 액세스할 수 있습니다.

![응답 그룹 에이전트 라이브 옵션 대화 상자](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "응답 그룹 에이전트 라이브 옵션 대화 상자")

응답 그룹 에이전트 라이브 구성에서는 다음과 같은 세 가지 다른 설정을 사용자 지정할 수 있습니다.

  - 호스트 주소:이는 일반적으로 에이전트의 홈 풀에 속하는 웹 풀 FQDN입니다. 정확한 응답 그룹 서비스 주소는 호스트 뒤에 적절 한 경로를 추가 하 여이 정보를 바탕으로 백그라운드에서 자동으로 파생 됩니다.

  - 바로 가기: 로그인/출력에 대 한 정확한 바로 가기를 사용자 지정할 수 있습니다. 두 바로 가기에는 모두 "Windows 로고" 키 (하나 이상의 키 추가)가 포함 되어야 한다는 제한이 있습니다.

  - Windows에서 시작: 응용 프로그램이 Windows에서 자동으로 시작 되도록 구성할 수 있습니다.

</div>

</div>

<div>

## <a name="examples"></a>예

아래 그림에서는 오른쪽 창에서 연락처를 마우스 오른쪽 단추로 클릭 하 여 다른 에이전트로 IM을 호출 하거나 보내는 방법을 보여 줍니다.

![통화 만들기 또는 메신저 대화 보내기](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "통화 만들기 또는 메신저 대화 보내기")

아래 그림에서는 응답 그룹 에이전트 라이브에 큐의 현재 통화 수와 이러한 모든 수신 전화 간의 대기 시간이 가장 긴 지를 보여 줍니다.

![큐 정보 보기](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "큐 정보 보기")

</div>

<div>

## <a name="summary"></a>요약

Fast sign-on 및 로그 아웃, 그룹 구성원 자격 및 기본 실시간 통계는 응답 그룹 서비스의 응용 프로그램 외부 에서만 사용할 수 있는 흥미로운 응답 그룹 에이전트 기능입니다. 응답 그룹 에이전트 라이브 리소스 키트 도구를 사용 하는 경우 Lync 관리자는 사용자가 더 빠르고 그래픽 방식으로 작업을 수행할 수 있도록 하는 Windows 응용 프로그램에 에이전트를 제공할 수 있습니다.

</div>

</div>

<div>

## <a name="sefautil"></a>SEFAUtil

SEFAUtil (보조 확장 기능 활성화)는 Microsoft Lync Server 2013 통신 소프트웨어 관리자 및 헬프데스크 에이전트에서 Lync Server 2013 사용자를 대신 하 여 위임-링, 착신 전환, 동시 전화 신호, 팀 호출 설정 및 그룹 통화 픽업을 구성할 수 있도록 하는 명령줄 도구입니다. 또한이 도구를 사용 하면 관리자가 특정 사용자에 대해 게시 된 통화 라우팅 설정을 쿼리할 수 있습니다. SEFAUtil 도구를 사용 하면 관리자가 사용자를 대신 하 여 착신 전환 또는 동시 신호음 울림을 사용 하거나 사용 하지 않도록 설정할 수 있습니다. 관리자는 대상 (SIP URI 형식)을 지정 하거나 사용자가 이미 게시 한 대상을 사용할 수 있습니다. 또한 관리자는이 도구를 사용 하 여 사용자 대신 대리인 또는 팀 호출 그룹 구성원을 추가 하거나 제거할 수 있습니다. 이 도구는 Microsoft 통합 커뮤니케이션 관리 API (지 수) 3.0를 기반으로 작성 되었으며 관리자가 SEFAUtil에 대 한 중앙 관리 저장소에서 트러스트 된 응용 프로그램을 만들어야 합니다.

SEFAUtil (보조 확장 기능 활성화) Lync server 2013 관리자 및 지원 센터 에이전트가 Lync Server 2013 사용자를 대신 하 여 위임-링, 착신 전환, 동시 신호 울림, 팀 호출 설정 및 그룹 통화 픽업을 구성할 수 있도록 합니다. 또한 관리자는이 도구를 사용 하 여 특정 사용자에 대해 게시 된 통화 라우팅 설정을 쿼리할 수 있습니다.

<div>

## <a name="description"></a>설명

현재 버전의 SEFAUtil는 명령줄 도구에 불과합니다. 지원 그래픽 사용자 인터페이스가 없습니다. 이 도구는 Microsoft 통합 커뮤니케이션 관리 API (c) 3.0를 기반으로 합니다. 관리자 및 헬프데스크 에이전트는이 도구의 기능을 사용 하 여 다음 작업을 수행할 수 있습니다.

  - 사용자에 대 한 모든 통화 라우팅 설정 보기 (통화 전달, 위임, 동시 신호음, 팀 통화 및 그룹 통화 픽업 포함)

  - 사용/사용 안 함/수정 통화 전달 설정 (대상 및 응답 없음 타이머 포함)

  - 사용/사용 안 함/수정 전화 착신 전환 즉시 구성

  - 위임 설정 사용/사용 안 함/수정

  - 팀 호출 그룹 설정 사용/사용 안 함/수정
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 SEFAUtil 도구에 새로 만들기

    
    </div>

  - 동시 벨 울림 설정 사용/사용 안 함/수정 (대상 포함)
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 SEFAUtil 도구에 새로 만들기

    
    </div>

  - 그룹 통화 픽업 설정 사용/사용 안 함/수정
    
    <div>
    

    > [!WARNING]  
    > Lync Server 2013 SEFAUtil 도구에 새로 만들기

    
    </div>

이 도구에는 다음과 같은 제한 사항이 있습니다.

  - Lync Server 풀에 속한 사용자만 지원 됨

  - 여러 사용자에 대 한 통화 라우팅 설정의 대량 편집은 지원 되지 않습니다.

</div>

<div>

## <a name="output"></a>출력

이 도구의 현재 버전은 명령 프롬프트 창에만 출력을 제공 합니다. 자세한 내용은이 문서 뒷부분의 예 섹션을 참조 하십시오.

</div>

<div>

## <a name="purpose"></a>용도

이 도구를 사용할 수 있는 몇 가지 주요 시나리오는 다음과 같습니다.

  - Bob은 임원 이며 Lync Server 전화 통신으로 이동 되었습니다. 기존 PBX 시스템에 대 한 위임이 있습니다. Lync로 이동의 일부로, 관리자는 기존 위임 구성을 반영 하도록 Bob의 라우팅을 구성할 수 있습니다.

  - Alice가 모바일 고객 중 한 명에 게 중요 한 전화를 거는 것을 인식 하 고 있습니다. 하지만 호텔에는 해당 컴퓨터에 대 한 액세스 권한이 없습니다. 지원 센터에 전화를 걸고 사용자에 게 회사 번호로 건 모든 통화를 휴대폰으로 전달 하도록 요청 합니다. 지원 센터 직원이 자신을 대신해 서 구성을 수행할 수 있습니다.

  - Joe의 직장 번호에 대 한 통화는 직장에서 언제 든 지 모바일 음성 메일로 이동 합니다. 그러나 대부분의 다른 위치에서 제대로 작동 하는 것 처럼 보입니다. 헬프데스크 기술자는 Joe의 라우팅 구성을 볼 수 있으며, Joe가 휴대폰으로 구성 된 동시 연결을 감지 합니다. 기술자는 귀하의 사무실에 있는 모바일 기능에 대 한 정보를 제공 하 고 동시 벨 울림 규칙으로 인해 네트워크에 문제가 있을 경우 Joe의 모바일 음성 메일로 전화가 이동 하도록 하는 것을 확인할 수 있습니다.

  - Mike는 Contoso의 새로운 직원이 며, Microsoft Lync에 대해 사용 하도록 설정 된 경우 관리자가 팀 호출에 대해 모든 구성원을 포함 하도록 구성 하는 새 팀에 참여 하 고 있으며, 관리자는 팀의 각 구성원에 대해 Mike를 팀 호출 그룹 구성원으로 추가할 수 있습니다.

  - Contoso의 인적 자원 부서에 있는 고객 서비스 연습은 최초 통화 이후 모든 발신자에 게 개인 서비스를 제공 하는 것입니다. 부서의 모든 구성원이 서로 가까이에 있을 것 이므로 모든 전화가 팀과 동시에 모든 전화를 사용 하는 것은 팀에 게 매우 방해가 됩니다. 팀 구성원을 중단시 키 지 않고 최상의 서비스를 제공 하기 위해 Lync 관리자는 그룹 통화 픽업 기능을 활용 합니다. 관리자가 모든 부서 구성원을 pickup 그룹에 추가 하 고 해당 부서에 pickup 그룹 번호를 전달 합니다. Samantha가 책상에 없으면 Joe가 전화를 걸고 사용자의 책상 으로부터 통화에 응답 하도록 진행 합니다.

</div>

<div>

## <a name="requirements"></a>요구 사항

SEFAUtil 도구는 트러스트 된 응용 프로그램 풀의 일부인 컴퓨터 에서만 실행할 수 있습니다. 해당 컴퓨터에 c s p 3.0이 설치 되어 있어야 합니다. 이 도구를 실행 하려면 SEFAUtil 응용 프로그램 ID가 있는 새 신뢰할 수 있는 응용 프로그램을 해당 풀에 만들어야 합니다.

**SEFAUtil 도구에 대 한 신뢰할 수 있는 응용 프로그램 새로 만들기**

1.  SEFAUTil 도구는 트러스트 된 응용 프로그램 풀에 속하는 컴퓨터 에서만 실행할 수 있습니다. 필요한 경우 다음 cmdlet을 사용 하 여 Lync Server 관리 셸을 통해 풀을 새 신뢰할 수 있는 응용 프로그램 풀로 추가 하는 작업을 수행할 수 있습니다.
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > SEFAUtil 도구를 실행 하는 데 사용 되는 모든 컴퓨터에는 c s p 3.0이 설치 되어 있어야 합니다.

    
    </div>

2.  신뢰할 수 있는 응용 프로그램은 SEFAUtil 도구에 대 한 토폴로지에서 정의 해야 합니다. SEFAUtil를 새 신뢰할 수 있는 응용 프로그램으로 정의 하려면 Lync Server 관리 셸을 사용 하 여 다음 cmdlet을 실행 합니다.
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > 필요한 경우 다른 포트를 사용할 수 있습니다.

    
    </div>

3.  토폴로지 변경 내용을 사용 하도록 설정 해야 합니다. 다음 cmdlet을 실행 하 여 Lync Server 관리 셸을 통해 토폴로지 변경을 사용 하도록 설정할 수 있습니다.
    
        Enable-CsToplogy

4.  필요한 경우 SEFAUtil 도구를 실행 하는 데 사용할 Lync Server 2013 Resource Kit 도구 (서버는 신뢰할 수 있는 응용 프로그램 풀의 일부가 되어야 함)를 설치 합니다.

5.  SEFAUtil가 제대로 실행 되 고 있는지 확인 합니다. 이렇게 하려면 관리자 권한으로 windows 명령 프롬프트에서 도구를 실행 하 여 배포에 포함 된 사용자의 착신 전환 설정을 표시 합니다. 도구는 기본적으로 다음 \\ 위치에 배치 됩니다. 프로그램 파일 \\ Microsoft Lync Server 2013 \\ Reskit ". 사용자의 착신 전환 설정을 표시 하려면 다음 명령을 사용 합니다.
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    사용자의 착신 전환 설정이 표시 됩니다.

<div>

## <a name="group-call-pickup"></a>그룹 통화 받기

그룹 통화 픽업 기능을 사용 하려면 Lync Server의 추가 구성이 필요 합니다. 사용자에 게 pickup 그룹을 할당 하기 전에이 기능의 계획 및 배포 단계에 대 한 Call Pickup 제품 설명서 그룹을 참조 하십시오.

</div>

</div>

<div>

## <a name="examples"></a>예

<div>

## <a name="display-current-call-handling-settings"></a>현재 통화 처리 설정 표시

다음 명령은 사용자에 대 한 통화 처리를 표시 합니다. `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> 다음은 <STRONG>/server</STRONG> 스위치를 사용 하 여 연결할 Lync server를 지정 하는 예제입니다.



</div>

**출력**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a>착신 전환 대상/응답 없음 설정

이 예에서는 착신 전환/아니요 응답 대상과 링 지연을 설정 합니다. 여기서/server 스위치는 제공 되지 않습니다. SEFAUtil에서 Lync Server의 자동 검색을 시도 합니다.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

**출력**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a>착신 전환 즉시 사용

다음은 다른 사용자에 게 즉시 착신 전환 기능을 사용 하도록 설정 하는 예제입니다.

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

**출력**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

</div>

<div>

## <a name="disable-call-forwarding-immediately"></a>착신 전환 즉시 사용 안 함

이 예에서는 착신 전환을 즉시 사용 하지 않도록 설정 합니다.

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

**출력**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>사용자를 대리인으로 추가 하 고 대리인에 게 동시 신호음 울림 설정

다음은 사용자를 대리인으로 추가 하 고 대리인의 동시 신호음을 설정 하는 예제입니다.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

**출력**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a>위임의 동시 벨 울림 규칙 변경

이 예에서는 이전 예제에서 설정한 동시 신호음 규칙을 지연 된 링 규칙으로 변경 합니다.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

**출력**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

</div>

<div>

## <a name="remove-the-delegate"></a>대리인 제거

이 예에서는 대리인을 제거 합니다.

<div>


> [!NOTE]  
> 마지막 대리인이 제거 되 면 대리인의 벨 울림은 자동으로 사용 하지 않도록 설정 됩니다.



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

**출력**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>대리인을 추가 하 고 대리인 규칙에 Call-Forward 설정

다음은 대리인을 추가 하 고 착신 전환을 대리인 규칙에 설정 하는 예제입니다.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

**출력**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>동시 신호음 사용 및 대상 번호 설정

이 예에서는 동시 신호음을 사용 하도록 설정 하 고 동시 벨 울림 대상 번호를 설정 합니다.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> 이미 동시에 신호음을 사용 하도록 설정 된 사용자의 동시 울림 대상 번호를 변경 하려면/enablesimulring 스위치를 사용 하 여 명령을 유지 하 고, 그렇지 않으면 대상 번호가 변경 되지 않습니다.



</div>

**출력**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="disable-simultaneous-ringing"></a>동시 신호음 사용 안 함

이 예에서는 동시 신호음을 사용 하지 않도록 설정 합니다.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

**출력**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>Team-Call에 대 한 팀 구성원을 추가 하 고 Team-Call 구성원 그룹으로 동시 벨 울림 설정

이 예에서는 사용자의 팀 호출 그룹에 팀 구성원을 추가 하 고 팀 호출 그룹에 동시에 신호음을 울리는 기능을 사용 하도록 설정 합니다.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> 사용자의 팀 호출 그룹에 구성원을 추가 하면 자동으로 사용자의 동시 연결 해제 settigs가 팀 호출 그룹을 simulring으로 전환 됩니다.



</div>

**출력**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

</div>

<div>

## <a name="remove-a-member-from-the-team-call-group"></a>Team-Call 그룹에서 구성원을 제거 합니다.

이 예에서는 사용자의 팀 호출 그룹 팀 구성원을 제거 합니다.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

<div>


> [!NOTE]  
> 제거할 구성원이 팀 호출 그룹의 유일한 구성원이 면 팀 호출 그룹에 동시에 연결 하는 것이 자동으로 사용 하지 않도록 설정 됩니다.



</div>

**출력**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a>지연 된 링을 Team-Call 그룹으로 설정

이 예에서는 지연 된 링을 팀 통화 그룹 시간 설정으로 변경 합니다.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

**출력**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

</div>

<div>

## <a name="enable-team-call"></a>Team-Call 사용

이 예에서는 지정 된 사용자에 대해 팀 호출을 사용 하도록 설정 합니다.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

<div>


> [!NOTE]  
> 사용자의 팀 호출 그룹에 구성원이 없으면 팀 호출을 사용 하도록 설정 되지 않습니다.



</div>

**출력**

</div>

<div>

## <a name="disable-team-call"></a>Team-Call 사용 안 함

이 예에서는 지정 된 사용자에 대해 팀 호출을 사용 하지 않도록 설정 합니다.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

**출력**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>그룹 통화 픽업 사용 및 사용자에 게 Pickup 그룹 할당

이 예에서는 사용자에 게 pickup 그룹을 할당 하 고 그룹 통화 픽업을 사용 하도록 설정 합니다.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

**출력**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

</div>

<div>

## <a name="disable-group-call-pickup"></a>그룹 통화 픽업 사용 안 함

이 예에서는 지정 된 사용자에 대해 그룹 통화 픽업를 사용 하지 않도록 설정 합니다.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

<div>


> [!NOTE]  
> 사용자에 대해 그룹 통화 픽업를 사용 하지 않도록 설정 하면 사용자에 게 할당 된 그룹 번호가 보존 되지 않습니다. 이후에 해당 사용자에 대 한 그룹 통화 픽업을 다시 사용 하도록 설정 하려면/enablegrouppickup 스위치를 사용 하 여 그룹 번호를 다시 할당 해야 합니다.



</div>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

</div>

</div>

</div>

<div>

## <a name="sysprepps1"></a>SYSPrep.ps1

<div>

## <a name="description"></a>설명

SYSPrep.ps1는 Windows Server 2008 운영 체제 컴퓨터에 다음 Lync Server 2013 필수 구성 요소를 설치 하는 Windows PowerShell 스크립트입니다.

  - Microsoft .Net Framework 4.5

  - Microsoft SQL Server Express

  - Windows Powershell 버전 3.0

  - Visual 2010 재배포 가능 패키지

  - 인터넷 정보 서버 업데이트

  - Windows Identity Foundation

  - Lync Server 2013 코어 파일

스크립트 이름은 Microsoft Windows 운영 체제에 대 한 시스템 준비 도구와 비슷하지만 서로 다릅니다. 이 스크립트는 Lync Server 2013에 필요한 필수 구성 요소만 설치 합니다. 이러한 필수 구성 요소를 설치한 후에는 Windows SYSPrep 도구를 사용 하 여 서버의 이미지를 만들 수 있습니다.

</div>

<div>

## <a name="requirements"></a>요구 사항

SYSPrep.ps1 스크립트를 실행 하기 전에 먼저 필수 구성 요소 파일을 Windows Server 2008 운영 체제 컴퓨터의 로컬 폴더 (예 **: D; \\ 설치)** 에 복사 해야 합니다. 이 폴더에는 Lync Server 2013 파일의 복사본 (특히Setup.exe)도 포함 해야 합니다 ** .** 필수 구성 요소 파일은 다음 위치에서 다운로드할 수 있습니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>충족</th>
<th>위치</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft .Net Framework 4.5</p></td>
<td><p>https://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p>Microsoft SQL Server Express 2008 R2</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p>Windows Powershell 버전 3.0</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p>Visual 2010 재배포 가능 패키지</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p>인터넷 정보 서버 업데이트</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 Setup.exe</p></td>
<td><p>Lync Server 2013 미디어에서 복사</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="parameter"></a>매개 변수

**– Setupfolder** 매개 변수는 필수 구성 요소 파일의 디렉터리 위치를 인수로 사용 합니다.

</div>

<div>

## <a name="examples"></a>예

SYSPrep.ps1 스크립트를 실행 하 고 Lync Server 2013 필수 구성 요소를 설치 하려면 관리자 권한 명령 프롬프트에서 다음 명령을 실행 합니다.

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a>할당 되지 않은 번호 알림 마이그레이션

지정 되지 않은 번호 알림 마이그레이션 도구를 사용 하면 Lync 관리자가 알림 응용 프로그램에서 제공 하는 할당 되지 않은 번호 구성을 원본 Lync Server 또는 풀에서 대상 Lync Server 또는 풀로 이동할 수 있습니다.

<div>

## <a name="description"></a>설명

할당 되지 않은 번호 알림 마이그레이션 도구는 원본 서버 또는 풀의 알림 응용 프로그램에서 제공 하는 할당 되지 않은 번호 구성을 다른 서버나 풀로 이동 하는 Windows PowerShell 스크립트입니다.

할당 되지 않은 번호 알림 마이그레이션 스크립트를 실행 하면 다음 작업이 수행 됩니다.

1.  원본 서버 또는 풀에 호스트 된 알림 응용 프로그램의 할당 되지 않은 번호 알림에 사용 되는 모든 오디오 파일을 대상 서버 또는 풀의 파일 저장소로 이동 합니다.
    
    <div>
    

    > [!NOTE]  
    > 오디오 파일은 대상 풀로 복사 된 후 원본 풀에서 제거 됩니다.

    
    </div>

2.  원본 서버 또는 풀에서 호스트 되는 알림 응용 프로그램에 대해 구성 된 모든 할당 되지 않은 번호 알림을 대상 서버 또는 풀로 이동 합니다.

3.  원본 서버 또는 풀에서 호스트 되는 알림 응용 프로그램에서 지 원하는 모든 할당 되지 않은 번호 범위를 대상 서버 또는 풀에 다시 할당 합니다.

스크립트를 성공적으로 실행 한 후에는 원본 서버 또는 풀에서 호스트 되는 알림 응용 프로그램에 의해 처리 된 모든 할당 되지 않은 번호 범위가 대상 서버 또는 풀에서 동일한 구성으로 처리 됩니다.

</div>

<div>

## <a name="output"></a>출력

**CsAnnouncementConfiguration** 스크립트는 마이그레이션 작업의 성공 또는 실패를 실행 하는 Lync Management Shell 창을 나타냅니다.

작업 실행이 오류로 인해 중단 되는 경우 대상으로 성공적으로 이동 된 지정 되지 않은 번호 범위는 운영 양식의 대상에 유지 되 고 마이그레이션될 수 없는 나머지 번호 범위는 운영 양식의 원본에도 유지 됩니다. 나머지 구성을 완전히 마이그레이션하려면 오류를 해결 한 후 스크립트를 다시 실행 합니다.

</div>

<div>

## <a name="purpose"></a>용도

할당 되지 않은 번호 알림 마이그레이션 스크립트는 다음과 같은 세 가지 시나리오에서 사용할 수 있습니다.

  - **새 버전의 Lync Server로 구성 설정 마이그레이션:** Contoso는 lync server 2013로 마이그레이션하고 마이그레이션 프로세스의 일부로, Lync server 관리자가 알림 응용 프로그램에서 서비스를 제공 하는 할당 되지 않은 번호 구성을 Lync Server 2010 배포에서 새 Lync Server 2013 배포로 이동 하 고 싶습니다. 구성 설정을 이동 하기 위해 Lync Server 관리자는 할당 되지 않은 번호 알림 마이그레이션 도구를 사용 합니다.

  - **Lync server 2013에서 Lync server 2010로 배포 롤백:** 예기치 않은 요인으로 인해 Contoso는 새 Lync Server 2013 배포로 마이그레이션을 롤백해야 합니다. 서비스 중단을 최소화 하기 위해 Lync Server 관리자는 할당 되지 않은 번호 알림 마이그레이션 도구를 사용 하 여 Lync server 2013 배포의 구성을 Lync Server 2010 배포로 롤백합니다.

  - **Lync 배포 간에 데이터 이동:** Contoso는 한 풀의 모든 서버를 새 서버로 교체 하는 프로세스를 진행 중입니다. 이러한 전략은 새 Lync Server 2013 풀을 배포 하 고, 이전의 모든 데이터를 새 풀로 이동한 다음, 이전 풀을 사용 중지 하는 것입니다. 새 풀이 배포 되 면 할당 되지 않은 번호 알림 마이그레이션 도구를 사용 하 여 구성을 이전 풀에서 새 그룹으로 이동 합니다.

<div>

## <a name="requirements"></a>요구 사항

도구를 성공적으로 실행 하려면 다음과 같은 주요 요구 사항을 충족 해야 합니다.

1.  Lync Server 2013 관리 셸이 설치 된 컴퓨터에서 스크립트를 실행 해야 합니다.

2.  알림 응용 프로그램을 원본 및 대상 Lync 서버 또는 풀에 배포 해야 합니다.

<div>

## <a name="move-csannouncementconfiguration-script"></a>Move-CsAnnouncementConfiguration 스크립트

Move-CsAnnouncementConfiguration 스크립트를 사용 하려면 아래 표에 설명 된 매개 변수가 두 가지입니다.

![CsAnnouncementConfiguration 매개 변수입니다.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration 매개 변수")

</div>

</div>

</div>

<div>

## <a name="examples"></a>예

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a>지정 되지 않은 번호 알림 구성을 Lync Server 2010 풀에서 Lync Server 2013 풀로 이동

이 예제에서는 지정 되지 않은 번호 알림을 원본 풀 (Lync Server 2010)에서 대상 풀 (Lync Server 2013)로 이동 합니다.

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a>지정 되지 않은 번호 알림 구성을 Lync Server 2013 풀에서 Lync Server 2010 풀로 이동

이 예제에서는 지정 되지 않은 번호 알림을 원본 풀 (Lync Server 2013)에서 대상 풀 (Lync Server 2010)로 이동 합니다.

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a>웹 회의 데이터

웹 회의 데이터 도구를 사용 하면 Lync Server 2013 통신 소프트웨어 관리자가 이끌이의 웹 회의와 관련 된 데이터를 보다 강력 하 게 제어할 수 있습니다. 시나리오에는 타임 스탬프 조건을 기준으로 특정 사용자의 모임 데이터를 삭제 하는 기능이 포함 되어 있습니다.

<div>

## <a name="description"></a>설명

이 도구를 사용 하면 관리자가 다음 작업을 수행할 수 있습니다.

1.  단일 사용자와 연결 된 모든 웹 회의 데이터를 찾습니다.

2.  단일 사용자와 연결 된 모든 웹 회의 데이터를 삭제 합니다.

3.  특정 날짜 보다 오래 된 단일 사용자와 연결 된 모든 웹 회의 데이터를 삭제 합니다.

4.  사용자가 풀 간에 이동할 때 단일 사용자와 연결 된 모든 웹 회의 데이터를 이동 합니다.

<div>


> [!NOTE]  
> Lync Server 2010에 대 한 리소스 키트 도구는 단일 사용자와 연결 된 모든 웹 회의 데이터를 풀 간에 이동할 때 지원 합니다. 이 기능은 이제 <STRONG>MoveConferenceData</STRONG> 매개 변수로 인해이 도구에서 더 이상 사용 되지 않습니다. 이 매개 변수에 대 한 자세한 내용은 <A href="https://technet.microsoft.com/library/gg398528(v=ocs.15)">csuser</A> 을 참조 하십시오.



</div>

이 도구는 비활성 상태인 모임에 대 한 모임 데이터만 삭제 합니다. 활성 모임 (또는 세션의 모임)은 삭제할 수 없습니다.

이 도구는 대상 사용자와 같은 풀에 있는 컴퓨터에서 실행 해야 합니다. 이 도구를 사용 하 여 해당 모임 콘텐츠 데이터를 관리 하는 사용자는 동일한 사용자 풀에 있어야 합니다.

</div>

<div>

## <a name="output"></a>출력

이 도구는 각 작업의 결과를 출력 합니다.

  - 쿼리가 수행 되 면이 도구는 해당 사용자가 이끌이 인 모든 비활성 모임 데이터 폴더의 목록을 출력 합니다.

  - Delete를 수행 하는 경우이 도구는 해당 데이터가 삭제 될 모든 모임 데이터 폴더의 목록을 출력 합니다.

</div>

<div>

## <a name="requirements"></a>요구 사항

이 도구는 이끌이를 현재 홈에 있는 동일한 풀에서 실행 해야 합니다.

이 도구는 콘텐츠 파일 저장소에 대 한 액세스 권한으로 관리자 권한을 사용 하 여 실행 해야 합니다.

</div>

<div>

## <a name="examples"></a>예

다음 표에서는 예제에 사용 된 매개 변수에 대해 설명 합니다.

![웹 회의 데이터 도구 매개 변수](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "웹 회의 데이터 도구 매개 변수")

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

위 예제에서는 쿼리 명령이 작동 하는 방식을 보여 줍니다. 이러한 명령의 출력은이 도구의 영향을 받게 되는 모든 모임 콘텐츠 폴더의 목록입니다.

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

위의 예제는 delete 명령의 예입니다. 삭제 명령을 실행 하면 해당 사용자의 모든 비활성 모임 폴더가 제거 됩니다.

</div>

<div>

## <a name="summary"></a>요약

이 도구는 전화 회의 데이터를 보다 세부적으로 제어 해야 하는 관리자에 게 유용한 리소스가 될 수 있습니다.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

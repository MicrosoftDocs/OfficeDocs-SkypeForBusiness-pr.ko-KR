---
title: 'Lync Server 2013: System Center Operations Manager 데이터베이스로 Microsoft SQL Server 2008 R2 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49733555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27516e7ca6c3fb70a01b7c1d245054d515ae351b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744058"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a>Lync Server 2013의 System Center Operations Manager 데이터베이스로 Microsoft SQL Server 2008 R2를 사용 하는 경우

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-07-29_

백 엔드 데이터베이스로 SQL Server 2008 R2를 사용 하려면이 항목에서 설명 하는 단계를 완료 합니다.

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a>SQL Server 2008 R2 및 SQL Server Reporting Services 구성

System Center Operations Manager 설치를 시작 하기 전에 SQL Server 2008 R2 및 SQL Server Reporting Services 구성에 대 한 두 가지 변경 작업을 수행 해야 합니다. 이러한 변경 사항은 SQL Server 2008 R2를 Operations Manager 데이터베이스로 사용 하는 경우에만 필요 합니다. 먼저 Operations Manager 데이터베이스를 호스트 하는 컴퓨터에서 다음을 수행 합니다.

1.  **시작** 을 클릭 한 다음 **실행**을 클릭 합니다.

2.  **실행** 대화 상자에 **C\\: Program Files\\Microsoft SQL Server\\ MSRS10\_50ARCHINST\\Reporting Services\\ReportServer** 를 입력 한 다음 enter 키를 누릅니다.

3.  **ReportServer** 폴더에서 메모장 또는 다른 텍스트 편집기에서 **rsreportserver** 파일을 엽니다.

4.  파일의 시작 부분 근처에 일련의 "키 추가" 노드가 표시 됩니다. 키 추가를 시작 **** ** \<하는 항목을 찾아 "secureconnectionlevel"** 을 입력 하 고 값을 0으로 설정 합니다.
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  **Rsreportserver** 파일을 저장 한 다음 텍스트 편집기를 닫습니다.

보고서 서버 구성 파일을 업데이트 한 후에는 SQL Server Reporting Services에 올바른 인증서를 할당 해야 합니다. 실행할 작업

1.  **시작**을 클릭 하 고 **모든 프로그램**, **Microsoft SQL Server 2008 R2**, **구성 도구**를 차례로 클릭 한 다음 **Reporting Services 구성 관리자**를 클릭 합니다.

2.  **Reporting Services 구성 연결** 대화 상자의 **서버** 이름 상자에 서버 이름이 표시 되는지 확인 합니다. **보고서 서버 인스턴스** 드롭다운 목록에서 Operations Manager 데이터베이스 (예: **ARCHINST**)을 호스팅할 SQL Server 인스턴스를 선택한 다음 **연결**을 클릭 합니다.

3.  Reporting Services 구성 관리자에서 **웹 서비스 URL**을 클릭 합니다.

4.  **웹 서비스 URL** 페이지의 **SSL 인증서** 드롭다운 목록에서 보고 서비스에 사용할 인증서를 선택 하 고 **적용**을 클릭 합니다. 몇 초 후에는 **보고서 서버 웹 서비스 url**아래에 나열 된 하나의 url이 표시 됩니다.

5.  두 Url을 모두 클릭 하 여 SQL Server Reporting Services에 액세스할 수 있는지 확인 합니다.

6.  Reporting Services 구성 관리자를 닫습니다.

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a>SQL Server 2008 R2와 함께 사용할 System Center Operations Manager 데이터베이스 만들기

SQL Server 2008 R2 데이터베이스를 사용 하도록 System Center Operations Manager를 구성 하려면 SQL Server 2008 R2를 실행 하는 컴퓨터에서 Operations Manager 데이터베이스를 "수동으로 만들어야 합니다."가 필요 합니다. (이 단계는 SQL Server 2005 또는 SQL Server 2008를 백 엔드 데이터베이스로 사용 하는 경우에는 필요 하지 않습니다.)

Operations Manager 데이터베이스를 수동으로 만들려면 다음을 실행 합니다.

1.  System Center Operations Manager 2007 R2 설치 미디어의 SupportTools\\AMD64 폴더에서 **dbcreatewizard. exe**를 두 번 클릭 합니다.

2.  데이터베이스 구성 마법사의 **데이터베이스 구성 마법사 시작** 페이지에서 **다음**을 클릭 합니다.

3.  **데이터베이스 정보** 페이지에서 모든 설정을 그대로 두고 **다음** 을 클릭 합니다.

4.  관리 그룹 **구성** 페이지의 관리 그룹 **이름** 상자에 관리 그룹의 이름 (예: **Lync Server 모니터링**)을 입력 하 고 **다음**을 클릭 합니다.

5.  **Operations Manager 오류 보고서** 페이지에서 **다음**을 클릭 합니다.

6.  **요약** 페이지에서 **마침을**클릭 합니다.

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a>SQL Server 2008 R2와 함께 사용할 System Center Operations Manager 데이터 웨어하우스 만들기

Microsoft Lync Server 2013에는 다음과 같은 세 가지 새로운 System Center Operations Manager 보고서가 제공 됩니다.

  - **End to end 시나리오 가용성 보고서**   이 보고서에는 등록 또는 현재 상태와 같은 주요 Lync Server 서비스의 가용성/가동 시간이 자세히 설명 되어 있습니다.

  - **용량 보고서**   성능 카운터 정보를 사용 하 여이 보고서에는 메모리 가용성 및 프로세서 사용량 같은 시스템 구성 요소에 대 한 추세가 표시 됩니다.

  - **구성 요소 보고서**   이 보고서에는 Lync Server 구성 요소로 그룹화 된 최상위 알림 생성기가 나열 됩니다.

이러한 새 보고서를 사용 하기 위해서는 System Center Operations Manager 데이터 웨어하우스를 설치 해야 합니다. (데이터 웨어하우스는 작업 데이터의 장기 저장소를 제공 합니다.) SQL Server 2008 R2에서 데이터 웨어하우스를 사용 하려면 SQL Server 데이터베이스를 호스트 하는 컴퓨터에서 다음 단계를 수행 해야 합니다.

1.  System Center Operations Manager 설치 미디어의 설정\\supporttools\\AMD64 폴더에서 **dbcreatewizard. exe**를 두 번 클릭 합니다.

2.  데이터베이스 구성 마법사의 **데이터베이스 구성 마법사 시작** 페이지에서 **다음**을 클릭 합니다.

3.  **데이터베이스 정보** 페이지의 **데이터베이스 유형** 드롭다운 목록에서 **Operations Manager 데이터 웨어하우스 데이터베이스** 를 선택 하 고 **다음**을 클릭 합니다.

4.  **요약** 페이지에서 **마침을**클릭 합니다.

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a>System Center Operations Manager 콘솔 설치

Operations Manager 콘솔은 System Center Operations Manager를 관리 하는 데 사용 되는 기본 도구입니다. Operations Manager 콘솔을 설치 하기 전에 SQL Server Reporting Services와 함께 지원 되는 버전의 SQL Server가 설치 되어 있는지 확인 합니다. 또한 SQL Server의 Reporting Services 구성 관리자를 실행 하 여 보고 서비스가 올바르게 설치 및 구성 되었는지 확인 하는 것이 좋습니다.

System Center Operations Manager 콘솔을 설치 하려면 다음을 수행 합니다.

1.  System Center Operations Manager 설치 미디어에서 **SetupOM**를 두 번 클릭 합니다.

2.  System Center Operations Manager 2007 R2 설정에서 **필수 구성 요소 확인**을 클릭 합니다.

3.  System Center Operations Manager 필수 구성 요소 뷰어에서 설치할 System Center 구성 요소 (**서버**;)를 선택 합니다. **콘솔**; 및 **PowerShell**)을 선택한 다음 **확인**을 클릭 합니다. 차단 문제가 보고 되지 않았는지 확인 한 다음 **닫기를**클릭 합니다. 차단 문제가 보고 된 경우 문제를 해결 한 다음 **확인** 을 클릭 하 여 필수 구성 요소 테스트를 다시 실행 합니다.

4.  System Center Operations Manager 설치에서 **Operations Manager 설치**를 클릭 합니다.

5.  System Center Operations Manager 설치 마법사의 **System Center Operations Manager 설치 마법사 시작** 페이지에서 **다음**을 클릭 합니다.

6.  **최종 사용자 사용권 계약** 페이지에서 **사용권 계약에 동의 함을** 선택 하 고 **다음**을 클릭 합니다.

7.  **제품 등록** 페이지의 **사용자 이름** 상자에 이름을 입력 하 고 **조직** 상자에 조직의 이름을 입력 합니다. **25 자리 CD 키 입력** 상자에 System Center Operations Manager 제품 키를 입력 하 고 **다음**을 클릭 합니다.

8.  **사용자 지정 설정** 페이지에서 설치할 시스템 센터 옵션을 선택 하 고 **다음**을 클릭 합니다. 설치할 **관리 서버**, **사용자 인터페이스**, **웹 콘솔** 을 선택 해야 합니다. **데이터베이스** 를 선택 하 여 설치 하면 안 됩니다.

9.  **SC 데이터베이스 서버 인스턴스** 페이지에서 Operations Manager 데이터베이스가 설치 되어 있는 컴퓨터의 이름이 **System Center 데이터베이스 서버** 상자에 나타나는지 확인 합니다. **다음**을 클릭 합니다.

10. **관리 서버 작업 계정** 페이지에서 **도메인 또는 로컬 컴퓨터 계정을** 선택한 다음 **사용자 계정**, **암호**및 **도메인 또는 로컬 컴퓨터** 상자에 적절 한 값을 입력 합니다. **다음**을 클릭 합니다.

11. **SDK 및 구성 서비스 계정** 페이지에서 **도메인 또는 로컬 컴퓨터 계정을** 선택한 다음 **사용자 계정**, **암호**및 **도메인 또는 로컬 컴퓨터** 상자에 적절 한 값을 입력 합니다. **다음**을 클릭 합니다.

12. **Operations Manager 오류 보고서** 페이지에서 **다음**을 클릭 합니다.

13. **사용자 환경 개선 프로그램** 페이지에서 **다음**을 클릭 합니다.

14. **프로그램 설치 준비 완료** 페이지에서 **설치**를 클릭 합니다.

15. **System Center Operations Manager 설치 완료** 페이지에서 **백업 암호화 키** 를 지우고 **콘솔 확인란을 시작한** 다음 **마침을**클릭 합니다.

16. System Center Operations Manager 설치 **종료**를 클릭 합니다.

</div>

<div>

## <a name="installing-system-center-reporting-services"></a>System Center Reporting Services 설치

System Center Operations Manager 콘솔을 설치 하 고 구성한 후 System Center Reporting Services를 설치 해야 합니다. SQL Server 2008 R2를 Operations Manager 백 엔드 데이터베이스로 사용 하는 경우 먼저 SQL Server Reporting Services와 연결 된 보안 그룹에 대 한 임시 변경 작업을 수행 해야 합니다. SQL Server 2008 R2를 사용 하는 경우 다음을 수행 해야 합니다.

1.  **시작**을 클릭 하 고 **관리 도구**를 가리킨 다음 **서버 관리자**를 클릭 합니다.

2.  서버 관리자에서 **구성을**확장 하 고 **로컬 사용자 및 그룹**을 확장 한 다음 **그룹**을 클릭 합니다.

3.  다음 그룹을 찾습니다. 여기서 atl-sc-001은 컴퓨터의 이름을 나타내고 ARCHINST는 System Center 데이터베이스에 대 한 SQL Server 인스턴스를 나타냅니다. **SQLServerReportServerUser $ atl-sc-001 $ MSRS10\_50. ARCHINST**.

4.  그룹을 마우스 오른쪽 단추로 클릭 한 다음 **이름 바꾸기를**클릭 합니다. 그룹 이름에서 ** \_50** 을 삭제 하 여 그룹의 이름을 바꿉니다. 예: **SQLServerReportServerUser $ atl-sc-001 $ MSRS10. ARCHINST**.

5.  서버 관리자를 닫습니다.

이 시점에서 System Center Reporting Services를 설치할 준비가 되었습니다. 실행할 작업:

1.  System Center Operations Manager 2007 R2 설치 미디어에서 **SetupOM**를 두 번 클릭 합니다.

2.  System Center Operations Manager 2007 R2 설정에서 **Operations Manager Reporting 설치**를 클릭 합니다.

3.  System Center Operations Manager 2007 R2 Reporting 설치 마법사의 **Operations Manager Reporting Setup 시작** 페이지에서 **다음**을 클릭 합니다.

4.  **최종 사용자 사용권 계약** 페이지에서 **사용권 계약 조건에 동의 함을** 선택 하 고 **다음**을 클릭 합니다.

5.  **제품 등록** 페이지에서 **사용자** 이름 및 **조직** 상자에 조직의 이름과 이름이 표시 되는지 확인 하 고 **다음**을 클릭 합니다.

6.  **사용자 지정 설정** 페이지에서 **보고 서버** 를 클릭 하 고 **이 구성 요소와 모든 종속 구성 요소가 로컬 디스크 드라이브에 설치 됩니다**를 선택 합니다. **데이터 웨어하우스** 를 클릭 하 고 **이 구성 요소를 사용할 수 없게 됨**을 선택한 후 **다음**을 클릭 합니다.

7.  **루트 관리 서버에 연결** 페이지의 **루트 관리 서버** 상자에 Operations Manager 루트 관리 서버의 이름을 입력 하 고 **다음**을 클릭 합니다.

8.  **Operations Manager 데이터 웨어하우스에 연결** 페이지에서 **sql server 인스턴스** 상자에 데이터 웨어하우스가 있는 sql server 인스턴스를 입력 합니다. (데이터 웨어하우스가 기본 인스턴스에 있는 경우 서버 이름을 입력 합니다 (예: atl--001).). **이름** 상자에 데이터베이스 이름 **OperationsManagerDW** 이 표시 되 고 해당 포트 **1433** 이 **SQL Server 포트** 상자에 표시 되는지 확인 합니다. **다음**을 클릭 합니다.

9.  **Sql Server 보고 인스턴스** 페이지의 **Sql Server reporting Services 서버** 드롭다운 목록에서 sql server reporting server를 선택 하 고 **다음**을 클릭 합니다.

10. **데이터 웨어하우스 쓰기 계정** 페이지에서 **사용자 계정** 및 **암호** 상자에 데이터 웨어하우스에 대 한 쓰기 권한을 처음 할당할 사용자의 이름과 암호를 입력 합니다. **도메인** 드롭다운 목록에서 사용자의 도메인을 선택 하 고 **다음**을 클릭 합니다.

11. **데이터 읽기 프로그램 계정** 페이지에서 SQL Reporting Services **가 사용자 계정** 및 **암호** 상자에 데이터 웨어하우스를 쿼리할 때 사용할 사용자 계정의 이름과 암호를 입력 합니다. **도메인** 드롭다운 목록에서 계정 도메인을 선택 하 고 **다음**을 클릭 합니다.

12. **작업 데이터 보고서** 페이지에서 **다음**을 클릭 합니다.

13. **Microsoft 업데이트** 페이지에서 **다음**을 클릭 합니다.

14. **프로그램 설치 준비 완료** 페이지에서 **설치**를 클릭 합니다.

15. **Operations Manager 보고 구성 요소 설정 마법사 완료** 페이지에서 **마침을**클릭 합니다.

16. System Center Operations Manager 2007 R2 설정에서 **끝내기**를 클릭 합니다.

System Center reporting을 설치한 후에는 다음 절차를 사용 하 여 SQL Server reporting에 연결 된 보안 그룹의 이름을 다시 설정 합니다. 이 절차는 SQL Server를 사용 하는 경우에만 필요 합니다.

1.  **시작**을 클릭 하 고 **관리 도구**를 가리킨 다음 **서버 관리자**를 클릭 합니다.

2.  서버 관리자에서 **구성을**확장 하 고 **로컬 사용자 및 그룹**을 확장 한 다음 **그룹**을 클릭 합니다.

3.  다음 그룹을 찾습니다. 여기서 atl-sc-001은 컴퓨터의 이름을 나타내고 ARCHINST는 보관 및 모니터링 데이터베이스에 대 한 SQL Server 인스턴스를 나타냅니다. **SQLServerReportServerUser $ atl-sc-001 $ MSRS10. ARCHINST**.

4.  그룹을 마우스 오른쪽 단추로 클릭 한 다음 **이름 바꾸기를**클릭 합니다. 그룹 이름 끝에 ** \_50** 를 추가 하 여 그룹의 이름을 변경 하 고 SQL Server 인스턴스 이름 바로 앞에 있습니다. 예: **SQLServerReportServerUser $ atl-sc-001 $ MSRS10\_50. ARCHINST**.

5.  서버 관리자를 닫습니다.

System Center Operations Console이 열려 있는 경우에는 응용 프로그램을 닫았다가 다시 시작 해야 합니다. 이 작업을 수행 하지 않으면 작업 콘솔 사용자 인터페이스에 **보고** 탭이 표시 되지 않습니다. 처음으로 운영 콘솔을 다시 시작한 후에는 모든 모니터링 보고서가 **보고** 탭에 표시 되기까지 몇 분 정도 걸릴 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>


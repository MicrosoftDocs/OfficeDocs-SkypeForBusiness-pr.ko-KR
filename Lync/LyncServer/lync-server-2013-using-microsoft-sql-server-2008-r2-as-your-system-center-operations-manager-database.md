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
ms.openlocfilehash: 0001d70033aac6d7c6125bb9e4016143beefc80f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a>Lync Server 2013에 Microsoft SQL Server 2008 R2를 System Center Operations Manager 데이터베이스로 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-07-29_

SQL Server 2008 R2를 백 엔드 데이터베이스로 사용 하려면이 항목에서 설명 하는 단계를 완료 합니다.

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a>SQL Server 2008 R2 및 SQL Server Reporting Services 구성

System Center Operations Manager 설치를 시작 하기 전에 SQL Server 2008 R2 및 SQL Server Reporting Services 구성에 대 한 두 가지 변경 작업을 수행 해야 합니다. 이러한 변경 내용은 SQL Server 2008 R2를 Operations Manager 데이터베이스로 사용 하는 경우에만 필요 합니다. 먼저 Operations Manager 데이터베이스를 호스트 하는 컴퓨터에서 다음을 수행 합니다.

1.  **시작**을 클릭하고 **실행**을 클릭합니다.

2.  **실행** 대화 상자에 **C\\: Program Files\\Microsoft SQL Server\\ atl-sc-001\_은\\Reporting Services\\ReportServer** 를 입력 한 다음 enter 키를 누릅니다.

3.  **ReportServer** 폴더에서 **Rsreportserver.config** 파일을 메모장 이나 다른 텍스트 편집기에서 엽니다.

4.  파일의 시작 부분에 일련의 "Add Key (키)" 노드가 표시 됩니다. **Add Key = "secureconnectionlevel"을 입력 하 고 값을 0으로 설정 합니다. \<** ****
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  **Rsreportserver.config** 파일을 저장 하 고 텍스트 편집기를 닫습니다.

보고서 서버 구성 파일을 업데이트 한 후에는 SQL Server Reporting Services에 올바른 인증서를 할당 해야 합니다. 이렇게 하려면 다음을 수행 합니다.

1.  **시작**, **모든 프로그램**, **Microsoft SQL Server 2008 R2**, **구성 도구**를 차례로 클릭 한 후 **Reporting Services 구성 관리자**를 클릭 합니다.

2.  **Reporting Services 구성 연결** 대화 상자에서 서버 이름이 **서버 이름** 상자에 표시 되는지 확인 합니다. **보고서 서버 인스턴스** 드롭다운 목록에서 Operations Manager 데이터베이스 (예: **은**)를 호스팅할 SQL Server 인스턴스를 선택 하 고 **연결**을 클릭 합니다.

3.  Reporting Services 구성 관리자에서 **웹 서비스 URL**을 클릭 합니다.

4.  **웹 서비스 URL** 페이지의 **SSL 인증서** 드롭다운 목록에서 Reporting Services에 사용할 인증서를 선택 하 고 **적용**을 클릭 합니다. 몇 초 후에는 **보고서 서버 웹 서비스 url**아래에 나열 된 한 쌍의 url이 표시 됩니다.

5.  두 Url을 모두 클릭 하 여 SQL Server Reporting Services에 액세스할 수 있는지 확인 합니다.

6.  Reporting Services 구성 관리자를 닫습니다.

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a>SQL Server 2008 r 2에 사용할 System Center Operations Manager 데이터베이스 만들기

System Center Operations Manager에서 SQL Server 2008 R2 데이터베이스를 사용 하도록 구성 하려면 SQL Server 2008 R2를 실행 하는 컴퓨터에 Operations Manager 데이터베이스를 "수동" 해야 합니다. 다시 말하지만, SQL Server 2005 또는 SQL Server 2008을 백 엔드 데이터베이스로 사용 하는 경우에는 이러한 단계를 수행할 필요가 없습니다.

Operations Manager 데이터베이스를 수동으로 만들려면 다음을 수행 합니다.

1.  System Center Operations Manager 2007 R2 설치 미디어의 SupportTools\\AMD64 폴더에서 **dbcreatewizard .exe**를 두 번 클릭 합니다.

2.  데이터베이스 구성 마법사의 **데이터베이스 구성 마법사 시작** 페이지에서 **다음**을 클릭 합니다.

3.  **데이터베이스 정보** 페이지에서 모든 설정을 그대로 유지 하 고 **다음** 을 클릭 합니다.

4.  관리 그룹 **구성** 페이지의 관리 **그룹 이름** 상자에 관리 그룹의 이름 (예: **Lync Server Monitoring**)을 입력 하 고 **다음**을 클릭 합니다.

5.  **Operations Manager 오류 보고서** 페이지에서 **다음**을 클릭 합니다.

6.  **요약** 페이지에서 **마침을**클릭 합니다.

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a>SQL Server 2008 r 2에 사용할 System Center Operations Manager 데이터 웨어하우스 만들기

Microsoft Lync Server 2013은 다음과 같은 세 가지 새로운 System Center Operations Manager 보고서와 함께 제공 됩니다.

  - **End to end Scenario availability report**   이 보고서는 등록 또는 현재 상태의 주요 Lync Server 서비스에 대 한 가용성/가동 시간을 자세히 설명 합니다.

  - **용량 보고서**   이 보고서에서는 성능 카운터 정보를 사용 하 여 메모리 가용성 및 프로세서 사용량과 같은 시스템 구성 요소의 추세를 보여 줍니다.

  - **구성 요소 보고서**   이 보고서에는 Lync Server 구성 요소별 그룹화 된 최상위 알림 생성기가 나열 됩니다.

이러한 새 보고서를 사용 하려면 System Center Operations Manager 데이터 웨어하우스를 설치 해야 합니다. (데이터 웨어하우스는 장기 작업 데이터 저장소를 제공 합니다.) SQL Server 2008 R2에서 데이터 웨어하우스를 사용 하려면 SQL Server 데이터베이스를 호스팅하는 컴퓨터에서 다음 단계를 수행 해야 합니다.

1.  System Center Operations Manager 설치 미디어의 설치\\지원 도구\\AMD64 폴더에서 **dbcreatewizard .exe**를 두 번 클릭 합니다.

2.  데이터베이스 구성 마법사의 **데이터베이스 구성 마법사 시작** 페이지에서 **다음**을 클릭 합니다.

3.  **데이터베이스 정보** 페이지의 **데이터베이스 유형** 드롭다운 목록에서 **Operations Manager 데이터 웨어하우스 데이터베이스** 를 선택 하 고 **다음**을 클릭 합니다.

4.  **요약** 페이지에서 **마침을**클릭 합니다.

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a>System Center Operations Manager 콘솔 설치

Operations Manager 콘솔은 System Center Operations Manager를 관리 하는 데 사용 되는 기본 도구입니다. Operations Manager 콘솔을 설치 하기 전에 sql Server Reporting Service와 함께 지원 되는 버전의 SQL Server를 설치 했는지 확인 합니다. 또한 SQL Server의 Reporting Services 구성 관리자를 실행 하 여 Reporting Service가 올바르게 설치 및 구성 되었는지 확인 하는 것이 좋습니다.

System Center Operations Manager 콘솔을 설치 하려면

1.  System Center Operations Manager 설치 미디어에서 **setupom.exe**를 두 번 클릭 합니다.

2.  System Center Operations Manager 2007 R2 설치에서 **필수 구성 요소 확인**을 클릭 합니다.

3.  System Center Operations Manager 필수 구성 요소 보기에서 설치할 System Center components (**서버**;)를 선택 합니다. **콘솔**; 및 **PowerShell**)을 선택 하 고 **확인**을 클릭 합니다. 차단 문제가 보고 되지 않았는지 확인 하 고 **닫기를**클릭 합니다. 차단 문제가 보고 된 경우 문제를 해결 한 다음 **확인** 을 클릭 하 여 필수 구성 요소 테스트를 다시 실행 합니다.

4.  System Center Operations Manager 설치에서 **Operations Manager 설치**를 클릭 합니다.

5.  System Center Operations Manager 설치 마법사의 **System Center Operations Manager 설치 마법사 시작** 페이지에서 **다음**을 클릭 합니다.

6.  **최종 사용자 사용권 계약** 페이지에서 **동의 함을** 선택 하 고 **다음**을 클릭 합니다.

7.  **제품 등록** 페이지의 **사용자 이름** 상자에 이름을 입력 하 고 **조직 상자의 이름** **25 자리 CD 키 입력** 상자에 System Center Operations Manager 제품 키를 입력 하 고 **Next (다음**)를 클릭 합니다.

8.  **사용자 지정 설치** 페이지에서 설치할 시스템 센터 옵션을 선택 하 고 **다음**을 클릭 합니다. 설치할 **관리 서버**, **사용자 인터페이스**및 **웹 콘솔** 을 선택 해야 합니다. **데이터베이스** 를 선택 하 여 설치 하면 안 됩니다.

9.  **SC 데이터베이스 서버 인스턴스** 페이지에서 Operations Manager 데이터베이스가 설치 된 컴퓨터의 이름이 **System Center 데이터베이스 서버** 상자에 나타나는지 확인 합니다. **다음**을 클릭합니다.

10. **관리 서버 작업 계정** 페이지에서 **도메인 또는 로컬 컴퓨터 계정을** 선택 하 고 **사용자 계정**, **암호**및 **도메인 또는 로컬 컴퓨터** 상자에 적절 한 값을 입력 합니다. **다음**을 클릭합니다.

11. **SDK 및 Config Service 계정** 페이지에서 **도메인 또는 로컬 컴퓨터 계정을** 선택 하 고 **사용자 계정**, **암호**및 **도메인 또는 로컬 컴퓨터** 상자에 적절 한 값을 입력 합니다. **다음**을 클릭합니다.

12. **Operations Manager 오류 보고서** 페이지에서 **다음**을 클릭 합니다.

13. **사용자 환경 개선 프로그램** 페이지에서 **다음**을 클릭 합니다.

14. **프로그램 설치 준비 완료** 페이지에서 **설치**를 클릭 합니다.

15. **System Center Operations Manager 설치 완료** 페이지에서 **암호화 키 백업** 및 **콘솔 시작 확인란** 선택을 취소 하 고 **마침을**클릭 합니다.

16. System Center Operations Manager 설치에서 **끝내기**를 클릭 합니다.

</div>

<div>

## <a name="installing-system-center-reporting-services"></a>System Center Reporting Services 설치

System Center Operations Manager 콘솔을 설치 및 구성한 후 System Center Reporting Services를 설치 해야 합니다. SQL Server 2008 R2를 Operations Manager 백 엔드 데이터베이스로 사용 하는 경우에는 먼저 SQL Server Reporting Services와 연결 된 보안 그룹을 임시로 변경 해야 합니다. SQL Server 2008 R2를 사용 하는 경우에는 다음을 수행 해야 합니다.

1.  **시작**을 클릭하고 **관리 도구**를 가리킨 다음 **서버 관리자**를 클릭합니다.

2.  서버 관리자에서 **구성**, **로컬 사용자 및 그룹**을 차례로 확장한 다음 **그룹**을 클릭합니다.

3.  다음 그룹을 찾습니다. 여기서 atl-sc-a는 컴퓨터의 이름을 나타내고은는 System Center 데이터베이스에 대 한 SQL Server 인스턴스 **SQLServerReportServerUser $ atl-sc-001 $\_atl-sc-001 50은**를 나타냅니다.

4.  그룹을 마우스 오른쪽 단추로 클릭 한 다음 **이름 바꾸기를**클릭 합니다. 그룹 이름에서 ** \_50** 을 삭제 하 여 그룹 이름을 바꿉니다. 예: **SQLServerReportServerUser $ atl-sc-001 $ atl-sc-001. 은**

5.  서버 관리자를 닫습니다.

이 시점에 System Center Reporting Services를 설치할 준비가 되었습니다. 이렇게 하려면 다음을 실행합니다.

1.  System Center Operations Manager 2007 R2 설치 미디어에서 **setupom.exe**를 두 번 클릭 합니다.

2.  System Center Operations Manager 2007 R2 설치에서 **Operations Manager 보고 설치**를 클릭 합니다.

3.  System Center Operations Manager 2007 R2 Reporting 설치 마법사의 **Operations Manager Reporting 설치 시작** 페이지에서 **다음**을 클릭 합니다.

4.  **최종 사용자 사용권 계약** 페이지에서 **동의** 함을 선택 하 고 **다음**을 클릭 합니다.

5.  **제품 등록** 페이지에서 **사용자** 이름과 **조직 상자에 조직의 이름 및 이름이** 표시 되는지 확인 하 고 **다음**을 클릭 합니다.

6.  **사용자 지정 설치** 페이지에서 **Reporting Server** 를 클릭 하 고 **이 구성 요소를 선택 하 고 모든 종속 구성 요소를 로컬 디스크 드라이브에 설치**합니다. **데이터 웨어하우스** 를 클릭 하 고 **이 구성 요소를 사용할 수 없는**것을 선택한 후 **다음**을 클릭 합니다.

7.  **루트 관리 서버에 연결** 페이지의 **루트 관리 서버** 상자에 Operations Manager 루트 관리 서버의 이름을 입력 하 고 **다음**을 클릭 합니다.

8.  **Operations Manager 데이터 웨어하우스에 연결** 페이지에서 데이터 웨어하우스가 **sql server 인스턴스** 상자에 있는 sql server 인스턴스를 입력 합니다. (데이터 웨어하우스가 기본 인스턴스에 있는 경우에는 서버 이름 (예: atl-sql-dmo)을 입력 하면 됩니다.) 데이터베이스 이름 **OperationsManagerDW** 이 **이름** 상자에 나타나고 해당 포트 **1433** 이 **SQL Server 포트** 상자에 나타나는지 확인 합니다. **다음**을 클릭합니다.

9.  **Sql Server 보고 인스턴스** 페이지의 **Sql Server Reporting Services 서버 입력** 드롭다운 목록에서 sql server 보고 서버를 선택 하 고 **다음**을 클릭 합니다.

10. **데이터 웨어하우스의 계정 쓰기** 페이지에서 **사용자 계정** 및 **암호** 상자에 데이터 웨어하우스에서 처음에 할당 될 사용자의 이름과 암호를 입력 합니다. **도메인** 드롭다운 목록에서 사용자의 도메인을 선택 하 고 **다음**을 클릭 합니다.

11. **데이터 판독기 계정** 페이지에 SQL Reporting Services에서 **사용자 계정** 및 **암호** 상자에 데이터 웨어하우스를 쿼리할 때 사용할 사용자 계정의 이름과 암호를 입력 합니다. **도메인** 드롭다운 목록에서 계정 도메인을 선택 하 고 **다음**을 클릭 합니다.

12. **운영 데이터 보고서** 페이지에서 **다음**을 클릭 합니다.

13. **Microsoft 업데이트** 페이지에서 **다음**을 클릭 합니다.

14. **프로그램 설치 준비 완료** 페이지에서 **설치**를 클릭 합니다.

15. **Operations Manager Reporting Components 설치 마법사 완료** 페이지에서 **마침을**클릭 합니다.

16. System Center Operations Manager 2007 R2 설치에서 **끝내기**를 클릭 합니다.

System Center 보고가 설치 된 후 다음 절차에 따라 SQL Server 보고와 연결 된 보안 그룹의 이름을 다시 설정 합니다. 이 절차는 SQL Server를 사용 하는 경우에만 필요 합니다.

1.  **시작**을 클릭하고 **관리 도구**를 가리킨 다음 **서버 관리자**를 클릭합니다.

2.  서버 관리자에서 **구성**, **로컬 사용자 및 그룹**을 차례로 확장한 다음 **그룹**을 클릭합니다.

3.  다음 그룹을 찾습니다. 여기서 atl-sc-a는 컴퓨터의 이름을 나타내고은은 보관 및 모니터링 데이터베이스에 대 한 SQL Server 인스턴스 **SQLServerReportServerUser $ atl-sc-001 $ atl-sc-001를 나타냅니다. 은**

4.  그룹을 마우스 오른쪽 단추로 클릭 한 다음 **이름 바꾸기를**클릭 합니다. 그룹 이름 끝에 ** \_50** 을 더하여 SQL Server 인스턴스 이름 바로 앞에 추가 하 여 그룹 이름을 바꿉니다. 예: **SQLServerReportServerUser $ atl-sc-001 $ atl-sc-001\_50.은**

5.  서버 관리자를 닫습니다.

System Center Operations 콘솔이 열려 있는 경우 응용 프로그램을 닫고 다시 시작 해야 합니다. 이 작업을 수행 하지 않으면 작업 콘솔 사용자 인터페이스에 **보고** 탭이 나타나지 않습니다. 운영 콘솔을 처음 다시 시작한 후에는 모든 모니터링 보고서가 **보고** 탭에 표시 될 때까지 몇 분 정도 걸릴 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: 응답 그룹 구성 권한 및 필수 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1360a6dee8dbbf169fa0ceda1ee1b2f215ff09b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a>Lync Server 2013의 응답 그룹 구성 권한 및 필수 구성 요소

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-05_

응답 그룹은 엔터프라이즈 음성 통화 관리 기능입니다. 이 항목에서는 응답 그룹을 구성 하 고 구성 작업을 수행 하는 데 필요한 관리 자격 증명과 사용 권한을 구성할 수 있도록 하기 위해 필요한 사항에 대해 설명 합니다.

이 섹션에서는 응답 그룹과 관련 된 계획 문서를 읽은 것으로 가정 합니다. 자세한 내용은 계획 문서에서 [Lync Server 2013의 통화 관리 기능 계획](lync-server-2013-planning-for-call-management-features.md) 을 참조 하세요.

<div>

## <a name="configuration-tools-and-administrative-roles"></a>구성 도구 및 관리 역할

다음 관리 도구를 사용 하 여 응답 그룹을 구성할 수 있습니다.

  - Lync Server 제어판

  - 응답 그룹 구성 도구

  - Lync Server Management Shell

응답 그룹을 구성 하려면 다음 관리 역할 중 하나 이상의 구성원 이어야 합니다.


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Active Directory 보안 그룹 (1)</strong></p></td>
<td><p>워크플로 만들기</p></td>
<td><p>관리자 할당</p></td>
<td><p>에이전트 만들기/할당/큐</p></td>
<td><p>휴일 및 업무 시간 만들기/관리</p></td>
<td><p>워크플로 활성화/비활성화</p></td>
<td><p>워크플로 구성 (IVR 또는 헌트 그룹)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsResponseGroupAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsResponseGroupManager</strong></p></td>
<td> </td>
<td><p>√ (2)</p></td>
<td><p>√ (3)</p></td>
<td><p>√ (3)</p></td>
<td><p>√ (3)</p></td>
<td><p>√ (3)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsVoiceAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsServerAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="even">
<td><p><strong>CsAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>Csviewadministrator</strong></p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>(1)</STRONG> Active Directory 도메인 서비스 사용자 개체가 나열 된 active directory 보안 그룹의 구성원 이어야 합니다. 보안 그룹에 사용자를 추가 하는 적절 한 사용 권한이 있는 관리자 또는 기타 위임 된 Active Directory 그룹 구성원 (예: 관리자, 계정 운영자)이 사용자에 게 나열 된 보안 그룹 또는 그룹에 사용자 개체를 추가 해야 사용할 수 있습니다. 나열 된 함수를 수행 합니다. <STRONG>(2)</STRONG> CsResponseGroupAdministrator가 Csresponsegroupadministrator에 할당 한 워크플로에만 해당 합니다. <STRONG>(3)</STRONG> 응답 그룹 관리자가 CsResponseGroupManager의 다른 구성원을 현재 관리자가 이미 관리 하는 워크플로에 할당할 수 있습니다. <STRONG>(4)</STRONG> csviewonly 관리자는 동사 "Get" Lync Server Management Shell cmdlet만 실행할 수 있습니다.



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a>응답 그룹 구성 필수 조건

응답 그룹에는 다음 구성 요소가 필요 합니다.

  - 응용 프로그램 서비스

  - 응답 그룹 응용 프로그램

  - 언어 팩

  - 파일 저장소 (오디오 파일 저장)

  - 웹 서비스 (응답 그룹 구성 도구 및 에이전트의 로그인 및 로그 아웃 콘솔 포함)

이러한 구성 요소는 모두 엔터프라이즈 음성을 구축할 때 기본적으로 설치 됩니다.

응답 그룹을 구성 하기 전에 다음 작업을 수행 해야 할 수 있습니다.

  - Lync Server 2013 및 Enterprise Voice에 대해 사용자를 사용 하도록 설정 합니다.

  - 연방 정보 처리 표준 (FIPS)을 준수 하도록 구성 파일을 수정 합니다.

  - 데이터베이스 데이터 정렬을 수정 하 여 대기열 이름과 에이전트 그룹 이름에 대해 Yi, Meng 및 Zang 문자를 지원 합니다.

<div>

## <a name="enabling-users"></a>사용자 설정

응답 그룹을 구성 하는 첫 번째 단계는 에이전트 그룹을 만드는 것입니다. 에이전트 그룹을 만들려면 먼저 Lync Server 2013 및 Enterprise Voice에 대 한 응답 그룹의 에이전트로 사용할 사용자를 사용 하도록 설정 해야 합니다. Lync Server 2013에 대 한 사용자 사용은 일반적으로 Enterprise Edition server 또는 Standard Edition server 배포의 단계입니다. Lync Server 2013 사용자를 사용 하는 방법에 대 한 자세한 내용은 [Lync server 2013에 대 한 사용자 계정 비활성화 또는 다시 사용](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)을 참조 하세요. 엔터프라이즈 음성에 대 한 사용자 사용은 일반적으로 엔터프라이즈 음성 배포의 단계입니다. 자세한 내용은 [Lync Server 2013에서 엔터프라이즈 음성 사용자 사용](lync-server-2013-enable-users-for-enterprise-voice.md)을 참조 하세요.

</div>

<div>

## <a name="complying-with-fips-requirements"></a>FIPS 요구 사항 준수

이 섹션은 조직이 FIPS (정보 처리 표준)를 준수 해야 하는 경우에만 적용 됩니다.

FIPS를 준수 하려면 웹 서비스를 설치한 후 다른 암호화 알고리즘을 사용 하도록 응용 프로그램 수준 Web.config 파일을 수정 해야 합니다. ASP.NET에서 3DES (삼중 데이터 암호화 표준) 알고리즘을 사용 하 여 뷰 상태 데이터를 처리 하도록 지정 해야 합니다. 응답 그룹 응용 프로그램의 경우이 요구 사항은 응답 그룹 구성 도구와 에이전트 로그인 및 로그 아웃 콘솔에 적용 됩니다. 이 요구 사항에 대 한 자세한 내용은 Microsoft 기술 자료 문서 911722, "ASP.NET 1.1에서 ASP.NET 2.0으로 업그레이드 한 후 ViewState가 설정 된 ASP.NET 웹 페이지에 액세스할 때 오류 메시지가 표시 될 수 있습니다 [http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183)."를 참조 하세요.

Web.config 파일을 수정 하려면 다음을 수행 합니다.

1.  메모장과 같은 텍스트 편집기에서 응용 프로그램 수준 Web.config 파일을 엽니다.

2.  Web.config 파일에서 `<system.web>` 섹션을 찾습니다.

3.  `<system.web>` 섹션에 다음 `<machineKey>` 섹션을 추가 합니다.
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  Web.config 파일을 저장 합니다.

5.  명령 프롬프트에서 다음 명령을 실행 하 여 IIS (인터넷 정보 서비스) 서비스를 다시 시작 합니다.
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a>Yi, Meng 및 Zang 문자 지원

이 섹션은 조직에서 Yi, Meng 또는 Zang 문자를 지원 해야 하는 경우에만 적용 됩니다.

<div>


> [!NOTE]  
> Yi, Meng 및 Zang 문자에 대 한 정보와 배포에 중요할 수 있는 이유는 GB18030 문자 집합 <A href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</A>에 대 한 정보를 참조 하세요.



</div>

Yi, Meng 또는 Zang 문자를 지원 하려면 Rgsconfig 데이터베이스에 대 한 데이터 정렬을 수정 해야 합니다. 각 Rgsconfig 데이터베이스의 다음 테이블에서 **이름** 열의 데이터 정렬을 변경 합니다.

  - dbo. AgentGroups

  - dbo. BusinessHours

  - dbo. HolidaySets

  - dbo. 시키고

  - dbo. 과정

SQL Server 2008 R2 및 SQL Server 2012의 경우 라틴어\_일반\_100 (악센트 구분) 데이터 정렬을 사용 합니다. 이 데이터 정렬을 사용 하는 경우 모든 개체 이름은 대/소문자를 구분 하지 않습니다.

Microsoft SQL Server Management Studio를 사용 하 여 데이터 정렬을 변경할 수 있습니다. 이 도구를 사용 하는 방법에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184)"SQL Server Management Studio 사용"을 참조 하세요. 데이터 정렬을 변경 하려면 다음 단계를 따르세요.

1.  테이블을 다시 만들어야 하는 변경 내용을 허용 하도록 SQL Server Management Studio가 구성 되어 있는지 확인 합니다. 자세한 내용은의 "저장 (허용 되지 않음) 대화 상자"를 [http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186)참조 하세요. 열 데이터 정렬을 설정 하는 방법에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185)"방법: 열 데이터 정렬 설정 (Visual Database Tools)"을 참조 하세요.

2.  Microsoft SQL Server Management Studio를 사용 하 여 Rgsconfig 데이터베이스에 연결 합니다.

3.  Rgsconfig 데이터베이스에서 변경할 테이블을 찾고 테이블을 마우스 오른쪽 단추로 클릭 한 다음 **디자인**을 클릭 합니다.

4.  **이름** 열의 데이터 정렬을 변경 하 고 테이블을 저장 합니다.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


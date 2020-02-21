---
title: 'Lync Server 2013: 응답 그룹 구성 권한 및 필수 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8e27d3495ce2152dee67a5f176c4a0d9f7e7f82
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182970"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a>Lync Server 2013의 응답 그룹 구성 권한 및 필수 구성 요소

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-05_

응답 그룹은 Enterprise Voice 통화 관리 기능입니다. 이 항목에서는 응답 그룹을 구성하기 전에 필요한 항목과 구성 작업을 수행하는 데 필요한 관리 자격 증명 및 권한에 대해 설명합니다.

이 섹션에서는 응답 그룹과 관련된 계획 설명서를 읽은 것으로 간주합니다. 자세한 내용은 계획 설명서에서 [Lync Server 2013의 통화 관리 기능 계획](lync-server-2013-planning-for-call-management-features.md) 을 참조 하십시오.

<div>

## <a name="configuration-tools-and-administrative-roles"></a>구성 도구 및 관리 역할

다음 관리 도구를 사용하여 응답 그룹을 구성할 수 있습니다.

  - Lync Server 제어판

  - 응답 그룹 구성 도구

  - Communications Server 관리 셸

응답 그룹을 구성하려면 다음 관리 역할 중 하나 이상의 구성원이어야 합니다.


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
<td><p><strong>Active Directory 보안 그룹(1)</strong></p></td>
<td><p>워크플로 만들기</p></td>
<td><p>관리자 지정</p></td>
<td><p>에이전트, 큐 만들기/지정</p></td>
<td><p>휴일 및 업무 시간 만들기/관리</p></td>
<td><p>워크플로 활성화/비활성화</p></td>
<td><p>워크플로 구성(IVR 또는 헌트 그룹)</p></td>
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
<td><p><strong>CsViewOnlyAdministrator</strong></p></td>
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
> <STRONG>(1)</STRONG> Active Directory 도메인 서비스 사용자 개체가 나열 된 active directory 보안 그룹의 구성원 이어야 합니다. 보안 그룹에 사용자를 추가할 수 있는 적절 한 사용 권한이 있는 관리자 또는 기타 위임 된 Active Directory 그룹 구성원 (예: 관리자, 계정 운영자)은 나열 된 보안 그룹 또는 그룹에 사용자 개체를 추가 해야 사용자가 나열 된 함수를 수행 합니다. <STRONG>(2)</STRONG> CsResponseGroupAdministrator가 Csresponsegroupadministrator에 할당 한 워크플로에만 해당 됩니다. <STRONG>(3)</STRONG> 응답 그룹 관리자는 CsResponseGroupManager의 다른 구성원에 게 현재 관리자가 이미 관리 하는 워크플로에 할당할 수 있습니다. <STRONG>(4)</STRONG> csviewonly 관리자는 동사 "Get" Lync Server 관리 셸 cmdlet만 실행할 수 있습니다.



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a>응답 그룹 구성 도구 필수 구성 요소

응답 그룹에는 다음 구성 요소가 필요합니다.

  - 응용 프로그램 서비스

  - 응답 그룹 응용 프로그램

  - 언어 팩

  - 파일 저장소(오디오 파일 유지용)

  - 웹 서비스 (응답 그룹 구성 도구 및 에이전트의 로그인 및 로그 아웃 콘솔 포함)

이러한 구성 요소는 모두 Enterprise Voice를 배포할 때 기본적으로 설치됩니다.

응답 그룹을 구성 하기 전에 다음 작업을 수행 해야 할 수 있습니다.

  - 사용자가 Lync Server 2013 및 Enterprise Voice를 사용 하도록 설정 합니다.

  - FIPS(Federal Information Processing Standards)를 준수하도록 구성 파일 수정

  - 큐 이름 및 에이전트 그룹 이름에 Yi, Meng 및 Zang 문자를 지원하도록 데이터베이스 데이터 정렬 수정

<div>

## <a name="enabling-users"></a>사용자 설정

응답 그룹을 구성 하는 첫 번째 단계는 에이전트 그룹을 만드는 것입니다. 에이전트 그룹을 만들려면 Lync Server 2013 및 Enterprise Voice에 대 한 응답 그룹의 에이전트로 사용할 사용자를 설정 해야 합니다. Lync Server 2013에 대해 사용자를 사용 하도록 설정 하는 것은 일반적으로 Enterprise Edition server 또는 Standard Edition server 배포의 단계입니다. Lync Server 2013에 대해 사용자를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 [Disable or enable user account For Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)을 참조 하십시오. 사용자가 Enterprise Voice를 사용할 수 있도록 설정하는 것은 일반적으로 Enterprise Voice 배포 단계에 속합니다. 자세한 내용은 [Lync Server 2013에서 사용자에 게 Enterprise Voice 사용을 설정](lync-server-2013-enable-users-for-enterprise-voice.md)하는 기능을 참조 하십시오.

</div>

<div>

## <a name="complying-with-fips-requirements"></a>FIPS 요구 사항 준수

이 섹션은 조직에서 FIPS(Federal Information Processing Standards)를 준수해야 하는 경우에만 적용됩니다.

FIPS를 준수하려면 웹 서비스를 설치한 후 다른 암호화 알고리즘을 사용하도록 응용 프로그램 수준 Web.config 파일을 수정해야 합니다. ASP.NET에서 3DES(Triple Data Encryption Standard) 알고리즘을 사용하여 보기 상태 데이터를 처리하도록 지정해야 합니다. 응답 그룹 응용 프로그램의 경우에는 응답 그룹 구성 도구와 에이전트 로그인 및 로그 아웃 콘솔에이 요구 사항이 적용 됩니다. 이 요구 사항에 대 한 자세한 내용은 Microsoft 기술 자료 문서 911722, "ViewState를 사용 하도록 설정 된 ASP.NET 웹 페이지에 액세스할 때 오류 메시지가 표시 될 수 있습니다." (여기서 [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkid=196183)는 ASP.NET 1.1에서 ASP.NET 2.0로 업그레이드)를 참조 하십시오.

Web.config 파일을 수정하려면 다음을 수행합니다.

1.  메모장과 같은 텍스트 편집에서 응용 프로그램 수준 Web.config 파일을 엽니다.

2.  Web.config 파일에서 `<system.web>` 섹션을 찾습니다.

3.  `<system.web>` 섹션에 다음 `<machineKey>` 섹션을 추가 합니다.
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  Web.config 파일을 저장합니다.

5.  명령 프롬프트에서 다음 명령을 실행 하 여 IIS (인터넷 정보 서비스) 서비스를 다시 시작 합니다.
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a>Yi, Meng 및 Zang 문자 지원

이 섹션은 조직에서 Yi, Meng 또는 Zang 문자를 지원해야 하는 경우에만 적용됩니다.

<div>


> [!NOTE]  
> Yi, Meng 및 Zang 문자에 대해 설명 하 고 배포에 중요 한 이유를 확인 하려면 GB18030 문자 집합 <A href="https://go.microsoft.com/fwlink/p/?linkid=240223">https://go.microsoft.com/fwlink/p/?linkId=240223</A>에 대 한 정보를 참조 하세요.



</div>

Yi, Meng 또는 Zang 문자를 지원하려면 Rgsconfig 데이터베이스에 대한 데이터 정렬을 수정해야 합니다. 각 Rgsconfig 데이터베이스의 다음 테이블에서 **이름** 열의 데이터 정렬을 변경합니다.

  - dbo. AgentGroups

  - dbo. Microsoft.rtc.rgs.management.writablesettings.businesshours

  - dbo. HolidaySets

  - dbo. 쿼리

  - dbo. 워크플로

SQL Server 2008 R2 및 SQL Server 2012의 경우 라틴어\_일반\_100 (악센트 구분) 데이터 정렬을 사용 합니다. 이 데이터 정렬을 사용하는 경우 모든 개체 이름이 대/소문자를 구분하지 않습니다.

Microsoft SQL Server Management Studio를 사용하여 데이터 정렬을 변경할 수 있습니다. 이 도구를 사용 하는 방법에 대 한 자세한 내용은에서 [https://go.microsoft.com/fwlink/p/?linkId=196184](https://go.microsoft.com/fwlink/p/?linkid=196184)"SQL Server Management Studio 사용"을 참조 하십시오. 다음 단계에 따라 데이터 정렬을 변경합니다.

1.  테이블을 다시 만들어야 하는 변경 작업을 허용하도록 SQL Server Management Studio가 구성되었는지 확인합니다. 자세한 내용은의 "저장 (허용 안 됨) 대화 상자"를 [https://go.microsoft.com/fwlink/p/?linkId=196186](https://go.microsoft.com/fwlink/p/?linkid=196186)참조 하십시오. 열 데이터 정렬 설정에 대 한 자세한 내용은에서 [https://go.microsoft.com/fwlink/p/?linkId=196185](https://go.microsoft.com/fwlink/p/?linkid=196185)"방법: 열 데이터 정렬 설정 (비주얼 데이터베이스 도구)"을 참조 하십시오.

2.  Microsoft SQL Server Management Studio를 사용하여 Rgsconfig 데이터베이스에 연결합니다.

3.  Rgsconfig 데이터베이스에서 변경할 테이블을 찾아서 마우스 오른쪽 단추로 클릭한 다음 **디자인**을 클릭합니다.

4.  **이름** 열의 데이터 정렬을 변경하고 테이블을 저장합니다.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


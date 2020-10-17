---
title: 'Lync Server 2013: Lync 클라이언트에서 2 단계 인증 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using two-factor authentication with Lync client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn338071(v=OCS.15)
ms:contentKeyID: 55115593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a90dd3c40267f0994e7f41eabb689c869182cea7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508645"
---
# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a>Lync 클라이언트 및 Lync Server 2013에서 2 단계 인증 사용

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-07-11_

이 항목에서는 Lync 2013 클라이언트에서 2 단계 인증을 활용 하는 방법에 대해 설명 했습니다.

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a>처음으로 Lync 2013에 로그인 합니다.

Lync 로그인 정보는 대개 Lync 2013이 설치 될 때 자동으로 구성 됩니다. 하지만 Lync를 처음 사용 하는 경우에는 클라이언트를 수동으로 시작 해야 할 수도 있습니다.

**처음으로 Lync에 로그인 하려면**

1.  조직의 네트워크에 로그온 합니다.

2.  **Start** \> **모든 프로그램** 시작 \> **Microsoft Lync \> Lync 2013**을 선택 합니다.
    
    Lync 로그인 화면이 표시 됩니다.
    
      - 로그인 주소 상자에 이미 입력 되어 있는 경우 표시 된 주소가 올바른지 확인 합니다.
    
      - 올바르지 않거나 상자가 비어 있으면 Lync 로그인 주소 (일반적으로 사용자의 전자 메일 주소와 같음)를 입력 합니다.
    
      - 빈 암호 상자가 표시 되 면 암호를 추가 합니다.

3.  **로그인**을 선택 합니다.

</div>

<div>

## <a name="sign-out-of-lync"></a>Lync에서 로그 아웃

Lync 사용을 마친 후에는 파일 메뉴에서 디스플레이를 닫거나, 세션을 로그 아웃 하거나, 프로그램을 끝낼 수 있습니다. 다음 표에서는 옵션의 차이점에 대해 설명 합니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>옵션</th>
<th>속성 기능</th>
<th>수행 방법</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>닫지</p></td>
<td><p>Lync 화면을 닫지만 사용자 ID로 식별 된 Lync 세션을 계속 실행할 수 있습니다. 따라서 계속 해 서 알림을 받고 다른 사람들과 상호 작용할 수 있습니다.</p>
<p>작업 표시줄의 Lync 아이콘 또는 화면 아래쪽에 있는 알림 영역을 클릭 하 여 언제 든 지 다시 표시할 수 있습니다.</p></td>
<td><p>Lync 주 창에서 다음 중 하나를 수행 합니다.</p>
<ol>
<li><p><strong>옵션</strong> 단추를 선택한 다음 <strong>파일</strong> &gt; <strong>닫기를</strong>선택 합니다.</p></li>
<li><p>창의 오른쪽 위 모서리에 있는 <strong>닫기</strong> 단추 (X)를 클릭 합니다.</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p>로그 아웃</p></td>
<td><p>사용자 ID와 연결 된 Lync 세션을 종료 하지만 Lync는 백그라운드에서 계속 실행 됩니다. 로그 아웃 하면 로그인 창이 표시 됩니다.</p>
<div>

> [!TIP]  
> 컴퓨터에서 로그온 ID 및 암호 기록을 제거 하려면 로그 아웃할 때 <STRONG>내 로그인 정보 삭제</STRONG> 를 선택 합니다. 이렇게 하면 사용자가 로그인 문제를 보다 쉽게 해결할 수 있습니다. 또한 인증 되지 않은 사용자가 자격 증명을 사용 하 여 로그온 하는 것을 어렵게 하 여 로그인 정보를 보다 안전 하 게 유지 하는 데 도움이 될 수 있습니다.


</div></td>
<td><p>Lync 주 창에서 <strong>옵션</strong> 단추를 선택한 다음 <strong>파일</strong> &gt; <strong>로그 아웃</strong>을 선택 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>마침</p></td>
<td><p>Lync 세션을 종료 하 고 컴퓨터에서 Lync를 종료 합니다. 종료 후 Lync를 다시 시작 하려면 <strong>Start</strong> &gt; <strong>All Programs</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>모든 프로그램 시작을 선택 합니다.</p></td>
<td><p>Lync 주 창에서 <strong>옵션</strong> 단추를 선택 하 고 <strong>파일</strong> &gt; <strong>종료</strong>를 선택 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a>스마트 카드를 사용 하 여 Lync에 로그인

일부 조직에서는 이제 2 단계 인증 이라는 다단계 로그인 프로세스를 사용 하 여 Lync 2013 사용자의 보안을 강화 합니다. 이 옵션을 사용할 것으로 예상 되 면 Lync에 로그인 하기 위한 "스마트 카드"가 필요 합니다. 스마트 카드는 실제 및 가상의 두 가지 형태로 제공 됩니다.

  - **실제**     신용 카드의 크기 정보 로그인 할 때 스마트 카드 판독기에 삽입 합니다.

  - **가상**     실제 개체는 아니지만 컴퓨터의 특수 칩에 기록 되는 전자 식별자 이며, 기본적으로 컴퓨터에 스마트 카드를 작성 합니다. TPM (신뢰할 수 있는 플랫폼 모듈) 칩이 포함 된 Windows 8 컴퓨터 에서만 사용할 수 있습니다.

<div>

## <a name="enroll-your-smart-card"></a>스마트 카드 등록

스마트 카드를 사용 하 여 로그인 하려면 카드를 "등록" 해야 하며, 즉 사용자 자격 증명을 해당 카드와 함께 식별할 수 있어야 합니다. 이는 명함이 실제 또는 가상 인지 여부입니다. 이 프로세스는 Lync Server 관리자가 이미 수행 했을 수 있습니다. 완료 되었는지 여부를 확인 하지 않은 경우 해당 내용을 확인 하세요.

<div>


> [!NOTE]  
> 각 가상 스마트 카드는 설치 된 장치에만 연결 되므로 사용 하는 각 Windows 8 컴퓨터에 대해 별도의 카드를 등록 해야 합니다.



</div>

**스마트 카드를 수동으로 등록 하려면**

1.  Lync를 실행할 컴퓨터에 로그온 합니다.

2.  Internet Explorer를 사용 하 여 조직의 인증 기관 웹 등록 페이지로 이동 합니다.
    
    이 리소스가 없으면 Lync Server 관리자에 게 해당 리소스의 웹 주소를 문의 하세요. URL은 https://MyCA.\ [이란 companyname \] . .com/certsrv와 같이 표시 됩니다.
    
    <div>
    

    > [!NOTE]  
    > Internet Explorer 10을 사용 중인 경우 호환 모드에서이 웹 사이트를 확인 해야 할 수 있습니다.

    
    </div>

3.  인증 페이지에 로그온 하 라는 메시지가 표시 되 면 사용자 컴퓨터의 관리자가 아닌 도메인 계정을 사용 하 여 로그온 합니다.

4.  웹 사이트 시작 페이지에서 **인증서 요청**을 선택 합니다.

5.  **고급 요청**을 선택 합니다.

6.  **이 CA에 요청 만들기 및 제출을**선택 하 고 **다음**을 클릭 합니다.

7.  이제 스마트 카드 등록 스테이션 이라는 페이지가 표시 됩니다. ActiveX 컨트롤 설치 요청을 승인 하 고 다음과 같이 고급 인증서 요청 양식을 완료 합니다.
    
    1.  **인증서 템플릿** 드롭다운 목록에서 **스마트 카드 사용자** 를 선택 합니다.
    
    2.  **새 키 집합 만들기**를 선택 합니다.
    
    3.  스마트 카드 레이블에서 제조업체 정보를 확인 하 고 **CSP** 드롭다운 목록에서 해당 제조업체를 선택 합니다.
    
    4.  요청 형식이 아직 선택 되지 않은 경우 **CSP** 를 선택 합니다.
    
    5.  해시 알고리즘 드롭다운 목록에서 **sha1** 을 선택 합니다 (아직 선택 되어 있지 않은 경우).
    
    6.  사용자에 게 인식할 수 있는 이름을 인증서에 제공 하 고 **제출을**클릭 합니다.

8.  이제 등록 스테이션에 연결 된 카드 판독기에 빈 스마트 카드를 삽입 하 고 **등록**을 클릭 합니다.

9.  메시지가 표시 되 면 PIN (개인 id 번호)을 입력 하 고 **확인**을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 기술 지원 담당자가 스마트 카드를 등록 하는 데 사용할 특수 PIN을 제공 하지 않은 경우 기본 스마트 카드 PIN 값 (12345678)을 사용 합니다.

    
    </div>

10. 사용자가 스마트 카드를 처음 사용할 때 PIN을 강제로 변경 하도록 하려면이 옵션을 선택 합니다.

11. 이제 등록 스테이션에 연결 된 카드 판독기에 빈 스마트 카드를 삽입 하 고 **등록**을 클릭 합니다.

12. 메시지가 표시 되 면 PIN (개인 id 번호)을 입력 하 고 **확인**을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 기술 지원 담당자가 스마트 카드를 등록 하는 데 사용할 특수 PIN을 제공 하지 않은 경우 기본 스마트 카드 PIN 값 (12345678)을 사용 합니다.

    
    </div>

13. 사용자가 스마트 카드를 처음 사용할 때 PIN을 강제로 변경 하도록 하려면이 옵션을 선택 합니다.

14. **확인** 을 클릭 하 여 표시 된 인증서에 정보가 있는지 확인 합니다.

15. 인증서가 발급 되었음을 알리는 메시지가 표시 되 면 **이 인증서 설치** 를 클릭 하 여 등록 프로세스를 완료 합니다.

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a>스마트 카드 자격 증명을 사용 하 여 Lync에 로그인

스마트 카드를 처음 사용 하기 전에 Lync 로그인 페이지에서 **내 로그인 정보 삭제** 를 클릭 하는 것이 좋습니다. 이렇게 하면 컴퓨터에 저장 된 모든 로그인 자격 증명이 지워지고 오류가 발생할 수 있는 원인이 제거 됩니다.

**스마트 카드 자격 증명을 사용 하 여 Lync에 로그인 하려면**

1.  Lync 클라이언트를 시작 합니다.

2.  로그인 화면에서 **로그인 주소** 상자에 로그인 사용자 계정 이름을 입력 하 고 **로그인**을 클릭 합니다.

3.  가상 스마트 카드를 사용 하는 경우에는이 단계를 건너뜁니다.
    
    실제 스마트 카드를 사용 하는 경우 스마트 카드 판독기에 스마트 카드를 삽입 하 고, 카드를 넣으라는 메시지가 표시 되 면 **확인** 을 클릭 합니다.

4.  PIN 번호를 스마트 카드에 입력 하 고 **확인**을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 지원 담당자가 스마트 카드 PIN 번호를 할당 하지 않은 경우 기본값 (12345678)을 사용 합니다.

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


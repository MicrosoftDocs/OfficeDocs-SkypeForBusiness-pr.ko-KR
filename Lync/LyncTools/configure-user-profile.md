---
title: 사용자 프로필 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c53f156aee56aa1986302bf2ff2514aef78af592
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-user-profile"></a>사용자 프로필 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2018-10-11_

Lync Server 2013 스트레스 및 성능 도구 패키지에 포함 된 도구를 사용 하 여 부하 시뮬레이션을 실행 하는 데 사용할 수 있는 테스트 사용자 계정을 만들고 구성 합니다. Lync Server 2013 사용자 만들기 도구를 사용 하 여 사용자를 만듭니다. 자세한 내용은 [Create Users And Contacts](create-users-and-contacts.md)를 참조 하십시오. 사용자를 만든 후 Lync Server 2013 부하 구성 도구를 사용 하 여 사용자 프로필을 구성 합니다.

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a>Lync Server 2013 Load 구성 도구 실행

사용자 프로필을 구성 하려면 Lync Server 2013 부하 구성 도구 (Userprofilegenerator.exe 공용)를 실행 하 고 각 탭을 입력 합니다. Userprofilegenerator.exe 공용는 시뮬레이션을 실행 하는 데 필요한 각 클라이언트 컴퓨터에 대 한 디렉터리를 생성 합니다. 각 클라이언트 디렉터리에는 Lync Server 2013 스트레스 및 성능 도구 (LyncPerfTool)의 모든 인스턴스를 시작 하는 스크립트도 함께 제공 됩니다.

<div>


> [!IMPORTANT]  
> Userprofilegenerator.exe 공용에 지정 된 사용자 관련 값은 풀에 대 한 Lync Server 2013 사용자 만들기 도구 (UserProvisioningTool)에 지정 된 값과 일치 해야 합니다.



</div>

다음 섹션에서 설명 하는 대로 Lync Server 2013 부하 구성 도구의 각 탭에 있는 필드를 채웁니다.

<div>

## <a name="common-configuration"></a>일반 구성

Lync Server 2013 부하 구성 도구의 **일반 구성** 탭이 다음 그림에 나와 있습니다. 다음 단계에 설명 된 대로 **일반 구성** 탭의 필드에 내용을 입력 합니다.

![일반 구성 탭](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "일반 구성 탭")

1.  **사용 가능한 컴퓨터 수**에서 LyncPerfTool를 실행 하는 데 사용할 컴퓨터 수를 입력 하거나 클릭 합니다. 시뮬레이션할 모든 4500 사용자에 대해 컴퓨터 한 대를 보유 하는 것이 좋습니다. 이 숫자는 부하 수준을 줄이거나 사용 가능한 기능의 하위 집합만 사용 하는 경우에 다를 수 있습니다. (부하 수준은 **일반 시나리오** 탭에서 설정 됩니다.)

2.  **사용자 이름의 접두사**에 사용자의 사용자 이름에 대 한 접두사를 입력 합니다. 로그인 하려면 URI (Uniform Resource Identifier)가 UserPrefix\[사용자 시작 인덱스입니다. (사용자 수-1) \]@User 도메인

3.  **모든 사용자의 암호**에 사용자를 만드는 데 사용 된 암호를 입력 합니다. 이 필드를 비워 두면 사용자 이름이 암호로 사용 됩니다.

4.  **사용자 시작 인덱스**에서 구성할 첫 번째 사용자의 인덱스를 클릭 하거나 입력 합니다. 각 유형이 나 부하 수준에 대해 서로 다른 범위를 구성할 수 있지만, 구성 하려는 범위에 따라 Userprofilegenerator.exe 공용를 한 번 실행 해야 합니다.

5.  **사용자 수**에서 구성할 총 사용자 수를 클릭 하거나 입력 합니다.

6.  **사용자 도메인**에서 SIP URI에 사용 되는 도메인을 입력 합니다. 이는 Lync Server 2013 프런트 엔드 서버 또는 Standard Edition 서버에 로그온 하는 각 사용자의 SIP URI를 구성 하는 데 사용 됩니다. 이 도메인은 계정 도메인과 다를 수 있습니다.

7.  **계정 도메인**에 Active Directory 도메인 서비스 도메인 로그온을 입력 합니다.

8.  도구가 모든 끝점/사용자에 게 로그인 할 최대 동시 끝점 수 **(인스턴스당)** 를 입력 합니다. 권장 속도는 초당 \<= 2/STANDARD SKU FE입니다.

9.  **액세스 프록시 또는 풀 FQDN**에 클라이언트와 연결 하려는 서버의 FQDN (정규화 된 도메인 이름)을 입력 합니다. 사용자가 외부에서 로그온 하는 경우 액세스 프록시를 지정 합니다. 내부 사용자 인 경우 해당 풀 또는 Standard Edition 서버의 FQDN을 지정 합니다.

10. **포트**에서 사용자가 SIP에 사용 하도록 할 포트를 클릭 하거나 입력 합니다 (기본값: 5061).

외부 네트워크 서버 설정에 대해 **액세스 프록시 또는 풀 FQDN** 및 **포트**를 지정 합니다. 이러한 설정은 외부 끝점 부하 시뮬레이션에만 사용 됩니다.

</div>

<div>

## <a name="general-scenarios"></a>일반 시나리오

Lync Server 2013 부하 구성 도구의 **일반 시나리오** 탭은 다음 그림에 나와 있습니다.

실행 하려는 일반 시나리오 각각에 대해 부하 수준 및 매개 변수를 구성 하거나 사용 하지 않도록 설정 된 상태로 두세요.

![일반 시나리오 탭](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "일반 시나리오 탭")

1.  피어 투 피어 및 회의를 포함 하는 **인스턴트 메시징**에서 부하 수준에 적절 한 값을 지정 합니다.
    
    <div>
    

    > [!NOTE]  
    > 위치 정보 서비스를 제외한 모든 필드에 대 한 부하 수준 값은 <STRONG>사용 안 함</STRONG>, <STRONG>낮음</STRONG>, <STRONG>중간</STRONG>, <STRONG>높음</STRONG>, <STRONG>사용자 지정</STRONG>입니다. 낮음, 중간, 높음 또는 사용자 지정을 선택 하면 각 모달 및 클라이언트에 대 한 구성이 생성 됩니다. 높은 경우 서버에 대해 지원 되는 최대 부하가 생성 되 고, 중간 크기는 부하의 60%에 해당 하며, 낮은 부하의 30%에 해당 합니다.

    
    </div>

2.  오디오 **회의 에서만**가능 하며 부하 수준에 적절 한 값을 지정 합니다. 피어 투 피어 통화에 대해서는이 항목의 뒷부분에 나오는 Voice 시나리오 섹션에서 설명 합니다. 멀티뷰를 사용 하도록 설정 하려면 해당 형식에 대 한 **고급** 탭을 엽니다.

3.  **응용 프로그램 공유**에서 부하 수준에 적절 한 값을 지정 합니다.

4.  데이터 회의를 포함 하는 **데이터 공동 작업**에서 부하 수준에 적절 한 값을 지정 합니다.

5.  **메일 그룹 확장**에서 부하 수준에 적절 한 값을 지정 합니다. 또한 **고급** 단추를 클릭 한 다음 Lync Server 사용자 만들기 도구 (UserProvisioningTool)의 **메일 그룹** 탭에서 구성한 값과 동일한 필드를 입력 해야 합니다. 이러한 필드에 대 한 자세한 내용은 [Create Users And Contacts](create-users-and-contacts.md) 를 참조 하십시오.

6.  주소록 **웹 쿼리**(주소록이 파일을 다운로드 하는 것이 아님)에서 로드 수준에 적절 한 값을 지정 합니다. 주소록 다운로드를 사용 하도록 설정 하려면 해당 하는 **고급** 단추를 클릭 한 다음 **EnableABSDownload** 를 true로 설정 합니다.

7.  **응답 그룹 서비스**에서 부하 수준에 적절 한 값을 지정 합니다. 또한 해당 하는 **고급** 단추를 클릭 한 다음 응답 그룹 서비스 에이전트를 프로 비전 할 때 이미 만든 응답 그룹의 uri를 지정 해야 합니다. 하나 이상의 응답 그룹을 지정 해야 합니다. 세미콜론을 사용 하 여 여러 응답 그룹을 구분 합니다. 실제 값으로 RGSUriSuffixStartIndex 및 RGSUriSuffixEndIndex를 업데이트 합니다.

8.  **위치 정보 서비스**에서 부하 수준에 적합 한 값을 선택 합니다. 위치 정보 서비스에 대 한 부하 수준을 **사용** 하거나 **사용 하지 않도록**설정 해야 합니다.

<div>


> [!NOTE]  
> 각 시나리오에는 그 옆에 <STRONG>고급</STRONG> 단추가 있으며, 시나리오 변형을 가능 하 게 하는 확인란 집합을 포함 합니다. <STRONG>Ad-hoc은</STRONG> 한 시간 동안 생성 되는 회의 시뮬레이션을 생성 하는 것을 의미 합니다. <STRONG>큰</STRONG> 컨퍼런스는 대규모 회의 시나리오가 시뮬레이션 됨을 의미 합니다. <STRONG>외부</STRONG> 를 통해 외부 사용자를 시뮬레이션할 수도 있습니다.<BR>이러한 단추 및 확인란을 사용 하면 Lync Server 2013 스트레스 및 성능 도구 (LyncPerfTool)의 동작을 변경 하 고 사용자 지정할 수 있도록 하는 각 시나리오와 관련 된 값에 액세스할 수 있습니다. <STRONG>일반 시나리오</STRONG> 탭 (위치 정보 서비스 제외)의 각 시나리오에서는 부하 수준 값이 <STRONG>Custom</STRONG>인 경우 <STRONG>고급</STRONG> 대화 상자의 해당 필드를 사용 하 여 대화 속도를 계산 합니다. 필드 이름은 시나리오에 따라 다르지만 필드 설명에는 "참고:이 번호는 드롭다운 메뉴에서 사용자 지정을 선택한 경우에만 사용 됩니다." 일반적으로 <STRONG>High</STRONG>, <STRONG>Medium</STRONG>, <STRONG>Low</STRONG> 값은 모든 시나리오의 잔고에 해당 하는 사용자 모델을 기준으로 하 여 각 줄에 대 한 대화 속도를 변경 합니다. 예상 사용량의 차이로 인해 모달 형식으로 로드 수준을 변경 해야 하는 경우에는 <STRONG>사용자 지정</STRONG> 대화 비율을 사용 하는 것이 좋습니다.<BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a>음성 시나리오

Lync Server 2013 부하 구성 도구의 **음성 시나리오** 탭이 다음 그림에 나와 있습니다.

음성 **시나리오** 탭을 사용 하 여 모든 음성 관련 시나리오를 구성 합니다.

![음성 시나리오 탭](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "음성 시나리오 탭")

1.  **VoIP**에서 **고급** 단추를 클릭 한 다음 **PhoneAreaCode** 및 **locationprofile** (다이얼 플랜) 필드에 대 한 값을 입력 합니다. 또한 **부하 수준**에 대 한 값을 지정 해야 합니다. **VoIP** 및 **Uc/PSTN 게이트웨이에** 대 한 로드 수준이 사용 하도록 설정 된 경우 외부 통화를 시뮬레이트하기 위한 공중 전화망 (uc) 구성 파일에 대 한 공공 전화망 (PSTN)이 항상 생성 됩니다.

2.  **UC/PSTN 게이트웨이에서**부하 수준 값을 지정 합니다. **사용 안 함**이외의 부하 수준을 선택한 경우에는 중재 서버 및 PSTN에서 **추가** 단추를 클릭 하 여 **pstn 지역 번호** 값을 제공 해야 합니다. 해당 지역 번호에 대해 경로가 구성 되어 있는지 확인 합니다.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 제어판 또는 Lync Server 관리 셸을 사용 하 여 음성 경로 구성을 확인할 수 있습니다.

    
    </div>

3.  **회의 전화 교환**에서 부하 수준에 대 한 값을 지정 합니다. **사용 하지 않도록 설정**된 부하를 제외 하 고 로드 수준을 선택 하면 **전화 번호** 필드가 사용 됩니다. 사용할 자동 전화 교환의 전화 번호를 입력 합니다. 또한 **고급** 단추를 클릭 한 다음 **locationprofile** 필드에 대 한 값을 지정 합니다.

4.  **통화 대기 서비스**에서 **부하 수준**에 적합 한 값을 지정 합니다.

5.  **중재 서버 및 PSTN**에서 사용 하려는 각 중재 서버에 대해 별도의 PSTN 시뮬레이터가 있어야 합니다. 시뮬레이터로 사용할 클라이언트를 결정 한 후에는 사용자가 구성한 PSTN 시뮬레이터 포트에서 해당 컴퓨터로 통화를 라우팅하도록 중재 서버를 구성 해야 합니다. **추가** 를 클릭 하 여 중재 서버의 값을 구성 합니다.

<div>


> [!NOTE]  
> 각 시나리오에는 그 옆에 <STRONG>고급</STRONG> 단추가 있습니다. 이러한 단추를 사용 하 여 Lync Server 2013 스트레스 및 성능 도구 (LyncPerfTool)의 동작을 변경 하 고 사용자 지정 기능을 설정 하는 각 시나리오와 관련 된 값에 액세스할 수 있습니다. <STRONG>음성 시나리오</STRONG> 탭의 각 시나리오에서 <STRONG>부하 수준</STRONG> 값이 <STRONG>Custom</STRONG>이면 <STRONG>Advanced (고급</STRONG> ) 대화 상자에서 해당 하는 필드를 사용 하 여 대화 속도를 계산 합니다. 필드 이름은 시나리오에 따라 다르지만 필드 설명에는 "참고:이 번호는 드롭다운 메뉴에서 사용자 지정을 선택한 경우에만 사용 됩니다."



</div>

</div>

<div>

## <a name="reach"></a>지원함

은 프런트 엔드 서버에 설치 된 통합 커뮤니케이션 웹 API (WA) 서버를 통해 회의 시나리오를 지 원하는 Lync Server 2013의 새로운 환경입니다. Lync Server 2013 부하 구성 도구의 **Reach** 탭은 다음 그림에 나와 있습니다.

**Reach 탭을** 사용 하 여 모든 관련 시나리오를 구성 합니다.

![연결 탭](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "연결 탭")

1.  **일반 연결 설정**옆에 있는 **고급** 단추를 클릭 합니다. **UcwaTargetServerUrl** 필드를 디렉터 풀 vip (가상 IP) 또는 프런트 엔드 풀 vip로 설정 합니다.

2.  **응용 프로그램 공유**, **데이터 공동 작업**및 **IM**에서 **부하 수준**에 적합 한 값을 선택 합니다.

<div>


> [!NOTE]  
> 각 시나리오에는 그 옆에 <STRONG>고급</STRONG> 단추가 있습니다. 이러한 단추를 사용 하 여 Lync Server 2013 스트레스 및 성능 도구 (LyncPerfTool)의 동작을 변경 하 고 사용자 지정 기능을 설정 하는 각 시나리오와 관련 된 값에 액세스할 수 있습니다. 각 시나리오에서 <STRONG>로드 수준이</STRONG> <STRONG>Custom</STRONG>인 경우에는 <STRONG>ConversationsPerHour</STRONG> 필드에 지정 된 값이 기본값 대신 사용 됩니다.



</div>

**이동성 탭을** 사용 하 여 모든 모바일 관련 시나리오를 구성 합니다.

![모바일 기능 탭](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "모바일 기능 탭")

1.  **Mobility (DATWA)** 옆에 있는 **고급** 단추를 클릭 합니다. **UcwaTargetServerUrl** 필드를 디렉터 풀 vip (가상 IP) 또는 프런트 엔드 풀 vip로 설정 합니다.

2.  **현재 상태 및 P2P 인스턴트 메시징\\오디오**에서 **부하 수준** 에 대 한 적절 한 값을 선택 하 여 이동성 시나리오 시뮬레이션을 사용 하도록 설정 합니다.

<div>


> [!NOTE]  
> 각 시나리오에는 그 옆에 <STRONG>고급</STRONG> 단추가 있습니다. 이러한 단추를 사용 하 여 Lync Server 2013 스트레스 및 성능 도구 (LyncPerfTool)의 동작을 변경 하 고 사용자 지정 기능을 설정 하는 각 시나리오와 관련 된 값에 액세스할 수 있습니다. 각 시나리오에서 <STRONG>로드 수준이</STRONG> <STRONG>Custom</STRONG>인 경우에는 <STRONG>ConversationsPerHour</STRONG> 필드에 지정 된 값이 기본값 대신 사용 됩니다.



</div>

</div>

<div>

## <a name="summary"></a>요약

Lync Server 2013 Load 구성 도구의 **요약** 탭은 다음 그림에 나와 있습니다.

![요약 탭](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "요약 탭")

**요약** 탭에는 각 시나리오에 사용할 사용자가 표시 됩니다. 사용자 **지정 사용자 범위 생성 사용** 확인란을 선택한 후 사용자 지정 하려는 **사용자 범위가** 있는 테이블에서 시나리오를 두 번 클릭 하는 방법으로, 직접 번호 범위를 구성할 수 있습니다. 확인 (RunClient .bat) 시작 시 로그인 지연을 추가 하 여 생성 된 일괄 처리 파일에 로그인 속도를 포함 하는 지연 시간을 포함할 수 있습니다. 이 기능은 많은 사용자에 게 로그인 할 때 서버 오버 로드를 방지 하는 데 유용 합니다. **파일 생성**을 클릭 하 고 구성을 생성할 폴더를 선택 합니다. 파일을 성공적으로 만든 후에는 다음 그림과 같은 대화 상자가 나타납니다.

![파일이 생성 되었음을 승인 합니다.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "파일이 생성 되었음을 승인 합니다.")

</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[사용자 및 연락처 만들기](create-users-and-contacts.md)  
</div>
</div>
<span></span>
</div>
</div>
</div>

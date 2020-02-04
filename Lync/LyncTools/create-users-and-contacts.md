---
title: 사용자 및 연락처 만들기
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1463a7caaad2bcf36996eaac4bd47e2bab25e6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a>사용자 및 연락처 만들기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-22_

Lync Server 2013 사용자 프로비저닝 도구 (UserProvisioningTool)를 사용 하 여 스트레스 및 성능 부하 테스트를 준비 하는 데 필요한 사용자 및 연락처를 만들어야 합니다.

다음은이 항목을 읽어 볼 때 유용 하 게 사용할 수 있는 용어 및 정의 목록입니다.

  - 조직 구성 단위-Active Directory 도메인 서비스 OU (조직 구성 단위)입니다.

  - 페더레이션/교차도-인터넷 서비스의 MSN 네트워크, AOL®, Yahoo\!® 같은 다른 IM (인스턴트 메시징) 서비스의 사용자와 통신 하는 데 사용할 수 있는 사용자입니다.

  - 배포 목록 – 사용자 그룹과의 통신을 시작 하는 데 사용 되는 Active Directory 도메인 서비스 사용자 목록이 포함 된 Active Directory 도메인 서비스의 개체입니다.

  - 위치 정보 서비스 – 휴대폰에 대해 사용 하도록 설정 하 고 구성 하는 경우 향상 된 9-1-1 (E9-1) 서비스에 대 한 실제 위치를 검색할 수 있는 Lync Server 2013 서비스입니다.

  - 미국 전화 번호 – 인바운드 및 아웃 바운드 통화와 역방향 번호 조회 (RNL)를 라우팅하는 데 사용 되는 SIP URI 외에도 사용자에 게 할당 된 전화 번호입니다.

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>UserProvisioningTool를 사용 하 여 사용자 및 연락처 만들기

Lync Server 사용자 프로비저닝 도구를 사용 하 여 부하 시뮬레이션에 대 한 사용자 및 연락처를 만들어야 합니다. Lync server 사용자 프로비저닝 도구는 Lync Server 스트레스 및 성능 도구 패키지와 함께 설치 됩니다. 패키지 설치 관리자 (CapacityPlanningTool)가 프런트 엔드 서버 또는 Standard Edition 서버에서 실행 되었는지 확인 합니다. 프런트 엔드 서버 또는 Standard Edition Server에서 UserProvisioningTool (% InstalledDirectory% LyncStressAndPerfTool\\l c스트레스가에 위치)를 실행 하 여 Lync Server 사용자 제공 도구를 시작 합니다.

<div>


> [!IMPORTANT]  
> UserProvisioningTool를 실행 하려면 Domain Admins 보안 그룹의 구성원으로 로그온 해야 합니다. UserProvisioningTool가 새 Active Directory 도메인 서비스 사용자를 만들고 구성 하기 때문에이 컨텍스트에서 실행 해야 합니다.



</div>

<div>


> [!NOTE]  
> 많은 수의 사용자를 만드는 경우 (1만 이상), 고급 컴퓨터에서 UserProvisioningTool를 실행 합니다. 사용자를 만드는 동안에도 도메인 컨트롤러에 로드가 많이 발생 하는 것을 참고 하세요.



</div>

Lync Server 사용자 프로비저닝 도구가 열리면 **구성을** 클릭 하 고 **구성 로드**를 선택 합니다. 사용자 및 연락처 구성을 시작 하려면 패키지, SampleData에 포함 된 기본 파일을 로드 합니다. 이렇게 하면 시스템에서 수정 해야 하는 예제 데이터를 사용 하 여 필드를 미리 채울 수 있습니다. 이미 사용자 지정 설정을 포함 하는 미리 구성 된 XML 파일이 있으면 그 파일을 로드 합니다. 다음 섹션에서 설명 하는 대로 Lync Server 사용자 프로비저닝 도구에 필드를 입력 합니다.

![사용자 만들기 탭.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "사용자 만들기 탭.")

서버 옵션을 구성 하려면 다음 단계를 따릅니다.

1.  **프런트 엔드 풀 fqdn**에는 사용자를 호스트 하는 데 사용할 Standard Edition Server 또는 프런트 엔드 풀의 fqdn (정규화 된 도메인 이름)을 입력 합니다.

2.  **사용자 이름 접두사**에서 테스트를 위해 사용자 이름을 빌드하는 데 사용할 접두사를 입력 합니다.

3.  **암호**에서 모든 테스트 사용자 계정에 적용 되는 암호를 지정 합니다.

4.  **Sip 도메인**에서 테스트 사용자의 sip Uri (Uniform resource identifier)에 사용할 도메인 이름을 입력 합니다.

5.  **계정 도메인**에 테스트 사용자를 만들려는 현재 Active Directory 도메인 서비스 도메인의 도메인 이름을 입력 합니다.

6.  **조직 단위**에서 사용자 개체를 만들 Active Directory 도메인 서비스 OU의 이름을 입력 합니다. OU가 없는 경우 생성 됩니다.

7.  **전화 번호 지역 번호**에서 사용자 계정 테스트에 사용 되는 세 자리 지역 번호를 입력 합니다. 전화 번호 지역 번호가 Active Directory 도메인 서비스의 다른 사용자의 지역 코드와 충돌 하지 않는지 확인 합니다.

8.  엔터프라이즈 음성에 대 한 테스트 사용자를 사용 하도록 설정 하려면 **음성 사용** 확인란을 선택 합니다.

9.  **사용자 수**에서 만들려는 테스트 사용자의 총 수를 지정 합니다.

10. **시작 색인**에서 사용자 이름 접두사에 대 한 접미사로 사용 될 시작 번호를 지정 합니다.

<div>

## <a name="create-users-button"></a>사용자 만들기 단추

사용자 만들기 단추를 클릭 하면 모든 입력 매개 변수가 검사 됩니다.

  - 유효성 검사 오류가 있는 경우 해당 입력 값을 수정 하 라는 메시지가 표시 됩니다.

  - 모든 입력 값이 올바르면 Active Directory 도메인 서비스에서 사용자를 만드는 것이 시작 됩니다. 진행률 표시줄이이 양식 맨 아래에 표시 됩니다. 진행률 표시줄이 활성 상태인 동안에는 응용 프로그램을 닫지 않는 것이 좋습니다.

사용자 만들기는 처리 속도가 느립니다. 몇 분 정도 걸릴 수 있습니다. 사용자 수가 매우 큰 경우에는 프로세스에 몇 시간이 걸릴 수도 있습니다. 사용자가 이미 있는 경우 변경 내용으로 업데이트 됩니다. 범위에 있는 사용자 중 하나로 로그온 하 여 사용자가 만들어졌는지 확인할 수 있습니다. 사용자 접두사, 사용자 번호 및 @sipDomain를 지정 된 암호와 함께 사용자 이름 (예: LyncUser10@contoso.net)으로 사용 합니다.

</div>

<div>

## <a name="delete-users-button"></a>사용자 삭제 단추

사용자 삭제 단추를 클릭 하면 모든 입력 매개 변수가 검사 됩니다.

  - 유효성 검사 오류가 있는 경우 해당 입력 값을 수정 하 라는 메시지가 표시 됩니다.

  - 모든 입력 값이 올바르면 Active Directory 도메인 서비스에서 사용자를 사용 하지 않도록 설정 하 고 삭제 하는 것이 시작 됩니다. 진행률 표시줄이이 양식 맨 아래에 표시 됩니다. 진행률 표시줄이 활성 상태인 동안에는 응용 프로그램을 닫지 않는 것이 좋습니다.

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P>미국 형식의 전화 번호만 지원 됩니다. 전화 번호는 항상 사용자에 게 할당 되며 UserProvisioningTool에서 만든 모든 사용자가 엔터프라이즈 음성에 대해 사용 하도록 설정 됩니다. 전화 번호를 사용 하는 모든 시나리오 (예: 회의 자동 전화 교환 또는 UC-PSTN 통화)는이 전화 번호를 사용 하 여 통화를 올바르게 라우팅합니다. 이러한 이유로 모든 사용자는 고유한 전화 번호를가지고 있어야 합니다. 사용자를 두 번 만들어야 하는 경우 다른 지역 번호를 사용 하지 않거나 이전 사용자가 <STRONG>CsUser</STRONG> cmdlet을 사용 하 여 비활성화 된 경우를 제외 하 고 명령이 실패 합니다.</P>
> <LI>
> <P>연락처를 만들기 전에 먼저 사용자 탭에서 수행 되는 사용자 복제를 완료 해야 합니다. 방금 사용자를 만든 경우에는 Lync Server 복제가 완료 될 때까지 기다린 후 데이터베이스의 사용자 계정을 채울 수 있습니다. 사용자가 복제를 완료 하지 않은 경우 오류가 표시 됩니다. 사용자는 Lync Server 2013 프론트 엔드 서비스가 시작 된 경우 또는 마지막 사용자의 <STRONG>Get-CsUser</STRONG> cmdlet을 성공적으로 실행 하 여 복제를 완료 한 경우를 알 수 있습니다.</P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a>연락처 만들기 탭

연락처 만들기 탭을 통해 사용자의 연락처에 대 한 세부 정보를 지정할 수 있습니다.

![대화 상대 만들기 탭.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "대화 상대 만들기 탭.")

사용자의 연락처를 구성 하려면 다음 단계를 따릅니다.

1.  사용자 당 평균 연락처에서 각 사용자의 연락처 목록에 채울 평균 연락처 수를 지정 합니다.

2.  모든 사용자에 대해 동일한 수의 연락처를 만들려면 수정 됨 확인란을 선택 합니다. 사용자에 게 생성 되는 연락처 수를 변경 하려면 확인란의 선택을 취소 합니다.

3.  사용자 당 평균 연락처 그룹에서 사용자 당 대화 상대 그룹 수를 지정 합니다. 이 번호는 사용자 당 평균 연락처 보다 작아야 합니다.

4.  페더레이션/교차 풀 대화 상대 백분율에서 0과 100 사이의 숫자를 지정 합니다. 이 연락처의 백분율은 페더레이션 사용자와 함께 만들어집니다.

5.  페더레이션/교차 풀 사용자 접두사에서 로컬 사용자의 연락처 목록에 추가 될 페더레이션 사용자의 사용자 이름을 지정 합니다.

6.  페더레이션/교차 풀 사용자 SIP 도메인에서 페더레이션 사용자의 SIP 도메인 이름을 지정 합니다.
    
    <div>
    

    > [!NOTE]  
    > 연락처를 만들 때 어떤 사용자도 로그인 하지 않아야 합니다.

    
    </div>

7.  사용자 만들기 탭에서 매개 변수가 정확한 지 확인 합니다. 연락처를 만들 사용자의 범위는 사용자 만들기 탭에서 가져옵니다.

8.  연락처 만들기를 클릭 하 여 연락처 만들기를 시작 합니다. 이 프로세스는 몇 분 정도 걸릴 수 있습니다. 완료 되 면 "작업이 완료 되었습니다." 라는 메시지가 표시 되는 대화 상자가 나타납니다. 사용자 만들기 탭에서 만든 사용자로 로그온 하 여 만든 연락처의 유효성을 검사할 수 있습니다.
    
    <div>
    

    > [!NOTE]  
    > 연락처를 만든 후이 도구는 대상 풀의 모든 프런트 엔드 서버를 다시 시작 합니다. 이 작업으로 만든 연락처 수에 따라 프런트 엔드 서버를 시작 하는 데 걸리는 시간이 최대 2 시간까지 길어질 수 있습니다.

    
    </div>

</div>

<div>

## <a name="distribution-list"></a>메일 그룹

Lync Server 2013 스트레스 및 성능 도구의 기능 중 하나는 Lync 2013에서 메일 그룹 (DL) 확장 기능을 시뮬레이트하는 것입니다. UserProvisioningTool에서 DL 확장을 사용 하지 않을 경우이 단계를 건너뛸 수 있습니다.

![배포 목록 만들기 탭.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "배포 목록 만들기 탭.")

메일 그룹 탭에서 스트레스 및 성능 도구가 메일 그룹 확장 기능에 사용할 Dl을 만들 수 있습니다. Dl을 만들기 전에 Lync Server 2013가 이미 설치 되어 있어야 합니다. Lync Server 2013 ForestPrep을 실행 해야 합니다. 그렇지 않으면 DL 특성이 Active Directory 도메인 서비스 스키마에 존재 하지 않으며 도구가 Dl을 만들 수 없게 됩니다.

메일 그룹을 구성 하려면 다음 단계를 따릅니다.

1.  메일 그룹 수에서 만들려는 Dl의 총 수를 지정 합니다. (사용자 수의 2 배를 사용 하는 것이 좋습니다.) 0에서 n-1부터 번호가 매겨집니다.

2.  메일 그룹 접두사에서 Dl에 포함 되는 접두사를 지정 합니다. 예를 들어 100 Dl과 testDL의 접두사를 지정 하는 경우 Dl의 이름은 testDL0, testDL1 등이 고 testDL99입니다.

3.  분산의 최소 구성원 목록에서 각 메일 그룹에 추가할 최소 사용자 수를 지정 합니다.

4.  최대 구성원 수 목록에서 각 메일 그룹에 추가할 최대 사용자 수를 지정 합니다.

<div>

## <a name="create-distribution-lists-button"></a>메일 그룹 만들기 단추

메일 그룹 만들기 단추를 클릭 하면 도구는 Active Directory 도메인 서비스를 쿼리하여 접두사 및 번호와 일치 하는 메일 그룹이 이미 존재 하는지 확인 합니다. 이 도구는 아직 존재 하지 않는 항목만 만듭니다. 새로 만든이 메일 그룹에 구성원을 추가 하는 경우 사용자 만들기 탭에 지정 된 범위에서 사용자를 선택 합니다.

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a>위치 정보 서비스 구성 탭

Lync Server 2013 스트레스 및 성능 도구의 기능 중 하나는 위치 정보 서비스에 대 한 더미 구성 파일을 생성 하는 것입니다. 일반적으로 위치 정보 서비스에는 서버에 중대 한 성능 영향이 없습니다.

![위치 정보 서비스 구성 탭.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "위치 정보 서비스 구성 탭.")

이 기능을 테스트 하기로 선택 하면 양식에 언급 된 값을 입력 한 다음 LIS Config 파일 생성 단추를 클릭할 수 있습니다. 이\_는 lis 서브넷 .CSV,\_lis\_, lis. c a v a c c a .와 같은 csv 파일을\_생성 하 고, lis WAP. 그런 다음 set- **CsLisSubnet** Cmdlet, **set-CsLisSwitch** cmdlet, **set CsLisPort** cmdlet 및 **set-CSWIRELESSACCESSPOINT** cmdlet을 사용 하 여 이러한 CSV 파일을 LIS 데이터베이스로 가져올 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>


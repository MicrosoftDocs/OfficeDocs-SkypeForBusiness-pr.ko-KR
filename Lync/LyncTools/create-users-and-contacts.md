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
ms.openlocfilehash: f30737ebf721d17059418c690e678f69f0296a6c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a>사용자 및 연락처 만들기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-22_

스트레스 및 성능 부하 테스트를 준비 하는 동안 Lync Server 2013 사용자 프로 비전 도구 (UserProvisioningTool)를 사용 하 여 사용자 및 연락처를 만들어야 합니다.

이 항목을 참조 하 여 읽을 때 유용한 용어 및 정의 목록이 나와 있습니다.

  - 조직 구성 단위-Active Directory 도메인 서비스 OU (조직 구성 단위)입니다.

  - 페더레이션/교차 풀 – 인터넷 서비스의 MSN 네트워크, AOL® 및 Yahoo\!®와 같은 다른 IM (인스턴트 메시징) 서비스의 사용자와 통신 하도록 설정할 수 있는 사용자입니다.

  - 메일 그룹-사용자 그룹과의 통신을 시작 하는 데 사용 되는 Active Directory 도메인 서비스 사용자 목록을 포함 하는 Active Directory 도메인 서비스의 개체입니다.

  - Location Info Service-전화 별로 사용 하도록 설정 하 고 구성 하는 경우 E9-1-1) 서비스 9-1-1에 대 한 실제 위치 검색을 사용할 수 있는 Lync Server 2013 서비스입니다.

  - 미국 전화 번호-인바운드 및 아웃 바운드 통화 및 RNL (역방향 번호 조회)를 라우팅하는 데 사용 되는 SIP URI 외에 사용자에 게 할당 되는 전화 번호입니다.

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>UserProvisioningTool을 사용 하 여 사용자 및 연락처 만들기

부하 시뮬레이션을 위해 사용자 및 연락처를 만들려면 Lync Server 사용자 프로 비전 도구를 사용 해야 합니다. Lync server 사용자 프로 비전 도구는 Lync Server 스트레스 및 성능 도구 패키지와 함께 설치 됩니다. 프런트 엔드 서버 또는 Standard Edition 서버에서 패키지 설치 관리자 (CapacityPlanningTool)를 실행 해야 합니다. 프런트 엔드 서버 또는 Standard Edition Server에서 UserProvisioningTool 파일 (% InstalledDirectory% LyncStressAndPerfTool\\lyncstress)을 실행 하 여 Lync Server 사용자 프로 비전 도구를 시작 합니다.

<div>


> [!IMPORTANT]  
> UserProvisioningTool를 실행 하려면 Domain Admins 보안 그룹의 구성원으로 로그온 해야 합니다. UserProvisioningTool에서 새 Active Directory 도메인 서비스 사용자를 만들고 구성 하기 때문에이 컨텍스트에서 실행 해야 합니다.



</div>

<div>


> [!NOTE]  
> 많은 수의 사용자를 만들 때 (1만 이상), 고급 컴퓨터에서 UserProvisioningTool를 실행 합니다. 사용자가 만들어지는 동안에도 도메인 컨트롤러의 부하가 높아집니다.



</div>

Lync Server 사용자 프로 비전 도구가 열리면 **구성을** 클릭 하 고 **구성 로드**를 선택 합니다. 사용자 및 연락처 구성을 시작 하려면 패키지, SampleData에 포함 된 기본 파일을 로드 합니다. 이렇게 하면 시스템에서 수정 해야 하는 예제 데이터를 사용 하 여 필드를 미리 채울 수 있습니다. 이미 사용자 지정 설정을 포함 하는 미리 구성 된 XML 파일이 있는 경우 해당 파일을 로드 합니다. 다음 섹션에서 설명 하는 대로 Lync Server 사용자 프로 비전 도구의 필드를 입력 합니다.

![사용자 만들기 탭](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "사용자 만들기 탭")

서버 옵션을 구성 하려면 다음 단계를 수행 합니다.

1.  **프런트 엔드 풀 FQDN**에 사용자를 호스트 하려는 Standard Edition Server 또는 프런트 엔드 풀의 FQDN (정규화 된 도메인 이름)을 입력 합니다.

2.  **사용자 이름 접두사**에 테스트용으로 사용자 이름을 만드는 데 사용할 접두사를 입력 합니다.

3.  **암호**에서 모든 테스트 사용자 계정에 적용 되는 암호를 지정 합니다.

4.  **Sip 도메인**에서 테스트 사용자의 sip Uri (Uniform resource identifier)에 사용할 도메인 이름을 입력 합니다.

5.  **계정 도메인**에 테스트 사용자를 만들 현재 Active Directory 도메인 서비스 도메인의 도메인 이름을 입력 합니다.

6.  **조직 구성 단위**에 사용자 개체를 만들 Active Directory 도메인 서비스 OU의 이름을 입력 합니다. OU가 없는 경우에는 만들어집니다.

7.  **전화 지역 번호**에 사용자 계정 테스트에 사용할 3 자리 지역 번호를 입력 합니다. 전화 번호 지역 코드가 Active Directory 도메인 서비스의 다른 사용자 지역 코드와 충돌 하지 않도록 합니다.

8.  Enterprise Voice에 대 한 테스트 사용자를 사용 하도록 설정 하려면 **음성 사용** 확인란을 선택 합니다.

9.  **사용자 수**에서 만들려는 테스트 사용자의 총 수를 지정 합니다.

10. **시작 인덱스**에서 사용자 이름 접두사에 대 한 접미사로 사용 되는 시작 번호를 지정 합니다.

<div>

## <a name="create-users-button"></a>사용자 만들기 단추

사용자 만들기 단추를 클릭 하면 모든 입력 매개 변수가 유효성 검사 됩니다.

  - 유효성 검사 오류가 있으면 해당 입력 값을 수정 하 라는 메시지가 표시 됩니다.

  - 모든 입력 값이 올바르면 Active Directory 도메인 서비스에서 사용자를 만드는 것이 시작 됩니다. 진행률 표시줄이이 폼의 아래쪽에 표시 됩니다. 진행률 표시줄이 활성 상태인 동안에는 응용 프로그램을 닫지 않는 것이 좋습니다.

사용자 만들기가 느린 프로세스입니다. 몇 분 정도 걸릴 수 있습니다. 사용자 수가 매우 큰 경우 프로세스에 몇 시간이 걸릴 수도 있습니다. 사용자가 이미 있는 경우에는 변경 내용으로 업데이트 됩니다. 범위에 있는 사용자 중 하나로 로그온 하 여 사용자가 만들어졌는지 확인할 수 있습니다. 사용자 접두사, 사용자 번호 및 @sipDomain를 지정 된 암호와 함께 사용자 이름 (예: LyncUser10@contoso.net)으로 사용 합니다.

</div>

<div>

## <a name="delete-users-button"></a>사용자 삭제 단추

사용자 삭제 단추를 클릭 하면 모든 입력 매개 변수가 유효성 검사 됩니다.

  - 유효성 검사 오류가 있으면 해당 입력 값을 수정 하 라는 메시지가 표시 됩니다.

  - 모든 입력 값이 올바르면 Active Directory 도메인 서비스에서 사용자를 사용 하지 않도록 설정 하 고 삭제 하는 것이 시작 됩니다. 진행률 표시줄이이 폼의 아래쪽에 표시 됩니다. 진행률 표시줄이 활성 상태인 동안에는 응용 프로그램을 닫지 않는 것이 좋습니다.

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P>미국 형식으로 된 전화 번호만 지원 됩니다. 전화 번호가 항상 사용자에 게 할당 되며 UserProvisioningTool에서 만든 모든 사용자가 Enterprise Voice를 사용할 수 있도록 설정 됩니다. 전화 회의 자동 전화 교환 또는 UC-PSTN 통화와 같이 해당 번호를 사용 하는 모든 시나리오에서이 전화 번호를 사용 하 여 통화를 올바르게 라우팅합니다. 따라서 모든 사용자에 게 고유한 전화 번호가 있어야 합니다. 사용자를 두 번 만들어야 하는 경우 다른 지역 번호를 사용 하지 않거나 이전 사용자가 <STRONG>Disable-CsUser</STRONG> cmdlet을 사용 하 여 사용 하지 않도록 설정한 경우에만 명령이 실패 합니다.</P>
> <LI>
> <P>연락처를 만들기 전에 먼저 사용자 탭에서 수행 하는 전체 복제를 완료 해야 합니다. 사용자를 방금 만든 경우 Lync Server 복제가 완료 될 때까지 기다린 후 데이터베이스의 사용자 계정을 채웁니다. 사용자가 복제를 완료 하지 않은 경우 오류가 표시 됩니다. Lync Server 2013 프런트 엔드 서비스가 시작 되었거나 마지막 사용자에 대해 <STRONG>csuser</STRONG> cmdlet을 성공적으로 실행 하 여 사용자가 복제를 완료 한 경우를 알 수 있습니다.</P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a>대화 상대 만들기 탭

연락처 만들기 탭에서는 사용자의 연락처에 대 한 세부 정보를 지정할 수 있습니다.

![연락처 만들기 탭](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "연락처 만들기 탭")

사용자의 연락처를 구성 하려면 다음 단계를 수행 합니다.

1.  사용자 당 평균 대화 상대 수에서 각 사용자의 대화 상대 목록에 채울 평균 대화 상대 개수를 지정 합니다.

2.  모든 사용자에 대해 동일한 수의 연락처를 만들려면 고정 확인란을 선택 합니다. 사용자에 대해 만들어진 연락처 수를 변경 하려면 확인란을 선택 취소 합니다.

3.  사용자 당 평균 대화 상대 그룹 수에서 사용자 당 대화 상대 그룹의 개수를 지정 합니다. 이 숫자는 사용자 당 평균 대화 상대 수보다 작아야 합니다.

4.  페더레이션/교차 풀 대화 상대 백분율에서 0에서 100 사이의 숫자를 지정 합니다. 이 연락처의 백분율은 페더레이션 사용자와 함께 만들어집니다.

5.  페더레이션/교차 풀 사용자 접두사에서 로컬 사용자의 대화 상대 목록에 추가 될 페더레이션 사용자의 사용자 이름을 지정 합니다.

6.  페더레이션/교차 풀 사용자 SIP 도메인에서 페더레이션 사용자의 SIP 도메인 이름을 지정 합니다.
    
    <div>
    

    > [!NOTE]  
    > 연락처를 만들 때 어떤 사용자도 로그인 할 수 없습니다.

    
    </div>

7.  사용자 만들기 탭에서 매개 변수가 올바른지 확인 합니다. 연락처를 만들 사용자 범위는 사용자 만들기 탭에서 가져옵니다.

8.  연락처 만들기를 클릭 하 여 연락처 만들기를 시작 합니다. 이 프로세스는 몇 분 정도 걸릴 수 있습니다. 작업이 완료 되 면 "작업을 성공적으로 완료 했습니다." 라는 메시지가 표시 되는 대화 상자가 나타납니다. 사용자 만들기 탭에서 만든 사용자로 로그온 하 여 만든 연락처의 유효성을 검사할 수 있습니다.
    
    <div>
    

    > [!NOTE]  
    > 연락처가 만들어지면이 도구는 대상 풀에서 모든 프런트 엔드 서버를 다시 시작 합니다. 이 작업을 통해 만들어진 연락처 수에 따라 프런트 엔드 서버를 시작 하는 데 시간이 오래 걸릴 수 있습니다.

    
    </div>

</div>

<div>

## <a name="distribution-list"></a>메일 그룹

Lync Server 2013 스트레스 및 성능 도구의 기능 중 하나는 Lync 2013에서 메일 그룹 (DL) 확장 기능을 시뮬레이트하는 것입니다. UserProvisioningTool에서 DL 확장을 사용 하도록 설정 하지 않을 경우이 단계를 건너뛸 수 있습니다.

![메일 그룹 만들기 탭](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "메일 그룹 만들기 탭")

메일 그룹 탭에서는 스트레스 및 성능 도구에서 메일 그룹 확장 기능에 사용할 Dl을 만들 수 있습니다. Dl을 만들기 전에 Lync Server 2013이 이미 설치 되어 있어야 합니다. Lync Server 2013 ForestPrep를 실행 해야 합니다. 그렇지 않으면 DL 특성이 Active Directory 도메인 서비스 스키마에 없고 도구에서 Dl을 만들 수 없습니다.

메일 그룹을 구성 하려면 다음 단계를 수행 합니다.

1.  메일 그룹 수에서 만들려는 Dl의 총 수를 지정 합니다. (사용자 수를 두 번 사용 하는 것이 좋습니다.) 0부터 n-1까지 번호가 매겨집니다.

2.  메일 그룹 접두사에서 Dl에 포함 될 접두사를 지정 합니다. 예를 들어 100 Dl과 testDL의 접두사를 지정 하는 경우 Dl의 이름은 testDL0, testDL1 등이 됩니다.

3.  배포의 최소 구성원 목록에서 각 메일 그룹에 추가할 최소 사용자 수를 지정 합니다.

4.  최대 구성원 목록에서 각 메일 그룹에 추가할 최대 사용자 수를 지정 합니다.

<div>

## <a name="create-distribution-lists-button"></a>메일 그룹 만들기 단추

메일 그룹 만들기 단추를 클릭 하면이 도구는 Active Directory 도메인 서비스에 쿼리하여 접두사와 번호와 일치 하는 메일 그룹이 이미 있는지 확인 합니다. 이 도구는 아직 없는 항목만 만듭니다. 새로 만든이 메일 그룹에 구성원을 추가 하면 사용자 만들기 탭에 지정 된 범위에서 사용자를 선택 하 게 됩니다.

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a>위치 정보 서비스 구성 탭

Lync Server 2013 스트레스 및 성능 도구의 기능 중 하나는 위치 정보 서비스에 대 한 더미 구성 파일을 생성 하는 것입니다. 일반적으로 위치 정보 서비스는 서버에 대 한 성능에 큰 영향을 주지 않습니다.

![위치 정보 서비스 구성 탭](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "위치 정보 서비스 구성 탭")

이 기능을 테스트 하도록 선택한 경우 양식에 언급 된 값을 입력 한 다음 LIS Config 파일 생성 단추를 클릭할 수 있습니다. 이를 통해\_lis 서브넷 .CSV, lis\_스위치 .csv\_, lis 및\_lis의 .csv 파일을 생성 합니다. 그런 다음 **CsLisSubnet** Cmdlet, **CsLisSwitch** cmdlet, **CsLisPort** cmdlet 및 **CsWirelessAccessPoint** cmdlet을 각각 사용 하 여 이러한 CSV 파일을 LIS 데이터베이스로 가져올 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>


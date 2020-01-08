---
title: 'Lync Server 2013: 백업 및 복원 요구 사항: 데이터'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Backup and restoration requirements: data'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202194(v=OCS.15)
ms:contentKeyID: 51541526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54814295343b99cb51e5827791df160dbeff2638
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a>Lync Server 2013의 백업 및 복원 요구 사항: 데이터

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-03-26_

Lync Server는 데이터베이스에 저장 된 설정 및 구성 정보와 데이터베이스 및 파일 저장소에 저장 된 데이터를 사용 합니다. 이 항목에서는 조직에 장애가 있거나 중단 되는 경우 서비스를 복원할 수 있도록 백업 해야 하는 데이터에 대해 설명 하 고, Lync Server에서 사용 하는 데이터와 구성 요소를 별도로 확인 해야 합니다.

<div>

## <a name="settings-and-configuration-requirements"></a>설정 및 구성 요구 사항

이 항목에는 Lync Server 서비스의 복구에 필요한 설정 및 구성 정보를 백업 및 복원 하는 절차가 포함 되어 있습니다. 구성 정보는 중앙 관리 저장소나 다른 백 엔드 데이터베이스 또는 Standard Edition server에 있습니다.

다음 표에서는 백업 및 복원에 필요한 설정 및 구성 정보를 식별 합니다.

### <a name="settings-and-configuration-data"></a>설정 및 구성 데이터

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>데이터 형식</th>
<th>저장 위치</th>
<th>설명/백업 시기</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>토폴로지 구성 정보</p></td>
<td><p>중앙 관리 저장소 (데이터베이스: Xds)</p></td>
<td><p>토폴로지, 정책 및 구성 설정</p>
<p>정기 백업으로 백업 하 고 Lync Server 제어판 또는 cmdlet을 사용 하 여 구성 또는 정책을 수정 합니다.</p></td>
</tr>
<tr class="even">
<td><p>위치 정보</p></td>
<td><p>중앙 관리 저장소 (데이터베이스: Lis)</p></td>
<td><p>Enterprise Voice 향상 9-1-1 (E9-1-1) 구성 정보. 이 정보는 일반적으로 정적입니다.</p>
<p>정기 백업을 사용 하 여 백업 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>응답 그룹 구성 정보</p></td>
<td><p>백 엔드 서버 또는 Standard Edition 서버 (데이터베이스: RgsConfig)</p></td>
<td><p>응답 그룹 에이전트 그룹, 큐 및 워크플로</p>
<p>정기 백업으로 백업 하 고 에이전트 그룹, 큐 또는 워크플로를 추가 하거나 변경한 후</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a>데이터 요구 사항

다음은 오류가 발생할 경우 Lync Server 서비스를 복원할 수 있도록 백업 해야 하는 Lync Server 데이터 목록입니다.

일부 유형의 데이터는 복구에 필요 하지 않습니다. 이 항목에는 다음을 포함 하 여 이러한 유형의 데이터를 백업 하는 절차가 포함 되어 있지 않습니다.

  - 끝점, 구독, 활성 회의 서버 및 일시적인 회의 상태 (데이터베이스: RtcDyn)와 같은 임시 사용자 데이터

  - 주소록 데이터 (데이터베이스: Rtcab .mdf 및 Rtcab1). 주소록 데이터베이스는 Active Directory 도메인 서비스에서 자동으로 다시 생성 됩니다.

  - 통화 공원 응용 프로그램에 대 한 동적 정보 (데이터베이스: CpsDyn)

  - 에이전트 로그인 상태 및 통화 대기 정보 (데이터베이스: RgsDyn)와 같은 임시 응답 그룹 데이터

  - 영구 채팅 (데이터베이스: MgcComp)에 대 한 준수 데이터베이스입니다. 지속적인 채팅 준수를 사용 하는 경우 데이터베이스에서 정보를 읽고 대체 형식으로 변환 하도록 구성 된 어댑터가 있으면 영구 채팅 준수 데이터베이스의 정보는 일시적입니다. 따라서 영구 채팅에 대 한 규정 준수 데이터베이스가 일시적인 것으로 간주 됩니다.
    
    Lync Server 2013 영구 채팅 서버에는 XML 어댑터가 함께 제공 됩니다. 또한이 데이터를 사용 하는 사용자 지정 어댑터를 설치 하 고 Exchange 호스팅 보관 함과 같은 다른 원본으로 이동할 수 있습니다.

다음 표에서는 백업 하 고 복원 하는 데 필요한 데이터를 식별 합니다.

### <a name="data-stored-in-databases"></a>데이터베이스에 저장 된 데이터

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>데이터 형식</th>
<th>저장 위치</th>
<th>설명/백업 시기</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>영구 사용자 데이터</p></td>
<td><p>백 엔드 서버 또는 Standard Edition 서버 (데이터베이스: RTCXDS)</p></td>
<td><p>사용자 권한, 사용자 연락처 목록, 서버 또는 풀 데이터, 예약 된 회의 등 이 사용자 데이터에는 회의에 업로드 한 콘텐츠가 포함 되지 않습니다.</p>
<p>정기 백업을 사용 하 여 백업 합니다. 이 정보는 동적 이지만 마지막 정기 백업으로 복원 해야 하는 경우에는 업데이트 손실이 Lync Server에 치명적이 지 않습니다. 연락처 목록이 조직에 중요 한 경우에는이 데이터를 더 자주 백업할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>데이터 보관</p></td>
<td><p>보관 데이터베이스 (데이터베이스: LcsLog. mdf)</p>
<p>Microsoft Exchange 통합 옵션을 사용 하도록 설정한 경우이 데이터는 Exchange 2013에 저장 될 수 있습니다. 그렇지 않으면이 데이터는 Lync Server 보관 데이터베이스에 보관 되며, 이것은 다른 Lync Server 데이터베이스와 함께 collocated, 별도의 데이터베이스 서버에 독립 실행형 일 수 있습니다.</p></td>
<td><p>인스턴트 메시지 (IM) 및 모임 콘텐츠.</p>
<p>이 데이터는 Lync Server에 중요 하지 않지만 규정 목적을 위해 조직에 중요할 수 있습니다. 백업 일정을 적절 하 게 결정 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>데이터 모니터링</p></td>
<td><p>데이터베이스 모니터링 (LcsCDR 및 QoeMetrics)</p>
<p>이러한 데이터베이스는 다른 Lync Server 데이터베이스와 함께 collocated 또는 별도의 데이터베이스 서버에 독립 실행형이 될 수 있습니다.</p></td>
<td><p>통화 정보 레코드 (LcsCDR) 및 환경 품질 (체감 품질) 메트릭 (QoeMetrics).</p>
<p>통화 정보 레코드는 동적인 업무에 중요할 수 있습니다. 규정 상의 이유로 이러한 레코드가 필요한 지 여부를 고려 하 여 백업 일정을 결정 합니다.</p>
<p>경력 정보의 품질은 동적입니다. Lync Server의 작동에 대 한 체감 품질 데이터 손실은 중요 하지 않지만 비즈니스에 중요 한 역할을 할 수 있습니다. 이 정보가 조직에 얼마나 중요 한 지에 따라 백업 일정을 결정 합니다.</p></td>
</tr>
<tr class="even">
<td><p>영구 채팅 데이터</p></td>
<td><p>영구 채팅 데이터베이스 (mgd).</p>
<p>이 데이터베이스는 다른 Lync Server 데이터베이스와 함께 collocated 또는 별도의 데이터베이스 서버에 독립 실행형 일 수 있습니다.</p></td>
<td><p>영구 채팅 데이터는 채팅방에 게시 되는 실제 채팅 콘텐츠입니다. 이 데이터는 비즈니스에 중요 한 역할을 합니다.</p>
<p>Lync Server에 제공 되는 <strong>export-CsPersistentChatData</strong> cmdlet을 사용 하 여 SQL Server 백업을 사용할지 또는 데이터베이스를 내보낼지 선택할 수 있습니다. 데이터 복구의 경우 마지막 전체 백업의 시점으로 데이터베이스를 가져오고 복원할 수 있으며,이는 실패 시점으로 데이터베이스를 복원할 수 없음을 의미 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a>파일 저장소 데이터 요구 사항

Enterprise Edition 배포에서 Lync Server 파일 저장소는 일반적으로 파일 서버에 있습니다. 스탠더드 버전 배포의 경우 Lync Server 파일 저장소는 기본적으로 Standard Edition 서버에 위치 합니다. 일반적으로 사이트에 대해 공유 되는 Lync Server 파일 저장소 1 개가 있습니다. 영구 채팅 파일 저장소는 Lync Server 파일 저장소와 동일한 파일 공유를 사용 합니다.

파일 저장소 위치는 서버 \\ \\\\공유 이름으로 식별 됩니다. 파일 저장소의 특정 위치를 찾으려면 토폴로지 작성기를 열고 **파일 저장소** 노드를 찾습니다.

다음 표에서는 백업 하 고 복원 하는 데 필요한 파일 저장소를 보여줍니다.

### <a name="file-stores"></a>파일 저장소

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>데이터 형식</th>
<th>저장 위치</th>
<th>설명/백업 시기</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 파일 저장소</p></td>
<td><p>일반적으로 파일 서버, 파일 클러스터 또는 Standard Edition 서버에서</p></td>
<td><p>모임 콘텐츠, 모임 콘텐츠 메타 데이터, 모임 준수 로그, 장치 업데이트에 대 한 파일 업데이트, 응답 그룹에 대 한 오디오 파일, 통화 공원, 알림 응용 프로그램, 영구 채팅방에 게시 된 파일</p>
<p>정기 백업을 사용 하 여 백업 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a>추가 백업 요구 사항

오류가 발생 했을 때 Lync Server 서비스를 복원할 수 있도록 하려면 Lync Server 자체에 포함 되지 않은 필요한 구성 요소를 백업 해야 합니다. 다음 구성 요소는이 문서에서 설명 하는 Lync Server 백업 및 복원 프로세스의 일부로 서 백업 또는 복원 되지 않습니다.

  - **Active directory 도메인 서비스**   Lync Server를 백업할 때 active directory 도구를 사용 하 여 AD DS를 백업 해야 합니다. Lync Server에서 AD DS의 연락처 개체가 필요한 경우 발생할 수 있는 문제를 방지 하기 위해 AD DS와 Lync 서버를 동기화 하는 것이 중요 합니다. AD DS는 Lync Server에 사용 되는 다음 설정을 저장 합니다.
    
      - 사용자 SIP URI 및 기타 사용자 설정
    
      - 응답 그룹 및 회의 수행자와 같은 응용 프로그램에 대 한 연락처 개체
    
      - 중앙 관리 저장소에 대 한 포인터입니다.
    
      - Kerberos 인증 계정 (선택적 컴퓨터 개체) 및 Lync Server 보안 그룹
    
    Windows Server 2008에서 AD DS를 백업 및 복원 하는 방법에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkId=209105](http://go.microsoft.com/fwlink/p/?linkid=209105)"Ad ds 백업 및 복구 단계별 가이드"를 참조 하세요.

  - **인증 기관 및 인증서**   는 CA (인증 기관) 및 인증서 백업에 조직의 정책을 사용 합니다. 내보낼 수 있는 개인 키를 사용 하는 경우에는 인증서와 개인 키를 백업한 다음이 문서의 절차를 사용 하 여 Lync Server를 복원 하는 경우 내보냅니다. 내부 CA를 사용 하는 경우 Lync Server를 복원 해야 하는 경우 다시 등록할 수 있습니다. 컴퓨터에 장애가 발생할 경우 사용할 수 있는 안전한 위치에 개인 키를 유지 하는 것이 중요 합니다.

  - **System center operations manager**   microsoft system center operations manager (이전의 microsoft Operations manager)를 사용 하 여 lync server 배포를 모니터링 하는 경우 선택적으로 lync server를 모니터링 하는 동안 만든 데이터를 백업할 수 있습니다. 표준 SQL Server 백업 프로세스를 사용 하 여 System Center Operations Manager 파일을 백업 합니다. 이러한 파일은 복구 중에 복원 되지 않습니다.

  - **Pstn (공개 전환 전화 네트워크) 게이트웨이 구성**   엔터프라이즈 음성 또는 Survivable Branch 기기를 사용 하는 경우 pstn 게이트웨이 구성을 백업 해야 합니다. PSTN 게이트웨이 구성 백업 및 복원에 대 한 자세한 내용은 공급 업체에 문의 하세요.

  - **Lync server 또는 office Communications server**   버전 동시 사용 lync server 2013 배포가 lync server 2010 또는 이전 버전의 Office communications server와 함께 존재 하는 경우이 문서의 절차를 사용 하 여 이전 버전을 백업 하거나 복원할 수 없습니다. 대신 이전 버전에 맞게 문서화 된 백업 및 복원 절차를 사용 해야 합니다. Lync Server 2010를 백업 및 복원 하는 방법에 대 [http://go.microsoft.com/fwlink/p/?linkId=265417](http://go.microsoft.com/fwlink/p/?linkid=265417) 한 자세한 내용은을 참조 하세요. Microsoft Office Communications Server 2007 R2를 백업 및 복원 하는 방법에 대 [http://go.microsoft.com/fwlink/p/?linkId=168162](http://go.microsoft.com/fwlink/p/?linkid=168162)한 자세한 내용은을 참조 하세요.

  - ****   인프라 구성, 부하 분산 구성, IIS (인터넷 정보 서비스) 구성, DNS (Domain Name System) 레코드 및 IP 주소, DHCP (동적 호스트 구성 프로토콜) 구성 등 인프라에 대 한 정보를 백업 하는 데 필요한 인프라 정보 이러한 구성 요소를 백업 하는 방법에 대 한 자세한 내용은 해당 공급 업체에 문의 하세요.

  - ****   Microsoft exchange 및 exchange um (통합 메시징) 백업 및 microsoft exchange 설명서에 설명 된 대로 microsoft exchange 및 exchange um을 복원 합니다. Exchange Server 2013 백업 및 복원에 대 한 자세한 내용은을 [http://go.microsoft.com/fwlink/?LinkId=285384](http://go.microsoft.com/fwlink/?linkid=285384)참조 하세요. Exchange Server 2010 백업 및 복원에 대 한 자세한 내용은을 [http://go.microsoft.com/fwlink/p/?linkId=209179](http://go.microsoft.com/fwlink/p/?linkid=209179)참조 하세요.
    
    Lync Server 2013에는 사용자 연락처 목록, 고화질 사용자 사진, Exchange 2013에 저장 된 데이터 보관 등이 포함 됩니다. 이러한 유형의 데이터를 백업 하는 방법에 대 한 자세한 내용은 다음 목록을 참조 하세요.
    
      - **고해상도 사진은** Exchange Server 백업의 일부로 백업 됩니다.
    
      - **통합 된 대화 상대 저장소** 는 Lync Server 2013에서 도입 되었습니다. 통합 된 대화 상대 저장소를 통해 사용자는 Exchange 2013에서 모든 연락처 정보를 유지할 수 있습니다.
        
        사용자 연락처가 통합 된 연락처 저장소나 Lync 백 엔드 서버에 저장 되는지 여부에 따라 백업이 사용자에 게 최신 상태 인지 확인 해야 합니다. 다음 시나리오는 사용자 연락처를 통합 대화 저장소로 마이그레이션하는 경우 백업 및 복원 프로세스에 문제가 발생할 수 있는 경우를 보여 줍니다.
        
        **시나리오 1:** 사용자 연락처는 통합 된 연락처 저장소로 마이그레이션되고 사용자 연락처를 마이그레이션하기 전에 수행한 Lync Server 백업에서 복원이 수행 됩니다. 이 시나리오에서는 Lync Server 마이그레이션 작업이 사용자 연락처를 Exchange로 마이그레이션하기 시작 하기까지 최대 1 일 동안 사용자에 게 오래 된 연락처의 상태가 포함 됩니다. (사용자 연락처는 이전에 통합 된 연락처 저장소로 마이그레이션 되었기 때문에 Exchange 연락처 정보가 사용 됩니다.) 이 시나리오에서는 관리자 개입이 필요 하지 않습니다.
        
        **시나리오 2:** 사용자 연락처가 이전에 통합 된 연락처 저장소에 저장 되었지만 롤백 되었습니다. 사용자 연락처가 통합 대화 상대 저장소에 저장 되었을 때 만든 Lync Server 백업에서 복원이 수행 됩니다. 이 시나리오에서는 클라이언트 또는 Lyss 서버 `Error: Incorrect Exchange Version` 로그의 오류 메시지가이에 대 한 문제로 표시 될 수 있습니다. 사용자가 Exchange에서 직접 Lync 2013의 연락처 목록에 액세스할 수 있지만 클라이언트의 상태는 Lync Server 상태와 일치 하지 않습니다. 이 문제를 해결 하려면 관리자가 영향을 받는 사용자에 대 한 **CsUCSRollback** cmdlet을 실행 해야 합니다.
    
      - **데이터 보관** 은 Exchange 2013에 저장 될 수 있습니다. 이 데이터는 Lync Server에 중요 하지 않지만 규정 목적을 위해 조직에 중요할 수 있습니다. 데이터 보관이 Exchange에 저장 되어 있고 조직에 중요 한 경우에는 Exchange 백업 및 복원 절차를 따릅니다. Exchange에 저장 된 데이터 보관은 Lync 서버로 다시 이동할 수 없습니다. 또한 Lync 보관 데이터베이스에 이미 저장 된 데이터를 Exchange에 이동할 수 있는 방법은 없습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>


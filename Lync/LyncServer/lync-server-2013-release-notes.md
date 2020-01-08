---
title: Lync Server 2013 릴리스 정보
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a93fabf10355dcc4ba7873921c0aaf35475927c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="release-notes-for-lync-server-2013"></a>Lync Server 2013 릴리스 정보

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2016-12-08_

Lync Server 2013 릴리스 정보에 오신 것을 환영 합니다. Lync Server 2013의 알려진 문제 관련 정보는이 파일을 참조 하세요.

<div>

## <a name="about-this-document"></a>이 문서 정보

이 문서에는 Lync Server 2013를 배포 하 고 사용 하기 전에 알아야 할 중요 한 정보가 포함 되어 있습니다. Lync Server 2013에 대 한 자세한 내용은 [Microsoft Lync server 2013](microsoft-lync-server-2013.md) 설명서를 참조 하세요.

이 문서에는 다음 섹션이 포함 되어 있습니다.

  - Lync 2013 클라이언트

  - Lync Server

  - 설치용

  - 이동성

  - 회의

  - Enterprise Voice

  - 현재 상태

  - 응답 그룹 응용 프로그램 및 통화 공원 응용 프로그램

  - Lync Server 컨트롤 패널, 토폴로지 작성기 및 계획 도구

  - 지역화

  - 저작권

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a>Lync 2013 클라이언트

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a>다른 응용 프로그램에서 파일이 열려 있는 경우 인스턴트 메시지에서 파일을 전송할 수 없음

**문제**

다른 Lync 사용자에 게 메신저 대화를 포함 하 여 Word 문서와 같은 파일을 전송 하려고 하면 전송이 성공한 것으로 나타나지만 실제로 파일을 전송 하지 못할 수 있습니다. Lync 클라이언트에는 파일 형식에 대 한 아이콘이 표시 되지만 의도 하지 않은 수신자가 해당 파일을 열 수 없습니다. 성공적으로 전송 되지 않았음을 알리는 오류 메시지가 표시 되지 않습니다.

**방법을**

이 문제를 해결 하려면 인스턴트 메시지에서 파일 전송을 시도 하기 전에 열려 있는 파일이 나 열려 있는 응용 프로그램을 닫습니다.

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a>Lync Server

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a>Lync Server 저장소 서비스 데이터 복제에 실패 하는 경우 관리자가 부실 저장소 서비스 큐 항목에 대 한 성능 카운터를 확인 해야 합니다.

**문제**

Lync Server 저장소 서비스는 복제에 Windows Fabric을 사용 합니다. 기본 프런트 엔드 서버에서 데이터를 삭제 했지만 보조 프런트 엔드 서버에서 삭제가 실패 하는 경우 (예: 프런트 엔드 서버에서 예기치 않은 종료 또는 오류가 발생 한 경우) 데이터는 그대로 유지 되 고 "고아" 상태가 될 수 있습니다. 고아 데이터는 성능이 떨어지고 드라이브 공간을 낭비 시킬 수 있습니다.

**방법을**

이 문제\_를 해결 하려면 이벤트 로그에\_\_사용\_된 이벤트 (id = 32058) 및 lyss\_db\_공간\_\_(id = 32059)이 발생 하는 경우, 관리자는 Name Ss **-i: lyss** 서버의 성능 카운터를 확인 해야 합니다 **-현재 저장소 서비스의 오래 된 큐 항목 수**를 포함 하는 저장소 서비스 API 이 성능 카운터의 값이 높은 경우 (예: 50000 보다 큼) 관리자는 Lync Server 2013 Resource Kit에서 CleanuUpStorageServiceData 도구를 실행 하 여 풀에서 고아 데이터가 모두 삭제 됩니다. 도구에 대 한 자세한 내용은 Lync Server 2013 리소스 키트 설명서를 참조 하세요.

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a>서버 또는 풀에 대해 IP 주소 구성이 변경 될 때마다 Lync Server 서비스를 다시 시작 해야 합니다.

**문제**

IPv4에서 듀얼 스택으로 변경 하는 것과 같이 Lync Server 2013 배포에 대해 IP 주소 구성을 변경 하거나 듀얼 스택에서 Ipv6으로 변경 하는 경우 모든 서버 구성 요소가 서비스를 다시 시작할 때까지 구성 변경을 선택 하지 않습니다.

**방법을**

이 문제를 해결 하려면 배포에 대 한 IP 주소 구성을 변경한 후 Lync Server 서비스를 다시 시작 합니다. 이렇게 하려면 Lync Server 관리 셸에서 다음 cmdlet을 실행 합니다.

   ```
    Stop-CsWindowsService -graceful
   ```

   ```
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a>Lync Server 2013 관리 팩에서 전화 접속 회의 가상 트랜잭션 cmdlet을 더 이상 사용할 수 없음

**문제**

Lync Server 2013 관리 팩에서는 전화 접속 회의 가상 트랜잭션 cmdlet **테스트-CsDialInConferencing** 을 더 이상 사용할 수 없습니다.

**방법을**

전화 접속 회의 가상 트랜잭션 cmdlet **테스트 사용-CsDialInConferencing** 는 엔터프라이즈 내부 에서만 지원 됩니다.

관리자는 문제 해결을 위해 Lync Server 관리 셸에서 cmdlet을 계속 사용할 수 있습니다. 필요한 경우 엔터프라이즈는 내부에서 cmdlet을 실행 하는 개인 관리 팩을 개발할 수도 있습니다.

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a>네트워크 공유에 로그 파일을 복사할 때 네트워크 트래픽이 중단 되는 경우 중앙 로깅 서비스가 중지 됨

**문제**

중앙 로깅 서비스가 네트워크 경로를 사용 하도록 구성 된 경우 ( **Get-CsClsConfiguration** Cmdlet의 CacheFileNetworkFolder 매개 변수 값이 유효한 UNC 경로인 경우) 캐시 된 로그 파일이 네트워크 공유에 복사 됩니다. 파일을 복사 하는 동안 네트워크 트래픽이 중단 되는 경우 중앙 로깅 서비스를 중지 시키는 예외가 발생 합니다.

서비스는 최대 3 회까지 자동으로 다시 시작 되도록 구성 되므로 처음 세 가지 예외에서 서비스가 복구 됩니다.

**방법을**

이 문제에 대 한 해결 방법은 없습니다. 문제를 확인 하려면 "Lync Server 중앙 로깅 서비스 에이전트" 서비스가 예기치 않게 종료 되는 경우를 기록 하는 이벤트 ID 7031 ("서비스 제어 관리자")에 대 한 이벤트 로그를 모니터링 하세요. 이 문제가 세 번 이상 발생 하는 경우 **시작-CsWindowService** cmdlet을 사용 하 여 서비스를 수동으로 다시 시작 합니다.

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a>저장소 서비스 큐 항목을 수동으로 가져와야 할 경우

**문제**

Lync Server 2013는 각 프런트 엔드 서버의 데이터베이스에 보관 된 메시지 및 CDR (통화 정보 기록)와 같은 회의 및 인스턴트 메시지에 대 한 데이터를 저장 합니다. 데이터는 의도 한 대상에 게 전달 되기 전에 처리 되는 동안 데이터베이스에 저장 됩니다. 성능을 향상 시키기 위해 Lync Server 2013는 오랜 시간 동안 처리 되지 않은 로컬 데이터베이스에서 큐 항목을 주기적으로 내보내고 파일 저장소에 저장 합니다. 파일 저장소를 사용할 수 없는 경우 각 프런트 엔드 서버에 항목이 저장 됩니다. 풀 장애 조치 (failover) 중 데이터 손실을 방지 하기 위해 동일한 작업이 발생 합니다.

내보내기 작업 중에 Lync Server 저장소 서비스가 32075의 이벤트 Id를 사용 하 여 이벤트 로그에 모든 단계를 기록 (전체 플러시 작업이 시작 됨), 32076 (전체 플러시 완료), 32082 (유지 관리 수준 플러시 시작 됨), 32083 (유지 관리 수준 플러시) 완료 됨), 32089 (데이터베이스 채우기 때문에 플러시 발생). 이 데이터는 처리 하 여 최종 대상 (SQL Server 또는 Exchange Server)에 게 전달 하는 시스템으로 다시 가져오지 않습니다.

**방법을**

시스템으로 데이터를 가져오려면 관리자는 Lync Server Resource Kit에서 ImportStorageServiceData 도구를 사용 하 여 처리 하 고 최종 목적지로 배달 되도록 데이터를 다시 시스템에 추가 해야 합니다.

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a>UseNormalizationRules의 기본값을 False로 변경 하면 주소록 웹 쿼리 검색에 실패 합니다.

**문제**

UseNormalizationRules의 기본값이 False로 변경 되 면 주소록 웹 쿼리 검색이 실패 합니다. 기본값을 변경한 후 Lync 클라이언트 사용자는 Lync 주소록 웹 쿼리를 사용 하 여 사용자를 검색할 수 없습니다.

**방법을**

UseNormalizationRules의 기본값을 False로 설정 하 여 사용자가 Lync Server 2013 정규화 규칙을 적용 하지 않고 Active Directory 도메인 서비스에 정의 된 대로 전화 번호를 사용할 수 있도록 하려면 다음을 수행 하 여이 문제를 해결 하세요.

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  다음 중 하나를 수행 합니다.
    
      - 배포에 Lync Server 2013 서버만 포함 된 경우 전역 수준에서 다음 cmdlet을 실행 하 여 UseNormalizationRules 및 IgnoreGenericRules의 값을 True로 변경 합니다.
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - 배포에 Lync Server 2013 및 Lync Server 2010 또는 Office Communications Server 2007 R2 조합이 포함 되어 있는 경우 다음 cmdlet을 실행 하 고 토폴로지의 각 Lync Server 2013 풀에 할당 합니다.
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  모든 풀에서 CMS 복제가 수행 될 때까지 기다립니다.

4.  배포에 대 한 전화 정규화 규칙 파일을 수정 하 여 콘텐츠를 지웁니다. 파일은 각 Lync Server 2013 풀의 파일 공유에 있습니다. 파일이 없는 경우 "\_회사 전화\_번호\_정규화\_규칙. x" 라는 빈 파일을 만듭니다.

5.  모든 프런트 엔드 풀이 새 파일을 읽을 수 있도록 몇 분 정도 기다립니다.

6.  배포의 각 Lync Server 2013 풀에서 다음 cmdlet을 실행 합니다.
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a>주소록 서버 오류 이벤트 21054이 각 Lync 2013 풀에 대해 매일 한 번씩 생성 됨

**문제**

Lync Server 2013 주소록 서버는 매일 유지 관리를 수행할 때마다 오류 이벤트 21054를 생성 합니다. 업데이트를 성공적으로 수행 하는 경우에도 관리자가 **업데이트 csAddressBook** cmdlet을 실행할 때마다 오류가 생성 됩니다. 그러나 업데이트가 성공할 경우이 오류 이벤트는 무시 해도 안전 합니다.

**방법을**

이 오류 이벤트가 발생 하는 경우 다음 cmdlet을 실행 합니다.

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

Cmdlet에서 인덱싱되지 않거나 중단 된 개체가 없다고 보고 하면 오류 이벤트 21054을 무시 해도 안전 합니다.

또한 System Center Operations Manager에서 KHI (키 상태 표시기) "주소록 사용자가 올바르게 색인 지정" 되어 있어야 합니다.

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a>Edge 풀에 IPv6이 구성 되어 있으면 요청이 실패할 수 있음

**문제**

Edge 풀에 IPv6이 구성 되어 있으면 Edge 풀에 대 한 일부 요청이 실패할 수 있습니다.

**방법을**

이 문제를 해결 하려면 IPv6을 사용 하 여 Edge 풀을 구성 하지 마세요.

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a>풀 장애 복구 중에 csPoolFailback cmdlet이 실패할 수 있음

**문제**

풀을 장애 복구 하려고 할 때 **csPoolFailback** cmdlet이 오류로 실패할 수 있으며, "반복 시도 후 hydration 프로세스를 완료 하지 못했습니다."

**방법을**

이 문제를 해결 하려면 cmdlet을 다시 실행 하 고 cmdlet이 성공할 때까지 기다립니다. 장애 복구 프로세스가 완료 될 때까지 몇 분이 소요 될 수 있다는 점에 유의 하세요. 2만 사용자가 있는 풀에 대해 최대 60 분이 걸릴 수 있습니다.

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a>프런트 엔드 서버를 이미 설정 된 풀에 추가 하면 데이터 손실이 발생할 수 있음-하이브리드, 비즈니스용 Skype Online

**문제**

풀에 프런트 엔드 서버가 두 대 이상 있고 프런트 엔드 서버 중 하나를 다시 시작 하거나 이전에 풀의 일부가 아닌 새 프런트 엔드 서버를 추가 하는 환경에서이 문제가 발생할 수 있습니다.

해당 데이터를 보관 하는 사용자에 게는 풀에 대해 안정적인 데이터 보관을 설정할 때까지 데이터 손실이 발생할 수 있습니다. 이 기간 잠재적 데이터 손실은 사용자 간 대화에 대해 15 분으로 제한 되며 회의에 30 분이 소요 됩니다.

**방법을**

유지 관리를 수행 하는 경우 풀의 프런트 엔드 서버를 하나씩 시작 하는 대신 풀을 다른 풀로 장애 조치 하 고 서버에서 유지 관리 작업을 수행 해야 합니다. 유지 관리 작업을 수행 하기 전에 서비스를 사용할 수 없게 설정한 다음 유지 관리가 완료 되 면 가용성을 복원할 수도 있습니다.

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a>관리자가 Get CsClientAccessLicense cmdlet을 사용 하 여 라이선스 사용자 수를 가져올 수 없음

**문제**

관리자는 **get-CsClientAccessLicense** cmdlet을 사용 하 여 정확한 클라이언트 라이선스 사용을 가져올 수 없습니다.

**방법을**

서버 라이선스 유형을 확인 하려면 **Get-CsService** cmdlet을 실행 하 여 모든 데이터베이스의 정규화 된 도메인 이름 (FDQNs)을 검색할 수 있습니다. 프런트 엔드 서버의 FQDN이 백 엔드 데이터베이스의 FQDN과 같은 경우 라이선스는 Standard edition 라이선스입니다. 그렇지 않으면 라이선스는 Enterprise edition 라이선스입니다.

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a>클라이언트 정식 사용자 수가 정확 하 게 보고 되지 않음

**문제**

클라이언트 라이선스 개수를 결정할 때 다음과 같은 상황이 발생할 수 있습니다.

1.  **모바일 사용자의 부정확 한 라이선스 수**
    
    라이선스 수는 장치 기반 사용자에 대 한 고유한 IP 주소 수를 기반으로 합니다. 라이선스 수는 다음 방법으로 제한 됩니다.
    
      - Lync 세션 중에 사용자의 IP 주소가 변경 되 면 라이선스의 과잉 계산으로 간주 됩니다. 이 문제는 사용자가 데스크톱 클라이언트를 사용 하 여 둘 이상의 위치에서 Lync Server에 연결할 때 발생할 수 있습니다.
    
      - 장치에 대 한 IP 주소를 확인할 수 없기 때문에 사용자가 모바일 클라이언트에 연결 하는 경우 라이선스가 곧 계산 됩니다.

2.  **라이선스는 Lync 클라이언트에 대 한 PSTN (공개 통신 네트워크) 통화, PSTN 회선으로 Lync 클라이언트 호출, PSTN 회선으로 착신 전환 된 Lync 통화에 대해 두 번 계산 됩니다.**
    
    다음 시나리오에서는 전화 번호와 Lync 사용자가 모두 사용 된 라이선스 수를 확인 하기 위해 계산 되므로 두 개의 추가 라이선스가 1이 아닌 계산 됩니다. 정확한 라이선스 데이터를 얻으려면 전화 번호로 생성 된 라이선스를 수동으로 제거 합니다.
    
      - Lync에 대 한 PSTN 전화 통화
    
      - PSTN 회선에 대 한 Lync 통화
    
      - Lync에 대 한 PSTN 통화는 PSTN 회선으로 통화를 전달 합니다. PSTN 회선 중 하나가 계산 됩니다.

3.  **라이선스는 로그온 한 Lync 휴대폰에 대해 계산 되지 않습니다.**
    
    사용자가 Lync 인증 된 전화를 사용 하는 경우에는 로그인 상태를 유지 하는 연결을 사용 하 여 로그인 하 고 유지 하는 경우, 전화를 로그인 한 후에 라이선스에 대 한 쿼리가 발생 하는 경우 해당 전화가 라이선스를 사용할 때와 같이 계산 되지 않습니다.

4.  **회의 참가에 대 한 PSTN 전화의 라이선스 개수 계산**
    
    사용자가 PSTN 전화기를 사용 하 여 전화 회의에 참가 하는 경우에는 회의가 전화 회의에 참가 하는 것으로 간주 되지 않습니다. 그러나 PSTN 전화기로는 회의에 참가 하는 데 필요한 라이선스가 없습니다.

**방법을**

1.  **모바일 사용자의 부정확 한 라이선스 수**
    
      - 동일한 장치에 속한 IP 주소를 수동으로 식별 한 다음 라이선스 수에서 그 중 하나를 제거할 수 있습니다.
    
      - Lync 클라이언트에 연결 하는 모바일 장치에서는이 문제에 대 한 해결 방법이 없습니다.

2.  **라이선스는 Lync 클라이언트에 대 한 PSTN 통화, PSTN 회선으로 Lync 클라이언트 호출, PSTN 회선으로 착신 전환 된 lync 통화에 대해 두 번 계산 됩니다.**
    
    PSTN 전화번호를 수동으로 식별 하 고 해당 번호에 대해 생성 된 라이선스 수를 제거 해야 합니다.

3.  **로그인 한 Lync phone의 경우 라이선스가 계산 되지 않습니다.**
    
    Lync phone을 로그 오프 하도록 구성한 다음 정기적으로 3 개월 간격으로 다시 로그온 할 수 있습니다.

4.  **회의 참가에 대 한 PSTN 전화의 라이선스 개수 계산**
    
    전화 회의에 참가 하는 데 사용 되는 PSTN 전화 번호를 수동으로 식별 하 고 해당 번호로 생성 된 라이선스를 제거할 수 있습니다.

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a>Lync Server 제어판은 Silverlight 5로 업그레이드 한 후 VMware 환경에서 작동을 중지 합니다.

**문제**

VMware 환경에서 Lync Server 제어판을 사용 하는 경우 Microsoft Silverlight를 버전 5로 업그레이드 한 후 Lync Server 제어판이 작동 하지 않을 수 있습니다.

**방법을**

이 문제를 해결 하려면 다음 중 하나를 수행 합니다.

  - Silverlight 5를 제거 하 고 Silverlight 4를 [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156)설치 합니다.

  - VMware 가상 컴퓨터가 아닌 컴퓨터에서 Lync Server 제어판에 액세스 합니다.
    
    이렇게 하려면 컴퓨터에 Lync Server 관리 도구가 설치 되어 있는 경우 서버의 Windows **시작** 메뉴에서 Lync server 제어판을 시작할 수 있습니다.
    
    웹 브라우저를 사용 하 여 Lync Server 제어판에 액세스할 수도 있습니다. \<URL은 https://프런트\_엔드 풀\_fqdn\>/cscp.와 유사 합니다.

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a>Active Directory에서 사용자의 고유 이름을 수정한 후에 주소록 서비스의 사용자 정보가 업데이트 되지 않음

**문제**

Active Directory 도메인 서비스에서 사용자의 고유 이름 (DN이 라고도 함)이 변경 되는 경우 추가 변경 내용이 주소록 서비스 (ABS)에 업데이트 되지 않습니다. 이는 사용자에 대 한 로그인 또는 현재 상태에 영향을 주지 않지만, SIP 주소도 변경한 경우 검색은 오래 된 SIP 주소를 반환 하기 때문에 사용자에 대 한 통신을 방지 합니다.

**방법을**

이 문제를 해결 하려면 사용자의 DN을 변경 하지 마세요. 사용자의 DN을 이전 값으로 되돌리면 주소록 서비스에 업데이트가 반영 됩니다.

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a>설치용

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a>ASCII 문자가 아닌 문자를 사용 하 여 Lync server가 시작 되지 않는 문제가 발생 하는 경우

**문제**

대상 폴더 이름에 ASCII가 아닌 문자 (유니코드, 더블 바이트 문자 집합 (DBCS), u t f-8 및 u t f-16 포함)가 포함 되어 있으면 설치에 실패 합니다. 또한 설치가 성공할 수 있지만 비 ASCII 문자가 다음 중 하나에 포함 되어 있는 경우에는 서버가 시작 되지 않습니다.

  - 컴퓨터 이름

  - 도메인 이름

  - 사용자 이름

  - 사용자 SIP URI

  - 서비스 계정 이름

**방법을**

대상 폴더 이름, 컴퓨터 이름, 도메인 이름, 사용자 이름, 사용자 SIP URI 및 서비스 계정 이름에 ASCII 문자만 사용 합니다.

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a>Lync Server 2013를 설치 하기 전에 모듈에서 IIS 7.5의 InsertEntityBody 메서드를 호출할 때 "힙 손상 발생" 핫픽스가 설치 되어 있어야 합니다.

**문제**

"힙 손상에 대 한 핫픽스는 모듈에서 Microsoft 기술 자료 문서 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)[https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603))에 설명 된 IIS 7.5" ()의 insertentitybody 메서드를 호출할 때 발생 하며 Lync Server 2013을 설치 하기 전에 필요 합니다.

**방법을**

Microsoft 다운로드 센터에서 핫픽스를 다운로드 하 여 설치 [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)합니다.

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a>Lync Server 2013을 ITA에 설치 하는 데 실패 했습니다. Windows Server 2012 OS RTM 버전

**문제**

Windows Fabric 설치 오류로 인해 ITA Windows Server 2012에서 Lync Server 2013 설치에 실패 합니다.

HH: MM: SS의 시간 형식으로 패브릭 추적을 만들기 때문에 Windows Fabric 설치가 실패 합니다. 그러나 ITA Windows Server에서 시간 형식은 HH입니다. MM.SS.

**방법을**

이 문제를 해결 하려면 Lync Server 2013을 설치 하기 전에 시스템 레지스트리를 업데이트 합니다. 업데이트 해야 하는 레지스트리 키는 HKEY\_사용자\\입니다. 기본\\제어판\\국제\\sTimeFormat. 다음과 같이 Windows PowerShell 명령줄 인터페이스를 사용 하 여 sTimeFormat 값을 HH: mm: ss로 변경 합니다.

1.  Windows PowerShell을 시작 하 고 다음 cmdlet을 실행 합니다.
    
       ```
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  현재 값을 보려면 다음 cmdlet을 실행 합니다.
    
        Get-itemproperty $a -Name sTimeFormat
    
    설치가 완료 되 면 복원할 수 있도록 sTimeFormat의 현재 값을 기록해 둡니다.

3.  새 값으로 설정 하려면 다음 cmdlet을 실행 합니다.
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  Lync Server 2013가 성공적으로 설치 되 면 다음 cmdlet을 실행 하 여 sTimeFormat의 원래 값을 복원 합니다.
    
        - Set-3 단계에서 적어 둔 ItemProperty $a-Name sTimeFormat-Value "<값. > 위 "

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a>이동성

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a>서버 장애 조치 프로세스 중 모바일 클라이언트 문제

**문제**

Lync Server에 오류가 발생 하 고 장애 조치 프로세스가 시작 되 면 모바일 클라이언트 사용자에 게 다음과 같은 문제가 발생할 수 있습니다.

  - 장애 조치 (failover)가 시작 된 후 최대 10 분 동안 들어오는 Lync 호출이 나 신호가 없습니다.

  - 들어오는 채팅 요청을 수락할 수 없음

  - 실패 한 서버가 사용자의 홈 서버인 경우 모임에 참가할 수 없음

**방법을**

이 문제에 대 한 해결 방법은 없습니다. 장애 조치 프로세스가 완료 되 면 정상 기능이 복원 됩니다.

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a>모바일 사용자가 다른 Lync 끝점에서 걸려오는 전화를 거절 하는 경우 통화가 Lync 모바일 클라이언트에서 부재 중 변환으로 표시 됩니다.

**문제**

모바일 사용자가 수신 전화를 거절 하 고 다른 Lync 끝점에서 통화가 시작 되 면 통화가 장치 통화 목록에 있는 통화 대신 Lync 모바일 클라이언트에 부재 중 대화로 표시 됩니다.

**방법을**

이 문제에 대 한 해결 방법은 없습니다.

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a>모바일 클라이언트가 연락처를 검색할 때 페더레이션된 대화 상대의 표시 이름을 표시 하지 않을 수 있음

**문제**

연락처 목록에서 페더레이션 대화 상대를 검색 하는 경우와 같이 페더레이션 대화 상대의 표시 이름이 일부 시나리오에 표시 되지 않을 수 있습니다. Lync 모바일 클라이언트의 연락처에 대 한 활성 현재 상태 구독이 없는 경우이 문제가 발생할 수 있습니다.

**방법을**

이 문제에 대 한 해결 방법은 없습니다.

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a>모바일 클라이언트에서 회의 초대 인 부재 중 대화에 대 한 초대 대 상자 및 타임 스탬프 정보가 누락 되었습니다.

**문제**

모바일 클라이언트에서 부재 중 대화가 컨퍼런스 초대 인 경우, 초대 대 상자 및 타임 스탬프 정보가 부재 중 대화 메시지에 없습니다.

**방법을**

이 문제에 대 한 해결 방법은 없습니다.

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a>VoIP를 사용 하 여 전화를 걸고 있는 모바일 클라이언트 사용자는 음성 메일이 Exchange 2010 또는 이전 버전에서 구성 된 사용자에 게 음성 메일을 남길 수 없습니다.

**문제**

모바일 클라이언트 사용자가 VoIP를 사용 하 여 전화를 거는 경우 사용자는 Microsoft Exchange Server 2007 또는 Microsoft Exchange Server 2010에서 음성 메일을 사용 하도록 구성 된 사용자에 대해 음성 메일 메시지를 남길 수 없습니다.

**방법을**

이 문제를 해결 하려면 Microsoft Exchange Server SP1 이상 버전에서 Exchange 2010을 사용 하세요.

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a>모바일 클라이언트의 클라이언트 버전 구성에 대 한 URL과 함께 Block을 사용 하는 경우 잘못 된 오류 메시지가 표시 될 수 있습니다.

**문제**

모바일 클라이언트의 클라이언트 버전 구성에 대 한 **URL과 함께 Block** 을 사용 하는 경우 클라이언트 버전이 지원 되지 않는 경우 잘못 된 오류 메시지가 표시 될 수 있습니다.

**방법을**

이 문제를 해결 하려면 **URL을 사용 하 여 블록**대신 **블록** 을 사용 하도록 클라이언트 버전 구성을 구성 합니다.

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a>회의

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a>Lync Server 2013 프런트 엔드 서버에서 실행 되는 바이러스 백신 소프트웨어를 통해 Lync Web App 2013, Lync 모바일 2010 및 Lync 모바일 2013 클라이언트에 대 한 서비스를 일시적으로 중단 하는 응용 프로그램 도메인 재활용이 발생할 수 있습니다.

**문제**

바이러스 백신 소프트웨어는 응용 프로그램 도메인 다시 시작을 트리거할 수 있으며, Lync Mobility Service 2013 및 통합 커뮤니케이션 (UC) Web API 클라이언트 응용 프로그램 (Lync Web App 2013, Lync 모바일 2010 및 Lync Mobile 2013)에서 상태를 잃을 수 있습니다.

**방법을**

이 문제를 해결 하려면 바이러스 백신 검사에서 웹 구성 요소 및 .NET 프레임 워크를 포함 하는 폴더를 제외 합니다. 자세한 내용은 Microsoft 기술 자료 문서 312592, "PRB: 임의 응용 프로그램 다시 시작 '에서 ' 응용 프로그램을 다시 시작 하 고 [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592)있습니다. '의 ASP.NET" 오류 "를 참조 하세요.

다음 폴더를 제외 해야 합니다.

  - % ProgramFiles%\\Microsoft Lync Server 2013\\웹 구성\\요소 mcx\\Ext

  - % ProgramFiles%\\Microsoft Lync Server 2013\\웹 구성\\요소 mcx\\Int

  - % ProgramFiles%\\Microsoft Lync Server 2013\\웹 구성\\요소 및\\wa Int

  - % ProgramFiles%\\Microsoft Lync Server 2013\\웹 구성\\요소 및\\인터넷 확장

  - % Windir%\\Microsoft.NET\\Framework64\\v 4.0.30319\\Config

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a>회의에 성공적으로 참가 하려면 Windows Internet Explorer에서 ActiveX 컨트롤 또는 기본 XMLHTTP 지원 기능을 사용 하도록 설정 해야 합니다.

**문제**

Windows Internet Explorer 인터넷 브라우저 설정에서 사용자가 ActiveX 컨트롤과 기본 XMLHTTP 지원을 모두 비활성화 한 경우 Internet Explorer가 기본 브라우저로 선택 되어 있으면 사용자가 모임에 참가할 수 없습니다.

**방법을**

Internet Explorer에서 ActiveX 컨트롤 또는 "기본 XMLHTTP 지원"을 사용 하도록 설정 합니다.

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a>Lync Server 웹 회의 서비스가 중요 모드에서 복구할 수 없음

**문제**

중요 모드가 보관을 위해 설정 되어 있는 경우 시스템 장애가 발생 하는 경우 중요 모드가 시작 되 고 회의가 더 이상 참가자에 대해 작동 하지 않게 됩니다. 관리자가 데이터베이스 문제 해결 등의 시스템 오류를 해결 한 후에는 데이터 회의 서비스가 자동으로 복구 되지 않으며, 관리자는 회의를 위해 회의 서비스를 수동으로 다시 시작 해야 다시 시작할 수 있습니다.

**방법을**

시스템 장애가 해결 된 후에는 관리자가 회의 서비스를 수동으로 다시 시작 해야 합니다.

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a>웹 회의 서비스는 외부 Office Web App 서버에 대 한 HTTP 프록시를 무시 합니다.

**문제**

웹 회의 서비스 외부 (즉, 내부 회사 네트워크에 있지 않은 서버)에 대 한 Office Web Apps 서버를 인터넷, 주변 네트워크 및 웹 회의 서비스에 배포한 경우 HTTP 프록시를 사용 하 여이를 연결 하는 경우 Office Web Apps Server 검색에 실패 합니다. 웹 회의 서비스는 Office Web Apps 서버 설정에 대 한 토폴로지 작성기에 정의 된 대로 HTTP 프록시 설정을 무시 합니다. 결과적으로 Lync 클라이언트는 전화 회의의 다른 참가자와 Microsoft PowerPoint 2010 공유를 수행할 수 없게 됩니다. Lync Server를 온-프레미스로 설치 하 고 내부 네트워크에서 Office Web Apps 서버를 온-프레미스로 구성 하는 경우 프록시 구성은 필요 하지 않습니다.

**방법을**

유일한 해결 방법은 외부 Office Web Apps 서버와 통신 하는 데 HTTP 프록시를 사용 해야 하는 배포 구성을 사용 하지 않는 것입니다.

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a>오디오 회의 공급자 컨퍼런스에 비디오를 추가 하는 것은 지원 되지 않습니다.

**문제**

사용자가 오디오에 대 한 오디오 회의 공급자 회의에 참가 한 경우 비디오 추가는 지원 되지 않습니다.

**방법을**

이 문제에 대 한 해결 방법은 없습니다.

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a>IPv6을 사용 하는 경우 lync Web App Silverlight 플러그 인 자동 업데이트를 통해 Lync Web App에서 화면 공유 기능을 사용할 수 있는지 확인

**문제**

IPv6을 사용 하도록 설정 된 토폴로지가 있는 경우 이전 버전의 화면 공유 플러그 인이 이미 설치 되어 있는 경우 사용자는 Lync Web App 클라이언트에서 화면을 공유할 수 없습니다.

**방법을**

Lync Web App을 통해 모임에 참가할 때 화면 공유 플러그인의 최신 버전을 강제로 업데이트 하려면 다음 두 파일에서 **MinSupportedBuildVersion** 의 값을 "4.0.7457.0"에서 "4.0.7577.380"로 수정 합니다.

  - % ProgramFiles%\\Microsoft Lync Server 15\\웹 구성\\요소\\는\\Int\\클라이언트\\플러그 인 ReachAppShPluginProperties에 도달 합니다.

  - % ProgramFiles%\\Microsoft Lync Server 15\\웹 구성\\요소\\는\\Ext\\클라이언트\\플러그인 ReachAppShPluginProperties에 도달 했습니다.

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a>Enterprise Voice

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a>IPv4 및 IPv6 이중 스택을 사용 하도록 구성 된 컴퓨터에서 실행 되는 Lync 클라이언트는 E911, 미디어 바이패스, 통화 허용 제어 및 위치 기반 라우팅과 같은 컴퓨터의 IP 서브넷에 의존 하는 기능을 지원 하지 않을 수 있습니다.

<div class="">


> [!NOTE]  
> 이 섹션의 정보는 Lync Server 2013의 누적 업데이트 (2013:2 월)와 관련이 있습니다.



</div>

**문제**

IPv4 및 IPv6 이중 스택에 대해 설정 된 컴퓨터에서 Lync 클라이언트를 실행 하는 경우 프록시 서버의 DNS 확인을 기준으로 하는 경우 클라이언트는 컴퓨터의 IPv6 주소를 사용 하 여 로그인 할 수 있습니다. 이 작업을 수행한 후 Lync 클라이언트는 E911, 미디어 바이패스, 통화 허용 제어 및 위치 기반 라우팅을 제외 하는 IPv6에 대해 지원 되는 기능만 지원 합니다.

**방법을**

이 문제를 해결 하려면 클라이언트 컴퓨터에서 IPv6 지원을 사용 하지 않도록 설정 합니다.

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a>사용자에 대해 Enterprise Voice가 구성 되어 있지 않은 경우 사용자는 E164 형식을 사용 하 여 전화를 걸고 있어야 합니다.

**문제**

사용자에 대해 Enterprise Voice가 구성 되어 있지 않으면 해당 사용자는 E164 형식을 사용 하 여 전화를 성공적으로 종료 해야 합니다. E164 형식이 사용 되지 않으면 사용자가 회의에서 전화를 걸 수 없습니다.

**방법을**

이 문제를 해결 하기 위해 Enterprise Voice를 사용 하도록 설정 하지 않은 사용자는 E164 형식의 숫자를 사용 하 여 전화를 걸 수 있습니다.

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a>현재 상태

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a>사용자가 통합 된 대화 상대 저장소를 사용 하도록 설정 되어 있는 동안 사용자가 "모든 초대 및 통신 차단"을 선택한 경우 현재 상태는 거부 되지 않습니다.

**문제**

사용자가 사용자에 대해 통합 된 대화 상대 저장소를 켠 상태에서 "모든 초대 및 통신 차단"을 선택한 경우 현재 상태는 거부 되지 않습니다.

**방법을**

이 문제를 해결 하려면 해당 사용자의 통합 된 연락처 저장소를 해제할 수 있습니다. 이렇게 하려면 다음 cmdlet을 실행 합니다.

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

예를 들면 다음과 같습니다.

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a>Office Communications Server 2007 R2 온-프레미스 사용자가 하이브리드 배포에서 비즈니스용 Skype Online 사용자의 현재 상태를 볼 수 없음-하이브리드

**문제**

Lync Server 2013 디렉터를 사용 하는 경우 하이브리드 배포에서 문제가 발생할 수 있습니다.

비즈니스용 Skype Online에 속한 사용자의 현재 상태는 온-프레미스 사용자에 게 알려지지 않은 현재 상태가 표시 됩니다. 또한 비즈니스용 Skype Online에 속한 사용자가 Office Communications Server R2 온-프레미스 사용자의 현재 상태를 볼 수 없습니다.

**방법을**

이 문제를 부분적으로 해결 하려면 비즈니스용 Skype Online 사용자의 홈 서버 (msrtcsip-presencehomeserver)를 Lync Server 2013 Director 대신 Lync Server 2013 온-프레미스 풀을 가리키도록 변경 합니다. 온-프레미스 프런트 엔드 서버에서이 설정을 수정할 수 있습니다.

이 해결 방법은 Office Communications Server 2007 R2에 속한 사용자의 현재 상태를 비즈니스용 Skype Online 사용자에 게 올바르게 표시 합니다.

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a>응답 그룹 응용 프로그램, 통화 공원 응용 프로그램, 그룹 통화 픽업

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a>발신자가 파티를 검색 하 여 통화를 설정 하는 동안 음악 대기 중 1 초 동안 들릴 수가 있습니다.

<div class="">


> [!NOTE]  
> 이 섹션의 정보는 Lync Server 2013의 누적 업데이트 (2013:2 월)와 관련이 있습니다.



</div>

**문제**

그룹 통화 픽업을 통해 통화가 검색 되는 경우 검색기 파티와 통화를 설정 하는 동안 발신자가 1 초 동안 음악 대기를 들릴 수 있습니다.

**방법을**

이 문제에 대 한 해결 방법은 없습니다.

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a>응답 그룹 에이전트는 lync Server 2010 에이전트 콘솔을 통해 로그인 하 고 Lync Server 2010 정식 에이전트 그룹만을 통해 로그 아웃할 수 있습니다.

**문제**

Lync Server 2013 응답 그룹 에이전트는 lync server 2010 에이전트 콘솔을 통해 lync server 2010 정식 에이전트 그룹만을 통해 로그인 하 고 로그 아웃할 수 있습니다. Lync Server 2010 에이전트 콘솔에서 사용자는 자신이 속한 Lync Server 2010 응답 그룹만 볼 수 있습니다. 해당 사용자가 속한 Lync Server 2013 응답 그룹은 볼 수 없습니다.

**방법을**

응답 그룹 에이전트가 Lync Server 2013 사용자이 고 Lync Server 2013 정식 에이전트 그룹의 일부인 경우 사용자는 브라우저의 웹 링크를 통해 Lync Server 2013 에이전트 콘솔에 직접 액세스 하 여 Lync Server 2013 Agent 그룹에 로그인 하 고 로그 아웃 해야 합니다.

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a>Lync Server 2010 응답 그룹 에이전트는 Lync Server 2013 응답 그룹을 대신 하 여 전화를 걸 수 없음

**문제**

Lync server 2010 응답 그룹 2013의 에이전트 인 사용자는 응답 그룹을 대신 하 여 전화를 걸 수 없습니다. Lync Server 2013 응답 그룹은 Lync 클라이언트에서 전화를 걸 수 없습니다.

**방법을**

이 문제를 해결 하려면 Lync Server 2010 사용자를 Lync Server 2013로 이동 해야 합니다.

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a>Lync Server 2010에서 응답 그룹을 제거한 2013 후에는 응답 그룹이 들어오는 전화를 수락 하지 못하게 됩니다.

**문제**

Lync server 2010에서 Lync server 2013로 마이그레이션한 응답 그룹이 lync server 제어판 또는 Lync Server Management Shell 2010에서 제거 되는 경우 Lync server 2013의 응답 그룹은 걸려오는 전화 수신을 중지 합니다.

**방법을**

이 문제를 해결 하려면 lync server 2010에서 Lync server 2013으로 마이그레이션한 Lync Server 2010에서 응답 그룹을 제거 하지 마세요.

응답 그룹이 이미 제거 된 경우 Lync Server 2013에서 다시 배포 해야 합니다.

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a>새 관리 워크플로가 생성 될 때 비활성으로 설정 되 면 워크플로 구축이 실패 합니다.

**문제**

새 관리 워크플로가 생성 될 때 비활성으로 설정 된 경우 워크플로 배포는 실패 합니다. 이 문제는 워크플로를 만들 때 비활성으로 설정 했지만 워크플로가 배포 후 비활성으로 설정 되도록 편집 된 워크플로에 영향을 주지 않을 때 발생 합니다.

**방법을**

워크플로를 만들고 배포 하는 경우 워크플로를 활성으로 설정한 다음 배포 합니다. 워크플로가 성공적으로 배포 된 후에는 워크플로를 편집 하 고 비활성으로 설정할 수 있습니다.

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a>응답 그룹을 백업 풀로 가져온 경우 소유자 풀에서 응답 그룹을 제거 하면 장애 조치 (failover) 동안에는 백업 풀의 응답 그룹이 들어오는 전화를 수락 하지 않습니다.

**문제**

소유자를 덮어쓰지 않고 기본 풀에서 소유 하는 응답 그룹을 백업 풀로 가져왔지만 소유자 풀에서 응답 그룹이 제거 되는 경우 백업 풀의 응답 그룹은 장애 조치 동안 들어오는 전화를 수락 하지 않습니다.

**방법을**

응답 그룹을 기본 풀에 다시 배포 해야 합니다. 그런 다음 기본 풀에서 응답 그룹 구성을 내보내고 백업 풀로 다시 가져와야 합니다.

백업 풀에서 응답 그룹을 다시 만들 수도 있습니다. 이 경우 백업 풀은 응답 그룹의 소유자 풀이 됩니다.

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a>응답 그룹을 대신 하 여 검색 요청이 완료 되 면 통화 공원 응용 프로그램에서 파킹 된 통화를 검색할 수 없습니다.

**문제**

다음 조건에 해당 하는 경우 파킹 호출에 대 한 검색 요청이 실패 합니다.

  - 에이전트가 익명 응답 그룹의 일부입니다.

  - 에이전트는 익명 응답 그룹을 통해 통화 공원 응용 프로그램에서 파킹 된 통화를 검색 하려고 시도 합니다.

  - 상담원은 통화 전화 옵션을 통해 궤도 번호로 전화를 걸거나 Lync 수행자 클라이언트의 동일한 옵션을 통해 통화를 검색 하려고 시도 합니다.

**방법을**

이 문제에 대 한 해결 방법은 없습니다. 파킹 통화는 응답 그룹 대신이 작업을 수행 하지 않고 검색 해야 합니다.

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a>Lync Server 컨트롤 패널, 토폴로지 작성기 및 계획 도구

<div>

## <a name="planning-tool-limitations"></a>계획 도구 제한 사항

<div class="">


> [!NOTE]  
> 이 섹션의 정보는 Lync Server 2013의 누적 업데이트 (2013:2 월)와 관련이 있습니다.



</div>

**문제**

계획 도구에는 배포 계획을 세울 때 다음과 같은 제한 사항이 있습니다.

  - 최대 10 개의 중앙 사이트가 지원 됩니다.

  - 각 중앙 사이트는 최대 14 개의 분기 사이트를 가질 수 있습니다.

  - 각 중앙 사이트는 최대 24만 명의 사용자를 가질 수 있습니다.

또한 계획 도구에는 권장 토폴로지를 계산할 때 다음 값이 포함 되지 않습니다.

  - 온라인 상태인 사용자 수

  - XMPP 페더레이션에 대해 사용 하도록 설정 된 사용자의 백분율

  - Lync Web App을 사용 하는 사용자의 백분율

**방법을**

이러한 문제에 대 한 해결 방법은 없습니다. 계획 도구에 대 한 자세한 내용은 [계획 도구를 사용 하 여 Lync Server 2013의 토폴로지 디자인](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md)을 참조 하세요.

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a>계획 도구에서 옵션을 업데이트할 때 Edge 네트워크에 대해 이전에 정의 된 IP 주소를 사용할 수 없음

**문제**

계획 도구를 사용 하 여 디자인을 완료 한 후에 Edge 네트워크 옵션을 변경 하면 기존 IP 주소를 업데이트 하는 대신 추가 IP 주소가 디자인에 추가 될 수 있습니다. 이 문제는 Edge 네트워크 다이어그램의 세부 정보를 볼 때, **여기를 클릭 하 여 옵션을 업데이트**한 다음 구성 옵션 대화 상자에서 edge 네트워크를 선택 하 여 **동일한 fqdn과 IP 주소를 사용 하 려 하지만 edge 서버의 edge 서비스에는 다른 포트**를 선택 하는 경우에 발생할 수 있습니다. 변경 내용을 적용 하면 새 IP 주소와 Edge 서버가 디자인에 추가 될 수 있습니다.

**방법을**

지금은이 문제에 대 한 해결 방법이 없습니다.

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a>Lync Server 제어판에서 "모든 사용자를 풀로 이동"이 예상 대로 작동 하지 않을 수 있음

**문제**

Lync Server 제어판을 사용 하 여 여러 도메인 컨트롤러 및 부모/자식 도메인이 있는 경우와 같이 복잡 한 Active Directory 환경에서 모든 사용자를 한 풀에서 다른 풀로 이동할 때 "지정 된 사용자가 레거시 사용자가 아닌 경우, 아니면 CsUser cmdlet을 대신 사용 합니다." 라는 오류 메시지가 반환 될 수 있습니다. 복잡 한 Active Directory 환경의 복제 시간이 길어질 때의 결과입니다.

**방법을**

이 문제를 해결 하려면 다음 중 하나를 수행 합니다.

  - Lync Server 제어판에서 필터를 사용 하 여 레거시 사용자를 검색 하 고 해당 사용자를 선택한 다음 **모든 사용자를 풀로 이동 하**는 대신 **선택한 사용자를 그룹으로 이동 명령을** 사용 합니다.

  - Lync server Management Shell을 사용 하 여 Lync Server cmdlet을 사용 하 여 레거시 사용자를 일괄적으로 이동 합니다.

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a>Microsoft Silverlight 브라우저 플러그 인이 버전 5로 업데이트 된 후 Lync Server 제어판이 VMware 환경에서 작동을 중지 한다

**문제**

VMware 환경에서 Lync Server 제어판을 사용 하는 경우 Silverlight를 버전 5로 업그레이드 한 후 Lync Server 제어판이 작동 하지 않을 수 있습니다.

**방법을**

이 문제를 해결 하려면 다음 중 하나를 수행 합니다.

  - Silverlight 5를 제거한 다음 Silverlight 4를 설치 [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0)합니다.

  - VMware 가상 컴퓨터가 아닌 컴퓨터에서 Lync Server 제어판을 엽니다.
    
    원격 컴퓨터에서 Lync Server 제어판을 열려면 컴퓨터에 Lync Server 관리 도구를 설치한 다음 Windows **시작** 메뉴에서 Lync server 제어판을 시작 합니다.
    
    웹 브라우저에서 URL을 입력 하 여 Lync Server 제어판을 열 수도 있습니다. \<URL은 https://프런트\_엔드 풀\_fqdn\>/cscp.와 유사 합니다.

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a>토폴로지 작성기에서 미러링 데이터베이스를 제거한 후 관리자가 제거 csMirrorDB cmdlet을 실행할 수 없음

**문제**

관리자가 토폴로지 작성기에서 미러링 데이터베이스를 사용 하지 않도록 설정한 다음 토폴로지 작성기에서 미러링 데이터베이스를 삭제 하면 관리자가 **csMirrorDatabase** cmdlet을 실행 하 여 SQL Server에서 미러링을 제거 하는 메시지가 작업 목록에 표시 됩니다. 관리자가 cmdlet을 실행 하려고 하면 실패 합니다.

**방법을**

토폴로지 작성기에서 풀의 SQL 미러링을 제거 하려면 먼저 cmdlet을 사용 하 여 SQL Server에서 미러를 제거 해야 합니다. 그런 다음 토폴로지 작성기를 사용 하 여 토폴로지에서 미러를 제거할 수 있습니다. SQL Server에서 미러를 제거 하려면 다음 cmdlet을 사용 합니다.

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

예를 들어 미러링을 제거 하 고 사용자 데이터베이스용 데이터베이스를 삭제 하려면 다음을 입력 합니다.

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

*DropExistingDatabasesOnMirror* 매개 변수를 적용 하면 해당 데이터베이스가 미러에서 삭제 됩니다. 그런 다음 토폴로지에서 미러를 제거 하려면 다음을 수행 합니다.

1.  토폴로지 작성기에서 풀을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 합니다.

2.  **SQL 저장소 미러링 사용** 을 선택 취소 하 고 **확인**을 클릭 합니다.

3.  토폴로지를 게시 합니다.

<div class="">


> [!IMPORTANT]  
> 백 엔드 데이터베이스 미러링 관계를 변경할 때마다 풀의 모든 프런트 엔드 서버를 다시 시작 해야 합니다.



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a>관리자가 연결 된 감시 저장소가 있는 프런트 엔드 풀을 사용 하 여 배포를 제거 하려고 하면 토폴로지 작성기에 유효성 검사 오류가 반환 됩니다.

**문제**

관리자가 토폴로지 작성기에서 **배포 제거** 명령을 사용 하 여 연결 된 감시 저장소와 함께 프런트 엔드 풀을 포함 하는 배포를 제거 하려고 하면 토폴로지 작성기에 유효성 검사 오류가 표시 되 고 작업이 진행 되지 않습니다.

**방법을**

이 문제를 해결 하려면 다음 중 하나를 수행 합니다.

  - 배포 제거를 시도 하기 전에 미러링 모니터 저장소를 제거 합니다.

  - 프런트 엔드 풀에 대 한 감시 저장소를 추가한 다음 제거 합니다.

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a>계획 도구와 토폴로지 작성기 간에 영구 채팅 서버 배포 정보가 일치 하지 않음

**문제**

Lync Server 2013에서 계획 도구가 재해 복구를 사용 하는 영구 채팅 서버 배포에 대 한 사이트 토폴로지 다이어그램을 출력 합니다. 사이트 토폴로지 다이어그램에는 여러 개의 (실제) 사이트가 포함 되어 있으며 각 사이트에 일관 되 게 영구 채팅 서버가 할당 되어 있습니다. site. 토폴로지 작성기에서 모든 영구 채팅 서버는 단일 (논리) 사이트에 속하는 것으로 표시 되며 동일한 영구 채팅 서버 풀 노드 아래에 나열 됩니다.

**방법을**

현재이 문제에 대 한 해결 방법은 없습니다. 사용자는 영구 채팅 서버 배포에 대 한 계획 도구의 출력을 분석 하 고 해당 요구 사항에 맞게 계획을 수정 해야 합니다.

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a>지역화

<div>

## <a name="monitoring"></a>모니터링

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a>동아시아 버전의 Lync Server를 사용 하는 경우 모니터링 보고서 배포 마법사에서 특정 상황에 잘못 된 문자가 표시 됨

**문제**

중국어 (간체), 중국어 (번체), 일본어 또는 한국어와 같은 동아시아 버전의 Lync Server 2013을 사용 하는 경우 시스템 로캘이 동아시아 언어로 설정 되지 않은 운영 체제에서는 모니터링 보고서 배포 마법사가 지역화 된 메시지 대신 물음표 또는 다른 문자를 표시 합니다.

**방법을**

이 문제를 해결 하려면 운영 체제 및 Lync Server 2013의 로케일을 동일한 언어로 설정 하 고 모든 메시지가 올바르게 표시 되도록 합니다.

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a>Lync Server 제어판

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a>경우에 따라 맨 위 탐색 모음의 마지막 항목을 클릭 하면 Lync Server 제어판의 페이지 위쪽 탐색 모음에 있는 첫 번째 항목이 사라집니다.

**문제**

Lync Server 제어판 페이지의 위쪽 탐색 모음에 있는 마지막 항목을 클릭 하면 위쪽 탐색 모음의 첫 번째 항목이 사라질 수 있는 세 가지 상황이 있습니다.

  - 프랑스어 버전의 "Féderation et accès externe" 페이지에서 "Partenaires d'accès XMPP"를 클릭 하면 "Stratégie externe fédérés" 항목이 사라집니다.

  - 독일어 버전의 "클라이언트" 페이지에서 "Pushbenachrichtigungskonfiguration"을 클릭 하면 "Clientversionskonfiguration" 항목이 사라집니다.

  - 러시아어 버전의 "Конфигурация сети" 페이지에서 "Маршрут региона"을 클릭 하면 "Глобально" 항목이 사라집니다.

**방법을**

이 문제를 해결 하려면 브라우저에서 Lync Server 제어판의 페이지를 새로 고칩니다. 위쪽 탐색 모음의 모든 항목이 표시 된 상태로 브라우저에 페이지가 로드 됩니다.

</div>

</div>

<div>

## <a name="address-book"></a>주소록

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a>일부 언어에서는 주소록의 색인이 예상 대로 작동 하지 않음

<div class="">


> [!NOTE]  
> 이 섹션의 정보는 Lync Server 2013의 누적 업데이트 (2013:2 월)와 관련이 있습니다.



</div>

사용자의 속성에 인덱싱된 필드가 포함 되어 있고이 필드에 인덱스할 수 없는 문자만 있으면 주소록에서 수행한 검색에 사용자가 표시 되지 않습니다.

다음 문자 및 로캘을 인덱싱할 수 없습니다.

  - 대문자 키릴 자모, 그리스어, 아르메니아어 문자

  - 대문자를 악센트 부호가 있는 문자

  - 태국어

  - 라오스

  - 미얀마

  - 데바나가리 문자

  - Ethiopic

  - 티베트어

  - 벵골어

  - 구자라트어

  - 텔루구어

  - 다른 모든 인도어 스크립트

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a>Lync Web App, 웹 스케줄러, 웹 구성 요소

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a>Lync Web Scheduler, 전화 접속, 참가 시작 관리자, 영구 채팅방 관리, OCTab의 특정 언어에 대 한 언어 대체 기능이 예상 대로 작동 하지 않을 수 있음

**문제**

Internet Explorer에서 웹 브라우저의 중립 로캘을 선택 하는 경우 예 \[를 들어 언어\] \[\]이름에 "노르웨이어 no"와 같은 추가 사양이 지정 된 경우, "노르웨이어 no"와 같은 "라틴어 no"와 같이, Lync Web Scheduler, 전화 접속, 참가 시작 관리자, 영구 채팅방 관리, ocx 탭의 특정 언어에 대 한 예기치 않은 표시 동작을 야기할 수 있습니다. 예를 들어 다음 언어 중 하나를 선택 하면 사용자에 게 영어 페이지가 표시 될 수 있습니다.

  - 노르웨이어

  - 포르투갈어

  - 세르비아어

**방법을**

중립 로캘을 사용 하 여 언어를 선택 하려는 경우에는 브라우저의 언어 기본 설정 목록에서 특정 로케일 (스크립트 및/또는 국가 코드 포함)을 추가 언어로 사용 하 여 언어를 추가 하는 것도 항상 가능 합니다.

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a>일부 웹 브라우저에서 Lync 웹 스케줄러, 전화 접속, 참가 시작 관리자, 영구 채팅방 관리, Ocx 탭을 사용 하는 경우 아제리어 및 우즈베크어 로캘이 제한적으로 지원 됩니다.

<div class="">


> [!NOTE]  
> 이 섹션의 정보는 Lync Server 2013의 누적 업데이트 (2013:2 월)와 관련이 있습니다.



</div>

**문제**

Internet Explorer 8 또는 Internet Explorer 9를 사용 하 고 브라우저 언어를 아제리어 (라틴 문자) 또는 우즈베크어 (라틴 문자)로 설정 하면 전화 접속 및 참가 시작 관리자 페이지가 영어 또는 브라우저의 기본 설정 언어로 표시 됩니다.

Firefox 또는 Chrome 브라우저를 사용 하는 경우 브라우저 언어를 아제리어 (라틴 문자) 또는 우즈베크어 (라틴 문자)로 설정 하면 Lync Web App, Lync 웹 스케줄러 및 RGS 탭이 브라우저에 대 한 영어 또는 기본 설정 언어에 표시 됩니다.

우즈베크어 (라틴 문자) 로캘은 Safari 브라우저에서 지원 되지 않습니다.

**방법을**

이러한 문제에 대 한 해결 방법은 없습니다.

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a>루마니아어 버전의 Lync Web App에서 "모임 참가 중" 목록의 드롭다운 화살표가 누락 됨

**문제**

루마니아어 버전의 Lync Web App을 사용 하는 사용자가 다음 단계를 수행 하는 경우 드롭다운 목록에 **참가 모임** 에 대 한 드롭다운 화살표가 표시 되지 않습니다.

1.  **일반** 탭에서 **이 컴퓨터에** 자동으로 이름 입력을 선택 합니다.

2.  **전화** 탭을 선택 합니다.

3.  **모임 참가**의 드롭다운 목록을 클릭 합니다.
    
    사용자는 기본 **Lync 웹 앱**( **예: 루마니아어** , "뉴 se asociaža la componenta Audio") 및 **새 번호**"(루마니아어" Număr nou ") 보다 더 많은 옵션이 있음을 나타내는 화살표가 표시 되지 않습니다.

**방법을**

이 드롭다운 목록의 화살표는 표시 되지 않지만 사용자는 기본 값을 클릭 하 여 목록에서 추가 설정을 선택할 수 있습니다.

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a>터키어 버전의 Lync Web Scheduler를 사용 하는 경우 "발표자의 사용자 선택" 옵션을 사용 하는 경우 모임을 저장할 수 없습니다.

**문제**

터키어 버전의 Lync 웹 스케줄러에서 모임을 만들거나 편집할 때 "발표자 인 사용자"의 선택 옵션은 지원 되지 않습니다. 이 옵션을 선택 하면 모임을 저장할 수 없습니다. 대신 한 명 이상의 사용자가 발표자를 수행할 수 없음을 나타내는 오류 메시지가 나타납니다.

**방법을**

이 문제를 해결 하려면 사용자가 "내 회사의 피플"의 기본 옵션을 사용 하거나 "유일한 이끌이" 또는 "회사 외부의 사용자를 포함 한 모든 사용자"와 같은 다른 선택 항목을 사용할 수 있습니다. 이끌이는 나중에 모임에 참가 한 후에 사용자를 올바른 역할로 내리거나 올릴 수 있습니다.

또는 다른 언어를 이해 하는 사용자는 브라우저의 언어 선택을 다른 43 지원 언어 중 하나로 변경 하 고 "선택한 사람 선택" 옵션을 사용해 볼 수 있습니다.

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a>저작권

이 문서는 최종 상용 발매 이전에는 대폭 변경 될 수 있는 소프트웨어 제품의 예비 릴리스를 지원 하며, Microsoft Corporation의 기밀 및 독점 정보입니다. 이는 받는 사람과 Microsoft 간의 비밀 없는 계약에 따라 공개 됩니다. 이 문서는 정보용 으로만 제공 되며 Microsoft는이 문서에서 명시적 또는 묵시적으로 어떠한 보증도 하지 않습니다. URL 및 기타 인터넷 웹 사이트 참조를 비롯 한이 문서의 정보는 예 고 없이 변경 될 수 있습니다. 이 문서를 사용 하는 경우의 모든 위험성 또는 결과는 사용자에 게 남아 있습니다. 다른 언급이 없는 한, 용례에 나와 있는 회사, 기관, 제품, 도메인 이름, 전자 메일 주소, 로고, 사람, 장소 및 이벤트는 실제 데이터가 아닙니다. 어떠한 실제 회사, 기관, 제품, 도메인 이름, 전자 메일 주소, 로고, 사람, 위치 또는 이벤트와도 연관 시킬 의도가 없으며 그렇게 유추 해서도 안 됩니다. 해당 저작권법을 준수 하는 것은 사용자의 책임입니다. 저작권에서의 권리와는 별도로,이 문서의 어떠한 부분도 검색 시스템에 저장 또는 도입 되거나, 어떠한 형태나 수단 (전기적, 기계적, 복사기에의 한 복사, 기록 또는 다른 방법) 또는 용도에 따라 전송 될 수 없습니다. Microsoft Corporation의 명시적인 서 면 승인 권한이 없는 경우

Microsoft는이 문서에서 다루는 주제에 대 한 특허권, 특허권, 상표권, 저작권 또는 기타 지적 재산권을 가질 수 있습니다. Microsoft의 작성 된 라이선스 계약에 명시적으로 제공 되는 경우를 제외 하 고,이 문서의 제공은 이러한 특허권, 상표, 저작권 또는 기타 지적 재산권에 대 한 라이선스를 제공 하지 않습니다.

© 2012 Microsoft Corporation. 모든 rights reserved.

Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook, SQL Server는 미국 및/또는 기타 국가/지역에서 Microsoft Corporation의 등록 상표 또는 상표 중 하나입니다.

다른 모든 상표는 해당 소유주의 재산입니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

